---
title: Lier un document de vente à un bon de commande pour une livraison directe | Microsoft Docs
description: Décrit comment créer un document de vente liée à un bon de commande pour permettre la livraison directe du fournisseur au client.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 7a87023445ea10aa19cc0cc4f60d76ce4cf3e365
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "929369"
---
# <a name="make-drop-shipments"></a><span data-ttu-id="1f088-103">Effectuer des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="1f088-103">Make Drop Shipments</span></span>
<span data-ttu-id="1f088-104">Lors d'une livraison directe, un ou plusieurs articles de l'un de vos fournisseurs sont livrés directement chez l'un de vos clients.</span><span class="sxs-lookup"><span data-stu-id="1f088-104">A drop shipment is the shipment of items from one of your vendors directly to one of your customers.</span></span>

<span data-ttu-id="1f088-105">Lorsqu'une commande vente est marquée pour livraison directe, et lorsque vous créez une commande achat spécifiant le client dans le champ **N° donneur d'ordre**</span><span class="sxs-lookup"><span data-stu-id="1f088-105">When a sales order is marked for drop shipment, and you create a purchase order specifying the customer in the **Sell-to Customer No.**</span></span> <span data-ttu-id="1f088-106">, vous pouvez ensuite associer les deux documents et par conséquent informer le fournisseur de procéder directement à la livraison au client.</span><span class="sxs-lookup"><span data-stu-id="1f088-106">field, you can link the two documents and thereby instruct the vendor to ship directly to the customer.</span></span>

## <a name="to-create-a-sales-order-for-drop-shipment"></a><span data-ttu-id="1f088-107">Pour créer un document de vente pour des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="1f088-107">To create a sales order for drop shipment</span></span>
<span data-ttu-id="1f088-108">Pour préparer une livraison directe, vous créez un document de vente pour un article, sauf que vous devez indiquer sur la ligne vente que la vente exige la livraison directe.</span><span class="sxs-lookup"><span data-stu-id="1f088-108">To prepare a drop shipment, you create a sales order for an item as normal, except you must indicate on the sales line that the sale requires drop shipment.</span></span>

1. <span data-ttu-id="1f088-109">Créez un document de vente pour un article.</span><span class="sxs-lookup"><span data-stu-id="1f088-109">Create a sales order for an item.</span></span> <span data-ttu-id="1f088-110">Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).</span><span class="sxs-lookup"><span data-stu-id="1f088-110">For more information, see [Sell Products](sales-how-sell-products.md).</span></span>
2. <span data-ttu-id="1f088-111">Sur la ligne commande vente pour l'article envoyé, cochez la case **Livraison directe**.</span><span class="sxs-lookup"><span data-stu-id="1f088-111">On the sales order line for the drop shipment, select the **Drop Shipment** check box.</span></span> <span data-ttu-id="1f088-112">Utilisez la fonction **Choisir les colonnes** si le champ n'est pas visible.</span><span class="sxs-lookup"><span data-stu-id="1f088-112">Use the **Choose Columns** function if the field is not visible.</span></span> <span data-ttu-id="1f088-113">Pour plus d'informations, voir [Personnalisation de votre espace de travail](ui-personalization-user.md).</span><span class="sxs-lookup"><span data-stu-id="1f088-113">For more information, see [Personalizing Your Workspace](ui-personalization-user.md).</span></span>

## <a name="to-create-the-purchase-order-for-drop-shipment"></a><span data-ttu-id="1f088-114">Pour créer le bon de commande pour livraison directe</span><span class="sxs-lookup"><span data-stu-id="1f088-114">To create the purchase order for drop shipment</span></span>
<span data-ttu-id="1f088-115">Pour préparer une livraison directe pour l'article mis en vente, vous créez un bon de commande, comme à l'accoutumée, sauf que vous devez indiquer sur le bon de commande qu'il doit être envoyé à votre client et non pas à vous-même.</span><span class="sxs-lookup"><span data-stu-id="1f088-115">To prepare a drop shipment for the item to be sold, you create a purchase order as normal, except you must indicate on the purchase order that it must be shipped to your customer, not to yourself.</span></span>

1. <span data-ttu-id="1f088-116">Créez un bon de commande.</span><span class="sxs-lookup"><span data-stu-id="1f088-116">Create a purchase order.</span></span> <span data-ttu-id="1f088-117">Ne remplissez pas les champs sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="1f088-117">Do not fill any fields on the lines.</span></span> <span data-ttu-id="1f088-118">Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).</span><span class="sxs-lookup"><span data-stu-id="1f088-118">For more information, see [Record Purchases](purchasing-how-record-purchases.md).</span></span>
2. <span data-ttu-id="1f088-119">Dans le champ **N° donneur d'ordre**</span><span class="sxs-lookup"><span data-stu-id="1f088-119">In the **Sell-to Customer No.**</span></span> <span data-ttu-id="1f088-120">, sélectionnez le client auquel vous souhaitez vendre l'article en question.</span><span class="sxs-lookup"><span data-stu-id="1f088-120">field, select the customer that you are selling to.</span></span>
3. <span data-ttu-id="1f088-121">Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire commande vente**.</span><span class="sxs-lookup"><span data-stu-id="1f088-121">Choose the **Drop Shipments** action, and then choose the **Get Sales Order** action.</span></span>
4. <span data-ttu-id="1f088-122">Sur la page **Liste des ventes**, sélectionnez le document de vente que vous avez préparée dans la section [Créer un document de vente pour livraison directe](sales-how-drop-shipment.md#to-create-a-sales-order-for-drop-shipment).</span><span class="sxs-lookup"><span data-stu-id="1f088-122">On the **Sales List** page, select the sales order that you prepared in [To create a sales order for drop shipment](sales-how-drop-shipment.md#to-create-a-sales-order-for-drop-shipment).</span></span>
5. <span data-ttu-id="1f088-123">Choisissez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="1f088-123">Choose the **OK** button.</span></span>

<span data-ttu-id="1f088-124">Les informations de ligne du document de vente sont insérées sur la/les ligne(s) bon de commande.</span><span class="sxs-lookup"><span data-stu-id="1f088-124">The line information from the sales order is inserted on the purchase order line(s).</span></span>

<span data-ttu-id="1f088-125">Vous pouvez maintenant informer le fournisseur quant à la livraison des articles à votre client, par exemple en envoyant le bon de commande au format PDF.</span><span class="sxs-lookup"><span data-stu-id="1f088-125">You can now instruct the vendor to ship the items to your customer, for example, by mailing the purchase order as a PDF.</span></span>     

## <a name="to-view-the-linked-purchase-order-from-the-sales-order"></a><span data-ttu-id="1f088-126">Pour afficher le bon de commande associé à partir du document de vente</span><span class="sxs-lookup"><span data-stu-id="1f088-126">To view the linked purchase order from the sales order</span></span>
* <span data-ttu-id="1f088-127">Sélectionnez la ligne commande vente livraison directe, choisissez l'action **Commande**, puis l'action **Livraison directe** et enfin l'action **Commande achat**.</span><span class="sxs-lookup"><span data-stu-id="1f088-127">Select the drop-shipment sales order line, choose the **Order** action, choose the **Drop Shipment** action, and then choose the **Purchase Order** action.</span></span>

## <a name="to-post-a-drop-shipment"></a><span data-ttu-id="1f088-128">Pour reporter une livraison directe</span><span class="sxs-lookup"><span data-stu-id="1f088-128">To post a drop shipment</span></span>
<span data-ttu-id="1f088-129">Lorsque le fournisseur a livré les articles, vous pouvez reporter le document de vente comme envoyé.</span><span class="sxs-lookup"><span data-stu-id="1f088-129">After the vendor ships the items, you can post the sales order as shipped.</span></span> <span data-ttu-id="1f088-130">Vous pouvez également valider la commande achat, mais uniquement avec l'option **Réceptionner** jusqu'à ce que la commande vente ait été facturée.</span><span class="sxs-lookup"><span data-stu-id="1f088-130">You can also post the purchase order, but only with the **Receive** option until the sales order has been invoiced.</span></span>

1. <span data-ttu-id="1f088-131">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1f088-131">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="1f088-132">Ouvrez les documents de vente que vous avez créés dans la section [Pour créer un document de vente pour une livraison directe]().</span><span class="sxs-lookup"><span data-stu-id="1f088-132">Open the sales order that you created in [To create a sales order for drop shipment]().</span></span>
3. <span data-ttu-id="1f088-133">Dans le champ **Qté à livrer**, spécifiez quelle quantité de la commande livrer : la quantité totale ou partielle.</span><span class="sxs-lookup"><span data-stu-id="1f088-133">In the **Qty. to Ship** field, specify how many of the order quantity to ship, the full or a partial order quantity.</span></span>
4. <span data-ttu-id="1f088-134">Sélectionnez l'action **Valider** ou **Valider et envoyer**.</span><span class="sxs-lookup"><span data-stu-id="1f088-134">Choose the **Post** or **Post and Send** action.</span></span>
5. <span data-ttu-id="1f088-135">Sélectionnez l'option **Livrer** pour facturer ultérieurement ou l'option **Livrer et facturer** pour facturer immédiatement.</span><span class="sxs-lookup"><span data-stu-id="1f088-135">Choose either the **Ship** option to invoice later, or the **Ship and Invoice** option to invoice immediately.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f088-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1f088-136">See Also</span></span>
[<span data-ttu-id="1f088-137">Créer des commandes spéciales</span><span class="sxs-lookup"><span data-stu-id="1f088-137">Create Special Orders</span></span>](sales-how-to-create-special-orders.md)  
[<span data-ttu-id="1f088-138">Acheter des articles pour une vente</span><span class="sxs-lookup"><span data-stu-id="1f088-138">Purchase Items for a Sale</span></span>](purchasing-how-purchase-products-sale.md)  
[<span data-ttu-id="1f088-139">Vendre des produits</span><span class="sxs-lookup"><span data-stu-id="1f088-139">Sell Products</span></span>](sales-how-sell-products.md)  
[<span data-ttu-id="1f088-140">Enregistrer des achats</span><span class="sxs-lookup"><span data-stu-id="1f088-140">Record Purchases</span></span>](purchasing-how-record-purchases.md)  
[<span data-ttu-id="1f088-141">Ventes</span><span class="sxs-lookup"><span data-stu-id="1f088-141">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="1f088-142">Stock</span><span class="sxs-lookup"><span data-stu-id="1f088-142">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="1f088-143">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1f088-143">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
