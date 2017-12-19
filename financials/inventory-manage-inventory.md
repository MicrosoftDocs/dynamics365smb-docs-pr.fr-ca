---
title: Gestion de l'inventaire| Microsoft Docs
description: "Décrit comment gérer les biens physiques que vous commercialisez, par exemple, la gestion du stock de votre entrepôt."
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: a49e50213f808fb72b43dfa22a34833b306ef12d
ms.openlocfilehash: 1aa1a7c2ec56c3f123bde67a9870be4efd99bdb5
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---

# <a name="inventory"></a>Stocks
Pour chaque produit physique que vous commercialisez, vous devez créer une fiche article de type **Stock**. Les articles que vous proposez aux clients, mais que vous ne conservez pas dans l'inventaire, peuvent être enregistrés comme articles hors inventaire. Vous pouvez ensuite les convertir en articles en inventaire, le cas échéant. Vous pouvez augmenter ou diminuer la quantité d'un article en inventaire en reportant directement les écritures de l'article, par exemple, après un comptage physique ou si vous n'enregistrez pas les achats.

Les augmentations et diminutions d'inventaire sont également évidemment enregistrées lorsque vous reportez des documents achat et vente, respectivement. Pour plus d'informations, reportez-vous à [Procédure : enregistrer des achats](purchasing-how-record-purchases.md), [Procédure : vendre des produits](sales-how-sell-products.md) et à [Procédure : facturer des ventes](sales-how-invoice-sales.md). Les transferts entre emplacements modifient les quantités dans l'inventaire dans tous les entrepôts de votre compagnie.   

Pour accroître votre aperçu d'articles et pour vous aider à les trouver, vous pouvez catégoriser les articles et leur donner des attributs pour vos opérations de recherche et de tri.

> [!NOTE]
> Le traitement physique des articles est appelé Activités entrepôt. Pour plus d'informations, voir [Gestion d'entrepôt](warehouse-manage-warehouse.md).

## <a name="inventory-reconciliation"></a>Rapprochement inventaire
Lorsque vous reportez des transactions inventaire, tels que des livraisons vente, des factures achat ou des ajustements inventaire, les coûts article modifiés sont enregistrés dans les écritures valeur article. Pour refléter ces modifications de la valeur inventaire dans vos livres financiers, les coûts inventaire sont automatiquement reportés dans les comptes inventaire associés dans le grand livre. Pour chaque transaction inventaire que vous reportez, les valeurs appropriées sont reportées dans le compte inventaire, le compte ajustement et le compte variation inventaire dans le grand livre. Pour plus d'informations, voir [Procédure : rapprocher les coûts inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md).

Bien que les coûts inventaire soient automatiquement reportés dans le grand livre, il est malgré tout nécessaire de vous assurer que les coûts des biens sont transmis à la transaction de vente sortante associée, notamment dans les situations où vous vendez des biens avant de facturer l'achat. Il s'agit d'un ajustement des coûts. Le coût des articles est ajusté automatiquement lorsque vous reportez des transactions article, mais vous pouvez également les ajuster manuellement. Pour en savoir plus, voir [Procédure : Ajuster coûts article](inventory-how-adjust-item-costs.md).

|À |Voir |
|---|----|
|Créer des fiches article pour les articles en inventaire que vous commercialisez.|[Procédure : enregistrer de nouveaux articles](inventory-how-register-new-items.md)|
|Structurez les articles parents que vous vendez sous forme de kits constitués des composants du parent ou que vous assemblez pour commande ou stock.|[Procédure : utiliser les nomenclatures](inventory-how-work-BOMs.md)|
|Conservez un aperçu des articles et simplifiez la recherche et le tri des articles en les organisant par catégorie.|[Procédure : catégoriser des articles](inventory-how-categorize-items.md)|
|Affecter des attributs de différents types de valeurs à vos articles pour vous aider à les trier et à les rechercher.|[Procédure : utilisation des attributs d'article](inventory-how-work-item-attributes.md)|
|Créez des fiches article spéciales pour les articles que vous proposez aux clients, mais que vous ne stockez pas dans l'inventaire.|[Procédure : utiliser des articles non stockés](inventory-how-work-nonstock-items.md)|
|Effectuez un inventaire physique, faire des ajustements négatifs ou positifs et modifiez des informations, telles que l'emplacement ou le numéro de lot, sur des écritures article.|[Procédure : Inventaire, ajustement et reclassement du stock](inventory-how-count-adjust-reclassify.md)|
|Afficher la disponibilité des articles par emplacement, par période, par événement de vente ou d'achat, ou encore en fonction de leur utilisation dans les nomenclatures d'assemblage ou de production.|[Procédure : voir la disponibilité des articles](inventory-how-availability-overview.md)|
|Transférez des articles en inventaire entre des emplacements avec des ordres de transfert pour gérer les activités entrepôt ou avec le journal reclassement article.|[Procédure : transfert de stock entre des magasins](inventory-how-transfer-between-locations.md)|
|Réservez des articles en inventaire ou entrants pour les documents de vente, les bons de commande, les commandes service, les ordres d'assemblage ou les bons de production.|[Procédure : réserver des articles](inventory-how-to-reserve-items.md)|
|Affectez des numéros de série ou de lot à n'importe quel document ou ligne journal entrant ou sortant, par exemple pour suivre les articles dans le cas d'un rappel.|[Procédure : utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md)|
|Rechercher où un numéro de série ou de lot a été utilisé dans sa chaîne d'approvisionnement, par exemple dans les situations de rappel.|[Procédure : tracer des articles suivis](inventory-how-to-trace-item-tracked-items.md)|
|Gérez les opérations commerciales dans les bureaux de vente, les départements d'achat ou les bureaux de planification d'usine pour plusieurs emplacements.|[Procédure : utiliser les centres de gestion](inventory-responsibility-centers.md)|

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)    
[Utilisation de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]

