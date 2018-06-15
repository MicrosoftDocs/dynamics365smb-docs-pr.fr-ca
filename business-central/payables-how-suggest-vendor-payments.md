---
title: Utilisez le traitement en lot Proposer paiements fournisseur| Microsoft Docs
description: "Vous pouvez spécifier les paramètres du paiement fournisseur pour obtenir des suggestions ou des propositions pour les paiements arrivant à échéance ou donnant lieu à un escompte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 05/15/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: 02f063daf5afeea85832c8a322183b3db120d8d2
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---
# <a name="suggest-vendor-payments"></a><span data-ttu-id="c004a-103">Proposer paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="c004a-103">Suggest Vendor Payments</span></span>
<span data-ttu-id="c004a-104">Dans la fenêtre **Feuille paiement**, vous pouvez utiliser le traitement par lots **Proposer paiements fournisseur** pour proposer des lignes paiement.</span><span class="sxs-lookup"><span data-stu-id="c004a-104">In the **Payment Journal** window, you can use the **Suggest Vendor Payments** batch job to suggest payment lines.</span></span> <span data-ttu-id="c004a-105">Des lignes pour les paiements échus à courte échéance ou les paiements pour lesquels un escompte de paiement est disponible, sont proposées en fonction de vos paramètres.</span><span class="sxs-lookup"><span data-stu-id="c004a-105">Lines for payments that are due soon or payments where a payment discount is available are suggested based on your settings.</span></span>

<span data-ttu-id="c004a-106">Pour bénéficier pleinement des suggestions de paiement, vous devez d'abord attribuer une priorité à vos fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c004a-106">To benefit fully from payment suggestions, you must first prioritize your vendors.</span></span> <span data-ttu-id="c004a-107">Pour plus d'informations, voir [Octroyer une priorité à des fournisseurs](purchasing-how-prioritize-vendors.md).</span><span class="sxs-lookup"><span data-stu-id="c004a-107">For more information, see [Prioritize Vendors](purchasing-how-prioritize-vendors.md).</span></span>  

> [!NOTE]  
> <span data-ttu-id="c004a-108">Le traitement en lot n'inclut pas les écritures fournisseur marquées **En attente**.</span><span class="sxs-lookup"><span data-stu-id="c004a-108">Vendor ledger entries that are **On Hold** are not included in the batch job.</span></span>  

> [!IMPORTANT]  
>   <span data-ttu-id="c004a-109">Si vous souhaitez profiter d'escomptes et que vous avez saisi un montant disponible, ce montant est d'abord utilisé pour :</span><span class="sxs-lookup"><span data-stu-id="c004a-109">If you want to take advantage of payment discounts, and have entered an available amount, the amount will be used for:</span></span>  

* <span data-ttu-id="c004a-110">Les écritures fournisseur échues et prioritaires, par ordre de priorité.</span><span class="sxs-lookup"><span data-stu-id="c004a-110">Prioritized overdue vendor entries first in order of priority.</span></span>  
* <span data-ttu-id="c004a-111">Les écritures fournisseur échues et non prioritaires.</span><span class="sxs-lookup"><span data-stu-id="c004a-111">Overdue vendor entries that are not prioritized.</span></span>  
* <span data-ttu-id="c004a-112">Les écritures fournisseur ouvertes donnant lieu à un escompte, dans l'ordre des numéros des fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="c004a-112">Open vendor entries that qualify for payment discounts, arranged by vendor number.</span></span>  

## <a name="to-use-the-suggest-vendor-payments-function"></a><span data-ttu-id="c004a-113">Pour utiliser la fonction Proposer paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="c004a-113">To use the Suggest Vendor Payments function</span></span>
1. <span data-ttu-id="c004a-114">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles paiement**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="c004a-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Payment Journals**, and then choose the related link.</span></span>  
2. <span data-ttu-id="c004a-115">Ouvrez la feuille appropriée, puis sélectionnez l'action **Proposer paiements fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="c004a-115">Open the relevant journal, and then choose the **Suggest Vendor Payments** action.</span></span>  
3. <span data-ttu-id="c004a-116">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="c004a-116">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
4. <span data-ttu-id="c004a-117">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="c004a-117">Choose the **OK** button.</span></span>  

## <a name="to-insert-the-due-date-as-posting-date-on-payment-journal-lines"></a><span data-ttu-id="c004a-118">Pour insérer la date d'échéance comme date de report sur les lignes journal paiement</span><span class="sxs-lookup"><span data-stu-id="c004a-118">To insert the due date as posting date on payment journal lines</span></span>
<span data-ttu-id="c004a-119">Lorsque vous utilisez le traitement par lots **Proposer paiements fournisseur** pour créer des lignes de paiement pour vos fournisseurs, vous pouvez remplir deux champs spéciaux pour vous assurer que les lignes générées utilisent la date d'échéance pour calculer la date comptabilisation.</span><span class="sxs-lookup"><span data-stu-id="c004a-119">When you use the **Suggest Vendor Payments** batch job to create payment lines for your vendors, you can fill two special fields to make sure that the generated lines use the due date to calculate the posting date.</span></span> <span data-ttu-id="c004a-120">Ces champs sont **Calculer la date comptabilisation à partir de la date d'échéance doc. lettrage** et **Décalage date d'échéance doc. lettrage**.</span><span class="sxs-lookup"><span data-stu-id="c004a-120">These fields are **Calculate Posting Date from Applies-to-Doc Due Date** and **Applies-to-Doc Due Date Offset**.</span></span>  

> [!IMPORTANT]  
>   <span data-ttu-id="c004a-121">Vous ne pouvez pas utiliser le champ **Calculate Posting Date from Applies-to-Doc Due Date** avec le champ **Find Payment Discounts** ou le champ **Summarize per Vendor**.</span><span class="sxs-lookup"><span data-stu-id="c004a-121">You cannot use the **Calculate Posting Date from Applies-to-Doc Due Date** field together with the **Find Payment Discounts** field or the **Summarize per Vendor** field.</span></span> <span data-ttu-id="c004a-122">Si la date de report est basée sur la date d'échéance, des escomptes de paiement risquent de ne pas être calculés correctement, parce que la date de report peut se trouver après la date d'escompte de paiement.</span><span class="sxs-lookup"><span data-stu-id="c004a-122">If the posting date is based on the due date, some payment discounts may not calculate correctly because the posting date is after the payment discount date.</span></span>  

<span data-ttu-id="c004a-123">De plus, si la date de report calculée se trouve dans le passé, la date de report est déplacée à la date de travail, et un message d'attention s'affiche.</span><span class="sxs-lookup"><span data-stu-id="c004a-123">Also, if the calculated posting date is in the past, then the posting date is moved up to the work date, and a warning is displayed.</span></span>  

<span data-ttu-id="c004a-124">Vous pouvez aussi créer manuellement des lignes de paiement à l'aide de la date d'échéance pour calculer la date de report.</span><span class="sxs-lookup"><span data-stu-id="c004a-124">Alternatively, you can manually create payment lines using the due date to calculate the posting date.</span></span> <span data-ttu-id="c004a-125">Une fois que vous avez appliqué les écritures comptables fournisseur, vous pouvez utiliser l'option **Calculer date comptabilisation** pour mettre à jour la date comptabilisation de la ligne feuille à la date d'échéance de la facture achat associée.</span><span class="sxs-lookup"><span data-stu-id="c004a-125">After you apply vendor ledger entries, you can use the **Calculate Posting Date** action to update the posting date on the journal line with the due date of the related purchase invoice.</span></span> <span data-ttu-id="c004a-126">Pour plus d'informations, voir [Affecter les achats manuellement](payables-how-apply-purchase-transactions-manually.md).</span><span class="sxs-lookup"><span data-stu-id="c004a-126">For more information, see [Apply Purchase Transactions Manually](payables-how-apply-purchase-transactions-manually.md).</span></span>  

> [!NOTE]  
>   <span data-ttu-id="c004a-127">Si la facture achat est en retard, la date de report est définie sur la date de travail et la police de la ligne devient rouge.</span><span class="sxs-lookup"><span data-stu-id="c004a-127">If the purchase invoice is overdue, the posting date is set to the work date, and the font on the line becomes red.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c004a-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c004a-128">See Also</span></span>
[<span data-ttu-id="c004a-129">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="c004a-129">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="c004a-130">Effectuer des paiements</span><span class="sxs-lookup"><span data-stu-id="c004a-130">Making Payments</span></span>](payables-make-payments.md)  
[<span data-ttu-id="c004a-131">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="c004a-131">Working with General Journals</span></span>](ui-work-general-journals.md)  
<span data-ttu-id="c004a-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="c004a-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

