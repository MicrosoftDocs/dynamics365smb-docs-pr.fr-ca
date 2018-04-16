---
title: "Activités entrepôt | Microsoft Docs"
description: "Entre la réception des biens et leur livraison, une série d'utilisations entrepôt internes a lieu pour assurer un flux efficace dans l'entrepôt, ainsi que pour organiser et mettre à jour les inventaires de la compagnie."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/15/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: acef03f32124c5983846bc6ed0c4d332c9c8b347
ms.openlocfilehash: 7540467cdb958f82a64ca0097b365b09b2d1e947
ms.contentlocale: fr-ca
ms.lasthandoff: 04/16/2018

---
# <a name="warehouse-management"></a><span data-ttu-id="1f4e1-103">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="1f4e1-103">Warehouse Management</span></span>
<span data-ttu-id="1f4e1-104">Entre la réception des biens et leur livraison, une série d'utilisations entrepôt internes a lieu pour assurer un flux efficace dans l'entrepôt, ainsi que pour organiser et mettre à jour les inventaires de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-104">After goods are received and before goods are shipped, a series of internal warehouse activities take place to ensure an effective flow through the warehouse and to organize and maintain company inventories.</span></span>

<span data-ttu-id="1f4e1-105">Les activités entrepôt courantes incluent le rangement d'articles, leur déplacement entre plusieurs entrepôts et leur prélèvement à des fins d'assemblage, de production et de livraison.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-105">Typical warehouse activities include putting items away, moving items inside or between warehouses, and picking items for assembly, production, or shipment.</span></span> <span data-ttu-id="1f4e1-106">Assembler des articles pour les ventes ou l'inventaire peut également être considéré comme des activités entrepôt, mais cela est traité ailleurs.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-106">Assembling items for sale or inventory may also be considered warehouse activities, but these are covered elsewhere.</span></span> <span data-ttu-id="1f4e1-107">Pour plus d'informations, voir [Gestion d'assemblage](assembly-assemble-items.md).</span><span class="sxs-lookup"><span data-stu-id="1f4e1-107">For more information, see [Assembly Management](assembly-assemble-items.md).</span></span>  

<span data-ttu-id="1f4e1-108">Dans les entrepôts importants, vous pouvez séparer ces tâches de traitement par département et gérer l'intégration par un flux suggéré.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-108">In large warehouses, these different handling tasks can be separated by departments and the integration managed by a directed workflow.</span></span> <span data-ttu-id="1f4e1-109">Dans les installations plus simples, le flux est moins formalisé et vous pouvez exécuter les activités entrepôt avec les rangements et prélèvements stock.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-109">In simpler installations, the flow is less formalized and the warehouse activities are performed with so-called inventory put-aways and inventory picks.</span></span> <span data-ttu-id="1f4e1-110">Pour plus d'informations sur les configurations entrepôt de base et avancées, voir [Détails de conception : vue d'ensemble d'entrepôt](design-details-warehouse-overview.md).</span><span class="sxs-lookup"><span data-stu-id="1f4e1-110">For more information about basic versus advanced warehouse configurations, see [Design Details: Warehouse Overview](design-details-warehouse-overview.md).</span></span>

<span data-ttu-id="1f4e1-111">Avant d'effectuer des activités entrepôt, vous devez configurer le système pour la complexité de traitement d'entrepôt appropriée.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-111">Before you can perform warehouse activities, you must set the system up for the relevant complexity of warehouse processing.</span></span> <span data-ttu-id="1f4e1-112">Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="1f4e1-112">For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).</span></span>

 <span data-ttu-id="1f4e1-113">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-113">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>   

|<span data-ttu-id="1f4e1-114">**Pour**</span><span class="sxs-lookup"><span data-stu-id="1f4e1-114">**To**</span></span>|<span data-ttu-id="1f4e1-115">**Voir**</span><span class="sxs-lookup"><span data-stu-id="1f4e1-115">**See**</span></span>|  
|------------|-------------|  
|<span data-ttu-id="1f4e1-116">Enregistrez la réception d'articles dans les emplacements entrepôts, soit avec un bon de commande uniquement, dans les configurations d'emplacement simples, soit avec une réception entrepôt, en cas de traitement d'entrepôt partiellement ou entièrement automatisé dans l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-116">Record the receipt of items at warehouse locations, either with a purchase order only, in simple location setups, or with a warehouse receipt, in case of semi or fully automated warehouse processing at the location.</span></span>|[<span data-ttu-id="1f4e1-117">Réceptionner des articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-117">Receive Items</span></span>](warehouse-how-receive-items.md)|
|<span data-ttu-id="1f4e1-118">Contourner les processus de rangement et de prélèvement pour expédier un article directement de la réception ou fabrication à l'expédition.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-118">Bypass the put-away and pick processes to expedite an item straight from receiving or production to shipping.</span></span>|[<span data-ttu-id="1f4e1-119">Transborder des articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-119">Cross-Dock Items</span></span>](warehouse-how-to-cross-dock-items.md)|    
|<span data-ttu-id="1f4e1-120">Ranger les articles provenant des achats, retours vente, transferts ou de la production en fonction du processus d'entrepôt configuré.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-120">Put away items received from purchases, sales returns, transfers, or production output according to the configured warehouse process.</span></span>|[<span data-ttu-id="1f4e1-121">Rangement des articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-121">Putting Items Away</span></span>](warehouse-put-away-items.md)|
|<span data-ttu-id="1f4e1-122">Déplacez des articles d'une zone à l'autre dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-122">Move items between bins in the warehouse.</span></span>|[<span data-ttu-id="1f4e1-123">Déplacement d'articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-123">Moving Items</span></span>](warehouse-move-items.md)|
|<span data-ttu-id="1f4e1-124">Prélever des articles à livrer, transférer ou consommer en assemblage ou production, en fonction du processus d'entrepôt configuré.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-124">Pick items to be shipped, transferred, or consumed in assembly or production, according to the configured warehouse process.</span></span>|[<span data-ttu-id="1f4e1-125">Prélèvement des articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-125">Picking Items</span></span>](warehouse-pick-items.md)|
|<span data-ttu-id="1f4e1-126">Enregistrez la livraison d'articles à partir d'emplacements entrepôts, soit avec un document de vente uniquement, dans les configurations d'emplacement simples, soit avec une livraison entrepôt, en cas de processus d'entrepôt partiellement ou entièrement automatisés dans l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="1f4e1-126">Record the shipment of items from warehouse locations, either with a sales order only, in simple location setups, or with a warehouse shipment, in case of semi or fully automated warehouse processes at the location.</span></span>|[<span data-ttu-id="1f4e1-127">Livrer des articles</span><span class="sxs-lookup"><span data-stu-id="1f4e1-127">Ship Items</span></span>](warehouse-how-ship-items.md)|  

## <a name="see-also"></a><span data-ttu-id="1f4e1-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f4e1-128">See Also</span></span>  
[<span data-ttu-id="1f4e1-129">Stock</span><span class="sxs-lookup"><span data-stu-id="1f4e1-129">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="1f4e1-130">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="1f4e1-130">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="1f4e1-131">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="1f4e1-131">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="1f4e1-132">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="1f4e1-132">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="1f4e1-133">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1f4e1-133">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

## [!INCLUDE [d365fin](includes/free_trial_md.md)]  
## [!INCLUDE [d365fin](includes/training_link_md.md)]

