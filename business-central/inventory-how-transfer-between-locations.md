---
title: Transfert d'articles entre des magasins entrepôt| Microsoft Docs
description: Décrit comment déplacer un inventaire d'un emplacement ou d'un entrepôt vers un autre soit avec le journal reclassement soit à l'aide d'ordres de transfert.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.date: 03/01/2019
ms.author: SorenGP
ms.openlocfilehash: bf0687d5b3000dde609c1eca29a0f2534d384ada
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813240"
---
# <a name="transfer-inventory-between-locations"></a><span data-ttu-id="89d77-103">Transfert d'inventaire entre des emplacements</span><span class="sxs-lookup"><span data-stu-id="89d77-103">Transfer Inventory Between Locations</span></span>
<span data-ttu-id="89d77-104">Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="89d77-104">You can transfer inventory items between locations by creating transfer orders.</span></span> <span data-ttu-id="89d77-105">Vous pouvez également utiliser le journal reclassement article.</span><span class="sxs-lookup"><span data-stu-id="89d77-105">Alternatively, you can use the item reclassification journal.</span></span>

<span data-ttu-id="89d77-106">Avec des ordres de transfert, vous pouvez livrer un transfert sortant à partir d'un emplacement et recevoir un transfert entrant à l'autre emplacement.</span><span class="sxs-lookup"><span data-stu-id="89d77-106">With transfer orders, you ship the outbound transfer from one location and receive the inbound transfer at the other location.</span></span> <span data-ttu-id="89d77-107">Cela vous permet de gérer les activités entrepôt impliquées et garantit que les quantités en inventaire sont mises à jour correctement.</span><span class="sxs-lookup"><span data-stu-id="89d77-107">This allows you to manage the involved warehouse activities and provides more certainty that inventory quantities are updated correctly.</span></span>

<span data-ttu-id="89d77-108">Avec la feuille reclassement, il vous suffit de renseigner les champs **Code magasin** et **Nouveau code magasin**.</span><span class="sxs-lookup"><span data-stu-id="89d77-108">With the reclassification journal, you simply fill in the **Location Code** and the **New Location Code** fields.</span></span> <span data-ttu-id="89d77-109">Lorsque vous reportez le journal, les écritures article sont ajustées dans les emplacements en question.</span><span class="sxs-lookup"><span data-stu-id="89d77-109">When you post the journal, the item ledger entries are adjusted at the locations in question.</span></span> <span data-ttu-id="89d77-110">Avec cette méthode, les activités entrepôt ne sont pas traitées.</span><span class="sxs-lookup"><span data-stu-id="89d77-110">With this method, warehouse activities are not managed.</span></span>

> [!NOTE]  
>   <span data-ttu-id="89d77-111">Si vous avez des articles enregistrés dans votre inventaire sans code d'emplacement, par exemple datant d'une période où vous n'aviez qu'un seul entrepôt, vous ne pouvez pas transférer ces articles en utilisant des ordres de transfert.</span><span class="sxs-lookup"><span data-stu-id="89d77-111">If you have items recorded in your inventory without a location code, for example from a time when you only had one warehouse, then you cannot transfer those items using transfer orders.</span></span> <span data-ttu-id="89d77-112">Au lieu de cela, vous devez utiliser le journal reclassement pour reclasser les articles à partir d'un code d'emplacement vide vers un code d'emplacement réel.</span><span class="sxs-lookup"><span data-stu-id="89d77-112">Instead, you must use the reclassification journal to reclassify the items from a blank location code to an actual location code.</span></span>  <span data-ttu-id="89d77-113">Pour plus d'informations, voir l'étape 3 dans [Pour transférer des articles avec le journal reclassement article](inventory-how-transfer-between-locations.md#to-transfer-items-with-the-item-reclassification-journal).</span><span class="sxs-lookup"><span data-stu-id="89d77-113">For more information, see step 3 in [To transfer items with the item reclassification journal](inventory-how-transfer-between-locations.md#to-transfer-items-with-the-item-reclassification-journal).</span></span>

<span data-ttu-id="89d77-114">Pour transférer des articles, des acheminements transfert et des emplacements doivent être créés.</span><span class="sxs-lookup"><span data-stu-id="89d77-114">To transfer items, locations and transfer routes must be set up.</span></span> <span data-ttu-id="89d77-115">Pour plus d'informations, voir [Configurer des emplacements](inventory-how-setup-locations.md).</span><span class="sxs-lookup"><span data-stu-id="89d77-115">For more information, see [Set Up Locations](inventory-how-setup-locations.md).</span></span>

## <a name="to-transfer-items-with-a-transfer-order"></a><span data-ttu-id="89d77-116">Pour transférer des articles avec un ordre de transfert</span><span class="sxs-lookup"><span data-stu-id="89d77-116">To transfer items with a transfer order</span></span>
1. <span data-ttu-id="89d77-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Ordres de transfert**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="89d77-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="89d77-118">Sur la page **Ordre de transfer**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="89d77-118">On the **Transfer Order** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   <span data-ttu-id="89d77-119">Si vous avez renseigné les champs **Code transit**, **Code agent de livraison**, et **Service agent de livraison** sur la page **Spéc. acheminement transfert** lors de la configuration de l'acheminement transfert ; ensuite les champs correspondants sur l'ordre de transfert sont renseignés automatiquement.</span><span class="sxs-lookup"><span data-stu-id="89d77-119">If you have filled in the **In-Transit Code**, **Shipping Agent Code**, and **Shipping Agent Service** fields on the **Trans. Route Spec.** page when you set up the transfer route, then the corresponding fields on the transfer order are filled in automatically.</span></span>

    <span data-ttu-id="89d77-120">Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.</span><span class="sxs-lookup"><span data-stu-id="89d77-120">When you fill in the **Shipping Agent Service** field, the receipt date at the transfer-to location is calculated by adding the shipping time of the shipping agent service to the shipment date.</span></span>

    <span data-ttu-id="89d77-121">En tant que magasinier dans l'emplacement provenance transfert, continuez à livrer les articles.</span><span class="sxs-lookup"><span data-stu-id="89d77-121">As a warehouse worker at the transfer-from location, proceed to ship the items.</span></span>
3. <span data-ttu-id="89d77-122">Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d77-122">Choose the **Post** action, choose the **Ship** option, and then choose the **OK** button.</span></span>

    <span data-ttu-id="89d77-123">Les articles sont à présent en transit entre les magasins spécifiés, selon l'acheminement transfert spécifié.</span><span class="sxs-lookup"><span data-stu-id="89d77-123">The items are now in transit between the specified locations, according to the specifies transfer route.</span></span>

    <span data-ttu-id="89d77-124">En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles.</span><span class="sxs-lookup"><span data-stu-id="89d77-124">As a warehouse worker at the transfer-from location, proceed to receive the items.</span></span>
4. <span data-ttu-id="89d77-125">Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="89d77-125">Choose the **Post** action, choose the **Receive** option, and then choose the **OK** button.</span></span>

## <a name="to-transfer-items-with-the-item-reclassification-journal"></a><span data-ttu-id="89d77-126">Pour transférer des articles avec le journal reclassement article</span><span class="sxs-lookup"><span data-stu-id="89d77-126">To transfer items with the item reclassification journal</span></span>
1. <span data-ttu-id="89d77-127">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux reclassement article**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="89d77-127">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Reclass. Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="89d77-128">Sur la page **Journal reclassement article**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="89d77-128">On the **Item Reclass. Journal** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="89d77-129">Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.</span><span class="sxs-lookup"><span data-stu-id="89d77-129">In the **Location Code** field, enter the location where the items are currently stored.</span></span>

    > [!NOTE]  
    >   <span data-ttu-id="89d77-130">Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.</span><span class="sxs-lookup"><span data-stu-id="89d77-130">To transfer items that have no location code, leave the **Location Code** field blank.</span></span>
4. <span data-ttu-id="89d77-131">Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.</span><span class="sxs-lookup"><span data-stu-id="89d77-131">In the **New Location Code** field, enter the location that you want to transfer the items to.</span></span>
5. <span data-ttu-id="89d77-132">Sélectionnez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="89d77-132">Choose the **Post** action.</span></span>

## <a name="see-also"></a><span data-ttu-id="89d77-133">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89d77-133">See Also</span></span>
[<span data-ttu-id="89d77-134">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="89d77-134">Manage Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="89d77-135">Configurer des emplacements</span><span class="sxs-lookup"><span data-stu-id="89d77-135">Set Up Locations</span></span>](inventory-how-setup-locations.md)  
<span data-ttu-id="89d77-136">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="89d77-136">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="89d77-137">Modification des fonctionnalités affichées</span><span class="sxs-lookup"><span data-stu-id="89d77-137">Changing Which Features are Displayed</span></span>](ui-experiences.md)  
[<span data-ttu-id="89d77-138">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="89d77-138">General Business Functionality</span></span>](ui-across-business-areas.md)
