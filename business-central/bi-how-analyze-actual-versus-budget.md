---
title: "Analyse des montants réalisés et des montants budgétés| Microsoft Docs"
description: "Décrit comment analyser les montants réalisés et les montants budgétés."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 01/25/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 900a14c46a6e5c027b3cf8888bb59765902e50cb
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="analyze-actual-amounts-versus-budgeted-amounts"></a><span data-ttu-id="f7540-103">Analyser les montants réalisés et les montants budgétés</span><span class="sxs-lookup"><span data-stu-id="f7540-103">Analyze Actual Amounts Versus Budgeted Amounts</span></span>
<span data-ttu-id="f7540-104">Dans le cadre de la collecte, de l'analyse et du partage des données de votre compagnie, vous voyez les montants réels comparés aux montants budgétés de tous les comptes et pour plusieurs périodes.</span><span class="sxs-lookup"><span data-stu-id="f7540-104">As a part of gathering, analyzing, and sharing your company data, you view actual amounts compared to budgeted amounts for all accounts and for several periods.</span></span>

<span data-ttu-id="f7540-105">Pour analyser les montants budgétés, vous devez d'abord créer des budgets comptabilité.</span><span class="sxs-lookup"><span data-stu-id="f7540-105">To analyze budgeted amounts, you must first create G(L budgets.</span></span> <span data-ttu-id="f7540-106">Pour plus d'informations, voir [Créer des budgets GL](finance-how-create-budgets.md).</span><span class="sxs-lookup"><span data-stu-id="f7540-106">For more information, see [Create G/L Budgets](finance-how-create-budgets.md).</span></span>

## <a name="to-view-a-gl-budget"></a><span data-ttu-id="f7540-107">Pour visualiser un budget GL</span><span class="sxs-lookup"><span data-stu-id="f7540-107">To view a G/L budget</span></span>
<span data-ttu-id="f7540-108">Dans un budget doté d'axes, vous pouvez filtrer les écritures et visualiser des budgets spécifiques.</span><span class="sxs-lookup"><span data-stu-id="f7540-108">In a budget with dimensions, you can filter the entries and see specific budgets.</span></span>

1. <span data-ttu-id="f7540-109">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Budgets**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f7540-109">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Budgets**, and then choose the related link.</span></span>
2. <span data-ttu-id="f7540-110">Dans la fenêtre **Budgets**, ouvrez le budget que vous souhaitez visualiser.</span><span class="sxs-lookup"><span data-stu-id="f7540-110">In the **G/L Budgets** window, open the budget that you want to view.</span></span>  
3. <span data-ttu-id="f7540-111">En haut de la fenêtre, renseignez les champs nécessaires pour définir ce qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="f7540-111">At the top of the window, fill in the fields as necessary to define what is shown.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
>   <span data-ttu-id="f7540-112">Si vous avez sélectionné **Période** dans le champ **Afficher lignes** ou **Afficher colonnes**, puis vous devez renseigner le champ **Afficher par**.</span><span class="sxs-lookup"><span data-stu-id="f7540-112">If you have selected **Period** in either the **Show as Lines** or the **Show as Columns** field, then you must fill in the **View by** field.</span></span> <span data-ttu-id="f7540-113">Si vous n'avez pas sélectionné **Période** dans le champ **Afficher lignes** ou **Afficher colonnes**, entrez la période appropriée dans le champ **Filtre date**.</span><span class="sxs-lookup"><span data-stu-id="f7540-113">If you have not selected **Period** in either the **Show as Lines** or **Show as Columns** field, then enter the appropriate period in **Date Filter** field.</span></span>  

> [!NOTE]  
>   <span data-ttu-id="f7540-114">Seules les écritures budget en comptabilité contenant les codes filtre entrés sur le raccourci **Filtres** sont incluses dans le calcul.</span><span class="sxs-lookup"><span data-stu-id="f7540-114">Only entries from the general ledger budget with the filter codes that you enter on the **Filters** FastTab are included in the calculation.</span></span> <span data-ttu-id="f7540-115">Les écritures budget contenant d'autres codes filtre ou ne contenant aucun code filtre sont exclues.</span><span class="sxs-lookup"><span data-stu-id="f7540-115">Budget entries with other filter codes or without any filter codes are not included.</span></span> <span data-ttu-id="f7540-116">Tant que le filtre est présent dans la fenêtre, le budget n'affiche que les écritures budget contenant ces codes filtre.</span><span class="sxs-lookup"><span data-stu-id="f7540-116">As long as the filter remains on the window, the budget only displays the budget entries with these filter codes.</span></span>  

> [!TIP]  
>   <span data-ttu-id="f7540-117">Si vous souhaitez modifier le budget, vous pouvez modifier les écritures budget.</span><span class="sxs-lookup"><span data-stu-id="f7540-117">If you want to modify the budget, you can modify the budget entries.</span></span> <span data-ttu-id="f7540-118">Choisissez un montant pour afficher les écritures budget sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="f7540-118">Choose an amount to view the underlying general ledger budget entries.</span></span>

## <a name="to-view-actual-and-budgeted-amounts-for-all-accounts"></a><span data-ttu-id="f7540-119">Pour afficher les montants budgétés et réalisés de tous les comptes</span><span class="sxs-lookup"><span data-stu-id="f7540-119">To view actual and budgeted amounts for all accounts</span></span>  
<span data-ttu-id="f7540-120">Vous pouvez afficher des budgets et les comparer aux chiffres réels dans différents modules de [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="f7540-120">You can view general ledger budgets and compare them with actual figures in several areas of [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>

1. <span data-ttu-id="f7540-121">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Plan comptable**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="f7540-121">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f7540-122">Dans la fenêtre **Plan comptable**, choisissez l'action **Réalisé/Budget par compte**.</span><span class="sxs-lookup"><span data-stu-id="f7540-122">In the **Chart of Accounts** window, choose the **G/L Balance/Budget** action.</span></span>
3. <span data-ttu-id="f7540-123">En haut de la fenêtre, renseignez les champs nécessaires pour définir ce qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="f7540-123">At the top of the window, fill in the fields as necessary to define what is shown.</span></span>  
4. <span data-ttu-id="f7540-124">Pour voir le détail d'un montant affiché, sélectionnez ce champ.</span><span class="sxs-lookup"><span data-stu-id="f7540-124">To see a specification that makes up the amount shown, choose the field.</span></span>  

> [!NOTE]  
>   <span data-ttu-id="f7540-125">Les filtres que vous définissez dans l'en-tête de la fenêtre sont affectés aux écritures du grand livre et aux écritures budget.</span><span class="sxs-lookup"><span data-stu-id="f7540-125">The filters you set in the window header will be applied to general ledger entries and also budget entries.</span></span>

<span data-ttu-id="f7540-126">Les colonnes les plus à gauche contiennent le plan comptable.</span><span class="sxs-lookup"><span data-stu-id="f7540-126">The leftmost columns contain the chart of accounts.</span></span> <span data-ttu-id="f7540-127">Sur les cinq colonnes les plus à droite, les quatre premières affichent les montants crédit et débit budgétés, et réalisés pour chaque compte.</span><span class="sxs-lookup"><span data-stu-id="f7540-127">Of the five columns on the rightmost side, the first four columns show actual and budgeted debit and credit amounts for each account.</span></span> <span data-ttu-id="f7540-128">La cinquième colonne indique la relation proportionnelle entre les montants budgétés et réalisés sur le compte du grand livre.</span><span class="sxs-lookup"><span data-stu-id="f7540-128">The fifth column shows the proportional relationship between the actual and the budgeted amounts on the general ledger account.</span></span>  

> [!TIP]  
>   <span data-ttu-id="f7540-129">Le champ **Afficher par** de la fenêtre **Réalisé/Budget par compte** permet de sélectionner la longueur de la période.</span><span class="sxs-lookup"><span data-stu-id="f7540-129">Use the **View by** field in the **G/L Balance/Budget** window to select the period length.</span></span> <span data-ttu-id="f7540-130">Le champ **Afficher en tant que** permet de sélectionner le mode de calcul des montants, à savoir **Solde période** ou **Solde au**.</span><span class="sxs-lookup"><span data-stu-id="f7540-130">Use the **View as** field to select the way the amounts will be calculated, **Net Change** or **Balance at Date**.</span></span> <span data-ttu-id="f7540-131">Choisissez **Période précédente** ou **Période suivante** pour changer de période.</span><span class="sxs-lookup"><span data-stu-id="f7540-131">Choose the **Previous Period** or **Next Period** action to change the period.</span></span>  

## <a name="to-view-actual-and-budgeted-amounts-for-several-periods"></a><span data-ttu-id="f7540-132">Pour afficher les montants budgétés et réalisés de plusieurs périodes</span><span class="sxs-lookup"><span data-stu-id="f7540-132">To view actual and budgeted amounts for several periods</span></span>  
<span data-ttu-id="f7540-133">Au lieu de visualiser les montants budgétés et réalisés de tous les comptes au sein d'une seule période, vous pouvez afficher un certain nombre de périodes pour un seul compte.</span><span class="sxs-lookup"><span data-stu-id="f7540-133">Instead of viewing the actual and budgeted amounts for all accounts within a single period, you can view a number of periods for a single account.</span></span>  

1. <span data-ttu-id="f7540-134">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Plan comptable**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="f7540-134">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f7540-135">Dans la fenêtre **Plan comptable**, sélectionnez le compte général approprié, puis choisissez l'action **Réalisé/Budget compte général**.</span><span class="sxs-lookup"><span data-stu-id="f7540-135">In the **Chart of Accounts** window, select the relevant general ledger account, and then choose the **G/L Account Balance/Budget** action.</span></span>  
3. <span data-ttu-id="f7540-136">En haut de la fenêtre, renseignez les champs nécessaires pour définir ce qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="f7540-136">At the top of the window, fill in the fields as necessary to define what is shown.</span></span>   
4. <span data-ttu-id="f7540-137">Pour voir le détail d'un montant affiché, sélectionnez ce champ.</span><span class="sxs-lookup"><span data-stu-id="f7540-137">To see a specification of an amount shown, choose the field.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f7540-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f7540-138">See Also</span></span>
[<span data-ttu-id="f7540-139">Veille économique</span><span class="sxs-lookup"><span data-stu-id="f7540-139">Business Intelligence</span></span>](bi.md)  
[<span data-ttu-id="f7540-140">Utilisation des tableaux d'analyse</span><span class="sxs-lookup"><span data-stu-id="f7540-140">Work with Account Schedules</span></span>](bi-how-work-account-schedule.md)  
[<span data-ttu-id="f7540-141">Finance</span><span class="sxs-lookup"><span data-stu-id="f7540-141">Finance</span></span>](finance.md)  
[<span data-ttu-id="f7540-142">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="f7540-142">Setting Up Finance</span></span>](finance-setup-finance.md)  
[<span data-ttu-id="f7540-143">Les écritures comptables et le plan comptable</span><span class="sxs-lookup"><span data-stu-id="f7540-143">The General Ledger and the Chart of Accounts</span></span>](finance-general-ledger.md)  
<span data-ttu-id="f7540-144">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f7540-144">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
