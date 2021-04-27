---
title: Cession ou annulation d'immobilisations| Microsoft Docs
description: Vous devez reporter une valeur de cession lorsque vous mettez au rebut, vendez ou annulez une immobilisation.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: scrap
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 041f228a0ea2e34fb9986ebb45e98c1300f02f8d
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5774065"
---
# <a name="dispose-of-or-retire-fixed-assets"></a><span data-ttu-id="45781-103">Céder ou annuler des immobilisations</span><span class="sxs-lookup"><span data-stu-id="45781-103">Dispose of or Retire Fixed Assets</span></span>

<span data-ttu-id="45781-104">Lorsque vous commercialisez ou cédez une immobilisation, la valeur de cession doit être reportée pour calculer et enregistrer le gain ou la perte.</span><span class="sxs-lookup"><span data-stu-id="45781-104">When you sell or otherwise dispose of a fixed asset, the disposal value must be posted to calculate and record the gain or loss.</span></span> <span data-ttu-id="45781-105">Une écriture cession doit être la dernière écriture reportée pour une immobilisation.</span><span class="sxs-lookup"><span data-stu-id="45781-105">A disposal entry must be the last entry posted for a fixed asset.</span></span> <span data-ttu-id="45781-106">Pour les immobilisations partiellement cédées, vous pouvez reporter plusieurs écritures cession.</span><span class="sxs-lookup"><span data-stu-id="45781-106">For partially disposed fixed assets, you can post more than one disposal entry.</span></span> <span data-ttu-id="45781-107">Le total de tous les montants de cession reportés doit être un montant crédit.</span><span class="sxs-lookup"><span data-stu-id="45781-107">The total of all posted disposal amounts must be a credit amount.</span></span>  

> [!NOTE]  
> <span data-ttu-id="45781-108">Si vous négociez une immobilisation en échange d'une autre, vous devez enregistrer à la fois la vente de l'ancienne immobilisation (cession) et l'achat de la nouvelle (acquisition).</span><span class="sxs-lookup"><span data-stu-id="45781-108">If you trade-in a fixed asset for another one, you must record both the sale of the old asset (disposal) and the purchase of the new one (acquisition).</span></span> <span data-ttu-id="45781-109">Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).</span><span class="sxs-lookup"><span data-stu-id="45781-109">For more information, see [Acquire Fixed Assets](fa-how-acquire.md).</span></span>  

<span data-ttu-id="45781-110">Les étapes suivantes supposent que vous avez déjà configuré les groupes de report appropriés dans la page **Groupes de report immo**.</span><span class="sxs-lookup"><span data-stu-id="45781-110">The following steps assume that you have already set up the relevant posting groups in the **FA Posting Groups** page.</span></span> <span data-ttu-id="45781-111">Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span><span class="sxs-lookup"><span data-stu-id="45781-111">For more information, see [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span></span>  

## <a name="to-post-a-disposal-from-the-fixed-asset-gl-journal"></a><span data-ttu-id="45781-112">Pour reporter une cession à partir du journal GL immobilisation</span><span class="sxs-lookup"><span data-stu-id="45781-112">To post a disposal from the fixed asset G/L journal</span></span>

1. <span data-ttu-id="45781-113">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journaux GL immobilisation**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="45781-113">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Asset G/L Journals**, and then choose the related link.</span></span>  
2. <span data-ttu-id="45781-114">Créez une ligne journal initiale et complétez les champs, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="45781-114">Create an initial journal line and fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. <span data-ttu-id="45781-115">Dans le champ **Type compta. immo**, sélectionnez **Cession**.</span><span class="sxs-lookup"><span data-stu-id="45781-115">In the **FA Posting Type** field, select **Disposal**.</span></span>  
4. <span data-ttu-id="45781-116">Sélectionnez l'action **Insérer contrepartie immo.**.</span><span class="sxs-lookup"><span data-stu-id="45781-116">Choose the **Insert FA Bal. Account** action.</span></span> <span data-ttu-id="45781-117">Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de la cession.</span><span class="sxs-lookup"><span data-stu-id="45781-117">A second journal line is created for the balancing account that is set up for disposal posting.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="45781-118">L'étape 4 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** pour le groupe de report de l'immobilisation, le champ **Compte cession** contient le compte débit du grand livre et le champ **Compte contrepartie cession** contient le compte GL dans lequel vous souhaitez reporter les écritures contrepartie pour appréciation.</span><span class="sxs-lookup"><span data-stu-id="45781-118">Step 4 only works if you have set up the following: On the **FA Posting Group Card** page for the posting group of the fixed asset, the **Disposal Account** field contains the general ledger debit account and the **Disposal Bal. Account** field contains the general ledger account to which you want to post balancing entries for appreciation.</span></span> <span data-ttu-id="45781-119">Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span><span class="sxs-lookup"><span data-stu-id="45781-119">For more information, see [To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span></span>  
5. <span data-ttu-id="45781-120">Sélectionnez l'action **Reporter**.</span><span class="sxs-lookup"><span data-stu-id="45781-120">Choose the **Post** action.</span></span>  

<span data-ttu-id="45781-121">Si vous vendez une immobilisation ou en cédez une partie, vous devez d'abord diviser l'immobilisation avant de pouvoir enregistrer la transaction cession.</span><span class="sxs-lookup"><span data-stu-id="45781-121">If you sell or dispose of part of a fixed asset, you must split up the asset before you can record the disposal transaction.</span></span> <span data-ttu-id="45781-122">Pour en savoir plus, voir [Transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md).</span><span class="sxs-lookup"><span data-stu-id="45781-122">For more information, see [Transfer, Split, or Combine Fixed Assets](fa-how-trans-split-combine.md).</span></span>  

## <a name="to-view-disposal-ledger-entries"></a><span data-ttu-id="45781-123">Pour visualiser des écritures cession</span><span class="sxs-lookup"><span data-stu-id="45781-123">To view disposal ledger entries</span></span>
<span data-ttu-id="45781-124">Lorsque vous vendez ou cédez une immobilisation, la valeur de cession est reportée dans le grand livre où vous pouvez afficher le résultat.</span><span class="sxs-lookup"><span data-stu-id="45781-124">When you sell or dispose of a fixed asset, the disposal value is posted to the general ledger where you can view the result.</span></span>  

1. <span data-ttu-id="45781-125">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Immobilisations**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="45781-125">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Fixed Assets**, and then choose the related link.</span></span>  
2. <span data-ttu-id="45781-126">Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Lois d'amortissement**.</span><span class="sxs-lookup"><span data-stu-id="45781-126">Select the fixed asset that you want to view entries for, and then choose the **Depreciation Books** action.</span></span>  
3. <span data-ttu-id="45781-127">Sélectionnez la loi d'amortissement pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="45781-127">Select the depreciation book that you want to view entries for, and then choose the **Ledger Entries** action.</span></span>  
4. <span data-ttu-id="45781-128">Sélectionnez une ligne avec **Cession** dans le champ **Catégorie report immo.**, puis sélectionnez l’action **Rechercher des écritures**.</span><span class="sxs-lookup"><span data-stu-id="45781-128">Select a line with **Disposal** in the **FA Posting Category** field, and then choose the **Find Entries** action.</span></span>  
5. <span data-ttu-id="45781-129">Sur la page **Rechercher des écritures**, sélectionnez la ligne écriture, puis l’action **Afficher les écritures associées**.</span><span class="sxs-lookup"><span data-stu-id="45781-129">On the **Find Entries** page, select the general ledger entry line, and then choose the **Show Related Entries** action.</span></span>  

<span data-ttu-id="45781-130">La page **Écritures** s'ouvre. Vous pouvez y voir les écritures résultant du report de la cession.</span><span class="sxs-lookup"><span data-stu-id="45781-130">The **General Ledger Entries** page opens where you can see the entries that the disposal posting resulted in.</span></span>  

## <a name="see-also"></a><span data-ttu-id="45781-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45781-131">See Also</span></span>

[<span data-ttu-id="45781-132">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="45781-132">Fixed Assets</span></span>](fa-manage.md)  
[<span data-ttu-id="45781-133">Paramétrage d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="45781-133">Setting Up Fixed Assets</span></span>](fa-setup.md)  
<span data-ttu-id="45781-134">[Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span><span class="sxs-lookup"><span data-stu-id="45781-134">[To set up fixed asset posting groups](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).</span></span>  
[<span data-ttu-id="45781-135">Finance</span><span class="sxs-lookup"><span data-stu-id="45781-135">Finance</span></span>](finance.md)  
[<span data-ttu-id="45781-136">Préparation aux activités commerciales</span><span class="sxs-lookup"><span data-stu-id="45781-136">Getting Ready for Doing Business</span></span>](ui-get-ready-business.md)  
<span data-ttu-id="45781-137">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="45781-137">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="45781-138">Rechercher des écritures</span><span class="sxs-lookup"><span data-stu-id="45781-138">Find Entries</span></span>](ui-find-entries.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]