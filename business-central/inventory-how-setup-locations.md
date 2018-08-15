---
title: "Configurer une fiche emplacement et définir des acheminements de transfert| Microsoft Docs"
description: "Vous créez une fiche emplacement pour chaque emplacement où vous stockez des articles d'inventaire, par exemple, un entrepôt ou un centre de distribution, et configurez des acheminements pour le transfert d'articles entre emplacements."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 01/25/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: 7c346455a9e27d7274b116754f1d594484b95d67
ms.openlocfilehash: 45943ef97eee9d6bf24fd679e5dbbab96f5177f8
ms.contentlocale: fr-ca
ms.lasthandoff: 04/18/2018

---
# <a name="set-up-locations"></a><span data-ttu-id="89663-103">Configurer des emplacements</span><span class="sxs-lookup"><span data-stu-id="89663-103">Set Up Locations</span></span>
<span data-ttu-id="89663-104">Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez spécifier chaque emplacement avec une fiche emplacement et définir des acheminements transfert.</span><span class="sxs-lookup"><span data-stu-id="89663-104">If you buy, store, or sell items at more than one place or warehouse, you must set each location up with a location card and define transfer routes.</span></span>

<span data-ttu-id="89663-105">Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements.</span><span class="sxs-lookup"><span data-stu-id="89663-105">You can then create document lines for a specific location, view availability by location, and transfer inventory between locations.</span></span> <span data-ttu-id="89663-106">Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="89663-106">For more information, see [Manage Inventory](inventory-manage-inventory.md).</span></span>

## <a name="to-create-a-location-card"></a><span data-ttu-id="89663-107">Pour créer une fiche emplacement</span><span class="sxs-lookup"><span data-stu-id="89663-107">To create a location card</span></span>
1. <span data-ttu-id="89663-108">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="89663-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.</span></span>
2. <span data-ttu-id="89663-109">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="89663-109">Choose the **New** action.</span></span>
3. <span data-ttu-id="89663-110">Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="89663-110">In the **Location Card** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="89663-111">Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.</span><span class="sxs-lookup"><span data-stu-id="89663-111">Repeat steps 2 and 3 for every location where you want to keep inventory.</span></span>

> [!NOTE]  
> <span data-ttu-id="89663-112">De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement.</span><span class="sxs-lookup"><span data-stu-id="89663-112">Many fields on the location card refer to the handling of items in inbound and outbound warehouse processes.</span></span> <span data-ttu-id="89663-113">Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="89663-113">For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).</span></span>

## <a name="to-create-a-transfer-route"></a><span data-ttu-id="89663-114">Pour créer un acheminement transfert</span><span class="sxs-lookup"><span data-stu-id="89663-114">To create a transfer route</span></span>
1. <span data-ttu-id="89663-115">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="89663-115">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer Routes**, and then choose the related link.</span></span>
2. <span data-ttu-id="89663-116">Sinon, à partir de n'importe quelle fenêtre **Fiche magasin**, cliquez sur **Acheminements transfert**.</span><span class="sxs-lookup"><span data-stu-id="89663-116">Alternatively, from any **Location Card** window, choose the **Transfer Routes** action.</span></span>
3. <span data-ttu-id="89663-117">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="89663-117">Choose the **New** action.</span></span>
4. <span data-ttu-id="89663-118">Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="89663-118">In the **Location Card** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

<span data-ttu-id="89663-119">Vous pouvez à présent transférer des articles en inventaire entre deux emplacements.</span><span class="sxs-lookup"><span data-stu-id="89663-119">You can now transfer inventory items between two locations.</span></span> <span data-ttu-id="89663-120">Pour plus d'informations, voir [Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).</span><span class="sxs-lookup"><span data-stu-id="89663-120">For more information, see [Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md).</span></span>    

## <a name="see-also"></a><span data-ttu-id="89663-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89663-121">See Also</span></span>
[<span data-ttu-id="89663-122">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="89663-122">Manage Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="89663-123">[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)  </span><span class="sxs-lookup"><span data-stu-id="89663-123">[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  </span></span>  
<span data-ttu-id="89663-124">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="89663-124">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="89663-125">Modification des fonctionnalités affichées</span><span class="sxs-lookup"><span data-stu-id="89663-125">Changing Which Features are Displayed</span></span>](ui-experiences.md)  
[<span data-ttu-id="89663-126">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="89663-126">General Business Functionality</span></span>](ui-across-business-areas.md)
