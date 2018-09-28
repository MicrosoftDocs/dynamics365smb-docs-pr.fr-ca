---
title: "Détails de conception - Fermeture de la demande et de l'approvisionnement | Microsoft Docs"
description: "Cette rubrique suggère des tâches à effectuer une fois les procédures d'équilibrage d'approvisionnement exécutées."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, planning, example, closing, supply
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 6cacf967295944ba720c20203700db30d9ec45c4
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-closing-demand-and-supply"></a>Détails de conception : fermeture de la demande et de l'approvisionnement
Lorsque les procédures d'équilibre d'approvisionnement ont été réalisées, il existe trois situations de fin possibles :  
  
* La quantité et la date requises des événements de demande ont été respectées et leur planification peut être fermée. L'événement d'approvisionnement est encore ouvert et peut couvrir la demande suivante, donc la procédure de contrepartie peut recommencer avec l'événement d'approvisionnement actif et la demande suivante.  
* La commande approvisionnement ne peut pas être modifiée pour couvrir l'ensemble de la demande. L'événement demande est encore ouvert, avec une certaine quantité non couverte qui peut être couverte par l'événement suivant d'approvisionnement. Ainsi, l'événement d'approvisionnement actuel est fermé, donc l'acte d'équilibrage peut recommencer avec la demande actuelle et l'événement d'approvisionnement suivant.  
* L'ensemble de la demande a été couvert ; il n'existe aucune demande suivante (ou il n'y a pas de demande du tout). S'il existe un approvisionnement excédentaire, il peut être diminué (ou annulé), puis fermé. Il est possible que des événements d'approvisionnement supplémentaires existent plus loin dans la chaîne, et ils doivent également être annulés.  
  
Enfin, le système de planification crée un lien de chaînage entre l'approvisionnement et la demande.  
  
## <a name="creating-the-planning-line-suggested-action"></a>Création de la ligne planification (tâche suggérée)  
Si une tâche quelconque (Nouveau, Changer qté, Reprogrammer, Reprogrammer et changer qté ou Annuler) est suggérée pour modifier la commande approvisionnement, le système de planification crée une ligne planification dans la feuille planification. En raison du chaînage, la ligne planification est créée non seulement lorsque l'événement d'approvisionnement est fermé, mais également si l'événement de demande est fermé, même si l'événement d'approvisionnement est encore ouvert et qu'il peut être soumis à des modifications supplémentaires lorsque l'événement de demande suivant est traité. Cela signifie qu'après sa création, la ligne de planification peut être modifiée à nouveau.  
  
Pour réduire l'accès aux bases de données lors du traitement des bons de production, la ligne de planification peut être maintenue dans trois niveaux, tout en visant à effectuer le niveau d'entretien le moins exigeant :  
  
* Créer uniquement la ligne planification avec la date d'échéance et la quantité actuelles mais sans itinéraire et composantes.  
* Inclure l'itinéraire : l'itinéraire planifié est présenté avec le calcul des dates et heures de début et de fin. Ceci est exigeant en termes d'accès aux bases de données. Pour déterminer les dates de fin et d'échéance, il peut être nécessaire de calculer ceci même si l'événement d'approvisionnement n'a pas été fermé (dans le cas d'une planification en aval).  
* Inclure l'éclatement de la nomenclature : ceci peut attendre juste avant que l'événement approvisionnement soit fermé.  
  
Cela conclut les descriptions de la manière dont la demande et l'approvisionnement sont chargés, priorisés et équilibrés par le système de planification. En association avec cette activité de planification des approvisionnements, le système doit veiller à ce que le niveau d'inventaire requis de chaque article planifié soit maintenu en fonction de ses stratégies de réapprovisionnement.  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)   
[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)
