---
title: Configuration des processus entrepôt | Microsoft Docs
description: "La stratégie de distribution d'une compagnie se reflète dans la configuration de ses processus entrepôt : Cela inclut la définition de la manière dont différents articles sont traités dans différents entrepôts (par exemple, degré de contrôle des zones et étendue du flux de travail requis entre les activités entrepôt)."
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/04/2018
ms.author: sgroespe
ms.openlocfilehash: 7f7d07ce7965b0db0f9779e396b1818ce398e812
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813777"
---
# <a name="setting-up-warehouse-management"></a>Configuration de la gestion des entrepôts
La stratégie de distribution d'une compagnie se reflète dans la configuration de ses processus entrepôt : Cela inclut la définition de la manière dont différents articles sont traités dans différents entrepôts (par exemple, degré de contrôle des zones et étendue du flux de travail requis entre les activités entrepôt).  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Obtenir un aperçu des capacités de base par rapport à la fonctionnalité de stockage avancée.|[Détails de conception : vue d'ensemble d'entrepôt](design-details-warehouse-overview.md)|  
|Configurer huit types de zones (zone prélèvement, par exemple) pour définir les activités de flux associées à chaque type de zone.|[Configurer des types de zone](warehouse-how-to-set-up-bin-types.md)|  
|Créez des zones manuellement ou automatiquement avec des informations (nom, séries de numéros et catégorie) sur la base d'un modèle de zone.|[Créer zones](warehouse-how-to-create-individual-bins.md)|  
|Définir quels articles vous souhaitez stocker dans une zone donnée et définir les règles devant être suivies lors du remplissage de la zone avec un article spécifique.|[Créer les contenus de la zone](warehouse-how-to-set-up-bin-contents.md)|  
|Définir un article de sorte qu'il soit toujours stocké dans une zone spécifique.|[Affecter des zones par défaut à des articles](warehouse-how-to-assign-default-bins-to-items.md)|
|Créer des modèles pour gérer l'emplacement et le mode de rangement des articles dans le cadre du rangement suggéré.|[Configurer des modèles rangement](warehouse-how-to-set-up-put-away-templates.md)|
|Définir des utilisateurs comme employés d'entrepôts spécifiques.|[Configurer des employés d'entrepôt](warehouse-how-to-set-up-warehouse-employees.md)|
|Définir différents types d'emplacement dans l'entrepôt pour contrôler l'emplacement des articles sur la base de leur type, priorité ou niveau de traitement.|[Configurer des emplacements de sorte qu'ils utilisent des zones](warehouse-how-to-set-up-locations-to-use-bins.md)|
|Définir des paramètres supplémentaires pour un emplacement existant afin de l'activer pour les activités entrepôt.|[Convertir des emplacements existants en entrepôts](warehouse-how-to-convert-existing-locations-to-warehouse-locations.md)|
|Activez le prélèvement, le déplacement et le rangement des ordres d'assemblage ou de fabrication dans des configurations de stockage de base.|[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)|  
|Configurez des articles et des emplacements pour la portée de gestion d'entrepôt la plus avancée dans laquelle toutes les activités doivent suivre un flux strict.|[Configurer des articles et des emplacements pour prélèvement et rangement suggérés](warehouse-how-to-set-up-items-for-directed-put-away-and-pick.md)|  
|Définir la date et le mode d'inventaire des articles dans les entrepôts à des fins d'entretien ou de génération de rapports financiers.|[Nombre, ajustement ou reclassement de l'inventaire](inventory-how-count-adjust-reclassify.md)|
|Permettez aux employés d'entrepôt de diviser une unité de mesure plus grande en unités de mesure plus petites afin de répondre aux besoins des documents sources.|[Activer la rupture de charge automatique avec prélèvement et rangement dirigé](warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md)|  
|Configurer l'entrepôt de manière à ce qu'il suggère automatiquement les articles à prélever qui expirent en premier.|[Activer le prélèvement par FEFO](warehouse-picking-by-fefo.md)|
|Obtenir des conseils relatifs à la réorganisation des magasins, emplacements ou zones pour générer des activités entrepôt plus efficaces.|[Restructurer les entrepôts](warehouse-how-to-restructure-warehouses.md)|
|Intégrez les lecteurs de code barres à votre solution de gestion d'entrepôt. Uniquement pour le déploiement sur site.|[Utilisation des systèmes de saisie automatisée (ADCS)](warehouse-use-automated-data-capture-systems-adcs.md)|

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
