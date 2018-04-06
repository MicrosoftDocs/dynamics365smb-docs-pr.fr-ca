---
title: "Détails de conception - Le rôle de la plage de temps | Microsoft Docs"
description: "L'objectif de la plage de temps est de collecter les événements de demande dans la fenêtre de temps de manière à effectuer une commande d'approvisionnement commune."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 099465f0ef7bdafa3df80c377cd83b177bb68072
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-the-role-of-the-time-bucket"></a>Détails de conception : rôle de la plage de temps
L'objectif de la plage de temps est de collecter les événements de demande dans la fenêtre de temps de manière à effectuer une commande d'approvisionnement commune.  
  
 Pour les méthodes de réapprovisionnement qui utilisent un point de réapprovisionnement, vous pouvez définir une plage de temps. Cela garantit que la demande dans la même période est accumulée avant d'évaluer l'impact sur l'inventaire prévisionnel et de vérifier si le point de réapprovisionnement a été atteint. Si le point de réapprovisionnement est passé, une nouvelle commande approvisionnement est programmée en aval à partir de la fin de la période définie par la plage de temps. Les plages de temps débutent à la date de début de la planification.  
  
 Le concept de plage de temps reflète le processus manuel de vérification fréquente du niveau d'inventaire plutôt que pour chaque transaction. L'utilisateur doit définir la fréquence (plage de temps). Par exemple, l'utilisateur regroupe les besoins article d'un fournisseur pour passer une commande hebdomadaire.  
  
 ![](media/nav_app_supply_planning_2_reorder_cycle.png "NAV_APP_supply_planning_2_reorder_cycle")  
  
 La plage de temps est généralement utilisée pour éviter un effet cascade. Par exemple, une ligne équilibrée de demande et d'approvisionnement dans laquelle une demande antérieure est annulée ou une nouvelle demande est créée. Le résultat est que chaque commande d'approvisionnement est reprogrammée (excepté la dernière).  
  
## <a name="see-also"></a>Voir aussi  
 [Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
 [Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
 [Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
 [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)
