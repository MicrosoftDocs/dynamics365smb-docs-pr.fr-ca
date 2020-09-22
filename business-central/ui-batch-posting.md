---
title: Comment reporter plusieurs documents en même temps | Microsoft Docs
description: Au lieu de reporter des documents individuels un par un, vous pouvez sélectionner plusieurs documents non reportés dans une liste afin de les reporter en lot, soit pour un report immédiat, soit pour un report programmé, par exemple, à la fin de la journée.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 08/18/2020
ms.author: edupont
ms.openlocfilehash: 2c04dac37b043995a9b78e2f662f9411c3cf9ae1
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3782528"
---
# <a name="post-multiple-documents-at-the-same-time"></a><span data-ttu-id="42f92-103">Reporter plusieurs documents en même temps</span><span class="sxs-lookup"><span data-stu-id="42f92-103">Post Multiple Documents at the Same Time</span></span>

<span data-ttu-id="42f92-104">Au lieu de reporter des documents individuels un par un, vous pouvez sélectionner plusieurs documents non reportés dans une liste pour un report immédiat ou un report en lot, conformément à une programmation, à la fin de la journée, par exemple.</span><span class="sxs-lookup"><span data-stu-id="42f92-104">Instead of posting individual documents one by one, you can select multiple non-posted documents in a list for immediate posting or for batch posting according to a schedule, such as at the end of the day.</span></span> <span data-ttu-id="42f92-105">Cela peut être utile si seul un superviseur peut reporter des documents créés par d'autres utilisateurs ou pour éviter des problèmes de performance du système liés au report pendant les heures de travail.</span><span class="sxs-lookup"><span data-stu-id="42f92-105">This may be useful if only a supervisor can post documents created by other users or to avoid system performance issues from posting during work hours.</span></span>

## <a name="to-post-multiple-purchase-orders-immediately"></a><span data-ttu-id="42f92-106">Pour reporter plusieurs bons de commande immédiatement</span><span class="sxs-lookup"><span data-stu-id="42f92-106">To post multiple purchase orders immediately</span></span>

<span data-ttu-id="42f92-107">La procédure suivante explique comment reporter immédiatement plusieurs bons de commande.</span><span class="sxs-lookup"><span data-stu-id="42f92-107">The following procedure explains how to post multiple purchase orders immediately.</span></span> <span data-ttu-id="42f92-108">Les étapes sont similaires pour tous les documents achat et vente.</span><span class="sxs-lookup"><span data-stu-id="42f92-108">The steps are similar for all purchase and sales documents.</span></span>

1. <span data-ttu-id="42f92-109">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="42f92-109">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="42f92-110">Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :</span><span class="sxs-lookup"><span data-stu-id="42f92-110">On the **Purchase Orders** page, proceed to select all orders to be posted:</span></span>
3. <span data-ttu-id="42f92-111">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="42f92-111">In the **No.**</span></span> <span data-ttu-id="42f92-112">choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.</span><span class="sxs-lookup"><span data-stu-id="42f92-112">field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.</span></span>
4. <span data-ttu-id="42f92-113">Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.</span><span class="sxs-lookup"><span data-stu-id="42f92-113">Select the check box for all the lines representing orders that you want to post at the same time.</span></span>
5. <span data-ttu-id="42f92-114">Choisissez l'action **Report**, puis sélectionnez l'action **Reporter**.</span><span class="sxs-lookup"><span data-stu-id="42f92-114">Choose the **Posting** action, and then choose the **Post** action.</span></span>
6. <span data-ttu-id="42f92-115">Choisissez le bouton **Oui** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="42f92-115">Choose the **Yes** button on the confirmation message.</span></span>

## <a name="to-batch-post-multiple-purchase-orders"></a><span data-ttu-id="42f92-116">Pour exécuter en lot plusieurs bons de commande</span><span class="sxs-lookup"><span data-stu-id="42f92-116">To batch post multiple purchase orders</span></span>

<span data-ttu-id="42f92-117">La procédure suivante explique comment exécuter en lot plusieurs bons de commande.</span><span class="sxs-lookup"><span data-stu-id="42f92-117">The following procedure explains how to batch post purchase orders.</span></span> <span data-ttu-id="42f92-118">Les étapes sont similaires pour tous les documents achat et vente où l'action **Exécuter en lot** est disponible.</span><span class="sxs-lookup"><span data-stu-id="42f92-118">The steps are similar for all purchase and sales documents where the **Batch Post** action is available.</span></span>

> [!NOTE]
> <span data-ttu-id="42f92-119">Le report en lot de documents se produit en arrière-plan.</span><span class="sxs-lookup"><span data-stu-id="42f92-119">Batch posting of documents happens in the background.</span></span> <span data-ttu-id="42f92-120">[!INCLUDE [prodshort](includes/prodshort.md)] en ligne inclut les travaux par défaut pour le report en arrière-plan et le report en lot.</span><span class="sxs-lookup"><span data-stu-id="42f92-120">[!INCLUDE [prodshort](includes/prodshort.md)] online includes default jobs for background posting and batch posting.</span></span> <span data-ttu-id="42f92-121">Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="42f92-121">For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).</span></span>

1. <span data-ttu-id="42f92-122">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="42f92-122">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Purchase Orders**, and then choose the related link.</span></span>  
2. <span data-ttu-id="42f92-123">Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :</span><span class="sxs-lookup"><span data-stu-id="42f92-123">On the **Purchase Orders** page, proceed to select all orders to be posted:</span></span>
3. <span data-ttu-id="42f92-124">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="42f92-124">In the **No.**</span></span> <span data-ttu-id="42f92-125">choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.</span><span class="sxs-lookup"><span data-stu-id="42f92-125">field, choose the three vertical dots to open the context menu, and then choose the **Select More** action.</span></span>
4. <span data-ttu-id="42f92-126">Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.</span><span class="sxs-lookup"><span data-stu-id="42f92-126">Select the check box for all the lines representing orders that you want to post at the same time.</span></span>
5. <span data-ttu-id="42f92-127">Choisissez l'action **Report**, puis sélectionnez l'action **Reporter en lot**.</span><span class="sxs-lookup"><span data-stu-id="42f92-127">Choose the **Posting** action, and then choose the **Post Batch** action.</span></span>
6. <span data-ttu-id="42f92-128">Sur la page **Exécuter en lot les bons de commande**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="42f92-128">On the **Batch Post Purchase Order** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. <span data-ttu-id="42f92-129">Choisissez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="42f92-129">Choose the **OK** button.</span></span>
8. <span data-ttu-id="42f92-130">Pour afficher les problèmes potentiels survenus lors du report en lot de documents, ouvrez la page **Registre des messages d'erreur**.</span><span class="sxs-lookup"><span data-stu-id="42f92-130">To view potential issues that occurred during batch posting of documents, open the **Error Message Register** page.</span></span>

<span data-ttu-id="42f92-131">Les bons de commande seront désormais ajoutés à une entrée de file d'attente des travaux dédiée, qui définit le moment où les documents sont reportés.</span><span class="sxs-lookup"><span data-stu-id="42f92-131">The purchase orders will now be added to a dedicated job queue entry, which defines when the documents are posted.</span></span> <span data-ttu-id="42f92-132">Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).</span><span class="sxs-lookup"><span data-stu-id="42f92-132">For more information, see [Use Job Queues to Schedule Tasks](admin-job-queues-schedule-tasks.md).</span></span>

<span data-ttu-id="42f92-133">Si vous sélectionnez **PDF** dans le champ **Type sortie rapport**, les bons de commande reportés avec succès seront disponibles dans la partie **boîte de réception rapport** de votre tableau de bord.</span><span class="sxs-lookup"><span data-stu-id="42f92-133">If you select **PDF** in the **Report Output Type** field, successfully posted purchase orders will be available in the **Report Inbox** part on your Role Center.</span></span>

## <a name="see-also"></a><span data-ttu-id="42f92-134">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42f92-134">See Also</span></span>

[<span data-ttu-id="42f92-135">Validation des documents et des feuilles</span><span class="sxs-lookup"><span data-stu-id="42f92-135">Posting Documents and Journals</span></span>](ui-post-documents-journals.md)  
[<span data-ttu-id="42f92-136">Utiliser des files d'attente des travaux pour programmer des tâches</span><span class="sxs-lookup"><span data-stu-id="42f92-136">Use Job Queues to Schedule Tasks</span></span>](admin-job-queues-schedule-tasks.md)  
[<span data-ttu-id="42f92-137">Modifier les documents reportés</span><span class="sxs-lookup"><span data-stu-id="42f92-137">Edit Posted Documents</span></span>](across-edit-posted-document.md)  
[<span data-ttu-id="42f92-138">Corriger ou annuler des factures achat impayées</span><span class="sxs-lookup"><span data-stu-id="42f92-138">Correct or Cancel Unpaid Purchase Invoices</span></span>](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[<span data-ttu-id="42f92-139">Recherche de pages et d'informations avec Tell Me</span><span class="sxs-lookup"><span data-stu-id="42f92-139">Finding Pages and Information with Tell Me</span></span>](ui-search.md)  
<span data-ttu-id="42f92-140">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="42f92-140">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
