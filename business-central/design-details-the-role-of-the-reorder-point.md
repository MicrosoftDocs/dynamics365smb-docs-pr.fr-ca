---
title: "Détails de conception - Le rôle du point de commande | Microsoft Docs"
description: "Cette rubrique met l'accent sur l'importance de définir un point de réapprovisionnement, afin de déterminer quand commander plus d'inventaire."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: desigh, reorder, demand, supply
ms.date: 10/01/2018
ms.author: sgroespe
redirect_url: design-details-handling-reordering-policies
ms.translationtype: HT
ms.sourcegitcommit: 67400e424305cc705db5c1bd52a8e4de17ecc5a9
ms.openlocfilehash: e39a7efdc796e8745bd9d8f7d74cdcfb171d851f
ms.contentlocale: fr-ca
ms.lasthandoff: 11/20/2018

---
# <a name="design-details-the-role-of-the-reorder-point"></a><span data-ttu-id="e825d-103">Détails de conception : Le rôle du point de commande</span><span class="sxs-lookup"><span data-stu-id="e825d-103">Design Details: The Role of the Reorder Point</span></span>
<span data-ttu-id="e825d-104">En plus de l'équilibrage général de la demande et de l'approvisionnement, le système de planification doit également surveiller les niveaux d'inventaire des articles affectés pour respecter les stratégies de réapprovisionnement définies.</span><span class="sxs-lookup"><span data-stu-id="e825d-104">In addition to the general balancing of supply and demand, the planning system must also monitor inventory levels for the affected items to respect the defined reordering policies.</span></span>  

<span data-ttu-id="e825d-105">Un point de commande représente la demande lors d'un délai.</span><span class="sxs-lookup"><span data-stu-id="e825d-105">A reorder point represents demand during lead time.</span></span> <span data-ttu-id="e825d-106">Lorsque l'inventaire prévisionnel passe en dessous du niveau d'inventaire défini par le point de réapprovisionnement, il est temps de commander une plus grande quantité.</span><span class="sxs-lookup"><span data-stu-id="e825d-106">When the projected inventory passes below the inventory level defined by the reorder point, it is time to order more quantity.</span></span> <span data-ttu-id="e825d-107">Par ailleurs, l'inventaire doit diminuer progressivement et probablement atteindre zéro (ou le niveau d'inventaire de sécurité), jusqu'au moment du réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="e825d-107">Meanwhile, the inventory is expected to decrease gradually and possibly reach zero (or the safety stock level), until the replenishment arrives.</span></span>  

<span data-ttu-id="e825d-108">Par conséquent, le système de planification suggère une commande d'approvisionnement planifiée en aval au moment où l'inventaire prévisionnel passe sous le point de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="e825d-108">Accordingly, the planning system will suggest a forward-scheduled supply order at the point when the projected inventory passes below the reorder point.</span></span>  

<span data-ttu-id="e825d-109">Le point de réapprovisionnement indique un certain niveau d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="e825d-109">The reorder point reflects a certain inventory level.</span></span> <span data-ttu-id="e825d-110">Cependant, les niveaux d'inventaire peuvent changer de façon significative au cours de la plage de temps et, par conséquent, le système de planification doit constamment contrôler l'inventaire prévisionnel disponible.</span><span class="sxs-lookup"><span data-stu-id="e825d-110">However, inventory levels can move significantly during the time bucket and, therefore, the planning system must constantly monitor the projected available inventory.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e825d-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e825d-111">See Also</span></span>  
<span data-ttu-id="e825d-112">[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="e825d-112">[Design Details: Reordering Policies](design-details-reordering-policies.md) </span></span>  
<span data-ttu-id="e825d-113">[Détails de conception : paramètres de planification](design-details-planning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="e825d-113">[Design Details: Planning Parameters](design-details-planning-parameters.md) </span></span>  
<span data-ttu-id="e825d-114">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="e825d-114">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
[<span data-ttu-id="e825d-115">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="e825d-115">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)

