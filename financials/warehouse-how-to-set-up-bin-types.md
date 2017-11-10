---
title: "Procédure : configurer des types de zone | Microsoft Docs"
description: "Vous pouvez diriger la circulation des articles vers les emplacements que vous avez définis pour des activités entrepôt particulières. Vous attribuez à chaque zone des activités de flux de base, et définissez de cette façon la manière dont une zone est utilisée, en lui affectant un type."
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
ms.openlocfilehash: aaa710de292e7f4bd7bfd32238160b332f24cad3
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-bin-types"></a><span data-ttu-id="866ee-104">Procédure : configurer des types de zones</span><span class="sxs-lookup"><span data-stu-id="866ee-104">How to: Set Up Bin Types</span></span>
<span data-ttu-id="866ee-105">Vous pouvez diriger la circulation des articles vers les emplacements que vous avez définis pour des activités entrepôt particulières.</span><span class="sxs-lookup"><span data-stu-id="866ee-105">You can direct the flow of items through bins that you have defined for particular warehouse activities.</span></span> <span data-ttu-id="866ee-106">Vous attribuez à chaque zone des activités de flux de base, et définissez de cette façon la manière dont une zone est utilisée, en lui affectant un type.</span><span class="sxs-lookup"><span data-stu-id="866ee-106">You give each bin its basic flow activities, and thereby define the way the way a bin is used, by assigning it a bin type.</span></span>  

<span data-ttu-id="866ee-107">Il existe huit types de zones.</span><span class="sxs-lookup"><span data-stu-id="866ee-107">There are eight bin types.</span></span> <span data-ttu-id="866ee-108">Votre entrepôt peut fonctionner avec la totalité de ces huit types de zones, mais vous pouvez également décider de n'utiliser que les types RÉCEPT., RANGPRÉLÈV., LIVR. et CQ.</span><span class="sxs-lookup"><span data-stu-id="866ee-108">You can operate your warehouse with all of the eight possible bin types, or you can choose to operate with just the RECEIVE, PUTPICK, SHIP and QC bin types.</span></span> <span data-ttu-id="866ee-109">Ces quatre types de zones permettent à des propositions relatives à la prise en charge du flux des articles d'être effectuées et vous permettent d'enregistrer les différences d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="866ee-109">These four bin types enable suggestions to be made that support the flow of items and allow you to record inventory discrepancies.</span></span>  

## <a name="to-set-up-the-bin-types-you-want-to-use"></a><span data-ttu-id="866ee-110">Pour configurer les types de zones que vous souhaitez utiliser</span><span class="sxs-lookup"><span data-stu-id="866ee-110">To set up the bin types you want to use</span></span>  
1.  <span data-ttu-id="866ee-111">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Types zone**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="866ee-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Bin Types**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="866ee-112">Dans la fenêtre **Types zone**, créez un code à 10 caractères pour chaque type de zone.</span><span class="sxs-lookup"><span data-stu-id="866ee-112">In the **Bin Types** window, create a 10-character code for a bin type.</span></span>  
3.  <span data-ttu-id="866ee-113">Sélectionnez les activités qui peuvent être effectuées avec chaque type de zone.</span><span class="sxs-lookup"><span data-stu-id="866ee-113">Select the activities that can be performed with each bin type.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="866ee-114">Les types de zone ne sont applicables qu'en cas d'utilisation d'un prélèvement et d'un rangement suggérés pour votre emplacement.</span><span class="sxs-lookup"><span data-stu-id="866ee-114">Bin types are only applicable if you are using directed put-away and pick for your location.</span></span>  

<span data-ttu-id="866ee-115">Le type de zone ne définit que la manière dont une zone donnée est utilisée lors du traitement du flux d'articles dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="866ee-115">The bin type determines only how a bin is used when processing the flow of items through the warehouse.</span></span> <span data-ttu-id="866ee-116">Vous pouvez toujours remplacer les propositions d'un document entrepôt, et vous pouvez également placer ou prendre des articles dans une zone en réalisant un mouvement entrepôt.</span><span class="sxs-lookup"><span data-stu-id="866ee-116">You can always override the suggestions for any warehouse document, and you can move items in or out of any bin by performing a warehouse movement.</span></span>  

<span data-ttu-id="866ee-117">Les types de zones que vous pouvez créer sont répertoriés ci-après.</span><span class="sxs-lookup"><span data-stu-id="866ee-117">The bin types that you can create are listed below.</span></span>  

|<span data-ttu-id="866ee-118">Type zone</span><span class="sxs-lookup"><span data-stu-id="866ee-118">Bin Type</span></span>|<span data-ttu-id="866ee-119">Description</span><span class="sxs-lookup"><span data-stu-id="866ee-119">Description</span></span>|  
|------------------|---------------------------------------|  
|<span data-ttu-id="866ee-120">RECEPT.</span><span class="sxs-lookup"><span data-stu-id="866ee-120">RECEIVE</span></span>|<span data-ttu-id="866ee-121">Les articles enregistrés en tant que réceptions reportées, mais pas encore rangées.</span><span class="sxs-lookup"><span data-stu-id="866ee-121">Items registered as posted receipts but not yet put away.</span></span>|  
|<span data-ttu-id="866ee-122">LIVR.</span><span class="sxs-lookup"><span data-stu-id="866ee-122">SHIP</span></span>|<span data-ttu-id="866ee-123">Les articles prélevés pour des lignes livraison entrepôt, mais pas encore reportés en tant qu'articles livrés.</span><span class="sxs-lookup"><span data-stu-id="866ee-123">Items picked for warehouse shipment lines but not yet posted as shipped.</span></span>|  
|<span data-ttu-id="866ee-124">RANG.</span><span class="sxs-lookup"><span data-stu-id="866ee-124">PUT AWAY</span></span>|<span data-ttu-id="866ee-125">Généralement, les articles devant être stockés dans de grandes unités de mesure, mais auxquels vous ne souhaitez pas accéder à des fins de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="866ee-125">Typically, items to be stored in large units of measure but that you do not want to access for picking purposes.</span></span> <span data-ttu-id="866ee-126">Étant donné que ces zones ne sont pas utilisées pour le prélèvement, que ce soit pour des bons de production ou des livraisons, l'utilisation d'une zone de type Rangement risque d'être limitée, mais ce type de zone peut se révéler utile si vous avez acheté une grande quantité d'articles.</span><span class="sxs-lookup"><span data-stu-id="866ee-126">Because these bins are not used for picking, either for production orders or shipments, your use of a Put Away type bin might be limited, but this bin type could be useful if you have purchased a large quantity of items.</span></span> <span data-ttu-id="866ee-127">La priorité des zones de ce type doit toujours être peu élevée. Ainsi, lors du rangement des articles reçus, ce sont les zones RANGPRÉLÈV. de priorité plus élevée associés à l'article concerné qui sont rangées en premier lieu.</span><span class="sxs-lookup"><span data-stu-id="866ee-127">Bins of this type should always have a low bin-ranking, so that when received items are put away, other higher-ranking PUTPICK bins fixed to the item are put away first.</span></span> <span data-ttu-id="866ee-128">Lorsque vous utilisez ce type de zone, vous devez régulièrement procéder au réapprovisionnement des zones, afin que les articles stockés dans ces zones puissent également être disponibles dans les zones de type RANGPRÉLÈV. ou PRÉLÈV.</span><span class="sxs-lookup"><span data-stu-id="866ee-128">If you are using this type of bin, you must regularly perform bin replenishment so that the items stored in these bins are also available in PUTPICK or PICK type bins.</span></span>|  
|<span data-ttu-id="866ee-129">PRELEV.</span><span class="sxs-lookup"><span data-stu-id="866ee-129">PICK</span></span>|<span data-ttu-id="866ee-130">Les articles devant être utilisés uniquement pour des prélèvements (par exemple, des articles dont la date d'expiration est proche et que vous avez déplacés dans ce type de zone).</span><span class="sxs-lookup"><span data-stu-id="866ee-130">Items to be used only for picking, for example, for items with an approaching expiration date that you have moved into this type of bin.</span></span> <span data-ttu-id="866ee-131">Attribuez un classement élevé à ces zones afin qu'elles soient proposées en premier pour le prélèvement.</span><span class="sxs-lookup"><span data-stu-id="866ee-131">You would place a high bin ranking on these bins so they are suggested for picking first.</span></span>|  
|<span data-ttu-id="866ee-132">RGMT/PRLVT</span><span class="sxs-lookup"><span data-stu-id="866ee-132">PUTPICK</span></span>|<span data-ttu-id="866ee-133">Articles dans des zones qui sont proposés à la fois pour les fonctions de rangement et de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="866ee-133">Items in bins that are suggested for both the put-away and pick functions.</span></span> <span data-ttu-id="866ee-134">Les emplacements de ce type ont vraisemblablement un classement différent.</span><span class="sxs-lookup"><span data-stu-id="866ee-134">Bins of this type probably have different bin rankings.</span></span> <span data-ttu-id="866ee-135">Vous pouvez configurer vos zones de stockage en vrac comme ce type de zone avec un classement peu élevé par rapport à vos zones prélèvement ordinaires ou vos zones prélèvement en aval.</span><span class="sxs-lookup"><span data-stu-id="866ee-135">You can set up your bulk storage bins as this type of bin with low bin rankings compared to your ordinary pick bins or forward picking area bins.</span></span>|  
|<span data-ttu-id="866ee-136">CQ</span><span class="sxs-lookup"><span data-stu-id="866ee-136">QC</span></span>|<span data-ttu-id="866ee-137">Cet emplacement est utilisé pour des ajustements stock, si vous le spécifiez sur la fiche magasin dans le champ **Code empl. ajustement**.</span><span class="sxs-lookup"><span data-stu-id="866ee-137">This bin is used for inventory adjustments if you specify this bin on the location card in the **Adjustment Bin Code** field.</span></span> <span data-ttu-id="866ee-138">Vous pouvez également configurer des emplacements de ce type pour des articles défectueux ou en cours de contrôle.</span><span class="sxs-lookup"><span data-stu-id="866ee-138">You can also set up bins of this type for defective items and items being inspected.</span></span> <span data-ttu-id="866ee-139">Vous pouvez déplacer des articles vers ce type de zone afin que le flux habituel des articles ne puisse pas y accéder.</span><span class="sxs-lookup"><span data-stu-id="866ee-139">You can move items to this type of bin if you want to make them inaccessible to the usual item flow.</span></span><br /><br /> <span data-ttu-id="866ee-140">**NOTE :** contrairement à tous les autres types d'emplacement, les cases à cocher pour le traitement des articles sont toutes désactivées par défaut pour le type **CQ**.</span><span class="sxs-lookup"><span data-stu-id="866ee-140">**NOTE:** Unlike all other bin types, the **QC** bin type has none of the item handling check boxes selected by default.</span></span> <span data-ttu-id="866ee-141">Cela signifie que tout contenu que vous placez dans une zone de type CQ est exclu des flux d'articles.</span><span class="sxs-lookup"><span data-stu-id="866ee-141">This indicates that any content you place in a QC bin is excluded from item flows.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="866ee-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="866ee-142">See Also</span></span>
[<span data-ttu-id="866ee-143">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="866ee-143">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="866ee-144">Stock</span><span class="sxs-lookup"><span data-stu-id="866ee-144">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="866ee-145">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="866ee-145">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="866ee-146">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="866ee-146">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="866ee-147">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="866ee-147">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="866ee-148">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="866ee-148">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
