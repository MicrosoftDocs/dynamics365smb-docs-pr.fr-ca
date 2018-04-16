---
title: "Procédure : configurer des unités de stock | Microsoft Docs"
description: "Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné."
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
ms.sourcegitcommit: acef03f32124c5983846bc6ed0c4d332c9c8b347
ms.openlocfilehash: aa25b3b809b27160f1493408fc8f61f14b651b67
ms.contentlocale: fr-ca
ms.lasthandoff: 04/16/2018

---
# <a name="set-up-stockkeeping-units"></a><span data-ttu-id="f5ab9-103">Configurer des unités de stock</span><span class="sxs-lookup"><span data-stu-id="f5ab9-103">Set Up Stockkeeping Units</span></span>
<span data-ttu-id="f5ab9-104">Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-104">You can use stockkeeping units to record information about your items for a specific location or a specific variant code.</span></span>  

 <span data-ttu-id="f5ab9-105">Les points de stock représentent un supplément des fiches article.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-105">Stockkeeping units are a supplement to item cards.</span></span> <span data-ttu-id="f5ab9-106">Ils ne les remplacent pas, bien qu'ils soient liés à ces documents.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-106">They do not replace them, although they are related to them.</span></span> <span data-ttu-id="f5ab9-107">Les unités de stock vous permettent de différencier des informations relatives à un article pour un emplacement donné, comme un entrepôt ou un centre de distribution, ou une variante donnée, comme plusieurs numéros de tablette et plusieurs informations de réapprovisionnement, pour un même article.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-107">Stockkeeping units allow you to differentiate information about an item for a specific location, such as a warehouse or distribution center, or a specific variant, such as different shelf numbers and different replenishment information, for the same item.</span></span>  

## <a name="to-set-up-a-stockkeeping-unit"></a><span data-ttu-id="f5ab9-108">Pour configurer une unité de stock</span><span class="sxs-lookup"><span data-stu-id="f5ab9-108">To set up a stockkeeping unit</span></span>  

1. <span data-ttu-id="f5ab9-109">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Unités de stock**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-109">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Stockkeeping Units**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f5ab9-110">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-110">Choose the **New** action.</span></span>  
3. <span data-ttu-id="f5ab9-111">Renseignez les champs de la fiche.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-111">Fill in the fields on the card.</span></span> <span data-ttu-id="f5ab9-112">Les champs suivants sont nécessaires : **N° article**, **Code d'emplacement** et/ou **Code variante**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-112">The following fields are required: **Item No.**, **Location Code**, and/or **Variant Code**.</span></span> [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

<span data-ttu-id="f5ab9-113">Après avoir configuré la première unité de stock pour un article, la case à cocher **Unité de stock existante** sur la fiche **Article** est activée.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-113">When you have set up the first stockkeeping unit for an item, the **Stockkeeping Unit Exists** check box on the **Item** card is selected.</span></span>  

<span data-ttu-id="f5ab9-114">Pour créer plusieurs points de stock pour un article, utilisez le traitement par lots **Créer point de stock**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-114">To create several stockkeeping units for an item, use the **Create Stockkeeping Unit** batch job.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="f5ab9-115">Les informations de la fiche **Point de stock** sont prioritaires par rapport à celles de la fiche **Article**.</span><span class="sxs-lookup"><span data-stu-id="f5ab9-115">The information on the **Stockkeeping Unit** card has priority over the **Item** card.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f5ab9-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f5ab9-116">See Also</span></span>  
[<span data-ttu-id="f5ab9-117">Enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="f5ab9-117">Register New Items</span></span>](inventory-how-register-new-items.md)  
[<span data-ttu-id="f5ab9-118">Configuration de la gestion des entrepôts</span><span class="sxs-lookup"><span data-stu-id="f5ab9-118">Setting Up Warehouse Management</span></span>](warehouse-setup-warehouse.md)  
[<span data-ttu-id="f5ab9-119">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f5ab9-119">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="f5ab9-120">Stock</span><span class="sxs-lookup"><span data-stu-id="f5ab9-120">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="f5ab9-121">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="f5ab9-121">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="f5ab9-122">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f5ab9-122">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="f5ab9-123">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f5ab9-123">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

