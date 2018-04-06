---
title: Configurer l'arrondissement facture | Microsoft Docs
description: "Vous pouvez arrondir les montants des factures lors de la création de celles-ci. De plus, les réglementations ou la douane locale peuvent exiger des factures arrondies d'une certaine manière, par exemple, divisibles par 0,05."
services: project-madeira
documentationcenter: 
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/15/2017
ms.author: bholtorf
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: ceebeeac325c00d6aef25d8ca51fcfee1ab4e1d5
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-invoice-rounding"></a><span data-ttu-id="8759a-104">Configuration de la fonction arrondissement facture</span><span class="sxs-lookup"><span data-stu-id="8759a-104">Set Up Invoice Rounding</span></span>
<span data-ttu-id="8759a-105">Si vous devez arrondir des montants de factures lorsque vous créez des factures, vous pouvez utiliser la fonction d'arrondissement automatique.</span><span class="sxs-lookup"><span data-stu-id="8759a-105">If you need to round invoice amounts when you create invoices, you can use the automatic rounding function.</span></span> <span data-ttu-id="8759a-106">Lorsqu'une facture est arrondie, une ligne supplémentaire contenant le montant de l'arrondissement est ajoutée et reportée avec les autres lignes facture.</span><span class="sxs-lookup"><span data-stu-id="8759a-106">When an invoice is rounded, an extra line is added with the rounding amount and posted with the other invoice lines.</span></span>

> [!NOTE]  
>  <span data-ttu-id="8759a-107">Les réglementations ou la douane locale peuvent exiger des factures arrondies d'une certaine manière, par exemple, divisibles par 0,05.</span><span class="sxs-lookup"><span data-stu-id="8759a-107">Local regulations or local custom may require the invoice to be rounded in a specific way, for example, to an amount divisible by 0.05.</span></span>  
  
<span data-ttu-id="8759a-108">Pour utiliser l'arrondissement facture automatique, vous devez :</span><span class="sxs-lookup"><span data-stu-id="8759a-108">To use automatic invoice rounding, you must:</span></span>  
  
* <span data-ttu-id="8759a-109">Spécifier les comptes du grand livre dans lesquels les différences d'arrondissement seront reportées ;</span><span class="sxs-lookup"><span data-stu-id="8759a-109">Specify the general ledger accounts to which rounding differences will be posted.</span></span>  
* <span data-ttu-id="8759a-110">configurer les règles d'arrondissement des factures dans les devises locales et étrangère ;</span><span class="sxs-lookup"><span data-stu-id="8759a-110">Set up rules for rounding invoices in local currency and in foreign currency.</span></span>  
* <span data-ttu-id="8759a-111">activer la fonction.</span><span class="sxs-lookup"><span data-stu-id="8759a-111">Activate the function.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8759a-112">Outre les fonctions d'arrondissement facture, vous pouvez arrondir les montants des factures à l'aide des fonctions arrondissement montant unité de mesure et arrondissement montant.</span><span class="sxs-lookup"><span data-stu-id="8759a-112">In addition to the invoice rounding features, you can round amounts on invoices by the unit-amount rounding feature and the amount rounding feature.</span></span>  
 
## <a name="set-up-general-ledger-accounts-for-invoice-rounding-differences"></a><span data-ttu-id="8759a-113">Configurer des comptes GL afin d'autoriser les différences d'arrondissement dans les factures</span><span class="sxs-lookup"><span data-stu-id="8759a-113">Set up general ledger accounts for invoice rounding differences</span></span>
<span data-ttu-id="8759a-114">Pour utiliser la fonction d'arrondissement automatique de facture, vous devez configurer les comptes du grand livre dans lesquels des différences d'arrondissement seront reportées.</span><span class="sxs-lookup"><span data-stu-id="8759a-114">To use the automatic invoice rounding function, you must set up the general ledger account or accounts where rounding differences will be posted.</span></span> <span data-ttu-id="8759a-115">Pour cela, vous devez au préalable configurer des groupes comptabilisation produit TVA.</span><span class="sxs-lookup"><span data-stu-id="8759a-115">Before you can do this, you must set up VAT product posting groups.</span></span> <span data-ttu-id="8759a-116">Pour plus d'informations, reportez-vous à [Configuration TVA](finance-setup-vat.md).</span><span class="sxs-lookup"><span data-stu-id="8759a-116">For more information, see [Set up VAT](finance-setup-vat.md).</span></span>  
  
### <a name="to-set-up-general-ledger-accounts-for-invoice-rounding-differences"></a><span data-ttu-id="8759a-117">Pour configurer des comptes du grand livre afin d'autoriser les différences d'arrondissement dans les factures</span><span class="sxs-lookup"><span data-stu-id="8759a-117">To set up general ledger accounts for invoice rounding differences</span></span>  
1. <span data-ttu-id="8759a-118">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Plan comptable**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="8759a-118">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>  
2. <span data-ttu-id="8759a-119">Sur la page **Plan comptable**, configurez le compte et nommez-le, par exemple **Arrondissement facture**.</span><span class="sxs-lookup"><span data-stu-id="8759a-119">On the **Chart of Accounts** page, set up the account and name it **Invoice Rounding** or something similar.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="8759a-120"> utilise le nom de ce compte comme texte pour les factures arrondies.</span><span class="sxs-lookup"><span data-stu-id="8759a-120"> will use the account name as text for invoices that are rounded.</span></span>  
3. <span data-ttu-id="8759a-121">Selon que vous utilisez la TVA ou la taxe de vente, dans les champs **Groupe de report produit Taxe** ou **Groupe de report produit TVA**, choisissez un groupe de report pour les montants arrondis.</span><span class="sxs-lookup"><span data-stu-id="8759a-121">Depending on whether you use VAT or sales tax, in the **Tax Prod. Posting Group** or **VAT Prod. Posting Group** fields, choose a posting group for rounded amounts.</span></span> <span data-ttu-id="8759a-122">Vous pouvez aussi configurer un nouveau code groupe à utiliser pour les arrondissements facture.</span><span class="sxs-lookup"><span data-stu-id="8759a-122">You may want to set up a new group code to use for invoice rounding.</span></span>
4. <span data-ttu-id="8759a-123">Laissez les champs **Type de report général** et **Groupes de report marché fiscal** ou **Groupe de report marché TVA** vides.</span><span class="sxs-lookup"><span data-stu-id="8759a-123">Leave the **Gen. Posting Type**, and either the **Tax Bus. Posting Group** or **VAT Bus. Posting Group** fields blank.</span></span> <!-- Why do we say to leave these blank, when there are a lot of other fields we also leave blank but don't mention? -->  
  
<span data-ttu-id="8759a-124">À présent, vous pouvez affecter le compte arrondissement facture aux groupes de report sur la page **Groupes de report du fournisseur**.</span><span class="sxs-lookup"><span data-stu-id="8759a-124">Now you can assign the invoice rounding account to posting groups on the **Vendor Posting Groups** page.</span></span>  <!-- Why only the vendor posting groups? -->

## <a name="set-up-rounding-for-foreign-and-local-currencies"></a><span data-ttu-id="8759a-125">Configuration de règles d'arrondissement pour les devises étrangères et locales</span><span class="sxs-lookup"><span data-stu-id="8759a-125">Set up rounding for foreign and local currencies</span></span>
<span data-ttu-id="8759a-126">Avant d'utiliser la fonction d'arrondissement automatique, vous devez configurer les règles d'arrondissement pour les devises étrangères et locales.</span><span class="sxs-lookup"><span data-stu-id="8759a-126">Before you can use the automatic invoice rounding function, you must set up rounding rules for foreign and local currencies.</span></span>

### <a name="to-set-up-rounding-for-foreign-currencies"></a><span data-ttu-id="8759a-127">Pour configurer les règles d'arrondissement pour les devises étrangères</span><span class="sxs-lookup"><span data-stu-id="8759a-127">To set up rounding for foreign currencies</span></span>  
1. <span data-ttu-id="8759a-128">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Devises**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="8759a-128">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Currencies**, and then choose the related link.</span></span>  
2. <span data-ttu-id="8759a-129">Sur la page **Devises**, choisissez la devise étrangère pour ouvrir la **Fiche devise**, puis renseignez les champs **Précision arrondissement montant**, **Précis. arrondissement montant unité de mesure**, **Précision arrondissement facture** et **Type arrondissement facture**.</span><span class="sxs-lookup"><span data-stu-id="8759a-129">On the **Currencies** page, choose the foreign currency to open the **Currency Card**, and then fill in the **Amount Rounding Precision**, **Unit-Amount Rounding Precision**, **Invoice Rounding Precision** and **Invoice Rounding Type** fields.</span></span>
  
### <a name="to-set-up-rounding-for-your-local-currency"></a><span data-ttu-id="8759a-130">Pour configurer les règles d'arrondissement pour les devises locales</span><span class="sxs-lookup"><span data-stu-id="8759a-130">To set up rounding for your local currency</span></span>
1. <span data-ttu-id="8759a-131">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres comptabilité**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="8759a-131">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="8759a-132">Sur la page **Configuration du grand livre**, sous le raccourci **Général**, renseignez les champs **Précis. arrondissement fact.** et **Type arrondissement facture**.</span><span class="sxs-lookup"><span data-stu-id="8759a-132">On the **General Ledger Setup** page, on the **General** FastTab, fill in the **Inv. Rounding Precision** and **Inv. Rounding Type** fields.</span></span>  

## <a name="activate-the-invoice-rounding-function"></a><span data-ttu-id="8759a-133">Activer la fonction d'arrondissement de factures</span><span class="sxs-lookup"><span data-stu-id="8759a-133">Activate the invoice rounding function</span></span>  
<span data-ttu-id="8759a-134">Vous devez activer la fonction d'arrondissement facture pour que les factures vente et achat soient automatiquement arrondies.</span><span class="sxs-lookup"><span data-stu-id="8759a-134">To ensure that sales and purchase invoices are rounded automatically, you must activate the invoice rounding function.</span></span> <span data-ttu-id="8759a-135">Activez séparément la fonction d'arrondissement facture pour les factures vente et les factures achat.</span><span class="sxs-lookup"><span data-stu-id="8759a-135">You activate invoice rounding separately for sales and purchase invoices.</span></span>

1. <span data-ttu-id="8759a-136">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Paramètres ventes** ou **Paramètres achats**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="8759a-136">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales & Receivables Setup** or **Purchases & Payables Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="8759a-137">Sur le raccourci **Général**, sélectionnez la case **Arrondissement facture**.</span><span class="sxs-lookup"><span data-stu-id="8759a-137">On the **General** FastTab, choose the **Invoice Rounding** check box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8759a-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8759a-138">See Also</span></span>  
[<span data-ttu-id="8759a-139">Facturer des ventes</span><span class="sxs-lookup"><span data-stu-id="8759a-139">Invoice Sales</span></span>](sales-how-invoice-sales.md)  
[<span data-ttu-id="8759a-140">Enregistrer des achats</span><span class="sxs-lookup"><span data-stu-id="8759a-140">Record Purchases</span></span>](purchasing-how-record-purchases.md)
