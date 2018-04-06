---
title: "Détails de conception - Qté maximum | Microsoft Docs"
description: "La stratégie de la quantité maximum permet de conserver l'inventaire à l'aide d'un point de réapprovisionnement."
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
ms.openlocfilehash: a9fd9a2387b209931165cd18bdfb025390778af5
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-maximum-qty"></a>Détails de conception : qté maximum.
La stratégie de la quantité maximum permet de conserver l'inventaire à l'aide d'un point de réapprovisionnement.  
  
 Tout ce qui concerne la stratégie Qté fixe de commande s'applique également à cette méthode. La seule différence est la quantité de l'approvisionnement proposé. Lors de l'utilisation de la stratégie de la quantité maximum, la quantité de réapprovisionnement est définie de façon dynamique en fonction du niveau d'inventaire prévisionnel et diffère donc généralement de celle de la stratégie commande à commande.  
  
## <a name="calculated-per-time-bucket"></a>Calculé par plage de temps  
 La quantité de réapprovisionnement est déterminée au moment (à la fin d'une plage de temps) où le système de planification détecte le que le point de réapprovisionnement a été dépassé. Le système mesure l'écart entre le niveau d'inventaire prévisionnel actuel et l'inventaire maximal spécifié. Cela constitue la quantité à recommander. Le système vérifie ensuite si l'approvisionnement a déjà été commandé ailleurs pour être reçu dans les délais et, si c'est le cas, réduit la quantité de la nouvelle commande d'approvisionnement des quantités déjà commandées.  
  
 Le système s'assure que l'inventaire prévisionnel atteint au moins le niveau du point de réapprovisionnement (dans la cas où l'utilisateur oublierait de spécifier une quantité d'inventaire maximum).  
  
## <a name="combines-with-order-modifiers"></a>Associe avec les modificateurs d'ordre  
 En fonction de la configuration, il peut être préférable de combiner la stratégie de la quantité maximum avec des modificateurs de commande pour garantir une quantité de commande minimale ou de l'arrondir au nombre supérieur d'unités de mesure d'achat, ou de le diviser en davantage de lots comme défini par la quantité maximum commande.  
  
## <a name="combines-with-calendars"></a>Combinaison avec des calendriers  
 Avant de proposer une nouvelle commande d'approvisionnement pour répondre à un point de recommande, le système de planification vérifie si la commande est programmée pour un jour chômé, en fonction des calendriers définis dans le champ **Code calendrier principal** des fenêtres **Informations compagnie** et **Fiche emplacement**.  
  
 Si la date programmée est un jour chômé, le système de planification déplace la commande en aval à la date de travail la plus proche. Cela peut entraîner une commande qui satisfait un point de commande mais ne pas satisfait une certaine demande spécifique. Pour une telle demande non soldée, le système de planification crée un approvisionnement supplémentaire.  
  
## <a name="see-also"></a>Voir aussi  
 [Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
 [Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
 [Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
 [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)
