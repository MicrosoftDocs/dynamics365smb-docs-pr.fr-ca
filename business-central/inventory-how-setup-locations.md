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
ms.date: 10/01/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 828979bf181f1cd7f7a66d2c7c8ac8a2700b732b
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="set-up-locations"></a><span data-ttu-id="e1657-103">Configurer des emplacements</span><span class="sxs-lookup"><span data-stu-id="e1657-103">Set Up Locations</span></span>
<span data-ttu-id="e1657-104">Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez spécifier chaque emplacement avec une fiche emplacement et définir des acheminements transfert.</span><span class="sxs-lookup"><span data-stu-id="e1657-104">If you buy, store, or sell items at more than one place or warehouse, you must set each location up with a location card and define transfer routes.</span></span>

<span data-ttu-id="e1657-105">Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements.</span><span class="sxs-lookup"><span data-stu-id="e1657-105">You can then create document lines for a specific location, view availability by location, and transfer inventory between locations.</span></span> <span data-ttu-id="e1657-106">Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="e1657-106">For more information, see [Manage Inventory](inventory-manage-inventory.md).</span></span>

## <a name="to-create-a-location-card"></a><span data-ttu-id="e1657-107">Pour créer une fiche emplacement</span><span class="sxs-lookup"><span data-stu-id="e1657-107">To create a location card</span></span>
1. <span data-ttu-id="e1657-108">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Emplacements**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e1657-108">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.</span></span>
2. <span data-ttu-id="e1657-109">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e1657-109">Choose the **New** action.</span></span>
3. <span data-ttu-id="e1657-110">Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e1657-110">On the **Location Card** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="e1657-111">Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.</span><span class="sxs-lookup"><span data-stu-id="e1657-111">Repeat steps 2 and 3 for every location where you want to keep inventory.</span></span>

> [!NOTE]  
> <span data-ttu-id="e1657-112">De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement.</span><span class="sxs-lookup"><span data-stu-id="e1657-112">Many fields on the location card refer to the handling of items in inbound and outbound warehouse processes.</span></span> <span data-ttu-id="e1657-113">Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="e1657-113">For more information, see [Setting Up Warehouse Management](warehouse-setup-warehouse.md).</span></span>

## <a name="to-create-a-transfer-route"></a><span data-ttu-id="e1657-114">Pour créer un acheminement transfert</span><span class="sxs-lookup"><span data-stu-id="e1657-114">To create a transfer route</span></span>
1. <span data-ttu-id="e1657-115">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Acheminements transfert**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e1657-115">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer Routes**, and then choose the related link.</span></span>
2. <span data-ttu-id="e1657-116">Sinon, à partir de n'importe quelle page **Fiche emplacement**, cliquez sur **Acheminements transfert**.</span><span class="sxs-lookup"><span data-stu-id="e1657-116">Alternatively, from any **Location Card** page, choose the **Transfer Routes** action.</span></span>
3. <span data-ttu-id="e1657-117">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e1657-117">Choose the **New** action.</span></span>
4. <span data-ttu-id="e1657-118">Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="e1657-118">On the **Location Card** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

<span data-ttu-id="e1657-119">Vous pouvez à présent transférer des articles en inventaire entre deux emplacements.</span><span class="sxs-lookup"><span data-stu-id="e1657-119">You can now transfer inventory items between two locations.</span></span> <span data-ttu-id="e1657-120">Pour plus d'informations, voir [Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).</span><span class="sxs-lookup"><span data-stu-id="e1657-120">For more information, see [Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md).</span></span>    

## <a name="see-also"></a><span data-ttu-id="e1657-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e1657-121">See Also</span></span>
[<span data-ttu-id="e1657-122">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="e1657-122">Manage Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="e1657-123">[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)  </span><span class="sxs-lookup"><span data-stu-id="e1657-123">[Transfer Inventory Between Locations](inventory-how-transfer-between-locations.md)  </span></span>  
<span data-ttu-id="e1657-124">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="e1657-124">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="e1657-125">Modification des fonctionnalités affichées</span><span class="sxs-lookup"><span data-stu-id="e1657-125">Changing Which Features are Displayed</span></span>](ui-experiences.md)  
[<span data-ttu-id="e1657-126">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="e1657-126">General Business Functionality</span></span>](ui-across-business-areas.md)

