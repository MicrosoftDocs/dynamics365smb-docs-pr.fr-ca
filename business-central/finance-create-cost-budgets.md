---
title: Création des budgets des coûts | Microsoft Docs
description: Cette rubrique décrit l'emplacement où créer et analyser les budgets des coûts.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 2a8b8e88e296f36b8f4eb9bb41b05d5fc529b23b
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4750965"
---
# <a name="creating-cost-budgets"></a><span data-ttu-id="49c36-103">Création des budgets des coûts</span><span class="sxs-lookup"><span data-stu-id="49c36-103">Creating Cost Budgets</span></span>
<span data-ttu-id="49c36-104">La budgétisation en comptabilité analytique ressemble à la budgétisation dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="49c36-104">Budgeting in cost accounting resembles budgeting in the general ledger.</span></span> <span data-ttu-id="49c36-105">Un budget de coûts est créé en fonction des types de coûts, tel qu'un budget est créé pour les écritures en fonction des comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="49c36-105">A cost budget is created based on cost types just as a budget for the general ledger is created based on general ledger accounts.</span></span>  

<span data-ttu-id="49c36-106">Un budget des coûts est créé pour une certaine période, par exemple, un exercice financier.</span><span class="sxs-lookup"><span data-stu-id="49c36-106">A cost budget is created for a certain period of time, for example, a fiscal year.</span></span> <span data-ttu-id="49c36-107">Vous pouvez créer autant de budgets de coûts que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="49c36-107">You can create as many cost budgets as needed.</span></span> <span data-ttu-id="49c36-108">Vous pouvez créer un budget de coûts manuellement, en important un budget de coûts ou en copiant un budget de coûts existant comme base budgétaire.</span><span class="sxs-lookup"><span data-stu-id="49c36-108">You can create a new cost budget manually, or by importing a cost budget, or by copying an existing cost budget as the budget base.</span></span> <span data-ttu-id="49c36-109">Pour plus d'informations, voir [Créer des budgets GL](finance-how-create-budgets.md).</span><span class="sxs-lookup"><span data-stu-id="49c36-109">For more information, see [Create G/L Budgets](finance-how-create-budgets.md).</span></span>

<span data-ttu-id="49c36-110">Vous utilisez les pages suivantes pour créer et analyser les budgets de coûts.</span><span class="sxs-lookup"><span data-stu-id="49c36-110">You use the following pages to create and analyze cost budgets.</span></span> <span data-ttu-id="49c36-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") pour rechercher une page et lire l'info-bulle de chacune.</span><span class="sxs-lookup"><span data-stu-id="49c36-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon to find a page, and then read the tooltip for each.</span></span>

|<span data-ttu-id="49c36-112">Pour</span><span class="sxs-lookup"><span data-stu-id="49c36-112">To</span></span>|<span data-ttu-id="49c36-113">Voir</span><span class="sxs-lookup"><span data-stu-id="49c36-113">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="49c36-114">Transférez des budgets à partir du grand livre.</span><span class="sxs-lookup"><span data-stu-id="49c36-114">Transfer budgets from the general ledger.</span></span>|<span data-ttu-id="49c36-115">Traitement en lot **Copier budget GL vers comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="49c36-115">**Copy G-L Budget to Cost Acctg.** batch job</span></span>|  
|<span data-ttu-id="49c36-116">Copiez le budget des coûts.</span><span class="sxs-lookup"><span data-stu-id="49c36-116">Copy cost budgets.</span></span>|<span data-ttu-id="49c36-117">Traitement en lot **Copier le budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="49c36-117">**Copy Cost Budget** batch job</span></span>|  
|<span data-ttu-id="49c36-118">Répartir les budgets.</span><span class="sxs-lookup"><span data-stu-id="49c36-118">Allocate budgets.</span></span>|<span data-ttu-id="49c36-119">Page **Affectation des coûts**</span><span class="sxs-lookup"><span data-stu-id="49c36-119">**Cost Allocation** page</span></span>|  
|<span data-ttu-id="49c36-120">Consultez les registres du budget des coûts et les écritures correspondantes.</span><span class="sxs-lookup"><span data-stu-id="49c36-120">See cost budget registers and cost budget entries.</span></span>|<span data-ttu-id="49c36-121">Page **Registres du budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="49c36-121">**Cost Budget Registers** page</span></span>|  
|<span data-ttu-id="49c36-122">Imprimez les comparaisons budgétaires de coûts à l'aide de divers états.</span><span class="sxs-lookup"><span data-stu-id="49c36-122">Print cost budget comparisons using various reports.</span></span>|<span data-ttu-id="49c36-123">Rapport **Budget/Solde comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="49c36-123">**Cost Acctg. Balance-Budget** report</span></span><br /><br /> <span data-ttu-id="49c36-124">Rapport **Budget/Relevé comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="49c36-124">**Cost Acctg. Statement-Budget** report</span></span><br /><br /> <span data-ttu-id="49c36-125">Rapport **Budget des coûts par centre de coûts**</span><span class="sxs-lookup"><span data-stu-id="49c36-125">**Cost Budget by Cost Center** report</span></span><br /><br /> <span data-ttu-id="49c36-126">Rapport **Budget des coûts par objet de coûts**</span><span class="sxs-lookup"><span data-stu-id="49c36-126">**Cost Budget by Cost Object** report</span></span>|  

## <a name="see-also"></a><span data-ttu-id="49c36-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="49c36-127">See Also</span></span>  
[<span data-ttu-id="49c36-128">Comptabilité pour les coûts</span><span class="sxs-lookup"><span data-stu-id="49c36-128">Accounting for Costs</span></span>](finance-manage-cost-accounting.md)  
[<span data-ttu-id="49c36-129">Créer des budgets GL</span><span class="sxs-lookup"><span data-stu-id="49c36-129">Create G/L Budgets</span></span>](finance-how-create-budgets.md)  
<span data-ttu-id="49c36-130">[Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md) </span><span class="sxs-lookup"><span data-stu-id="49c36-130">[Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md) </span></span>  
[<span data-ttu-id="49c36-131">Définition et répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="49c36-131">Defining and Allocating Costs</span></span>](finance-define-and-allocate-costs.md)  
<span data-ttu-id="49c36-132">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="49c36-132">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>
