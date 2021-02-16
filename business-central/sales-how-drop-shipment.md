---
title: Lier un document de vente à un bon de commande pour une livraison directe | Microsoft Docs
description: Décrit comment créer un document de vente liée à un bon de commande pour permettre la livraison directe du fournisseur au client.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: c6b84d3622b4261c1f88880ba1257bf00f83e346
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4748453"
---
# <a name="make-drop-shipments"></a><span data-ttu-id="0e2a6-103">Effectuer des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="0e2a6-103">Make Drop Shipments</span></span>

<span data-ttu-id="0e2a6-104">Lors d'une livraison directe, un ou plusieurs articles de l'un de vos fournisseurs sont livrés directement chez l'un de vos clients.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-104">A drop shipment is the shipment of items from one of your vendors directly to one of your customers.</span></span>

<span data-ttu-id="0e2a6-105">Lorsqu'un document de vente est marqué pour livraison directe, et lorsque vous créez un bon de commande précisant le client dans le champ **Destinataire**, **Adresse client**, vous pouvez associer les deux documents pour demander au fournisseur de faire directement la livraison au client.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-105">When a sales order is marked for drop shipment, and you create a purchase order specifying the customer in the **Ship-to** field, **Customer Address**, you can link the two documents to instruct the vendor to ship directly to the customer.</span></span>
<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4mOyM?rel=0]

## <a name="to-create-a-sales-order-for-drop-shipment"></a><span data-ttu-id="0e2a6-106">Pour créer un document de vente pour des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="0e2a6-106">To create a sales order for drop shipment</span></span>

<span data-ttu-id="0e2a6-107">Pour préparer une livraison directe, vous créez un document de vente pour un article et indiquer sur la ligne vente que la vente exige la livraison directe.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-107">To prepare a drop shipment, you create a sales order for an item and indicate on the sales line that the sale requires drop shipment.</span></span>

1. <span data-ttu-id="0e2a6-108">Créez un document de vente pour un article.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-108">Create a sales order for an item.</span></span> <span data-ttu-id="0e2a6-109">Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).</span><span class="sxs-lookup"><span data-stu-id="0e2a6-109">For more information, see [Sell Products](sales-how-sell-products.md).</span></span>
2. <span data-ttu-id="0e2a6-110">Sur la ligne commande vente pour l'article envoyé, cochez la case **Livraison directe**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-110">On the sales order line for the drop shipment, select the **Drop Shipment** check box.</span></span> <span data-ttu-id="0e2a6-111">Utilisez la fonction **Choisir les colonnes** si le champ n'est pas visible.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-111">Use the **Choose Columns** function if the field is not visible.</span></span> <span data-ttu-id="0e2a6-112">Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).</span><span class="sxs-lookup"><span data-stu-id="0e2a6-112">For more information, see [Personalize Your Workspace](ui-personalization-user.md).</span></span>

## <a name="to-create-the-purchase-order-for-drop-shipment"></a><span data-ttu-id="0e2a6-113">Pour créer le bon de commande pour livraison directe</span><span class="sxs-lookup"><span data-stu-id="0e2a6-113">To create the purchase order for drop shipment</span></span>

<span data-ttu-id="0e2a6-114">Pour préparer une livraison directe, vous indiquez sur le bon de commande qu'elle doit être livrée à votre client, et non à vous-même.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-114">To prepare a drop shipment, you indicate on the purchase order that it must be shipped to your customer, not to yourself.</span></span>

1. <span data-ttu-id="0e2a6-115">Créez un bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-115">Create a purchase order.</span></span> <span data-ttu-id="0e2a6-116">Ne remplissez pas les champs sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-116">Do not fill any fields on the lines.</span></span> <span data-ttu-id="0e2a6-117">Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).</span><span class="sxs-lookup"><span data-stu-id="0e2a6-117">For more information, see [Record Purchases](purchasing-how-record-purchases.md).</span></span>
2. <span data-ttu-id="0e2a6-118">Dans le champ **Destinataire**, sélectionnez **Adresse client**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-118">In the **Ship-to** field, select **Customer Address**.</span></span>
3. <span data-ttu-id="0e2a6-119">Dans le champ **Client**, sélectionnez le client auquel vous souhaitez vendre l'article en question.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-119">In the **Customer** field, select the customer that you are selling to.</span></span>
4. <span data-ttu-id="0e2a6-120">Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire document de vente**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-120">Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.</span></span>
5. <span data-ttu-id="0e2a6-121">Sur la page **Liste des ventes**, sélectionnez le document de vente que vous avez préparée dans la section [Créer un document de vente pour livraison directe](sales-how-drop-shipment.md#to-create-a-sales-order-for-drop-shipment).</span><span class="sxs-lookup"><span data-stu-id="0e2a6-121">On the **Sales List** page, select the sales order that you prepared in [To create a sales order for drop shipment](sales-how-drop-shipment.md#to-create-a-sales-order-for-drop-shipment).</span></span>
6. <span data-ttu-id="0e2a6-122">Choisissez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-122">Choose the **OK** button.</span></span>

<span data-ttu-id="0e2a6-123">Les informations de ligne du document de vente sont insérées sur la/les ligne(s) bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-123">The line information from the sales order is inserted on the purchase order line(s).</span></span>

<span data-ttu-id="0e2a6-124">Vous pouvez maintenant informer le fournisseur quant à la livraison des articles à votre client, par exemple en envoyant le bon de commande au format PDF.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-124">You can now instruct the vendor to ship the items to your customer, for example, by mailing the purchase order as a PDF.</span></span>     

## <a name="to-create-multiple-purchase-orders-for-drop-shipments"></a><span data-ttu-id="0e2a6-125">Pour créer plusieurs bons de commande pour des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="0e2a6-125">To create multiple purchase orders for drop shipments</span></span>

<span data-ttu-id="0e2a6-126">Vous pouvez également utiliser la feuille de réquisition pour créer le bon de commande du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-126">You can also use the requisition worksheet to create the purchase order for the vendor.</span></span> <span data-ttu-id="0e2a6-127">L'avantage d'utiliser la feuille de réquisition est qu'elle permet de créer des bons de commande pour toutes les livraisons directes en attente, il n'est donc pas nécessaire de créer chacun d'eux individuellement.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-127">The advantage of using the requisition worksheet is that it can create purchase orders for all outstanding drop shipments, so you don't have to create each one individually.</span></span>

1. <span data-ttu-id="0e2a6-128">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Demandes achat**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-128">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Requistion Worksheets**, and then choose the related link.</span></span>
2. <span data-ttu-id="0e2a6-129">Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire document de vente**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-129">Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.</span></span>
3. <span data-ttu-id="0e2a6-130">Choisissez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-130">Choose the **OK** button.</span></span>
4. <span data-ttu-id="0e2a6-131">Passez en revue les lignes bon de commande et, dans le champ **N° fournisseur**, sélectionnez le fournisseur qui fournit les marchandises requises.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-131">Review the purchase order lines, and in the **Vendor No.** field, select vendor that supplies required goods.</span></span> 
5. <span data-ttu-id="0e2a6-132">Choisissez l’action **Traiter messages d’action** pour convertir les lignes révisées en bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-132">Choose the **Carry Out Action Message** action to convert reviewed lines to a purchase order.</span></span>

## <a name="to-view-the-linked-purchase-order-from-the-sales-order"></a><span data-ttu-id="0e2a6-133">Pour afficher le bon de commande associé à partir du document de vente</span><span class="sxs-lookup"><span data-stu-id="0e2a6-133">To view the linked purchase order from the sales order</span></span>

* <span data-ttu-id="0e2a6-134">Sélectionnez la ligne commande vente livraison directe, choisissez l'action **Commande**, puis l'action **Livraison directe** et enfin l'action **Commande achat**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-134">Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.</span></span>

## <a name="to-post-a-drop-shipment"></a><span data-ttu-id="0e2a6-135">Pour reporter une livraison directe</span><span class="sxs-lookup"><span data-stu-id="0e2a6-135">To post a drop shipment</span></span>

<span data-ttu-id="0e2a6-136">Lorsque le fournisseur a livré les articles, vous pouvez reporter le document de vente comme envoyé.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-136">After the vendor ships the items, you can post the sales order as shipped.</span></span> <span data-ttu-id="0e2a6-137">Vous pouvez également valider la commande achat, mais uniquement avec l'option **Réceptionner** jusqu'à ce que la commande vente ait été facturée.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-137">You can also post the purchase order, but only with the **Receive** option until the sales order has been invoiced.</span></span>

1. <span data-ttu-id="0e2a6-138">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-138">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="0e2a6-139">Ouvrez le document de vente que vous avez créé dans [Pour créer un document de vente pour une livraison directe](#to-create-a-sales-order-for-drop-shipment).</span><span class="sxs-lookup"><span data-stu-id="0e2a6-139">Open the sales order that you created in [To create a sales order for drop shipment](#to-create-a-sales-order-for-drop-shipment).</span></span>
3. <span data-ttu-id="0e2a6-140">Dans le champ **Qté à livrer**, spécifiez quelle quantité de la commande livrer : la quantité totale ou partielle.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-140">In the **Qty. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.</span></span>
4. <span data-ttu-id="0e2a6-141">Sélectionnez l'action **Valider** ou **Valider et envoyer**.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-141">Choose the **Post** or **Post and Send** action.</span></span>
5. <span data-ttu-id="0e2a6-142">Sélectionnez l'option **Livrer** pour facturer ultérieurement ou l'option **Livrer et facturer** pour facturer immédiatement.</span><span class="sxs-lookup"><span data-stu-id="0e2a6-142">Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e2a6-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0e2a6-143">See Also</span></span>

[<span data-ttu-id="0e2a6-144">Créer des commandes spéciales</span><span class="sxs-lookup"><span data-stu-id="0e2a6-144">Create Special Orders</span></span>](sales-how-to-create-special-orders.md)  
[<span data-ttu-id="0e2a6-145">Acheter des articles pour une vente</span><span class="sxs-lookup"><span data-stu-id="0e2a6-145">Purchase Items for a Sale</span></span>](purchasing-how-purchase-products-sale.md)  
[<span data-ttu-id="0e2a6-146">Vendre des produits</span><span class="sxs-lookup"><span data-stu-id="0e2a6-146">Sell Products</span></span>](sales-how-sell-products.md)  
[<span data-ttu-id="0e2a6-147">Enregistrer des achats</span><span class="sxs-lookup"><span data-stu-id="0e2a6-147">Record Purchases</span></span>](purchasing-how-record-purchases.md)  
[<span data-ttu-id="0e2a6-148">Vente</span><span class="sxs-lookup"><span data-stu-id="0e2a6-148">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="0e2a6-149">Inventaire</span><span class="sxs-lookup"><span data-stu-id="0e2a6-149">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="0e2a6-150">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="0e2a6-150">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>
