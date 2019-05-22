---
title: Gestion de l'inventaire| Microsoft Docs
description: Décrit comment gérer les biens physiques que vous commercialisez, par exemple, la gestion du stock de votre entrepôt.
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: a4c4788f7f262dee32f489095bf1ee303ea712c5
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1239416"
---
# <a name="inventory"></a>Stocks
Pour chaque produit physique que vous commercialisez, vous devez créer une fiche article de type **Stock**. Les articles que vous proposez aux clients, mais que vous n'avez pas en inventaire, peuvent être enregistrés comme articles de catalogue. Vous pouvez ensuite les convertir en articles d'inventaire, le cas échéant. Vous pouvez augmenter ou diminuer la quantité d'un article en inventaire en reportant directement les écritures de l'article, par exemple, après un comptage physique ou si vous n'enregistrez pas les achats.

Les augmentations et diminutions d'inventaire sont également évidemment enregistrées lorsque vous reportez des documents achat et vente, respectivement. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md), [Vendre des produits](sales-how-sell-products.md) et  [Facturer des ventes](sales-how-invoice-sales.md). Les transferts entre emplacements modifient les quantités dans l'inventaire dans tous les entrepôts de votre compagnie.   

Pour accroître votre aperçu d'articles et pour vous aider à les trouver, vous pouvez catégoriser les articles et leur donner des attributs pour vos opérations de recherche et de tri.

> [!NOTE]
> Le traitement physique des articles est appelé Activités entrepôt. Pour plus d'informations, voir [Gestion d'entrepôt](warehouse-manage-warehouse.md).

## <a name="inventory-reconciliation"></a>Rapprochement inventaire
Lorsque vous reportez des transactions inventaire, tels que des livraisons vente, des factures achat ou des ajustements inventaire, les coûts article modifiés sont enregistrés dans les écritures valeur article. Pour refléter ces modifications de la valeur inventaire dans vos livres financiers, les coûts inventaire sont automatiquement reportés dans les comptes inventaire associés dans le grand livre. Pour chaque transaction inventaire que vous reportez, les valeurs appropriées sont reportées dans le compte inventaire, le compte ajustement et le compte variation inventaire dans le grand livre. Pour plus d'informations, voir [Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md).

Bien que les coûts inventaire soient automatiquement reportés dans le grand livre, il est malgré tout nécessaire de vous assurer que les coûts des biens sont transmis à la transaction de vente sortante associée, notamment dans les situations où vous vendez des biens avant de facturer l'achat. Il s'agit d'un ajustement des coûts. Le coût des articles est ajusté automatiquement lorsque vous reportez des transactions article, mais vous pouvez également les ajuster manuellement. Pour en savoir plus, voir [Ajuster coûts article](inventory-how-adjust-item-costs.md).

|À |Voir |
|---|----|
|Créer des fiches article pour les articles en inventaire que vous commercialisez.|[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)|
|Structurez les articles parents que vous vendez sous forme de kits constitués des composants du parent ou que vous assemblez pour commande ou stock.|[Utiliser les nomenclatures](inventory-how-work-BOMs.md)|
|Conservez un aperçu des articles et simplifiez la recherche et le tri des articles en les organisant par catégorie.|[Catégoriser des articles](inventory-how-categorize-items.md)|
|Affecter des attributs de différents types de valeurs à vos articles pour vous aider à les trier et à les rechercher.|[Utiliser les attributs d'article](inventory-how-work-item-attributes.md)|
|Créez des fiches article spéciales pour les articles que vous proposez aux clients, mais que vous ne stockez pas dans l'inventaire.|[Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md)|
|Exécutez l'inventaire physique de votre inventaire avec les pages **Commande d'inventaire physique** et Enregistrement d'inventaire physique**.|[Faire l'inventaire à l'aide de documents](inventory-how-count-inventory-with-documents.md)|
|Effectuez un inventaire physique, faire des ajustements négatifs ou positifs et modifiez des informations, telles que l'emplacement ou le numéro de lot, sur des écritures article.|[Comptabiliser, ajuster et reclasser l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md)|
|Afficher la disponibilité des articles par emplacement, par période, par événement de vente ou d'achat, ou encore en fonction de leur utilisation dans les nomenclatures d'assemblage ou de production.|[Voir la disponibilité des articles](inventory-how-availability-overview.md)|
|Transférez des articles en inventaire entre des emplacements avec des ordres de transfert pour gérer les activités entrepôt ou avec le journal reclassement article.|[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)|
|Réservez des articles en inventaire ou entrants pour les documents de vente, les bons de commande, les commandes service, les ordres d'assemblage ou les bons de production.|[Réserver des articles](inventory-how-to-reserve-items.md)|
|Configurer la description propre à un fournisseur ou à un client pour un article, afin de pouvoir insérer facilement leur description de l'article dans les documents commerciaux.|[Utiliser les références externes article](inventory-how-use-item-cross-refs.md)|
|Affectez des numéros de série ou de lot à n'importe quel document ou ligne journal entrant ou sortant, par exemple pour suivre les articles dans le cas d'un rappel.|[Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md)|
|Configurer la description d'un article propre à un fournisseur ou à un client sur votre fiche article, afin de pouvoir insérer rapidement leur description de l'article dans les documents commerciaux.|[Utiliser les références externes article](inventory-how-use-item-cross-refs.md)|
|Rechercher où un numéro de série ou de lot a été utilisé dans sa chaîne d'approvisionnement, par exemple dans les situations de rappel.|[Tracer des articles - Articles suivis](inventory-how-to-trace-item-tracked-items.md)|
|Bloquez des articles pour empêcher leur saisie dans des lignes vente ou achat, ou leur report dans n'importe quelle transaction.|[Bloquer les articles](inventory-how-block-items.md)|
|Gérez les opérations commerciales dans les bureaux de vente, les départements d'achat ou les bureaux de planification d'usine pour plusieurs emplacements.|[Utiliser les centres de gestion](inventory-responsibility-centers.md)|

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
