---
title: "Affecter des écritures dans des devises différentes| Microsoft Docs"
description: "Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 06/02/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 6379aea58ab7943b117e5b19b22f71193290c2cb
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-enable-application-of-ledger-entries-in-different-currencies"></a><span data-ttu-id="96e69-103">Procédure : activer l'affectation des écritures en devises différentes</span><span class="sxs-lookup"><span data-stu-id="96e69-103">How to: Enable Application of Ledger Entries in Different Currencies</span></span>
<span data-ttu-id="96e69-104">Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.</span><span class="sxs-lookup"><span data-stu-id="96e69-104">If you purchase from a vendor in one currency and submit payment in another currency, you can apply the payment to the purchase.</span></span>

<span data-ttu-id="96e69-105">De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.</span><span class="sxs-lookup"><span data-stu-id="96e69-105">Likewise, if you sell to a customer in one currency and receive payment in another currency, you can apply the payment to the sales invoice.</span></span>

<span data-ttu-id="96e69-106">La procédure suivante indique comment configurer cela pour les écritures comptables fournisseur dans la fenêtre **Paramètres achats**.</span><span class="sxs-lookup"><span data-stu-id="96e69-106">The following procedure describes how to set this up for vendor ledger entries in the **Purchases & Payables Setup** window.</span></span> <span data-ttu-id="96e69-107">La configuration est semblable à celle des écritures comptables client dans la fenêtre **Paramètres ventes**.</span><span class="sxs-lookup"><span data-stu-id="96e69-107">The setup is similar for customer ledger entries in the **Sales & Receivables Setup** window.</span></span>

> [!NOTE]  
>   <span data-ttu-id="96e69-108">Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="96e69-108">This functionality requires that your experience is set to **Suite**.</span></span> <span data-ttu-id="96e69-109">Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="96e69-109">For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).</span></span>

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a><span data-ttu-id="96e69-110">Pour activer l'affectation des écritures fournisseur en devises différentes</span><span class="sxs-lookup"><span data-stu-id="96e69-110">To enable application of vendor ledger entries in different currencies</span></span>
1. <span data-ttu-id="96e69-111">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres achats**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="96e69-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="96e69-112">Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="96e69-112">In the **Appln. between Currencies** field, select one of the following options.</span></span>

| <span data-ttu-id="96e69-113">Option</span><span class="sxs-lookup"><span data-stu-id="96e69-113">Option</span></span> | <span data-ttu-id="96e69-114">Description</span><span class="sxs-lookup"><span data-stu-id="96e69-114">Description</span></span> |
| --- | --- |
| <span data-ttu-id="96e69-115">Aucun</span><span class="sxs-lookup"><span data-stu-id="96e69-115">None</span></span> |<span data-ttu-id="96e69-116">L'affectation entre devises n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="96e69-116">Application between currencies is not allowed.</span></span> |
| <span data-ttu-id="96e69-117">Devises U.M.E.</span><span class="sxs-lookup"><span data-stu-id="96e69-117">EMU</span></span> |<span data-ttu-id="96e69-118">L'affectation entre devises UME est autorisée.</span><span class="sxs-lookup"><span data-stu-id="96e69-118">Application between EMU currencies is allowed.</span></span> |
| <span data-ttu-id="96e69-119">Tout</span><span class="sxs-lookup"><span data-stu-id="96e69-119">All</span></span> |<span data-ttu-id="96e69-120">L'affectation entre toutes les devises est autorisée.</span><span class="sxs-lookup"><span data-stu-id="96e69-120">Application between all currencies is allowed.</span></span> |

## <a name="to-set-up-gl-accounts-for-currency-application-rounding-differences"></a><span data-ttu-id="96e69-121">Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement des devises</span><span class="sxs-lookup"><span data-stu-id="96e69-121">To set up G/L accounts for currency application rounding differences</span></span>  
<span data-ttu-id="96e69-122">Si vous affectez des écritures dans différentes devises, vous devez configurer les comptes du grand livre sur lesquels reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="96e69-122">If you apply entries in different currencies, you must set up the general ledger accounts to which you want to post rounding differences.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="96e69-123">Vous devez configurer les comptes généraux avant de terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="96e69-123">You must set up the general ledger accounts before you complete the task.</span></span> <span data-ttu-id="96e69-124">Pour plus d'informations, voir [Description du grand livre et du plan comptable](finance-general-ledger.md).</span><span class="sxs-lookup"><span data-stu-id="96e69-124">For more information, see [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).</span></span> 
  
1. <span data-ttu-id="96e69-125">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes de report du client**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="96e69-125">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customer Posting Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="96e69-126">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="96e69-126">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  
3. <span data-ttu-id="96e69-127">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes de report du fournisseur**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="96e69-127">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendor Posting Groups**, and then choose the related link.</span></span>  
4. <span data-ttu-id="96e69-128">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="96e69-128">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  

## <a name="see-also"></a><span data-ttu-id="96e69-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="96e69-129">See Also</span></span>
[<span data-ttu-id="96e69-130">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="96e69-130">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="96e69-131">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="96e69-131">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="96e69-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="96e69-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

