---
title: Configurer les processus de production | Microsoft Docs
description: "Pour convertir des matières en articles finis produits, vous devez configurer des ressources de production, telles que les nomenclatures, les itinéraires, les opérateurs machines et les machines, dans le système."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/04/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: de493a4697c3a5c2fb8581545a29ee832fe1c3dc
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="setting-up-manufacturing"></a>Paramétrage de la production
Pour convertir des matières en articles finis produits, vous devez configurer des ressources de production, telles que les nomenclatures, les gammes, les opérateurs machines et les machines, dans le système.

Les opérateurs et les machines sont représentés dans le système comme des unités de production pouvant être organisées en ateliers et en groupes d'ateliers. Lorsque ces ressources sont établies, elles peuvent être chargées avec des opérations en fonction des nomenclatures matières et de la structure (itinéraire) opératoire définies pour l'article, et en fonction de la capacité de l'unité de production ou de l'atelier. Vous pouvez également configurer la capacité de production de chaque ressource. La capacité est définie par le temps de travail disponible dans les postes et centres de charge, et est gérée par des calendriers pour chaque niveau. Un calendrier d'atelier spécifie les jours ouvrés et les heures de travail, les équipes, les jours fériés et les absences déterminant la capacité disponible brute de l'atelier (généralement mesurée en minutes). Tout cela est déterminé par les valeurs d'efficacité et de capacité définies.  

Une fois que vous avez paramétré la production, vous pouvez planifier et exécuter des ordres de fabrication. Pour plus d'informations, voir [Planification](production-planning.md) et [Production](production-manage-manufacturing.md).  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Configurer les fonctionnalités de fabrication, telles que la définition des heures de travail atelier et la sélection des principes de planification.|Page **Configuration de la fabrication**.|  
|Définir une semaine de travail standard dans le département Production en termes d'heures de début et de fin de chaque journée de travail et des équipes associées.|[Procédure : créer des calendriers usine](production-how-to-create-work-center-calendars.md)|  
|Organisez les exigences et les valeurs fixes des ressources de production en tant qu'ateliers ou unités de production pour régir leur sortie de production.|[Procédure : configurer des ateliers et des unités de production](production-how-to-set-up-work-and-machine-centers.md)|
|Organisez les opérations de production dans l'ordre requis et affectez-les aux ateliers ou unités de production avec les temps de travail nécessaires.|[Comment créer des gammes](production-how-to-create-routings.md)|
|Organisez des sous-assemblages ou des composantes de production sous un article parent produit et certifiez la nomenclature d'exécution dans les ateliers.|[Comment créer des nomenclatures de production](production-how-to-create-production-boms.md)|
|Vérifiez que la quantité appropriée de composantes est disponible lorsque des articles produits sont stockés dans une unité de mesure mais produits dans une autre.|[Procédure : utiliser les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)|  
|Définir des familles d'articles produits ayant des processus de fabrication similaires pour réduire la consommation. Par exemple, quatre pièces du même article et dix pièces d'un autre peuvent être fabriquées simultanément à partir d'une plaque.|[Procédure : utiliser les familles de production](production-how-work-family.md)|
|Utilisez des tâches standard pour simplifier la création d'itinéraires en associant rapidement des informations supplémentaires aux opérations récurrentes.|[Procédure : configurer des lignes itinéraire standard](production-how-set-up-standard-routing-lines.md)|  
|Préparez les centres de charge et les gammes à représenter les opérations de production sous-traitées.|[Procédure : sous-traiter la production](production-how-to-subcontract-manufacturing.md)|  

## <a name="see-also"></a>Voir aussi
[Production](production-manage-manufacturing.md)    
[Planification](production-planning.md)   
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

