---
title: "Détails de conception - Arrondissement | Microsoft Docs"
description: "Des arrondissements résiduels peuvent se produire lorsque vous évaluez le coût d'une diminution d'inventaire qui est mesurée dans une quantité différente de l'augmentation d'inventaire correspondante. Les reliquats d'arrondissement sont calculés pour tous les modes d'évaluation du coût lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 39d4bdc430fc74452e7f089c38b28b3214304725
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-rounding"></a><span data-ttu-id="2c187-104">Détails de conception : arrondissement</span><span class="sxs-lookup"><span data-stu-id="2c187-104">Design Details: Rounding</span></span>
<span data-ttu-id="2c187-105">Des arrondissements résiduels peuvent se produire lorsque vous évaluez le coût d'une diminution d'inventaire qui est mesurée dans une quantité différente de l'augmentation d'inventaire correspondante.</span><span class="sxs-lookup"><span data-stu-id="2c187-105">Rounding residuals can occur when you value the cost of an inventory decrease that is measured in a different quantity than the corresponding inventory increase.</span></span> <span data-ttu-id="2c187-106">Les reliquats d'arrondissement sont calculés pour tous les modes d'évaluation du coût lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**.</span><span class="sxs-lookup"><span data-stu-id="2c187-106">Rounding residuals are calculated for all costing methods when you run the **Adjust Cost - Item Entries** batch job.</span></span>  

 <span data-ttu-id="2c187-107">Lorsque vous utilisez le mode d'évaluation des coûts moyen, le montant résiduel arrondi est calculé et enregistré sur une base cumulative écriture par écriture.</span><span class="sxs-lookup"><span data-stu-id="2c187-107">When you use the average costing method, the rounding residual is calculated and recorded on a cumulative, entry-by-entry basis.</span></span>  

 <span data-ttu-id="2c187-108">Lorsque vous utilisez un mode d'évaluation des coûts autre que Moyenne, le montant résiduel est calculé lorsque l'augmentation d'inventaire a été totalement affectée, c'est-à-dire lorsque la quantité restante pour l'augmentation d'inventaire est égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="2c187-108">When you use a costing method other than Average, the rounding residual is calculated when the inventory increase has been fully applied, that is when the remaining quantity for the inventory increase is equal to zero.</span></span> <span data-ttu-id="2c187-109">Une écriture distincte est ensuite créée pour l'arrondissement résiduel, et la date de report de l'écriture arrondissement correspond à la date de report de la dernière écriture valeur facturée de l'augmentation d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="2c187-109">A separate entry is then created for the rounding residual, and the posting date on this rounding entry is the posting date of the last invoiced value entry of the inventory increase.</span></span>  

## <a name="example"></a><span data-ttu-id="2c187-110">Exemple :</span><span class="sxs-lookup"><span data-stu-id="2c187-110">Example</span></span>  
 <span data-ttu-id="2c187-111">L'exemple suivant présente la manière dont les différents reliquats d'arrondissement sont traités pour le mode évaluation des coûts moyen et pour le mode évaluation des coûts non moyen, respectivement.</span><span class="sxs-lookup"><span data-stu-id="2c187-111">The following example illustrates how different rounding residuals are handled for the average costing method and non-Average costing method, respectively.</span></span> <span data-ttu-id="2c187-112">Dans les deux cas, le traitement en lot **Ajuster coûts - Écr. article** a été exécuté.</span><span class="sxs-lookup"><span data-stu-id="2c187-112">In both cases, the **Adjust Cost - Item Entries** batch job has been run.</span></span>  

 <span data-ttu-id="2c187-113">La table suivante montre les écritures du grand livre d'articles sur lesquelles l'exemple est basé.</span><span class="sxs-lookup"><span data-stu-id="2c187-113">The following table shows the item ledger entries that the example is based on.</span></span>  

|<span data-ttu-id="2c187-114">Date de report</span><span class="sxs-lookup"><span data-stu-id="2c187-114">Posting Date</span></span>|<span data-ttu-id="2c187-115">Quantité</span><span class="sxs-lookup"><span data-stu-id="2c187-115">Quantity</span></span>|<span data-ttu-id="2c187-116">N° séquence </span><span class="sxs-lookup"><span data-stu-id="2c187-116">Entry No.</span></span>|  
|------------------|--------------|---------------|  
|<span data-ttu-id="2c187-117">01/01/20</span><span class="sxs-lookup"><span data-stu-id="2c187-117">01-01-20</span></span>|<span data-ttu-id="2c187-118">3</span><span class="sxs-lookup"><span data-stu-id="2c187-118">3</span></span>|<span data-ttu-id="2c187-119">1</span><span class="sxs-lookup"><span data-stu-id="2c187-119">1</span></span>|  
|<span data-ttu-id="2c187-120">01/02/20</span><span class="sxs-lookup"><span data-stu-id="2c187-120">02-01-20</span></span>|<span data-ttu-id="2c187-121">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-121">-1</span></span>|<span data-ttu-id="2c187-122">2</span><span class="sxs-lookup"><span data-stu-id="2c187-122">2</span></span>|  
|<span data-ttu-id="2c187-123">01/03/20</span><span class="sxs-lookup"><span data-stu-id="2c187-123">03-01-20</span></span>|<span data-ttu-id="2c187-124">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-124">-1</span></span>|<span data-ttu-id="2c187-125">3</span><span class="sxs-lookup"><span data-stu-id="2c187-125">3</span></span>|  
|<span data-ttu-id="2c187-126">01/04/20</span><span class="sxs-lookup"><span data-stu-id="2c187-126">04-01-20</span></span>|<span data-ttu-id="2c187-127">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-127">-1</span></span>|<span data-ttu-id="2c187-128">4</span><span class="sxs-lookup"><span data-stu-id="2c187-128">4</span></span>|  

 <span data-ttu-id="2c187-129">Pour un article utilisant le mode évaluation des coûts moyen, l'arrondissement résiduel (1/300) est calculé avec la première diminution (numéro de séquence 2) et est reporté sur le numéro de séquence 3.</span><span class="sxs-lookup"><span data-stu-id="2c187-129">For an item using the Average costing method, the rounding residual (1/300) is calculated with the first decrease (entry number 2) and is carried forward to entry number 3.</span></span> <span data-ttu-id="2c187-130">Par conséquent, le numéro de séquence 3 est évalué à –3,34.</span><span class="sxs-lookup"><span data-stu-id="2c187-130">Therefore, entry number 3 is valued at –3.34.</span></span>  

 <span data-ttu-id="2c187-131">Le tableau suivant montre les écritures valeur résultantes.</span><span class="sxs-lookup"><span data-stu-id="2c187-131">The following table shows the resulting value entries.</span></span>  

|<span data-ttu-id="2c187-132">Date de report</span><span class="sxs-lookup"><span data-stu-id="2c187-132">Posting Date</span></span>|<span data-ttu-id="2c187-133">Quantité</span><span class="sxs-lookup"><span data-stu-id="2c187-133">Quantity</span></span>|<span data-ttu-id="2c187-134">Coût indiqué (réel)</span><span class="sxs-lookup"><span data-stu-id="2c187-134">Cost Amount (Actual)</span></span>|<span data-ttu-id="2c187-135">N° écriture article gr. livre</span><span class="sxs-lookup"><span data-stu-id="2c187-135">Item Ledger Entry No.</span></span>|<span data-ttu-id="2c187-136">N° séquence </span><span class="sxs-lookup"><span data-stu-id="2c187-136">Entry No.</span></span>|  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|<span data-ttu-id="2c187-137">01/01/20</span><span class="sxs-lookup"><span data-stu-id="2c187-137">01-01-20</span></span>|<span data-ttu-id="2c187-138">3</span><span class="sxs-lookup"><span data-stu-id="2c187-138">3</span></span>|<span data-ttu-id="2c187-139">10</span><span class="sxs-lookup"><span data-stu-id="2c187-139">10</span></span>|<span data-ttu-id="2c187-140">1</span><span class="sxs-lookup"><span data-stu-id="2c187-140">1</span></span>|<span data-ttu-id="2c187-141">1</span><span class="sxs-lookup"><span data-stu-id="2c187-141">1</span></span>|  
|<span data-ttu-id="2c187-142">01/02/20</span><span class="sxs-lookup"><span data-stu-id="2c187-142">02-01-20</span></span>|<span data-ttu-id="2c187-143">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-143">-1</span></span>|<span data-ttu-id="2c187-144">-3,33</span><span class="sxs-lookup"><span data-stu-id="2c187-144">-3.33</span></span>|<span data-ttu-id="2c187-145">2</span><span class="sxs-lookup"><span data-stu-id="2c187-145">2</span></span>|<span data-ttu-id="2c187-146">2</span><span class="sxs-lookup"><span data-stu-id="2c187-146">2</span></span>|  
|<span data-ttu-id="2c187-147">01/03/20</span><span class="sxs-lookup"><span data-stu-id="2c187-147">03-01-20</span></span>|<span data-ttu-id="2c187-148">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-148">-1</span></span>|<span data-ttu-id="2c187-149">-3,34</span><span class="sxs-lookup"><span data-stu-id="2c187-149">-3.34</span></span>|<span data-ttu-id="2c187-150">3</span><span class="sxs-lookup"><span data-stu-id="2c187-150">3</span></span>|<span data-ttu-id="2c187-151">3</span><span class="sxs-lookup"><span data-stu-id="2c187-151">3</span></span>|  
|<span data-ttu-id="2c187-152">01/04/20</span><span class="sxs-lookup"><span data-stu-id="2c187-152">04-01-20</span></span>|<span data-ttu-id="2c187-153">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-153">-1</span></span>|<span data-ttu-id="2c187-154">-3,33</span><span class="sxs-lookup"><span data-stu-id="2c187-154">-3.33</span></span>|<span data-ttu-id="2c187-155">4</span><span class="sxs-lookup"><span data-stu-id="2c187-155">4</span></span>|<span data-ttu-id="2c187-156">4</span><span class="sxs-lookup"><span data-stu-id="2c187-156">4</span></span>|  

 <span data-ttu-id="2c187-157">Pour un article utilisant une méthode d'évaluation coût autre que Moyenne, l'arrondissement résiduel (0,01) est calculé lorsque la quantité restante pour l'augmentation d'inventaire est égale à zéro.</span><span class="sxs-lookup"><span data-stu-id="2c187-157">For an item using a costing method other than Average, the rounding residual (0.01) is calculated when the remaining quantity for the inventory increase is zero.</span></span> <span data-ttu-id="2c187-158">Le montant résiduel arrondi a une écriture distincte (numéro 5).</span><span class="sxs-lookup"><span data-stu-id="2c187-158">The rounding residual has a separate entry (number 5).</span></span>  

 <span data-ttu-id="2c187-159">Le tableau suivant montre les écritures valeur résultantes.</span><span class="sxs-lookup"><span data-stu-id="2c187-159">The following table shows the resulting value entries.</span></span>  

|<span data-ttu-id="2c187-160">Date de report</span><span class="sxs-lookup"><span data-stu-id="2c187-160">Posting Date</span></span>|<span data-ttu-id="2c187-161">Quantité</span><span class="sxs-lookup"><span data-stu-id="2c187-161">Quantity</span></span>|<span data-ttu-id="2c187-162">Coût indiqué (réel)</span><span class="sxs-lookup"><span data-stu-id="2c187-162">Cost Amount (Actual)</span></span>|<span data-ttu-id="2c187-163">N° écriture article gr. livre</span><span class="sxs-lookup"><span data-stu-id="2c187-163">Item Ledger Entry No.</span></span>|<span data-ttu-id="2c187-164">N° séquence </span><span class="sxs-lookup"><span data-stu-id="2c187-164">Entry No.</span></span>|  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|<span data-ttu-id="2c187-165">01/01/20</span><span class="sxs-lookup"><span data-stu-id="2c187-165">01-01-20</span></span>|<span data-ttu-id="2c187-166">3</span><span class="sxs-lookup"><span data-stu-id="2c187-166">3</span></span>|<span data-ttu-id="2c187-167">10</span><span class="sxs-lookup"><span data-stu-id="2c187-167">10</span></span>|<span data-ttu-id="2c187-168">1</span><span class="sxs-lookup"><span data-stu-id="2c187-168">1</span></span>|<span data-ttu-id="2c187-169">1</span><span class="sxs-lookup"><span data-stu-id="2c187-169">1</span></span>|  
|<span data-ttu-id="2c187-170">01/02/20</span><span class="sxs-lookup"><span data-stu-id="2c187-170">02-01-20</span></span>|<span data-ttu-id="2c187-171">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-171">-1</span></span>|<span data-ttu-id="2c187-172">-3,33</span><span class="sxs-lookup"><span data-stu-id="2c187-172">-3.33</span></span>|<span data-ttu-id="2c187-173">2</span><span class="sxs-lookup"><span data-stu-id="2c187-173">2</span></span>|<span data-ttu-id="2c187-174">2</span><span class="sxs-lookup"><span data-stu-id="2c187-174">2</span></span>|  
|<span data-ttu-id="2c187-175">01/03/20</span><span class="sxs-lookup"><span data-stu-id="2c187-175">03-01-20</span></span>|<span data-ttu-id="2c187-176">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-176">-1</span></span>|<span data-ttu-id="2c187-177">-3,33</span><span class="sxs-lookup"><span data-stu-id="2c187-177">-3.33</span></span>|<span data-ttu-id="2c187-178">3</span><span class="sxs-lookup"><span data-stu-id="2c187-178">3</span></span>|<span data-ttu-id="2c187-179">3</span><span class="sxs-lookup"><span data-stu-id="2c187-179">3</span></span>|  
|<span data-ttu-id="2c187-180">01/04/20</span><span class="sxs-lookup"><span data-stu-id="2c187-180">04-01-20</span></span>|<span data-ttu-id="2c187-181">-1</span><span class="sxs-lookup"><span data-stu-id="2c187-181">-1</span></span>|<span data-ttu-id="2c187-182">-3,33</span><span class="sxs-lookup"><span data-stu-id="2c187-182">-3.33</span></span>|<span data-ttu-id="2c187-183">4</span><span class="sxs-lookup"><span data-stu-id="2c187-183">4</span></span>|<span data-ttu-id="2c187-184">4</span><span class="sxs-lookup"><span data-stu-id="2c187-184">4</span></span>|  
|<span data-ttu-id="2c187-185">01/01/20</span><span class="sxs-lookup"><span data-stu-id="2c187-185">01-01-20</span></span>|<span data-ttu-id="2c187-186">0</span><span class="sxs-lookup"><span data-stu-id="2c187-186">0</span></span>|<span data-ttu-id="2c187-187">-0,01</span><span class="sxs-lookup"><span data-stu-id="2c187-187">-0.01</span></span>|<span data-ttu-id="2c187-188">1</span><span class="sxs-lookup"><span data-stu-id="2c187-188">1</span></span>|<span data-ttu-id="2c187-189">5</span><span class="sxs-lookup"><span data-stu-id="2c187-189">5</span></span>|  

## <a name="see-also"></a><span data-ttu-id="2c187-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2c187-190">See Also</span></span>  
 <span data-ttu-id="2c187-191">[Détails de conception : stock évaluation stock](design-details-inventory-costing.md) </span><span class="sxs-lookup"><span data-stu-id="2c187-191">[Design Details: Inventory Costing](design-details-inventory-costing.md) </span></span>  
 <span data-ttu-id="2c187-192">[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md) </span><span class="sxs-lookup"><span data-stu-id="2c187-192">[Design Details: Cost Adjustment](design-details-cost-adjustment.md) </span></span>  
 <span data-ttu-id="2c187-193">[Détails de conception : Modes évaluation stock](design-details-costing-methods.md) [Gestion des composants des coûts](finance-manage-inventory-costs.md)</span><span class="sxs-lookup"><span data-stu-id="2c187-193">[Design Details: Costing Methods](design-details-costing-methods.md) [Managing Inventory Costs](finance-manage-inventory-costs.md)</span></span>  
 [<span data-ttu-id="2c187-194">Finance</span><span class="sxs-lookup"><span data-stu-id="2c187-194">Finance</span></span>](finance.md)  
 <span data-ttu-id="2c187-195">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="2c187-195">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
