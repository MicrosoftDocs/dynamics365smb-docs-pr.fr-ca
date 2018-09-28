---
title: "Détails de conception - Coût moyen | Microsoft Docs"
description: "Le coût moyen d'un article est calculé avec une moyenne pondérée périodique, selon la période coût moyen qui est paramétrée dans Business Central."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 5c87d33bbf9d97f53e033c663532052c8aeddee9
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-average-cost"></a>Détails de conception : coût moyen
Le coût moyen d'un article est calculé avec une moyenne pondérée périodique, selon la période coût moyen qui est paramétrée dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

 La date d'évaluation est définie automatiquement.  

## <a name="setting-up-average-cost-calculation"></a>Configuration du calcul du coût moyen  
 Le tableau suivant décrit les deux champs de la fenêtre **Paramètres stock** qui doivent être renseignés pour activer le calcul du coût moyen.  

|Champ|Description|  
|---------------------------------|---------------------------------------|  
|**Période de coût moyen**|Spécifie à quel moment le coût moyen est calculé. Les options possibles sont les suivantes :<br /><br /> -   **Jour**<br />-   **Semaine**<br />-   **Mois**<br />-   **Période comptable**<br /><br /> Le coût moyen calculé pour cette période est affecté à toutes les diminutions d'inventaire reportées au cours de la période coût moyen.|  
|**Type calcul coût moyen**|Indique le mode de calcul du coût moyen. Les options possibles sont les suivantes :<br /><br /> -   **Article**<br />-   **Article, variante et magasin**<br />     Avec cette option, le coût moyen est calculé pour chaque article, pour chaque emplacement et pour chaque variante de l'article. Cela signifie que le coût moyen de cet article dépend du lieu de stockage et de la variante de l'article que vous avez sélectionnés (par exemple, la couleur).|  

> [!NOTE]  
>  Vous pouvez uniquement utiliser une période de coût moyen et un type de calcul de coût moyen dans une année fiscale.  
>   
>  La fenêtre **Périodes comptables** affiche la période coût moyen et le type de calcul du coût moyen qui est en vigueur au cours de la période, pour chaque période comptable.  

## <a name="calculating-average-cost"></a>Calcul du coût moyen  
 Lorsque vous validez une transaction pour un article qui utilise la méthode évaluation stock coût moyen, une écriture est créée dans la table **Point d'entrée ajustement coût moyen**. Cette écriture contient le numéro d'article, le code variante et le code d'emplacement de la transaction. L'écriture contient également le champ **Date évaluation**, qui spécifie la dernière date de la période coût moyen dans laquelle la transaction a été validée.  

> [!NOTE]  
>  Ce champ ne doit pas être confondu avec le champ **Date évaluation** dans le tableau **Ecritures valeur** qui indique la date à laquelle la valeur entre en vigueur et est utilisé pour déterminer la période de coût moyen à laquelle l'écriture valeur appartient.  

 Le coût moyen d'une transaction est calculé lorsque le coût de l'article est ajusté. Pour plus d'informations, voir [Détails de conception : modes évaluation stock](design-details-cost-adjustment.md). Un ajustement des coûts utilise les écritures de la table **Point d'entrée ajustement coût moyen** pour identifier les articles (ou articles, emplacements et variantes) pour lesquels calculer les coûts moyens. Pour chaque écriture dont le coût n'a pas été ajusté, l'ajustement des coûts utilise ce qui suit pour déterminer le coût moyen :  

-   calcul du coût de l'article au début de la période coût moyen ;  
-   Ajoute la somme des coûts entrants reportés au cours de la période de coût moyen. Ceux-ci incluent les achats, les retours vente, les ajustements positifs, et les résultats de production et d'assemblage.  
-   Soustrait la somme des coûts des transactions sortantes ayant été affectées de manière fixe à des réceptions au cours de la période de coût moyen. Ceux-ci incluent généralement des retours achat et les sorties négatives.  
-   Divise par la quantité d'inventaire totale pour la fin de la période coût moyen, sans les sorties d'inventaire qui sont évaluées.  

 Le coût moyen calculé est ensuite appliqué aux diminutions d'inventaire pour l'article (ou article, emplacement et variante) avec des dates de report qui surviennent au cours de la période coût moyen. S'il y a des augmentations d'inventaire affectées de façon fixe à des diminutions d'inventaire au cours de la période coût moyen, le calcul du coût moyen est transmis de l'augmentation à la diminution.  

### <a name="example-average-cost-period--day"></a>Exemple : période coût moyen = jour  
 L'exemple suivant montre l'effet du calcul du coût moyen basé sur une période coût moyen d'un jour. Le champ **Type calcul coût moyen** de la fenêtre **Paramètres stock** est défini sur **Article**.  

 Le tableau suivant montre les écritures article pour un exemple d'article de coût moyen, ARTICLE1, avant que le traitement en lot **Ajuster coûts - Écr. article** ne soit exécuté.  

|**Date de report**|**Type d'écriture gr. livre art.**|**Quantité**|**Coût indiqué (réel)**|**N° séquence**|  
|---------------------------------------|---------------------------------------------------|------------------------------------|----------------------------------------------------|------------------------------------|  
|01/01/20|Achat|1|20.00|1|  
|01/01/20|Achat|1|40.00|2|  
|01/01/20|Vente|-1|-20,00|3|  
|01/02/20|Vente|-1|-40,00|4|  
|02/02/20|Achat|1|100.00|5|  
|03/02/20|Vente|-1|-100,00|6|  

> [!NOTE]  
>  Comme l'ajustement des coûts ne s'est pas encore produit, les valeurs du champ **Coût indiqué (réel)** des diminutions d'inventaire correspondent aux augmentations d'inventaire auxquelles elles sont affectées.  

 Le tableau suivant montre les écritures de la table **Point d'entrée ajustement coût moyen** qui s'appliquent aux écritures valeur résultant des écritures comptables article dans la table précédente.  

|**N° article**|**Code variante**|**Code d'emplacement**|**Date évaluation**|**Coût ajusté**|  
|-------------------------------------|-----------------------------------------|------------------------------------------|-------------------------------------------|---------------------------------------------|  
|ARTICLE1||BLEU|01/01/20|Non|  
|ARTICLE1||BLEU|01/02/20|Non|  
|ARTICLE1||BLEU|02/02/20|Non|  
|ARTICLE1||BLEU|03/02/20|Non|  

 Le tableau suivant montre les mêmes écritures article une fois le traitement en lot **Ajuster coûts - Écr. article** exécuté. Le coût moyen par jour est calculé et affecté aux diminutions d'inventaire.  

|**Date de report**|**Type d'écriture gr. livre art.**|**Quantité**|**Coût indiqué (réel)**|**N° séquence**|  
|---------------------------------------|---------------------------------------------------|------------------------------------|----------------------------------------------------|------------------------------------|  
|01/01/20|Achat|1|20.00|1|  
|01/01/20|Achat|1|40.00|2|  
|01/01/20|Vente|-1|-30,00|3|  
|01/02/20|Vente|-1|-30,00|4|  
|02/02/20|Achat|1|100.00|5|  
|03/02/20|Vente|-1|-100,00|6|  

### <a name="example-average-cost-period--month"></a>Exemple : période coût moyen = mois  
 L'exemple suivant montre l'effet du calcul du coût moyen basé sur une période coût moyen d'un mois. Le champ **Type calcul coût moyen** de la fenêtre **Paramètres stock** est défini sur **Article**.  

 Si la période coût moyen est d'un mois, une seule écriture est créée pour chaque combinaison du numéro article, code variante, code d'emplacement et date évaluation.  

 Le tableau suivant montre les écritures article pour un exemple d'article de coût moyen, ARTICLE1, avant que le traitement en lot **Ajuster coûts - Écr. article** ne soit exécuté.  

|**Date de report**|**Type d'écriture gr. livre art.**|**Quantité**|**Coût indiqué (réel)**|**N° séquence**|  
|---------------------------------------|---------------------------------------------------|------------------------------------|----------------------------------------------------|------------------------------------|  
|01/01/20|Achat|1|20.00|1|  
|01/01/20|Achat|1|40.00|2|  
|01/01/20|Vente|-1|-20,00|3|  
|01/02/20|Vente|-1|-40,00|4|  
|02/02/20|Achat|1|100.00|5|  
|03/02/20|Vente|-1|-100,00|6|  

> [!NOTE]  
>  Comme l'ajustement des coûts ne s'est pas encore produit, les valeurs du champ **Coût indiqué (réel)** des diminutions d'inventaire correspondent aux augmentations d'inventaire auxquelles elles sont affectées.  

 Le tableau suivant montre les écritures de la table **Point d'entrée ajustement coût moyen** qui s'appliquent aux écritures valeur résultant des écritures comptables article dans la table précédente.  

|**N° article**|**Code variante**|**Code d'emplacement**|**Date évaluation**|**Coût ajusté**|  
|-------------------------------------|-----------------------------------------|------------------------------------------|-------------------------------------------|---------------------------------------------|  
|ARTICLE1||BLEU|31/01/20|Non|  
|ARTICLE1||BLEU|28/02/20|Non|  

> [!NOTE]  
>  La date d'évaluation est définie au dernier jour de la période de coût moyen, qui est dans ce cas le dernier jour du mois.  

 Le tableau suivant montre les mêmes écritures article une fois le traitement en lot **Ajuster coûts - Écr. article** exécuté. Le coût moyen par mois est calculé et affecté aux diminutions d'inventaire.  

|**Date de report**|**Type d'écriture gr. livre art.**|**Quantité**|**Coût indiqué (réel)**|**N° séquence**|  
|---------------------------------------|---------------------------------------------------|------------------------------------|----------------------------------------------------|------------------------------------|  
|01/01/20|Achat|1|20.00|1|  
|01/01/20|Achat|1|40.00|2|  
|01/01/20|Vente|-1|-30,00|3|  
|01/02/20|Vente|-1|-65,00|4|  
|02/02/20|Achat|1|100.00|5|  
|03/02/20|Vente|-1|-65,00|6|  

 Le coût moyen pour l'entrée numéro 3 est calculé dans la période coût moyen pour janvier, et le coût moyen pour les écritures 4 et 6 est calculé dans la période coût moyen pour février.  

 Pour obtenir le coût moyen pour février, le coût moyen de la pièce reçue dans l'inventaire (100,00) est ajouté au coût moyen au début de la période (30,00). La somme des deux (130,00) est ensuite divisée par la quantité totale en inventaire (2) ce qui permet d'obtenir le coût moyen de l'article dans la période de février (65,00). Le coût moyen est affecté aux diminutions d'inventaire dans la période (écritures 4 et 6).  

## <a name="setting-the-valuation-date"></a>Définition de la date d'évaluation  
 Le champ **Date évaluation** de la table **Ecritures valeur** permet de déterminer à quelle période coût moyen appartient une écriture de sortie de stock. Ceci s'applique à l'inventaire travail en cours (TEC).  

 Le tableau suivant montre les critères utilisés pour définir la date évaluation.  

|Scénario|Date de report|Quantité valorisée|Réévaluation|Date évaluation|  
|--------------|-------------------------------------|-----------------------------------------|-----------------|-----------------------------------------|  
|1||Positif|Non|Date de report de l'écriture du grand livre d'articles|  
|2|Ultérieur à la dernière date évaluation des écritures valeur affectées|Négatif|Non|Date de report de l'écriture du grand livre d'articles|  
|3|Antérieur à la dernière date évaluation des écritures valeur affectées|Positif|Non|Dernière date évaluation des écritures valeur affectées|  
|4||Négatif|Oui|Date de report de l'écriture valeur de réévaluation.|  

### <a name="example"></a>Exemple :  
 Le tableau suivant d'écritures valeur illustre les différents scénarios.  

|Scénario|Date de report|Type d'écriture gr. livre art.|Date évaluation|Quantité valorisée|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|--------------|-------------------------------------|-----------------------------------------------|-----------------------------------------|-----------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|1|01/01/20|Achat|01/01/20|2|20.00|1|1|  
|2|15/01/20|(Frais annexes)|01/01/20|2|8.00|1|2|  
|3|01/02/20|Vente|01/02/20|-1|-14,00|2|3|  
|4|01/03/20|(Réévaluation)|01/03/20|1|-.4,00|1|4|  
|5|01/02/20|Vente|01/03/20|-1|-10,00|3|5|  

> [!NOTE]  
>  Dans le numéro d'écriture 5 de la table précédente, l'utilisateur a entré un document de vente avec une date de report (02-01-20) qui est antérieure à la dernière date évaluation des écritures valeur affectées (03-01-20). Si la valeur correspondante dans le champ **Coût indiqué (réel)** pour cette date (02-01-20) a été utilisée pour cette écriture, elle correspond à 14,00. Cela donnerait une situation où la quantité en inventaire est égale à zéro, mais la valeur inventaire est de -4.00.  
>   
>  Pour éviter une telle erreur quantité-valeur, la date d'évaluation est configurée pour être égale à la dernière date évaluation des écritures valeur affectées (03-01-20). La valeur du champ **Coût indiqué (réel)** devient 10,00 (après appréciation), ce qui signifie que la quantité en inventaire est égale à zéro, et la valeur d'inventaire est également zéro.  

> [!CAUTION]  
>  Comme le rapport **Évaluation de l'inventaire** est basé sur la date de report, le rapport reflète toutes les erreurs de correspondance de quantité-valeur dans les scénarios comme dans l'exemple ci-dessus. Pour plus d'informations, voir [Détails de conception : évaluation du stock](design-details-inventory-valuation.md).  

 Si la quantité en inventaire est inférieure à zéro après avoir reporté la diminution d'inventaire, la date évaluation est d'abord définie sur la date de report de la diminution d'inventaire. Cette date peut être modifiée plus tard, en fonction des règles décrites dans la remarque précédente dans cette section, lorsque l'augmentation d'inventaire est appliquée.  

## <a name="recalculating-average-cost"></a>Recalcul du coût moyen  
 L'évaluation des diminutions d'inventaire en tant que moyenne pondérée serait directe si les achats étaient toujours facturés avant la facturation des ventes, que les reports n'étaient jamais antidatés, et que vous ne commettiez jamais d'erreurs. Toutefois, la réalité est un peu différente de cet idéal.  

 Comme cela est illustré dans les exemples de cette rubrique, la date d'évaluation est définie comme la date à partir de laquelle l'écriture valeur est incluse dans le calcul du coût moyen. Cela vous offre la flexibilité d'effectuer les opérations suivantes pour les articles utilisant la méthode évaluation coût Moyen :  

-   Facturer la vente d'un article avant que l'achat de l'article aient été facturé.  
-   Antidater un report.  
-   Rétablir un report incorrect.  

> [!NOTE]  
>  Un autre motif de cette flexibilité est l'affectation fixe. Pour plus d'informations sur le lettrage fixe, voir [Détails de conception : lettrage article](design-details-item-application.md).  

 En raison de cette flexibilité, vous pouvez être amené à recalculer le coût moyen après que le report associé s'est produit. Par exemple, si vous reportez une augmentation ou diminution d'inventaire avec une date évaluation antérieure à une ou plusieurs diminutions d'inventaire. Le nouveau calcul du coût moyen s'effectue automatiquement lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**, manuellement ou automatiquement.  

 Vous pouvez modifier la base d'évaluation du stock au cours d'une période comptable en modifiant le champ **Période coût moyen** et le champ **Type calcul coût moyen**. Cependant, cette action doit être menée avec soin et en accord avec un auditeur.  

### <a name="example"></a>Exemple :  
 L'exemple suivant illustre la manière dont le coût moyen est recalculé lorsqu'un report en retard est introduit à une date qui se trouve avant une ou plusieurs diminutions d'inventaire. L'exemple est basé sur une période coût moyen **Jour**.  

 Le tableau suivant montre les écritures valeur qui existent pour l'article avant le report.  

|Date évaluation|Quantité|Coût indiqué (réel)|N° séquence |  
|-----------------------------------------|--------------------------------|------------------------------------------------|----------------------------------|  
|01/01/20|1|10.00|1|  
|02/01/20|1|20.00|2|  
|15/02/20|-1|-15,00|3|  
|16/02/20|-1|-15,00|4|  

 L'utilisateur reporte une augmentation d'inventaire (écriture numéro 5) avec une date évaluation (01-03-20) intervenant avant une ou plusieurs diminutions d'inventaire. Pour équilibrer l'inventaire, le coût moyen doit être recalculé et ajusté à 17.00.  

 Le tableau suivant montre les écritures valeur qui existent pour l'article après la saisie du numéro de séquence 5.  

|Date évaluation|Quantité|Coût indiqué (réel)|N° séquence |  
|-----------------------------------------|--------------------------------|------------------------------------------------|----------------------------------|  
|01/01/20|1|10.00|1|  
|02/01/20|1|20.00|2|  
|03/01/20|1|21.00|5|  
|15/02/20|-1|-17,00|3|  
|16/02/20|-1|-17,00|4|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : modes évaluation stock](design-details-costing-methods.md)   
 [Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)   
 [Détails de conception : lettrage article](design-details-item-application.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

