---
title: "Détails de conception - Le rôle du point de commande | Microsoft Docs"
description: "Cette rubrique met l'accent sur l'importance de définir un point de réapprovisionnement, afin de déterminer quand commander plus d'inventaire."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: desigh, reorder, demand, supply
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 5b5e3cec4bc5af8188470ea1d711422c0130677e
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-the-role-of-the-reorder-point"></a>Détails de conception : Le rôle du point de commande
En plus de l'équilibrage général de la demande et de l'approvisionnement, le système de planification doit également surveiller les niveaux d'inventaire des articles affectés pour respecter les stratégies de réapprovisionnement définies.  
  
Un point de commande représente la demande lors d'un délai. Lorsque l'inventaire prévisionnel passe en dessous du niveau d'inventaire défini par le point de réapprovisionnement, il est temps de commander une plus grande quantité. Par ailleurs, l'inventaire doit diminuer progressivement et probablement atteindre zéro (ou le niveau d'inventaire de sécurité), jusqu'au moment du réapprovisionnement.  
  
Par conséquent, le système de planification suggère une commande d'approvisionnement planifiée en aval au moment où l'inventaire prévisionnel passe sous le point de réapprovisionnement.  
  
Le point de réapprovisionnement indique un certain niveau d'inventaire. Cependant, les niveaux d'inventaire peuvent changer de façon significative au cours de la plage de temps et, par conséquent, le système de planification doit constamment contrôler l'inventaire prévisionnel disponible.  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)
