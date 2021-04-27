---
title: Affecter des écritures dans des devises différentes| Microsoft Docs
description: Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise.
services: project-madeira
documentationcenter: ''
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: f0c56a6cc8ed428a8984cb40f43887bd297fca2a
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5784875"
---
# <a name="enable-application-of-ledger-entries-in-different-currencies"></a><span data-ttu-id="0d8cf-103">Activer l'affectation des écritures en devises différentes</span><span class="sxs-lookup"><span data-stu-id="0d8cf-103">Enable Application of Ledger Entries in Different Currencies</span></span>
<span data-ttu-id="0d8cf-104">Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-104">If you purchase from a vendor in one currency and submit payment in another currency, you can apply the payment to the purchase.</span></span>

<span data-ttu-id="0d8cf-105">De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-105">Likewise, if you sell to a customer in one currency and receive payment in another currency, you can apply the payment to the sales invoice.</span></span>

<span data-ttu-id="0d8cf-106">La procédure suivante indique comment configurer cela pour les écritures fournisseur sur la page **Configuration achats et à payer**.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-106">The following procedure describes how to set this up for vendor ledger entries on the **Purchases & Payables Setup** page.</span></span> <span data-ttu-id="0d8cf-107">La configuration est semblable à celle des écritures client sur la page **Configuration des ventes et des comptes à recevoir**.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-107">The setup is similar for customer ledger entries on the **Sales & Receivables Setup** page.</span></span>

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a><span data-ttu-id="0d8cf-108">Pour activer l'affectation des écritures fournisseur en devises différentes</span><span class="sxs-lookup"><span data-stu-id="0d8cf-108">To enable application of vendor ledger entries in different currencies</span></span>
1. <span data-ttu-id="0d8cf-109">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration achats et à payer**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-109">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="0d8cf-110">Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-110">In the **Appln. between Currencies** field, select one of the following options.</span></span>

| <span data-ttu-id="0d8cf-111">Option</span><span class="sxs-lookup"><span data-stu-id="0d8cf-111">Option</span></span> | <span data-ttu-id="0d8cf-112">Description</span><span class="sxs-lookup"><span data-stu-id="0d8cf-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="0d8cf-113">Aucun</span><span class="sxs-lookup"><span data-stu-id="0d8cf-113">None</span></span> |<span data-ttu-id="0d8cf-114">L'affectation entre devises n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-114">Application between currencies is not allowed.</span></span> |
| <span data-ttu-id="0d8cf-115">Devises U.M.E.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-115">EMU</span></span> |<span data-ttu-id="0d8cf-116">L'affectation entre devises UME est autorisée.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-116">Application between EMU currencies is allowed.</span></span> |
| <span data-ttu-id="0d8cf-117">Tout</span><span class="sxs-lookup"><span data-stu-id="0d8cf-117">All</span></span> |<span data-ttu-id="0d8cf-118">L'affectation entre toutes les devises est autorisée.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-118">Application between all currencies is allowed.</span></span> |

## <a name="to-set-up-gl-accounts-for-currency-application-rounding-differences"></a><span data-ttu-id="0d8cf-119">Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement des devises</span><span class="sxs-lookup"><span data-stu-id="0d8cf-119">To set up G/L accounts for currency application rounding differences</span></span>  
<span data-ttu-id="0d8cf-120">Si vous affectez des écritures dans différentes devises, vous devez configurer les comptes du grand livre sur lesquels reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-120">If you apply entries in different currencies, you must set up the general ledger accounts to which you want to post rounding differences.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="0d8cf-121">Vous devez configurer les comptes généraux avant de terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-121">You must set up the general ledger accounts before you complete the task.</span></span> <span data-ttu-id="0d8cf-122">Pour plus d'informations, voir [Description du grand livre et du plan comptable](finance-general-ledger.md).</span><span class="sxs-lookup"><span data-stu-id="0d8cf-122">For more information, see [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).</span></span>

1. <span data-ttu-id="0d8cf-123">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Groupes de report client**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-123">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Posting Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="0d8cf-124">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-124">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  
3. <span data-ttu-id="0d8cf-125">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report fournisseur**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-125">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Groups**, and then choose the related link.</span></span>  
4. <span data-ttu-id="0d8cf-126">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="0d8cf-126">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0d8cf-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d8cf-127">See Also</span></span>
[<span data-ttu-id="0d8cf-128">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="0d8cf-128">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="0d8cf-129">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="0d8cf-129">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="0d8cf-130">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="0d8cf-130">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]