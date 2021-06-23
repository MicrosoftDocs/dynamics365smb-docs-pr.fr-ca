---
title: Créer des bons de production à partir de documents de vente
description: Vous pouvez créer des bons de production à partir de documents de vente.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 05/28/2021
ms.author: edupont
ms.openlocfilehash: 438f4d4e1833ba607ceedb9f5d9450c0a4dbb680
ms.sourcegitcommit: f9a190933eadf4608f591e2f1b04c69f1e5c0dc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115246"
---
# <a name="create-production-orders-from-sales-orders"></a><span data-ttu-id="6faef-103">Créer des bons de production à partir de documents de vente</span><span class="sxs-lookup"><span data-stu-id="6faef-103">Create Production Orders from Sales Orders</span></span>
<span data-ttu-id="6faef-104">Vous pouvez créer des bons de production pour les articles produits directement à partir des documents de vente.</span><span class="sxs-lookup"><span data-stu-id="6faef-104">You can create production orders for produced items directly from sales orders.</span></span>  

## <a name="to-create-a-production-order-from-a-sales-order"></a><span data-ttu-id="6faef-105">Pour créer un bon de production à partir d'un document de vente</span><span class="sxs-lookup"><span data-stu-id="6faef-105">To create a production order from a sales order</span></span>  

1.  <span data-ttu-id="6faef-106">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="6faef-106">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="6faef-107">Sélectionnez le document de vente pour lequel vous voulez créer un bon de production.</span><span class="sxs-lookup"><span data-stu-id="6faef-107">Select the sales order you want to create a production order for.</span></span>  
3.  <span data-ttu-id="6faef-108">Sélectionnez l'action **Planification**.</span><span class="sxs-lookup"><span data-stu-id="6faef-108">Choose the **Planning** action.</span></span> <span data-ttu-id="6faef-109">Sur la page **Planification document de vente**, vous pouvez afficher la disponibilité de l'article de document de vente.</span><span class="sxs-lookup"><span data-stu-id="6faef-109">On the **Sales Order Planning** page, you can view the availability of the sales order item.</span></span>  
4.  <span data-ttu-id="6faef-110">Sélectionnez l'action **Créer O.F**.</span><span class="sxs-lookup"><span data-stu-id="6faef-110">Choose the **Create Prod. Order** action.</span></span>  
5.  <span data-ttu-id="6faef-111">Sélectionnez l'état et le type de commande.</span><span class="sxs-lookup"><span data-stu-id="6faef-111">Select the status and order type.</span></span>  
6.  <span data-ttu-id="6faef-112">Choisissez le bouton **Oui** pour créer un ou plusieurs bons de production pour les lignes ayant **Bon de production** dans le champ **Système réapprovisionnement**.</span><span class="sxs-lookup"><span data-stu-id="6faef-112">Choose the **Yes** button to create one or more production orders for the lines that have **Prod. Order** in their **Replenishment System** field.</span></span>


> [!NOTE]  
> <span data-ttu-id="6faef-113">Les lignes de demandes du bon de production créé qui ont **Bon de production** dans le champ **Système réapprovisionnement** représentent des bons de production sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="6faef-113">Demand lines in the created production order that have **Prod. Order** in their **Replenishment System** field represent underlying production orders.</span></span> <span data-ttu-id="6faef-114">Après avoir généré ces bons de production, n’oubliez pas d’identifier toute demande de composante non réalisée pour ceux-ci à l’aide de la page **Planification commande** ou de la fonction **Replanifier** à partir d’ordres créés.</span><span class="sxs-lookup"><span data-stu-id="6faef-114">After you have generated these production orders, remember to identify any unfulfilled component demand for them using the **Order Planning** page or the **Replan** function from created orders.</span></span> 

## <a name="order-type"></a><span data-ttu-id="6faef-115">Type de commande</span><span class="sxs-lookup"><span data-stu-id="6faef-115">Order type</span></span>  
<span data-ttu-id="6faef-116">Vous pouvez choisir entre deux façons de créer les bons de production, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="6faef-116">You can choose between two ways to create the production orders as outlined in the following table.</span></span>

|<span data-ttu-id="6faef-117">Option</span><span class="sxs-lookup"><span data-stu-id="6faef-117">Option</span></span>|<span data-ttu-id="6faef-118">Description</span><span class="sxs-lookup"><span data-stu-id="6faef-118">Description</span></span>|
|------|-----------|
|<span data-ttu-id="6faef-119">O.F. article</span><span class="sxs-lookup"><span data-stu-id="6faef-119">Item Order</span></span>|<span data-ttu-id="6faef-120">Un bon de production est créé pour chaque bon de production nécessaire qui est représenté par une ligne dans la fenêtre **Planification document de vente**.</span><span class="sxs-lookup"><span data-stu-id="6faef-120">One production order is created for each needed production order that is represented by a line in the **Sales Order Planning** window.</span></span>|
|<span data-ttu-id="6faef-121">O.F. projet</span><span class="sxs-lookup"><span data-stu-id="6faef-121">Project Order</span></span>|<span data-ttu-id="6faef-122">Un bon de production est créé pour tous les bons de production nécessaires qui sont représentés par des lignes dans la fenêtre **Planification document de vente**.</span><span class="sxs-lookup"><span data-stu-id="6faef-122">One production order is created for all needed production orders order that are represented by lines in the **Sales Order Planning** window.</span></span> |

<span data-ttu-id="6faef-123">Lorsque vous utilisez des projets de commande, le champ **Type origine** du bon de production indique **En-tête vente** et la commande comporte plusieurs lignes, une pour chaque article de la ligne vente à produire.</span><span class="sxs-lookup"><span data-stu-id="6faef-123">When you use project orders, the **Source Type** field of the production order contains **Sales Header** and the order has multiple lines, one for each sales line item that must be produced.</span></span>  


## <a name="see-also"></a><span data-ttu-id="6faef-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6faef-124">See Also</span></span>  
[<span data-ttu-id="6faef-125">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="6faef-125">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="6faef-126">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="6faef-126">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="6faef-127">Inventaire</span><span class="sxs-lookup"><span data-stu-id="6faef-127">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="6faef-128">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="6faef-128">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="6faef-129">[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md) </span><span class="sxs-lookup"><span data-stu-id="6faef-129">[Design Details: Supply Planning](design-details-supply-planning.md) </span></span>  
[<span data-ttu-id="6faef-130">Configurer des recommandations : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="6faef-130">Setup Best Practices: Supply Planning</span></span>](setup-best-practices-supply-planning.md)  
<span data-ttu-id="6faef-131">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="6faef-131">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]
