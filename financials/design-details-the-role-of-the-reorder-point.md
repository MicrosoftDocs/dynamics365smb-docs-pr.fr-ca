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
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-the-role-of-the-reorder-point"></a><span data-ttu-id="0f4c5-103">Détails de conception : Le rôle du point de commande</span><span class="sxs-lookup"><span data-stu-id="0f4c5-103">Design Details: The Role of the Reorder Point</span></span>
<span data-ttu-id="0f4c5-104">En plus de l'équilibrage général de la demande et de l'approvisionnement, le système de planification doit également surveiller les niveaux d'inventaire des articles affectés pour respecter les stratégies de réapprovisionnement définies.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-104">In addition to the general balancing of supply and demand, the planning system must also monitor inventory levels for the affected items to respect the defined reordering policies.</span></span>  
  
<span data-ttu-id="0f4c5-105">Un point de commande représente la demande lors d'un délai.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-105">A reorder point represents demand during lead time.</span></span> <span data-ttu-id="0f4c5-106">Lorsque l'inventaire prévisionnel passe en dessous du niveau d'inventaire défini par le point de réapprovisionnement, il est temps de commander une plus grande quantité.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-106">When the projected inventory passes below the inventory level defined by the reorder point, it is time to order more quantity.</span></span> <span data-ttu-id="0f4c5-107">Par ailleurs, l'inventaire doit diminuer progressivement et probablement atteindre zéro (ou le niveau d'inventaire de sécurité), jusqu'au moment du réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-107">Meanwhile, the inventory is expected to decrease gradually and possibly reach zero (or the safety stock level), until the replenishment arrives.</span></span>  
  
<span data-ttu-id="0f4c5-108">Par conséquent, le système de planification suggère une commande d'approvisionnement planifiée en aval au moment où l'inventaire prévisionnel passe sous le point de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-108">Accordingly, the planning system will suggest a forward-scheduled supply order at the point when the projected inventory passes below the reorder point.</span></span>  
  
<span data-ttu-id="0f4c5-109">Le point de réapprovisionnement indique un certain niveau d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-109">The reorder point reflects a certain inventory level.</span></span> <span data-ttu-id="0f4c5-110">Cependant, les niveaux d'inventaire peuvent changer de façon significative au cours de la plage de temps et, par conséquent, le système de planification doit constamment contrôler l'inventaire prévisionnel disponible.</span><span class="sxs-lookup"><span data-stu-id="0f4c5-110">However, inventory levels can move significantly during the time bucket and, therefore, the planning system must constantly monitor the projected available inventory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f4c5-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0f4c5-111">See Also</span></span>  
<span data-ttu-id="0f4c5-112">[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="0f4c5-112">[Design Details: Reordering Policies](design-details-reordering-policies.md) </span></span>  
<span data-ttu-id="0f4c5-113">[Détails de conception : paramètres de planification](design-details-planning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="0f4c5-113">[Design Details: Planning Parameters](design-details-planning-parameters.md) </span></span>  
<span data-ttu-id="0f4c5-114">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="0f4c5-114">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
[<span data-ttu-id="0f4c5-115">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="0f4c5-115">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)
