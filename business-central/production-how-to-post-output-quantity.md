---
title: "Procédure : exécuter en lot la sortie de production et les temps d'exécution | Microsoft Docs"
description: La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 82e28246f1a1c65c7bd702023d9c68c614383cc2
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759152"
---
# <a name="batch-post-output-and-run-times"></a><span data-ttu-id="29b23-103">Exécuter en lot la production et les temps d'exécution</span><span class="sxs-lookup"><span data-stu-id="29b23-103">Batch Post Output and Run Times</span></span>
<span data-ttu-id="29b23-104">La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.</span><span class="sxs-lookup"><span data-stu-id="29b23-104">The output quantity represents the work progress in the form of the finished quantity.</span></span>  

> [!NOTE]
> <span data-ttu-id="29b23-105">L'inventaire est automatiquement mis à jour uniquement lorsque vous reportez la quantité sortie durant la dernière opération.</span><span class="sxs-lookup"><span data-stu-id="29b23-105">Only when you post output quantity on the last operation, the inventory is updated automatically.</span></span>  

## <a name="to-post-output-quantities-for-one-or-more-production-order-lines"></a><span data-ttu-id="29b23-106">Pour reporter les quantités sorties pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="29b23-106">To post output quantities for one or more production order lines</span></span>
1. <span data-ttu-id="29b23-107">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="29b23-107">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="29b23-108">Renseignez les champs en indiquant les données relatives à la fabrication et à la production.</span><span class="sxs-lookup"><span data-stu-id="29b23-108">Fill in the fields with the production order data and the output data.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="29b23-109">Si l'opération est achevée, sélectionnez le champ **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="29b23-109">If the operation has been completed, select the **Finished** field.</span></span>  

    <span data-ttu-id="29b23-110">Si l'emplacement entrepôt dans lequel les articles doivent être rangés utilise des zones mais n'exige pas le traitement des rangements, affectez un code de zone à la ligne journal pour indiquer l'endroit où les articles doivent être placés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="29b23-110">If the warehouse location where the items should be put away uses bins but does not require put-away processing,  assign a bin code to the journal line to specify where the items should be placed in the warehouse.</span></span> <span data-ttu-id="29b23-111">Pour plus d'informations, voir [Rangement du résultat de fabrication ou d'assemblage](warehouse-how-to-put-away-production-output.md).</span><span class="sxs-lookup"><span data-stu-id="29b23-111">For more information, see [Put Away Production or Assembly Output](warehouse-how-to-put-away-production-output.md).</span></span>  

4. <span data-ttu-id="29b23-112">Choisissez l'action **Reporter** pour reporter les opérations.</span><span class="sxs-lookup"><span data-stu-id="29b23-112">Choose the **Post** acto post the operations.</span></span> <span data-ttu-id="29b23-113">La quantité produite est reportée.</span><span class="sxs-lookup"><span data-stu-id="29b23-113">The output quantity will be posted.</span></span> <span data-ttu-id="29b23-114">L'article peut être livré.</span><span class="sxs-lookup"><span data-stu-id="29b23-114">The item is now available for shipping.</span></span>  

## <a name="to-post-run-times-for-one-or-more-production-order-lines"></a><span data-ttu-id="29b23-115">Pour reporter les temps d'exécution pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="29b23-115">To post run times for one or more production order lines</span></span>
<span data-ttu-id="29b23-116">Le temps d'exécution représente l'avancement des travaux en prenant en compte le temps de travail nécessaire.</span><span class="sxs-lookup"><span data-stu-id="29b23-116">The run time represents work progress in the form of the necessary working time.</span></span>    

1.  <span data-ttu-id="29b23-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="29b23-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="29b23-118">Renseignez les champs en indiquant les données relatives à la fabrication et à la production.</span><span class="sxs-lookup"><span data-stu-id="29b23-118">Fill in the fields with the production order data and the output data.</span></span>  
3.  <span data-ttu-id="29b23-119">Si l'opération est achevée, sélectionnez le champ **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="29b23-119">If the operation is completed, select the **Finished** field.</span></span>  
4. <span data-ttu-id="29b23-120">Choisissez l'action **Reporter** pour reporter le temps passé par opération.</span><span class="sxs-lookup"><span data-stu-id="29b23-120">Choose the **Post** action to post the time spent per operation.</span></span> <span data-ttu-id="29b23-121">Les écritures du grand livre de capacité sont mises à jour pour les unités de production ou les ateliers utilisés.</span><span class="sxs-lookup"><span data-stu-id="29b23-121">Capacity ledger entries are updated for the used work or machine centers.</span></span>

## <a name="see-also"></a><span data-ttu-id="29b23-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29b23-122">See Also</span></span>  
<span data-ttu-id="29b23-123">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="29b23-123">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="29b23-124">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="29b23-124">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="29b23-125">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="29b23-125">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="29b23-126">Inventaire</span><span class="sxs-lookup"><span data-stu-id="29b23-126">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="29b23-127">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="29b23-127">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="29b23-128">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="29b23-128">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>
