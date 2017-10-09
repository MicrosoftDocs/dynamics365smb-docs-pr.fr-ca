---
title: "Procédure : configurer des agents de livraison | Microsoft Docs"
description: "Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 84a5d9eb8757dc82834c17327ffbb510cd15fa1a
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-shipping-agents"></a><span data-ttu-id="228dc-103">Procédure : configurer des transporteurs</span><span class="sxs-lookup"><span data-stu-id="228dc-103">How to: Set Up Shipping Agents</span></span>
<span data-ttu-id="228dc-104">Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.</span><span class="sxs-lookup"><span data-stu-id="228dc-104">You can set up a code for each of your shipping agents and enter information about them.</span></span>  

<span data-ttu-id="228dc-105">Si vous saisissez une adresse Internet pour l'agent de livraison, et que l'agent de livraison fournit des prestations de traçabilité des colis sur Internet, vous pouvez utiliser la fonction de suivi de colis automatique.</span><span class="sxs-lookup"><span data-stu-id="228dc-105">If you enter an Internet address for the shipping agent, and the agent provides package tracking services on the Internet, you can use the automatic package tracking feature.</span></span> <span data-ttu-id="228dc-106">Pour plus d'informations, voir [Procédure : suivre des colis](sales-how-track-packages.md).</span><span class="sxs-lookup"><span data-stu-id="228dc-106">For more information, see [How to: Track Packages](sales-how-track-packages.md).</span></span>

<span data-ttu-id="228dc-107">Lorsque vous configurez des agents de livraison sur vos documents de vente, vous pouvez également spécifier les services proposés par chaque agent de livraison.</span><span class="sxs-lookup"><span data-stu-id="228dc-107">When you set up shipping agents on your sales orders, you can also specify the services that each shipping agent offers.</span></span>  
<span data-ttu-id="228dc-108">Pour chaque agent de livraison, vous pouvez configurer un nombre illimité de services et spécifier un délai de livraison pour chaque service.</span><span class="sxs-lookup"><span data-stu-id="228dc-108">For each shipping agent, you can set up an unlimited number of services, and you can specify a shipping time for each service.</span></span>  

<span data-ttu-id="228dc-109">Lorsque vous avez affecté une service agent de livraison à une ligne document de vente, le délai de livraison du service est inclus dans le calcul de la promesse de livraison, pour cette ligne.</span><span class="sxs-lookup"><span data-stu-id="228dc-109">When you have assigned a shipping agent service to a sales order line, the shipping time of the service will be included in the order promising calculation, for that line.</span></span> <span data-ttu-id="228dc-110">Pour plus d'informations, voir [Procédure : calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).</span><span class="sxs-lookup"><span data-stu-id="228dc-110">For more information, see [How to: Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).</span></span>

## <a name="to-set-up-a-shipping-agent"></a><span data-ttu-id="228dc-111">Pour configurer un agent de livraison</span><span class="sxs-lookup"><span data-stu-id="228dc-111">To set up a shipping agent</span></span>  
1.  <span data-ttu-id="228dc-112">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Agents de livraison**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="228dc-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Shipping Agents**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="228dc-113">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="228dc-113">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]<span data-ttu-id="228dc-114">.</span><span class="sxs-lookup"><span data-stu-id="228dc-114">.</span></span>  
3.  <span data-ttu-id="228dc-115">Sélectionnez l'action **Services agent de livraison**.</span><span class="sxs-lookup"><span data-stu-id="228dc-115">Choose the **Shipping Agent Services** action.</span></span>
4. <span data-ttu-id="228dc-116">Dans la fenêtre **Services agent de livraison**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="228dc-116">In the **Shipping Agent Services**, fill in the fields as necessary.</span></span>

> [!NOTE]  
>  <span data-ttu-id="228dc-117">Si vous supprimez l'agent de livraison de la ligne commande, le code prestation agent de livraison est également supprimé.</span><span class="sxs-lookup"><span data-stu-id="228dc-117">If you delete the shipping agent on the order line, the shipping agent service code is also deleted.</span></span> <span data-ttu-id="228dc-118">La valeur des champs basée en partie sur la prestation agent de livraison est ensuite recalculée.</span><span class="sxs-lookup"><span data-stu-id="228dc-118">The contents of fields that were based in part on the shipping agent service are recalculated.</span></span>  

## <a name="see-also"></a><span data-ttu-id="228dc-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="228dc-119">See Also</span></span>
<span data-ttu-id="228dc-120">[Procédure : suivre des colis](sales-how-track-packages.md)  </span><span class="sxs-lookup"><span data-stu-id="228dc-120">[How to: Track Packages](sales-how-track-packages.md)  </span></span>  
[<span data-ttu-id="228dc-121">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="228dc-121">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="228dc-122">Stock</span><span class="sxs-lookup"><span data-stu-id="228dc-122">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="228dc-123">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="228dc-123">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="228dc-124">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="228dc-124">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="228dc-125">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="228dc-125">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="228dc-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="228dc-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

