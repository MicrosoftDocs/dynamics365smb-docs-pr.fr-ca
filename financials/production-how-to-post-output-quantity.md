---
title: "Procédure : exécuter en lot la sortie de production et les temps d'exécution | Microsoft Docs"
description: "La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: e885149e28c2e09dc244bc5c0a431e7b2fe047a5
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="batch-post-output-and-run-times"></a><span data-ttu-id="4e93a-103">Exécuter en lot la production et les temps d'exécution</span><span class="sxs-lookup"><span data-stu-id="4e93a-103">Batch Post Output and Run Times</span></span>
<span data-ttu-id="4e93a-104">La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.</span><span class="sxs-lookup"><span data-stu-id="4e93a-104">The output quantity represents the work progress in the form of the finished quantity.</span></span>  

> [!NOTE]
> <span data-ttu-id="4e93a-105">L'inventaire est automatiquement mis à jour uniquement lorsque vous reportez la quantité sortie durant la dernière opération.</span><span class="sxs-lookup"><span data-stu-id="4e93a-105">Only when you post output quantity on the last operation, the inventory is updated automatically.</span></span>  

## <a name="to-post-output-quantities-for-one-or-more-production-order-lines"></a><span data-ttu-id="4e93a-106">Pour reporter les quantités sorties pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="4e93a-106">To post output quantities for one or more production order lines</span></span>
1. <span data-ttu-id="4e93a-107">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="4e93a-107">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="4e93a-108">Renseignez les champs en indiquant les données relatives à la fabrication et à la production.</span><span class="sxs-lookup"><span data-stu-id="4e93a-108">Fill in the fields with the production order data and the output data.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="4e93a-109">Si l'opération est achevée, sélectionnez le champ **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="4e93a-109">If the operation has been completed, select the **Finished** field.</span></span>  

    <span data-ttu-id="4e93a-110">Si l'emplacement entrepôt dans lequel les articles doivent être rangés utilise des zones mais n'exige pas le traitement des rangements, affectez un code de zone à la ligne journal pour indiquer l'endroit où les articles doivent être placés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="4e93a-110">If the warehouse location where the items should be put away uses bins but does not require put-away processing,  assign a bin code to the journal line to specify where the items should be placed in the warehouse.</span></span> <span data-ttu-id="4e93a-111">Pour plus d'informations, voir [Rangement du résultat de fabrication ou d'assemblage](warehouse-how-to-put-away-production-output.md).</span><span class="sxs-lookup"><span data-stu-id="4e93a-111">For more information, see [Put Away Production or Assembly Output](warehouse-how-to-put-away-production-output.md).</span></span>  

4. <span data-ttu-id="4e93a-112">Choisissez l'action **Reporter** pour reporter les opérations.</span><span class="sxs-lookup"><span data-stu-id="4e93a-112">Choose the **Post** acto post the operations.</span></span> <span data-ttu-id="4e93a-113">La quantité produite est reportée.</span><span class="sxs-lookup"><span data-stu-id="4e93a-113">The output quantity will be posted.</span></span> <span data-ttu-id="4e93a-114">L'article peut être livré.</span><span class="sxs-lookup"><span data-stu-id="4e93a-114">The item is now available for shipping.</span></span>  

## <a name="to-post-run-times-for-one-or-more-production-order-lines"></a><span data-ttu-id="4e93a-115">Pour reporter les temps d'exécution pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="4e93a-115">To post run times for one or more production order lines</span></span>
<span data-ttu-id="4e93a-116">Le temps d'exécution représente l'avancement des travaux en prenant en compte le temps de travail nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4e93a-116">The run time represents work progress in the form of the necessary working time.</span></span>    

1.  <span data-ttu-id="4e93a-117">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="4e93a-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Output Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="4e93a-118">Renseignez les champs en indiquant les données relatives à la fabrication et à la production.</span><span class="sxs-lookup"><span data-stu-id="4e93a-118">Fill in the fields with the production order data and the output data.</span></span>  
3.  <span data-ttu-id="4e93a-119">Si l'opération est achevée, sélectionnez le champ **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="4e93a-119">If the operation is completed, select the **Finished** field.</span></span>  
4. <span data-ttu-id="4e93a-120">Choisissez l'action **Reporter** pour reporter le temps passé par opération.</span><span class="sxs-lookup"><span data-stu-id="4e93a-120">Choose the **Post** action to post the time spent per operation.</span></span> <span data-ttu-id="4e93a-121">Les écritures du grand livre de capacité sont mises à jour pour les unités de production ou les ateliers utilisés.</span><span class="sxs-lookup"><span data-stu-id="4e93a-121">Capacity ledger entries are updated for the used work or machine centers.</span></span>

## <a name="see-also"></a><span data-ttu-id="4e93a-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4e93a-122">See Also</span></span>  
<span data-ttu-id="4e93a-123">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="4e93a-123">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="4e93a-124">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="4e93a-124">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="4e93a-125">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="4e93a-125">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="4e93a-126">Stock</span><span class="sxs-lookup"><span data-stu-id="4e93a-126">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="4e93a-127">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="4e93a-127">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="4e93a-128">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="4e93a-128">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

