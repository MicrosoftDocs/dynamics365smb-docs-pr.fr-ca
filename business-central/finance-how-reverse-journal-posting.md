---
title: Annuler un report en reportant une écriture de contrepassation | Microsoft Docs
description: Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: f2767fca96e1f3689fc4806d878381d02622f261
ms.sourcegitcommit: addfb47612cc2e4e98dfd7e338b6f41cde405d5c
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/16/2019
ms.locfileid: "938601"
---
# <a name="reverse-postings"></a><span data-ttu-id="72ebd-103">Inverser des reports</span><span class="sxs-lookup"><span data-stu-id="72ebd-103">Reverse Postings</span></span>
<span data-ttu-id="72ebd-104">Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine.</span><span class="sxs-lookup"><span data-stu-id="72ebd-104">To undo an erroneous journal posting, you select the entry and create a reverse entry (entries identical to the original entry but with opposite sign in the amount field) with the same document number and posting date as the original entry.</span></span> <span data-ttu-id="72ebd-105">Une fois l'écriture inversée, créez l'écriture correcte.</span><span class="sxs-lookup"><span data-stu-id="72ebd-105">After reversing an entry, you must make the correct entry.</span></span>

<span data-ttu-id="72ebd-106">Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général.</span><span class="sxs-lookup"><span data-stu-id="72ebd-106">You can only reverse entries that are posted from a general journal line.</span></span> <span data-ttu-id="72ebd-107">Une écriture ne peut être inversée qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="72ebd-107">An entry can only be reversed once.</span></span>

<span data-ttu-id="72ebd-108">Pour plus d'informations sur le report d'un journal général, voir [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).</span><span class="sxs-lookup"><span data-stu-id="72ebd-108">For more information about posting from a general journal, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).</span></span>

<span data-ttu-id="72ebd-109">Si vous avez effectué un report de quantité négatif incorrect, comme un bon de commande avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant reçu (mais non facturé), vous pouvez annuler ce report.</span><span class="sxs-lookup"><span data-stu-id="72ebd-109">If you have made an incorrect negative quantity posting, such as a purchase order with the wrong number of items and posted it as received but not invoiced, then you can undo the posting.</span></span>

<span data-ttu-id="72ebd-110">Si vous avez effectué un report de quantité positif incorrect, comme un retour commande achat avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant livré (mais non facturé), vous pouvez annuler ce report.</span><span class="sxs-lookup"><span data-stu-id="72ebd-110">If you have made an incorrect positive quantity posting, such as a purchase return order with the wrong number of items and posted it as shipped but not invoiced, then you can undo the posting.</span></span>   

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a><span data-ttu-id="72ebd-111">Pour inverser le report journal d'une écriture grand livre</span><span class="sxs-lookup"><span data-stu-id="72ebd-111">To reverse the journal posting of a general ledger entry</span></span>
<span data-ttu-id="72ebd-112">Vous pouvez inverser des écritures sur toutes les pages **Écritures**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-112">You can reverse entries from all **Ledger Entries** pages.</span></span> <span data-ttu-id="72ebd-113">La procédure suivante se base sur la page **Écritures**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-113">The following procedure is based on the **General Ledger Entries** page.</span></span>
1. <span data-ttu-id="72ebd-114">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Écritures**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="72ebd-114">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Ledger Entries**, and then choose the related link.</span></span>
2. <span data-ttu-id="72ebd-115">Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-115">Select the entry that you want to reverse, and then choose the **Reverse Transaction** action.</span></span> <span data-ttu-id="72ebd-116">Notez qu'elle doit provenir d'un report journal.</span><span class="sxs-lookup"><span data-stu-id="72ebd-116">Note that is must originate from a journal posting.</span></span>
3. <span data-ttu-id="72ebd-117">Sur la page **Inverser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Inverser**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-117">On the **Reverse Transaction Entries** page, select the relevant entry, and then choose the **Reverse** action.</span></span>
4. <span data-ttu-id="72ebd-118">Choisissez le bouton **Oui** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="72ebd-118">Choose the **Yes** button on the confirmation message.</span></span>

## <a name="to-undo-a-quantity-posting-on-a-posted-purchase-receipt"></a><span data-ttu-id="72ebd-119">Pour annuler un report de quantité sur une réception d'achat reportée</span><span class="sxs-lookup"><span data-stu-id="72ebd-119">To undo a quantity posting on a posted purchase receipt</span></span>  

1.  <span data-ttu-id="72ebd-120">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Réceptions achat reportées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="72ebd-120">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Purchase Receipts**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="72ebd-121">Ouvrez la réception reportée à annuler.</span><span class="sxs-lookup"><span data-stu-id="72ebd-121">Open the posted receipt that you want to undo.</span></span>  
3.  <span data-ttu-id="72ebd-122">Sélectionnez la ligne ou les lignes à annuler.</span><span class="sxs-lookup"><span data-stu-id="72ebd-122">Select the line or lines that you want to undo.</span></span>  
4.  <span data-ttu-id="72ebd-123">Choisissez l'action **Annuler réception**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-123">Choose **Undo Receipt** action.</span></span>

    <span data-ttu-id="72ebd-124">Une ligne de correction est insérée sous la ligne de la réception sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="72ebd-124">A corrective line is inserted under the selected receipt line.</span></span>  

    <span data-ttu-id="72ebd-125">Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est insérée dans la réception entrepôt reportée.</span><span class="sxs-lookup"><span data-stu-id="72ebd-125">If the quantity was received in a warehouse receipt, then a corrective line is inserted in the posted warehouse receipt.</span></span>  

    <span data-ttu-id="72ebd-126">Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.</span><span class="sxs-lookup"><span data-stu-id="72ebd-126">The **Quantity Received** and **Qty. Rcd. Not Invoiced** fields on the related purchase order are set to zero.</span></span>

## <a name="to-undo-and-then-redo-a-quantity-posting-on-a-posted-return-shipment"></a><span data-ttu-id="72ebd-127">Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée</span><span class="sxs-lookup"><span data-stu-id="72ebd-127">To undo and then redo a quantity posting on a posted return shipment</span></span>

1.  <span data-ttu-id="72ebd-128">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Livraisons retour reportées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="72ebd-128">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Return Shipments**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="72ebd-129">Ouvrez la livraison de retour reportée à annuler.</span><span class="sxs-lookup"><span data-stu-id="72ebd-129">Open the posted return shipment that you want to undo.</span></span>
3. <span data-ttu-id="72ebd-130">Sélectionnez la ligne ou les lignes à annuler.</span><span class="sxs-lookup"><span data-stu-id="72ebd-130">Select the line or lines you want to undo.</span></span>  

4.  <span data-ttu-id="72ebd-131">Choisissez l'action **Annuler livraison retour**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-131">Choose the **Undo Return Shipment** action.</span></span>  

    <span data-ttu-id="72ebd-132">Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.</span><span class="sxs-lookup"><span data-stu-id="72ebd-132">A corrective line is inserted in the posted document, and the **Return Qty. Shipped** and **Return Shpd. Not Invd.** fields on the return order are set to zero.</span></span>  

    <span data-ttu-id="72ebd-133">Retournez à présent au retour achat pour un nouveau report.</span><span class="sxs-lookup"><span data-stu-id="72ebd-133">Now go back to the purchase return order to redo the posting.</span></span>  

5.  <span data-ttu-id="72ebd-134">Sur la page **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour**</span><span class="sxs-lookup"><span data-stu-id="72ebd-134">On the **Posted Return Shipment** page, take a note of the number in the **Return Order No.**</span></span> <span data-ttu-id="72ebd-135">.</span><span class="sxs-lookup"><span data-stu-id="72ebd-135">field.</span></span>  
6.  <span data-ttu-id="72ebd-136">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Retours achat**, et sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="72ebd-136">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Return Orders**, and then select the related link.</span></span>  
7.  <span data-ttu-id="72ebd-137">Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-137">Open the return order in question, and then choose the **Reopen** action.</span></span>  
8.  <span data-ttu-id="72ebd-138">Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.</span><span class="sxs-lookup"><span data-stu-id="72ebd-138">Correct the entry in the **Quantity** field and post the purchase return order again.</span></span>  

## <a name="to-post-a-negative-entry"></a><span data-ttu-id="72ebd-139">Pour reporter une écriture négative</span><span class="sxs-lookup"><span data-stu-id="72ebd-139">To post a negative entry</span></span>  
<span data-ttu-id="72ebd-140">Vous pouvez utiliser le champ **Correction** pour reporter un débit négatif au lieu d'un crédit, ou pour reporter un crédit négatif au lieu d'un débit sur un compte.</span><span class="sxs-lookup"><span data-stu-id="72ebd-140">You can use the **Correction** field to post a negative debit instead of a credit, or to post a negative credit instead of a debit on an account.</span></span> <span data-ttu-id="72ebd-141">Pour répondre aux exigences légales, ce champ est visible par défaut sur tous les journaux.</span><span class="sxs-lookup"><span data-stu-id="72ebd-141">To meet legal requirements, this field is visible by default in all journals.</span></span> <span data-ttu-id="72ebd-142">Les champs **Montant débit** et **Montant crédit** comprennent l'écriture initiale et l'écriture corrigée.</span><span class="sxs-lookup"><span data-stu-id="72ebd-142">The **Debit Amount** and **Credit Amount** fields include both the original entry, and the corrected entry.</span></span> <span data-ttu-id="72ebd-143">Ces champs n'ont aucune incidence sur le solde du compte.</span><span class="sxs-lookup"><span data-stu-id="72ebd-143">These fields have no effect on the account balance.</span></span>  

1.  <span data-ttu-id="72ebd-144">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="72ebd-144">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link</span></span>  
2.  <span data-ttu-id="72ebd-145">Dans le champ **Nom de la feuille**, sélectionnez le nom de feuille requis.</span><span class="sxs-lookup"><span data-stu-id="72ebd-145">In the **Batch Name** field, select the required batch name.</span></span>  
3.  <span data-ttu-id="72ebd-146">Entrez les informations dans les champs pertinents.</span><span class="sxs-lookup"><span data-stu-id="72ebd-146">Enter information into the relevant fields.</span></span>  
4.  <span data-ttu-id="72ebd-147">Dans la ligne journal que vous souhaitez activer pour les écritures négatives, sélectionnez la case à cocher **Correction**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-147">In the journal line that you want to activate for negative entries, select the **Correction** check box.</span></span>  
5.  <span data-ttu-id="72ebd-148">Pour reporter le journal, sélectionnez l'action **Reporter**, puis le bouton **Oui**.</span><span class="sxs-lookup"><span data-stu-id="72ebd-148">To post the journal, choose the **Post** action, and then choose the **Yes** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="72ebd-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="72ebd-149">See Also</span></span>
[<span data-ttu-id="72ebd-150">Reporter les transactions directement dans le grand livre</span><span class="sxs-lookup"><span data-stu-id="72ebd-150">Post Transactions Directly to the General Ledger</span></span>](finance-how-post-transactions-directly.md)  
[<span data-ttu-id="72ebd-151">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="72ebd-151">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="72ebd-152">Finances</span><span class="sxs-lookup"><span data-stu-id="72ebd-152">Finance</span></span>](finance.md)  
<span data-ttu-id="72ebd-153">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="72ebd-153">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
