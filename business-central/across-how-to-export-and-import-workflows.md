---
title: "Procédure : exporter et importer des flux de travail | Microsoft Docs"
description: "Pour transférer des workflows vers d'autres bases de données Business Central, par exemple pour gagner du temps lors de la création de workflows, vous pouvez exporter et importer des workflows."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 579a2ab10eefd5e706dfa5f686702ac780764578
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="export-and-import-workflows"></a><span data-ttu-id="8100e-103">Exporter et importer des workflows</span><span class="sxs-lookup"><span data-stu-id="8100e-103">Export and Import Workflows</span></span>
<span data-ttu-id="8100e-104">Pour transférer des workflows vers d'autres bases de données [!INCLUDE[d365fin](includes/d365fin_md.md)], par exemple pour gagner du temps lors de la création de workflows, vous pouvez exporter et importer des workflows.</span><span class="sxs-lookup"><span data-stu-id="8100e-104">To transfer workflows to other [!INCLUDE[d365fin](includes/d365fin_md.md)] databases, for example to save time when creating new workflows, you can export and import workflows.</span></span>  

 <span data-ttu-id="8100e-105">Un autre moyen rapide de créer des workflows consiste à les créer à partir de modèles de workflow.</span><span class="sxs-lookup"><span data-stu-id="8100e-105">Another way to quickly create workflows is to create workflows from workflow templates.</span></span> <span data-ttu-id="8100e-106">Pour plus d'informations, reportez-vous à la rubrique [Créer des flux de travail à partir de modèles de flux de travail](across-how-to-create-workflows-from-workflow-templates.md).</span><span class="sxs-lookup"><span data-stu-id="8100e-106">For more information, see [Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md).</span></span>  

 <span data-ttu-id="8100e-107">Dans la fenêtre **Workflow**, créez un workflow en répertoriant les étapes concernées sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="8100e-107">In the **Workflow** window, you create a workflow by listing the involved steps on the lines.</span></span> <span data-ttu-id="8100e-108">Chaque étape comprend un événement de workflow modéré par des conditions d'événement, et une réponse de workflow modérée par des options de réponse.</span><span class="sxs-lookup"><span data-stu-id="8100e-108">Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options.</span></span> <span data-ttu-id="8100e-109">Définissez les phases de workflow en renseignez les champs des lignes de workflow à partir de listes fixes de valeurs d'événement et de réponse qui sont les scénarios pris en charge par le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="8100e-109">You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.</span></span> <span data-ttu-id="8100e-110">Pour plus d'informations, voir [Créer des flux de travail](across-how-to-create-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="8100e-110">For more information, see [Create Workflows](across-how-to-create-workflows.md).</span></span>  

## <a name="to-export-a-workflow"></a><span data-ttu-id="8100e-111">Pour exporter un workflow</span><span class="sxs-lookup"><span data-stu-id="8100e-111">To export a workflow</span></span>  
1.  <span data-ttu-id="8100e-112">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Flux de travail**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8100e-112">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="8100e-113">Sélectionnez un flux de travail, puis sélectionnez l'action **Exporter vers un fichier**.</span><span class="sxs-lookup"><span data-stu-id="8100e-113">Select a workflow, and then choose the **Export to File** action.</span></span>  
3.  <span data-ttu-id="8100e-114">Dans la fenêtre **Exporter fichier**, cliquez sur le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8100e-114">In the **Export File** window, choose the **Save** button.</span></span>  
4.  <span data-ttu-id="8100e-115">Dans la fenêtre **Exporter**, sélectionnez un emplacement de fichier, puis choisissez le bouton **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="8100e-115">In the **Export** window, select a file location, and then choose the **Save** button.</span></span>  

## <a name="to-import-a-workflow"></a><span data-ttu-id="8100e-116">Pour importer un workflow</span><span class="sxs-lookup"><span data-stu-id="8100e-116">To import a workflow</span></span>  
1.  <span data-ttu-id="8100e-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Flux de travail**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8100e-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Workflows**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="8100e-118">Choisissez l'action **Importer à partir d'un fichier**.</span><span class="sxs-lookup"><span data-stu-id="8100e-118">Choose the **Import from File** action.</span></span>  
3.  <span data-ttu-id="8100e-119">Dans la fenêtre **Importer**, sélectionnez le fichier XML contenant le workflow, puis choisissez le bouton **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="8100e-119">In the **Import** window, choose the XML file that contains the workflow, and then choose the **Open** button.</span></span>  

> [!CAUTION]  
>  <span data-ttu-id="8100e-120">Si le code du workflow existe déjà dans la base de données, les étapes du workflow sont remplacées avec celles du workflow importé.</span><span class="sxs-lookup"><span data-stu-id="8100e-120">If the workflow code already exists in the database, the workflow steps will be overwritten with the steps in the imported workflow.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8100e-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8100e-121">See Also</span></span>  
 <span data-ttu-id="8100e-122">[Créer des workflows](across-how-to-create-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-122">[Create Workflows](across-how-to-create-workflows.md) </span></span>  
 <span data-ttu-id="8100e-123">[Créer des flux de travail à partir de modèles de flux de travail](across-how-to-create-workflows-from-workflow-templates.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-123">[Create Workflows from Workflow Templates](across-how-to-create-workflows-from-workflow-templates.md) </span></span>  
 <span data-ttu-id="8100e-124">[Afficher des instances d'étape de workflow archivées](across-how-to-view-archived-workflow-step-instances.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-124">[View Archived Workflow Step Instances](across-how-to-view-archived-workflow-step-instances.md) </span></span>  
 <span data-ttu-id="8100e-125">[Supprimer des workflows](across-how-to-delete-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-125">[Delete Workflows](across-how-to-delete-workflows.md) </span></span>  
 <span data-ttu-id="8100e-126">[Procédure pas à pas : Configuration et utilisation d'un flux d'approbation achat](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-126">[Walkthrough: Setting Up and Using a Purchase Approval Workflow](walkthrough-setting-up-and-using-a-purchase-approval-workflow.md) </span></span>  
 <span data-ttu-id="8100e-127">[Paramétrage des workflows](across-set-up-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-127">[Setting Up Workflows](across-set-up-workflows.md) </span></span>  
 <span data-ttu-id="8100e-128">[Utilisation des workflows](across-use-workflows.md) </span><span class="sxs-lookup"><span data-stu-id="8100e-128">[Using Workflows](across-use-workflows.md) </span></span>  
 [<span data-ttu-id="8100e-129">Flux de travail</span><span class="sxs-lookup"><span data-stu-id="8100e-129">Workflow</span></span>](across-workflow.md)   

