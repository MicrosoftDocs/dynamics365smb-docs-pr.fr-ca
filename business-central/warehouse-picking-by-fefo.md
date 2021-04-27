---
title: Comment activer le prélèvement par FEFO | Microsoft Docs
description: First-Expired-First-Out (FEFO) est une méthode de tri qui garantit que les articles les plus anciens, ceux qui ont les dates d'expiration les plus anciennes, sont prélevés en premier.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 3a47c9daeeab036055a0644e1b389735f7440106
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5784077"
---
# <a name="enable-picking-items-by-fefo"></a><span data-ttu-id="844c4-103">Activer le prélèvement d'articles par FEFO</span><span class="sxs-lookup"><span data-stu-id="844c4-103">Enable Picking Items by FEFO</span></span>
<span data-ttu-id="844c4-104">First-Expired-First-Out (FEFO) est une méthode de tri qui garantit que les articles les plus anciens, ceux qui ont les dates d'expiration les plus anciennes, sont prélevés en premier.</span><span class="sxs-lookup"><span data-stu-id="844c4-104">First-Expired-First-Out (FEFO) is a sorting method that ensures that the oldest items, those with the earliest expiration dates, are picked first.</span></span>  

 <span data-ttu-id="844c4-105">Cette fonctionnalité ne fonctionne que lorsque les critères suivants sont réunis :</span><span class="sxs-lookup"><span data-stu-id="844c4-105">This functionality only works when the following criteria are met:</span></span>  

-   <span data-ttu-id="844c4-106">L'article doit avoir un numéro de série/lot.</span><span class="sxs-lookup"><span data-stu-id="844c4-106">The item must have a serial/lot number.</span></span>  
-   <span data-ttu-id="844c4-107">Dans la configuration du code de traçabilité article de l'article, le champ **Traçabilité d'entrepôt par numéro de série** ou le champ **Traçabilité d'entrepôt par numéro de lot** doit être sélectionné.</span><span class="sxs-lookup"><span data-stu-id="844c4-107">On the item’s item tracking code setup, the **SN Warehouse Tracking** field or the **Lot Warehouse Tracking** field must be selected.</span></span>  
-   <span data-ttu-id="844c4-108">L'article doit être reporté dans l'inventaire avec une date d'expiration.</span><span class="sxs-lookup"><span data-stu-id="844c4-108">The item must be posted to inventory with an expiration date.</span></span>  
-   <span data-ttu-id="844c4-109">Dans l'emplacement, les boutons de basculement **Prélèvement requis**, **Prélèvement par FEFO**, et **Zone obligatoire** doivent être activés.</span><span class="sxs-lookup"><span data-stu-id="844c4-109">On the location, the **Require Pick**, **Pick According to FEFO**, and **Bin Mandatory** toggles must be turned on.</span></span>  

 <span data-ttu-id="844c4-110">Lorsque tous les critères sont réunis, les articles aux numéros de série/lot à prélever sont triés par ancienneté de prélèvements et mouvements, sauf pour les articles qui utilisent la traçabilité par numéro de série ou de lot.</span><span class="sxs-lookup"><span data-stu-id="844c4-110">When all the criteria are met, then serial/lot-numbered items to be picked are sorted with the oldest first in all picks and movements, except for items that use SN-specific or lot-specific tracking.</span></span>  

> [!NOTE]  
> <span data-ttu-id="844c4-111">Si certains articles avec numéros de série ou lot utilisent une traçabilité spécifique, ceux-ci sont respectés en premier et, en dessous, les numéros de série/lot non spécifiques restants sont listés selon FEFO.</span><span class="sxs-lookup"><span data-stu-id="844c4-111">If some serial or lot-numbered items use specific tracking, then those are respected first and under them, the remaining, non-specific, serial/lot numbers are listed according to FEFO.</span></span>
<br /><br />
<span data-ttu-id="844c4-112">Si deux articles avec des numéros de série ou de lot ont la même date d'expiration, l’application sélectionne celui avec le plus petit numéro de lot ou de série.</span><span class="sxs-lookup"><span data-stu-id="844c4-112">If two serial or lot-numbered items have the same expiration date, then the application selects the item with the lowest serial or lot number.</span></span>
<br /><br />
<span data-ttu-id="844c4-113">Lors du prélèvement d'articles avec numéro de série/de lot dans les emplacements configurés pour un prélèvement et un rangement suggérés, seules les quantités des zones de type *Prélèvement* sont prélevées selon FEFO.</span><span class="sxs-lookup"><span data-stu-id="844c4-113">When picking serial or lot-numbered items in locations set up for directed put-away and pick, only quantities on bins of type *Pick* are picked according to FEFO.</span></span>  
<br /><br />
<span data-ttu-id="844c4-114">Pour activer des mouvements selon FEFO, laissez le champ **Depuis zone** vide sur la page **Mouvement d'inventaire** ou les pages **Feuille mouvement**.</span><span class="sxs-lookup"><span data-stu-id="844c4-114">To enable movements according to FEFO, leave the **From Bin** field empty on the **Inventory Movement** page or the **Movement Worksheet** pages.</span></span>  
<br /><br />
<span data-ttu-id="844c4-115">Si le champ **Report expiration strict** est sélectionné sur la **Fiche Code traçabilité**, seuls les articles non expirés seront inclus dans le prélèvement et les lignes seront triées selon le principe FEFO.</span><span class="sxs-lookup"><span data-stu-id="844c4-115">If the **Strict Expiration Posting** field is selected on the **Item Tracking Code Card**, only items that are not expired will be included in the pick, and the lines are sorted according to the FEFO principle.</span></span>

## <a name="see-also"></a><span data-ttu-id="844c4-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="844c4-116">See Also</span></span>  
<span data-ttu-id="844c4-117">[Prélèvement des articles](warehouse-pick-items.md) </span><span class="sxs-lookup"><span data-stu-id="844c4-117">[Picking Items](warehouse-pick-items.md) </span></span>  
<span data-ttu-id="844c4-118">[Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md) </span><span class="sxs-lookup"><span data-stu-id="844c4-118">[Pick Items for Warehouse Shipment](warehouse-how-to-pick-items-for-warehouse-shipment.md) </span></span>  
<span data-ttu-id="844c4-119">[Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md) </span><span class="sxs-lookup"><span data-stu-id="844c4-119">[Pick Items with Inventory Picks](warehouse-how-to-pick-items-with-inventory-picks.md) </span></span>  
[<span data-ttu-id="844c4-120">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="844c4-120">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
[<span data-ttu-id="844c4-121">Stock</span><span class="sxs-lookup"><span data-stu-id="844c4-121">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="844c4-122">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="844c4-122">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]