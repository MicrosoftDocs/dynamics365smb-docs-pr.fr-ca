---
title: Procédure de suivi des relations entre l'offre et la demande | Microsoft Docs
description: À partir d'un document d'approvisionnement ou de demande dans le réseau d'ordres, vous pouvez suivre la demande de commande (quantité suivie), les prévisions, les commandes permanentes ventes ou les paramètres de planification (quantité non suivie) qui ont donné lieu à la ligne planification en question.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: beb438be379cfc6e3f239ebb0ae270a2e957651c
ms.sourcegitcommit: addfb47612cc2e4e98dfd7e338b6f41cde405d5c
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/16/2019
ms.locfileid: "938500"
---
# <a name="track-relations-between-demand-and-supply"></a><span data-ttu-id="041b1-103">Suivre les relations entre l'offre et la demande</span><span class="sxs-lookup"><span data-stu-id="041b1-103">Track Relations Between Demand and Supply</span></span>
<span data-ttu-id="041b1-104">À partir d'un document d'approvisionnement ou de demande dans le réseau d'ordres, vous pouvez suivre la demande de commande (quantité suivie), les prévisions, les commandes permanentes ventes ou les paramètres de planification (quantité non suivie) qui ont donné lieu à la ligne planification en question.</span><span class="sxs-lookup"><span data-stu-id="041b1-104">From any supply or demand document in the so-called order network, you can track the order demand (tracked quantity), forecast, blanket sales order, or planning parameter (untracked quantity) that has given rise to the planning line in question.</span></span>

<span data-ttu-id="041b1-105">Les feuilles planification incluent également des informations de planification sur les entités sans rapport avec les commandes pour aider le gestionnaire à obtenir un programme d'approvisionnement optimal.</span><span class="sxs-lookup"><span data-stu-id="041b1-105">The planning worksheets also offers supporting planning information about non-order entities to help the planner obtain an optimal supply plan.</span></span> <span data-ttu-id="041b1-106">Pour plus d'informations, voir [Éléments planification sans suivi](production-how-track-demand-supply.md#untracked-planning-elements).</span><span class="sxs-lookup"><span data-stu-id="041b1-106">For more information, see [Untracked Planning Elements](production-how-track-demand-supply.md#untracked-planning-elements).</span></span>

## <a name="to-track-linked-items"></a><span data-ttu-id="041b1-107">Pour chaîner des articles liés</span><span class="sxs-lookup"><span data-stu-id="041b1-107">To track linked items</span></span>
<span data-ttu-id="041b1-108">Par l'intermédiaire des systèmes de planification et de réservation, le suivi de commande montre de quelle manière les documents de vente, les bons de production et les bons de commande sont reliés aux ordres de fabrication.</span><span class="sxs-lookup"><span data-stu-id="041b1-108">Order tracking shows how sales orders, production orders, and purchase orders are related to the manufacturing order through the planning and reservation systems.</span></span>

<span data-ttu-id="041b1-109">La procédure suivante décrit comment chaîner des articles liés sur un ordre de fabrication planifié ferme.</span><span class="sxs-lookup"><span data-stu-id="041b1-109">The following describes how to track linked items on a firm planned production order.</span></span> <span data-ttu-id="041b1-110">La procédure est similaire pour tous les autres types de commande, et à partir des lignes feuille planification.</span><span class="sxs-lookup"><span data-stu-id="041b1-110">The steps are similar for all other order types, and from planning worksheet lines.</span></span>

1. <span data-ttu-id="041b1-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **O.F. planifié ferme**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="041b1-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Firm Planned Prod. Order**, and then choose the related link.</span></span>
2. <span data-ttu-id="041b1-112">Ouvrez le bon de production planifié ferme approprié dans la liste.</span><span class="sxs-lookup"><span data-stu-id="041b1-112">Open the relevant firm planned production order from the list.</span></span>
3. <span data-ttu-id="041b1-113">Sur le raccourci **Lignes**, choisissez l'action **Fonctions**, puis l'action **Chaînage**.</span><span class="sxs-lookup"><span data-stu-id="041b1-113">On the **Lines** FastTab, choose the **Functions** action, and then choose the **Order Tracking** action.</span></span>

<span data-ttu-id="041b1-114">Les lignes de la fenêtre **Chaînage** affichent les documents liés à la ligne de l'ordre de fabrication en cours.</span><span class="sxs-lookup"><span data-stu-id="041b1-114">The lines in the **Order Tracking** display the documents that are related to the current production order line.</span></span>

## <a name="untracked-planning-elements"></a><span data-ttu-id="041b1-115">Éléments de planification sans traçabilité</span><span class="sxs-lookup"><span data-stu-id="041b1-115">Untracked Planning Elements</span></span>
<span data-ttu-id="041b1-116">La page **Éléments planification sans suivi** s'affiche lorsque vous cliquez sur le champ **Qté sans suivi** sur la page **Planification commande**.</span><span class="sxs-lookup"><span data-stu-id="041b1-116">The **Untracked Planning Elements** page opens when you choose the **Untracked Qty.** field on the **order Planning** page.</span></span> <span data-ttu-id="041b1-117">Elle a deux objectifs :</span><span class="sxs-lookup"><span data-stu-id="041b1-117">It serves two purposes:</span></span>

1. <span data-ttu-id="041b1-118">Stockage d'informations sur les quantités non chaînées qui s'affichent lorsque l'utilisateur affiche la page Chaînage.</span><span class="sxs-lookup"><span data-stu-id="041b1-118">To hold information about untracked quantities displayed when the user looks up from the Order Tracking page to see untracked quantities.</span></span>
2. <span data-ttu-id="041b1-119">Stockage des messages d'avertissement qui s'affichent lorsque l'utilisateur clique sur l'icône **Avertissement** sur la page **Feuille planification**.</span><span class="sxs-lookup"><span data-stu-id="041b1-119">To hold warning messages displayed when the user chooses the **Warning** icon on the **Planning Worksheet** page.</span></span>

<span data-ttu-id="041b1-120">la page inclut les écritures représentant une quantité excédentaire non chaînée du réseau de chaînage.</span><span class="sxs-lookup"><span data-stu-id="041b1-120">The page contains entries which account for an untracked surplus quantity in order tracking network.</span></span> <span data-ttu-id="041b1-121">Ces écritures sont générées au cours de l'exécution de la planification et expliquent la provenance de la quantité excédentaire non chaînée des lignes chaînage.</span><span class="sxs-lookup"><span data-stu-id="041b1-121">These entries are generated during the planning run and explain where the untracked surplus quantity in the order tracking lines came from.</span></span> <span data-ttu-id="041b1-122">Cet excédent non chaîné peut provenir des lignes suivantes :</span><span class="sxs-lookup"><span data-stu-id="041b1-122">This untracked surplus can come from:</span></span>

- <span data-ttu-id="041b1-123">Prévisions production ;</span><span class="sxs-lookup"><span data-stu-id="041b1-123">Production forecast</span></span>
- <span data-ttu-id="041b1-124">Commandes ouvertes ;</span><span class="sxs-lookup"><span data-stu-id="041b1-124">Blanket orders</span></span>
- <span data-ttu-id="041b1-125">Stock de sécurité ;</span><span class="sxs-lookup"><span data-stu-id="041b1-125">Safety stock quantity</span></span>
- <span data-ttu-id="041b1-126">Point de commande ;</span><span class="sxs-lookup"><span data-stu-id="041b1-126">Reorder point</span></span>
- <span data-ttu-id="041b1-127">Inventaire maximum</span><span class="sxs-lookup"><span data-stu-id="041b1-127">Maximum inventory</span></span>
- <span data-ttu-id="041b1-128">Quantité de réappro. ;</span><span class="sxs-lookup"><span data-stu-id="041b1-128">Reorder quantity</span></span>
- <span data-ttu-id="041b1-129">Qté maximum commande ;</span><span class="sxs-lookup"><span data-stu-id="041b1-129">Maximum order quantity</span></span>
- <span data-ttu-id="041b1-130">Qté minimum commande ;</span><span class="sxs-lookup"><span data-stu-id="041b1-130">Minimum order quantity</span></span>
- <span data-ttu-id="041b1-131">Commandé par ;</span><span class="sxs-lookup"><span data-stu-id="041b1-131">Order multiple</span></span>
- <span data-ttu-id="041b1-132">Seuil (% taille lot).</span><span class="sxs-lookup"><span data-stu-id="041b1-132">Dampener (% of lot size)</span></span>

## <a name="see-also"></a><span data-ttu-id="041b1-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="041b1-133">See Also</span></span>  
<span data-ttu-id="041b1-134">[Planification](production-planning.md) </span><span class="sxs-lookup"><span data-stu-id="041b1-134">[Planning](production-planning.md) </span></span>  
[<span data-ttu-id="041b1-135">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="041b1-135">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="041b1-136">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="041b1-136">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="041b1-137">Stock</span><span class="sxs-lookup"><span data-stu-id="041b1-137">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="041b1-138">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="041b1-138">Purchasing</span></span>](purchasing-manage-purchasing.md)  
[<span data-ttu-id="041b1-139">Détails de conception : réservation, chaînage et message d'action</span><span class="sxs-lookup"><span data-stu-id="041b1-139">Design Details: Reservation, Tracking, and Action Messaging</span></span>](design-details-reservation-order-tracking-and-action-messaging.md)  
<span data-ttu-id="041b1-140">[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md) </span><span class="sxs-lookup"><span data-stu-id="041b1-140">[Design Details: Supply Planning](design-details-supply-planning.md) </span></span>  
[<span data-ttu-id="041b1-141">Configurer des recommandations : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="041b1-141">Setup Best Practices: Supply Planning</span></span>](setup-best-practices-supply-planning.md)  
<span data-ttu-id="041b1-142">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="041b1-142">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
