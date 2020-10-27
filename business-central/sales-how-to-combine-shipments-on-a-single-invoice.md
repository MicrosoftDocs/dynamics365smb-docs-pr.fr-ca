---
title: 'Procédure : regrouper des livraisons sur une seule facture | Microsoft Docs'
description: Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 19b6cb69d33d76d4263ad75a666eba14deaeeae8
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3925957"
---
# <a name="combine-shipments-on-a-single-invoice"></a><span data-ttu-id="1c9fb-103">Regroupement de livraisons sur une seule facture</span><span class="sxs-lookup"><span data-stu-id="1c9fb-103">Combine Shipments on a Single Invoice</span></span>
<span data-ttu-id="1c9fb-104">Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-104">If you want to invoice more than one shipment at a time, you can use the combined shipments feature.</span></span>  

<span data-ttu-id="1c9fb-105">Avant de pouvoir regrouper des livraisons, plusieurs livraisons vente pour le même client doivent être reportées dans la même devise.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-105">Before you can create a combined shipment, more than one sales shipment for the same customer in the same currency must be posted.</span></span> <span data-ttu-id="1c9fb-106">Autrement dit, vous devez avoir créé au moins deux documents de vente et les avoir reportés comme étant livrés, mais pas facturés.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-106">In other words, you must have create two or more sales orders and post them as shipped, but not invoiced.</span></span> 

## <a name="to-manually-combine-shipments-on-a-single-invoice"></a><span data-ttu-id="1c9fb-107">Regrouper manuellement les expéditions sur une seule facture</span><span class="sxs-lookup"><span data-stu-id="1c9fb-107">To manually combine shipments on a single invoice</span></span>  
1. <span data-ttu-id="1c9fb-108">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Factures vente** , puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-108">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Invoices** , and then choose the related link.</span></span>  
2. <span data-ttu-id="1c9fb-109">Sélectionnez l'action **Nouveau** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-109">Choose the **New** action.</span></span> <span data-ttu-id="1c9fb-110">Pour plus d'informations, reportez-vous à [Facturer des ventes](sales-how-invoice-sales.md).</span><span class="sxs-lookup"><span data-stu-id="1c9fb-110">For more information, see [Invoice Sales](sales-how-invoice-sales.md).</span></span>
3. <span data-ttu-id="1c9fb-111">Dans le champ **N° donneur d'ordre**</span><span class="sxs-lookup"><span data-stu-id="1c9fb-111">In the **Sell-to Customer No.**</span></span> <span data-ttu-id="1c9fb-112">entrez le client facturé pour les articles livrés.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-112">field, enter the customer who will receive the invoice for the shipped items.</span></span>  
4. <span data-ttu-id="1c9fb-113">Dans le raccourci **Lignes** , sélectionnez l'action **Extraire lignes livraison** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-113">On the **Lines** FastTab, choose the **Get Shipment Lines** action.</span></span>  
5. <span data-ttu-id="1c9fb-114">Sélectionnez la ligne livraison que vous voulez inclure dans la facture :</span><span class="sxs-lookup"><span data-stu-id="1c9fb-114">Select the shipment line that you want to include in the invoice:</span></span>  

    - <span data-ttu-id="1c9fb-115">Pour insérer toutes les lignes, sélectionnez-les toutes et sélectionnez le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-115">To insert all lines, select all lines and choose the **OK** button.</span></span>  
    - <span data-ttu-id="1c9fb-116">Pour insérer des lignes spécifiques, sélectionnez-les et sélectionnez le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-116">To insert specific lines, select the lines and choose the **OK** button.</span></span> <span data-ttu-id="1c9fb-117">Vous pouvez utiliser la touche Ctrl pour sélectionner plusieurs lignes qui ne sont pas séquentielles.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-117">You can use the Ctrl key to select multiple nonsequential lines.</span></span>  

    <span data-ttu-id="1c9fb-118">Si une ligne livraison incorrecte a été sélectionnée ou si vous voulez recommencer, supprimez simplement les lignes de la facture, puis exécutez de nouveau la fonction **Extraire lignes livraison** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-118">If an incorrect shipment line was selected or you want to start over, you can simply delete the lines on the invoice and re-run the **Get Shipment Lines** function.</span></span>  
7. <span data-ttu-id="1c9fb-119">Pour reporter la facture, sélectionnez l'action **Reporter** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-119">To post the invoice, choose the **Post** action.</span></span>  

## <a name="to-automatically-combine-shipments-on-a-single-invoice"></a><span data-ttu-id="1c9fb-120">Regrouper automatiquement les expéditions sur une seule facture</span><span class="sxs-lookup"><span data-stu-id="1c9fb-120">To automatically combine shipments on a single invoice</span></span>  
[!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="1c9fb-121">ne sélectionne que les documents de vente où **Regrouper les B.L.** est coché.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-121">will select only sales orders where **Combine Shipments** is chosen.</span></span> 

1. <span data-ttu-id="1c9fb-122">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Regrouper les livraisons** , puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-122">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Combine Shipments** , and then choose the related link.</span></span> <span data-ttu-id="1c9fb-123">La page de demande de traitement en lot s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-123">The batch job request page opens.</span></span>  
2. <span data-ttu-id="1c9fb-124">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-124">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="1c9fb-125">Cochez la case **Reporter factures** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-125">Choose the **Post Invoices** check box.</span></span>  
4. <span data-ttu-id="1c9fb-126">Choisissez le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-126">Choose the **OK** button.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="1c9fb-127">Vous devez valider manuellement les avoirs si la case à cocher **Valider avoirs** n'a pas été activée pour le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-127">You will need to manually post the invoices if the **Post Invoices** check box was not selected on the batch job.</span></span>  

## <a name="to-remove-open-sales-orders-after-combined-shipment-posting"></a><span data-ttu-id="1c9fb-128">Pour supprimer des documents de vente ouverts après le report des livraisons regroupées</span><span class="sxs-lookup"><span data-stu-id="1c9fb-128">To remove open sales orders after combined shipment posting</span></span> 
<span data-ttu-id="1c9fb-129">Lorsque des livraisons sont regroupées sur une facture et reportées, une facture vente reportées est créée pour les lignes facturées.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-129">When shipments are combined on an invoice and posted, a posted sales invoice is created for the invoiced lines.</span></span> <span data-ttu-id="1c9fb-130">Le champ **Quantité facturée** de la commande permanente ventes ou du document de vente d'origine est mis à jour sur la base de la quantité facturée.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-130">The **Quantity Invoiced** field on the originating blanket sales order or sales order is updated based on the invoiced quantity.</span></span>  

<span data-ttu-id="1c9fb-131">Lorsque vous facturez des livraisons de cette manière, les commandes à partir desquelles les livraisons ont été reportées continuent à exister, même si elles ont été entièrement reportées et facturées.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-131">When you invoice shipments in this way, the orders from which the shipments were posted still exist, even if they have been fully shipped and invoiced.</span></span>   

1. <span data-ttu-id="1c9fb-132">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Supprimer les documents de vente facturés** , puis sélectionnez le lien.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-132">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Delete Invoiced Sales Orders** , and then select the link.</span></span>  
2. <span data-ttu-id="1c9fb-133">Dans le champ de filtre **N°** ,</span><span class="sxs-lookup"><span data-stu-id="1c9fb-133">Specify in the **No.**</span></span> <span data-ttu-id="1c9fb-134">les commandes vente à supprimer.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-134">filter field which sales orders to delete.</span></span>  
3. <span data-ttu-id="1c9fb-135">Cliquez sur le bouton **OK** .</span><span class="sxs-lookup"><span data-stu-id="1c9fb-135">Choose the **OK** button.</span></span>  

<span data-ttu-id="1c9fb-136">Il est également possible de supprimer chacune des commandes vente manuellement.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-136">Alternatively, delete individual sales orders manually.</span></span>  

<span data-ttu-id="1c9fb-137">Répétez les étapes 1 à 3 pour tous les autres documents affectés, comme des commandes permanentes ventes.</span><span class="sxs-lookup"><span data-stu-id="1c9fb-137">Repeat steps 1 through 3 for any other affected documents, such as blanket sales orders.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c9fb-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c9fb-138">See Also</span></span>  
[<span data-ttu-id="1c9fb-139">Vente</span><span class="sxs-lookup"><span data-stu-id="1c9fb-139">Sales</span></span>](sales-manage-sales.md)  
<span data-ttu-id="1c9fb-140">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1c9fb-140">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
