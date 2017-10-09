---
title: Enregistrer et ajuster l'utilisation et les prix des ressources| Microsoft Docs
description: "Décrit la manière dont vous pouvez enregistrer l'utilisation ou la consommation ressource associée à un projet, de garder la trace et de gérer les coûts, les prix, ainsi que les types de travaux."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff
ms.date: 06/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: eea34afbee429d14ab150894729cb4ea3843bb2b
ms.openlocfilehash: f110f4cc342f5284e3da2641d56dc13f67c3773a
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-use-resources-for-jobs"></a><span data-ttu-id="eb61f-103">Procédure : Utiliser des ressources pour des projets</span><span class="sxs-lookup"><span data-stu-id="eb61f-103">How to: Use Resources for Jobs</span></span>
<span data-ttu-id="eb61f-104">Vous devez enregistrer l'utilisation des ressources dans le journal projet pour suivre les coûts et les prix, ainsi que les types de travaux associés aux projets.</span><span class="sxs-lookup"><span data-stu-id="eb61f-104">You record the usage of resources in the job journal to keep track of costs, prices, and the work types that are linked to jobs.</span></span> <span data-ttu-id="eb61f-105">Pour plus d'informations, reportez-vous à [Procédure : Enregistrer l'utilisation pour les projets](projects-how-record-job-usage.md).</span><span class="sxs-lookup"><span data-stu-id="eb61f-105">For more information, see [How to: Record Usage for Jobs](projects-how-record-job-usage.md).</span></span>

<span data-ttu-id="eb61f-106">Vous pouvez aussi reporter l'utilisation d'une ressource dans un journal ressource.</span><span class="sxs-lookup"><span data-stu-id="eb61f-106">You can also post the usage of a resource in a resource journal.</span></span> <span data-ttu-id="eb61f-107">Les écritures reportées dans un journal ressource n'ont aucune incidence sur le grand livre.</span><span class="sxs-lookup"><span data-stu-id="eb61f-107">Entries posted in a resource journal have no effect on the general ledger.</span></span>

> [!NOTE]  
>   <span data-ttu-id="eb61f-108">Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-108">This functionality requires that your experience is set to **Suite**.</span></span> <span data-ttu-id="eb61f-109">Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="eb61f-109">For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).</span></span>

## <a name="to-assign-resources-to-jobs"></a><span data-ttu-id="eb61f-110">Pour affecter des ressources aux projets</span><span class="sxs-lookup"><span data-stu-id="eb61f-110">To assign resources to jobs</span></span>
<span data-ttu-id="eb61f-111">Vous pouvez affecter des ressources aux projets en créant des lignes planification projet pour le projet.</span><span class="sxs-lookup"><span data-stu-id="eb61f-111">You assign resources to jobs by creating job planning lines for the job.</span></span> <span data-ttu-id="eb61f-112">Pour plus d'informations, reportez-vous à [Procédure : Créer des projets](projects-how-create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="eb61f-112">For more information, see [How to: Create Jobs](projects-how-create-jobs.md).</span></span>

## <a name="to-record-resource-usage-for-a-job"></a><span data-ttu-id="eb61f-113">Pour enregistrer l'utilisation des ressources pour un projet</span><span class="sxs-lookup"><span data-stu-id="eb61f-113">To record resource usage for a job</span></span>
1. <span data-ttu-id="eb61f-114">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles projet**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eb61f-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Job Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="eb61f-115">Ouvrez le lot journal projet approprié, puis complétez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="eb61f-115">Open a relevant job journal batch, and then fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="eb61f-116">Lorsque la feuille est renseignée, cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-116">When the journal is complete, choose the **Post** action.</span></span>

## <a name="to-adjust-resource-prices"></a><span data-ttu-id="eb61f-117">Pour ajuster le prix des ressources</span><span class="sxs-lookup"><span data-stu-id="eb61f-117">To adjust resource prices</span></span>
<span data-ttu-id="eb61f-118">Si vous souhaitez modifier le coût ou le prix d'un grand nombre de ressources, vous pouvez utiliser un traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="eb61f-118">If you want to change costs or prices for a large number of resources, you can use a batch job.</span></span>  

1. <span data-ttu-id="eb61f-119">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ajuster coûts/prix ressource**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eb61f-119">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Adjust Resource Costs/Prices**, and then choose the related link.</span></span>
2. <span data-ttu-id="eb61f-120">Renseignez les autres champs selon vos besoins, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-120">Fill in the fields on a line as necessary, and then choose the **OK** button.</span></span>

> [!NOTE]  
>   <span data-ttu-id="eb61f-121">Ce traitement en lot ne crée pas et n'ajuste pas les nouveaux coûts ou prix des ressources.</span><span class="sxs-lookup"><span data-stu-id="eb61f-121">This batch job does not create or adjust alternate costs or prices for resources.</span></span> <span data-ttu-id="eb61f-122">Il modifie uniquement le contenu du champ de la fiche ressource correspondant au champ **Champ à modifier** que vous avez sélectionné dans le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="eb61f-122">It only changes the contents of the field on the resource card for the **Adjust Field** field that you selected in the batch job.</span></span> <span data-ttu-id="eb61f-123">L'ajustement s'appliquant immédiatement aux ressources, vérifiez les facteurs d'ajustement avant de lancer le traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="eb61f-123">The adjustment will take effect immediately for resources, so check your adjustment factors before you run the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-existing-alternate-prices"></a><span data-ttu-id="eb61f-124">Pour obtenir des propositions de modification des prix ressource basées sur les prix secondaires existants</span><span class="sxs-lookup"><span data-stu-id="eb61f-124">To get resource price change suggestions based on existing alternate prices</span></span>
<span data-ttu-id="eb61f-125">Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.</span><span class="sxs-lookup"><span data-stu-id="eb61f-125">If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.</span></span>

1. <span data-ttu-id="eb61f-126">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Nouv. prix ressource proposés**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eb61f-126">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource Price Changes**, and then choose the related link.</span></span>
2. <span data-ttu-id="eb61f-127">Sélectionnez l'action **Prop. modif. prix ress. (prix)**, puis renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="eb61f-127">Choose the **Suggest Res. Price Chg. (Price)** action, and then fill in the fields as necessary.</span></span>
3. <span data-ttu-id="eb61f-128">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-128">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="eb61f-129">Lorsque le traitement par lots est terminé, la fenêtre **Nouv. prix ressource proposés** affiche les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="eb61f-129">When the batch job is finished, the **Resource Price Changes** window shows the results of the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-standard-prices"></a><span data-ttu-id="eb61f-130">Pour obtenir des propositions de modification des prix ressource basées sur les prix standard :</span><span class="sxs-lookup"><span data-stu-id="eb61f-130">To get resource price change suggestions based on standard prices</span></span>
<span data-ttu-id="eb61f-131">Si vous souhaitez configurer plusieurs autres prix ressource sur la base des prix standard des fiches ressource, vous pouvez utiliser un traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="eb61f-131">If you want to set up multiple alternate resource prices based on the standard prices on the resource cards, you can use a batch job.</span></span>  

1. <span data-ttu-id="eb61f-132">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Nouv. prix ressource proposés**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eb61f-132">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource Price Changes**, and then choose the related link.</span></span>
2. <span data-ttu-id="eb61f-133">Sélectionnez l'action **Prop. modif. prix ress. (ress)**, puis renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="eb61f-133">Choose the **Suggest Res. Price Chg. (Res.)** action, and then fill in the fields as necessary.</span></span>  
3. <span data-ttu-id="eb61f-134">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-134">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="eb61f-135">Lorsque le traitement par lots est terminé, ouvrez la fenêtre **Nouv. prix ressource proposés** pour visualiser les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="eb61f-135">When the batch job is finished, open the **Resource Price Changes** window to see the results of the batch job.</span></span>

## <a name="to-get-resource-price-change-suggestions-based-on-alternate-prices"></a><span data-ttu-id="eb61f-136">Pour obtenir des propositions de modification des prix ressource basées sur les prix standard</span><span class="sxs-lookup"><span data-stu-id="eb61f-136">To get resource price change suggestions based on alternate prices</span></span>
<span data-ttu-id="eb61f-137">Si vous avez déjà configuré d'autres prix pour un certain nombre de ressources, vous pouvez utiliser un traitement en lot pour configurer d'autres prix ressource.</span><span class="sxs-lookup"><span data-stu-id="eb61f-137">If you have already set up alternate resource price for some resources, you can use a batch job to set up multiple alternate resource prices.</span></span>

1. <span data-ttu-id="eb61f-138">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modification de prix de ressource proposée (prix)**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="eb61f-138">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Suggest Res. Price Chg. (Price)**, and then choose the related link.</span></span>  
2. <span data-ttu-id="eb61f-139">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="eb61f-139">Fill in the fields as necessary.</span></span>
3. <span data-ttu-id="eb61f-140">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="eb61f-140">Choose the **OK** button.</span></span>  
4. <span data-ttu-id="eb61f-141">Lorsque le traitement par lots est terminé, ouvrez la fenêtre **Nouv. prix ressource proposés** pour visualiser les résultats du traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="eb61f-141">When the batch job is finished, open the **Resource Price Changes** window to see the results of the batch job.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb61f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eb61f-142">See Also</span></span>
[<span data-ttu-id="eb61f-143">Gestion de projets</span><span class="sxs-lookup"><span data-stu-id="eb61f-143">Project Management</span></span>](projects-manage-projects.md)  
[<span data-ttu-id="eb61f-144">Finances</span><span class="sxs-lookup"><span data-stu-id="eb61f-144">Finance</span></span>](finance.md)  
<span data-ttu-id="eb61f-145">[Achats](purchasing-manage-purchasing.md)       </span><span class="sxs-lookup"><span data-stu-id="eb61f-145">[Purchasing](purchasing-manage-purchasing.md)       </span></span>  
<span data-ttu-id="eb61f-146">[Ventes](sales-manage-sales.md)   </span><span class="sxs-lookup"><span data-stu-id="eb61f-146">[Sales](sales-manage-sales.md)   </span></span>  
<span data-ttu-id="eb61f-147">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="eb61f-147">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

