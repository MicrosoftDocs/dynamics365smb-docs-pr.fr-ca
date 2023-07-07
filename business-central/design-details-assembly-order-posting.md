---
title: "Détails de conception\_-\_Report d’ordre d’assemblage"
description: Le report d'ordre d'assemblage est basé sur les mêmes principes que le report des activités similaires des documents de vente et de la consommation de production/production.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/15/2021
ms.author: edupont
---
# <a name="design-details-assembly-order-posting"></a>Détails de conception : report d'un ordre d'assemblage
Le report d'ordre d'assemblage est basé sur les mêmes principes que le report des activités similaires des documents de vente et de la consommation de production/production. Cependant, les principes sont combinés du fait que les ordres d'assemblage ont leur propre interface utilisateur de report, comme celle des documents de vente, alors que le report des écritures réel se produit en arrière-plan en tant que report direct d'article et de journal ressource, comme pour la consommation de production, la production et la capacité.  

Comme pour le report d'un bon de production, les composantes consommées et les ressources utilisées sont converties et sorties en tant qu'élément d'assemblage lorsque l'ordre d'assemblage est reporté. Pour plus d'informations, voir [Détails de conception : validation d'ordre de fabrication](design-details-production-order-posting.md). Toutefois, le flux des coûts des ordres d'assemblage est moins complexe, notamment parce que le report du coût d'assemblage ne se produit qu'une fois et ne génère donc pas d'inventaire travaux en cours.  

Les reports journal suivants se produisent lors du report d'un ordre d'assemblage :  

-   Le journal article reporte les écritures positives du grand livre d'articles, représentant la production de l'élément d'assemblage, à partir de l'en-tête de l'ordre d'assemblage.  
-   Le journal article reporte les écritures négatives du grand livre d'articles, représentant la consommation des composantes d'assemblage, à partir des lignes d'ordre d'assemblage.  
-   Le journal ressource reporte l'utilisation des ressources d'assemblage (unités de temps), à partir des lignes d'ordre d'assemblage.  
-   Le journal capacité reporte les écritures valeur liées à l'utilisation des ressources, à partir des lignes d'ordre d'assemblage.  

Le schéma suivant montre la structure des écritures article et ressource qui résultent du report d'un ordre d'assemblage.  

![Écritures article, ressource et du grand livre de capacité résultant du report d’ordre d’assemblage.](media/design_details_assembly_posting_1.png "Écritures article, ressource et capacité résultant du report d'ordre d'assemblage")  

> [!NOTE]  
>  Les postes et ateliers sont inclus pour illustrer que les écritures du grand livre de capacité sont créées à la fois à partir de la production et de l'assemblage.  

Le schéma suivant montre la manière dont les données d'assemblage circulent dans les écritures au cours du report :  

![Flux d’écritures lié à l’assemblage lors du report.](media/design_details_assembly_posting_2.png "Flux d'écritures lié à l'assemblage lors du report")  

## <a name="posting-sequence"></a>Séquence de report
Le report d'un ordre d'assemblage se produit dans l'ordre suivant :  

1.  Les lignes ordre d'assemblage sont reportées.  
2.  L'en-tête d'ordre d'assemblage est reporté.  

Le tableau suivant indique la séquence d'actions.  

|Action|Description|  
|------------|-----------------|  
|Initialiser le report|1. Effectuer une vérification préliminaire.<br />2. Ajoutez le numéro de report et modifiez l'en\-tête d'ordre d'assemblage.<br />3. Libérez l'ordre d'assemblage.|  
|Comptabilisation|<ol><li>Créer l'en-tête d'ordre d'assemblage reporté.</li><li>Copier les lignes commentaire.</li><li>Reportez les lignes ordre d'assemblage (consommation) :<br /><br /> <ol><li>Créer une page d'état pour calculer la consommation d'assemblage.</li><li>Obtenez la quantité restante sur laquelle la ligne journal article est basée.</li><li>Réinitialisez les quantités consommées et les quantités d'assemblage.</li><li>Pour les lignes ordre d'assemblage de type Article :<br /><br /> <ol><li>Renseignez les champs dans la ligne journal article.</li><li>Transférez les réservations vers la ligne journal article.</li><li>Reportez la ligne journal article pour créer les écritures du grand livre d'articles.</li><li>Créez les lignes journal entrepôt et reportez-les.</li></ol></li><li>Pour les lignes ordre d'assemblage de type Ressource :<br /><br /> <ol><li>Renseignez les champs dans la ligne journal article.</li><li>Reportez la ligne journal article. Cela crée des écritures du grand livre de capacité.</li><li>Créez et reportez la ligne journal ressource.</li></ol></li><li>Transférez des valeurs de champ de l'ordre d'assemblage dans une ligne d'ordre d'assemblage reporté nouvellement créée.</li></ol></li><li>Reportez l'en-tête d'ordre d'assemblage (résultat) :<br /><br /> <ol><li>Renseignez les champs dans la ligne journal article.</li><li>Transférez les réservations vers la ligne journal article.</li><li>Reportez la ligne journal article pour créer les écritures du grand livre d'articles.</li><li>Créez les lignes journal entrepôt et reportez-les.</li><li>Réinitialisez les quantités d'assemblage et les quantités restantes.</li></ol></li></ol>|  

> [!IMPORTANT]  
>  Contrairement à la sortie de production, qui est reportée au coût prévu, le résultat d'assemblage est reporté au coût réel.  

## <a name="cost-adjustment"></a>Ajustement du coût
 Une fois l'ordre d'assemblage reporté, à savoir que les composantes (matériel) et les ressources sont assemblées dans un nouvel article, il doit être possible de déterminer le coût réel de cet élément d'assemblage, et le coût inventaire réel des composantes impliquées. Ceci est obtenu en transférant les coûts des écritures reportées de la source (les composantes et ressources) vers les écritures reportées de la destination (l'élément d'assemblage). Le transfert des coûts est effectué en calculant et en générant de nouvelles écritures, appelées écritures ajustement qui sont associées aux écritures de destination.  

 Les coûts d'assemblage à transférer sont détectés grâce au mécanisme de détection du niveau de commande. Pour plus d'informations sur d'autres mécanismes de détection d'ajustement, reportez\-vous à [Détails de conception : ajustement des coûts](design-details-cost-adjustment.md).  

### <a name="detecting-the-adjustment"></a>Détection de l'ajustement
La fonction de détection du niveau de commande est utilisée pour les scénarios de conversion, de production et d'assemblage. La fonction opère comme suit :  

-   L'ajustement des coûts est détecté en marquant la commande chaque fois que des matières/ressources sont reportées comme étant consommées/utilisées pour la commande.  
-   Les coûts sont transférés en appliquant les coûts des matières/ressources aux écritures de production liées à la même commande.  

Le graphique suivant montre la structure d'écriture d'ajustement et comment les coûts d'assemblage sont ajustés.  

![Flux d’écritures lié à l’assemblage lors de l’ajustement des coûts.](media/design_details_assembly_posting_3.png "Flux d'écritures lié à l'assemblage lors du report")  

### <a name="performing-the-adjustment"></a>Procéder à l'ajustement
La répartition des ajustements détectés entre les coûts matière et ressource et les écritures de résultat d'assemblage est effectuée par le traitement par lots **Ajuster coûts : Écr. article**. Il contient la fonction Effectuer un ajustement à plusieurs niveaux, qui se compose des deux éléments suivants :  

-   Effectuer un ajustement d'ordre d'assemblage : qui transmet le coût d'utilisation des matières et des ressources à l'écriture de résultat d'assemblage. Les lignes 5 et 6 dans l'algorithme ci-dessous sont responsables de cela.  
-   Effectuer des ajustements à niveau unique : ce qui transfère les coûts des différents articles en utilisant leur mode d'évaluation de l'inventaire. Les lignes 9 et 10 dans l'algorithme ci-dessous sont responsables de cela.  

![Résumé de l’algorithme d’ajustement des coûts pour report de l’assemblage.](media/design_details_assembly_posting_4.jpg "Résumé de l'algorithme d'ajustement des coûts pour le report d'assemblage")  

> [!NOTE]  
>  L'élément Effectuer des ajustements de TEC, dans les lignes 7 et 8, est responsable du transfert du matériel de production et de l'utilisation de la capacité vers la production des ordres de fabrication non terminés. Ceci n'est pas utilisé lors de l'ajustement des coûts d'ordre d'assemblage, car le concept de TEC ne s'applique pas à l'assemblage.  

Pour plus d'informations sur la manière dont les coûts d'assemblage ou de production sont validés dans la comptabilité, reportez\-vous à [Détails de conception : comptabilisation stock](design-details-inventory-posting.md).  

## <a name="assembly-costs-are-always-actual"></a>Les coûts d'assemblage sont toujours réels
 Le concept de travaux en cours (TEC) ne s'applique pas au report d'un ordre d'assemblage. Les coûts d'assemblage sont uniquement reportés en tant que coûts réels, jamais en tant que coûts prévus. Pour plus d'informations, voir [Détails de conception : validation du coût prévu](design-details-expected-cost-posting.md).  

Ceci est activé par la structure de données suivante.  

-   Dans le champ **Type** des lignes feuille article, dans les tables **Écriture comptable capacité** et **Écriture valeur**, *Ressource* est utilisé pour identifier les écritures ressource d'assemblage.  
-   Dans le champ **Type écriture comptable article** sur les lignes feuille article, dans les tables **Écriture comptable capacité** et **Écriture valeur**, *Résultat d'assemblage* et *Consommation d'assemblage* permettent d'identifier les écritures d'élément d'assemblage de production et les écritures composant d'assemblage consommées respectivement.  

En outre, les champs de groupe de report dans l'en-tête d'ordre d'assemblage et les lignes d'ordre d'assemblage sont renseignés par défaut comme suit.  

|Entité|Type|Paramètre report|Groupe. Groupe de report prod.|  
|------------|----------|-------------------|------------------------------|  
|En-tête d'ordre d'assemblage|Article|Groupe de report inventaire|Groupe. Groupe de report prod.|  
|Ligne d'ordre d'assemblage|Article|Groupe de report inventaire|Groupe. Groupe de report prod.|  
|Ligne d'ordre d'assemblage|Ressource||Groupe. Groupe de report prod.|  

Par conséquent, seuls les coûts réels sont reportés dans le grand livre, et aucun compte provisoire n'est renseigné à partir du report d'un ordre d'assemblage. Pour plus d'informations, voir [Détails de conception : comptes de la comptabilité](design-details-accounts-in-the-general-ledger.md).  

## <a name="assemble-to-order"></a>Assembler pour commande
L'écriture article qui résulte du report d'une vente assembler pour commande est affectée de façon fixe à l'écriture article associée pour le résultat d'assemblage. Par conséquent, le coût d'une vente assembler pour commande est dérivé de l'ordre d'assemblage auquel la vente a été liée.  

Les écritures article de type Vente qui résultent du report des quantités à assembler pour commande sont identifiées par **Oui** dans le champ **Assembler pour commande**.  

Le report de lignes document de vente dont une partie est une quantité en inventaire et une autre partie est une quantité à assembler pour commande entraîne la création d'écritures article distinctes, une pour la quantité en inventaire et une pour la quantité à assembler pour commande.  

### <a name="posting-dates"></a>Dates de report

En général, les dates report sont copiées d’un document de vente vers l’ordre d’assemblage lié. La date de report dans l’ordre d’assemblage est automatiquement mise à jour lorsque vous modifiez la date de report dans le document de vente directement ou indirectement, par exemple si vous modifiez la date de report dans la livraison entrepôt, le prélèvement inventaire ou dans le cadre d’un report groupé.

Vous pouvez modifier manuellement la date de report dans l’ordre d’assemblage. Cependant, elle ne peut pas être postérieure à la date de report dans le document de vente lié. Le système conservera cette date, à moins que vous ne mettiez à jour la date de report dans le document de vente.


## <a name="see-also"></a>Voir aussi
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : validation d'ordre de fabrication](design-details-production-order-posting.md)   
 [Détails de conception : modes évaluation stock](design-details-costing-methods.md)  
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
