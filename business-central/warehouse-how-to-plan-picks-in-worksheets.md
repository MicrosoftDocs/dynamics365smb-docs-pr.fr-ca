---
title: "Comment planifier des prélèvements dans des feuilles | Microsoft Docs"
description: "Lorsque l'entrepôt est configuré pour exiger un traitement des prélèvements et des livraisons, le fonctionnement de l'entrepôt peut être établi de telle sorte que les lignes des documents livraison ne soient pas automatiquement transformées en instructions de prélèvement, mais soient plutôt activées sur le journal prélèvement."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 073cc86b9df5845fbce18804756f980649f94081
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="plan-picks-in-worksheets"></a><span data-ttu-id="ab28d-103">Planifier des prélèvements dans la feuille</span><span class="sxs-lookup"><span data-stu-id="ab28d-103">Plan Picks in Worksheets</span></span>
<span data-ttu-id="ab28d-104">Lorsque l'entrepôt est configuré pour exiger un traitement des prélèvements et des livraisons, le fonctionnement de l'entrepôt peut être établi de telle sorte que les lignes des documents livraison ne soient pas automatiquement transformées en instructions de prélèvement, mais soient plutôt activées sur le journal prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ab28d-104">If your warehouse is set up to require both pick and shipment processing, the warehouse can choose to operate so that the lines on shipment documents are not automatically transformed into pick instructions, but are made available instead to the pick worksheet.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="ab28d-105">Si des instructions de prélèvement entrepôt ont déjà été créées et que vous souhaitez les combiner pour former une instruction de prélèvement plus efficace, supprimez les prélèvements entrepôt individuels.</span><span class="sxs-lookup"><span data-stu-id="ab28d-105">If warehouse pick instructions have already been created, and you would like to combine them into one efficient pick instruction, then you must delete the individual warehouse picks.</span></span> <span data-ttu-id="ab28d-106">Les lignes à prélever sont alors listées dans la feuille.</span><span class="sxs-lookup"><span data-stu-id="ab28d-106">The lines to be picked can now be listed in the worksheet.</span></span>  

<span data-ttu-id="ab28d-107">Dans la feuille prélèvement, vous pouvez définir des listes de prélèvement pour les employés de manière à réduire au minimum leurs déplacements lors du prélèvement des articles dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ab28d-107">In the pick worksheet, you can set up pick lists for employees that minimize the time the employee has to move about the warehouse picking items.</span></span> <span data-ttu-id="ab28d-108">Les champs contiennent des informations concernant les quantités d'articles disponibles dans les zones de transbordement. En cas de transbordement, ces champs vous permettent de planifier l'affectation des tâches, car le programme propose toujours en priorité de prélever un article dans une zone de transbordement avant de le prélever dans un autre zone, quelle que soit l'unité de mesure de l'article.</span><span class="sxs-lookup"><span data-stu-id="ab28d-108">There are fields that contain information about the quantities of items available in the cross-dock bins. This is useful in cross docking situations to plan your work assignments, because the program will always propose a pick from a cross-dock bin before any other bin, regardless of the unit of measure.</span></span> <span data-ttu-id="ab28d-109">Les lignes de la feuille peuvent provenir d'un certain nombre de documents sources et être triées par article, numéro tablette, document source, date d'échéance ou adresse de livraison.</span><span class="sxs-lookup"><span data-stu-id="ab28d-109">The lines in the worksheet can come from a number of source documents and be sorted by item, shelf number, source document, due date, or ship-to address.</span></span>  

<span data-ttu-id="ab28d-110">Si vous triez par date d'échéance, vous pouvez choisir d'effacer de la feuille toutes les lignes à l'exception de celles nécessitant un traitement immédiat.</span><span class="sxs-lookup"><span data-stu-id="ab28d-110">If you sort by due date, you can choose to delete from the worksheet all lines except those that need immediate attention.</span></span> <span data-ttu-id="ab28d-111">Les lignes moins urgentes ne sont pas effacées mais renvoyées à la feuille **sélection prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="ab28d-111">The less urgent lines are not deleted as such, but just sent back to the **Pick Selection** worksheet.</span></span> <span data-ttu-id="ab28d-112">Lorsque vous créez le prélèvement, les lignes sont déjà triées par date d'échéance et vous pouvez choisir d'affecter le prélèvement à un employé donné.</span><span class="sxs-lookup"><span data-stu-id="ab28d-112">When you create the pick, the lines have already been sorted by due date, and you can choose to assign the pick to a particular employee.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="ab28d-113">Le prélèvement pour la livraison entrepôt des articles assemblés au document de vente en cours de livraison suit les mêmes étapes que les prélèvements entrepôt ordinaires pour la livraison, comme décrit dans cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="ab28d-113">Picking for warehouse shipment of items that are assembled to the sales order being shipped follows the same steps as for regular warehouse picks for shipment, as described in this topic.</span></span> <span data-ttu-id="ab28d-114">Cependant, le nombre de lignes prélèvement par quantité à livrer peut varier considérablement, car ce sont les composantes qui sont prélevées et non l'élément d'assemblage.</span><span class="sxs-lookup"><span data-stu-id="ab28d-114">However, the number of pick lines per quantity to ship may be many to one because you pick the components, not the assembly item.</span></span>  
>   
>  <span data-ttu-id="ab28d-115">Les lignes prélèvement entrepôt sont créées suivant la valeur du champ **Quantité restante** sur les lignes de l'ordre d'assemblage associé à la ligne document de vente en cours de livraison.</span><span class="sxs-lookup"><span data-stu-id="ab28d-115">The warehouse pick lines are created for the value in the **Remaining Quantity** field on the lines of the assembly order that is linked to the sales order line that is being shipped.</span></span> <span data-ttu-id="ab28d-116">Ceci garantit le prélèvement de toutes les composantes en une seule tâche.</span><span class="sxs-lookup"><span data-stu-id="ab28d-116">This ensures that all components are picked in one action.</span></span>  
>   
>  <span data-ttu-id="ab28d-117">Pour plus d’informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les livraisons entrepôt » dans Livraison entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ab28d-117">For more information, see “Handling Assemble-to-Order Items in Warehouse Shipments” in Warehouse Shipment.</span></span>  
>   
>  <span data-ttu-id="ab28d-118">Pour plus d'informations sur le prélèvement de composantes pour les ordres d'assemblage en général, notamment les situations où l'élément d'assemblage n'est pas dû dans une livraison vente, voir [Prélever pour l'assemblage ou la production dans les configurations de stockage avancées.](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).</span><span class="sxs-lookup"><span data-stu-id="ab28d-118">For information about picking components for assembly orders generally, including situations where the assembly item is not due on a sales shipment, see [Pick for Assembly or Production in Advanced Warehouse Configurations](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).</span></span>  

## <a name="to-plan-picks-in-the-worksheet"></a><span data-ttu-id="ab28d-119">Pour planifier des prélèvements dans la feuille</span><span class="sxs-lookup"><span data-stu-id="ab28d-119">To plan picks in the worksheet</span></span>  
1.  <span data-ttu-id="ab28d-120">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille prélèvement**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ab28d-120">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Pick Worksheet**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ab28d-121">Choisissez l'action **Extraire documents entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="ab28d-121">Choose the **Get Whse. Documents** action.</span></span>  
3.  <span data-ttu-id="ab28d-122">Sélectionnez les livraisons pour lesquelles vous souhaitez préparer un prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ab28d-122">Select the shipments for which you want to prepare a pick.</span></span> <span data-ttu-id="ab28d-123">Vous pouvez à présent opérer un tri ponctuel, qui ne suivra pas l'instruction globale de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ab28d-123">You can now sort the lines to some degree, but the sorting you do here will not be carried through to the pick instruction.</span></span> <span data-ttu-id="ab28d-124">Vous pouvez aussi supprimer certaines lignes pour rendre le prélèvement plus efficace.</span><span class="sxs-lookup"><span data-stu-id="ab28d-124">You can also delete some of the lines to make a more effective pick.</span></span> <span data-ttu-id="ab28d-125">Par exemple, si un certain nombre de lignes comporte des articles situés dans des zones de transbordement, vous pouvez créer un prélèvement pour toutes les lignes associées à ces lignes.</span><span class="sxs-lookup"><span data-stu-id="ab28d-125">For instance, if there are a number of lines with items in cross-dock bins, you might want to create a pick for all the lines associated with these lines.</span></span> <span data-ttu-id="ab28d-126">Les articles transbordés seront livrés, avec les autres articles des livraisons, et les zones de transbordement pourront à nouveau recevoir d'autres articles entrants.</span><span class="sxs-lookup"><span data-stu-id="ab28d-126">The cross-docked items will be shipped, along with the other items on the shipments, and the cross-dock bins will have space for more incoming items.</span></span>  
4.  <span data-ttu-id="ab28d-127">Choisissez l'action **Créer prélèvement**, puis remplissez la fenêtre de demande **Créer prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="ab28d-127">Choose the **Create Pick** action, and fill in the **Create Pick** request window.</span></span> <span data-ttu-id="ab28d-128">Le tri que vous demandez ici organisera les lignes prélèvement que vous créez.</span><span class="sxs-lookup"><span data-stu-id="ab28d-128">The sorting you request here will order the pick lines you create.</span></span> <span data-ttu-id="ab28d-129">Par exemple, vous pouvez créer un prélèvement pour chaque zone et trier les lignes selon le classement de zone au sein de chaque prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ab28d-129">For example, you can create one pick for each zone and sort the lines by bin ranking within each pick.</span></span>  
5.  <span data-ttu-id="ab28d-130">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Prélèvements**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ab28d-130">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Picks**, and then choose the related link.</span></span> <span data-ttu-id="ab28d-131">La fenêtre **Prélèvements** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="ab28d-131">The **Picks** window opens.</span></span>  
6.  <span data-ttu-id="ab28d-132">Vous pouvez à présent trouver le prélèvement affecté que vous venez de créer en sélectionnant le prélèvement doté du numéro le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="ab28d-132">You can now find the pick assignment you just created by selecting the pick with the highest number.</span></span>  
7.  <span data-ttu-id="ab28d-133">Dans ce prélèvement, vous pouvez toujours au besoin modifier le code utilisateur de la personne à qui ce prélèvement est affecté, ainsi que le mode de tri des lignes.</span><span class="sxs-lookup"><span data-stu-id="ab28d-133">In the pick, you can still alter, if necessary, the assigned user ID and the way the lines are sorted.</span></span>  
8.  <span data-ttu-id="ab28d-134">Choisissez l'action **Imprimer** pour imprimer les instructions relatives au prélèvement.</span><span class="sxs-lookup"><span data-stu-id="ab28d-134">Choose the **Print** action to print the pick instructions.</span></span>  
9. <span data-ttu-id="ab28d-135">Une fois le prélèvement exécuté, choisissez l'action **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="ab28d-135">After you have performed the pick, choose the **Register** action.</span></span>  

<span data-ttu-id="ab28d-136">Si la numérotation des zones reflète la disposition de l'entrepôt, les lignes triées par code de zone permettent à la personne qui réalise le prélèvement de prélever les articles nécessaires à plusieurs livraisons en ne réalisant qu'un tour dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ab28d-136">If the bins have been numbered in a way that mirrors the physical layout of the warehouse, the lines sorted by bin code allow the picker to pick for a number of shipments in one round of the warehouse.</span></span> <span data-ttu-id="ab28d-137">L'employé prélève dans chaque zone le nombre d'articles requis pour chaque ligne livraison et les place avec les autres articles en les organisant par livraison.</span><span class="sxs-lookup"><span data-stu-id="ab28d-137">The worker takes the required number of items for each shipment line out of each bin and places them along with the other items for the particular shipment.</span></span> <span data-ttu-id="ab28d-138">L'employé gagne ainsi un temps considérable en prélevant en une fois dans une zone donnée les articles nécessaires à plusieurs livraisons.</span><span class="sxs-lookup"><span data-stu-id="ab28d-138">A picker can save a great deal of time by picking for several shipments in one visit to a bin.</span></span>  

<span data-ttu-id="ab28d-139">Le classement de zone constitue une autre méthode de tri efficace, si l'entrepôt est organisé en fonction du classement de zone plutôt que du code de zone.</span><span class="sxs-lookup"><span data-stu-id="ab28d-139">Another effective sorting option is bin ranking, if the physical layout of the warehouse is more according to bin ranking than bin code.</span></span>  

<span data-ttu-id="ab28d-140">Dans la feuille prélèvement, vous pouvez aussi trier par adresse de livraison, ce qui vous permet d'assembler, puis de livrer en premier les commandes destinées aux clients lointains.</span><span class="sxs-lookup"><span data-stu-id="ab28d-140">In the pick worksheet, you can also sort by ship-to address, enabling you to assemble and ship the orders to far-away customers first.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ab28d-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ab28d-141">See Also</span></span>
[<span data-ttu-id="ab28d-142">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ab28d-142">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="ab28d-143">Stock</span><span class="sxs-lookup"><span data-stu-id="ab28d-143">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="ab28d-144">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="ab28d-144">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="ab28d-145">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="ab28d-145">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="ab28d-146">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ab28d-146">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="ab28d-147">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="ab28d-147">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
