---
title: Prélèvement d'articles
description: L’activité consistant à prélever les articles avant leur livraison ou consommation s’exécute différemment selon la configuration des fonctionnalités du module Gestion d’entrepôt.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 5779, 5798, 7343, 7345, 7357, 7359, 7377, 7392, 7395, 7397, 9313, 9316, 9344
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: 07cb13480146496c7186cef2d845c4a799eb699a
ms.sourcegitcommit: 3acadf94fa34ca57fc137cb2296e644fbabc1a60
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/19/2022
ms.locfileid: "9535594"
---
# <a name="pick-items"></a>Prélèvement d'articles

L'activité entrepôt consistant à prélever les articles avant leur livraison ou consommation s'exécute différemment selon la configuration des fonctions de gestion des entrepôts. Le niveau de complexité du paramétrage varie : aucune fonctionnalité entrepôt, configurations de stockage de base pour le traitement par commande dans une ou plusieurs activités uniquement, configurations avancées dans lesquelles toutes les activités entrepôt doivent être exécutées dans un flux suggéré. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Si vous décidez d'organiser et d'enregistrer votre activité de prélèvement avec des documents entrepôt, activez le champ **Prélèvement requis** dans la fiche emplacement. Ceci indique que lorsque vous avez des articles devant être prélevés pour un document origine sortant, vous souhaitez que le prélèvement de ces articles soit contrôlé par le système. Un document source sortant peut être un document de vente, un retour achat, une commande transfert sortant, une commande service ou un bon de production dont les composantes doivent être prélevées.

> [!NOTE]
> Bien que le paramètre soit appelé **Prélèvement requis**, vous pouvez quand même reporter les livraisons directement à partir des documents commerciaux sources dans lesquels vous cochez cette case.

Si votre emplacement est configuré pour exiger un traitement des prélèvements, mais pas un traitement des livraisons, vous utilisez la page **Prélèvement inventaire** pour organiser les informations de prélèvement, les imprimer, entrer le résultat du prélèvement effectif et reporter les informations de prélèvement, ce qui reporte les informations de livraison des articles. Dans le cas du prélèvement de composantes pour un bon de production, le report du prélèvement reporte également la consommation.

Si votre emplacement est configuré pour qu'il exige le traitement des prélèvements et celui des livraisons (ce qui implique que vous avez activé les champs **Prélèvement requis** et **Livraison requise** dans la fiche emplacement), vous utilisez la page **Prélèvement entrepôt** pour gérer le prélèvement. Le prélèvement entrepôt fonctionne de manière similaire au prélèvement inventaire, si ce n'est qu'au lieu de reporter les informations de prélèvement, vous enregistrez le prélèvement. Ce processus d'enregistrement ne reporte pas la livraison, mais assure simplement la disponibilité des articles pour livraison. En tant qu'administrateur entrepôt, vous pouvez utiliser des feuilles prélèvement pour organiser les informations de prélèvement avant de créer des instructions de prélèvement entrepôt.

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|
|------------|-------------|  
|Reporter la livraison d'articles directement dans le document commande sortante car aucune fonctionnalité entrepôt n'existe. (Valable également pour les documents de vente, les ordres de transfert sortants et les livraisons retour.)|[Livrer des articles](warehouse-how-ship-items.md)|  
|Prélever les articles par commande et reporter la livraison dans la même activité dans une configuration entrepôt de base.|[Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md)|
|Prélever les articles de plusieurs commandes dans une configuration entrepôt avancée.|[Prélever des articles avec les prélèvements entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md)|  
|Prélevez les composantes pour la production ou l'assemblage dans une configuration d'entrepôt de base.|[Prélever pour la fabrication ou l'assemblage dans les configurations de stockage de base.](warehouse-how-to-pick-for-production.md)|
|Prélevez les composantes pour la production ou l'assemblage dans une configuration d'entrepôt avancée.|[Prélever pour la fabrication ou l'assemblage dans les configurations de stockage avancées.](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)|  
|Planifier des instructions de prélèvement optimisées pour plusieurs livraisons. Dans ce cas, les magasiniers n'ont pas à agir directement sur les livraisons reportées.|[Planifier des prélèvements dans la feuille](warehouse-how-to-plan-picks-in-worksheets.md)|  
|Prélever des articles techniquement dans un but spécifique, par exemple une unité de production nécessitant des composants supplémentaires, de sorte que les articles ne quittent pas techniquement l'entrepôt.|[Prélever et ranger sans document origine](warehouse-how-to-create-put-aways-from-internal-put-aways.md)|
|Sachez comment prélever automatiquement des articles en fonction de leur date d'échéance, par exemple des denrées périssables.|[Prélèvement par FEFO](warehouse-picking-by-fefo.md)|
|Éclatez une ligne prélèvement en plusieurs lignes, par exemple si la zone désignée ne contient pas suffisamment d'articles à prélever.|[Répartir des lignes activité entrepôt](warehouse-how-to-split-warehouse-activity-lines.md)|
|Accéder immédiatement aux prélèvements qui vous ont été affectés en tant que magasinier.|[Trouver vos affectations d'entrepôt](warehouse-how-to-find-your-warehouse-assignments.md)|  

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/pick-ship-items-business-central/) associée

## <a name="see-also"></a>Voir aussi .

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
