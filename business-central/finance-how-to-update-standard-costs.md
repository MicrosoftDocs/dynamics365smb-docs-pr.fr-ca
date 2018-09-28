---
title: "Procédure : mise à jour des coûts standard | Microsoft Docs"
description: "Vous devez régulièrement mettre à jour les coûts standard des composants et remonter les nouveaux coûts dans l'article parent."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: e692c53d98760ac3ad71a6a56f3597ce3bc42fe0
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="update-standard-costs"></a><span data-ttu-id="668cf-103">Mise à jour des coûts standard</span><span class="sxs-lookup"><span data-stu-id="668cf-103">Update Standard Costs</span></span>
<span data-ttu-id="668cf-104">Vous devez régulièrement mettre à jour les coûts standard des composants et remonter les nouveaux coûts dans l'article parent.</span><span class="sxs-lookup"><span data-stu-id="668cf-104">You must periodically update the standard costs of components and roll the new costs up to the parent item.</span></span> <span data-ttu-id="668cf-105">Le processus comprend généralement les quatre étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="668cf-105">The process typically consists of the following four steps:</span></span>  

1.  <span data-ttu-id="668cf-106">Mettre à jour les coûts aux niveaux des composantes et de la capacité.</span><span class="sxs-lookup"><span data-stu-id="668cf-106">Update costs at the component and capacity levels.</span></span> <span data-ttu-id="668cf-107">Pour plus d'informations, voir le traitement en lot **Suggérer un coût standard d'article**.</span><span class="sxs-lookup"><span data-stu-id="668cf-107">For more information, see the **Suggest Item Standard Cost** batch job.</span></span>  
2.  <span data-ttu-id="668cf-108">La consolidation et le calcul multi-niveau des coûts des composantes et de capacité permettent de déterminer le coût total de fabrication ou d'assemblage des articles.</span><span class="sxs-lookup"><span data-stu-id="668cf-108">Consolidate and roll up the component and capacity costs to calculate the total manufacturing or assembly cost of the items.</span></span>  
3.  <span data-ttu-id="668cf-109">Appliquer les coûts standard entrés lorsque vous lancez les traitements par lots précédents.</span><span class="sxs-lookup"><span data-stu-id="668cf-109">Implement the standard costs that are entered when you run the previous batch jobs.</span></span> <span data-ttu-id="668cf-110">Les coûts standard n'entrent en vigueur que lorsqu'ils sont mis en œuvre.</span><span class="sxs-lookup"><span data-stu-id="668cf-110">The standard costs do not take effect until they are implemented.</span></span> <span data-ttu-id="668cf-111">Pour plus d'informations, voir Appliquer nouv. coût standard.</span><span class="sxs-lookup"><span data-stu-id="668cf-111">For more information, see Implement Standard Cost Changes.</span></span>  
4.  <span data-ttu-id="668cf-112">Appliquer les modifications pour mettre à jour le champ **Coût unitaire** de la fiche article et effectuer une réévaluation du stock.</span><span class="sxs-lookup"><span data-stu-id="668cf-112">Implement the changes to update the **Unit Cost** field on the item card and perform inventory revaluation.</span></span> <span data-ttu-id="668cf-113">Pour plus d'informations, voir [Réévaluer l'inventaire](inventory-how-revalue-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="668cf-113">For more information, see [Revalue Inventory](inventory-how-revalue-inventory.md).</span></span>  

<span data-ttu-id="668cf-114">Pour plus d'informations, voir [À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md) .</span><span class="sxs-lookup"><span data-stu-id="668cf-114">For more information, see [About Calculating Standard Cost](finance-about-calculating-standard-cost.md).</span></span>  
## <a name="to-update-standard-costs"></a><span data-ttu-id="668cf-115">Pour mettre à jour des coûts standard</span><span class="sxs-lookup"><span data-stu-id="668cf-115">To update standard costs</span></span>  
1.  <span data-ttu-id="668cf-116">Exécutez le traitement en lot **Ajuster coûts - Écr. article**.</span><span class="sxs-lookup"><span data-stu-id="668cf-116">Run the **Adjust Cost-Item Entries** batch job.</span></span>  
2.  <span data-ttu-id="668cf-117">Exécutez le traitement en lot **Reporter le coût de l'inventaire au grand livre**.</span><span class="sxs-lookup"><span data-stu-id="668cf-117">Run the **Post Inventory Cost to G/L** batch job.</span></span>  
3.  <span data-ttu-id="668cf-118">Ouvrez la **Feuille coût standard** et utilisez une ou plusieurs des fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="668cf-118">Open the **Standard Cost Worksheet** and use one or more of the following functions:</span></span>  

    1.  <span data-ttu-id="668cf-119">Exécutez le traitement en lot **Suggérer un coût standard d'article**.</span><span class="sxs-lookup"><span data-stu-id="668cf-119">Run the **Suggest Item Standard Cost** batch job.</span></span>  
    2.  <span data-ttu-id="668cf-120">Vérifiez les résultats et apportez des modifications si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="668cf-120">Review the results and make changes as necessary.</span></span>  
    3.  <span data-ttu-id="668cf-121">Exécutez le traitement en lot **Suggérer le coût standard de la capacité**.</span><span class="sxs-lookup"><span data-stu-id="668cf-121">Run the **Suggest Capacity Standard Cost** batch job.</span></span>  
    4.  <span data-ttu-id="668cf-122">Vérifiez les résultats et apportez des modifications si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="668cf-122">Review the results and make changes as necessary.</span></span>
    5. <span data-ttu-id="668cf-123">Exécutez le traitement en lot **Cumuler le coût standard**.</span><span class="sxs-lookup"><span data-stu-id="668cf-123">Run the **Roll Up Standard Cost** batch job.</span></span>
    6.  <span data-ttu-id="668cf-124">Vérifiez les résultats et apportez des modifications si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="668cf-124">Review the results and make changes as necessary.</span></span>
    7.  <span data-ttu-id="668cf-125">Exécutez le traitement en lot **Appliquer les modifications de coût standard**.</span><span class="sxs-lookup"><span data-stu-id="668cf-125">Run the **Implement Standard Cost Changes** batch job.</span></span>  
4.  <span data-ttu-id="668cf-126">Vérifiez et reportez la fenêtre **Journal réévaluation** renseignée avec les entrées des étapes précédentes de ce processus.</span><span class="sxs-lookup"><span data-stu-id="668cf-126">Review and post the **Revaluation Journal** window, which has been populated with entries from the previous steps in this process.</span></span>  

## <a name="see-also"></a><span data-ttu-id="668cf-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="668cf-127">See Also</span></span>  
 <span data-ttu-id="668cf-128">[À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md) </span><span class="sxs-lookup"><span data-stu-id="668cf-128">[About Calculating Standard Cost](finance-about-calculating-standard-cost.md) </span></span>  
 <span data-ttu-id="668cf-129">[Gestion des coûts ajustés](finance-manage-inventory-costs.md) </span><span class="sxs-lookup"><span data-stu-id="668cf-129">[Managing Inventory Costs](finance-manage-inventory-costs.md) </span></span>  
 <span data-ttu-id="668cf-130">[Détails de conception : modes évaluation stock](design-details-costing-methods.md) [[Finance](finance.md)</span><span class="sxs-lookup"><span data-stu-id="668cf-130">[Design Details: Costing Methods](design-details-costing-methods.md) [[Finance](finance.md)</span></span>  
 <span data-ttu-id="668cf-131">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="668cf-131">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

