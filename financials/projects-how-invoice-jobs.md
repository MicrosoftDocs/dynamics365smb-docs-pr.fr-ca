---
title: "Créez une facture vente projet pour facturer un projet| Microsoft Docs"
description: "Décrit comment facturer des clients pour les coûts au fur et à mesure de l'avancée du projet."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project invoice
ms.date: 06/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 9367dc5875b687b95076efffb3b0df2019332651
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-invoice-jobs"></a><span data-ttu-id="14749-103">Procédure : Facturer des projets</span><span class="sxs-lookup"><span data-stu-id="14749-103">How to: Invoice Jobs</span></span>
<span data-ttu-id="14749-104">Au cours du projet, les coûts provenant de l'utilisation de ressources, de matières, et d'achats associés au projet peuvent s'accumuler.</span><span class="sxs-lookup"><span data-stu-id="14749-104">During the project, job costs from resource usage, materials, and job-related purchases can accumulate.</span></span> <span data-ttu-id="14749-105">Au fur et à mesure de la progression du projet, ces transactions sont reportées dans le journal projet.</span><span class="sxs-lookup"><span data-stu-id="14749-105">As the job progresses, these transactions get posted to the job journal.</span></span> <span data-ttu-id="14749-106">Il est important que tous les coûts soient enregistrés dans le journal projet avant de facturer le client.</span><span class="sxs-lookup"><span data-stu-id="14749-106">It is important that all costs get recorded in the job journal before you invoice the customer.</span></span>

<span data-ttu-id="14749-107">Vous pouvez facturer l'ensemble du projet à partir de la fenêtre **Lignes tâche projet** ou facturer uniquement les lignes facturables sélectionnées dans la fenêtre **Lignes planning**.</span><span class="sxs-lookup"><span data-stu-id="14749-107">You can invoice the whole job from the **Job Task Lines** window or only invoice selected billable lines from the **Planning Lines** window.</span></span> <span data-ttu-id="14749-108">La facturation peut avoir lieu une fois le projet terminé ou à certains intervalles au cours du projet sur la base d'une prévision de facture.</span><span class="sxs-lookup"><span data-stu-id="14749-108">Invoicing can be done after the job is finished or at certain intervals during the job's progress based on an invoicing schedule.</span></span>

> [!NOTE]  
>   <span data-ttu-id="14749-109">Si vous sélectionnez **Facturable** dans le champ **Type ligne projet** dans les documents d'achat pour les achats associés au projet, les lignes planning projet prêtes pour facturation sont créées.</span><span class="sxs-lookup"><span data-stu-id="14749-109">If you select **Billable** in the **Job Line Type** field on the purchase documents for job-related purchases, then job planning lines that are ready to be invoiced to the customer are created.</span></span> <span data-ttu-id="14749-110">Pour en savoir plus, reportez-vous à [Procédure : Gérer des fournitures d'un projet](projects-how-manage-project-supplies.md).</span><span class="sxs-lookup"><span data-stu-id="14749-110">For more information, see [How to: Manage Project Supplies](projects-how-manage-project-supplies.md).</span></span>

## <a name="to-create-and-post-a-job-sales-invoice"></a><span data-ttu-id="14749-111">Pour créer et reporter une facture vente projet</span><span class="sxs-lookup"><span data-stu-id="14749-111">To create and post a job sales invoice</span></span>
<span data-ttu-id="14749-112">Vous pouvez créer une facture pour un projet ou pour une ou plusieurs tâches projet pour un client lorsque le travail à facturer est terminé ou lorsque la date de facturation dépendante d'une prévision de facture est atteinte.</span><span class="sxs-lookup"><span data-stu-id="14749-112">You can create an invoice for a job or for one or more job tasks for a customer when either the work to be invoiced is complete or the date for invoicing based on an invoicing schedule has been reached.</span></span>

<span data-ttu-id="14749-113">Dans la fenêtre **Projets**, vous pouvez facturer un client en sélectionnant le projet, puis en cliquant sur **Créer une facture vente projet**.</span><span class="sxs-lookup"><span data-stu-id="14749-113">From the **Jobs** window, you can invoice a customer by selecting the job, and then choosing the **Create Job Sales Invoice** action.</span></span> <span data-ttu-id="14749-114">La procédure suivante explique comment utiliser un traitement en lot pour facturer plusieurs projets.</span><span class="sxs-lookup"><span data-stu-id="14749-114">The following procedure shows how to use a batch job to invoice multiple jobs.</span></span>  

1. <span data-ttu-id="14749-115">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Projet Créer facture vente**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="14749-115">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Job Create Sales Invoice**, and then choose the related link.</span></span>  
2. <span data-ttu-id="14749-116">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="14749-116">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="14749-117">Définissez des filtres si vous souhaitez limiter le nombre de projets que le traitement en lot va traiter.</span><span class="sxs-lookup"><span data-stu-id="14749-117">Set filters if you want to limit the jobs that the batch job will process.</span></span>
4. <span data-ttu-id="14749-118">Pour créer les factures, cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="14749-118">Choose the **OK** button to create the invoices.</span></span>  

## <a name="to-create-multiple-job-sales-invoices-from-job-planning-lines"></a><span data-ttu-id="14749-119">Pour créer plusieurs factures vente projet à partir de lignes planification projet</span><span class="sxs-lookup"><span data-stu-id="14749-119">To create multiple job sales invoices from job planning lines</span></span>
<span data-ttu-id="14749-120">Vous pouvez créer une facture à partir des lignes planification projet et indiquer à ce moment-là la quantité de l'article, la ressource ou le compte du grand livre sur lequel vous souhaitez facturer.</span><span class="sxs-lookup"><span data-stu-id="14749-120">You can create an invoice from a job planning lines, and indicate at that time the quantity of the item, resource, or general ledger account that you want to invoice.</span></span>

1. <span data-ttu-id="14749-121">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Projets**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="14749-121">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Jobs**, and then choose the related link.</span></span>
2. <span data-ttu-id="14749-122">Ouvrez le projet approprié.</span><span class="sxs-lookup"><span data-stu-id="14749-122">Open a relevant job.</span></span>
3. <span data-ttu-id="14749-123">Sélectionnez une tâche projet pour laquelle le champ **Type tâche projet** contient **Validation** puis, cliquez sur **Lignes planning projet**.</span><span class="sxs-lookup"><span data-stu-id="14749-123">Select a job task for which the **Job Task Type** field contains **Posting**, and then choose the **Job Planning Lines** action.</span></span>  
4. <span data-ttu-id="14749-124">Dans une ligne planning projet, dans le champ **Qté à transférer à facturer**, saisissez la quantité de l'article, la ressource, le type de compte général sur lequel vous souhaitez facturer.</span><span class="sxs-lookup"><span data-stu-id="14749-124">On a job planning line, in the **Qty. To Transfer to Invoice** field, enter the quantity of the item, resource, general ledger account type that you want to invoice.</span></span>  
5. <span data-ttu-id="14749-125">Cliquez sur **Créer facture vente**.</span><span class="sxs-lookup"><span data-stu-id="14749-125">Choose the **Create Sales Invoice** action.</span></span>
6. <span data-ttu-id="14749-126">Dans la fenêtre **Projet Créer facture vente**, saisissez la date de validation et si vous souhaitez créer une facture ou ajouter cette facture à une facture existante.</span><span class="sxs-lookup"><span data-stu-id="14749-126">In the **Job Create Sales Invoice** window, enter the posting date and whether you want to create a new invoice or append this invoice to an existing one.</span></span>
7. <span data-ttu-id="14749-127">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="14749-127">Choose the **OK** button.</span></span>  

    <span data-ttu-id="14749-128">Dans la ligne planning projet, dans le champ **Qté à transférer à facturer**, vous pouvez visualiser la quantité.</span><span class="sxs-lookup"><span data-stu-id="14749-128">On the job planning line, in the **Qty. Transferred to Invoice** field, you can see the quantity.</span></span>
8. <span data-ttu-id="14749-129">Dans la fenêtre **Lignes planning projet**, cliquez sur **Avoirs/Factures vente**.</span><span class="sxs-lookup"><span data-stu-id="14749-129">In the **Job Planning Lines** window, choose the **Sales Invoices/Credit Memos** action.</span></span>

    <span data-ttu-id="14749-130">La fenêtre **Facture vente** s'ouvre et affiche la quantité que vous avez transférée à la facture.</span><span class="sxs-lookup"><span data-stu-id="14749-130">The **Sales Invoice** window opens, showing the quantity that you have transferred to the invoice.</span></span>  
9. <span data-ttu-id="14749-131">Apportez les modifications supplémentaires, puis cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="14749-131">Make any additional changes, and then choose the **Post** action.</span></span>

> [!NOTE]  
>   <span data-ttu-id="14749-132">La procédure ci-dessus permet également de créer, de consulter, puis de reporter une note de crédit vente associée à un projet.</span><span class="sxs-lookup"><span data-stu-id="14749-132">The above procedure is similar for creating, reviewing, and posting a job-related sales credit memo.</span></span>

## <a name="to-calculate-and-post-job-completion-entries"></a><span data-ttu-id="14749-133">Pour calculer et reporter les écritures d'achèvement du projet</span><span class="sxs-lookup"><span data-stu-id="14749-133">To calculate and post job completion entries</span></span>
<span data-ttu-id="14749-134">À la fin des activités d'un projet (validation et facturation comprises), vous devez le mettre à jour pour définir le **Statut** du projet sur **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="14749-134">When you have completed all activities for a job, including usage posting and invoicing, you must update the job to have a **Status** of **Completed**.</span></span> <span data-ttu-id="14749-135">Ensuite, vous devez inverser tous les TEC reportés antérieurement dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="14749-135">Then, you must reverse any WIP that has been posted to the general ledger.</span></span>

1. <span data-ttu-id="14749-136">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Projets**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="14749-136">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Jobs**, and then choose the related link.</span></span>  
2. <span data-ttu-id="14749-137">Sélectionnez un projet ouvert, puis cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="14749-137">Select an open job, and then choose the **Edit** action.</span></span>
3. <span data-ttu-id="14749-138">Dans le champ **Statut**, sélectionnez **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="14749-138">In the **Status** field, select **Completed**.</span></span>
4. <span data-ttu-id="14749-139">Suivez les phases d'aide pour calculer et reporter les TEC.</span><span class="sxs-lookup"><span data-stu-id="14749-139">Follow the assistance steps to calculate and post WIP.</span></span> <span data-ttu-id="14749-140">Sinon, suivez les phases 5 et 6 pour le faire manuellement.</span><span class="sxs-lookup"><span data-stu-id="14749-140">Alternatively, follows steps 5 and 6 to do so manually.</span></span>  
5. <span data-ttu-id="14749-141">Cliquez sur **Calculer TEC**.</span><span class="sxs-lookup"><span data-stu-id="14749-141">Choose the **Calculate WIP** action.</span></span>
6. <span data-ttu-id="14749-142">Dans la fenêtre **Projet Calculer TEC**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="14749-142">In the **Job Calculate WIP** window, fill in the fields as necessary.</span></span>  

     <span data-ttu-id="14749-143">Les écritures TEC projet créées par le traitement par lots auront la case **Projet terminé** cochée pour indiquer qu'il s'agit d'écritures d’achèvement.</span><span class="sxs-lookup"><span data-stu-id="14749-143">The job WIP entries created by running the batch job will have the **Job Complete** check box selected to show that they are completion entries.</span></span>  
7. <span data-ttu-id="14749-144">Cliquez sur **Projet Valider TEC en comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="14749-144">Choose the **Job Post WIP to G/L** action.</span></span>
8. <span data-ttu-id="14749-145">Dans la fenêtre **Projet Valider TEC en comptabilité**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="14749-145">In the **Job Post WIP to G/L** window, fill in the fields as necessary.</span></span>  

     <span data-ttu-id="14749-146">Les écritures comptabilité TEC projet créées par le traitement par lots verront la case **Projet terminé** cochée pour indiquer qu'il s'agit d'écritures d’achèvement.</span><span class="sxs-lookup"><span data-stu-id="14749-146">The job WIP general ledger entries created by running the batch job will have the **Job Complete** check box selected to show they are completion entries.</span></span>

## <a name="see-also"></a><span data-ttu-id="14749-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14749-147">See Also</span></span>
[<span data-ttu-id="14749-148">Gestion des projets</span><span class="sxs-lookup"><span data-stu-id="14749-148">Managing Projects</span></span>](projects-manage-projects.md)  
[<span data-ttu-id="14749-149">Finance</span><span class="sxs-lookup"><span data-stu-id="14749-149">Finance</span></span>](finance.md)  
<span data-ttu-id="14749-150">[Procédure d'achat](purchasing-manage-purchasing.md)       </span><span class="sxs-lookup"><span data-stu-id="14749-150">[Purchasing](purchasing-manage-purchasing.md)       </span></span>  
<span data-ttu-id="14749-151">[Vente](sales-manage-sales.md)    </span><span class="sxs-lookup"><span data-stu-id="14749-151">[Sales](sales-manage-sales.md)    </span></span>  
<span data-ttu-id="14749-152">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="14749-152">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
