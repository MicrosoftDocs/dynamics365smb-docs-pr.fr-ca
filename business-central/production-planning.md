---
title: Planification de l'approvisionnement| Microsoft Docs
description: "Préparez un programme exécutable détaillé ainsi que le calendrier de production de l'assemblage final pour la demande de vente et de production."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/14/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: a512e8e4e693a44015bc7675e5126259a5eff92b
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="planning"></a>Planification
Les opérations de production nécessaires à la transformation d'entrées en produits finis doivent être planifiées de manière quotidienne ou hebdomadaire en fonction du volume et de la nature des produits. [!INCLUDE[d365fin](includes/d365fin_md.md)] fournit des fonctionnalités permettant de répondre à la demande réelle et anticipée des ventes, de l'assemblage et de la production, et inclut des fonctionnalités pour une planification de la distribution basée sur les unités de stock et les transferts d'emplacement.

> [!NOTE]
> Cette rubrique décrit essentiellement la planification des compagnies impliquées dans la fabrication ou la gestion d'assemblage, où les commandes d'approvisionnement qui en résultent peuvent être des ordres de production, d'assemblage, de transfert ou des bons de commande. L'interface principale de cette tâche de planification est la fenêtre **Feuille planification**.

> [!INCLUDE[d365fin](includes/d365fin_md.md)] prend également en charge la planification de l'approvisionnement pour les compagnies de vente en gros, où les commandes d'approvisionnement qui en résultent peuvent être des ordres de transfert et des bons de commande. L'interface principale de cette tâche de planification est la fenêtre **Feuille de réquisition**, qui est décrite indirectement dans cette rubrique, car la plupart des fonctionnalités de planification s'appliquent aux deux feuilles.

Avant de planifier et d'exécuter des bons de production, vous devez configurer des capacités de production, par exemple créer des calendriers usine, des itinéraires, des nomenclatures production et des unités de production. Pour plus d'informations, voir [Paramétrage de la production](production-configure-production-processes.md).

La planification peut être considérée comme la préparation des commandes d'approvisionnement requises dans les départements d'assemblage ou de fabrication pour répondre à la demande. Pour plus d'informations, voir [Gestion d'assemblage](assembly-assemble-items.md) et [Production](production-manage-manufacturing.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Apprendre à utiliser le système de planification pour détecter la demande et lui donner la priorité et pour proposer un programme d'approvisionnement équilibré.|[À propos de la fonctionnalité Planification](production-about-planning-functionality.md)|
|Comprendre tous les aspects du système de planification et modifier les algorithmes pour répondre aux exigences de planification dans différents environnements.|[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)|
|Découvrez comment la logique de planification établit la différence entre la demande dans les emplacements en fonction de la configuration des unités de stock et la demande sans codes emplacement.|[Planification avec/sans emplacement](production-planning-with-without-locations.md).|
|Prévoir la demande de production présentée par les commandes vente et les ordres de fabrication prévus.|[Créer une prévision production](production-how-to-create-a-forecast.md)|  
|Créez automatiquement des bons de production un à un à partir d'un document de vente pour couvrir la demande exacte des lignes document de vente.|[Créer des bons de production à partir de documents de vente](production-how-to-create-production-orders-from-sales-orders.md)|
|Créer un bon de production projet directement à partir d'un document de vente multiligne représentant un projet de production.|[Planifier les O.F. projets](production-how-to-plan-project-orders.md)|
|Utiliser la fenêtre **Planification commande** pour effectuer la planification manuellement pour des ordres de vente ou de fabrication un niveau de nomenclature de production à la fois.|[Planifier de nouvelles demandes commande par commande](production-how-to-plan-for-new-demand.md)|
|Utilisez la fenêtre **Feuille planification** pour exécuter les options MPS et MRP afin de créer automatiquement un plan d'approvisionnement détaillé ou de haut niveau à tous les niveaux d'article.|[Exécuter une planification complète et un calcul PDP ou MRP](production-how-to-run-mps-and-mrp.md)|
|Exécuter la feuille de réquisition pour créer automatiquement un programme d'approvisionnement détaillé pour répondre à la demande d'articles réapprovisionnés uniquement par achat ou transfert.|Page **Feuille de réquisition**|  
|Lancez ou mettez à jour un bon de production en tant qu'opérations programmées approximativement dans le calendrier de production principal.|[Replanifier ou actualiser directement des ordres de fabrication](production-how-to-replan-refresh-production-orders.md)|
|Recalculez les calendriers d'atelier ou d'unité de production en raison de changements de planification.|Section « Pour calculer un calendrier d'atelier » dans [Configurer des calendriers usine](production-how-to-create-work-center-calendars.md)|
|Suivez la demande de commande (quantité suivie), les prévisions, les commandes permanentes ventes ou les paramètres de planification (quantité non suivie) qui ont donné lieu à la ligne planification en question.|[Suivre les relations entre l'offre et la demande](production-how-track-demand-supply.md)|
|Afficher le stock disponible prévu sous différents types d'affichage et voir quels besoins bruts, réceptions de commandes planifiées et autres événements l'influencent dans le temps.|[Voir la disponibilité des articles](inventory-how-availability-overview.md)|  
|Effectuez des activités de planification sélectionnées, comme la modification ou l'ajout de lignes feuille planification, dans une vue graphique du programme d'approvisionnement.|[Modifier les propositions de planification dans une vue graphique](production-how-to-modify-planning-suggestions-in-a-graphical-view.md)|

## <a name="see-also"></a>Voir aussi
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]

