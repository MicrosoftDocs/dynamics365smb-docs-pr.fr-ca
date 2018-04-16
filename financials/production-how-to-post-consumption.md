---
title: "Procédure : exécuter en lot la consommation | Microsoft Docs"
description: "Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation."
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
ms.sourcegitcommit: acef03f32124c5983846bc6ed0c4d332c9c8b347
ms.openlocfilehash: 49ec90028dd5e6e16a9a7606c0bfbaeb7c9a83da
ms.contentlocale: fr-ca
ms.lasthandoff: 04/16/2018

---
# <a name="batch-post-production-consumption"></a><span data-ttu-id="1557b-103">Exécuter en lot la consommation de la production</span><span class="sxs-lookup"><span data-stu-id="1557b-103">Batch Post Production Consumption</span></span>
<span data-ttu-id="1557b-104">Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.</span><span class="sxs-lookup"><span data-stu-id="1557b-104">If the flushing method is **Manual**, you must post the components manually, using a consumption journal.</span></span>

<span data-ttu-id="1557b-105">Vous pouvez également configurer le système pour reporter automatiquement (*consommer*) les composantes lorsque vous lancez ou terminez des bons de production.</span><span class="sxs-lookup"><span data-stu-id="1557b-105">You can also set the system up to automatically post (*flush*) components when you start or finish production orders.</span></span> <span data-ttu-id="1557b-106">Pour plus d'informations, voir [Activer la consommation des composantes en fonction de la sortie réalisée](production-how-to-flush-components-according-to-operation-output.md).</span><span class="sxs-lookup"><span data-stu-id="1557b-106">For more information, see [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).</span></span>

## <a name="to-post-consumption-for-one-or-more-production-order-lines"></a><span data-ttu-id="1557b-107">Pour reporter la consommation pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="1557b-107">To post consumption for one or more production order lines</span></span>  
1. <span data-ttu-id="1557b-108">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal consommation**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1557b-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Consumption Journal**, and then choose the related link.</span></span>  
2. <span data-ttu-id="1557b-109">Renseignez les champs en indiquant les données relatives au bon de production et à la consommation.</span><span class="sxs-lookup"><span data-stu-id="1557b-109">Fill in the fields with the production order data and the consumption data.</span></span> [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

   <span data-ttu-id="1557b-110">Si l'entrepôt dans lequel les composantes sont stockées est configuré pour utiliser des zones mais pas le traitement de prélèvement, affectez un code de zone à la ligne journal pour indiquer d'où les articles doivent être prélevés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="1557b-110">If the warehouse location where the components are stored is set up to use bins but does not require pick processing, assign a bin code to the journal line to indicate where the items should be taken from in the warehouse.</span></span> <span data-ttu-id="1557b-111">Pour plus d'informations, voir [Prélever pour la fabrication ou l'assemblage](warehouse-how-to-pick-for-production.md).</span><span class="sxs-lookup"><span data-stu-id="1557b-111">For more information, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md).</span></span>  
3. <span data-ttu-id="1557b-112">Choisissez l'action **Reporter** pour reporter la consommation.</span><span class="sxs-lookup"><span data-stu-id="1557b-112">Choose the **Post** action to post the consumption.</span></span> <span data-ttu-id="1557b-113">Les écritures article associées sont réduites.</span><span class="sxs-lookup"><span data-stu-id="1557b-113">The related item ledger entries are reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="1557b-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1557b-114">See Also</span></span>  
<span data-ttu-id="1557b-115">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="1557b-115">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="1557b-116">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="1557b-116">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="1557b-117">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="1557b-117">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="1557b-118">Stock</span><span class="sxs-lookup"><span data-stu-id="1557b-118">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="1557b-119">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="1557b-119">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="1557b-120">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1557b-120">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

