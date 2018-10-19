---
title: "Affecter des écritures dans des devises différentes| Microsoft Docs"
description: "Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 10/01/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: f8216885adb734dde214570c65b5f6036caa37d2
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="enable-application-of-ledger-entries-in-different-currencies"></a><span data-ttu-id="64bdf-103">Activer l'affectation des écritures en devises différentes</span><span class="sxs-lookup"><span data-stu-id="64bdf-103">Enable Application of Ledger Entries in Different Currencies</span></span>
<span data-ttu-id="64bdf-104">Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.</span><span class="sxs-lookup"><span data-stu-id="64bdf-104">If you purchase from a vendor in one currency and submit payment in another currency, you can apply the payment to the purchase.</span></span>

<span data-ttu-id="64bdf-105">De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.</span><span class="sxs-lookup"><span data-stu-id="64bdf-105">Likewise, if you sell to a customer in one currency and receive payment in another currency, you can apply the payment to the sales invoice.</span></span>

<span data-ttu-id="64bdf-106">La procédure suivante indique comment configurer cela pour les écritures comptables fournisseur dans la fenêtre **Paramètres achats**.</span><span class="sxs-lookup"><span data-stu-id="64bdf-106">The following procedure describes how to set this up for vendor ledger entries in the **Purchases & Payables Setup** window.</span></span> <span data-ttu-id="64bdf-107">La configuration est semblable à celle des écritures comptables client dans la fenêtre **Paramètres ventes**.</span><span class="sxs-lookup"><span data-stu-id="64bdf-107">The setup is similar for customer ledger entries in the **Sales & Receivables Setup** window.</span></span>

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a><span data-ttu-id="64bdf-108">Pour activer l'affectation des écritures fournisseur en devises différentes</span><span class="sxs-lookup"><span data-stu-id="64bdf-108">To enable application of vendor ledger entries in different currencies</span></span>
1. <span data-ttu-id="64bdf-109">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration achats et à payer**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="64bdf-109">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchases & Payables Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="64bdf-110">Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="64bdf-110">In the **Appln. between Currencies** field, select one of the following options.</span></span>

| <span data-ttu-id="64bdf-111">Option</span><span class="sxs-lookup"><span data-stu-id="64bdf-111">Option</span></span> | <span data-ttu-id="64bdf-112">Description</span><span class="sxs-lookup"><span data-stu-id="64bdf-112">Description</span></span> |
| --- | --- |
| <span data-ttu-id="64bdf-113">Aucun</span><span class="sxs-lookup"><span data-stu-id="64bdf-113">None</span></span> |<span data-ttu-id="64bdf-114">L'affectation entre devises n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="64bdf-114">Application between currencies is not allowed.</span></span> |
| <span data-ttu-id="64bdf-115">Devises U.M.E.</span><span class="sxs-lookup"><span data-stu-id="64bdf-115">EMU</span></span> |<span data-ttu-id="64bdf-116">L'affectation entre devises UME est autorisée.</span><span class="sxs-lookup"><span data-stu-id="64bdf-116">Application between EMU currencies is allowed.</span></span> |
| <span data-ttu-id="64bdf-117">Tout</span><span class="sxs-lookup"><span data-stu-id="64bdf-117">All</span></span> |<span data-ttu-id="64bdf-118">L'affectation entre toutes les devises est autorisée.</span><span class="sxs-lookup"><span data-stu-id="64bdf-118">Application between all currencies is allowed.</span></span> |

## <a name="to-set-up-gl-accounts-for-currency-application-rounding-differences"></a><span data-ttu-id="64bdf-119">Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement des devises</span><span class="sxs-lookup"><span data-stu-id="64bdf-119">To set up G/L accounts for currency application rounding differences</span></span>  
<span data-ttu-id="64bdf-120">Si vous affectez des écritures dans différentes devises, vous devez configurer les comptes du grand livre sur lesquels reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="64bdf-120">If you apply entries in different currencies, you must set up the general ledger accounts to which you want to post rounding differences.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="64bdf-121">Vous devez configurer les comptes généraux avant de terminer la tâche.</span><span class="sxs-lookup"><span data-stu-id="64bdf-121">You must set up the general ledger accounts before you complete the task.</span></span> <span data-ttu-id="64bdf-122">Pour plus d'informations, voir [Description du grand livre et du plan comptable](finance-general-ledger.md).</span><span class="sxs-lookup"><span data-stu-id="64bdf-122">For more information, see [Understanding the General Ledger and the Chart of Accounts](finance-general-ledger.md).</span></span>

1. <span data-ttu-id="64bdf-123">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report client**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="64bdf-123">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Customer Posting Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="64bdf-124">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="64bdf-124">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  
3. <span data-ttu-id="64bdf-125">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report fournisseur**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="64bdf-125">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Vendor Posting Groups**, and then choose the related link.</span></span>  
4. <span data-ttu-id="64bdf-126">Dans les champs **Cpte arr. affect. dev. débit** et **Cpte arr. affect. dev. crédit**, saisissez les comptes du grand livre correspondants pour reporter les différences d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="64bdf-126">In the **Debit Curr. Appln. Rndg. Acc.** and **Credit Curr. Appln. Rndg. Acc.** fields, enter the relevant general ledger accounts to post rounding differences.</span></span>  

## <a name="see-also"></a><span data-ttu-id="64bdf-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="64bdf-127">See Also</span></span>
[<span data-ttu-id="64bdf-128">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="64bdf-128">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="64bdf-129">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="64bdf-129">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="64bdf-130">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="64bdf-130">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

