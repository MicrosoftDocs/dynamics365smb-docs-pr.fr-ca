---
title: Mise à jour des coûts standard
description: Vous devez régulièrement mettre à jour les coûts standard des composants et remonter les nouveaux coûts dans l'article parent.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: 5841
ms.date: 10/11/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="update-standard-costs"></a>Mise à jour des coûts standard
Vous devez régulièrement mettre à jour les coûts standard des composants et remonter les nouveaux coûts dans l'article parent. Le processus comprend généralement les quatre étapes suivantes :  

1.  Mettre à jour les coûts aux niveaux des composantes et de la capacité. Pour plus d'informations, voir le traitement en lot **Suggérer un coût standard d'article**.  
2.  La consolidation et le calcul multi-niveau des coûts des composantes et de capacité permettent de déterminer le coût total de fabrication ou d'assemblage des articles.  
3.  Appliquer les coûts standard entrés lorsque vous lancez les traitements par lots précédents. Les coûts standard n'entrent en vigueur que lorsqu'ils sont mis en œuvre. Utilisez le traitement en lot **Appliquer les modifications de coût standard**, qui met à jour les modifications du coût standard sur les articles en fonction de ceux figurant dans la table Feuille coût standard.  
4.  Appliquer les modifications pour mettre à jour le champ **Coût unitaire** de la fiche article et effectuer une réévaluation du stock. Pour plus d'informations, voir [Réévaluer l'inventaire](inventory-how-revalue-inventory.md).  

Pour plus d'informations, voir [À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md) .
  
## <a name="to-update-standard-costs"></a>Pour mettre à jour des coûts standard

1.  Exécutez le traitement en lot **Ajuster coûts - Écr. article**. Pour lancer le traitement en lot, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ajuster coûts : Écr. article**, puis sélectionnez le lien associé. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Vérifiez les résultats et apportez des modifications si nécessaire.  
2.  Exécutez le traitement en lot **Reporter le coût de l'inventaire au grand livre**. Pour lancer le traitement en lot, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Reporter coût de l’inventaire au GL**, puis choisissez le lien associé. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)] Vérifiez les résultats et apportez des modifications si nécessaire.  
3.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Ouvrez la **Feuille coût standard** et utilisez une ou plusieurs des actions suivantes :

    1.  Exécutez le traitement en lot **Suggérer un coût standard d'article**.  
    2.  Vérifiez les résultats et apportez des modifications si nécessaire.  
    3.  Exécutez le traitement en lot **Suggérer le coût standard de la capacité**.  
    4.  Vérifiez les résultats et apportez des modifications si nécessaire.
    5. Exécutez le traitement en lot **Cumuler le coût standard**.
    6.  Vérifiez les résultats et apportez des modifications si nécessaire.
    7.  Exécutez le traitement en lot **Appliquer les modifications de coût standard**.  
4.  Vérifiez et reportez la page **Journal réévaluation** renseignée avec les entrées des étapes précédentes de ce processus.  

## <a name="see-also"></a>Voir aussi

 [À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md)   
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)   
 [Détails de conception : modes évaluation stock](design-details-costing-methods.md)   
 [Finances](finance.md)  
 [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
