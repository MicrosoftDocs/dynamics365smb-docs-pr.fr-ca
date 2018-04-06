---
title: "Gestion des coûts ajustés | Microsoft Docs"
description: "La gestion des coûts, aussi appelée « évaluation des coûts », se charge de l'enregistrement et du report des coûts d'exploitation de la compagnie. Inclut le report des coûts de fabrication et des coûts inventaire qui constituent la valeur des articles."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/29/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: e2443552440cae8a0d90753d9a56fdc82006a197
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="managing-inventory-costs"></a><span data-ttu-id="5b6d6-104">Gestion des coûts ajustés</span><span class="sxs-lookup"><span data-stu-id="5b6d6-104">Managing Inventory Costs</span></span>
<span data-ttu-id="5b6d6-105">La gestion des coûts, aussi appelée « évaluation des coûts », se charge de l'enregistrement et du report des coûts d'exploitation de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-105">Cost management, also referred to as “costing”, is concerned with recording and reporting business operating costs.</span></span> <span data-ttu-id="5b6d6-106">Inclut le report des coûts de fabrication et des coûts inventaire qui constituent la valeur des articles.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-106">It includes the reporting of manufacturing costs and inventory costs, that is, the value of items.</span></span>   

<span data-ttu-id="5b6d6-107">Il est essentiel de comprendre les principes suivants : les méthodes d'évaluation du coût définissent le mode d'évaluation des articles lors de leur sortie de l'inventaire, l'ajustement des coûts met à jour le coût des marchandises vendues avec les coûts d'achat associés reportés après la vente, les valeurs en inventaire doivent être reportées sur les comptes du grand livre appropriés à intervalles réguliers.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-107">Central principles to understand are that costing methods define how items are valued when they leave inventory, that cost adjustment updates the cost of goods sold with related purchase costs posted after the sale, and that inventory values must be posted to dedicated G/L accounts at regular intervals.</span></span>

<span data-ttu-id="5b6d6-108">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-108">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>

|<span data-ttu-id="5b6d6-109">**Pour**</span><span class="sxs-lookup"><span data-stu-id="5b6d6-109">**To**</span></span>|<span data-ttu-id="5b6d6-110">**Voir**</span><span class="sxs-lookup"><span data-stu-id="5b6d6-110">**See**</span></span>|  
|------------|-------------|  
|<span data-ttu-id="5b6d6-111">Lire différentes informations conceptuelles pour comprendre les principes et définitions qui gouvernent la fonctionnalité Comptabilité des coûts de stock [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b6d6-111">Read various conceptual information to understand the principles and definitions that govern the inventory costing accounting functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>|[<span data-ttu-id="5b6d6-112">À propos de l'évaluation des coûts de stock</span><span class="sxs-lookup"><span data-stu-id="5b6d6-112">About Inventory Costing</span></span>](finance-learn-about-costing.md)|  
|<span data-ttu-id="5b6d6-113">Configurer les périodes d'inventaire, les méthodes d'évaluation des coûts et les méthodes d'arrondissement.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-113">Set up inventory periods, costing methods, and rounding methods.</span></span>|[<span data-ttu-id="5b6d6-114">Configuration de l'évaluation de l'inventaire et des coûts</span><span class="sxs-lookup"><span data-stu-id="5b6d6-114">Setting Up Inventory Valuation and Costing</span></span>](finance-set-up-inventory-valuation-and-costing.md)|
|<span data-ttu-id="5b6d6-115">Réévaluer ou amortir la valeur d'un ou de plusieurs articles en inventaire en reportant leur valeur calculée actuelle.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-115">Appreciate or depreciate the value of one or more items in inventory by posting their current, calculated value.</span></span>|[<span data-ttu-id="5b6d6-116">Réévaluer l'inventaire</span><span class="sxs-lookup"><span data-stu-id="5b6d6-116">Revalue Inventory</span></span>](inventory-how-revalue-inventory.md)|
|<span data-ttu-id="5b6d6-117">Ajuster les coûts d'article, automatiquement ou manuellement, pour transférer les modifications de coût des écritures entrantes à leurs écritures sortantes associées.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-117">Adjust item costs, either automatically or manually, to forward cost changes from inbound entries to their related outbound entries.</span></span>|[<span data-ttu-id="5b6d6-118">Ajuster coûts et prix article</span><span class="sxs-lookup"><span data-stu-id="5b6d6-118">Adjust Item Costs</span></span>](inventory-how-adjust-item-costs.md)|
|<span data-ttu-id="5b6d6-119">Utiliser les fonctions d'évaluation des coûts spéciales pour les transactions article quotidiennes dans les opérations liées aux articles.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-119">Use special costing functions for every-day item transactions in the item operations.</span></span>|[<span data-ttu-id="5b6d6-120">Gestion des coûts inventaire et des coûts de fabrication</span><span class="sxs-lookup"><span data-stu-id="5b6d6-120">Handling Inventory and Manufacturing Costs</span></span>](finance-handle-inventory-and-manufacturing-costs.md)|  
|<span data-ttu-id="5b6d6-121">Actualisez périodiquement les coûts standard des composantes, dans les nomenclatures d'assemblage ou de production, et remontez les nouveaux coûts dans l'article parent.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-121">Periodically update the standard costs of components, in assembly or production BOMs, and roll the new costs up to the parent item.</span></span>|[<span data-ttu-id="5b6d6-122">Mise à jour des coûts standard</span><span class="sxs-lookup"><span data-stu-id="5b6d6-122">Update Standard Costs</span></span>](finance-how-to-update-standard-costs.md)|
|<span data-ttu-id="5b6d6-123">Effectuer un contrôle de fin d'exercice et des tâches de création de rapports, comme le calcul de l'inventaire et le report des coûts dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-123">Perform period-end control and reporting tasks, such calculate the value of inventory and post costs to the general ledger.</span></span>|[<span data-ttu-id="5b6d6-124">Génération de rapports sur les coûts et rapprochement avec le grand livre</span><span class="sxs-lookup"><span data-stu-id="5b6d6-124">Reporting Costs and Reconciling with the General Ledger</span></span>](finance-report-costs-and-reconcile-with-the-general-ledger.md)|  
|<span data-ttu-id="5b6d6-125">En savoir plus sur les mécanismes dans le système d'évaluation.</span><span class="sxs-lookup"><span data-stu-id="5b6d6-125">Learn about all mechanisms in the costing system.</span></span>|[<span data-ttu-id="5b6d6-126">Détails de conception : stock évaluation stock</span><span class="sxs-lookup"><span data-stu-id="5b6d6-126">Design Details: Inventory Costing</span></span>](design-details-inventory-costing.md)|  

## <a name="see-also"></a><span data-ttu-id="5b6d6-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5b6d6-127">See Also</span></span>  
 [<span data-ttu-id="5b6d6-128">Finance</span><span class="sxs-lookup"><span data-stu-id="5b6d6-128">Finance</span></span>](finance.md)  
 <span data-ttu-id="5b6d6-129">[Stocks](inventory-manage-inventory.md) </span><span class="sxs-lookup"><span data-stu-id="5b6d6-129">[Inventory](inventory-manage-inventory.md) </span></span>  
 <span data-ttu-id="5b6d6-130">[Vente](sales-manage-sales.md) </span><span class="sxs-lookup"><span data-stu-id="5b6d6-130">[Sales](sales-manage-sales.md) </span></span>  
 [<span data-ttu-id="5b6d6-131">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="5b6d6-131">Purchasing</span></span>](purchasing-manage-purchasing.md)  
 <span data-ttu-id="5b6d6-132">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="5b6d6-132">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

