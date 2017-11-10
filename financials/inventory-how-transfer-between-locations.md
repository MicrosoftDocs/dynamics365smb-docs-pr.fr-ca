---
title: "Transfert d'articles entre des magasins entrepôt| Microsoft Docs"
description: "Décrit comment déplacer un inventaire d'un emplacement ou d'un entrepôt vers un autre soit avec le journal reclassement soit à l'aide d'ordres de transfert."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.date: 06/02/2017
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 41804dc183f9fa05ec1599db34c2b4f76a790a72
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-transfer-inventory-between-locations"></a><span data-ttu-id="00eff-103">Procédure : transférer inventaire entre des emplacements</span><span class="sxs-lookup"><span data-stu-id="00eff-103">How to: Transfer Inventory Between Locations</span></span>
<span data-ttu-id="00eff-104">Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="00eff-104">You can transfer inventory items between locations by creating transfer orders.</span></span> <span data-ttu-id="00eff-105">Vous pouvez également utiliser le journal reclassement article.</span><span class="sxs-lookup"><span data-stu-id="00eff-105">Alternatively, you can use the item reclassification journal.</span></span>

<span data-ttu-id="00eff-106">Avec des ordres de transfert, vous pouvez livrer un transfert sortant à partir d'un emplacement et recevoir un transfert entrant à l'autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="00eff-106">With transfer orders, you ship the outbound transfer from one location and receive the inbound transfer at the other location.</span></span> <span data-ttu-id="00eff-107">Cela vous permet de gérer les activités entrepôt impliquées et garantit que les quantités en inventaire sont mises à jour correctement.</span><span class="sxs-lookup"><span data-stu-id="00eff-107">This allows you to manage the involved warehouse activities and provides more certainty that inventory quantities are updated correctly.</span></span>

<span data-ttu-id="00eff-108">Avec la feuille reclassement, il vous suffit de renseigner les champs **Code magasin** et **Nouveau code magasin**.</span><span class="sxs-lookup"><span data-stu-id="00eff-108">With the reclassification journal, you simply fill in the **Location Code** and the **New Location Code** fields.</span></span> <span data-ttu-id="00eff-109">Lorsque vous reportez le journal, les écritures article sont ajustées dans les emplacements en question.</span><span class="sxs-lookup"><span data-stu-id="00eff-109">When you post the journal, the item ledger entries are adjusted at the locations in question.</span></span> <span data-ttu-id="00eff-110">Avec cette méthode, les activités entrepôt ne sont pas traitées.</span><span class="sxs-lookup"><span data-stu-id="00eff-110">With this method, warehouse activities are not managed.</span></span>

> [!NOTE]  
>   <span data-ttu-id="00eff-111">Si vous avez des articles enregistrés dans votre inventaire sans code d'emplacement, par exemple datant d'une période où vous n'aviez qu'un seul entrepôt, vous ne pouvez pas transférer ces articles en utilisant des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="00eff-111">If you have items recorded in your inventory without a location code, for example from a time when you only had one warehouse, then you cannot transfer those items using transfer orders.</span></span> <span data-ttu-id="00eff-112">Au lieu de cela, vous devez utiliser le journal reclassement pour reclasser les articles à partir d'un code emplacement vide vers un code d'emplacement réel.</span><span class="sxs-lookup"><span data-stu-id="00eff-112">Instead, you must use the reclassification journal to reclassify the items from a blank location code to an actual location code.</span></span>  <span data-ttu-id="00eff-113">Pour plus d'informations, voir l'étape 3 dans la section « Pour transférer des articles avec le journal reclassement article ».</span><span class="sxs-lookup"><span data-stu-id="00eff-113">For more information, see step 3 in the "To transfer items with the item reclassification journal" section.</span></span>

<span data-ttu-id="00eff-114">Pour transférer des articles, des acheminements transfert et magasins doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="00eff-114">To transfer items, locations and transfer routes must be set up.</span></span> <span data-ttu-id="00eff-115">Pour plus d'informations, reportez-vous à [Procédure : Configurer des magasins](inventory-how-setup-locations.md).</span><span class="sxs-lookup"><span data-stu-id="00eff-115">For more information, see [How to: Set Up Locations](inventory-how-setup-locations.md).</span></span>

> [!NOTE]  
>   <span data-ttu-id="00eff-116">Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="00eff-116">This functionality requires that your experience is set to **Suite**.</span></span> <span data-ttu-id="00eff-117">Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="00eff-117">For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).</span></span>

## <a name="to-transfer-items-with-a-transfer-order"></a><span data-ttu-id="00eff-118">Pour transférer des articles avec un ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="00eff-118">To transfer items with a transfer order</span></span>
1. <span data-ttu-id="00eff-119">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Ordres de transfert**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="00eff-119">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="00eff-120">Dans la fenêtre **Ordre de transfer**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="00eff-120">In the **Transfer Order** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
>   <span data-ttu-id="00eff-121">Si vous avez renseigné les champs **Code transit**, **Code agent de livraison**, et **Prestation agent de livraison** dans la fenêtre **Spéc. acheminement transfert** lors de la configuration de l'acheminement transfert, les champs correspondants sur l'ordre de transfert sont renseignés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="00eff-121">If you have filled in the **In-Transit Code**, **Shipping Agent Code**, and **Shipping Agent Service** fields in the **Trans. Route Spec.** window when you set up the transfer route, then the corresponding fields on the transfer order are filled in automatically.</span></span>

    <span data-ttu-id="00eff-122">Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.</span><span class="sxs-lookup"><span data-stu-id="00eff-122">When you fill in the **Shipping Agent Service** field, the receipt date at the transfer-to location is calculated by adding the shipping time of the shipping agent service to the shipment date.</span></span>

    <span data-ttu-id="00eff-123">En tant que magasinier dans l'emplacement provenance transfert, continuez à livrer les articles.</span><span class="sxs-lookup"><span data-stu-id="00eff-123">As a warehouse worker at the transfer-from location, proceed to ship the items.</span></span>
3. <span data-ttu-id="00eff-124">Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="00eff-124">Choose the **Post** action, choose the **Ship** option, and then choose the **OK** button.</span></span>

    <span data-ttu-id="00eff-125">Les articles sont à présent en transit entre les magasins spécifiés, selon l'acheminement transfert spécifié.</span><span class="sxs-lookup"><span data-stu-id="00eff-125">The items are now in transit between the specified locations, according to the specifies transfer route.</span></span>

    <span data-ttu-id="00eff-126">En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles.</span><span class="sxs-lookup"><span data-stu-id="00eff-126">As a warehouse worker at the transfer-from location, proceed to receive the items.</span></span>
4. <span data-ttu-id="00eff-127">Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="00eff-127">Choose the **Post** action, choose the **Receive** option, and then choose the **OK** button.</span></span>

## <a name="to-transfer-items-with-the-item-reclassification-journal"></a><span data-ttu-id="00eff-128">Pour transférer des articles avec le journal reclassement article</span><span class="sxs-lookup"><span data-stu-id="00eff-128">To transfer items with the item reclassification journal</span></span>
1. <span data-ttu-id="00eff-129">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles reclassement article**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="00eff-129">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Item Reclass. Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="00eff-130">Dans la fenêtre **Feuilles reclassement article**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="00eff-130">In the **Item Reclass. Journal** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="00eff-131">Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.</span><span class="sxs-lookup"><span data-stu-id="00eff-131">In the **Location Code** field, enter the location where the items are currently stored.</span></span>

    > [!NOTE]  
>   <span data-ttu-id="00eff-132">Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.</span><span class="sxs-lookup"><span data-stu-id="00eff-132">To transfer items that have no location code, leave the **Location Code** field blank.</span></span>
4. <span data-ttu-id="00eff-133">Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.</span><span class="sxs-lookup"><span data-stu-id="00eff-133">In the **New Location Code** field, enter the location that you want to transfer the items to.</span></span>
5. <span data-ttu-id="00eff-134">Sélectionnez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="00eff-134">Choose the **Post** action.</span></span>

## <a name="see-also"></a><span data-ttu-id="00eff-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="00eff-135">See Also</span></span>
[<span data-ttu-id="00eff-136">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="00eff-136">Manage Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="00eff-137">Procédure : configurer des magasins</span><span class="sxs-lookup"><span data-stu-id="00eff-137">How to: Set Up Locations</span></span>](inventory-how-setup-locations.md)  
  
<span data-ttu-id="00eff-138">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="00eff-138">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
<span data-ttu-id="00eff-139">[Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="00eff-139">[Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md)</span></span>  
[<span data-ttu-id="00eff-140">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="00eff-140">General Business Functionality</span></span>](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]