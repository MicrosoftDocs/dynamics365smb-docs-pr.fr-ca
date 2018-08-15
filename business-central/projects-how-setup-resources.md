---
title: "Paramétrer les coûts, prix, et capacité des ressources| Microsoft Docs"
description: "Pour utiliser des ressources et faciliter la gestion de projets, vous spécifiez les coûts et les prix des différents ressources ou groupes de ressources, et définissez la capacité ressource."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, capacity, staff
ms.date: 06/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 982c250becec74472b89ae705057d1b34f95e338
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-resources"></a><span data-ttu-id="6e238-103">Paramétrer des ressources</span><span class="sxs-lookup"><span data-stu-id="6e238-103">Set Up Resources</span></span>
<span data-ttu-id="6e238-104">Pour gérer correctement les activités liées aux ressources, vous devez configurer ces dernières, ainsi que les coûts et prix associés.</span><span class="sxs-lookup"><span data-stu-id="6e238-104">To correctly manage resource activities, you must set up your resources and the related costs and prices.</span></span> <span data-ttu-id="6e238-105">Les prix, remises et règles de facteur coût associés au projet, sont définis dans la fiche projet.</span><span class="sxs-lookup"><span data-stu-id="6e238-105">The job-related prices, discounts, and cost factor rules are set up on the job card.</span></span> <span data-ttu-id="6e238-106">Vous pouvez spécifier les coûts et prix pour des ressources individuelles, des groupes de ressources, ou toutes les ressources disponibles de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="6e238-106">You can specify the costs and prices for individual resources, resource groups, or all available resources of the company.</span></span>

<span data-ttu-id="6e238-107">Lorsque des ressources sont utilisées ou vendues dans le cadre d'un projet, les prix et les coûts qui leur sont associés sont récupérés à l'aide des informations de configuration.</span><span class="sxs-lookup"><span data-stu-id="6e238-107">When resources are used or sold in a job, the prices and costs associated with them are retrieved from the information that you set up.</span></span>

<span data-ttu-id="6e238-108">Vous spécifiez le montant horaire par défaut lors de la création de la ressource.</span><span class="sxs-lookup"><span data-stu-id="6e238-108">You specify the default amount per hour when the resource is created.</span></span> <span data-ttu-id="6e238-109">Par exemple, si vous utilisez une machine spécifique pour un projet de cinq heures, le projet sera calculé sur la base du montant horaire.</span><span class="sxs-lookup"><span data-stu-id="6e238-109">For example, if you use a specific machine on a job for five hours, the job would be calculated based on the amount per hour.</span></span>

## <a name="to-set-up-a-resource"></a><span data-ttu-id="6e238-110">Pour paramétrer une ressource</span><span class="sxs-lookup"><span data-stu-id="6e238-110">To set up a resource</span></span>
<span data-ttu-id="6e238-111">Créez une fiche pour chaque ressource à utiliser dans les projets.</span><span class="sxs-lookup"><span data-stu-id="6e238-111">Create a card for each resource that you want to use in projects.</span></span>

1. <span data-ttu-id="6e238-112">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ressources**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6e238-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.</span></span>
2. <span data-ttu-id="6e238-113">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6e238-113">Choose the **New** action.</span></span>
3. <span data-ttu-id="6e238-114">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e238-114">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-set-up-a-resource-group"></a><span data-ttu-id="6e238-115">Pour configurer un groupe de ressources</span><span class="sxs-lookup"><span data-stu-id="6e238-115">To set up a resource group</span></span>
<span data-ttu-id="6e238-116">Vous pouvez combiner plusieurs ressources dans un groupe ressources.</span><span class="sxs-lookup"><span data-stu-id="6e238-116">You can combine several resources in one resource group.</span></span> <span data-ttu-id="6e238-117">Toutes les capacités et tous les budgets du groupe ressources sont additionnés à partir des ressources.</span><span class="sxs-lookup"><span data-stu-id="6e238-117">All capacities and budgets of resource groups are accumulated from the individual resources.</span></span> <span data-ttu-id="6e238-118">Il est également possible de saisir des capacités pour les groupes ressource, indépendamment des valeurs cumulées ou en plus de ces valeurs.</span><span class="sxs-lookup"><span data-stu-id="6e238-118">It is also possible to enter capacities for resource groups either independently of the accumulated values or in addition to them.</span></span>

1. <span data-ttu-id="6e238-119">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ressources**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6e238-119">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resource groups**, and then choose the related link.</span></span>
2. <span data-ttu-id="6e238-120">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="6e238-120">Choose the **New** action.</span></span>
3. <span data-ttu-id="6e238-121">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e238-121">Fill in the fields as necessary.</span></span>

## <a name="to-set-capacity-for-a-resource"></a><span data-ttu-id="6e238-122">Pour définir la capacité d'une ressource</span><span class="sxs-lookup"><span data-stu-id="6e238-122">To set capacity for a resource</span></span>
<span data-ttu-id="6e238-123">Pour calculer le temps qu'une ressource peut passer sur des projets, leur capacité doit d'abord être configurée comme temps disponible par période sur le calendrier de travail.</span><span class="sxs-lookup"><span data-stu-id="6e238-123">To calculate how much time a resource can spend on jobs, their capacity must first be set up as available time per period on the work calendar.</span></span> <span data-ttu-id="6e238-124">Cette configuration est utilisée lorsque vous renseignez les lignes planification projet qui contiennent la ressource.</span><span class="sxs-lookup"><span data-stu-id="6e238-124">This setup is used when you fill in job planning lines that contain the resource.</span></span> <span data-ttu-id="6e238-125">Pour plus d'informations, voir [Créer des projets](projects-how-create-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="6e238-125">For more information, see [Create Jobs](projects-how-create-jobs.md).</span></span>

1. <span data-ttu-id="6e238-126">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ressources**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6e238-126">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.</span></span>
2. <span data-ttu-id="6e238-127">Ouvrez la fiche ressource appropriée, puis cliquez sur **Capacité ressource**.</span><span class="sxs-lookup"><span data-stu-id="6e238-127">Open the relevant resource card, and then choose the **Resource Capacity** action.</span></span>
3. <span data-ttu-id="6e238-128">Dans la fenêtre **Capacité ressource**, dans le champ **Afficher par**, précisez la durée de la période (par exemple **Jour**) qui est indiquée dans le raccourci **Matrice Capacité ressource**.</span><span class="sxs-lookup"><span data-stu-id="6e238-128">In the **Resource Capacity** window, in the **View By** field, specify the length of the period, such as **Day**, that is shown on columns on the **Resource Capacity Matrix** FastTab.</span></span>
4. <span data-ttu-id="6e238-129">Pour chaque ressource sur une ligne, spécifiez pour chaque période sur les colonnes le nombre d'heures pendant lesquelles la ressource est disponible.</span><span class="sxs-lookup"><span data-stu-id="6e238-129">For each resource on a line, specify for each period on the columns the number of hours that the resource is available.</span></span>
5. <span data-ttu-id="6e238-130">Sinon, pour détailler la capacité hebdomadaire de la ressource dans un certain intervalle de temps, cliquez sur **Paramétrage capacité ressource**.</span><span class="sxs-lookup"><span data-stu-id="6e238-130">Alternatively, to detail the resource's weekly capacity within a starting and ending date, choose the **Set Capacity** action.</span></span>
6. <span data-ttu-id="6e238-131">Dans la fenêtre **Paramétrage capacité ressource**, renseignez les champs sur une ligne selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e238-131">In the **Resource Capacity Settings** window, fill in the fields as necessary.</span></span>
7. <span data-ttu-id="6e238-132">Cliquez sur **Mettre à jour la capacité**.</span><span class="sxs-lookup"><span data-stu-id="6e238-132">Choose the **Update Capacity** action.</span></span> <span data-ttu-id="6e238-133">La fenêtre **Capacité ressource** est mise à jour avec la capacité saisie.</span><span class="sxs-lookup"><span data-stu-id="6e238-133">The **Resource Capacity** window is updated with the entered capacity.</span></span>
8. <span data-ttu-id="6e238-134">Fermez la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="6e238-134">Close the window.</span></span>

## <a name="to-set-up-alternate-resource-costs"></a><span data-ttu-id="6e238-135">Pour configurer des coûts ressource secondaires</span><span class="sxs-lookup"><span data-stu-id="6e238-135">To set up alternate resource costs</span></span>
<span data-ttu-id="6e238-136">Outre le coût spécifié sur la fiche ressource, vous pouvez configurer des coûts secondaires pour chaque ressource.</span><span class="sxs-lookup"><span data-stu-id="6e238-136">In addition to the cost specified on the resource card, you can set up alternate costs for each resource.</span></span> <span data-ttu-id="6e238-137">Par exemple, si le taux horaire d'un employé augmente en raison d'heures supplémentaires, vous pouvez configurer un coût ressource pour le taux lié aux heures supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="6e238-137">For example, if you pay an employee a higher hourly rate for overtime, you can set up a resource cost for the overtime rate.</span></span> <span data-ttu-id="6e238-138">Le coût secondaire que vous avez configuré pour la ressource remplace le coût de la fiche ressource lorsque vous utilisez la ressource dans le journal ressource.</span><span class="sxs-lookup"><span data-stu-id="6e238-138">The alternate cost that you set up for the resource will override the cost on the resource card when you use the resource in the resource journal.</span></span>

1. <span data-ttu-id="6e238-139">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ressources**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6e238-139">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.</span></span>  
2. <span data-ttu-id="6e238-140">Sélectionnez la ressource pour laquelle vous souhaitez configurer un ou plusieurs coûts secondaires, puis cliquez sur **Coûts**.</span><span class="sxs-lookup"><span data-stu-id="6e238-140">Select the resource for that you want to set up one or more alternate costs for, and then choose the **Costs** action.</span></span>  
3. <span data-ttu-id="6e238-141">Dans la fenêtre **Coûts ressource**, renseignez les champs sur une ligne selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e238-141">In the **Resource Costs** window, fill in the fields on a line as necessary.</span></span>  
4. <span data-ttu-id="6e238-142">Répétez l'étape 3 pour chaque autre coût ressource à configurer.</span><span class="sxs-lookup"><span data-stu-id="6e238-142">Repeat step 3 for each alternate resource cost that you want to set up.</span></span>

<span data-ttu-id="6e238-143">**Remarque**.</span><span class="sxs-lookup"><span data-stu-id="6e238-143">**Note**.</span></span> <span data-ttu-id="6e238-144">Pour configurer les coûts des ressources s'appliquant à toutes les ressources et à tous les groupes ressources, ouvrez la fenêtre **Coûts ressource**, puis renseignez les champs.</span><span class="sxs-lookup"><span data-stu-id="6e238-144">To set up resource costs that will apply to all resources and resource groups, open the **Resource Costs** window and fill in the fields.</span></span>

## <a name="to-set-up-alternate-resource-prices"></a><span data-ttu-id="6e238-145">Pour configurer le prix des ressources secondaires</span><span class="sxs-lookup"><span data-stu-id="6e238-145">To set up alternate resource prices</span></span>
<span data-ttu-id="6e238-146">Outre le prix spécifié sur la fiche ressource, vous pouvez configurer des prix secondaires pour chaque ressource.</span><span class="sxs-lookup"><span data-stu-id="6e238-146">In addition to price specified on the resource card, you can set up alternate prices for each resource.</span></span> <span data-ttu-id="6e238-147">Ces prix secondaires peuvent être conditionnels.</span><span class="sxs-lookup"><span data-stu-id="6e238-147">These alternate prices can be conditional.</span></span> <span data-ttu-id="6e238-148">Ils peuvent être liés à l'utilisation de la ressource avec un projet ou un type travail donné.</span><span class="sxs-lookup"><span data-stu-id="6e238-148">They can depend on whether the resource is used with a specific job or work type.</span></span>

1. <span data-ttu-id="6e238-149">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ressources**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="6e238-149">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Resources**, and then choose the related link.</span></span>
2. <span data-ttu-id="6e238-150">Sélectionnez la ressource pour laquelle vous souhaitez configurer un ou plusieurs prix secondaires, puis sélectionnez l'action **Prix**.</span><span class="sxs-lookup"><span data-stu-id="6e238-150">Select the resource for that you want to set up one or more alternate prices for, and then choose the **Prices** action.</span></span>
3. <span data-ttu-id="6e238-151">Dans la fenêtre **Prix ressource**, renseignez les champs sur une ligne selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6e238-151">In the **Resource Prices** window, fill in the fields on a line as necessary.</span></span>
4. <span data-ttu-id="6e238-152">Répétez l'étape 3 pour chaque autre prix ressource à configurer.</span><span class="sxs-lookup"><span data-stu-id="6e238-152">Repeat step 3 for each alternate resource price that you want to set up.</span></span>

## <a name="see-also"></a><span data-ttu-id="6e238-153">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6e238-153">See Also</span></span>
[<span data-ttu-id="6e238-154">Configuration de la gestion de projet</span><span class="sxs-lookup"><span data-stu-id="6e238-154">Setting Up Project Management</span></span>](projects-setup-projects.md)  
[<span data-ttu-id="6e238-155">Gestion de projets</span><span class="sxs-lookup"><span data-stu-id="6e238-155">Project Management</span></span>](projects-manage-projects.md)  
[<span data-ttu-id="6e238-156">Finances</span><span class="sxs-lookup"><span data-stu-id="6e238-156">Finance</span></span>](finance.md)  
<span data-ttu-id="6e238-157">[Achats](purchasing-manage-purchasing.md)       </span><span class="sxs-lookup"><span data-stu-id="6e238-157">[Purchasing](purchasing-manage-purchasing.md)       </span></span>  
<span data-ttu-id="6e238-158">[Ventes](sales-manage-sales.md)    </span><span class="sxs-lookup"><span data-stu-id="6e238-158">[Sales](sales-manage-sales.md)    </span></span>  
<span data-ttu-id="6e238-159">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="6e238-159">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
