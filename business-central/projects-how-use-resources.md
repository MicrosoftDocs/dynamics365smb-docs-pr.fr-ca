---
title: Enregistrer et ajuster l'utilisation et les prix des ressources| Microsoft Docs
description: "Décrit la manière dont vous pouvez enregistrer l'utilisation ou la consommation ressource associée à un projet, de garder la trace et de gérer les coûts, les prix, ainsi que les types de travaux."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff
ms.date: 01/25/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: cd7561e97439b6ffcac28937a24b75a11bb31987
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="use-resources-for-jobs"></a><span data-ttu-id="a9dad-103">Utiliser des ressources pour des projets</span><span class="sxs-lookup"><span data-stu-id="a9dad-103">Use Resources for Jobs</span></span>
<span data-ttu-id="a9dad-104">Vous devez enregistrer l'utilisation des ressources dans le journal projet pour suivre les coûts et les prix, ainsi que les types de travaux associés aux projets.</span><span class="sxs-lookup"><span data-stu-id="a9dad-104">You record the usage of resources in the job journal to keep track of costs, prices, and the work types that are linked to jobs.</span></span> <span data-ttu-id="a9dad-105">Pour plus d'informations, voir [Enregistrer l'utilisation pour les projets](projects-how-record-job-usage.md).</span><span class="sxs-lookup"><span data-stu-id="a9dad-105">For more information, see [Record Usage for Jobs](projects-how-record-job-usage.md).</span></span>

<span data-ttu-id="a9dad-106">Vous pouvez aussi reporter l'utilisation d'une ressource dans un journal ressource.</span><span class="sxs-lookup"><span data-stu-id="a9dad-106">You can also post the usage of a resource in a resource journal.</span></span> <span data-ttu-id="a9dad-107">Les écritures reportées dans un journal ressource n'ont aucune incidence sur le grand livre.</span><span class="sxs-lookup"><span data-stu-id="a9dad-107">Entries posted in a resource journal have no effect on the general ledger.</span></span>

## <a name="to-assign-resources-to-jobs"></a><span data-ttu-id="a9dad-108">Pour affecter des ressources aux projets</span><span class="sxs-lookup"><span data-stu-id="a9dad-108">To assign resources to jobs</span></span>
<span data-ttu-id="a9dad-109">Vous pouvez affecter des ressources aux projets en créant des lignes planification projet pour le projet.</span><span class="sxs-lookup"><span data-stu-id="a9dad-109">You assign resources to jobs by creating job planning lines for the job.</span></span> <span data-ttu-id="a9dad-110">Pour plus d'informations, voir [Créer des projets](projects-how-create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="a9dad-110">For more information, see [Create Jobs](projects-how-create-jobs.md).</span></span>

## <a name="to-record-resource-usage-for-a-job"></a><span data-ttu-id="a9dad-111">Pour enregistrer l'utilisation des ressources pour un projet</span><span class="sxs-lookup"><span data-stu-id="a9dad-111">To record resource usage for a job</span></span>
1. <span data-ttu-id="a9dad-112">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles projet**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="a9dad-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Job Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="a9dad-113">Ouvrez le lot journal projet approprié, puis complétez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a9dad-113">Open a relevant job journal batch, and then fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="a9dad-114">Lorsque la feuille est renseignée, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="a9dad-114">When the journal is complete, choose the **Post** action.</span></span>

## <a name="to-adjust-resource-prices"></a><span data-ttu-id="a9dad-115">Pour ajuster le prix des ressources</span><span class="sxs-lookup"><span data-stu-id="a9dad-115">To adjust resource prices</span></span>
<span data-ttu-id="a9dad-116">Si vous souhaitez modifier le coût ou le prix d'un grand nombre de ressources, vous pouvez utiliser un traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="a9dad-116">If you want to change costs or prices for a large number of resources, you can use a batch job.</span></span>  

1. <span data-ttu-id="a9dad-117">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ajuster coûts/prix ressource**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="a9dad-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Adjust Resource Costs/Prices**, and then choose the related link.</span></span>
2. <span data-ttu-id="a9dad-118">Renseignez les autres champs selon vos besoins, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9dad-118">Fill in the fields on a line as necessary, and then choose the **OK** button.</span></span>

> [!NOTE]  
>   <span data-ttu-id="a9dad-119">Ce traitement en lot ne crée pas et n'ajuste pas les nouveaux coûts ou prix des ressources.</span><span class="sxs-lookup"><span data-stu-id="a9dad-119">This batch job does not create or adjust alternate costs or prices for resources.</span></span> <span data-ttu-id="a9dad-120">Il modifie uniquement le contenu du champ de la fiche ressource correspondant au champ **Champ à modifier** que vous avez sélectionné dans le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a9dad-120">It only changes the contents of the field on the resource card for the **Adjust Field** field that you selected in the batch job.</span></span> <span data-ttu-id="a9dad-121">L'ajustement s'appliquant immédiatement aux ressources, vérifiez les facteurs d'ajustement avant de lancer le traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="a9dad-121">The adjustment will take effect immediately for resources, so check your adjustment factors before you run the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-existing-alternate-prices"></a><span data-ttu-id="a9dad-122">Pour obtenir des propositions de modification des prix ressource basées sur les prix secondaires existants</span><span class="sxs-lookup"><span data-stu-id="a9dad-122">To get resource price change suggestions based on existing alternate prices</span></span>
<span data-ttu-id="a9dad-123">Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.</span><span class="sxs-lookup"><span data-stu-id="a9dad-123">If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.</span></span>

1. <span data-ttu-id="a9dad-124">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Nouv. prix ressource proposés**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="a9dad-124">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource Price Changes**, and then choose the related link.</span></span>
2. <span data-ttu-id="a9dad-125">Sélectionnez l'action **Prop. modif. prix ress. (prix)**, puis renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a9dad-125">Choose the **Suggest Res. Price Chg. (Price)** action, and then fill in the fields as necessary.</span></span>
3. <span data-ttu-id="a9dad-126">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9dad-126">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="a9dad-127">Lorsque le traitement par lots est terminé, la fenêtre **Nouv. prix ressource proposés** affiche les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a9dad-127">When the batch job is finished, the **Resource Price Changes** window shows the results of the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-standard-prices"></a><span data-ttu-id="a9dad-128">Pour obtenir des propositions de modification des prix ressource basées sur les prix standard :</span><span class="sxs-lookup"><span data-stu-id="a9dad-128">To get resource price change suggestions based on standard prices</span></span>
<span data-ttu-id="a9dad-129">Si vous souhaitez configurer plusieurs autres prix ressource sur la base des prix standard des fiches ressource, vous pouvez utiliser un traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="a9dad-129">If you want to set up multiple alternate resource prices based on the standard prices on the resource cards, you can use a batch job.</span></span>  

1. <span data-ttu-id="a9dad-130">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Nouv. prix ressource proposés**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="a9dad-130">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource Price Changes**, and then choose the related link.</span></span>
2. <span data-ttu-id="a9dad-131">Sélectionnez l'action **Prop. modif. prix ress. (ress)**, puis renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a9dad-131">Choose the **Suggest Res. Price Chg. (Res.)** action, and then fill in the fields as necessary.</span></span>  
3. <span data-ttu-id="a9dad-132">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9dad-132">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="a9dad-133">Lorsque le traitement par lots est terminé, ouvrez la fenêtre **Nouv. prix ressource proposés** pour visualiser les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a9dad-133">When the batch job is finished, open the **Resource Price Changes** window to see the results of the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-alternate-prices"></a><span data-ttu-id="a9dad-134">Pour obtenir des propositions de modification des prix ressource basées sur les prix standard</span><span class="sxs-lookup"><span data-stu-id="a9dad-134">To get resource price change suggestions based on alternate prices</span></span>
<span data-ttu-id="a9dad-135">Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.</span><span class="sxs-lookup"><span data-stu-id="a9dad-135">If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.</span></span>

1. <span data-ttu-id="a9dad-136">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modification de prix de ressource proposée (prix)**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a9dad-136">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Suggest Res. Price Chg. (Price)**, and then choose the related link.</span></span>  
2. <span data-ttu-id="a9dad-137">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a9dad-137">Fill in the fields as necessary.</span></span>
3. <span data-ttu-id="a9dad-138">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="a9dad-138">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="a9dad-139">Lorsque le traitement par lots est terminé, ouvrez la fenêtre **Nouv. prix ressource proposés** pour visualiser les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="a9dad-139">When the batch job is finished, open the **Resource Price Changes** window to see the results of the batch job.</span></span>

## <a name="see-also"></a><span data-ttu-id="a9dad-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a9dad-140">See Also</span></span>
[<span data-ttu-id="a9dad-141">Gestion de projets</span><span class="sxs-lookup"><span data-stu-id="a9dad-141">Project Management</span></span>](projects-manage-projects.md)  
[<span data-ttu-id="a9dad-142">Finances</span><span class="sxs-lookup"><span data-stu-id="a9dad-142">Finance</span></span>](finance.md)  
<span data-ttu-id="a9dad-143">[Achats](purchasing-manage-purchasing.md)       </span><span class="sxs-lookup"><span data-stu-id="a9dad-143">[Purchasing](purchasing-manage-purchasing.md)       </span></span>  
<span data-ttu-id="a9dad-144">[Ventes](sales-manage-sales.md)   </span><span class="sxs-lookup"><span data-stu-id="a9dad-144">[Sales](sales-manage-sales.md)   </span></span>  
<span data-ttu-id="a9dad-145">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a9dad-145">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
