---
title: "Procédure d'utilisation des centres de gestion | Microsoft Docs"
description: "Les centres de gestion permettent de gérer les centres administratifs. Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: b9b6a44463e204dbb5bba012782bea4759f8f396
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="work-with-responsibility-centers"></a><span data-ttu-id="ae190-104">Utiliser les centres de gestion</span><span class="sxs-lookup"><span data-stu-id="ae190-104">Work with Responsibility Centers</span></span>
<span data-ttu-id="ae190-105">Les centres de gestion permettent de gérer les centres administratifs.</span><span class="sxs-lookup"><span data-stu-id="ae190-105">Responsibility centers provide the ability to handle administrative centers.</span></span> <span data-ttu-id="ae190-106">Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie.</span><span class="sxs-lookup"><span data-stu-id="ae190-106">A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center.</span></span> <span data-ttu-id="ae190-107">Un bureau de vente, un département d'achat pour plusieurs emplacements, un bureau de planification d'usine, etc. sont des exemples de centres de gestion.</span><span class="sxs-lookup"><span data-stu-id="ae190-107">Examples of responsibility centers are a sales office, a purchasing department for several locations, and a plant planning office.</span></span> <span data-ttu-id="ae190-108">Par exemple, cette fonctionnalité permet aux compagnies de configurer des vues spécifiques à l'utilisateur des documents vente et achat associés exclusivement à un centre de gestion particulier.</span><span class="sxs-lookup"><span data-stu-id="ae190-108">Using this functionality, for example, companies can set up user-specific views of sales and purchase documents related exclusively to a particular responsibility center.</span></span>  

<span data-ttu-id="ae190-109">L'utilisation de plusieurs emplacements avec des centres de gestion permet de gérer les activités commerciales de façon flexible et optimale.</span><span class="sxs-lookup"><span data-stu-id="ae190-109">Using multiple locations together with responsibility centers provides the ability to manage business operations in the most flexible, yet optimal way.</span></span>

<span data-ttu-id="ae190-110">Des emplacements multiples permettent aux compagnies de gérer leur inventaire dans plusieurs emplacements au moyen d'une seule base de données.</span><span class="sxs-lookup"><span data-stu-id="ae190-110">Multiple locations allows companies to manage their inventory in multiple locations using one database.</span></span> <span data-ttu-id="ae190-111">Deux concepts, des magasins et des points de stock, sont les pierres angulaires du granule.</span><span class="sxs-lookup"><span data-stu-id="ae190-111">Two concepts, locations and stockkeeping units, are the cornerstones of this granule.</span></span> <span data-ttu-id="ae190-112">Un emplacement est défini comme un lieu qui gère l'emplacement physique et la quantité des articles.</span><span class="sxs-lookup"><span data-stu-id="ae190-112">A location is defined as a place that handles physical placement and quantities of items.</span></span> <span data-ttu-id="ae190-113">Le concept est assez étendu pour inclure des magasins tels que les usines ou les unités de fabrication et les centres de distribution, les entrepôts, les magasins d'exposition et les véhicules de service.</span><span class="sxs-lookup"><span data-stu-id="ae190-113">The concept is broad enough to include locations such as plants or production facilities as well as distribution centers, warehouses, showrooms and service vehicles.</span></span> <span data-ttu-id="ae190-114">Une unité de stock est définie comme un article à un emplacement spécifique et/ou comme une variante.</span><span class="sxs-lookup"><span data-stu-id="ae190-114">A stockkeeping unit is defined as an item at a specific location and/or as a variant.</span></span> <span data-ttu-id="ae190-115">Grâce aux unités de stock, les compagnies utilisant plusieurs emplacements peuvent ajouter des informations de réapprovisionnement, des adresses de livraison et des informations financières de report au niveau de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="ae190-115">Using stockkeeping units, companies with multiple locations are able to add replenishment information, addresses, and some financial posting information at the location level.</span></span> <span data-ttu-id="ae190-116">Elles peuvent ainsi réapprovisionner les variantes du même article pour chaque emplacement et commander des articles pour chaque emplacement d'après les informations de réapprovisionnement spécifiques de l'emplacement.</span><span class="sxs-lookup"><span data-stu-id="ae190-116">As a result, they have the ability to replenish variants of the same item for each location as well as to order items for each location on the basis of location-specific replenishment information.</span></span>  

<span data-ttu-id="ae190-117">Les centres de gestion élargissent la fonction de magasins multiples en permettant aux utilisateurs de gérer les centres administratifs.</span><span class="sxs-lookup"><span data-stu-id="ae190-117">Responsibility centers extends the multiple locations functionality by providing users the ability to handle administrative centers.</span></span> <span data-ttu-id="ae190-118">Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie.</span><span class="sxs-lookup"><span data-stu-id="ae190-118">A responsibility center can be a cost center, a profit center, an investment center, or other company-defined administrative center.</span></span> <span data-ttu-id="ae190-119">Un bureau de vente, un département d'achat pour plusieurs emplacements, un bureau de planification d'usine, etc. sont des exemples de centres de gestion.</span><span class="sxs-lookup"><span data-stu-id="ae190-119">Examples of responsibility centers are a sales office, a purchasing department for several locations, and a plant planning office.</span></span> <span data-ttu-id="ae190-120">Par exemple, cette fonctionnalité permet aux compagnies de configurer des vues spécifiques à l'utilisateur des documents vente et achat associés exclusivement à un centre de gestion particulier.</span><span class="sxs-lookup"><span data-stu-id="ae190-120">Using this functionality, for example, companies can set up user-specific views of sales and purchase documents related exclusively to a particular responsibility center.</span></span>

## <a name="to-set-up-a-responsibility-center"></a><span data-ttu-id="ae190-121">Pour configurer un centre de gestion</span><span class="sxs-lookup"><span data-stu-id="ae190-121">To set up a responsibility center</span></span>  
1.  <span data-ttu-id="ae190-122">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Centres de gestion**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ae190-122">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Responsibility Centers**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ae190-123">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="ae190-123">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="ae190-124">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ae190-124">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    <span data-ttu-id="ae190-125">Si vous utilisez des centres de gestion pour administrer votre compagnie, il peut être utile de définir un centre de gestion par défaut pour votre compagnie.</span><span class="sxs-lookup"><span data-stu-id="ae190-125">If you are using responsibility centers to administer your company, it can be useful to have a default responsibility center for your company.</span></span>
4. <span data-ttu-id="ae190-126">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Informations compagnie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ae190-126">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Company Information**, and then choose the related link.</span></span>
5. <span data-ttu-id="ae190-127">Dans le champ **Centre de gestion**, entrez un code centre de gestion.</span><span class="sxs-lookup"><span data-stu-id="ae190-127">In the **Responsibility Center** field, enter a responsibility center code.</span></span>

<span data-ttu-id="ae190-128">Ce code est utilisé sur tous les documents achat, vente ou service si l'utilisateur, le client ou le fournisseur n'a pas de centre de gestion par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae190-128">This code will be used on all purchase, sales, or service documents, if the user, customer, or vendor has no default responsibility center.</span></span> <span data-ttu-id="ae190-129">Sur un document vente, achat ou service, vous pouvez saisir un autre centre de gestion à la place de la valeur par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae190-129">On any sales, purchase, or service document, you can enter another responsibility center than the default.</span></span>

> [!NOTE]  
>  <span data-ttu-id="ae190-130">Lorsque vous saisissez un code centre de gestion sur un document, le programme affecte l'adresse, les axes et les prix indiqués sur le document.</span><span class="sxs-lookup"><span data-stu-id="ae190-130">When you enter a responsibility center code on a document, it affects the address, dimensions, and prices on the document.</span></span>  

## <a name="to-assign-responsibility-centers-to-users"></a><span data-ttu-id="ae190-131">Pour affecter des centres de gestion à des utilisateurs</span><span class="sxs-lookup"><span data-stu-id="ae190-131">To assign responsibility centers to users</span></span>  
<span data-ttu-id="ae190-132">Vous pouvez configurer des utilisateurs de sorte que, dans leurs routines quotidiennes, le programme récupère uniquement les documents propres à leur activité.</span><span class="sxs-lookup"><span data-stu-id="ae190-132">You can set up users so that in their daily routines the program retrieves only the documents relevant for their particular work areas.</span></span> <span data-ttu-id="ae190-133">Les utilisateurs sont généralement associés à un centre de gestion et utilisent uniquement les documents propres à des modules spécifiques de ce centre.</span><span class="sxs-lookup"><span data-stu-id="ae190-133">Users are usually associated with one responsibility center and work only with documents related to specific application areas at that particular center.</span></span>  

<span data-ttu-id="ae190-134">Pour configurer cela, vous devez affecter des centres de gestion à des utilisateurs dans trois modules : Achats, Ventes et Gestion des services.</span><span class="sxs-lookup"><span data-stu-id="ae190-134">To set this up, you assign responsibility centers to users in three functional areas: Purchases, Sales, and Service Management.</span></span>  

1.  <span data-ttu-id="ae190-135">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres utilisateur**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ae190-135">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **User Setup**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ae190-136">Dans la fenêtre **User Setup**, sélectionnez l'utilisateur auquel vous souhaitez affecter un centre de gestion.</span><span class="sxs-lookup"><span data-stu-id="ae190-136">In the **User Setup** window, select the user you want to assign a responsibility center to.</span></span> <span data-ttu-id="ae190-137">Si l'utilisateur ne figure pas dans la liste, saisissez un code utilisateur dans le champ **Code utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ae190-137">If the user not is on the list, you must enter a user ID in the **User ID** field.</span></span>  
3.  <span data-ttu-id="ae190-138">Dans le champ **Filtre centre gestion vente**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux ventes.</span><span class="sxs-lookup"><span data-stu-id="ae190-138">In the **Sales Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to sales.</span></span>  
4.  <span data-ttu-id="ae190-139">Dans le champ **Filtre centre gestion achat**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux achats.</span><span class="sxs-lookup"><span data-stu-id="ae190-139">In the **Purchase Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to purchasing.</span></span>  
5.  <span data-ttu-id="ae190-140">Dans le champ **Filtre centre gestion service**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées à la gestion des services.</span><span class="sxs-lookup"><span data-stu-id="ae190-140">In the **Service Resp. Ctr. Filter** field, enter the responsibility center where the user will have tasks related to service management.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="ae190-141">Les utilisateurs peuvent visualiser toutes les écritures et tous les documents reportés ; ils ne sont pas limités à ceux de leur centre de gestion.</span><span class="sxs-lookup"><span data-stu-id="ae190-141">Users will still be able to view all posted documents and ledger entries, not just those related to their own responsibility center.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae190-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae190-142">See Also</span></span>  
[<span data-ttu-id="ae190-143">Configuration de stock</span><span class="sxs-lookup"><span data-stu-id="ae190-143">Setting Up Inventory</span></span>](inventory-setup-inventory.md)  
<span data-ttu-id="ae190-144">[Configuration de la gestion d'entrepôt](warehouse-setup-warehouse.md)
[Inventaire](inventory-manage-inventory.md)[Gestion d'entrepôt](warehouse-manage-warehouse.md)</span><span class="sxs-lookup"><span data-stu-id="ae190-144">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)
[Inventory](inventory-manage-inventory.md)[Warehouse Management](warehouse-manage-warehouse.md)</span></span>  
<span data-ttu-id="ae190-145">[Gestion d’entrepôt](warehouse-manage-warehouse.md)  </span><span class="sxs-lookup"><span data-stu-id="ae190-145">[Warehouse Management](warehouse-manage-warehouse.md)  </span></span>  
[<span data-ttu-id="ae190-146">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ae190-146">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="ae190-147">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="ae190-147">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
