---
title: "Création des budgets des coûts | Microsoft Docs"
description: "Cette rubrique décrit l'emplacement où créer et analyser les budgets des coûts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: ab66e5b2404f512816d1a4fcb3b110a95265e1f7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="creating-cost-budgets"></a><span data-ttu-id="fcba7-103">Création des budgets des coûts</span><span class="sxs-lookup"><span data-stu-id="fcba7-103">Creating Cost Budgets</span></span>
<span data-ttu-id="fcba7-104">La budgétisation en comptabilité analytique ressemble à la budgétisation dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="fcba7-104">Budgeting in cost accounting resembles budgeting in the general ledger.</span></span> <span data-ttu-id="fcba7-105">Un budget de coûts est créé en fonction des types de coûts, tel qu'un budget est créé pour les écritures en fonction des comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="fcba7-105">A cost budget is created based on cost types just as a budget for the general ledger is created based on general ledger accounts.</span></span>  

<span data-ttu-id="fcba7-106">Un budget des coûts est créé pour une certaine période, par exemple, un exercice financier.</span><span class="sxs-lookup"><span data-stu-id="fcba7-106">A cost budget is created for a certain period of time, for example, a fiscal year.</span></span> <span data-ttu-id="fcba7-107">Vous pouvez créer autant de budgets de coûts que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="fcba7-107">You can create as many cost budgets as needed.</span></span> <span data-ttu-id="fcba7-108">Vous pouvez créer un budget de coûts manuellement, en important un budget de coûts ou en copiant un budget de coûts existant comme base budgétaire.</span><span class="sxs-lookup"><span data-stu-id="fcba7-108">You can create a new cost budget manually, or by importing a cost budget, or by copying an existing cost budget as the budget base.</span></span> <span data-ttu-id="fcba7-109">Pour plus d'informations, voir [Créer des budgets GL](finance-how-create-budgets.md).</span><span class="sxs-lookup"><span data-stu-id="fcba7-109">For more information, see [Create G/L Budgets](finance-how-create-budgets.md).</span></span>

<span data-ttu-id="fcba7-110">Vous utilisez les fenêtres suivantes pour créer et analyser les budgets de coûts.</span><span class="sxs-lookup"><span data-stu-id="fcba7-110">You use the following windows to create and analyze cost budgets.</span></span> <span data-ttu-id="fcba7-111">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche") pour rechercher une fenêtre, puis lisez chaque info-bulle correspondante.</span><span class="sxs-lookup"><span data-stu-id="fcba7-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon to find a window, and then read the tooltip for each.</span></span>

|<span data-ttu-id="fcba7-112">À</span><span class="sxs-lookup"><span data-stu-id="fcba7-112">To</span></span>|<span data-ttu-id="fcba7-113">Voir</span><span class="sxs-lookup"><span data-stu-id="fcba7-113">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="fcba7-114">Transférez des budgets à partir du grand livre.</span><span class="sxs-lookup"><span data-stu-id="fcba7-114">Transfer budgets from the general ledger.</span></span>|<span data-ttu-id="fcba7-115">Traitement en lot **Copier budget GL vers comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="fcba7-115">**Copy G-L Budget to Cost Acctg.** batch job</span></span>|  
|<span data-ttu-id="fcba7-116">Copiez le budget des coûts.</span><span class="sxs-lookup"><span data-stu-id="fcba7-116">Copy cost budgets.</span></span>|<span data-ttu-id="fcba7-117">Traitement en lot **Copier le budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="fcba7-117">**Copy Cost Budget** batch job</span></span>|  
|<span data-ttu-id="fcba7-118">Répartir les budgets.</span><span class="sxs-lookup"><span data-stu-id="fcba7-118">Allocate budgets.</span></span>|<span data-ttu-id="fcba7-119">Page **Affectation des coûts**</span><span class="sxs-lookup"><span data-stu-id="fcba7-119">**Cost Allocation** page</span></span>|  
|<span data-ttu-id="fcba7-120">Consultez les registres du budget des coûts et les écritures correspondantes.</span><span class="sxs-lookup"><span data-stu-id="fcba7-120">See cost budget registers and cost budget entries.</span></span>|<span data-ttu-id="fcba7-121">Page **Registres du budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="fcba7-121">**Cost Budget Registers** page</span></span>|  
|<span data-ttu-id="fcba7-122">Imprimez les comparaisons budgétaires de coûts à l'aide de divers états.</span><span class="sxs-lookup"><span data-stu-id="fcba7-122">Print cost budget comparisons using various reports.</span></span>|<span data-ttu-id="fcba7-123">Rapport **Budget/Solde comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="fcba7-123">**Cost Acctg. Balance-Budget** report</span></span><br /><br /> <span data-ttu-id="fcba7-124">Rapport **Budget/Relevé comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="fcba7-124">**Cost Acctg. Statement-Budget** report</span></span><br /><br /> <span data-ttu-id="fcba7-125">Rapport **Budget des coûts par centre de coûts**</span><span class="sxs-lookup"><span data-stu-id="fcba7-125">**Cost Budget by Cost Center** report</span></span><br /><br /> <span data-ttu-id="fcba7-126">Rapport **Budget des coûts par objet de coûts**</span><span class="sxs-lookup"><span data-stu-id="fcba7-126">**Cost Budget by Cost Object** report</span></span>|  

## <a name="see-also"></a><span data-ttu-id="fcba7-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fcba7-127">See Also</span></span>  
[<span data-ttu-id="fcba7-128">Comptabilité pour les coûts</span><span class="sxs-lookup"><span data-stu-id="fcba7-128">Accounting for Costs</span></span>](finance-manage-cost-accounting.md)  
[<span data-ttu-id="fcba7-129">Créer des budgets GL</span><span class="sxs-lookup"><span data-stu-id="fcba7-129">Create G/L Budgets</span></span>](finance-how-create-budgets.md)  
<span data-ttu-id="fcba7-130">[Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md) </span><span class="sxs-lookup"><span data-stu-id="fcba7-130">[Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md) </span></span>  
[<span data-ttu-id="fcba7-131">Définition et répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="fcba7-131">Defining and Allocating Costs</span></span>](finance-define-and-allocate-costs.md)  
<span data-ttu-id="fcba7-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="fcba7-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
