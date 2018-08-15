---
title: "Création de budgets GL | Microsoft Docs"
description: "Décrit la création de budgets GL pour prévoir différentes activités financières et affecter des dimensions à des fins de veille économique."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: postpone
ms.date: 01/25/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: dd3be77519075b67a942402bd01d5a2a562a1c32
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-gl-budgets"></a><span data-ttu-id="f74af-103">Créer des budgets GL</span><span class="sxs-lookup"><span data-stu-id="f74af-103">Create G/L Budgets</span></span>
<span data-ttu-id="f74af-104">Vous pouvez avoir plusieurs budgets pour des périodes identiques en les créant sous des noms différents.</span><span class="sxs-lookup"><span data-stu-id="f74af-104">You can have multiple budgets for identical time periods by creating budgets with separate names.</span></span> <span data-ttu-id="f74af-105">Vous indiquez d'abord le nom du budget et entrez les chiffres correspondants.</span><span class="sxs-lookup"><span data-stu-id="f74af-105">First, you set up the budget name and enter the budget figures.</span></span> <span data-ttu-id="f74af-106">Le nom du budget est ensuite inclus sur toutes les écritures budget que vous créez.</span><span class="sxs-lookup"><span data-stu-id="f74af-106">The budget name is then included on all the budget entries you create.</span></span>  

 <span data-ttu-id="f74af-107">Lorsque vous créez un budget, vous pouvez définir quatre axes analytiques par budget.</span><span class="sxs-lookup"><span data-stu-id="f74af-107">When you create a budget, you can define four dimensions for each budget.</span></span> <span data-ttu-id="f74af-108">Ces dimensions propres au budget sont appelées dimensions budget.</span><span class="sxs-lookup"><span data-stu-id="f74af-108">These budget-specific dimensions are called budget dimensions.</span></span> <span data-ttu-id="f74af-109">Vous sélectionnez les axes budget pour chaque budget parmi les axes analytiques que vous avez déjà configurés.</span><span class="sxs-lookup"><span data-stu-id="f74af-109">You select the budget dimensions for each budget from among the dimensions you have already set up.</span></span> <span data-ttu-id="f74af-110">Les dimensions budget peuvent être utilisées pour positionner des filtres sur un budget et pour ajouter des informations de dimensions aux écritures budget.</span><span class="sxs-lookup"><span data-stu-id="f74af-110">Budget dimensions can be used to set filters on a budget and to add dimension information to budget entries.</span></span> <span data-ttu-id="f74af-111">Pour plus d'informations, reportez-vous à [Utilisation des axes](finance-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="f74af-111">For more information, see [Working with Dimensions](finance-dimensions.md).</span></span>

 <span data-ttu-id="f74af-112">Les budgets jouent un rôle important dans la veille économique, par exemple dans les états financiers basés sur des tableaux d'analyse incluant des écritures budget ou lors de l'analyse des montants budgétés et des montants réels dans le plan comptable.</span><span class="sxs-lookup"><span data-stu-id="f74af-112">Budgets play an important role in business intelligence, such as in financial statement based on account schedules that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts.</span></span> <span data-ttu-id="f74af-113">Pour plus d'informations, reportez-vous à [Veille économique](bi.md).</span><span class="sxs-lookup"><span data-stu-id="f74af-113">For more information, see [Business Intelligence](bi.md).</span></span>

 <span data-ttu-id="f74af-114">Les budgets jouent un rôle important dans la veille économique, par exemple dans les états financiers basés sur des tableaux d'analyse incluant des écritures budget ou lors de l'analyse des montants budgétés et des montants réels dans le plan comptable.</span><span class="sxs-lookup"><span data-stu-id="f74af-114">Budgets play an important role in business intelligence, such as in financial statement based on account schedules that include budget entries or when analyzing budgeted versus actual amounts in the chart of accounts.</span></span> <span data-ttu-id="f74af-115">Pour plus d'informations, reportez-vous à [Veille économique](bi.md).</span><span class="sxs-lookup"><span data-stu-id="f74af-115">For more information, see [Business Intelligence](bi.md).</span></span>

<span data-ttu-id="f74af-116">En comptabilité analytique, vous travaillez avec des budgets de coûts de manière similaire.</span><span class="sxs-lookup"><span data-stu-id="f74af-116">In cost accounting, you work with cost budgets in a similar way.</span></span> <span data-ttu-id="f74af-117">Pour plus d'informations, voir [Procédure : Créer des budgets de coûts](finance-create-cost-budgets.md).</span><span class="sxs-lookup"><span data-stu-id="f74af-117">For more information, see [Creating Cost Budgets](finance-create-cost-budgets.md).</span></span>    

## <a name="to-create-a-new-gl-budget"></a><span data-ttu-id="f74af-118">Pour créer un budget GL</span><span class="sxs-lookup"><span data-stu-id="f74af-118">To create a new G/L budget</span></span>  
1. <span data-ttu-id="f74af-119">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Budgets**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f74af-119">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **G/L Budgets**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f74af-120">Cliquez sur **Modifier la liste**, puis renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f74af-120">Choose the **Edit List** action, and then fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. <span data-ttu-id="f74af-121">Sélectionnez **Modifier budget**.</span><span class="sxs-lookup"><span data-stu-id="f74af-121">Choose the **Edit Budget** action.</span></span>
4. <span data-ttu-id="f74af-122">En haut de la fenêtre **Budget**, renseignez les champs nécessaires pour définir ce qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="f74af-122">At the top of the **Budget** window, fill in the fields as necessary to define what is displayed.</span></span>  

    <span data-ttu-id="f74af-123">Seules les écritures contenant le nom du budget entré dans le champ **Nom budget** s'affichent.</span><span class="sxs-lookup"><span data-stu-id="f74af-123">Only entries that contain the budget name that you entered in the **budget Name** field are shown.</span></span> <span data-ttu-id="f74af-124">Étant donné que le nom du budget vient juste d'être créé, aucune écriture ne correspond au filtre.</span><span class="sxs-lookup"><span data-stu-id="f74af-124">Because the budget name has just been created, there are no entries that match the filter.</span></span> <span data-ttu-id="f74af-125">Par conséquent, la fenêtre est vide.</span><span class="sxs-lookup"><span data-stu-id="f74af-125">Therefore, the window is empty.</span></span>  
5. <span data-ttu-id="f74af-126">Pour entrer un montant, choisissez la cellule appropriée de la matrice.</span><span class="sxs-lookup"><span data-stu-id="f74af-126">To enter an amount, choose the relevant cell in the matrix.</span></span> <span data-ttu-id="f74af-127">La fenêtre **Écritures budget** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="f74af-127">The **G/L Budget Entries** window opens.</span></span>  
6. <span data-ttu-id="f74af-128">Créez une ligne et renseignez le champ **Montant**.</span><span class="sxs-lookup"><span data-stu-id="f74af-128">Create a new line and fill in the **Amount** field.</span></span> <span data-ttu-id="f74af-129">Fermez la fenêtre **Écritures budget**.</span><span class="sxs-lookup"><span data-stu-id="f74af-129">Close the **G/L Budget Entries** window.</span></span>  
7. <span data-ttu-id="f74af-130">Répétez les étapes 5 et 6 jusqu'à ce que vous ayez entré tous les montant du budget.</span><span class="sxs-lookup"><span data-stu-id="f74af-130">Repeat steps 5 and 6 until you have entered all of the budget amounts.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f74af-131">Sur le raccourci **Filtres**, vous pouvez filtrer les informations sur le budget selon le nombre d'axes budget configurés sous le nom du budget.</span><span class="sxs-lookup"><span data-stu-id="f74af-131">On the **Filters** FastTab, you can filter the budget information by budget dimensions you have set up under the budget name.</span></span>   

## <a name="see-also"></a><span data-ttu-id="f74af-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f74af-132">See Also</span></span>
[<span data-ttu-id="f74af-133">Finances</span><span class="sxs-lookup"><span data-stu-id="f74af-133">Finance</span></span>](finance.md)  
[<span data-ttu-id="f74af-134">Veille économique</span><span class="sxs-lookup"><span data-stu-id="f74af-134">Business Intelligence</span></span>](bi.md)  
[<span data-ttu-id="f74af-135">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="f74af-135">Setting Up Finance</span></span>](finance-setup-finance.md)  
[<span data-ttu-id="f74af-136">Les écritures comptables et le plan comptable</span><span class="sxs-lookup"><span data-stu-id="f74af-136">The General Ledger and the Chart of Accounts</span></span>](finance-general-ledger.md)  
<span data-ttu-id="f74af-137">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f74af-137">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
