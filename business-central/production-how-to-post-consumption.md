---
title: Exécuter en lot la consommation
description: Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 66a19b624c74ec844806c27c490c300746b46704
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5787912"
---
# <a name="batch-post-production-consumption"></a><span data-ttu-id="e6afd-103">Exécuter en lot la consommation de la production</span><span class="sxs-lookup"><span data-stu-id="e6afd-103">Batch Post Production Consumption</span></span>

<span data-ttu-id="e6afd-104">Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.</span><span class="sxs-lookup"><span data-stu-id="e6afd-104">If the flushing method is **Manual**, you must post the components manually, using a consumption journal.</span></span>  

>[!NOTE]
> <span data-ttu-id="e6afd-105">Si vous avez activé le champ **Prélèvement requis** sur la fiche emplacement pour indiquer que l'emplacement requiert un traitement de prélèvement inventaire, vous ne devez pas utiliser ce traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="e6afd-105">If you have placed a check mark in the **Require Pick** field on the location card to indicate that the location requires inventory pick processing, then you do not need to use this batch job.</span></span> [!INCLUDE[prod_short](includes/prod_short.md)] <span data-ttu-id="e6afd-106">gérera la consommation lorsque vous reporterez le prélèvement inventaire.</span><span class="sxs-lookup"><span data-stu-id="e6afd-106">will handle consumption when you post the inventory pick.</span></span> <span data-ttu-id="e6afd-107">Pour plus d’informations, voir [Prélever pour la Production ou l’Assemblage](warehouse-how-to-pick-for-production.md#to-pick-components-in-basic-warehouse-configurations).</span><span class="sxs-lookup"><span data-stu-id="e6afd-107">For more information, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md#to-pick-components-in-basic-warehouse-configurations).</span></span> 

<span data-ttu-id="e6afd-108">Vous pouvez également configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour reporter automatiquement (*consommer*) les composantes lorsque vous lancez ou terminez des bons de production.</span><span class="sxs-lookup"><span data-stu-id="e6afd-108">You can also set up [!INCLUDE[prod_short](includes/prod_short.md)] to automatically post (*flush*) components when you start or finish production orders.</span></span> <span data-ttu-id="e6afd-109">Pour plus d'informations, voir [Activer la consommation des composantes en fonction de la sortie réalisée](production-how-to-flush-components-according-to-operation-output.md).</span><span class="sxs-lookup"><span data-stu-id="e6afd-109">For more information, see [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).</span></span>

## <a name="to-post-consumption-for-one-or-more-production-order-lines"></a><span data-ttu-id="e6afd-110">Pour reporter la consommation pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="e6afd-110">To post consumption for one or more production order lines</span></span>

1.  <span data-ttu-id="e6afd-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal consommation**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6afd-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="e6afd-112">Renseignez les champs en indiquant les données relatives au bon de production et à la consommation.</span><span class="sxs-lookup"><span data-stu-id="e6afd-112">Fill in the fields with the production order data and the consumption data.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    <span data-ttu-id="e6afd-113">Utilisez l'action **Calculer consommation** pour générer les lignes journal des bons de production basés sur la production réelle (quantité de produits finis figurant dans le rapport) ou sur la production prévue (quantité de produits finis que vous prévoyez de fabriquer).</span><span class="sxs-lookup"><span data-stu-id="e6afd-113">Use the **Calc. Consumption** action to generate journal lines from production orders based on the actual output (the quantity of finished goods that you have reported) or on the expected output (the quantity of finished goods that you expect to produce).</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6afd-114">Si vous avez configuré la fiche emplacement pour exiger le traitement des prélèvements en entrepôt, seules les quantités déjà prélevées via une activité entrepôt peuvent être saisies dans le champ **Quantité** de la page **Journal consommation**, pas la quantité calculée.</span><span class="sxs-lookup"><span data-stu-id="e6afd-114">If you configured the location card to require warehouse pick processing, then only quantities that are already picked through a warehouse activity can be entered in the **Quantity** field in the **Consumption Journal** page, not any calculated quantity.</span></span> <span data-ttu-id="e6afd-115">Pour plus d’informations, consultez [Prélever pour la production ou l’assemblage dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)</span><span class="sxs-lookup"><span data-stu-id="e6afd-115">For more information, see [Pick for Production or Assembly in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)</span></span>

3.  <span data-ttu-id="e6afd-116">Choisissez l'action **Reporter** pour reporter la consommation.</span><span class="sxs-lookup"><span data-stu-id="e6afd-116">Choose the **Post** action to post the consumption.</span></span> <span data-ttu-id="e6afd-117">Les stocks associés sont réduits.</span><span class="sxs-lookup"><span data-stu-id="e6afd-117">The related inventories are reduced.</span></span>



## <a name="see-also"></a><span data-ttu-id="e6afd-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6afd-118">See Also</span></span>

<span data-ttu-id="e6afd-119">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="e6afd-119">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="e6afd-120">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="e6afd-120">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="e6afd-121">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="e6afd-121">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="e6afd-122">Inventaire</span><span class="sxs-lookup"><span data-stu-id="e6afd-122">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="e6afd-123">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="e6afd-123">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="e6afd-124">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="e6afd-124">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]
