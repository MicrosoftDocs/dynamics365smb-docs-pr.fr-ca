---
title: Déplacement d’articles
description: Lorsque les articles sont en inventaire, il peut être nécessaire de les déplacer entre plusieurs zones pour prendre en charge les activités entrepôt quotidiennes permettant de conserver le flux d'articles dans l'entrepôt.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 7315, 7349, 7351, 7382, 7384, 7386, 7387, 7399, 7400, 9314, 9330, 9345
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: 19e6d291cf2547ac0a9ad45dce264e1e326dfad6
ms.sourcegitcommit: 00a8acc82cdc90e0d0db9d1a4f98a908944fd50a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9078242"
---
# <a name="moving-items"></a>Déplacement d'articles

L'activité entrepôt consistant à déplacer les articles dans l'entrepôt s'exécute différemment selon la configuration des fonctionnalités du module Gestion d'entrepôt. Le niveau de complexité du paramétrage varie : aucune fonctionnalité entrepôt, configurations de stockage de base pour le traitement par commande dans une ou plusieurs activités uniquement, configurations avancées dans lesquelles toutes les activités entrepôt doivent être exécutées dans un flux suggéré. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Dans un emplacement entrepôt, il peut être nécessaire de déplacer les articles entre plusieurs zones pour prendre en charge les activités entrepôt quotidiennes permettant de conserver le flux d'articles dans l'entrepôt. Certains mouvements se produisent en relation directe avec les opérations internes ; par exemple, lorsqu'un bon de production impose que des composantes soient livrées ou que des produits finis soient rangés. D'autres mouvements se produisent dans le cadre d'une simple optimisation de l'espace des entrepôts ou en tant que mouvements ad-hoc depuis ou vers des opérations.

Des tâches de mouvement supplémentaires ont lieu régulièrement afin de réapprovisionner les zones prélèvement et atelier et modifier les informations relatives au contenu des zones.

Le déplacement d'articles vers d'autres emplacements affecte les écritures article et doit donc être effectué dans le cadre d'un ordre de transfert. Pour plus d'informations, voir [Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).  

Les tâches de comptabilisation, d'ajustement et de reclassement d'articles liées à l'inventaire peuvent impliquer des tâches entrepôt qui doivent être effectuées sur les écritures entrepôt avant qu'elles puissent être synchronisées avec les écritures articles correspondantes. Pour plus d'informations, voir [Comptabilisation, ajustement et reclassement de l'inventaire](inventory-how-count-adjust-reclassify.md)  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Déplacer des articles d'un emplacement à l'autre dans des configurations entrepôt de base à tout moment et sans documents origine.|[Déplacer des articles dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)|
|Utiliser la feuille mouvement entrepôt pour déplacer des articles dans des configurations d'entrepôt avancées, pour les documents origine et ad hoc.|[Déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md)|  
|Ajouter des articles composante à des opérations internes dans des configurations entrepôt de base en fonction des demandes issues des documents origine de ces opérations.|[Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)|
|Planifier les emplacements à remplir ou vider pour maintenir un flux efficace (par exemple, vidage d'une zone de stockage en vrac avant une réception importante).|[Planifier des mouvements entrepôt dans la feuille](warehouse-how-to-plan-warehouse-movements-in-worksheets.md)|
|Mettre à jour la fréquence de réapprovisionnement des emplacements (emplacements prélèvement, etc.) suite aux fluctuations de la demande.|[Calculer le réapprovisionnement de la zone](warehouse-how-to-calculate-bin-replenishment.md)|
|Restructurez votre entrepôt avec de nouveaux codes et caractéristiques de zone et déplacez-les le cas échéant.|[Restructurer les entrepôts](warehouse-how-to-restructure-warehouses.md)|  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/manage-internal-warehouse-processes/)

## <a name="see-also"></a>Voir aussi .

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]