---
title: "Détails de conception - Surveillance du niveau d'inventaire prévisionnel et du point de réapprovisionnement | Microsoft Docs"
description: "Découvrez comment la planification d'inventaire différencie les niveaux d'inventaire prévisionnel et les niveaux d'inventaire disponible prévu."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, supply, inventory, planning
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 336b5c300cf3640d7356313d2d627f6b4008c7b4
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="design-details-monitoring-the-projected-inventory-level-and-the-reorder-point"></a>Détails de conception : contrôle du niveau d'inventaire prévisionnel et du point de réapprovisionnement
L'inventaire est un type d'approvisionnement, mais pour la planification de l'inventaire, le système de planification différencie deux niveaux d'inventaire :  

* Inventaire prévisionnel  
* Inventaire disponible prévu  

## <a name="projected-inventory"></a>Inventaire projeté  
Normalement, l'inventaire prévisionnel est la quantité d'inventaire brut, y compris les demandes et approvisionnements du passé même s'ils n'ont pas été reportés, au début du processus de planification. Dans le futur, cela devient un niveau d'inventaire prévisionnel mobile qui est mis à jour par les quantités brutes d'un approvisionnement et d'une demande futurs parce que ceux-ci sont saisis suivant la planification (réservés ou affectés autrement).  

L'inventaire prévisionnel est utilisé par le système de planification pour contrôler le point de réapprovisionnement et pour déterminer la quantité de réapprovisionnement lorsque la méthode de réapprovisionnement Qté maximum est utilisée.  

## <a name="projected-available-inventory"></a>Inventaire disponible prévu  
L'inventaire prévisionnel disponible est la partie de l'inventaire prévisionnel qui est disponible à un moment donné pour honorer une demande. L'inventaire disponible prévu est utilisé par le moteur de planification lors du contrôle du niveau de stock de sécurité.  

L'inventaire disponible prévu est utilisé par le système de planification pour contrôler le niveau de stock de sécurité, parce que l'inventaire de sécurité doit toujours être disponible pour satisfaire une demande inattendue.  

## <a name="time-buckets"></a>Intervalles de planification  
Un contrôle strict de l'inventaire prévisionnel est crucial pour détecter le moment où le point de réapprovisionnement est atteint et pour calculer la quantité de commande correcte à l'aide de la stratégie de réapprovisionnement de la quantité maximum.  

Comme indiqué précédemment, le niveau d'inventaire prévisionnel est calculé au début de la période de planification. Il s'agit d'un niveau brut qui ne tient pas compte des réservations et des ventilations similaires. Pour contrôler ce niveau d'inventaire durant la séquence de planification, le système gère les changements cumulés sur une période de temps, une plage de temps. Le système garantit que la plage de temps est au moins d'un jour comme il s'agit de l'unité de temps la plus précise pour une demande ou un événement d'approvisionnement.  

## <a name="determining-the-projected-inventory-level"></a>Déterminer le niveau d'inventaire prévisionnel  
La séquence suivante décrit la manière dont le niveau d'inventaire prévisionnel est déterminé :  

* Lorsqu'un événement d'approvisionnement, tel qu'un bon de commande, a été totalement planifié, il augmente l'inventaire prévisionnel à sa date d'échéance.  
* Lorsqu'un événement de demande est entièrement satisfait, il ne diminue pas l'inventaire prévisionnel immédiatement. Au lieu de cela, il reporte un rappel de diminution. Il s'agit d'un enregistrement interne qui contient la date et la quantité de la contribution à l'inventaire prévisionnel.  
* Lorsqu'un événement d'approvisionnement ultérieur est planifié et placé sur la chronologie, les rappels de diminution reportés sont examinés un à un jusqu'à la date d'approvisionnement planifiée, tout en mettant à jour l'inventaire prévisionnel. Lors de ce processus, le niveau du point de réapprovisionnement du rappel interne d'augmentation peut être atteint ou dépassé.  
* Si une nouvelle commande approvisionnement est créée, le système vérifie si elle est saisie avant l'approvisionnement actif. Si c'est le cas, le nouvel approvisionnement devient l'approvisionnement actif et la procédure d'équilibrage reprend depuis le début.  

Voici une illustration graphique de ce principe :  

![Déterminer le niveau d'inventaire prévisionnel](media/nav_app_supply_planning_2_projected_inventory.png "Déterminer le niveau d'inventaire prévisionnel")  

1. L'approvisionnement **Sa** de 4 (fixe) ferme la demande **Da** de -3.  
2. CloseDemand : créez un rappel de baisse de -3 (pas affiché).  
3. L'approvisionnement **Sa** est fermé avec un excédent de 1 (plus aucune demande n'existe).  

     Cela augmente le niveau d'inventaire prévisionnel à +4, alors que l'inventaire **disponible** prévisionnel devient -1.  

4. L'approvisionnement suivant **Sb** de 2 (une autre commande) a déjà été placé dans la chronologie.  
5. Le système vérifie s'il y a des rappels de sortie précédant **Sb** (comme il n'y en a pas, aucune action n'est effectuée).  
6. Le système ferme l'approvisionnement **Sb** (plus aucune demande n'existe)—A : en réduisant à 0 (annuler) ou B : en le laissant tel quel.  

     Cela entraîne l'augmentation du niveau de stock projeté (A : +0 => +4 or B : +2 = +6).  

7. Le système effectue un contrôle final : existe-t-il un rappel de diminution ? Oui, il y en a un en date du **Da**.  
8. Le système ajoute le rappel de diminution -3 au niveau d'inventaire prévisionnel, soit A : +4 -3 = 1 ou B : +6 -3 = +3.  
9. Dans le cas A, le système crée une commande programmée en aval qui commence à la date **Da**.  

     Dans le cas de B, le point de commande est atteint et aucune commande n'est créée.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)

