---
title: "Procédure : calculer le réapprovisionnement de la zone | Microsoft Docs"
description: "Lorsque l'emplacement est configuré pour utiliser le prélèvement et le rangement suggérés, les priorités du modèle de rangement de l'emplacement sont prises en compte lors du rangement des réceptions."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 9296fe5b8773d894fe76a2e87271f139cb3b2b91
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="calculate-bin-replenishment"></a><span data-ttu-id="9c864-103">Calculer le réapprovisionnement de la zone</span><span class="sxs-lookup"><span data-stu-id="9c864-103">Calculate Bin Replenishment</span></span>
<span data-ttu-id="9c864-104">Lorsque l'emplacement est configuré pour utiliser le prélèvement et le rangement suggérés, les priorités du modèle de rangement de l'emplacement sont prises en compte lors du rangement des réceptions.</span><span class="sxs-lookup"><span data-stu-id="9c864-104">When the location is set up to use directed put-away and pick, priorities of the put-away template for the location are taken into account when putting receipts away.</span></span> <span data-ttu-id="9c864-105">Les priorités incluent les quantités minimale et maximale du contenu de la zone qui ont été définies pour une zone particulière, ainsi que les classements de zone.</span><span class="sxs-lookup"><span data-stu-id="9c864-105">Priorities include the minimum and maximum quantities of bin content that have been fixed for a particular bin, and the bin rankings.</span></span> <span data-ttu-id="9c864-106">Par conséquent, si des articles arrivent régulièrement, les zones prélèvement les plus utilisées sont remplies dès qu'elles sont vides.</span><span class="sxs-lookup"><span data-stu-id="9c864-106">Therefore, if items are arriving at a steady pace, the most-used pick bins will be filled up as they are emptied.</span></span>  

<span data-ttu-id="9c864-107">Cependant, les articles en inventaire n'arrivent pas toujours de manière régulière.</span><span class="sxs-lookup"><span data-stu-id="9c864-107">But inventory does not always arrive in a steady trickle.</span></span> <span data-ttu-id="9c864-108">Parfois, votre compagnie achète des articles en grande quantité afin d'obtenir un escompte de paiement ou votre unité de mesure de production fabrique un article en grande quantité afin de réduire le coût unitaire.</span><span class="sxs-lookup"><span data-stu-id="9c864-108">Sometimes, items are purchased in large quantities so that the company can obtain a rebate, or your production unit might produce a lot of one item to achieve a low unit cost.</span></span> <span data-ttu-id="9c864-109">L'entrepôt ne reçoit aucun article pendant un certain temps et doit périodiquement déplacer des articles de zones de stockage en vrac vers des emplacements prélèvement.</span><span class="sxs-lookup"><span data-stu-id="9c864-109">Then items will not be received in the warehouse again for some time, and the warehouse needs to periodically move items to pick bins from bulk storage areas.</span></span>  

<span data-ttu-id="9c864-110">Il se peut aussi que l'entrepôt attende l'arrivée imminente d'un nouveau stock et veuille vider la zone de stockage en vrac des articles avant l'arrivée de la nouvelle marchandise.</span><span class="sxs-lookup"><span data-stu-id="9c864-110">It could also be that the warehouse is expecting new stock to arrive soon and wants to empty the bulk storage area of items before the new merchandise arrives.</span></span>  

<span data-ttu-id="9c864-111">Enfin, si vous avez défini vos zones stockage en vrac avec une action de type de zone **Rangement** uniquement c'est à dire que l'action **Prélèvement** n'est pas sélectionnée pour le type de zone, vos zones prélèvement doivent toujours être réapprovisionnées, étant donné que les zones de type Rangement ne sont pas proposées pour un prélèvement d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="9c864-111">Finally, if you have defined your bulk storage bins with a bin type action **Put Away** only, that is, the bin type does not have the **Pick** action selected, you must always keep your pick bins replenished, since Put Away-type bins are not suggested for a pick of inventory.</span></span>  

## <a name="to-replenish-pick-bins"></a><span data-ttu-id="9c864-112">Pour réapprovisionner des emplacements prélèvement</span><span class="sxs-lookup"><span data-stu-id="9c864-112">To replenish pick bins</span></span>  
1.  <span data-ttu-id="9c864-113">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille mouvement**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9c864-113">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Movement Worksheet**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="9c864-114">Choisissez l'action **Calculer réappro. zone** pour ouvrir la page de demande de rapport.</span><span class="sxs-lookup"><span data-stu-id="9c864-114">Choose the **Calculate Bin Replenishment** action to open the report request page.</span></span>  
3.  <span data-ttu-id="9c864-115">Renseignez le formulaire de demande du traitement en lot pour limiter la portée des propositions de réapprovisionnement qui sera calculée.</span><span class="sxs-lookup"><span data-stu-id="9c864-115">Fill in the batch job request window to limit the scope of the replenishment suggestions that will be calculated.</span></span> <span data-ttu-id="9c864-116">Par exemple, vous pouvez vous intéresser à des articles, des zones ou des emplacements particuliers.</span><span class="sxs-lookup"><span data-stu-id="9c864-116">For example, you might be concerned with particular items, zones, or bins.</span></span>  
4.  <span data-ttu-id="9c864-117">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c864-117">Choose the **OK** button.</span></span> <span data-ttu-id="9c864-118">Des lignes sont créées pour les mouvements réapprovisionnement devant être effectués en fonction des règles configurées pour les emplacements et leur contenu, c'est à dire des articles.</span><span class="sxs-lookup"><span data-stu-id="9c864-118">Lines are created for the replenishment movements that need to be performed according to the rules that have been set up for the bins and bin contents, that is, items in bins.</span></span>  
5.  <span data-ttu-id="9c864-119">Pour effectuer tous les réapprovisionnements proposés, choisissez l'action **Créer mouvement**.</span><span class="sxs-lookup"><span data-stu-id="9c864-119">If you want to perform all the suggested replenishments, choose the **Create Movement** action.</span></span> <span data-ttu-id="9c864-120">Les employés peuvent maintenant consulter les instructions à partir de l'élément de menu **Mouvements**, puis les exécuter et les enregistrer.</span><span class="sxs-lookup"><span data-stu-id="9c864-120">Employees can now find instructions in the **Movements** menu item, carry them out and register them.</span></span>  
6.  <span data-ttu-id="9c864-121">Si vous ne souhaitez exécuter que certaines propositions, supprimez les lignes moins importantes, puis créez un mouvement.</span><span class="sxs-lookup"><span data-stu-id="9c864-121">If you only want some of the suggestions to be performed, delete the lines that are less important and then create a movement.</span></span>  

<span data-ttu-id="9c864-122">Lorsque vous calculez un nouvel approvisionnement zone, les propositions supprimées seront recréées si elles sont toujours valides.</span><span class="sxs-lookup"><span data-stu-id="9c864-122">The next time you calculate bin replenishment, the suggestions that you have deleted will be recreated, if they are still valid at that time.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="9c864-123">Si un article répond aux conditions suivantes :</span><span class="sxs-lookup"><span data-stu-id="9c864-123">If the following conditions are met for an item:</span></span>  
>   
>  -   <span data-ttu-id="9c864-124">l'article a une date d'expiration et</span><span class="sxs-lookup"><span data-stu-id="9c864-124">The item has an expiration date, and</span></span>  
> -   <span data-ttu-id="9c864-125">Le champ **Prélèvement selon FEFO** sur la fiche magasin doit être sélectionné, et</span><span class="sxs-lookup"><span data-stu-id="9c864-125">The **Pick According to FEFO** field on the location card is selected, and</span></span>  
> -   <span data-ttu-id="9c864-126">Vous utilisez la fonction **Calculer réappro. emplacement**,</span><span class="sxs-lookup"><span data-stu-id="9c864-126">You use the **Calculate Bin Replenishment** functionality</span></span>  
>   
>  <span data-ttu-id="9c864-127">alors les champs **De zone** et **D'emplacement** sont vides, car l'algorithme qui permet de calculer d'où déplacer les articles est déclenché uniquement lorsque vous activez la fonction **Créer mouvement**.</span><span class="sxs-lookup"><span data-stu-id="9c864-127">then the **From Zone** and **From Bin** fields will be blank because the algorithm to calculate from where to move the items is triggered only when you activate the **Create Movement** function.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c864-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c864-128">See Also</span></span>  
[<span data-ttu-id="9c864-129">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="9c864-129">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="9c864-130">Prélèvement par FEFO</span><span class="sxs-lookup"><span data-stu-id="9c864-130">Picking by FEFO</span></span>](warehouse-picking-by-fefo.md)  
[<span data-ttu-id="9c864-131">Stock</span><span class="sxs-lookup"><span data-stu-id="9c864-131">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="9c864-132">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="9c864-132">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="9c864-133">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="9c864-133">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="9c864-134">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="9c864-134">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="9c864-135">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="9c864-135">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
