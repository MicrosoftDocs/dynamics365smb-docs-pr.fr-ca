---
title: Gestion d'assemblage | Microsoft Docs
description: "Gérez les compagnies qui fournissent des produits à leurs clients en combinant des composantes dans des processus simples sans recourir aux fonctionnalités de fabrication, mais avec des fonctions permettant d'assembler les articles. Ces fonctions s'intègrent à celles existantes : ventes, planification, réservations et entreposage."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: kit, kitting
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 111f78578f298c662cc5a923a0b05c487f68b4c7
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6215613"
---
# <a name="assembly-management"></a>Gestion d'assemblage
Pour prendre en charge les sociétés qui fournissent des produits à leurs clients en combinant des composants dans des processus simples sans recourir aux fonctionnalités de fabrication, [!INCLUDE[prod_short](includes/prod_short.md)] inclut des fonctions permettant d'assembler les articles. Ces fonctions s'intègrent à celles existantes \(ventes, planification, réservations et entreposage\).  

 Un élément d'assemblage est défini comme un article pouvant être vendu contenant une nomenclature d'assemblage. Pour plus d'informations, reportez-vous à [Utiliser les nomenclatures](inventory-how-work-BOMs.md).

 Les ordres d'assemblage sont des ordres internes, tout comme les ordres de fabrication, qui permettent de gérer le processus d'assemblage et pour lier les besoins de vente aux activités entrepôt impliquées. Les ordres d'assemblage diffèrent des autres types de commande parce qu'ils impliquent à la fois la production et la consommation lors du report. L'en-tête d'ordre d'assemblage se comporte de façon similaire à une ligne journal de sortie, et les lignes d'ordre d'assemblage ont un comportement semblable aux lignes journal consommation.  

 Pour prendre en charge une stratégie d'inventaire juste-à-temps (JIT) et permettre la personnalisation des produits conformément aux demandes client, il est possible de créer des ordres d'assemblage et de les lier automatiquement dès que la ligne document de vente est créée. Le lien entre la demande de vente et l'approvisionnement d'assemblage permet aux préparateurs de documents de vente de personnaliser l'élément d'assemblage à la volée, d'établir les dates de livraison en fonction de la disponibilité des composantes, et de reporter la production et la livraison de l'article assemblé directement à partir de l'interface de document de vente. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).  

 Sur une ligne document de vente, vous pouvez vendre une quantité disponible et qui doit être prélevée à partir de l'inventaire conjointement à une quantité qui doit être assemblée pour commande. Certaines règles existent pour gérer la répartition de ces quantités afin de s'assurer que les quantités assembler pour commande sont prioritaires sur les quantités inventaire lors de livraisons partielles. Pour plus d’informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).  

 Il existe une fonctionnalité spéciale qui permet de gérer l'expédition des quantités à assembler pour commande. Lorsqu'une quantité à assembler pour commande est prête à être livrée, l'employé d'entrepôt responsable reporte un prélèvement inventaire pour la ou les lignes document de vente concernées. Cela crée un mouvement d'inventaire pour les composantes et reporte le résultat d'assemblage et la livraison du document de vente. Pour plus d’informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les prélèvements inventaire » dans [Prélever des articles avec les prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|En savoir plus sur la différence entre l'assemblage des articles juste avant la livraison des documents de vente et l'assemblage des articles destinés au stockage.|[Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md)|
|Renseignez les champs des fiches emplacement et de la configuration inventaire pour définir le flux des articles vers et depuis le département d'assemblage.|[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)|
|Personnalisez un élément d’assemblage sur la demande d’un client au cours du processus de vente, et convertissez-le en vente après acceptation.|[Établissement d'un devis de vente Assembler pour commande](assembly-how-to-quote-an-assemble-to-order-sale.md)|
|Combinez les composantes pour créer un article dans un processus simple, dans le cadre d'une commande ou d'un stock.|[Assembler des articles](assembly-how-to-assemble-items.md)|  
|Vendez les éléments d'assemblage qui ne sont pas disponibles actuellement en créant un ordre d'assemblage associé pour fournir la quantité totale ou partielle du document de vente.|[Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md)|
|Si certains articles à assembler pour commande sont déjà en inventaire, vous pouvez déduire cette quantité de l'ordre d'assemblage et la réserver dans l'inventaire.|[Vente d'articles d'inventaire dans des flux à assembler pour commande](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md)|  
|Lorsque vous vendez des éléments d'assemblage à partir de l'inventaire et que tous les articles ne sont pas disponibles, vous pouvez lancer un ordre d'assemblage automatiquement pour fournir une partie ou l'ensemble de la quantité sur document de vente.|[Vente simultanée d'articles à assembler pour commande et d'articles d'inventaire](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md)|
|Créez des éléments d'assemblage personnalisés pour les commandes permanentes ventes avant de créer périodiquement les documents de vente réels en fonction de l'entente commande permanente.|[Création d'ordres d'assemblage permanents](assembly-how-to-create-blanket-assembly-orders.md)|
|Annulez un ordre d'assemblage reporté, par exemple parce que l'ordre a été reporté avec des erreurs qui doivent être corrigées.|[Annuler le report d'assemblage](assembly-how-to-undo-assembly-posting.md)|
|En savoir plus sur la différence entre les nomenclatures d'assemblage et les nomenclatures de production et les différences de traitement impliquées.|[Utiliser les nomenclatures](inventory-how-work-BOMs.md)|
|Apprendre la manière dont la consommation d'assemblage et la production sont traitées lorsque vous reportez des ordres d'assemblage, et découvrir comment les coûts ressource et article sont traités et distribués aux écritures.|[Détails de conception : Report d'ordre d'assemblage](design-details-assembly-order-posting.md)|  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/assemble-items-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi

[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  
<!-- [Walkthrough: Planning Supplies Manually](walkthrough-planning-supplies-manually.md)   -->
<!-- [Walkthrough: Selling, Assembling, and Shipping Kits](walkthrough-selling-assembling-and-shipping-kits.md)   -->
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]