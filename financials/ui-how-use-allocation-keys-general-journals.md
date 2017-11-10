---
title: "Procédure : utiliser les clés de ventilation dans les feuilles comptabilité | Microsoft Docs"
description: "En savoir plus sur l'utilisation des clés de ventilation dans les feuilles."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cost accounting
ms.date: 03/29/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: bbacf9b5634d51478dd4d54ac4b587ea9bfaaf99
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-use-allocation-keys-in-general-journals"></a><span data-ttu-id="950f5-103">Comment utiliser les clés de ventilation dans les feuilles de comptabilité</span><span class="sxs-lookup"><span data-stu-id="950f5-103">How to: Use Allocation Keys in General Journals</span></span>
<span data-ttu-id="950f5-104">Vous pouvez ventiler une écriture dans un journal général dans différents comptes lorsque vous reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="950f5-104">You can allocate an entry in a general journal to several different accounts when you post the journal.</span></span> <span data-ttu-id="950f5-105">L'affectation peut être effectuée par quantité, pourcentage ou montant.</span><span class="sxs-lookup"><span data-stu-id="950f5-105">The allocation can be made by quantity, percentage, or amount.</span></span>

## <a name="to-set-up-allocation-keys"></a><span data-ttu-id="950f5-106">Pour définir des clés de ventilation</span><span class="sxs-lookup"><span data-stu-id="950f5-106">To set up allocation keys</span></span>
1. <span data-ttu-id="950f5-107">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille abonnement**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="950f5-107">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Recurring General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="950f5-108">Sélectionnez le champ **Nom de la feuille** pour ouvrir la fenêtre **Noms feuilles comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="950f5-108">Choose the **Batch Name** field to open the **General Journal Batches** window.</span></span>
3. <span data-ttu-id="950f5-109">Vous pouvez soit modifier les ventilations sur un lot existant dans la liste ou créer un lot avec des ventilations.</span><span class="sxs-lookup"><span data-stu-id="950f5-109">You can either modify allocations on an existing batch in the list or create a new batch with allocations.</span></span>
   * <span data-ttu-id="950f5-110">Pour créer un lot, sélectionnez l'action **Nouveau**, et passez à l'étape suivante.</span><span class="sxs-lookup"><span data-stu-id="950f5-110">To create a new batch, choose the **New** action, and go to the next step.</span></span>
   * <span data-ttu-id="950f5-111">Pour modifier les affectations à partir d'un journal existant, sélectionnez le journal et passez à l'étape 7.</span><span class="sxs-lookup"><span data-stu-id="950f5-111">To change the allocations of an existing journal, select the journal and go to step 7.</span></span>    
4. <span data-ttu-id="950f5-112">Dans le champ **Nom**, saisissez le nom du lot, par exemple NETTOYAGE.</span><span class="sxs-lookup"><span data-stu-id="950f5-112">In the **Name** field, enter a name for the batch, such as CLEANING.</span></span> <span data-ttu-id="950f5-113">Dans le champ **Description**, saisissez une description, par exemple Feuille frais de nettoyage.</span><span class="sxs-lookup"><span data-stu-id="950f5-113">In the **Description** field, enter a description, such as Cleaning Expenses Journal.</span></span>
5. <span data-ttu-id="950f5-114">Fermez la fenêtre lorsque vous avez terminé.</span><span class="sxs-lookup"><span data-stu-id="950f5-114">When you are done, close the window.</span></span> <span data-ttu-id="950f5-115">Un nouveau journal récurrent vide s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="950f5-115">A new, empty recurring journal opens.</span></span>
6. <span data-ttu-id="950f5-116">Renseignez les champs de la ligne.</span><span class="sxs-lookup"><span data-stu-id="950f5-116">Fill in the fields on the line.</span></span>
7. <span data-ttu-id="950f5-117">Sélectionnez l'action **Ventilations**.</span><span class="sxs-lookup"><span data-stu-id="950f5-117">Choose the **Allocations** action.</span></span>
8. <span data-ttu-id="950f5-118">Ajoutez une ligne pour chaque affectation.</span><span class="sxs-lookup"><span data-stu-id="950f5-118">Add a line for each allocation.</span></span> <span data-ttu-id="950f5-119">Vous devez renseigner le champ **% ventilation**, **Quantité imputée** ou **Montant**.</span><span class="sxs-lookup"><span data-stu-id="950f5-119">You must fill in either the **Allocation %**, **Allocation Quantity**, or **Amount** field.</span></span> <span data-ttu-id="950f5-120">Vous devez également renseigner le champ **N° compte** et, si vous affectez la transaction à des dimensions principales, les champs de ces dimensions principales.</span><span class="sxs-lookup"><span data-stu-id="950f5-120">You must also fill in the **Account No.** field and, if you are allocating the transaction among global dimensions, the global dimension fields.</span></span>
9. <span data-ttu-id="950f5-121">Si vous saisissez un pourcentage dans une ligne, le montant du champ **Montant** est calculé automatiquement.</span><span class="sxs-lookup"><span data-stu-id="950f5-121">If you enter a percentage on a line, the amount in the **Amount** field is calculated automatically.</span></span> <span data-ttu-id="950f5-122">Ces montants sont dotés du signe opposé à celui du montant total figurant dans le champ **Montant** de la feuille récurrente.</span><span class="sxs-lookup"><span data-stu-id="950f5-122">These amounts have the opposite sign from the total amount in the **Amount** field in the recurring journal.</span></span>
10. <span data-ttu-id="950f5-123">Après avoir saisi les lignes de ventilation, cliquez sur **OK** pour revenir à la fenêtre **Feuille abonnement**.</span><span class="sxs-lookup"><span data-stu-id="950f5-123">After entering the allocations lines, choose **OK** to return to the **Recurring General Journal** window.</span></span> <span data-ttu-id="950f5-124">Le champ **Montant imputé DS** est renseigné et correspond au champ **Montant**.</span><span class="sxs-lookup"><span data-stu-id="950f5-124">The **Allocated Amt. (USD)** field is filled in and matches the **Amount** field.</span></span>
11. <span data-ttu-id="950f5-125">Reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="950f5-125">Post the journal.</span></span>

## <a name="to-change-an-allocation-key-that-has-already-been-set-up"></a><span data-ttu-id="950f5-126">Pour modifier une clé d'affectation déjà configurée</span><span class="sxs-lookup"><span data-stu-id="950f5-126">To change an allocation key that has already been set up</span></span>
1. <span data-ttu-id="950f5-127">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille abonnement**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="950f5-127">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Recurring General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="950f5-128">Dans la fenêtre **Feuille récurrente**, sélectionnez la feuille contenant la ventilation.</span><span class="sxs-lookup"><span data-stu-id="950f5-128">In the **Recurring General Journal** window, select the journal with the allocation.</span></span>
3. <span data-ttu-id="950f5-129">Sélectionnez la ligne de la ventilation, puis sélectionnez l'action **Ventilations**.</span><span class="sxs-lookup"><span data-stu-id="950f5-129">Choose the line with the allocation, and then choose **Allocations** action.</span></span>
4. <span data-ttu-id="950f5-130">Modifiez les champs appropriés, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="950f5-130">Change the relevant fields, and then choose the **OK** button.</span></span>

## <a name="see-also"></a><span data-ttu-id="950f5-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="950f5-131">See Also</span></span>
[<span data-ttu-id="950f5-132">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="950f5-132">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="950f5-133">Validation des documents et des feuilles</span><span class="sxs-lookup"><span data-stu-id="950f5-133">Posting Documents and Journals</span></span>](ui-post-documents-journals.md)  
<span data-ttu-id="950f5-134">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="950f5-134">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
