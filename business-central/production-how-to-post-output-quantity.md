---
title: Exécuter en lot la sortie de production et les temps d'exécution
description: La quantité de sortie représente l'avancement du travail sous la forme de la quantité finie et de la capacité utilisée de l'atelier ou de l'unité de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 923f68b13619013dd54062438c66192a682868bc
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5787887"
---
# <a name="batch-post-output-and-run-times"></a><span data-ttu-id="14ad9-103">Exécuter en lot la production et les temps d'exécution</span><span class="sxs-lookup"><span data-stu-id="14ad9-103">Batch Post Output and Run Times</span></span>
<span data-ttu-id="14ad9-104">La quantité de sortie représente l'avancement du travail sous la forme de la quantité finie et de la capacité utilisée de l'atelier ou de l'unité de production.</span><span class="sxs-lookup"><span data-stu-id="14ad9-104">The output quantity represents the work progress in the form of the finished quantity and used capacity of work or machine center.</span></span>

<span data-ttu-id="14ad9-105">Vous pouvez utiliser le journal de sortie pour :</span><span class="sxs-lookup"><span data-stu-id="14ad9-105">You can use the output journal to:</span></span>
*  <span data-ttu-id="14ad9-106">Ajustez l'inventaire en fonction de la production des articles finis émanant de la production.</span><span class="sxs-lookup"><span data-stu-id="14ad9-106">Adjust inventory in connection with output of finished items from production.</span></span>
*  <span data-ttu-id="14ad9-107">Enregistrez les quantités et les rebuts pour chaque opération dans l'itinéraire de production.</span><span class="sxs-lookup"><span data-stu-id="14ad9-107">Register quantities and scrap for each operation in production routing.</span></span>
*  <span data-ttu-id="14ad9-108">Enregistrez la configuration et le temps d'exécution pour les ateliers et les unités de production.</span><span class="sxs-lookup"><span data-stu-id="14ad9-108">Register setup and run time for work and machine centers.</span></span>

> [!NOTE]
> <span data-ttu-id="14ad9-109">Si l'itinéraire de production est utilisé, l'inventaire est mis à jour uniquement lorsque vous reportez la quantité produite durant la dernière opération.</span><span class="sxs-lookup"><span data-stu-id="14ad9-109">If production routing are used, the inventory is updated only when you post output quantity on the last operation.</span></span>

<span data-ttu-id="14ad9-110">La fenêtre **Journal production** vous permet d’exécuter les mêmes tâches que celles de la fenêtre **Journal de sortie** et d'exécuter en même temps les tâches connexes de report de la consommation.</span><span class="sxs-lookup"><span data-stu-id="14ad9-110">With the **Production Journal** window, you can perform the same tasks as in the **Output Journal** window and at the same time perform the related consumption posting tasks.</span></span> <span data-ttu-id="14ad9-111">Pour plus d'informations, voir [Enregistrer la consommation et la production pour une ligne bon de production libéré](production-how-to-register-consumption-and-output.md).</span><span class="sxs-lookup"><span data-stu-id="14ad9-111">For more information, see [Register Consumption and Output for One Released Production order line](production-how-to-register-consumption-and-output.md).</span></span>

## <a name="to-post-output-quantities-andor-register-run-times-for-one-or-more-production-order-lines"></a><span data-ttu-id="14ad9-112">Pour reporter les quantités produites et/ou enregistrer le temps d’exécution pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="14ad9-112">To post output quantities and/or register run times for one or more production order lines</span></span>
1. <span data-ttu-id="14ad9-113">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="14ad9-113">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="14ad9-114">Renseignez les champs en indiquant les données relatives au bon de production et/ou le temps d’exécution.</span><span class="sxs-lookup"><span data-stu-id="14ad9-114">Fill in the fields with the production order data and the output data and/or run time.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
  
    <span data-ttu-id="14ad9-115">Vous pouvez utiliser la fonction **Éclater itinéraire** pour générer des lignes journal à partir des bons de production.</span><span class="sxs-lookup"><span data-stu-id="14ad9-115">You can use the **Explode Routing** function to generate journal lines from production orders.</span></span>
  
4. <span data-ttu-id="14ad9-116">Si l'opération est achevée, sélectionnez le champ **Terminé**.</span><span class="sxs-lookup"><span data-stu-id="14ad9-116">If the operation has been completed, select the **Finished** field.</span></span>  
5. <span data-ttu-id="14ad9-117">Choisissez l’action **Reporter** pour reporter les opérations.</span><span class="sxs-lookup"><span data-stu-id="14ad9-117">Choose the **Post** action to post the operations.</span></span> 
 
<span data-ttu-id="14ad9-118">Les écritures capacité sont mises à jour pour les unités de production ou les ateliers utilisés avec des informations sur le temps et la quantité de production et de rebut.</span><span class="sxs-lookup"><span data-stu-id="14ad9-118">Capacity ledger entries are updated for the used work or machine centers with information about time and quantity of output and scrap.</span></span> <span data-ttu-id="14ad9-119">Si vous avez reporté la dernière opération, l'article sera ajouté à l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="14ad9-119">If you posted the last operation, the item will be added to the inventory.</span></span> 

## <a name="see-also"></a><span data-ttu-id="14ad9-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="14ad9-120">See Also</span></span>  
<span data-ttu-id="14ad9-121">[Reporter la mise au rebut manuellement](production-how-to-post-scrap.md)
[Report de sortie inversée](production-how-to-reverse-output-posting.md)
[Fabrication](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="14ad9-121">[Post Scrap Manually](production-how-to-post-scrap.md)
[Reverse Output Posting](production-how-to-reverse-output-posting.md)
[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="14ad9-122">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="14ad9-122">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="14ad9-123">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="14ad9-123">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="14ad9-124">Inventaire</span><span class="sxs-lookup"><span data-stu-id="14ad9-124">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="14ad9-125">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="14ad9-125">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]
