---
title: "Annuler un report en reportant une écriture de contrepassation | Microsoft Docs"
description: "Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 08/03/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 802171d4f421270cb7e9b4f9dfedec9b9fe5ddc6
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-reverse-postings"></a><span data-ttu-id="a7165-103">Procédure : inverser des reports</span><span class="sxs-lookup"><span data-stu-id="a7165-103">How to: Reverse Postings</span></span>
<span data-ttu-id="a7165-104">Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine.</span><span class="sxs-lookup"><span data-stu-id="a7165-104">To undo an erroneous journal posting, you select the entry and create a reverse entry (entries identical to the original entry but with opposite sign in the amount field) with the same document number and posting date as the original entry.</span></span> <span data-ttu-id="a7165-105">Une fois l'écriture inversée, créez l'écriture correcte.</span><span class="sxs-lookup"><span data-stu-id="a7165-105">After reversing an entry, you must make the correct entry.</span></span>

<span data-ttu-id="a7165-106">Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général.</span><span class="sxs-lookup"><span data-stu-id="a7165-106">You can only reverse entries that are posted from a general journal line.</span></span> <span data-ttu-id="a7165-107">Une écriture ne peut être inversée qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="a7165-107">An entry can only be reversed once.</span></span>

<span data-ttu-id="a7165-108">Pour plus d'informations sur la validation d'une feuille comptabilité, voir [Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md).</span><span class="sxs-lookup"><span data-stu-id="a7165-108">For more information about posting from a general journal, see [How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).</span></span>

<span data-ttu-id="a7165-109">Si vous avez effectué un report de quantité négatif incorrect, comme un bon de commande avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant reçu (mais non facturé), vous pouvez annuler ce report.</span><span class="sxs-lookup"><span data-stu-id="a7165-109">If you have made an incorrect negative quantity posting, such as a purchase order with the wrong number of items and posted it as received but not invoiced, then you can undo the posting.</span></span>

<span data-ttu-id="a7165-110">Si vous avez effectué un report de quantité positif incorrect, comme un retour commande achat avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant livré (mais non facturé), vous pouvez annuler ce report.</span><span class="sxs-lookup"><span data-stu-id="a7165-110">If you have made an incorrect positive quantity posting, such as a purchase return order with the wrong number of items and posted it as shipped but not invoiced, then you can undo the posting.</span></span>   

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a><span data-ttu-id="a7165-111">Pour inverser le report journal d'une écriture grand livre</span><span class="sxs-lookup"><span data-stu-id="a7165-111">To reverse the journal posting of a general ledger entry</span></span>
<span data-ttu-id="a7165-112">Vous pouvez inverser des écritures dans toutes les fenêtres **Écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="a7165-112">You can reverse entries from all **Ledger Entries** windows.</span></span> <span data-ttu-id="a7165-113">La procédure suivante se base sur la fenêtre **Écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="a7165-113">The following procedure is based on the **General Ledger Entries** window.</span></span>
1. <span data-ttu-id="a7165-114">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ecritures comptables**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="a7165-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Entries**, and then choose the related link.</span></span>
2. <span data-ttu-id="a7165-115">Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="a7165-115">Select the entry that you want to reverse, and then choose the **Reverse Transaction** action.</span></span> <span data-ttu-id="a7165-116">Notez qu'elle doit provenir d'un report journal.</span><span class="sxs-lookup"><span data-stu-id="a7165-116">Note that is must originate from a journal posting.</span></span>
3. <span data-ttu-id="a7165-117">Dans la fenêtre **Contrepasser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Contrepasser**.</span><span class="sxs-lookup"><span data-stu-id="a7165-117">In the **Reverse Transaction Entries** window, select the relevant entry, and then choose the **Reverse** action.</span></span>
4. <span data-ttu-id="a7165-118">Choisissez le bouton **Oui** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="a7165-118">Choose the **Yes** button on the confirmation message.</span></span>

## <a name="to-undo-a-quantity-posting-on-a-posted-purchase-receipt"></a><span data-ttu-id="a7165-119">Pour annuler un report de quantité sur une réception d'achat reportée</span><span class="sxs-lookup"><span data-stu-id="a7165-119">To undo a quantity posting on a posted purchase receipt</span></span>  

1.  <span data-ttu-id="a7165-120">Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Réceptions achat reportées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a7165-120">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Purchase Receipts**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="a7165-121">Ouvrez la réception reportée à annuler.</span><span class="sxs-lookup"><span data-stu-id="a7165-121">Open the posted receipt that you want to undo.</span></span>  
3.  <span data-ttu-id="a7165-122">Sélectionnez la ligne ou les lignes à annuler.</span><span class="sxs-lookup"><span data-stu-id="a7165-122">Select the line or lines that you want to undo.</span></span>  
4.  <span data-ttu-id="a7165-123">Choisissez l'action **Annuler réception**.</span><span class="sxs-lookup"><span data-stu-id="a7165-123">Choose **Undo Receipt** action.</span></span>

    <span data-ttu-id="a7165-124">Une ligne de correction est insérée sous la ligne de la réception sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a7165-124">A corrective line is inserted under the selected receipt line.</span></span>  

    <span data-ttu-id="a7165-125">Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est insérée dans la réception entrepôt reportée.</span><span class="sxs-lookup"><span data-stu-id="a7165-125">If the quantity was received in a warehouse receipt, then a corrective line is inserted in the posted warehouse receipt.</span></span>  

    <span data-ttu-id="a7165-126">Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.</span><span class="sxs-lookup"><span data-stu-id="a7165-126">The **Quantity Received** and **Qty. Rcd. Not Invoiced** fields on the related purchase order are set to zero.</span></span>

## <a name="to-undo-and-then-redo-a-quantity-posting-on-a-posted-return-shipment"></a><span data-ttu-id="a7165-127">Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée</span><span class="sxs-lookup"><span data-stu-id="a7165-127">To undo and then redo a quantity posting on a posted return shipment</span></span>

1.  <span data-ttu-id="a7165-128">Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Livraisons de retour reportées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a7165-128">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Return Shipments**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="a7165-129">Ouvrez la livraison de retour reportée à annuler.</span><span class="sxs-lookup"><span data-stu-id="a7165-129">Open the posted return shipment that you want to undo.</span></span>
3. <span data-ttu-id="a7165-130">Sélectionnez la ligne ou les lignes à annuler.</span><span class="sxs-lookup"><span data-stu-id="a7165-130">Select the line or lines you want to undo.</span></span>  

4.  <span data-ttu-id="a7165-131">Choisissez l'action **Annuler livraison retour**.</span><span class="sxs-lookup"><span data-stu-id="a7165-131">Choose the **Undo Return Shipment** action.</span></span>  

    <span data-ttu-id="a7165-132">Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.</span><span class="sxs-lookup"><span data-stu-id="a7165-132">A corrective line is inserted in the posted document, and the **Return Qty. Shipped** and **Return Shpd. Not Invd.** fields on the return order are set to zero.</span></span>  

    <span data-ttu-id="a7165-133">Retournez à présent au retour achat pour un nouveau report.</span><span class="sxs-lookup"><span data-stu-id="a7165-133">Now go back to the purchase return order to redo the posting.</span></span>  

5.  <span data-ttu-id="a7165-134">Dans la fenêtre **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour**</span><span class="sxs-lookup"><span data-stu-id="a7165-134">In the **Posted Return Shipment** window, take a note of the number in the **Return Order No.**</span></span> <span data-ttu-id="a7165-135">.</span><span class="sxs-lookup"><span data-stu-id="a7165-135">field.</span></span>  
6.  <span data-ttu-id="a7165-136">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Retours achat**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a7165-136">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Return Orders**, and then select the related link.</span></span>  
7.  <span data-ttu-id="a7165-137">Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.</span><span class="sxs-lookup"><span data-stu-id="a7165-137">Open the return order in question, and then choose the **Reopen** action.</span></span>  
8.  <span data-ttu-id="a7165-138">Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.</span><span class="sxs-lookup"><span data-stu-id="a7165-138">Correct the entry in the **Quantity** field and post the purchase return order again.</span></span>  

## <a name="see-also"></a><span data-ttu-id="a7165-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7165-139">See Also</span></span>
[<span data-ttu-id="a7165-140">Procédure : Valider les transactions directement vers la comptabilité</span><span class="sxs-lookup"><span data-stu-id="a7165-140">How to: Post Transactions Directly to the General Ledger</span></span>](finance-how-post-transactions-directly.md)  
[<span data-ttu-id="a7165-141">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="a7165-141">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="a7165-142">Finances</span><span class="sxs-lookup"><span data-stu-id="a7165-142">Finance</span></span>](finance.md)  
<span data-ttu-id="a7165-143">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a7165-143">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
