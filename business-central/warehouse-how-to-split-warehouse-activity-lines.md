---
title: "Comment répartir des lignes activité entrepôt | Microsoft Docs"
description: "Dans le cadre de rangements, mouvements ou prélèvements entrepôt et de rangements et prélèvements inventaire, des zones sont proposées pour le prélèvement et le rangement des articles. Il arrive parfois que la quantité réelle disponible dans la zone soit insuffisante ou que l'espace de la zone proposé soit insuffisant pour le rangement de la quantité nécessaire. Dans ces cas, vous devez répartir la ligne de telle sorte que les articles d'une ligne soient prélevés ou placés dans plusieurs zones."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/16/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: dfb633ef874b77a3cf6060311f0bcbbf66e05102
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="split-warehouse-activity-lines"></a><span data-ttu-id="10e45-105">Répartir des lignes activité entrepôt</span><span class="sxs-lookup"><span data-stu-id="10e45-105">Split Warehouse Activity Lines</span></span>
<span data-ttu-id="10e45-106">Dans le cadre de rangements, mouvements ou prélèvements entrepôt et de rangements et prélèvements inventaire, des zones sont proposées pour le prélèvement et le rangement des articles.</span><span class="sxs-lookup"><span data-stu-id="10e45-106">In warehouse put-aways, movements, or picks, and in inventory put-aways and inventory picks, bins are suggested for the picking or putting away of items.</span></span> <span data-ttu-id="10e45-107">Il arrive parfois que la quantité réelle disponible dans la zone soit insuffisante ou que l'espace de la zone proposé soit insuffisant pour le rangement de la quantité nécessaire.</span><span class="sxs-lookup"><span data-stu-id="10e45-107">The actual quantity in the bin suggested may not be sufficient, or there is not enough room in the suggested bin to put away the required quantity.</span></span> <span data-ttu-id="10e45-108">Dans ces cas, vous devez répartir la ligne de telle sorte que les articles d'une ligne soient prélevés ou placés dans plusieurs zones.</span><span class="sxs-lookup"><span data-stu-id="10e45-108">In these cases, you need to split the line, so that the items for one line are either taken from or placed into more than one bin.</span></span>  

<span data-ttu-id="10e45-109">La procédure suivante s'applique aux documents entrepôt, à savoir les lignes de rangement, de mouvement et de prélèvement entrepôt, ainsi que les lignes de rangement, de mouvement et de prélèvement inventaire.</span><span class="sxs-lookup"><span data-stu-id="10e45-109">The following procedure applies to warehouse documents, such as warehouse put-away, movement, and pick lines, or inventory put-away, movement, and pick lines.</span></span>  

## <a name="to-split-warehouse-activity-lines"></a><span data-ttu-id="10e45-110">Pour éclater des lignes activité entrepôt</span><span class="sxs-lookup"><span data-stu-id="10e45-110">To split warehouse activity lines</span></span>  
1.  <span data-ttu-id="10e45-111">Ouvrez une ligne activité entrepôt dans laquelle vous tentez de traiter une quantité insuffisante.</span><span class="sxs-lookup"><span data-stu-id="10e45-111">Open a warehouse activity line where you are trying to handle an insufficient quantity.</span></span>  
2.  <span data-ttu-id="10e45-112">Dans le champ **Quantité à traiter**, entrez la quantité réduite que vous pouvez gérer.</span><span class="sxs-lookup"><span data-stu-id="10e45-112">In the **Qty. to Handle** field, enter the reduced quantity that you are able to handle.</span></span>  
3.  <span data-ttu-id="10e45-113">Sur le raccourci **Lignes**, choisissez l'action **Actions**, choisissez **Fonctions**, puis choisissez l'action **Eclater ligne**.</span><span class="sxs-lookup"><span data-stu-id="10e45-113">On the **Lines** FastTab, choose the **Actions** action, choose the **Functions** action, and then choose the **Split Line** action.</span></span> <span data-ttu-id="10e45-114">Une nouvelle ligne s'affiche. Il s'agit d'une copie de la ligne d'origine, à la différence près que la quantité que vous avez retirée de la ligne d'origine figure dans le champ **Quantité à traiter**.</span><span class="sxs-lookup"><span data-stu-id="10e45-114">A new line appears, which is a copy of the original line, except that the **Qty. to Handle** field contains the quantity that you removed from the original line.</span></span>  
4.  <span data-ttu-id="10e45-115">Affectez à cette nouvelle ligne une zone appropriée et, en cas d'utilisation d'un prélèvement et d'un rangement suggérés, une zone, ou continuez à répartir la ligne autant de fois que nécessaire jusqu'à ce que vous ayez trouvé des zones appropriées pour toute la quantité.</span><span class="sxs-lookup"><span data-stu-id="10e45-115">Assign an appropriate bin and, if you are using directed put-away and pick, a zone, to this new line, or continue splitting the line as necessary until you find appropriate bins for all of the quantity.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="10e45-116">Si, en cas d'utilisation d'un prélèvement et d'un rangement suggérés dans l'emplacement, vous éclatez les lignes, vous devez bien connaître l'entrepôt et être capable de choisir une zone répondant aux exigences de stockage de l'article et aux exigences générales du document entrepôt.</span><span class="sxs-lookup"><span data-stu-id="10e45-116">If the location uses directed put-away and pick and you split the lines, you must be familiar with the warehouse and be able to choose a bin that matches the storage requirements of the item and that fulfills the general requirements of the warehouse document.</span></span> <span data-ttu-id="10e45-117">Par exemple, vous n'allez pas répartir une ligne d'un document prélèvement et placer certains articles au niveau du stockage en vrac.</span><span class="sxs-lookup"><span data-stu-id="10e45-117">For example, you would not split a line on a pick document and place some items in the bulk storage.</span></span>  

## <a name="see-also"></a><span data-ttu-id="10e45-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="10e45-118">See Also</span></span>  
[<span data-ttu-id="10e45-119">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="10e45-119">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="10e45-120">Stock</span><span class="sxs-lookup"><span data-stu-id="10e45-120">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="10e45-121">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="10e45-121">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="10e45-122">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="10e45-122">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="10e45-123">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="10e45-123">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="10e45-124">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="10e45-124">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
