---
title: "Procédure : exporter et importer des flux de travail | Microsoft Docs"
description: "Pour transférer des workflows vers d'autres bases de données [!INCLUDE[d365fin](includes/d365fin_md.md)], par exemple pour gagner du temps lors de la création de workflows, vous pouvez exporter et importer des workflows."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 8126d3850103819e885d9d131ca3074f1b7cfda1
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-export-and-import-workflows"></a><span data-ttu-id="5af0f-103">Procédure : exporter et importer des workflows</span><span class="sxs-lookup"><span data-stu-id="5af0f-103">How to: Export and Import Workflows</span></span>
<span data-ttu-id="5af0f-104">Pour transférer des workflows vers d'autres bases de données [!INCLUDE[d365fin](includes/d365fin_md.md)], par exemple pour gagner du temps lors de la création de workflows, vous pouvez exporter et importer des workflows.</span><span class="sxs-lookup"><span data-stu-id="5af0f-104">To transfer workflows to other [!INCLUDE[d365fin](includes/d365fin_md.md)] databases, for example to save time when creating new workflows, you can export and import workflows.</span></span>  

 <span data-ttu-id="5af0f-105">Un autre moyen rapide de créer des workflows consiste à les créer à partir de modèles de workflow.</span><span class="sxs-lookup"><span data-stu-id="5af0f-105">Another way to quickly create workflows is to create workflows from workflow templates.</span></span> <span data-ttu-id="5af0f-106">Pour plus d'informations, reportez\-vous à [Procédure : créer des flux de travail à partir de modèles de flux de travail](across-how-to-create-workflows-from-workflow-templates.md).</span><span class="sxs-lookup"><span data-stu-id="5af0f-106">For more information, see [How to: Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).</span></span>  

 <span data-ttu-id="5af0f-107">Dans la fenêtre **Workflow**, créez un workflow en répertoriant les étapes concernées sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="5af0f-107">In the **Workflow** window, you create a workflow by listing the involved steps on the lines.</span></span> <span data-ttu-id="5af0f-108">Chaque étape comprend un événement de workflow modéré par des conditions d'événement, et une réponse de workflow modérée par des options de réponse.</span><span class="sxs-lookup"><span data-stu-id="5af0f-108">Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options.</span></span> <span data-ttu-id="5af0f-109">Définissez les phases de workflow en renseignez les champs des lignes de workflow à partir de listes fixes de valeurs d'événement et de réponse qui sont les scénarios pris en charge par le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="5af0f-109">You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.</span></span> <span data-ttu-id="5af0f-110">Pour plus d'informations, reportez\-vous à [Procédure : créer des flux de travail](across-how-to-create-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="5af0f-110">For more information, see [How to: Create Workflows](across-how-to-create-workflows.md).</span></span>  

## <a name="to-export-a-workflow"></a><span data-ttu-id="5af0f-111">Pour exporter un workflow</span><span class="sxs-lookup"><span data-stu-id="5af0f-111">To export a workflow</span></span>  
1.  <span data-ttu-id="5af0f-112">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Flux de travail**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="5af0f-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Workflows**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="5af0f-113">Sélectionnez un flux de travail, puis sélectionnez l'action **Exporter vers un fichier**.</span><span class="sxs-lookup"><span data-stu-id="5af0f-113">Select a workflow, and then choose the **Export to File** action.</span></span>  
3.  <span data-ttu-id="5af0f-114">Dans la fenêtre **Exporter fichier**, cliquez sur le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5af0f-114">In the **Export File** window, choose the **Save** button.</span></span>  
4.  <span data-ttu-id="5af0f-115">Dans la fenêtre **Exporter**, sélectionnez un emplacement de fichier, puis choisissez le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="5af0f-115">In the **Export** window, select a file location, and then choose the **Save** button.</span></span>  

## <a name="to-import-a-workflow"></a><span data-ttu-id="5af0f-116">Pour importer un workflow</span><span class="sxs-lookup"><span data-stu-id="5af0f-116">To import a workflow</span></span>  
1.  <span data-ttu-id="5af0f-117">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Flux de travail**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="5af0f-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Workflows**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="5af0f-118">Choisissez l'action **Importer à partir d'un fichier**.</span><span class="sxs-lookup"><span data-stu-id="5af0f-118">Choose the **Import from File** action.</span></span>  
3.  <span data-ttu-id="5af0f-119">Dans la fenêtre **Importer**, sélectionnez le fichier XML contenant le workflow, puis choisissez le bouton **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="5af0f-119">In the **Import** window, choose the XML file that contains the workflow, and then choose the **Open** button.</span></span>  

> [!CAUTION]  
>  <span data-ttu-id="5af0f-120">Si le code du workflow existe déjà dans la base de données, les étapes du workflow sont remplacées avec celles du workflow importé.</span><span class="sxs-lookup"><span data-stu-id="5af0f-120">If the workflow code already exists in the database, the workflow steps will be overwritten with the steps in the imported workflow.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5af0f-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5af0f-121">See Also</span></span>  
 <span data-ttu-id="5af0f-122">[Procédure : créer des workflows](across-how-to-create-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-122">[How to: Create Workflows](across-how-to-create-workflows.md) </span></span>  
 <span data-ttu-id="5af0f-123">[Procédure : créer des workflows à partir de modèles de workflow](across-how-to-create-workflows-from-workflow-templates.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-123">[How to: Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md) </span></span>  
 <span data-ttu-id="5af0f-124">[Procédure : afficher des instances d'étape de workflow archivées](across-how-to-view-archived-workflow-step-instances.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-124">[How to: View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md) </span></span>  
 <span data-ttu-id="5af0f-125">[Procédure : supprimer des workflows](across-how-to-delete-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-125">[How to: Delete Workflows](across-how-to-delete-workflows.md) </span></span>  
 <span data-ttu-id="5af0f-126">[Procédure pas à pas : Configuration et utilisation d'un flux d'approbation achat](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-126">[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md) </span></span>  
 <span data-ttu-id="5af0f-127">[Paramétrage des workflows](across-set-up-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-127">[Setting Up Workflows](across-set-up-workflows.md) </span></span>  
 <span data-ttu-id="5af0f-128">[Utilisation des workflows](across-use-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="5af0f-128">[Using Workflows](across-use-workflows.md) </span></span>  
 [<span data-ttu-id="5af0f-129">Flux de travail</span><span class="sxs-lookup"><span data-stu-id="5af0f-129">Workflow</span></span>](across-workflow.md)   
