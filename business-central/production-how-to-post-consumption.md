---
title: 'Procédure : exécuter en lot la consommation | Microsoft Docs'
description: Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: e656cf8ccf9c87187cb2b6e7bba858216cf9b413
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3190527"
---
# <a name="batch-post-production-consumption"></a><span data-ttu-id="978ea-103">Exécuter en lot la consommation de la production</span><span class="sxs-lookup"><span data-stu-id="978ea-103">Batch Post Production Consumption</span></span>
<span data-ttu-id="978ea-104">Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.</span><span class="sxs-lookup"><span data-stu-id="978ea-104">If the flushing method is **Manual**, you must post the components manually, using a consumption journal.</span></span>

<span data-ttu-id="978ea-105">Vous pouvez également configurer le système pour reporter automatiquement (*consommer*) les composantes lorsque vous lancez ou terminez des bons de production.</span><span class="sxs-lookup"><span data-stu-id="978ea-105">You can also set the system up to automatically post (*flush*) components when you start or finish production orders.</span></span> <span data-ttu-id="978ea-106">Pour plus d'informations, voir [Activer la consommation des composantes en fonction de la sortie réalisée](production-how-to-flush-components-according-to-operation-output.md).</span><span class="sxs-lookup"><span data-stu-id="978ea-106">For more information, see [Enable Flushing of Components According to Operation Output](production-how-to-flush-components-according-to-operation-output.md).</span></span>

## <a name="to-post-consumption-for-one-or-more-production-order-lines"></a><span data-ttu-id="978ea-107">Pour reporter la consommation pour une ou plusieurs lignes bon de production</span><span class="sxs-lookup"><span data-stu-id="978ea-107">To post consumption for one or more production order lines</span></span>  
1.  <span data-ttu-id="978ea-108">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal consommation**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="978ea-108">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Consumption Journal**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="978ea-109">Renseignez les champs en indiquant les données relatives au bon de production et à la consommation.</span><span class="sxs-lookup"><span data-stu-id="978ea-109">Fill in the fields with the production order data and the consumption data.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    <span data-ttu-id="978ea-110">Si l'entrepôt dans lequel les composantes sont stockées est configuré pour utiliser des zones mais pas le traitement de prélèvement, affectez un code de zone à la ligne journal pour indiquer d'où les articles doivent être prélevés dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="978ea-110">If the warehouse location where the components are stored is set up to use bins but does not require pick processing, assign a bin code to the journal line to indicate where the items should be taken from in the warehouse.</span></span> <span data-ttu-id="978ea-111">Pour plus d'informations, voir [Prélever pour la fabrication ou l'assemblage](warehouse-how-to-pick-for-production.md).</span><span class="sxs-lookup"><span data-stu-id="978ea-111">For more information, see [Pick for Production or Assembly](warehouse-how-to-pick-for-production.md).</span></span>  
3.  <span data-ttu-id="978ea-112">Choisissez l'action **Reporter** pour reporter la consommation.</span><span class="sxs-lookup"><span data-stu-id="978ea-112">Choose the **Post** action to post the consumption.</span></span> <span data-ttu-id="978ea-113">Les écritures article associées sont réduites.</span><span class="sxs-lookup"><span data-stu-id="978ea-113">The related item ledger entries are reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="978ea-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="978ea-114">See Also</span></span>  
<span data-ttu-id="978ea-115">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="978ea-115">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="978ea-116">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="978ea-116">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="978ea-117">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="978ea-117">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="978ea-118">Inventaire</span><span class="sxs-lookup"><span data-stu-id="978ea-118">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="978ea-119">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="978ea-119">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="978ea-120">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="978ea-120">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
