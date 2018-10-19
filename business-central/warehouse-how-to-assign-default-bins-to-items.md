---
title: "Procédure : affecter des zones par défaut à des articles | Microsoft Docs"
description: "Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: e6c6c8a54ae638fa90bca94e43a38d120b5fd3f6
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="assign-default-bins-to-items"></a><span data-ttu-id="707b2-104">Affecter des zones par défaut à des articles</span><span class="sxs-lookup"><span data-stu-id="707b2-104">Assign Default Bins to Items</span></span>
<span data-ttu-id="707b2-105">Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement.</span><span class="sxs-lookup"><span data-stu-id="707b2-105">If you are using bins at a location, assigning default bins to your items can make the process of shipping, receiving, and moving your items much easier.</span></span> <span data-ttu-id="707b2-106">Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article.</span><span class="sxs-lookup"><span data-stu-id="707b2-106">When a default bin is assigned to an item, this bin is suggested every time you initiate a transaction for this item.</span></span> <span data-ttu-id="707b2-107">Les emplacements par défaut sont définis dans la fenêtre **Contenu emplacement**.</span><span class="sxs-lookup"><span data-stu-id="707b2-107">Default bins are defined in the **Bin Content** window.</span></span>  

## <a name="to-assign-a-default-bin-to-an-item"></a><span data-ttu-id="707b2-108">Pour affecter une zone par défaut à un article</span><span class="sxs-lookup"><span data-stu-id="707b2-108">To assign a default bin to an item</span></span>
1.  <span data-ttu-id="707b2-109">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Feuille création contenu de la zone**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="707b2-109">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Content Creation Worksheet**, and choose the related link.</span></span>  
2.  <span data-ttu-id="707b2-110">Renseignez le code de zone et les informations article pour chaque zone que vous souhaitez définir par défaut pour un article.</span><span class="sxs-lookup"><span data-stu-id="707b2-110">Fill in the bin code and item information for each bin that you would like to set up as a default for an item.</span></span> <span data-ttu-id="707b2-111">Veillez à sélectionner le champ **Valeur par défaut**.</span><span class="sxs-lookup"><span data-stu-id="707b2-111">Make sure to select the **Default** field.</span></span>  
3.  <span data-ttu-id="707b2-112">Choisissez l'action **Créer contenu de la zone**.</span><span class="sxs-lookup"><span data-stu-id="707b2-112">Choose the **Create Bin Content** action.</span></span> <span data-ttu-id="707b2-113">Des zones par défaut sont maintenant affectées à votre article.</span><span class="sxs-lookup"><span data-stu-id="707b2-113">Default bins are now assigned for your item.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="707b2-114">Lorsqu'un article est rangé, si une zone par défaut ne lui est pas affectée, la zone dans laquelle l'article est rangé est affectée par défaut.</span><span class="sxs-lookup"><span data-stu-id="707b2-114">When an item is put away, if the item does not have a default bin assigned, the bin where the item is put away is assigned as the default.</span></span>  

## <a name="to-change-the-default-bin-for-an-item"></a><span data-ttu-id="707b2-115">Pour modifier la zone par défaut pour un article</span><span class="sxs-lookup"><span data-stu-id="707b2-115">To change the default bin for an item</span></span>  
<span data-ttu-id="707b2-116">Vous pouvez être amené à modifier l'affectation de la zone par défaut pour un article ou à affecter une zone par défaut à un nouvel article.</span><span class="sxs-lookup"><span data-stu-id="707b2-116">You may need to change the default bin assignment for an item or assign a default bin to a new item.</span></span>    
1.  <span data-ttu-id="707b2-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Contenus de la zone**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="707b2-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Bin Contents**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="707b2-118">Dans le champ **Filtre magasin**, sélectionnez le code emplacement approprié.</span><span class="sxs-lookup"><span data-stu-id="707b2-118">In the **Location Filter** field, select the appropriate location code.</span></span>  
3.  <span data-ttu-id="707b2-119">Recherchez l'écriture indiquant le contenu de la zone par défaut pour cet article et désactivez la case à cocher **Zone par déf.**.</span><span class="sxs-lookup"><span data-stu-id="707b2-119">Find the current default bin content entry for the item and clear the **Default Bin** check box.</span></span>  
4.  <span data-ttu-id="707b2-120">Recherchez la ligne contenu de la zone que vous souhaitez configurer comme étant la nouvelle zone par défaut.</span><span class="sxs-lookup"><span data-stu-id="707b2-120">Find the bin content line for the bin that you would like as the new default bin.</span></span> <span data-ttu-id="707b2-121">Cochez la case **Zone par défaut**.</span><span class="sxs-lookup"><span data-stu-id="707b2-121">Select the **Default Bin** check box.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="707b2-122">Lorsqu'un article est rangé pour la première fois, et si une zone par défaut ne lui est pas affectée, le système lui affecte comme zone par défaut celle dans laquelle l'article est rangé.</span><span class="sxs-lookup"><span data-stu-id="707b2-122">When an item is put away for the first time, and the item does not have a default bin assigned, the system will assign the bin where the item is put away as the default bin for the item.</span></span>  

## <a name="see-also"></a><span data-ttu-id="707b2-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="707b2-123">See Also</span></span>  
[<span data-ttu-id="707b2-124">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="707b2-124">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="707b2-125">Stock</span><span class="sxs-lookup"><span data-stu-id="707b2-125">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="707b2-126">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="707b2-126">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="707b2-127">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="707b2-127">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="707b2-128">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="707b2-128">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="707b2-129">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="707b2-129">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

