---
title: Créer des bons de production à partir de documents de vente
description: Découvrez différentes façons de créer des bons de production pour les articles produits directement à partir des documents de vente.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.form: '99000883, 99000884,'
---
# Créer des bons de production à partir de documents de vente

Vous pouvez créer des bons de production pour les articles produits directement à partir des documents de vente.  

## Pour créer un bon de production à partir d'un document de vente  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez le document de vente pour lequel vous voulez créer un bon de production.  
3. Sélectionnez l'action **Planification**. La page **Planification document de vente** affiche la disponibilité de l’article.  
4. Sélectionnez l'action **Créer O.F**.  
5. Sélectionnez l'état et le type de commande.  
6. Choisissez le bouton **Oui** pour créer un ou plusieurs bons de production pour les lignes ayant **Bon de production** dans le champ **Système réapprovisionnement**.

    > [!NOTE]  
    > Les lignes de demandes qui ont **Bon de production** dans le champ **Système réappro.** représentent des bons de production sous-jacents. Après avoir généré ces bons de production, n’oubliez pas d’identifier toute demande de composantes non satisfaite. Utilisez la page **Planification commande** ou l’action **Replanifier** pour identifier la demande non satisfaite.
    >
    > Lorsque vous créez des bons de production pour des commandes client avec la page Planification document de vente, des liens ordre pour ordre sont appliqués entre la demande et l’approvisionnement. Lorsque les liens ordre pour ordre existent, le système de planification n’inclut pas d’approvisionnement ou d’inventaire lié dans la procédure d’équilibrage. Pour en savoir plus sur l’équilibrage, consultez [Liens ordre pour ordre](design-details-central-concepts-of-the-planning-system.md#order-to-order-links).

## Type de commande  

Le tableau suivant décrit deux manières de créer des bons de production.

|Option|Désignation|
|------|-----------|
|O.F. article|Un bon de production est créé pour chaque article représenté par une ligne sur la page **Planification document de vente**.|
|O.F. projet|Un bon de production multiligne est créé pour tous les articles représentés par des lignes sur la page **Planification document de vente**. Lorsque vous utilisez des commandes projet, le champ **Type de source** du bon de production contient **En-tête vente**. L’ordre comporte une ligne pour chaque article de ligne de vente qui doit être produit.|

## Voir aussi  

[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
