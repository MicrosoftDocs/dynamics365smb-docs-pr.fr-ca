---
title: "Configurer une fiche emplacement et définir des acheminements de transfert| Microsoft Docs"
description: "Vous créez une fiche emplacement pour chaque emplacement où vous stockez des articles d'inventaire, par exemple, un entrepôt ou un centre de distribution, et configurez des acheminements pour le transfert d'articles entre emplacements."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 06/02/2017
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 7d82b1c63bb1da367736f8dd044640b583493af8
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-locations"></a><span data-ttu-id="74988-103">Comment configurer des magasins</span><span class="sxs-lookup"><span data-stu-id="74988-103">How to: Set Up Locations</span></span>
<span data-ttu-id="74988-104">Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez spécifier chaque emplacement avec une fiche emplacement et définir des acheminements transfert.</span><span class="sxs-lookup"><span data-stu-id="74988-104">If you buy, store, or sell items at more than one place or warehouse, you must set each location up with a location card and define transfer routes.</span></span>

<span data-ttu-id="74988-105">Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements.</span><span class="sxs-lookup"><span data-stu-id="74988-105">You can then create document lines for a specific location, view availability by location, and transfer inventory between locations.</span></span> <span data-ttu-id="74988-106">Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="74988-106">For more information, see [Manage Inventory](inventory-manage-inventory.md).</span></span>

> [!NOTE]  
>   <span data-ttu-id="74988-107">Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="74988-107">This functionality requires that your experience is set to **Suite**.</span></span> <span data-ttu-id="74988-108">Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="74988-108">For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).</span></span>

## <a name="to-create-a-location-card"></a><span data-ttu-id="74988-109">Pour créer une fiche emplacement</span><span class="sxs-lookup"><span data-stu-id="74988-109">To create a location card</span></span>
1. <span data-ttu-id="74988-110">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="74988-110">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.</span></span>
2. <span data-ttu-id="74988-111">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="74988-111">Choose the **New** action.</span></span>
3. <span data-ttu-id="74988-112">Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="74988-112">In the **Location Card** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="74988-113">Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.</span><span class="sxs-lookup"><span data-stu-id="74988-113">Repeat steps 2 and 3 for every location where you want to keep inventory.</span></span>

> [!NOTE]  
> <span data-ttu-id="74988-114">De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement.</span><span class="sxs-lookup"><span data-stu-id="74988-114">Many fields on the location card refer to the handling of items in inbound and outbound warehouse processes.</span></span> <span data-ttu-id="74988-115">Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="74988-115">For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).</span></span> 

## <a name="to-create-a-transfer-route"></a><span data-ttu-id="74988-116">Pour créer un acheminement transfert</span><span class="sxs-lookup"><span data-stu-id="74988-116">To create a transfer route</span></span>
1. <span data-ttu-id="74988-117">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="74988-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer Routes**, and then choose the related link.</span></span>
2. <span data-ttu-id="74988-118">Sinon, à partir de n'importe quelle fenêtre **Fiche magasin**, cliquez sur **Acheminements transfert**.</span><span class="sxs-lookup"><span data-stu-id="74988-118">Alternatively, from any **Location Card** window, choose the **Transfer Routes** action.</span></span>
3. <span data-ttu-id="74988-119">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="74988-119">Choose the **New** action.</span></span>
4. <span data-ttu-id="74988-120">Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="74988-120">In the **Location Card** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

<span data-ttu-id="74988-121">Vous pouvez à présent transférer des articles en inventaire entre deux emplacements.</span><span class="sxs-lookup"><span data-stu-id="74988-121">You can now transfer inventory items between two locations.</span></span> <span data-ttu-id="74988-122">Pour plus d'informations, voir [Procédure : Transfert de stock entre des magasins](inventory-how-transfer-between-locations.md).</span><span class="sxs-lookup"><span data-stu-id="74988-122">For more information, see [How to: Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md).</span></span>    

## <a name="see-also"></a><span data-ttu-id="74988-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="74988-123">See Also</span></span>
[<span data-ttu-id="74988-124">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="74988-124">Manage Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="74988-125">[Procédure : transfert de stock entre des magasins](inventory-how-transfer-between-locations.md)  </span><span class="sxs-lookup"><span data-stu-id="74988-125">[How to: Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  </span></span>  
<span data-ttu-id="74988-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="74988-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
<span data-ttu-id="74988-127">[Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md)</span><span class="sxs-lookup"><span data-stu-id="74988-127">[Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md)</span></span>  
[<span data-ttu-id="74988-128">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="74988-128">General Business Functionality</span></span>](ui-across-business-areas.md)
