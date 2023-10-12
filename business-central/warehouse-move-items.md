---
title: Déplacement d’articles
description: Plus d’informations sur le déplacement d’articles entre les zones de votre entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: Conceptual
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.form: '7315, 7349, 7351, 7382, 7384, 7386, 7387, 7399, 7400, 9314, 9330, 9345'
---
# Déplacement d'articles

Vous pouvez déplacer des articles dans votre entrepôt de différentes manières, selon la façon dont vous avez configuré votre entrepôt. La complexité peut varier :

* Les petits entrepôts peuvent utiliser des configurations d’entrepôt de base pour gérer les commandes individuellement, en une ou plusieurs étapes.
* Les grands entrepôts peuvent utiliser des configurations avancées dans lesquelles toutes les activités de l’entrepôt sont coordonnées par un workflow dirigé. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Les articles peuvent devoir être déplacés entre les zones, par exemple, en raison d’opérations internes :

* Un bon de production nécessite la livraison de composantes ou le rangement de ses articles finis.
* Un responsable d’entrepôt souhaite optimiser l’espace.
* Des mouvements imprévus ont lieu vers et depuis les opérations.
* Le réapprovisionnement des zones de prélèvement ou des zones d’atelier.
* La mise à jour du contenu des zones.

Les tâches de comptage, d’ajustement et de reclassement des articles peuvent impliquer des tâches d’entrepôt qui doivent être effectuées sur les écritures entrepôt avant qu’elles puissent être synchronisées avec les écritures du grand livre d’articles correspondantes. Pour en savoir plus, voir [Comptabiliser, ajuster et reclasser l’inventaire](inventory-how-count-adjust-reclassify.md).  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Déplacer des articles entre emplacements|[Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)|
|Déplacer des articles d'un emplacement à l'autre dans des configurations entrepôt de base à tout moment et sans documents origine.|[Déplacer des articles dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)|
|Utilisez la feuille mouvement entrepôt, le prélèvement et le rangement internes pour déplacer des articles dans des configurations d’entrepôt avancées avec un prélèvement et un rangement dirigés.|[Déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md)|  
|Restructurez votre entrepôt avec de nouveaux codes et caractéristiques de zone et déplacez-les le cas échéant.|[Restructuration des entrepôts](warehouse-how-to-restructure-warehouses.md)|  

## Voir aussi .

[Vue d’ensemble de la gestion d’entrepôt](design-details-warehouse-management.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
