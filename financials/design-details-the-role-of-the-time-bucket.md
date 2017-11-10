---
title: "Détails de conception - Le rôle de la plage de temps | Microsoft Docs"
description: "L'objectif de la plage de temps est de collecter les événements de demande dans la fenêtre de temps de manière à effectuer une commande d'approvisionnement commune."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: eb1b1a401dabe09a77c44558e9f5a83388078aaa
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-the-role-of-the-time-bucket"></a><span data-ttu-id="787c0-103">Détails de conception : rôle de la plage de temps</span><span class="sxs-lookup"><span data-stu-id="787c0-103">Design Details: The Role of the Time Bucket</span></span>
<span data-ttu-id="787c0-104">L'objectif de la plage de temps est de collecter les événements de demande dans la fenêtre de temps de manière à effectuer une commande d'approvisionnement commune.</span><span class="sxs-lookup"><span data-stu-id="787c0-104">The purpose of the time bucket is to collect demand events within the time window in order to make a joint supply order.</span></span>  
  
 <span data-ttu-id="787c0-105">Pour les méthodes de réapprovisionnement qui utilisent un point de réapprovisionnement, vous pouvez définir une plage de temps.</span><span class="sxs-lookup"><span data-stu-id="787c0-105">For reordering policies that use a reorder point, you can define a time bucket.</span></span> <span data-ttu-id="787c0-106">Cela garantit que la demande dans la même période est accumulée avant d'évaluer l'impact sur l'inventaire prévisionnel et de vérifier si le point de réapprovisionnement a été atteint.</span><span class="sxs-lookup"><span data-stu-id="787c0-106">This ensures that demand within the same time period is accumulated before checking the impact on the projected inventory and whether the reorder point has been passed.</span></span> <span data-ttu-id="787c0-107">Si le point de réapprovisionnement est passé, une nouvelle commande approvisionnement est programmée en aval à partir de la fin de la période définie par la plage de temps.</span><span class="sxs-lookup"><span data-stu-id="787c0-107">If the reorder point is passed, a new supply order is scheduled forward from the end of the period defined by the time bucket.</span></span> <span data-ttu-id="787c0-108">Les plages de temps débutent à la date de début de la planification.</span><span class="sxs-lookup"><span data-stu-id="787c0-108">The time buckets begin on the planning starting date.</span></span>  
  
 <span data-ttu-id="787c0-109">Le concept de plage de temps reflète le processus manuel de vérification fréquente du niveau d'inventaire plutôt que pour chaque transaction.</span><span class="sxs-lookup"><span data-stu-id="787c0-109">The time-bucketed concept reflects the manual process of checking the inventory level on a frequent basis rather than for each transaction.</span></span> <span data-ttu-id="787c0-110">L'utilisateur doit définir la fréquence (plage de temps).</span><span class="sxs-lookup"><span data-stu-id="787c0-110">The user needs to define the frequency (the time bucket).</span></span> <span data-ttu-id="787c0-111">Par exemple, l'utilisateur regroupe les besoins article d'un fournisseur pour passer une commande hebdomadaire.</span><span class="sxs-lookup"><span data-stu-id="787c0-111">For example, the user gathers all item needs from one vendor to place a weekly order.</span></span>  
  
 ![](media/nav_app_supply_planning_2_reorder_cycle.png "NAV_APP_supply_planning_2_reorder_cycle")  
  
 <span data-ttu-id="787c0-112">La plage de temps est généralement utilisée pour éviter un effet cascade.</span><span class="sxs-lookup"><span data-stu-id="787c0-112">The time bucket is generally used to avoid a cascade effect.</span></span> <span data-ttu-id="787c0-113">Par exemple, une ligne équilibrée de demande et d'approvisionnement dans laquelle une demande antérieure est annulée ou une nouvelle demande est créée.</span><span class="sxs-lookup"><span data-stu-id="787c0-113">For example, a balanced row of demand and supply where an early demand is canceled, or a new one is created.</span></span> <span data-ttu-id="787c0-114">Le résultat est que chaque commande d'approvisionnement est reprogrammée (excepté la dernière).</span><span class="sxs-lookup"><span data-stu-id="787c0-114">The result would be that every supply order (except the last one) is rescheduled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787c0-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="787c0-115">See Also</span></span>  
 <span data-ttu-id="787c0-116">[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="787c0-116">[Design Details: Reordering Policies](design-details-reordering-policies.md) </span></span>  
 <span data-ttu-id="787c0-117">[Détails de conception : paramètres de planification](design-details-planning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="787c0-117">[Design Details: Planning Parameters](design-details-planning-parameters.md) </span></span>  
 <span data-ttu-id="787c0-118">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="787c0-118">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
 [<span data-ttu-id="787c0-119">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="787c0-119">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)