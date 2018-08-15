---
title: "Corriger ou annuler des factures achat impayées | Microsoft Docs"
description: "Explique comment corriger, rétablir ou annuler une facture achat reportée et créer automatiquement une note de crédit achat."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 08/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: 7d5b59d15304a497dc4f3c35ac1d19dcd491aaed
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="correct-or-cancel-unpaid-purchase-invoices"></a><span data-ttu-id="590b9-103">Corriger ou annuler des factures achat impayées</span><span class="sxs-lookup"><span data-stu-id="590b9-103">Correct or Cancel Unpaid Purchase Invoices</span></span>
<span data-ttu-id="590b9-104">Vous pouvez corriger ou annuler une facture achat reportée.</span><span class="sxs-lookup"><span data-stu-id="590b9-104">You can correct or cancel a posted purchase invoice.</span></span> <span data-ttu-id="590b9-105">Cela est utile si vous souhaitez corriger une erreur de saisie, ou si vous souhaitez modifier l'achat assez tôt dans le processus de commande.</span><span class="sxs-lookup"><span data-stu-id="590b9-105">This is useful if you want to correct a typing mistake, or if you want to change the purchase early in the order process.</span></span>

<span data-ttu-id="590b9-106">Si vous avez déjà payé des produits sur la facture achat reportée, vous ne pouvez pas la corriger ni l'annuler à partir de la facture achat reportée elle-même.</span><span class="sxs-lookup"><span data-stu-id="590b9-106">If you have already paid for products on the posted purchase invoice, you cannot correct or cancel it from the posted purchase invoice itself.</span></span> <span data-ttu-id="590b9-107">Au lieu de cela, vous devez créer manuellement une note de crédit achat pour inverser l'achat, éventuellement géré à l'aide d'un retour achat.</span><span class="sxs-lookup"><span data-stu-id="590b9-107">Instead, you must manually create a purchase credit memo to reverse the purchase, optionally managed with a purchase return order.</span></span> <span data-ttu-id="590b9-108">Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md).</span><span class="sxs-lookup"><span data-stu-id="590b9-108">For more information, see [Process Purchase Returns or Cancellations](purchasing-how-process-purchase-returns-cancellations.md).</span></span>

<span data-ttu-id="590b9-109">Dans la fenêtre **Facture achat enregistrée**, vous pouvez cliquer sur le bouton **Corriger** ou **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="590b9-109">In the **Posted Purchase Invoice** window, you can choose the **Correct** button or the **Cancel** button.</span></span> <span data-ttu-id="590b9-110">Lorsque vous corrigez ou annulez une facture achat reportée, la note de crédit achat de correction est affectée à toutes les écritures du grand livre et de l'inventaire physique créées lors du report de la facture achat initiale.</span><span class="sxs-lookup"><span data-stu-id="590b9-110">When you correct or cancel a posted purchase invoice, the corrective purchase credit memo is applied to all general ledger and inventory ledger entries that were created when the initial purchase invoice was posted.</span></span> <span data-ttu-id="590b9-111">Cette action inverse la facture achat reportée dans vos enregistrements financiers et laisse la note de crédit achat reportée de correction pour votre piste de vérification.</span><span class="sxs-lookup"><span data-stu-id="590b9-111">This reverses the posted purchase invoice in your financial records and leaves the corrective posted purchase credit memo for your audit trail.</span></span> <span data-ttu-id="590b9-112">L'utilisation des boutons **Corriger** et **Annuler** est décrite ci-après.</span><span class="sxs-lookup"><span data-stu-id="590b9-112">In the following the use of **Correct** and **Cancel** is described.</span></span>

## <a name="to-correct-a-posted-purchase-invoice"></a><span data-ttu-id="590b9-113">Pour corriger une facture achat reportée</span><span class="sxs-lookup"><span data-stu-id="590b9-113">To correct a posted purchase invoice</span></span>
1. <span data-ttu-id="590b9-114">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Factures achat enregistrées**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="590b9-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Purchase Invoices**, and then choose the related link.</span></span>  
2. <span data-ttu-id="590b9-115">Sélectionnez la facture achat reportée à corriger.</span><span class="sxs-lookup"><span data-stu-id="590b9-115">Select the posted purchase invoice that you want to correct.</span></span>  

    > [!NOTE]  
    >   <span data-ttu-id="590b9-116">Si la case à cocher **Annulé** est activée, vous ne pouvez pas corriger la facture achat validée car elle l'a déjà été, ou a été annulée.</span><span class="sxs-lookup"><span data-stu-id="590b9-116">If the **Canceled** check box is selected, then you cannot correct the posted purchase invoice because it has already been corrected or canceled.</span></span>
3. <span data-ttu-id="590b9-117">Dans la fenêtre **Facture achat enregistrée** sélectionnez **Corriger**.</span><span class="sxs-lookup"><span data-stu-id="590b9-117">In the **Posted Purchase Invoice** window, choose **Correct**.</span></span>

    <span data-ttu-id="590b9-118">Une nouvelle facture achat avec les mêmes informations et dans laquelle vous pouvez apporter une correction est créée.</span><span class="sxs-lookup"><span data-stu-id="590b9-118">A new purchase invoice with the same information is created where you can make the correction.</span></span> <span data-ttu-id="590b9-119">Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).</span><span class="sxs-lookup"><span data-stu-id="590b9-119">For more information, see [Record Purchases](purchasing-how-record-purchases.md).</span></span> <span data-ttu-id="590b9-120">La valeur du champ **Annulé** de la facture achat validée initiale devient **Oui**.</span><span class="sxs-lookup"><span data-stu-id="590b9-120">The **Canceled** field on the initial posted purchase invoice is changed to **Yes**.</span></span>

    <span data-ttu-id="590b9-121">Une note de crédit achat est automatiquement créée et reportée pour annuler la facture achat reportée initiale.</span><span class="sxs-lookup"><span data-stu-id="590b9-121">A purchase credit memo is automatically created and posted to void the initial posted purchase invoice.</span></span>
4. <span data-ttu-id="590b9-122">Sélectionnez **Afficher un avoir correctif** pour afficher l'avoir achat validé qui annule la facture achat validée initiale.</span><span class="sxs-lookup"><span data-stu-id="590b9-122">Choose **Show Corrective Credit Memo** to view the posted purchase credit memo that voids the initial posted purchase invoice.</span></span>

## <a name="to-cancel-a-posted-purchase-invoice"></a><span data-ttu-id="590b9-123">Pour annuler une facture achat reportée</span><span class="sxs-lookup"><span data-stu-id="590b9-123">To cancel a posted purchase invoice</span></span>
1. <span data-ttu-id="590b9-124">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Factures achat enregistrées**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="590b9-124">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Posted Purchase Invoices**, and then choose the related link.</span></span>  
2. <span data-ttu-id="590b9-125">Sélectionnez la facture achat reportée à annuler.</span><span class="sxs-lookup"><span data-stu-id="590b9-125">Select the posted purchase invoice that you want to cancel.</span></span>

    > [!NOTE]  
    >   <span data-ttu-id="590b9-126">Si la case à cocher **Annulé** est activée, vous ne pouvez pas annuler la facture achat validée car elle l'a déjà été, ou a été corrigée.</span><span class="sxs-lookup"><span data-stu-id="590b9-126">If the **Canceled** check box is selected, then you cannot cancel the posted purchase invoice because it has already been canceled or corrected.</span></span>
3. <span data-ttu-id="590b9-127">Dans la fenêtre **Facture achat enregistrée** sélectionnez **Annuler**.</span><span class="sxs-lookup"><span data-stu-id="590b9-127">In the **Posted Purchase Invoice** window, choose **Cancel**.</span></span>

    <span data-ttu-id="590b9-128">Une note de crédit achat est automatiquement créée et reportée pour annuler la facture achat reportée initiale.</span><span class="sxs-lookup"><span data-stu-id="590b9-128">A purchase credit memo is automatically created and posted to void the initial posted purchase invoice.</span></span> <span data-ttu-id="590b9-129">La valeur du champ **Annulé** de la facture achat validée initiale devient **Oui**.</span><span class="sxs-lookup"><span data-stu-id="590b9-129">The **Canceled** field on the initial posted purchase invoice is changed to **Yes**.</span></span>
4. <span data-ttu-id="590b9-130">Sélectionnez **Afficher un avoir correctif** pour afficher l'avoir achat validé qui annule la facture achat validée initiale.</span><span class="sxs-lookup"><span data-stu-id="590b9-130">Choose **Show Corrective Credit Memo** to view the posted purchase credit memo that voids the initial posted purchase invoice.</span></span>

## <a name="see-also"></a><span data-ttu-id="590b9-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="590b9-131">See Also</span></span>
[<span data-ttu-id="590b9-132">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="590b9-132">Purchasing</span></span>](purchasing-manage-purchasing.md)  
[<span data-ttu-id="590b9-133">Enregistrer des achats</span><span class="sxs-lookup"><span data-stu-id="590b9-133">Record Purchases</span></span>](purchasing-how-record-purchases.md)  
<span data-ttu-id="590b9-134">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="590b9-134">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
