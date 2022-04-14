---
title: Gestion de l’inventaire
description: Cette rubrique décrit comment gérer les produits physiques que vous échangez en créant une fiche d’article d’inventaire.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.search.forms: 5804, 2106, 5823, 5751, 5750, 772, 5829, 5828, 513, 304, 40, 38, 167, 117, 5827, 9223, 158, 354, 9152, 286, 5754, 5402, 209, 297, 298, 99000782
ms.date: 06/16/2021
ms.author: edupont
ms.openlocfilehash: 567b1cd469816f175508dddac068b8b8b3e1bc2e
ms.sourcegitcommit: 8a12074b170a14d98ab7ffdad77d66aed64e5783
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2022
ms.locfileid: "8521972"
---
# <a name="manage-inventory"></a>Gestion de l'inventaire

Pour chaque produit physique que vous commercialisez, vous devez créer une fiche article de type **Stock**. Les articles que vous proposez aux clients, mais que vous n'avez pas en inventaire, peuvent être enregistrés comme articles de catalogue. Vous pouvez ensuite les convertir en articles d'inventaire, le cas échéant. Vous pouvez augmenter ou diminuer la quantité d'un article en inventaire en reportant directement les écritures de l'article, par exemple, après un comptage physique ou si vous n'enregistrez pas les achats.

Les augmentations et diminutions d'inventaire sont également évidemment enregistrées lorsque vous reportez des documents achat et vente, respectivement. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md), [Vendre des produits](sales-how-sell-products.md) et  [Facturer des ventes](sales-how-invoice-sales.md). Les transferts entre emplacements modifient les quantités dans l'inventaire dans tous les entrepôts de votre compagnie.   

Pour accroître votre aperçu d'articles et pour vous aider à les trouver, vous pouvez catégoriser les articles et leur donner des attributs pour vos opérations de recherche et de tri.

> [!NOTE]
> Le traitement physique des articles est appelé Activités entrepôt. Pour plus d'informations, voir [Gestion d'entrepôt](warehouse-manage-warehouse.md).

La planification d’articles pour répondre à la demande est couverte dans le cadre de la fonctionnalité de planification de l’offre. Pour plus d'informations, voir [Planification](production-planning.md).  

## <a name="inventory-reconciliation"></a>Rapprochement inventaire
Lorsque vous reportez des transactions inventaire, tels que des livraisons vente, des factures achat ou des ajustements inventaire, les coûts article modifiés sont enregistrés dans les écritures valeur article. Pour refléter ces modifications de la valeur inventaire dans vos livres financiers, les coûts inventaire sont automatiquement reportés dans les comptes inventaire associés dans le grand livre. Pour chaque transaction inventaire que vous reportez, les valeurs appropriées sont reportées dans le compte inventaire, le compte ajustement et le compte variation inventaire dans le grand livre. Pour plus d'informations, voir [Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md).

Bien que les coûts inventaire soient automatiquement reportés dans le grand livre, il est malgré tout nécessaire de vous assurer que les coûts des biens sont transmis à la transaction de vente sortante associée, notamment dans les situations où vous vendez des biens avant de facturer l'achat. Il s'agit d'un ajustement des coûts. Le coût des articles est ajusté automatiquement lorsque vous reportez des transactions article, mais vous pouvez également les ajuster manuellement. Pour en savoir plus, voir [Ajuster coûts article](inventory-how-adjust-item-costs.md).  

## <a name="related-tasks"></a>Tâches connexes

Le tableau suivant présente les tâches associées.

|Pour |Voir |
|---|----|
|Créer des fiches article pour les articles en inventaire que vous commercialisez.|[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)|
|Structurez les articles parents que vous vendez sous forme de kits constitués des composants du parent ou que vous assemblez pour commande ou stock.|[Utiliser les nomenclatures](inventory-how-work-BOMs.md)|
|Conservez un aperçu des articles et simplifiez la recherche et le tri des articles en les organisant par catégorie.|[Catégoriser des articles](inventory-how-categorize-items.md)|
|Affecter des attributs de différents types de valeurs à vos articles pour vous aider à les trier et à les rechercher.|[Utiliser les attributs d'article](inventory-how-work-item-attributes.md)|
|Créez des fiches article spéciales pour les articles que vous proposez aux clients, mais que vous ne stockez pas dans l'inventaire.|[Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md)|
|Exécutez le décompte physique de votre inventaire avec les pages **Commande inventaire physique** et **Enregistrement inventaire physique**.|[Faire l'inventaire à l'aide de documents](inventory-how-count-inventory-with-documents.md)|
|Effectuer un inventaire physique, faire des ajustements négatifs ou positifs, et modifier des informations, telles que l'emplacement ou le numéro de lot, sur des écritures article.|[Comptabiliser, ajuster et reclasser l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md)|
|Afficher la disponibilité des articles par emplacement, par période, par événement de vente ou d'achat, ou encore en fonction de leur utilisation dans les nomenclatures d'assemblage ou de production.|[Voir la disponibilité des articles](inventory-how-availability-overview.md)|
|Transférez des articles en inventaire entre des emplacements avec des ordres de transfert pour gérer les activités entrepôt ou avec le journal reclassement article.|[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)|
|Réservez des articles en inventaire ou entrants pour les documents de vente, les bons de commande, les commandes service, les ordres d'assemblage ou les bons de production.|[Réserver des articles](inventory-how-to-reserve-items.md)|
|Configurez la traçabilité afin de pouvoir suivre les numéros de série des articles, par exemple pour suivre les articles en cas de rappel.|[Configuration du suivi des articles avec les numéros lot, de série et paquet](inventory-how-setup-item-tracking.md)|
|Attribuez des numéros de série ou de lot à n'importe quel document ou ligne journal sortant ou entrant.|[Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md)|
|Rechercher où un numéro de série ou de lot a été utilisé dans sa chaîne d'approvisionnement, par exemple dans les situations de rappel.|[Tracer des articles - Articles suivis](inventory-how-to-trace-item-tracked-items.md)|
|Configurer la description d'un article propre à un fournisseur ou à un client sur votre fiche article, afin de pouvoir insérer rapidement leur description de l'article dans les documents commerciaux.|[Utiliser références article](inventory-how-use-item-cross-refs.md)|
|Bloquez des articles pour empêcher leur saisie dans des lignes vente ou achat, ou leur report dans n'importe quelle transaction.|[Bloquer les articles](inventory-how-block-items.md)|
|Gérez les opérations commerciales dans les bureaux de vente, les départements d'achat ou les bureaux de planification d'usine pour plusieurs emplacements.|[Utiliser les centres de gestion](inventory-responsibility-centers.md)|
|Utilisez des ressources avec des compétences spécifiques pour divers services et éléments de service.|[Configurer l'affectation des ressources](service-how-setup-resource-allocation.md)|

## <a name="see-also"></a>Voir aussi

[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]