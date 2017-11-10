---
title: "Procédure : vendre des articles en inventaire dans des flux assembler pour commande | Microsoft Docs"
description: "Si l'article est configuré pour la fiche d'assemblage pour commande, le processus par défaut de document de vente considère que l'article n'est pas en inventaire et doit être assemblé pour ce document de vente spécifique. Par conséquent, un ordre d'assemblage lié est automatiquement créé lorsque vous ajoutez l'article à une ligne document de vente."
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
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 134bc5c719aaa5d386b17f814a596d67f77b260e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-sell-inventory-items-in-assemble-to-order-flows"></a><span data-ttu-id="dcd1a-104">Procédure : vendre des articles en inventaire dans des flux à assembler pour commande</span><span class="sxs-lookup"><span data-stu-id="dcd1a-104">How to: Sell Inventory Items in Assemble-to-Order Flows</span></span>
<span data-ttu-id="dcd1a-105">Si le champ **Politique d'assemblage** de la fiche article d'un élément d'assemblage indique **Assembler pour commande**, le processus par défaut de document de vente considère que l'article n'est pas en inventaire et doit être assemblé pour ce document de vente spécifique.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-105">If the **Assembly Policy** field on the item card of an assembly item contains **Assemble-to-Order**, then the default sales order process assumes that the item is not in inventory and must be assembled for that specific sales order.</span></span> <span data-ttu-id="dcd1a-106">Par conséquent, un ordre d'assemblage lié est automatiquement créé lorsque vous ajoutez l'article à une ligne document de vente.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-106">Therefore, a linked assembly order is automatically created when you add the item to a sales order line.</span></span> <span data-ttu-id="dcd1a-107">Pour plus d'informations sur le paramétrage des éléments d'assemblage, voir [Procédure : Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).</span><span class="sxs-lookup"><span data-stu-id="dcd1a-107">For more information, see [How to: Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).</span></span> <span data-ttu-id="dcd1a-108">Toutefois, si une partie de la quantité sur commande vente est déjà disponible en stock, alors vous pouvez diminuer la quantité d'ordre d'assemblage en changeant le champ **Quantité à assembler pour commande** de la ligne commande vente.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-108">However, if a part of the sales order quantity is already available in inventory, then you can decrease the assembly order quantity by changing the **Qty. to Assemble to Order** field on the sales order line.</span></span>  

<span data-ttu-id="dcd1a-109">Ce scénario est rare parce que les articles à assembler pour commande sont toujours censés être personnalisés, et il est peu probable qu'ils soient en inventaire dans la configuration qui est demandée par un autre client.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-109">This scenario is rare because assemble-to-order items are expected to always be customized, and the chance that they are in inventory in the configuration that is requested by another customer is low.</span></span> <span data-ttu-id="dcd1a-110">Néanmoins, si une compagnie a des quantités assembler pour commande en inventaire à cause de retours ou d'annulations de commande, ces quantités doivent être prélevées et vendues avant que de nouvelles soient assemblées.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-110">However, if a company does have assemble-to-order quantities in inventory because of returns or order cancellations, then these quantities should be picked and sold before new ones are assembled.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="dcd1a-111">Aucune fonctionnalité n'existe sur les commandes vente qui vous alerte automatiquement ou vous aide à déduire les quantités d'ordre d'assemblage qui sont déjà disponibles.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-111">No functionality exists on sales orders that automatically alerts or helps you deduct assembly order quantities that are already available.</span></span> <span data-ttu-id="dcd1a-112">Au lieu de cela, vous devez contrôler les informations de disponibilité, par exemple dans le récapitulatif **Détails ligne vente**.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-112">Instead, you must monitor availability information, such as in the **Sales Line Details** FactBox.</span></span>  

<span data-ttu-id="dcd1a-113">Une fonctionnalité similaire est disponible lorsque vous vendez des éléments d'assemblage de l'inventaire et qu'une partie ou l'ensemble de la quantité n'est pas disponible et peut être fournie dans un ordre d'assemblage.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-113">Similar functionality is available when you are selling assembly items from inventory and a part or all of the quantity is unavailable and can be supplied by an assembly order.</span></span> <span data-ttu-id="dcd1a-114">Pour plus d’informations, reportez-vous à la section [Procédure : vendre simultanément des articles à assembler pour commande et des articles en inventaire](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).</span><span class="sxs-lookup"><span data-stu-id="dcd1a-114">For more information, see [How to: Sell Assemble-to-Order Items and Inventory Items Together](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="dcd1a-115">Certaines règles s'appliquent au champ **Qté à livrer** sur les lignes document de vente qui contiennent une combinaison de quantités assembler pour commande et de quantités inventaire.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-115">Certain rules apply to the **Qty. to Ship** field on sales order lines that contain a combination of assemble-to-order quantities and inventory quantities.</span></span> <span data-ttu-id="dcd1a-116">Pour plus d'informations, voir la section Scénarios de combinaison dans [Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md).</span><span class="sxs-lookup"><span data-stu-id="dcd1a-116">For more information, see the Combination Scenarios section in [Understanding Assemble to Order and Assemble to Stock](assembly-assemble-to-order-or-assemble-to-stock.md).</span></span>  

<span data-ttu-id="dcd1a-117">Dans cette procédure, vous remplacez les quantités à assembler pour commande par les quantités en inventaire sur une ligne document de vente.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-117">In this procedure, you replace assemble-to-order quantities with inventory quantities on a sales order line.</span></span> <span data-ttu-id="dcd1a-118">Les étapes comprennent la vérification des disponibilités existantes, la détection de la quantité de l'ordre d'assemblage associé, puis la réservation de la quantité en inventaire pour s'assurer qu'elle est prélevée et livrée pour la commande.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-118">The steps include detecting that availability exists, deducting that quantity from the linked assembly order, and then reserving the inventory quantity to make sure that it is picked and shipped for the order.</span></span>  

## <a name="to-sell-inventory-items-in-assemble-to-order-flows"></a><span data-ttu-id="dcd1a-119">Vendre des articles en inventaire dans des flux assembler pour commande</span><span class="sxs-lookup"><span data-stu-id="dcd1a-119">To sell inventory items in assemble-to-order flows</span></span>  
1.  <span data-ttu-id="dcd1a-120">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-120">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="dcd1a-121">Créez un document de vente.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-121">Create a sales order.</span></span> <span data-ttu-id="dcd1a-122">Pour en savoir plus, voir [Procédure : vendre des produits](sales-how-sell-products.md).</span><span class="sxs-lookup"><span data-stu-id="dcd1a-122">For more information, see [How to: Sell Products](sales-how-sell-products.md).</span></span>  
3.  <span data-ttu-id="dcd1a-123">Sur une ligne document de vente pour un article à assembler pour commande, dans le champ **Quantité**, entrez la quantité demandée.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-123">On a sales order line for an assemble-to-order item, in the **Quantity** field, enter the demanded quantity.</span></span>  
4.  <span data-ttu-id="dcd1a-124">Dans le récapitulatif **Détails ligne vente**, déterminez si une partie ou la totalité de la quantité demandée est disponible.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-124">In the **Sales Line Details** FactBox, determine if all or some of the demanded quantity is available.</span></span>  
5.  <span data-ttu-id="dcd1a-125">Dans le champ **Quantité à assembler pour commande**, déduisez la quantité disponible de manière à ce que seule la quantité indisponible soit assemblée à la commande.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-125">In the **Qty. to Assemble to Order** field, deduct the available quantity so that only the unavailable quantity is assembled to the order.</span></span> <span data-ttu-id="dcd1a-126">Le champ **Quantité réservée** est diminué en conséquence pour refléter que la relation ordre pour ordre, ou la réservation, s'applique uniquement à la quantité à assembler.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-126">The **Reserved Quantity** field is decreased accordingly to reflect that the order-to-order link, or reservation, only applies to the quantity to be assembled.</span></span>  
6.  <span data-ttu-id="dcd1a-127">Sur le raccourci **Lignes**, choisissez **Fonctions**, puis choisissez l'action **Réserver**.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-127">On the **Lines** FastTab, choose **Functions**, and then choose the **Reserve** action.</span></span>  
7.  <span data-ttu-id="dcd1a-128">Dans la fenêtre **Réservation**, sélectionnez la ou les lignes d'écriture article qui contiennent les quantités disponibles, sélectionnez **Réserver à partir de la ligne courante**, puis sélectionnez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-128">In the **Reservation** window, select the item ledger entry line or lines that contain the available quantities, choose the **Reserve from Current Line** action, and then choose the **OK** button.</span></span>  

    <span data-ttu-id="dcd1a-129">Dans la fenêtre **Commande vente**, le champ **Quantité réservée** indique maintenant que l'ensemble de la quantité ligne commande est réservé.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-129">In the **Sales Order** window, the **Reserved Quantity** field now shows that the whole order line quantity is reserved.</span></span> <span data-ttu-id="dcd1a-130">Le champ **Quantité à assembler pour commande** indique toujours la sous-quantité qui doit être assemblée.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-130">The **Qty. to Assemble to Order** field still reflects the subquantity that has to be assembled.</span></span>  

8.  <span data-ttu-id="dcd1a-131">Libérez le document de vente pour prélever les articles en inventaire et assembler les articles indisponibles.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-131">Release the sales order for picking of the inventory items and for assembly of the unavailable items.</span></span> <span data-ttu-id="dcd1a-132">Pour plus d'informations, voir [Procédure : assembler des articles](assembly-how-to-assemble-items.md).</span><span class="sxs-lookup"><span data-stu-id="dcd1a-132">For more information, see [How to: Assemble Items](assembly-how-to-assemble-items.md).</span></span>  

> [!CAUTION]  
>  <span data-ttu-id="dcd1a-133">Le champ **Code de zone** du document de vente peut être prérempli en fonction du champ **Code zone livr. ass. pr comm.** ou du champ **Code zone depuis assemblage** de la fiche emplacement.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-133">The **Bin Code** field on the sales order may be prefilled according to the **Assemble-to-Order Shpt. Bin Code** or the **From-Assembly Bin Code** field on the location card.</span></span> <span data-ttu-id="dcd1a-134">Dans ce cas, le champ **Code de zone** de la ligne document de vente peut être incorrect dans cette combinaison de quantités assembler pour commande et assembler pour stock.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-134">In that case, the **Bin Code** field on the sales order line may be incorrect in this combination of assemble-to-order and assemble-to-stock quantities.</span></span> <span data-ttu-id="dcd1a-135">Il est judicieux de consulter le champ **Code emplacement** et de s'assurer que le placement fonctionne pour toutes les quantités.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-135">It is a good idea to look in the **Bin Code** field and ensure that the placement works for all quantities.</span></span> <span data-ttu-id="dcd1a-136">Sinon, entrez les deux quantités différentes sur des lignes document de vente distinctes.</span><span class="sxs-lookup"><span data-stu-id="dcd1a-136">Alternatively, enter the two different quantities on separate sales order lines.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dcd1a-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dcd1a-137">See Also</span></span>  
[<span data-ttu-id="dcd1a-138">Gestion d'assemblage</span><span class="sxs-lookup"><span data-stu-id="dcd1a-138">Assembly Management</span></span>](assembly-assemble-items.md)  
[<span data-ttu-id="dcd1a-139">Procédure : réserver des articles</span><span class="sxs-lookup"><span data-stu-id="dcd1a-139">How to: Reserve Items</span></span>](inventory-how-to-reserve-items.md)  
[<span data-ttu-id="dcd1a-140">Procédure : utiliser les nomenclatures</span><span class="sxs-lookup"><span data-stu-id="dcd1a-140">How to: Work with Bills of Material</span></span>](inventory-how-work-BOMs.md)  
[<span data-ttu-id="dcd1a-141">Stocks</span><span class="sxs-lookup"><span data-stu-id="dcd1a-141">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="dcd1a-142">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="dcd1a-142">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="dcd1a-143">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="dcd1a-143">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
