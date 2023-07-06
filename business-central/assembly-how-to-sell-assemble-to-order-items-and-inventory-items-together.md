---
title: Vente simultanée d'articles à assembler pour commande et d'articles d'inventaire
description: 'Si une partie d’un article à assembler pour stock n’est pas disponible, vous pouvez créer un ordre d’assemblage pour la quantité restante.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: 'kit, kitting'
ms.search.form: '900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905'
---
# <a name="sell-assemble-to-order-items-and-inventory-items-together"></a><a name="sell-assemble-to-order-items-and-inventory-items-together"></a><a name="sell-assemble-to-order-items-and-inventory-items-together"></a>Vente simultanée d'articles à assembler pour commande et d'articles d'inventaire

Si le champ **Politique d’assemblage** de la fiche article d’un élément d’assemblage indique **Assembler pour stock**, le processus de document de vente se base sur l’hypothèse que l’article est déjà assemblé et peut être prélevé de l'inventaire, s’il est disponible. Par conséquent, aucun ordre d’assemblage n’est automatiquement créé ni lié à la ligne document de vente. Toutefois, si une partie ou la totalité de la quantité n’est pas disponible, vous pouvez créer un ordre d’assemblage pour la quantité restante. Pour ce faire, remplissez le champ **Qté. à assembler pour commande** sur la ligne document de vente. Ce paramètre vous permet d’assembler l’article pour commande même s’il est configuré pour être assemblé pour stock.  

Vous disposez d’une flexibilité similaire lorsque vous vendez des articles à assembler pour commande et qu’une partie de la quantité est déjà dans l’inventaire. Vous devrez déduire cette quantité de l’ordre d’assemblage. Pour en savoir plus sur la vente d’articles de l’inventaire, consultez [Vente d’articles de l’inventaire dans des flux à assembler pour commande](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

> [!NOTE]  
> Des règles s’appliquent au champ **Qté à livrer** sur les lignes document de vente qui contiennent une combinaison de quantités assembler pour commande et de quantités inventaire. Pour en savoir plus sur les règles, consultez [Scénarios de combinaison](assembly-assemble-to-order-or-assemble-to-stock.md#combination-scenarios).  

> [!NOTE]  
> La procédure suivante n’inclut pas les étapes de document de vente que vous devez suivre avant de créer un ordre d’assemblage pour les quantités indisponibles.

## <a name="to-sell-assemble-to-order-items-and-inventory-items-together"></a><a name="to-sell-assemble-to-order-items-and-inventory-items-together"></a><a name="to-sell-assemble-to-order-items-and-inventory-items-together"></a>Pour vendre des articles à assembler pour commande et des articles d'inventaire ensemble

1. Sur une ligne document de vente pour un article à assembler pour inventaire, entrez une quantité dans le champ **Quantité** qui est supérieure à l’inventaire. La page **Vérifier disponibilité** s'affiche. Pour en savoir plus sur la disponibilité des articles, consultez [Afficher la disponibilité des articles](inventory-how-availability-overview.md).
2. Dans le champ **Quantité à assembler pour commande**, entrez la valeur du champ **Quantité totale**.  
3. Exécutez toutes les modifications nécessaires aux composantes d’assemblage. Learn more at [Vente d’articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).  
4. Libérez le document de vente pour rendre les articles disponibles pour le prélèvement et pour l’assemblage des articles indisponibles. Pour en savoir plus sur les étapes d’assemblage standard, consultez [Assembler des articles](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
> Le champ **Code de zone** du document de vente peut contenir la valeur provenant des champs **Code de zone livr. ass. pr comm.** ou **Code de zone post-assemblage** de la fiche emplacement. Si c’est le cas, le champ **Code de zone** de la ligne document de vente peut être incorrect pour cette combinaison de quantités assembler pour commande et assembler pour stock. Il est bon de revérifier que la zone dans le champ **Code de zone** fonctionne pour toutes les quantités. Sinon, entrez les deux quantités différentes sur des lignes document de vente distinctes.  

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi

[Gestion d'assemblage](assembly-assemble-items.md)  
[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
