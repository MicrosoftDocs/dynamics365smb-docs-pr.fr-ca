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
ms.openlocfilehash: 9fceeeda18b846edd79b9fdc71ab1a22d80203bd
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3913356"
---
# <a name="creating-cost-budgets"></a><span data-ttu-id="f265b-103">Création des budgets des coûts</span><span class="sxs-lookup"><span data-stu-id="f265b-103">Creating Cost Budgets</span></span>
<span data-ttu-id="f265b-104">La budgétisation en comptabilité analytique ressemble à la budgétisation dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="f265b-104">Budgeting in cost accounting resembles budgeting in the general ledger.</span></span> <span data-ttu-id="f265b-105">Un budget de coûts est créé en fonction des types de coûts, tel qu'un budget est créé pour les écritures en fonction des comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="f265b-105">A cost budget is created based on cost types just as a budget for the general ledger is created based on general ledger accounts.</span></span>  

<span data-ttu-id="f265b-106">Un budget des coûts est créé pour une certaine période, par exemple, un exercice financier.</span><span class="sxs-lookup"><span data-stu-id="f265b-106">A cost budget is created for a certain period of time, for example, a fiscal year.</span></span> <span data-ttu-id="f265b-107">Vous pouvez créer autant de budgets de coûts que vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="f265b-107">You can create as many cost budgets as needed.</span></span> <span data-ttu-id="f265b-108">Vous pouvez créer un budget de coûts manuellement, en important un budget de coûts ou en copiant un budget de coûts existant comme base budgétaire.</span><span class="sxs-lookup"><span data-stu-id="f265b-108">You can create a new cost budget manually, or by importing a cost budget, or by copying an existing cost budget as the budget base.</span></span> <span data-ttu-id="f265b-109">Pour plus d'informations, voir [Créer des budgets GL](finance-how-create-budgets.md).</span><span class="sxs-lookup"><span data-stu-id="f265b-109">For more information, see [Create G/L Budgets](finance-how-create-budgets.md).</span></span>

<span data-ttu-id="f265b-110">Vous utilisez les pages suivantes pour créer et analyser les budgets de coûts.</span><span class="sxs-lookup"><span data-stu-id="f265b-110">You use the following pages to create and analyze cost budgets.</span></span> <span data-ttu-id="f265b-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") pour rechercher une page et lire l'info-bulle de chacune.</span><span class="sxs-lookup"><span data-stu-id="f265b-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon to find a page, and then read the tooltip for each.</span></span>

|<span data-ttu-id="f265b-112">Pour</span><span class="sxs-lookup"><span data-stu-id="f265b-112">To</span></span>|<span data-ttu-id="f265b-113">Voir</span><span class="sxs-lookup"><span data-stu-id="f265b-113">See</span></span>|  
|--------|---------|  
|<span data-ttu-id="f265b-114">Transférez des budgets à partir du grand livre.</span><span class="sxs-lookup"><span data-stu-id="f265b-114">Transfer budgets from the general ledger.</span></span>|<span data-ttu-id="f265b-115">Traitement en lot **Copier budget GL vers comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="f265b-115">**Copy G-L Budget to Cost Acctg.** batch job</span></span>|  
|<span data-ttu-id="f265b-116">Copiez le budget des coûts.</span><span class="sxs-lookup"><span data-stu-id="f265b-116">Copy cost budgets.</span></span>|<span data-ttu-id="f265b-117">Traitement en lot **Copier le budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="f265b-117">**Copy Cost Budget** batch job</span></span>|  
|<span data-ttu-id="f265b-118">Répartir les budgets.</span><span class="sxs-lookup"><span data-stu-id="f265b-118">Allocate budgets.</span></span>|<span data-ttu-id="f265b-119">Page **Affectation des coûts**</span><span class="sxs-lookup"><span data-stu-id="f265b-119">**Cost Allocation** page</span></span>|  
|<span data-ttu-id="f265b-120">Consultez les registres du budget des coûts et les écritures correspondantes.</span><span class="sxs-lookup"><span data-stu-id="f265b-120">See cost budget registers and cost budget entries.</span></span>|<span data-ttu-id="f265b-121">Page **Registres du budget des coûts**</span><span class="sxs-lookup"><span data-stu-id="f265b-121">**Cost Budget Registers** page</span></span>|  
|<span data-ttu-id="f265b-122">Imprimez les comparaisons budgétaires de coûts à l'aide de divers états.</span><span class="sxs-lookup"><span data-stu-id="f265b-122">Print cost budget comparisons using various reports.</span></span>|<span data-ttu-id="f265b-123">Rapport **Budget/Solde comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="f265b-123">**Cost Acctg. Balance-Budget** report</span></span><br /><br /> <span data-ttu-id="f265b-124">Rapport **Budget/Relevé comptabilité analytique**</span><span class="sxs-lookup"><span data-stu-id="f265b-124">**Cost Acctg. Statement-Budget** report</span></span><br /><br /> <span data-ttu-id="f265b-125">Rapport **Budget des coûts par centre de coûts**</span><span class="sxs-lookup"><span data-stu-id="f265b-125">**Cost Budget by Cost Center** report</span></span><br /><br /> <span data-ttu-id="f265b-126">Rapport **Budget des coûts par objet de coûts**</span><span class="sxs-lookup"><span data-stu-id="f265b-126">**Cost Budget by Cost Object** report</span></span>|  

## <a name="see-also"></a><span data-ttu-id="f265b-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f265b-127">See Also</span></span>  
[<span data-ttu-id="f265b-128">Comptabilité pour les coûts</span><span class="sxs-lookup"><span data-stu-id="f265b-128">Accounting for Costs</span></span>](finance-manage-cost-accounting.md)  
[<span data-ttu-id="f265b-129">Créer des budgets GL</span><span class="sxs-lookup"><span data-stu-id="f265b-129">Create G/L Budgets</span></span>](finance-how-create-budgets.md)  
<span data-ttu-id="f265b-130">[Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md) </span><span class="sxs-lookup"><span data-stu-id="f265b-130">[Terminology in Cost Accounting](finance-terminology-in-cost-accounting.md) </span></span>  
[<span data-ttu-id="f265b-131">Définition et répartition des coûts</span><span class="sxs-lookup"><span data-stu-id="f265b-131">Defining and Allocating Costs</span></span>](finance-define-and-allocate-costs.md)  
<span data-ttu-id="f265b-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f265b-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
