---
title: Annuler le report d'assemblage
description: Découvrez comment corriger les erreurs dans un ordre d’assemblage reporté.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: 'kit, kitting'
ms.search.form: '900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905'
---
# Annuler le report d'assemblage

Annulez le report d’un ordre d’assemblage pour corriger une erreur ou supprimer un report indésirable.

Lorsque vous annulez un ordre d’assemblage reporté, des écritures article de correction sont créées pour inverser les écritures d’origine. Chaque écriture production positive pour l'élément d'assemblage est inversée par une écriture production négative. Chaque écriture production négative pour une composante d'assemblage est inversée par une écriture production positive. L'affectation des coûts fixes est créée automatiquement entre les écritures de correction et les écritures d'origine afin de garantir l'exactitude de l'inversion de coût.  

Lorsque vous annulez un ordre d’assemblage entièrement reporté, vous pouvez recréer l’ordre d’origine. Par exemple, pour apporter des corrections avant de le reporter à nouveau.  

Lorsque vous annulez un ordre d’assemblage partiellement reporté, tous les champs de quantité concernés, notamment les champs **Quantité assemblée**, **Quantité consommée** et **Quantité restante** sont restaurés avec leur valeur précédant le report.  

Pour recréer ou restaurer des ordres d’assemblage, l’article du report d’origine doit respecter les conditions suivantes :  

* Il est toujours dans l’inventaire. Autrement dit, il n’a pas été vendu ni autrement consommé par des transactions sortantes.  
* Il n’est pas réservé.  
* Il doit exister dans la zone dans laquelle il a été produit.  

Les ordres d’assemblage ne peuvent être restaurés que si le numéro et la séquence des lignes de l’ordre d’assemblage n’ont pas été modifiés.  

> [!TIP]  
> Pour résoudre les conflits dus à des modifications des lignes, vous pouvez rétablir manuellement les modifications sur les lignes en question avant d’annuler l’ordre d’assemblage reporté. Vous pouvez reporter l’ordre d’assemblage, puis le recréer lorsque vous annulez le report.  

La procédure suivante décrit comment annuler les ordres d’assemblage reportés qui contiennent des articles assemblés pour stock. Pour annuler des ordres d’assemblage reportés avec des articles qui ont été assemblés pour commande, utilisez l’action **Annuler la livraison** sur la livraison reportée associée. Pour en savoir plus sur l’annulation de livraisons, consultez [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md). L’annulation de l’ordre d’assemblage reporté se déroule de la même manière que celle décrite dans cet article.  

## Pour annuler le report d'un ordre d'assemblage

Vous pouvez annuler des ordres d’assemblage entièrement ou partiellement reportés.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Ordres d’assemblage reportés**, puis sélectionnez le lien associé.  

   Chaque report partiel crée un ordre d'assemblage reporté distinct.  
2. Ouvrez l'ordre d'assemblage reporté que vous souhaitez annuler, puis choisissez **Annuler l'assemblage**.  

    Si l’ordre d’assemblage reporté est lié à un ordre d’assemblage entièrement reporté qui a été supprimé, vous pouvez recréer l’ordre supprimé. Par exemple, vous pouvez recréer l’ordre parce que vous souhaitez le retraiter.  
3. Pour recréer l’ordre d’assemblage, choisissez **Oui**. Pour annuler le report sans recréer l’ordre d’assemblage associé, choisissez **Non**.  

Le champ **Inversé** de l’ordre d’assemblage prend la valeur **Oui**. Le report de l’ordre d’assemblage est maintenant inversé. Vous pouvez traiter l’intégralité de l’ordre d’assemblage si vous avez choisi de le recréer, ou l’ordre d’assemblage ouvert que vous avez restauré à son état d’origine.  

> [!NOTE]  
> Pour restaurer les quantités de plusieurs reports partiels dans un ordre d’assemblage, vous devez annuler tous les ordres d’assemblage reportés en suivant les étapes 1 à 3.  

## Voir aussi

[Gestion d'assemblage](assembly-assemble-items.md)  
[Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md)  
[Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md)  
[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]