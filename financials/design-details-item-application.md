---
title: "Détails de conception - Affectation article | Microsoft Docs"
description: "Cette rubrique décrit où la quantité et la valeur d'inventaire sont enregistrées lorsque vous reportez une transaction inventaire."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, items, ledger entries, posting, inventory
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: e8b3015cfbf9c474d49d2e3dab6e3397e6ad6c80
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-item-application"></a>Détails de conception : affectation article
Lorsque vous reportez une transaction d'inventaire, le report de quantité est enregistré dans les écritures article, le report de valeur dans les écritures valeur. Pour plus d'informations, voir [Détails de conception : comptabilisation stock](design-details-inventory-posting.md).  

De même, une affectation article est effectuée pour lier le destinataire de coût à sa source de coût pour assurer le transfert de coûts en fonction du mode d'évaluation coût. Pour plus d'informations, [Détails de conception : modes évaluation stock](design-details-costing-methods.md).  

[!INCLUDE[d365fin](includes/d365fin_md.md)] effectue deux types de lettrage article.  

|Type d'affectation|Description|  
|----------------------|---------------------------------------|  
|Quantité affectée|Créé pour toutes les transactions d'inventaire|  
|Coût affecté|Créé pour les écritures entrantes conjointement avec une quantité affectée, en tant que résultat de l'interaction utilisateur dans des processus spécifiques.|  

Les lettrages article peuvent être effectués des manières suivantes.  

|Méthode|Description|Type d'affectation|  
|------------|---------------------------------------|----------------------|  
|Automatique|Se produit en tant que transfert de coûts général selon le mode évaluation stock|Quantité affectée|  
|Statique|Effectué par l'utilisateur lorsque :<br /><br /> \-   Traitement des retours<br />\-   Report de corrections<br />\-   Annulation des validations de quantité<br />-   Création de livraisons directes **Remarque :**  L'affectation fixe peut être effectuée manuellement en saisissant un numéro d'écriture dans le champ **Écriture article à affecter** ou à l'aide d'une fonction, telle que **Extraire les lignes de document reportées à inverser**.|Quantité affectée<br /><br /> Affectation coût **Remarque :**  L'affectation coût se produit uniquement dans les transactions entrantes dont le champ **Écriture article à affecter** est renseigné pour créer une affectation fixe. Consultez la table suivante.|  

L'affectation de quantités ou de coûts dépend de la direction de la transaction d'inventaire et de si l'affectation d'article est automatique ou fixe, en fonction des processus spécifiques.  

Le tableau suivant montre, à l'aide des champs d'affectation principaux sur les lignes de mouvement d'inventaire, la manière dont les coûts circulent en fonction de la direction de la transaction. Il indique aussi la date et la raison pour laquelle l'affectation article est de type quantité ou coût.  

||Champ Écr. article à lettrer|Champ Écriture article à lettrer|  
|-|--------------------------------|----------------------------------|  
|Affectation pour écriture sortante|L'écriture sortante extrait le coût de l'écriture entrante ouverte.<br /><br /> **Lettrage de quantité**|Non pris en charge|  
|Affectation pour écriture entrante|L'écriture entrante impose le coût sur l'écriture sortante ouverte.<br /><br /> L'écriture entrante est la source du coût.<br /><br /> **Lettrage de quantité**|L'écriture entrante extrait le coût de l'écriture sortante. **Remarque :** Lors de la réalisation de cette application fixe, la transaction entrante est traitée comme retour vente. Par conséquent, l'écriture sortante affectée reste ouverte. <br /><br /> L'écriture entrante n'est PAS la source du coût.<br /><br /> **Coût lettré**|  

> [!IMPORTANT]  
>  Un retour vente n'est PAS considéré comme une source de coût quand il est affecté de façon fixe.  
>   
>  L'écriture vente reste ouverte jusqu'à ce que la source réelle soit reportée.  

Une écriture d'affectation article enregistre les informations suivantes.  

|Champ|Description|  
|---------------------------------|---------------------------------------|  
|**N° écriture article gr. livre**|Le numéro de l'écriture article correspondant à la transaction pour laquelle cette écriture d'affectation est créée.|  
|**N° écriture article entrant**|Numéro d'écriture article de l'augmentation d'inventaire à laquelle la transaction doit être liée, le cas échéant.|  
|**N° écriture article sortant**|Numéro d'écriture article de la diminution d'inventaire à laquelle la transaction doit être liée, le cas échéant.|  
|**Quantité**|Quantité affectée.|  
|**Date de validation**|Date de report de la transaction.|  

## <a name="inventory-increase"></a>Augmentation d'inventaire  
Lorsque vous reportez une augmentation d'inventaire, une simple écriture d'affectation article est enregistrée sans affectation à une écriture sortante.  

### <a name="example"></a>Exemple :  
Le tableau suivant montre l'écriture d'affectation article qui est créée lorsque vous reportez une réception achat de 10 unités.  

|Date de report|N° écriture article entrant|N° écriture article sortant|Quantité|N° écriture article gr. livre|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|01/01/20|1|0|10|1|  

## <a name="inventory-decrease"></a>Diminution d'inventaire  
Lorsque vous reportez une diminution d'inventaire, une écriture d'affectation article qui lie la diminution d'inventaire à une augmentation d'inventaire est créée. Ce lien est créé en utilisant le mode évaluation stock de l'article comme base d'instructions. Pour les articles utilisant les modes évaluation du stock FIFO, standard, et moyen, le lien est basé sur le principe du premier entré, premier sorti. La diminution d'inventaire est affectée avec l'augmentation d'inventaire ayant la date de report future la plus proche. Pour les articles utilisant le mode évaluation stock LIFO, le lien est basé sur le principe du dernier entré, premier sorti. La diminution d'inventaire est affectée à l'augmentation d'inventaire ayant la date de report passée la plus récente.  

Dans la table **Ecriture article**, le champ **Quantité restante** présente la quantité qui n'a pas encore été lettrée. Si la quantité restante est supérieure à 0, la case à cocher **Ouvrir** est activée.  

### <a name="example"></a>Exemple :  
L'exemple suivant montre l'écriture d'affectation article créée lors du report d'une livraison vente de 5 unités des articles réceptionnés dans l'exemple précédent. La première écriture d'affectation article est la réception achat. La deuxième écriture d'affectation est la livraison vente.  

Le tableau suivant montre les deux écritures d'affectation article qui résultent respectivement de l'augmentation de la diminution d'inventaire.  

|Date de report|N° écriture article entrant|N° écriture article sortant|Quantité|N° écriture article gr. livre|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|01/01/20|1|0|10|1|  
|03/01/20|1|2|-5|2|  

## <a name="fixed-application"></a>Affectation fixe  
Vous effectuez une affectation fixe lorsque vous spécifiez que le coût d'une augmentation d'inventaire doit être affecté à une diminution d'inventaire spécifique ou inversement. Cette affectation fixe influence les quantités restantes des écritures, mais l'affectation fixe inverse également le coût exact de l'écriture d'origine sur laquelle vous affectez (ou à partir de laquelle vous affectez).  

Pour créer une affectation fixe, vous utilisez les champs **Écr. article à affecter** ou **Écriture article à affecter** des lignes document pour spécifier l'écriture article vers laquelle (ou à partir de laquelle) vous souhaitez affecter la ligne transaction. Par exemple, vous pouvez effectuer une affectation fixe lorsque vous voulez créer un coût affecté qui spécifie qu'un retour vente doit être affecté à une livraison vente spécifique afin d'inverser le coût de la livraison vente. Dans ce cas, [!INCLUDE[d365fin](includes/d365fin_md.md)] ignore le mode d'évaluation du stock et lettre la sortie de stock (ou l'entrée de stock en cas de retour vente) sur l'écriture comptable article que vous spécifiez. L'avantage d'effectuer une affectation fixe est que le coût de la transaction initiale est transmis à la nouvelle transaction.  

### <a name="example--fixed-application-in-purchase-return"></a>Exemple – affectation fixe dans le retour achat  
L'exemple suivant, qui illustre l'effet de l'affectation fixe d'un retour achat d'un article utilisant le mode d'évaluation coût FIFO, est basé sur le scénario suivant :  

1. Dans le numéro de séquence 1, l'utilisateur reporte un achat à un coût de 10,00 $.  
2. Dans le numéro de séquence 2, l'utilisateur reporte un achat à un coût de 20,00 $.  
3. Dans le numéro de séquence 3, l'utilisateur reporte un retour achat. L'utilisateur effectue une affectation fixe au second achat en saisissant le numéro d'écriture article dans le champ **Écr. article à affecter** sur la ligne retour achat.  

La table suivante montre des écritures du grand livre d'articles résultant de ce scénario.  

|**Date de report**|**Type d'écriture gr. livre art.**|**Quantité**|**Coût indiqué (réel)**|**N° écriture article gr. livre**|  
|----------------------|---------------------------------------------------|------------------|----------------------------------------------------|---------------------------------------------------|  
|04/01/20|Achat|10|10.00|1|  
|05/01/20|Achat|10|20.00|2|  
|06/01/20|Achat (retour)|-10|-20,00|3|  

Comme une affectation fixe est effectuée du retour achat vers la deuxième écriture achat, les articles doivent être retournés au coût correct. Si l'utilisateur n'avait pas effectué l'affectation fixe, l'article retourné serait évalué de façon incorrecte à 10,00 $ parce que le retour aurait été affecté dans la première écriture achat en fonction de la méthode FIFO.  

Le tableau suivant montre l'écriture d'affectation article générée par l'affectation fixe.  

|Date de report|N° écriture article entrant|N° écriture article sortant|Quantité|N° écriture article gr. livre|  
|------------------|----------------------------------------------|-----------------------------------------------|--------------|---------------------------------------------|  
|06/01/20|1|3|10|3|  

Le coût du second achat, 20,00 $, est ensuite transmis correctement au retour achat.  

### <a name="example--fixed-application-with-average-cost"></a>Exemple – affectation fixe avec le coût moyen  
L'exemple suivant, qui indique l'effet de l'affectation fixe, est basé sur le scénario suivant pour un article qui utilise le mode évaluation coût moyen :  

1. Dans les numéros de séquence 1 et 2, l'utilisateur reporte deux factures achat. La seconde facture a un coût unitaire direct incorrect de 1000,00 $.  
2. Dans le numéro de séquence 3, l'utilisateur reporte une note de crédit achat, avec une affectation fixe affectée à l'écriture achat avec le coût unitaire direct incorrect. La somme du champ **Coût indiqué (réel)** des deux écritures valeur affectées fixes devient 0,00  
3. Dans le numéro de séquence 4, l'utilisateur reporte une autre facture achat avec le coût unitaire direct correct de 100,00 $.  
4. Dans le numéro de séquence 5, l'utilisateur reporte une facture vente.  
5. La quantité en inventaire est 0, et la valeur inventaire est aussi égale à 0,00  

Le tableau suivant montre le résultat du scénario dans les écritures valeur de l'article.  

|Date de report|Type d'écriture gr. livre art.|Quantité valorisée|Coût indiqué (réel)|Écr. article à affecter|Valorisé par coût moyen|N° écriture article gr. livre|N° séquence |  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|--------------------------------------------|-------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01/01/20|Achat|1|200.00||Non|1|1|  
|01/01/20|Achat|1|1000.00||Non|2|2|  
|01/01/20|Achat|-1|-1 000|2|Non|3|3|  
|01/01/20|Achat|1|100.00||Non|4|4|  
|01/01/20|Vente|-2|-300,00||Oui|5|5|  

Si l'utilisateur n'avait pas effectué l'affectation fixe entre la note de crédit achat et l'achat avec le coût unitaire direct incorrect (étape 2 dans le scénario précédent), le coût aurait été ajusté différemment.  

Le tableau suivant montre le résultat dans les écritures valeur de l'article si l'étape 2 dans le scénario précédent est effectuée sans affectation fixe.  

|Date de report|Type d'écriture gr. livre art.|Quantité valorisée|Coût indiqué (réel)|Écr. article à affecter|Valorisé par coût moyen|N° écriture article gr. livre|N° séquence |  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|--------------------------------------------|-------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01/01/20|Achat|1|200.00||Non|1|1|  
|01/01/20|Achat|1|1000.00||Non|2|2|  
|01/01/20|Achat|-1|433,33||Oui|3|3|  
|01/01/20|Achat|1|100.00||Non|4|4|  
|01/01/20|Vente|-2|866,67||Oui|5|5|  

Dans le numéro d'écriture 3, la valeur du champ **Coût indiqué (réel)** est évaluée par moyenne et comprend donc le report erroné de 1000,00. Par conséquent, il prend la valeur -433,33, ce qui représente un coût indiqué gonflé. Le calcul est le suivant 1 300 / 3 = .-433,33.  

Dans le numéro d'écriture 5, la valeur du champ **Coût indiqué (réel)** de cette écriture est inexacte également pour le même motif.  

> [!NOTE]  
>  Si vous effectuez une affectation fixe pour une diminution d'inventaire d'un article qui utilise le mode évaluation coût moyen, la diminution d'inventaire ne reçoit pas le coût moyen pour l'article comme d'habitude, mais reçoit le coût de l'augmentation d'inventaire que vous avez spécifiée. Cette diminution d'inventaire ne fait alors plus partie du calcul du coût moyen.  

### <a name="example--fixed-application-in-sales-return"></a>Exemple – affectation fixe dans le retour vente  
Les affectations fixes sont également un excellent moyen d'inverser un coût exactement, par exemple avec des retours vente.  

L'exemple suivant, qui indique la manière dont une affectation fixe garantit l'inversion du coût exact, est basé sur le scénario suivant :  

1.  L'utilisateur reporte une facture achat.  
2.  L'utilisateur reporte une facture vente.  
3.  L'utilisateur reporte une note de crédit vente pour l'article retourné, qui affecte l'écriture ventes, pour inverser le coût correctement.  
4.  Des frais de transport liés au bon de commande reporté précédemment, arrivent. L'utilisateur le reporte comme frais article.  

Le tableau suivant montre le résultat des étapes 1 à 3 du scénario dans les écritures valeur de l'article.  

|Date de report|Type d'écriture gr. livre art.|Quantité valorisée|Coût indiqué (réel)|Écriture article à affecter|N° écriture article gr. livre|N° séquence |  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01/01/20|Achat|1|1000.00||1|1|  
|01/02/20|Vente|-1|1000.00||2|2|  
|01/03/20|Vente (Note de crédit)|1|1000|2|3|3|  

Le tableau suivant montre l'écriture valeur résultant de l'étape 4 du scénario, reportant les frais annexes.  

|Date de report|Type d'écriture gr. livre art.|Quantité valorisée|Coût indiqué (réel)|Écriture article à affecter|N° écriture article gr. livre|N° séquence |  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01/04/20|(Frais annexes)|1|100.00||1|4|  

Le tableau suivant montre l'effet de la contrepassation du coût exact des écritures valeur de l'article.  

|Date de report|Type d'écriture gr. livre art.|Quantité valorisée|Coût indiqué (réel)|Écriture article à affecter|N° écriture article gr. livre|N° séquence |  
|-------------------------------------|-----------------------------------------------|-----------------------------------------|------------------------------------------------|------------------------------------------------|-----------------------------------------------|----------------------------------|  
|01/01/20|Achat|1|1000.00||1|1|  
|01/02/20|Vente|-1|1100.00||2|2|  
|01/03/20|Vente (Note de crédit)|1|1100.00|2|3|3|  
|01/04/20|(Frais annexes)|1|100.00||1|4|  

Lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**, le coût augmenté de l'écriture achat, dû aux frais annexes, est transmis à l'écriture vente (écriture numéro 2). L'écriture vente transfère alors ce coût augmenté à l'écriture vente créditrice (numéro de séquence 3). Le résultat final est que le coût est correctement inversé.  

> [!NOTE]  
>  Si vous travaillez sur des retours ou des avoirs et que vous avez configuré le champ **Coût retour identique obligatoire** soit dans la fenêtre **Paramètres achats**, soit dans la fenêtre **Paramètres ventes**, en fonction de votre situation, puis [!INCLUDE[d365fin](includes/d365fin_md.md)] renseigne automatiquement ces champs lorsque vous utilisez la fonction **Copier document**. Si vous utilisez la fonction **Affichage de lignes document validées à contrepasser**, les champs sont toujours renseignés automatiquement.  

> [!NOTE]  
>  Si vous reportez une transaction avec une affectation fixe et si l'écriture article que vous affectez doit être fermée, ce qui signifie que la quantité restante est égale à zéro, l'ancienne affectation est automatiquement annulée et l'écriture article est réaffectée à l'aide de l'affectation fixe que vous avez spécifiée.  

## <a name="transfer-application"></a>Application de transfert  
Lorsqu'un article est transféré d'un emplacement à un autre, dans l'inventaire de la compagnie, alors une affectation est créée entre les deux écritures de transfert. L'évaluation d'une écriture de transfert dépend du mode d'évaluation. Pour les articles utilisant le mode évaluation stock moyen, l'évaluation est créée à l'aide du coût moyen dans la période coût moyen où se trouve la date évaluation du transfert. Pour les articles utilisant d'autres modes évaluation coût, l'évaluation est effectuée en remontant jusqu'au coût de l'augmentation d'inventaire d'origine.  

### <a name="example--average-costing-method"></a>Exemple – mode évaluation stock moyen  
L'exemple suivant, qui indique comment les écritures de transfert sont affectées, est basé sur le scénario suivant pour un article utilisant le mode évaluation stock moyen et une période coût moyen Jour.  

1. L'utilisateur achète l'article à un montant de 10,00 $.  
2. L'utilisateur achète à nouveau l'article à un montant de 20,00 $.  
3. L'utilisateur transfère l'article de l'emplacement BLEU à ROUGE.  

Le tableau suivant montre l'effet du transfert sur les écritures valeur de l'article.  

|Date de report|Type d'écriture gr. livre art.|Code d'emplacement|Quantité valorisée|Coût indiqué (réel)|N° séquence |  
|-------------------------------------|-----------------------------------------------|--------------------------------------|-----------------------------------------|------------------------------------------------|----------------------------------|  
|01/01/20|Achat|BLEU|1|10.00|1|  
|01/01/20|Achat|BLEU|1|20.00|2|  
|01/02/20|Virement|BLEU|-1|15.00|3|  
|01/02/20|Virement|ROUGE|1|15.00|4|  

### <a name="example--standard-costing-method"></a>Exemple – Mode d'évaluation du stock Standard  
L'exemple suivant, qui indique comment les écritures de transfert sont affectées, est basé sur le scénario suivant pour un article utilisant le mode évaluation stock Standard et une période coût moyen Jour.  

1. L'utilisateur achète l'article à un montant standard de 10,00 $.  
2. L'utilisateur transfère l'article à partir de l'emplacement BLEU à ROUGE à un coût standard de 12,00 $.  

Le tableau suivant montre l'effet du transfert sur les écritures valeur de l'article.  

|Date de report|Type d'écriture gr. livre art.|Code d'emplacement|Quantité valorisée|Coût indiqué (réel)|N° séquence |  
|-------------------------------------|-----------------------------------------------|--------------------------------------|-----------------------------------------|------------------------------------------------|----------------------------------|  
|01/01/20|Achat|BLEU|1|10.00|1|  
|01/02/20|Virement|BLEU|-1|10.00|2|  
|01/02/20|Virement|ROUGE|1|10.00|3|  

Étant donné que la valeur de l'augmentation d'inventaire d'origine est de 10,00 $, le transfert est évalué à ce coût, et non à 12,00 $.  

## <a name="reapplication"></a>Nouvelle affectation  
En raison du mode de calcul du coût unitaire d'un article, une affectation article incorrecte peut produire un coût moyen ou un coût unitaire erroné. Les scénarios suivants peuvent générer des affectations article incorrectes, qui nécessitent d'annuler des affectations article et d'appliquer à nouveau des écritures du grand livre d'articles :  

* Vous avez oublié d'effectuer une affectation fixe.  
* Vous avez effectué une affectation fixe incorrecte.  
* Vous souhaitez annuler l'affectation créée automatiquement lors du report, en fonction du mode d'évaluation du coût de l'article.  
* Vous devez retourner un article sur lequel une vente a déjà été appliquée manuellement, sans utiliser la fonction **Afficher des lignes document validées à contrepasser** et vous devez donc annuler l'application.  

[!INCLUDE[d365fin](includes/d365fin_md.md)] propose une fonction pour analyser et corriger des lettrages article. Cela s'effectue dans la fenêtre **Feuille lettrage**.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
[Détails de conception : modes évaluation stock](design-details-costing-methods.md)   
[Détails de conception : coût moyen](design-details-average-cost.md)   
[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

