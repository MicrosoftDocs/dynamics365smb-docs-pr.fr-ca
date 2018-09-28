---
title: Workflow | Microsoft Docs
description: "Vous pouvez configurer et utiliser des workflows qui connectent des tâches de processus entreprise exécutées par différents utilisateurs. Les tâches système, telles que le report automatique, peuvent être incluses comme étapes du flux de travail, précédées ou suivies des tâches de l'utilisateur. Demander et accorder une approbation pour créer des enregistrements sont des étapes classiques du workflow."
services: project-madeira
documentationcenter: 
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
ms.openlocfilehash: 7a7782fcb51eb9078cb62c4892814cd178518332
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="workflow"></a><span data-ttu-id="5bbc8-105">Flux de travail</span><span class="sxs-lookup"><span data-stu-id="5bbc8-105">Workflow</span></span>
<span data-ttu-id="5bbc8-106">Vous pouvez configurer et utiliser des workflows qui connectent des tâches de processus entreprise exécutées par différents utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-106">You can set up and use workflows that connect business-process tasks performed by different users.</span></span> <span data-ttu-id="5bbc8-107">Les tâches système, telles que le report automatique, peuvent être incluses comme étapes du flux de travail, précédées ou suivies des tâches de l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-107">System tasks, such as automatic posting, can be included as steps in workflows, preceded or followed by user tasks.</span></span> <span data-ttu-id="5bbc8-108">Demander et accorder une approbation pour créer des enregistrements sont des étapes classiques du workflow.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-108">Requesting and granting approval to create new records are typical workflow steps.</span></span>  

 <span data-ttu-id="5bbc8-109">Dans la fenêtre **Workflow**, créez un workflow en répertoriant les étapes concernées sur les lignes.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-109">In the **Workflow** window, you create a workflow by listing the involved steps on the lines.</span></span> <span data-ttu-id="5bbc8-110">Chaque étape comprend un événement de workflow modéré par des conditions d'événement, et une réponse de workflow modérée par des options de réponse.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-110">Each step consists of a workflow event, moderated by event conditions, and a workflow response, moderated by response options.</span></span> <span data-ttu-id="5bbc8-111">Définissez les phases de workflow en renseignez les champs des lignes de workflow à partir de listes fixes de valeurs d'événement et de réponse qui sont les scénarios pris en charge par le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-111">You define workflow steps by filling fields on workflow lines from fixed lists of event and response values representing scenarios that are supported by the application code.</span></span>  

 <span data-ttu-id="5bbc8-112">La version générique de [!INCLUDE[d365fin](includes/d365fin_md.md)] inclut plusieurs workflows préconfigurés, représentés par des modèles de workflow que vous pouvez copier pour créer des workflows.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-112">The generic version of [!INCLUDE[d365fin](includes/d365fin_md.md)] includes a number of preconfigured workflows represented by workflow templates that you can copy to create workflows.</span></span> <span data-ttu-id="5bbc8-113">Le code des modèles de workflow ajoutés par Microsoft a le préfixe « MS- ».</span><span class="sxs-lookup"><span data-stu-id="5bbc8-113">The code for workflow templates that are added by Microsoft are prefixed with “MS-“.</span></span> <span data-ttu-id="5bbc8-114">Pour plus d'informations, voir la liste des modèles de workflow dans la fenêtre Modèles flux de travail.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-114">For more information, see the list of workflow templates in the Workflow Templates window.</span></span>  

 <span data-ttu-id="5bbc8-115">Si un scénario d'entreprise requiert un événement ou une réponse de workflow non pris en charge, un partenaire Microsoft doit l'implémenter en personnalisant le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-115">If a business scenario requires a workflow event or response that is not supported, a Microsoft partner must implement them by customizing the application code.</span></span> <span data-ttu-id="5bbc8-116">Pour plus d'informations, voir [Procédure pas à pas : implémentation de nouveaux événements et réponses de flux de travail](/dynamics-nav/Walkthrough--Implementing-New-Workflow-Events-and-Responses) dans l'Aide destinée aux développeurs et aux professionnels de l'informatique.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-116">For more information, see [Walkthrough: Implementing New Workflow Events and Responses](/dynamics-nav/Walkthrough--Implementing-New-Workflow-Events-and-Responses) in the developer and IT-pro help.</span></span>

> [!NOTE]  
> <span data-ttu-id="5bbc8-117">Les flux de travail peuvent également être lancés à partir de Microsoft Flow.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-117">Workflows can also be initiated from Microsoft Flow.</span></span> <span data-ttu-id="5bbc8-118">Pour plus d'informations, voir [Utilisation de Business Central dans un flux automatisé](across-how-use-financials-data-source-flow.md).</span><span class="sxs-lookup"><span data-stu-id="5bbc8-118">For more information, see [Using Business Central in an Automated Workflow](across-how-use-financials-data-source-flow.md).</span></span>  

 <span data-ttu-id="5bbc8-119">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-119">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>  

|<span data-ttu-id="5bbc8-120">**Pour**</span><span class="sxs-lookup"><span data-stu-id="5bbc8-120">**To**</span></span>|<span data-ttu-id="5bbc8-121">**Voir**</span><span class="sxs-lookup"><span data-stu-id="5bbc8-121">**See**</span></span>|  
|------------|-------------|  
|<span data-ttu-id="5bbc8-122">Configurer des utilisateurs du workflow, spécifier comment les utilisateurs sont notifiés et créer des workflows.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-122">Set up workflow users, specify how users get notified, and create new workflows.</span></span> <span data-ttu-id="5bbc8-123">Pour de nouveaux flux de travail pour des scénarios non pris en charge, implémentez les éléments requis du flux de travail en personnalisant le code de l'application.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-123">For new workflows for unsupported scenarios, implement the required workflow elements by customizing the application code.</span></span>|[<span data-ttu-id="5bbc8-124">Paramétrage des workflows</span><span class="sxs-lookup"><span data-stu-id="5bbc8-124">Setting Up Workflows</span></span>](across-set-up-workflows.md)|  
|<span data-ttu-id="5bbc8-125">Activer des workflows, agir sur les notifications du workflow, notamment les approbations de demandes et approuver des demandes pour effectuer une étape du workflow.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-125">Enable workflows, act on workflow notifications, including request approvals and approve requests to perform a workflow step.</span></span> <span data-ttu-id="5bbc8-126">Archiver et supprimer des workflows.</span><span class="sxs-lookup"><span data-stu-id="5bbc8-126">Archive and delete workflows.</span></span>|[<span data-ttu-id="5bbc8-127">Utilisation des workflows</span><span class="sxs-lookup"><span data-stu-id="5bbc8-127">Using Workflows</span></span>](across-use-workflows.md)|  

## <a name="see-also"></a><span data-ttu-id="5bbc8-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5bbc8-128">See Also</span></span>  
[<span data-ttu-id="5bbc8-129">Vente</span><span class="sxs-lookup"><span data-stu-id="5bbc8-129">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="5bbc8-130">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="5bbc8-130">Purchasing</span></span>](purchasing-manage-purchasing.md)  
[<span data-ttu-id="5bbc8-131">Gestion des projets</span><span class="sxs-lookup"><span data-stu-id="5bbc8-131">Managing Projects</span></span>](projects-manage-projects.md)  
<span data-ttu-id="5bbc8-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="5bbc8-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

