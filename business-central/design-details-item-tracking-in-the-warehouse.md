---
title: "Détails de conception - Traçabilité dans l'entrepôt | Microsoft Docs"
description: "La gestion de numéro de série et de numéro de lot est surtout une tâche d'entrepôt, et donc tous les documents entrepôt enlogement et désenlogement ont une fonctionnalité standard pour affecter et sélectionner des numéros traçabilité. Toutefois, comme le système de réservation est basé sur les écritures article, les documents activité entrepôt qui enregistrent uniquement les écritures entrepôt ne sont pas totalement pris en charge."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, item, tracking, serial number, lot number, outbound documents
ms.date: 01/15/2019
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 5d6d2d9527e81a92987f6b8fcdbe8e087c3c537a
ms.openlocfilehash: e780dba122374bd80e48ca6bbc74b7540e034ac6
ms.contentlocale: fr-ca
ms.lasthandoff: 01/22/2019

---
# <a name="design-details-item-tracking-in-the-warehouse"></a><span data-ttu-id="c06f1-104">Détails de conception : traçabilité dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="c06f1-104">Design Details: Item Tracking in the Warehouse</span></span>
<span data-ttu-id="c06f1-105">La gestion de numéro de série et de numéro de lot est surtout une tâche d'entrepôt, et donc tous les documents entrepôt enlogement et désenlogement ont une fonctionnalité standard pour affecter et sélectionner des numéros traçabilité.</span><span class="sxs-lookup"><span data-stu-id="c06f1-105">Serial number and lot number handling is primarily a warehouse task and therefore all inbound and outbound warehouse documents have standard functionality for assigning and selecting item tracking numbers.</span></span>  

<span data-ttu-id="c06f1-106">Toutefois, comme le système de réservation est basé sur les écritures article, les documents activité entrepôt qui enregistrent uniquement les écritures entrepôt ne sont pas totalement pris en charge.</span><span class="sxs-lookup"><span data-stu-id="c06f1-106">However, because the reservation system is based on item ledger entries, warehouse activity documents that register only warehouse entries are not fully supported.</span></span> <span data-ttu-id="c06f1-107">Comme les réservations et les numéros traçabilité peuvent uniquement être traités au niveau emplacement, pas au niveau de la zone, la page **Lignes traçabilité** ne peut pas être ouverte à partir des documents activité entrepôt.</span><span class="sxs-lookup"><span data-stu-id="c06f1-107">Because reservations and item tracking numbers can be handled only at the location level, not at the bin and zone level, the **Item Tracking Lines** page cannot be opened from warehouse activity documents.</span></span> <span data-ttu-id="c06f1-108">Cela s'applique également à la page **Réservation**.</span><span class="sxs-lookup"><span data-stu-id="c06f1-108">The same applies to the **Reservation** page.</span></span>  

<span data-ttu-id="c06f1-109">Une fois qu'un numéro de série ou un numéro de lot a été ajouté à un article dans un emplacement entrepôt, il peut être déplacé et reclassé librement au sein de l'entrepôt à l'aide d'une structure de traçabilité distincte, qui n'est pas liée au système de réservation.</span><span class="sxs-lookup"><span data-stu-id="c06f1-109">After a serial or lot number has been added to an item at a warehouse location, it can be moved and reclassified freely within the warehouse by using an independent item tracking structure that is unrelated to the reservation system.</span></span> <span data-ttu-id="c06f1-110">Les champs **N° de série** et **N° lot** sont consultés directement dans les lignes document entrepôt.</span><span class="sxs-lookup"><span data-stu-id="c06f1-110">**Serial No.** and **Lot No.** fields are accessed directly on warehouse document lines.</span></span> <span data-ttu-id="c06f1-111">Lorsque le numéro de série ou de lot participe ultérieurement à un report sortant, il est synchronisé avec le système de réservation en tant que partie d'ajustement de zone ordinaire.</span><span class="sxs-lookup"><span data-stu-id="c06f1-111">When the serial or lot number later partakes in outbound posting, it is synchronized with the reservation system as a part of ordinary bin adjustment.</span></span> <span data-ttu-id="c06f1-112">Pour plus d'informations, voir [Détails de conception : intégration avec l'inventaire](design-details-integration-with-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="c06f1-112">For more information, see [Design Details: Integration with Inventory](design-details-integration-with-inventory.md).</span></span>  

<span data-ttu-id="c06f1-113">Cependant, le système de réservation prend en compte les activités entrepôt pour calculer la disponibilité.</span><span class="sxs-lookup"><span data-stu-id="c06f1-113">However, the reservation system does take warehouse activities into consideration when it calculates availability.</span></span> <span data-ttu-id="c06f1-114">Par exemple, des articles qui sont affectés aux prélèvements ou enregistrés comme prélevés, ne peuvent pas être réservés.</span><span class="sxs-lookup"><span data-stu-id="c06f1-114">For example, items that are allocated to picks, or registered as picked, cannot be reserved.</span></span> <span data-ttu-id="c06f1-115">Pour plus d'informations, voir [Détails de conception : disponibilité de l'entrepôt](design-details-availability-in-the-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="c06f1-115">For more information, see [Design Details: Warehouse Availability](design-details-availability-in-the-warehouse.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c06f1-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c06f1-116">See Also</span></span>  
[<span data-ttu-id="c06f1-117">Détails de conception : traçabilité</span><span class="sxs-lookup"><span data-stu-id="c06f1-117">Design Details: Item Tracking</span></span>](design-details-item-tracking.md)  
[<span data-ttu-id="c06f1-118">Détails de conception : intégration avec l'inventaire</span><span class="sxs-lookup"><span data-stu-id="c06f1-118">Design Details: Integration with Inventory</span></span>](design-details-integration-with-inventory.md)  
[<span data-ttu-id="c06f1-119">Détails de conception : Disponibilité de l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="c06f1-119">Design Details: Warehouse Availability</span></span>](design-details-availability-in-the-warehouse.md)  
[<span data-ttu-id="c06f1-120">Détails de conception : création de traçabilité</span><span class="sxs-lookup"><span data-stu-id="c06f1-120">Design Details: Item Tracking Design</span></span>](design-details-item-tracking-design.md)

