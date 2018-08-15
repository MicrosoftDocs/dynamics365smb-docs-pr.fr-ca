---
title: "À propos des coûts des O.F. terminés | Microsoft Docs"
description: "L'achèvement du bon de production est une tâche importante dans l'évaluation du cycle de vie de l'article en cours de production. Les coûts finaux, notamment les écarts dans un environnement de coût standard, les valeurs réelles dans un environnement de coût FIFO, moyen ou LIFO, sont calculés à l'aide du traitement en lot **Ajuster coûts - Écr. article**."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: ea69f3c8af84e92f09f4b2046530c9b935905ebe
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="about-finished-production-order-costs"></a><span data-ttu-id="b7900-104">À propos des coûts des bons de production achevés</span><span class="sxs-lookup"><span data-stu-id="b7900-104">About Finished Production Order Costs</span></span>
<span data-ttu-id="b7900-105">L'achèvement du bon de production est une tâche importante dans l'évaluation du cycle de vie de l'article en cours de production.</span><span class="sxs-lookup"><span data-stu-id="b7900-105">Finishing the production order is an important task in completing the costing lifecycle of the item that is being produced.</span></span> <span data-ttu-id="b7900-106">Les coûts finaux, notamment les écarts dans un environnement de coût standard, les valeurs réelles dans un environnement de coût FIFO, Moyenne ou LIFO, sont calculés à l'aide du traitement en lot **Ajuster coûts - Écr. article** qui permet d'opérer un rapprochement financier des coûts de production d'un article.</span><span class="sxs-lookup"><span data-stu-id="b7900-106">Final costs, including variances in a standard cost environment, actuals in a FIFO, Average, or LIFO cost environment, are calculated using the **Adjust Cost - Item Entries** batch job, which allows for financial reconciliation of the costs of item production.</span></span> <span data-ttu-id="b7900-107">Pour qu'un ordre de fabrication soit pris en considération pour un ajustement de coût, son statut doit être **Produit fini**.</span><span class="sxs-lookup"><span data-stu-id="b7900-107">For a production order to be considered for cost adjustment, the status must be **Finished**.</span></span> <span data-ttu-id="b7900-108">Il est donc essentiel qu'au moment de son achèvement, le statut d'un ordre de fabrication soit modifié en **Produit fini**.</span><span class="sxs-lookup"><span data-stu-id="b7900-108">It is therefore critical that upon completion, the status of a production order is changed to **Finished**.</span></span>  

## <a name="example"></a><span data-ttu-id="b7900-109">Exemple :</span><span class="sxs-lookup"><span data-stu-id="b7900-109">Example</span></span>  
 <span data-ttu-id="b7900-110">Dans un environnement de coût standard, lorsque vous consommez des matières pour produire un article, le coût de l'article, celui de la main-d'œuvre et celui des frais généraux sont répertoriés dans le TEC, pour définir simplement les choses.</span><span class="sxs-lookup"><span data-stu-id="b7900-110">In a standard cost environment, when you consume material to produce an item, stated simply, the cost of the item plus labor and overhead go into WIP.</span></span> <span data-ttu-id="b7900-111">Lorsque l'article est produit, son coût standard est retranché du TEC.</span><span class="sxs-lookup"><span data-stu-id="b7900-111">When the item is produced, WIP is reduced by the amount of the standard cost of the item.</span></span> <span data-ttu-id="b7900-112">Généralement, le résultat de l'opération n'est pas égal à zéro.</span><span class="sxs-lookup"><span data-stu-id="b7900-112">Typically, these costs do not net to zero.</span></span> <span data-ttu-id="b7900-113">Pour que le résultat obtenu soit égal à zéro, vous devez exécuter le traitement en lot **Ajuster coûts - Écr. article** en sachant que seuls les bons de production dont l'état est **Fini** seront pris en considération pour l'ajustement.</span><span class="sxs-lookup"><span data-stu-id="b7900-113">So that these costs can net to zero, you must run the **Adjust Cost - Item Entries** batch job, noting that only production orders with the status of **Finished** will be considered for adjustment.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b7900-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b7900-114">See Also</span></span>  
[<span data-ttu-id="b7900-115">Gestion des coûts ajustés</span><span class="sxs-lookup"><span data-stu-id="b7900-115">Managing Inventory Costs</span></span>](finance-manage-inventory-costs.md)  
[<span data-ttu-id="b7900-116">Production</span><span class="sxs-lookup"><span data-stu-id="b7900-116">Manufacturing</span></span>](production-manage-manufacturing.md)  
<span data-ttu-id="b7900-117">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="b7900-117">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
