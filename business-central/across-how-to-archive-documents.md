---
title: "Procédure d'archivage des documents vente et achat | Microsoft Docs"
description: "Vous pouvez archiver des documents de vente et des bons de commande, des devis, des retours et des commandes permanentes, et vous pouvez utiliser le document archivé pour recréer le document d'origine."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 12/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 74460bfcff36d293006229f4a89719f8c05c2631
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="archive-documents"></a><span data-ttu-id="6300c-103">Archiver des documents</span><span class="sxs-lookup"><span data-stu-id="6300c-103">Archive Documents</span></span>
<span data-ttu-id="6300c-104">Vous pouvez archiver des documents de vente et des bons de commande, des devis, des retours et des commandes permanentes, et vous pouvez utiliser le document archivé pour recréer le document d'origine.</span><span class="sxs-lookup"><span data-stu-id="6300c-104">You can archive sales and purchase orders, quotes, return orders, and blanket orders, and you can use the archived document to recreate the document that it was archived from.</span></span>

## <a name="to-set-up-automatic-document-archiving"></a><span data-ttu-id="6300c-105">Pour configurer l'archivage automatique des documents</span><span class="sxs-lookup"><span data-stu-id="6300c-105">To set up automatic document archiving</span></span>  
<span data-ttu-id="6300c-106">Vous pouvez configurer l'archivage automatique des documents de vente, des bons de commande, des devis, des commandes permanentes et des retours, avant de supprimer des documents.</span><span class="sxs-lookup"><span data-stu-id="6300c-106">You can set up automatic archiving of sales and purchase orders, quotes, blanket orders, and return orders, before you delete documents.</span></span>

<span data-ttu-id="6300c-107">La procédure suivante décrit comment configurer l'archivage automatique des documents vente.</span><span class="sxs-lookup"><span data-stu-id="6300c-107">The following procedure describes how to set up automatic archiving of sales documents.</span></span> <span data-ttu-id="6300c-108">La procédure est identique pour les documents achat.</span><span class="sxs-lookup"><span data-stu-id="6300c-108">The steps are similar for purchase documents.</span></span>
1.  <span data-ttu-id="6300c-109">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Paramètres ventes**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6300c-109">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="6300c-110">Dans la fenêtre **Configuration ventes et à recevoir**, renseignez les champs comme suit.</span><span class="sxs-lookup"><span data-stu-id="6300c-110">In the **Sales & Receivables Setup** window, fill in the fields as follows.</span></span>

|<span data-ttu-id="6300c-111">Champ</span><span class="sxs-lookup"><span data-stu-id="6300c-111">Field</span></span>|<span data-ttu-id="6300c-112">Description</span><span class="sxs-lookup"><span data-stu-id="6300c-112">Description</span></span>|
|-----|-----------|
|<span data-ttu-id="6300c-113">**Archivage des devis**</span><span class="sxs-lookup"><span data-stu-id="6300c-113">**Archiving Sales Quotes**</span></span>|<span data-ttu-id="6300c-114">**Jamais** pour ne jamais archiver les devis lorsqu'ils sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="6300c-114">**Never** to never archive sales quotes when they are deleted.</span></span> <span data-ttu-id="6300c-115">**Question** pour demander à l'utilisateur s'il souhaite archiver les devis lorsqu'ils sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="6300c-115">**Question** to prompt the user to choose whether to archive sales quotes when they are deleted.</span></span> <span data-ttu-id="6300c-116">**Toujours** pour archiver automatiquement les devis lorsqu'ils sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="6300c-116">**Always** to archive sales quotes automatically when they are deleted.</span></span>|
|<span data-ttu-id="6300c-117">**Archivage des commandes permanentes ventes**</span><span class="sxs-lookup"><span data-stu-id="6300c-117">**Archiving Blanket Sales Orders**</span></span>|<span data-ttu-id="6300c-118">Permet d'archiver automatiquement les commandes permanentes ventes chaque fois qu'elles sont supprimées.</span><span class="sxs-lookup"><span data-stu-id="6300c-118">Select to archive blanket sales orders automatically each time they are deleted.</span></span>|
|<span data-ttu-id="6300c-119">**Arch. commandes et retours**</span><span class="sxs-lookup"><span data-stu-id="6300c-119">**Arch. Orders and Ret. Orders**</span></span>|<span data-ttu-id="6300c-120">Permet d'archiver automatiquement les documents de vente chaque fois qu'ils sont supprimés.</span><span class="sxs-lookup"><span data-stu-id="6300c-120">Select to automatically archive sales orders each time they are deleted.</span></span>|

## <a name="to-archive-a-sales-order"></a><span data-ttu-id="6300c-121">Pour archiver un document de vente</span><span class="sxs-lookup"><span data-stu-id="6300c-121">To archive a sales order</span></span>
<span data-ttu-id="6300c-122">La procédure suivante décrit comment archiver un document de vente.</span><span class="sxs-lookup"><span data-stu-id="6300c-122">The following procedure describes how to archive a sales order.</span></span> <span data-ttu-id="6300c-123">La procédure est identique pour les commandes, les commandes ouvertes, les retours et les devis.</span><span class="sxs-lookup"><span data-stu-id="6300c-123">The steps are similar for all orders, blanket orders, return orders, and quotes.</span></span>

1.  <span data-ttu-id="6300c-124">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6300c-124">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="6300c-125">Ouvrez un document de vente que vous souhaitez archiver.</span><span class="sxs-lookup"><span data-stu-id="6300c-125">Open a sales order that you want to archive.</span></span>  
3.  <span data-ttu-id="6300c-126">Sélectionnez l'action **Archiver document**.</span><span class="sxs-lookup"><span data-stu-id="6300c-126">Choose the **Archive Document** action.</span></span>

<span data-ttu-id="6300c-127">Le document de vente est archivé.</span><span class="sxs-lookup"><span data-stu-id="6300c-127">The sales order is archived.</span></span> <span data-ttu-id="6300c-128">Vous pouvez l'afficher dans la fenêtre **Documents de vente archivés**.</span><span class="sxs-lookup"><span data-stu-id="6300c-128">You can view it in the **Archived Sales orders** window.</span></span> <span data-ttu-id="6300c-129">À partir d'ici, vous pouvez également l'utiliser pour recréer le document de vente d'origine.</span><span class="sxs-lookup"><span data-stu-id="6300c-129">From here, you can also use it to recreate the sales order that it was archived from.</span></span>

## <a name="to-recreate-a-sales-order-from-the-archive"></a><span data-ttu-id="6300c-130">Pour recréer un document de vente à partir de l'archive</span><span class="sxs-lookup"><span data-stu-id="6300c-130">To recreate a sales order from the archive</span></span>
<span data-ttu-id="6300c-131">La procédure suivante décrit comment recréer un document de vente.</span><span class="sxs-lookup"><span data-stu-id="6300c-131">The following procedure describes how to recreate a sales order.</span></span> <span data-ttu-id="6300c-132">La procédure est identique pour les commandes, les commandes ouvertes, les retours et les devis.</span><span class="sxs-lookup"><span data-stu-id="6300c-132">The steps are similar for all orders, blanket orders, return orders, and quotes.</span></span>

1.  <span data-ttu-id="6300c-133">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Documents de vente archivés**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="6300c-133">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Archived Sales Orders**, and then choose the related link.</span></span>
2.  <span data-ttu-id="6300c-134">Sélectionnez le document de vente archivé que vous voulez recréer, puis sélectionnez l'action **Restaurer**.</span><span class="sxs-lookup"><span data-stu-id="6300c-134">Select the archived sales order that you want to recreate, and then choose the **Restore** action.</span></span>  

<span data-ttu-id="6300c-135">Le document de vente est créé et ajouté à la fenêtre **Documents de vente**.</span><span class="sxs-lookup"><span data-stu-id="6300c-135">The sales order is created and added to the **Sales Orders** window.</span></span>

## <a name="to-delete-archived-sales-orders"></a><span data-ttu-id="6300c-136">Pour supprimer des documents de vente archivés</span><span class="sxs-lookup"><span data-stu-id="6300c-136">To delete archived sales orders</span></span>
<span data-ttu-id="6300c-137">La procédure suivante décrit comment supprimer des documents de vente archivés.</span><span class="sxs-lookup"><span data-stu-id="6300c-137">The following procedure describes how to delete archived sales orders.</span></span> <span data-ttu-id="6300c-138">La procédure est identique pour les autres documents achat et vente archivés.</span><span class="sxs-lookup"><span data-stu-id="6300c-138">The steps are similar for other archived sales and purchase documents.</span></span>

1.  <span data-ttu-id="6300c-139">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Supprimer les versions de documents de vente archivées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="6300c-139">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Delete Archived Sales Order Versions**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="6300c-140">Dans la fenêtre **Supprimer les versions de documents de vente archivées**, sélectionnez les filtres appropriés.</span><span class="sxs-lookup"><span data-stu-id="6300c-140">In the **Delete Archived Sales Order Versions** window, select the appropriate filters.</span></span>  
3.  <span data-ttu-id="6300c-141">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="6300c-141">Choose the **OK** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="6300c-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6300c-142">See Also</span></span>
[<span data-ttu-id="6300c-143">Suivre des lignes document</span><span class="sxs-lookup"><span data-stu-id="6300c-143">Track Document Lines</span></span>](across-how-to-track-document-lines.md)  
[<span data-ttu-id="6300c-144">Ventes</span><span class="sxs-lookup"><span data-stu-id="6300c-144">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="6300c-145">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="6300c-145">General Business Functionality</span></span>](ui-across-business-areas.md)  
<span data-ttu-id="6300c-146">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="6300c-146">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
