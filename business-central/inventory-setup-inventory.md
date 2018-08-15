---
title: Configuration de l'inventaire| Microsoft Docs
description: "Décrit comment configurer les processus d'inventaire, y compris les acheminements pour le transfert et les emplacements, tels que des entrepôts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 01/12/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 62eee7532e457721430cb31519b5acb23e95bfcb
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="setting-up-inventory"></a><span data-ttu-id="8d152-103">Configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="8d152-103">Setting Up Inventory</span></span>
<span data-ttu-id="8d152-104">Avant de pouvoir gérer les activités entrepôt et les coûts d'inventaire, vous devez configurer les règles et les valeurs qui définissent les stratégies d'inventaire de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="8d152-104">Before you can manage warehouse activities and inventory costing, you must configure the rules and values that define the company's inventory policies.</span></span>

<span data-ttu-id="8d152-105">Vous pouvez fournir un meilleur service clientèle et optimiser votre chaîne d'approvisionnement en organisant votre inventaire à différentes adresses.</span><span class="sxs-lookup"><span data-stu-id="8d152-105">You can provide better customer service and optimize your supply chain by organizing your inventory at different addresses.</span></span> <span data-ttu-id="8d152-106">Vous pouvez ensuite acheter, stocker ou vendre des articles à différents emplacements et transférer l'inventaire entre eux.</span><span class="sxs-lookup"><span data-stu-id="8d152-106">You can then buy, store, or sell items at different locations and transfer inventory between them.</span></span>

<span data-ttu-id="8d152-107">Lorsque vous avez configuré votre inventaire, vous pouvez gérer différents processus associés aux transactions article.</span><span class="sxs-lookup"><span data-stu-id="8d152-107">When you have set up your inventory, you can manage various processes related to item transactions.</span></span> <span data-ttu-id="8d152-108">Pour plus d'informations, voir [Gérer l'inventaire](inventory-manage-inventory.md) et [Gestion d'entrepôt](warehouse-manage-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="8d152-108">For more information, see [Manage Inventory](inventory-manage-inventory.md) and [Warehouse Management](warehouse-manage-warehouse.md).</span></span>

| <span data-ttu-id="8d152-109">À</span><span class="sxs-lookup"><span data-stu-id="8d152-109">To</span></span> | <span data-ttu-id="8d152-110">Voir</span><span class="sxs-lookup"><span data-stu-id="8d152-110">See</span></span> |
| --- | --- |
| <span data-ttu-id="8d152-111">Définissez la configuration générale de l'inventaire, telles que les séries de numéros et comment utiliser des emplacements.</span><span class="sxs-lookup"><span data-stu-id="8d152-111">Define the general inventory setup, such as number series and how to use locations.</span></span> |[<span data-ttu-id="8d152-112">Configurer des informations générales relatives à l'inventaire</span><span class="sxs-lookup"><span data-stu-id="8d152-112">Set Up General Inventory Information</span></span>](inventory-how-setup-general.md) |
|<span data-ttu-id="8d152-113">Configurez un modèle de distribution efficace avec une combinaison de différents emplacements et centres de gestion affectés aux partenaires commerciaux ou aux employés.</span><span class="sxs-lookup"><span data-stu-id="8d152-113">Configure an efficient distribution model with a combination of different locations and responsibility centers assigned to business partners or employees.</span></span>|[<span data-ttu-id="8d152-114">Utiliser les centres de gestion</span><span class="sxs-lookup"><span data-stu-id="8d152-114">Work with Responsibility Centers</span></span>](inventory-responsibility-centers.md)|
| <span data-ttu-id="8d152-115">Organisez votre inventaire dans plusieurs emplacements, y compris des acheminements transfert.</span><span class="sxs-lookup"><span data-stu-id="8d152-115">Organize your inventory at multiple locations, including transfer routes.</span></span> |[<span data-ttu-id="8d152-116">Configurer des emplacements</span><span class="sxs-lookup"><span data-stu-id="8d152-116">Set Up Locations</span></span>](inventory-how-register-new-items.md) |
| <span data-ttu-id="8d152-117">Créer des fiches article pour les articles en inventaire que vous commercialisez.</span><span class="sxs-lookup"><span data-stu-id="8d152-117">Create item cards for inventory items that you trade in.</span></span> |[<span data-ttu-id="8d152-118">Enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="8d152-118">Register New Items</span></span>](inventory-how-register-new-items.md) |
|<span data-ttu-id="8d152-119">Définissez plusieurs unités de mesure pour un article afin de pouvoir l'utiliser comme UOM secondaire, par exemple pour les transactions de ventes, d'achat ou de production.</span><span class="sxs-lookup"><span data-stu-id="8d152-119">Set up multiple units of measure for an item that you can use as alternate UOMs, for example on sales, purchasing, or production transactions.</span></span>|[<span data-ttu-id="8d152-120">Configurer des unités de mesure article</span><span class="sxs-lookup"><span data-stu-id="8d152-120">Set Up Item Units of Measure</span></span>](inventory-how-setup-units-of-measure.md)|
|<span data-ttu-id="8d152-121">En complément des fiches article, enregistrer des informations relatives à vos articles dans un emplacement spécifique ou d'une variante spécifique.</span><span class="sxs-lookup"><span data-stu-id="8d152-121">As a supplement to item cards, record information about your items in a specific location or of a specific variant.</span></span>|[<span data-ttu-id="8d152-122">Configurer des unités de stock</span><span class="sxs-lookup"><span data-stu-id="8d152-122">Set Up Stockkeeping Units</span></span>](inventory-how-to-set-up-stockkeeping-units.md)|
| <span data-ttu-id="8d152-123">Affectez des articles aux catégories et donnez-leur des attributs pour vous aider, vous et vos clients, à trouver des articles.</span><span class="sxs-lookup"><span data-stu-id="8d152-123">Assign items to categories and give them attributes to help you and customers find items.</span></span> |[<span data-ttu-id="8d152-124">Catégoriser des articles</span><span class="sxs-lookup"><span data-stu-id="8d152-124">Categorize Items</span></span>](inventory-how-categorize-items.md) |

## <a name="see-also"></a><span data-ttu-id="8d152-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d152-125">See Also</span></span>
[<span data-ttu-id="8d152-126">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="8d152-126">Managing Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="8d152-127">Gestion des achats</span><span class="sxs-lookup"><span data-stu-id="8d152-127">Managing Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="8d152-128">[Gestion des ventes](sales-manage-sales.md)  </span><span class="sxs-lookup"><span data-stu-id="8d152-128">[Managing Sales](sales-manage-sales.md)  </span></span>  
<span data-ttu-id="8d152-129">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="8d152-129">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="8d152-130">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="8d152-130">General Business Functionality</span></span>](ui-across-business-areas.md)
