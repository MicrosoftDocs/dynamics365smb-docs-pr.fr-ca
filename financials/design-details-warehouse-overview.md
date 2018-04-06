---
title: "Détails de conception - Vue d'ensemble d'entrepôt | Microsoft Docs"
description: "Pour prendre en charge la manipulation physique des articles au niveau des zones, toutes les informations doivent être suivies pour chaque transaction ou mouvement dans l'entrepôt. Ceci est géré dans la table **Écriture entrepôt**. Chaque transaction est enregistrée dans un registre entrepôt."
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
ms.openlocfilehash: f5dc30ab398ae41ab8c36b6c207d2f48036cc98c
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-warehouse-overview"></a><span data-ttu-id="89b75-105">Détails de conception : vue d'ensemble d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="89b75-105">Design Details: Warehouse Overview</span></span>
<span data-ttu-id="89b75-106">Pour prendre en charge la manipulation physique des articles au niveau des zones, toutes les informations doivent être suivies pour chaque transaction ou mouvement dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89b75-106">To support the physical handling of items on the zone and bin level, all information must be traced for each transaction or movement in the warehouse.</span></span> <span data-ttu-id="89b75-107">Ceci est géré dans la table **Écriture entrepôt**.</span><span class="sxs-lookup"><span data-stu-id="89b75-107">This is managed in the **Warehouse Entry** table.</span></span> <span data-ttu-id="89b75-108">Chaque transaction est enregistrée dans un registre entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89b75-108">Each transaction is stored in a warehouse register.</span></span>  

<span data-ttu-id="89b75-109">Les documents entrepôt et un journal entrepôt sont utilisés pour enregistrer des mouvements article dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89b75-109">Warehouse documents and a warehouse journal are used to register item movements in the warehouse.</span></span> <span data-ttu-id="89b75-110">Chaque fois qu'un article dans l'entrepôt est déplacé, reçu, rangé, prélevé, livré ou ajusté, les écritures entrepôt sont enregistrées pour stocker les informations physiques sur les zones et la quantité.</span><span class="sxs-lookup"><span data-stu-id="89b75-110">Every time that an item in the warehouse is moved, received, put away, picked, shipped, or adjusted, warehouse entries are registered to store the physical information about zone, bin, and quantity.</span></span> <span data-ttu-id="89b75-111">Pour plus d'informations, reportez\-vous à [Détails de conception : flux d'enlogement](design-details-outbound-warehouse-flow.md).</span><span class="sxs-lookup"><span data-stu-id="89b75-111">For more information, see [Design Details: Inbound Warehouse Flow](design-details-outbound-warehouse-flow.md).</span></span>  

<span data-ttu-id="89b75-112">La table **Contenu de la zone** est utilisée pour gérer l'ensemble des dimensions du contenu d'un d'une zone par article, par exemple, l'unité de mesure, la quantité maximum et la quantité minimum.</span><span class="sxs-lookup"><span data-stu-id="89b75-112">The **Bin Content** table is used to handle all the different dimensions of the contents of a bin per item, such as unit of measure, maximum quantity, and minimum quantity.</span></span> <span data-ttu-id="89b75-113">La table **Contenu de la zone** affiche également des champs de flux vers les écritures entrepôt, des instructions entrepôt et des lignes journal entrepôt, ce qui garantit que la disponibilité d'un article par zone et d'une zone pour un article peut être calculée rapidement.</span><span class="sxs-lookup"><span data-stu-id="89b75-113">The **Bin Content** table also contains flow fields to the warehouse entries, warehouse instructions, and warehouse journal lines, which ensures that the availability of an item per bin and a bin for an item can be calculated quickly.</span></span> <span data-ttu-id="89b75-114">Pour plus d'informations, voir [Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="89b75-114">For more information, see [Design Details: Availability in the Warehouse](design-details-availability-in-the-warehouse.md).</span></span>  

<span data-ttu-id="89b75-115">Lorsque les reports article se produisent en dehors du module d'entrepôt, une zone d'ajustement par défaut par emplacement est utilisée pour synchroniser des écritures d'entrepôt avec les écritures d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="89b75-115">When item postings occur outside the warehouse module, a default adjustment bin per location is used to synchronize warehouse entries with inventory entries.</span></span> <span data-ttu-id="89b75-116">Au cours de l'inventaire physique de l'entrepôt, toutes les différences entre les quantités calculées et comptées sont enregistrées dans la zone d'ajustement, puis reportées comme correction des écritures articles.</span><span class="sxs-lookup"><span data-stu-id="89b75-116">During physical inventory of the warehouse, any differences between the calculated and counted quantities are recorded in the adjustment bin and then posted as correcting item ledger entries.</span></span> <span data-ttu-id="89b75-117">Pour plus d'informations, voir [Détails de conception : intégration avec l'inventaire](design-details-integration-with-inventory.md).</span><span class="sxs-lookup"><span data-stu-id="89b75-117">For more information, see [Design Details: Integration with Inventory](design-details-integration-with-inventory.md).</span></span>  

<span data-ttu-id="89b75-118">La figure suivante présente les flux d'entrepôt courants.</span><span class="sxs-lookup"><span data-stu-id="89b75-118">The following illustration outlines typical warehouse flows.</span></span>  

<span data-ttu-id="89b75-119">![Vue d'ensemble des processus entrepôt](media/design_details_warehouse_management_overview.png "design_details_warehouse_management_overview")</span><span class="sxs-lookup"><span data-stu-id="89b75-119">![Overview of warehouse processes](media/design_details_warehouse_management_overview.png "design_details_warehouse_management_overview")</span></span>  

## <a name="basic-or-advanced-warehousing"></a><span data-ttu-id="89b75-120">Entreposage de base ou avancé</span><span class="sxs-lookup"><span data-stu-id="89b75-120">Basic or Advanced Warehousing</span></span>  
<span data-ttu-id="89b75-121">La fonctionnalité d'entrepôt dans [!INCLUDE[d365fin](includes/d365fin_md.md)] peut être implémentée à différents niveaux de complexité, selon les processus d'une compagnie et le volume de commande.</span><span class="sxs-lookup"><span data-stu-id="89b75-121">Warehouse functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] can be implemented in different complexity levels, depending on a company’s processes and order volume.</span></span> <span data-ttu-id="89b75-122">La principale différence est que les activités sont effectuées par commande dans l'entreposage de base, alors qu'elles sont regroupées pour plusieurs commandes dans l'entreposage avancé.</span><span class="sxs-lookup"><span data-stu-id="89b75-122">The main difference is that activities are performed order-by-order in basic warehousing when they are consolidated for multiple orders in advanced warehousing.</span></span>  

 <span data-ttu-id="89b75-123">Pour différencier les différents niveaux de complexité, ces documents font référence à deux dénominations générales de base, Basic et Advanced Warehousing.</span><span class="sxs-lookup"><span data-stu-id="89b75-123">To differentiate between the different complexity levels, this documentation refers to two general denominations, Basic and Advanced Warehousing.</span></span> <span data-ttu-id="89b75-124">Cette différenciation simple couvre plusieurs niveaux de complexité différents tels que définis par les granules produit et la configuration de l'emplacement, chacun étant pris en charge par différents documents d'interface utilisateur.</span><span class="sxs-lookup"><span data-stu-id="89b75-124">This simple differentiation covers several different complexity levels as defined by product granules and location setup, each supported by different UI documents.</span></span> <span data-ttu-id="89b75-125">Pour plus d'informations, reportez\-vous à [Détails de conception : Paramètres entrepôt](design-details-warehouse-setup.md).</span><span class="sxs-lookup"><span data-stu-id="89b75-125">For more information, see [Design Details: Warehouse Setup](design-details-warehouse-setup.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="89b75-126">Le niveau le plus avancé de l'entreposage est appelé « Installations WMS » dans cette documentation, étant donné que ce niveau requiert le granule le plus avancé, Warehouse Management Systems (systèmes de gestion d'entrepôt).</span><span class="sxs-lookup"><span data-stu-id="89b75-126">The most advanced level of warehousing is referred to as “WMS installations” in this documentation, since this level requires the most advanced granule, Warehouse Management Systems.</span></span>  

 <span data-ttu-id="89b75-127">Les différents documents de l'interface utilisateur suivants sont utilisés dans l'entreposage de base et avancé.</span><span class="sxs-lookup"><span data-stu-id="89b75-127">The following different UI documents are used in basic and advanced warehousing.</span></span>  

## <a name="basic-ui-documents"></a><span data-ttu-id="89b75-128">Documents de base de l'interface utilisateur</span><span class="sxs-lookup"><span data-stu-id="89b75-128">Basic UI Documents</span></span>  

-   <span data-ttu-id="89b75-129">**Article dans l'inventaire à classer**</span><span class="sxs-lookup"><span data-stu-id="89b75-129">**Inventory Put-away**</span></span>  
-   <span data-ttu-id="89b75-130">**Article en inventaire à prélever**</span><span class="sxs-lookup"><span data-stu-id="89b75-130">**Inventory Pick**</span></span>  
-   <span data-ttu-id="89b75-131">**Mouvement d'inventaire**</span><span class="sxs-lookup"><span data-stu-id="89b75-131">**Inventory Movement**</span></span>  
-   <span data-ttu-id="89b75-132">**Journal article**</span><span class="sxs-lookup"><span data-stu-id="89b75-132">**Item Journal**</span></span>  
-   <span data-ttu-id="89b75-133">**Journal de reclassements d'articles**</span><span class="sxs-lookup"><span data-stu-id="89b75-133">**Item Reclassification Journal**</span></span>  
-   <span data-ttu-id="89b75-134">(Divers rapports)</span><span class="sxs-lookup"><span data-stu-id="89b75-134">(Various reports)</span></span>  

## <a name="advanced-ui-documents"></a><span data-ttu-id="89b75-135">Documents d'interface utilisateur avancés</span><span class="sxs-lookup"><span data-stu-id="89b75-135">Advanced UI Documents</span></span>  

-   <span data-ttu-id="89b75-136">**Réception de l'entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-136">**Warehouse Receipt**</span></span>  
-   <span data-ttu-id="89b75-137">**Feuille rangement**</span><span class="sxs-lookup"><span data-stu-id="89b75-137">**Put-away Worksheet**</span></span>  
-   <span data-ttu-id="89b75-138">**Rangement magasin**</span><span class="sxs-lookup"><span data-stu-id="89b75-138">**Warehouse Put-away**</span></span>  
-   <span data-ttu-id="89b75-139">**Feuille prélèvement**</span><span class="sxs-lookup"><span data-stu-id="89b75-139">**Pick Worksheet**</span></span>  
-   <span data-ttu-id="89b75-140">**Prélèvement magasin**</span><span class="sxs-lookup"><span data-stu-id="89b75-140">**Warehouse Pick**</span></span>  
-   <span data-ttu-id="89b75-141">**Feuille mouvement**</span><span class="sxs-lookup"><span data-stu-id="89b75-141">**Movement Worksheet**</span></span>  
-   <span data-ttu-id="89b75-142">**Mouvement d'entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-142">**Warehouse Movement**</span></span>  
-   <span data-ttu-id="89b75-143">**Prélèvement interne entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-143">**Internal Whse. Pick**</span></span>  
-   <span data-ttu-id="89b75-144">**Rangement interne entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-144">**Internal Whse. Put-away**</span></span>  
-   <span data-ttu-id="89b75-145">**Feuille de création de zone**</span><span class="sxs-lookup"><span data-stu-id="89b75-145">**Bin Creation Worksheet**</span></span>  
-   <span data-ttu-id="89b75-146">**Feuille de création du contenu de la zone**</span><span class="sxs-lookup"><span data-stu-id="89b75-146">**Bin Content Creation Worksheet**</span></span>  
-   <span data-ttu-id="89b75-147">**Journal article entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-147">**Whse. Item Journal**</span></span>  
-   <span data-ttu-id="89b75-148">**Journal reclassement article entrepôt**</span><span class="sxs-lookup"><span data-stu-id="89b75-148">**Whse. Item Reclass. Journal**</span></span>  
-   <span data-ttu-id="89b75-149">(Divers rapports)</span><span class="sxs-lookup"><span data-stu-id="89b75-149">(Various reports)</span></span>  

<span data-ttu-id="89b75-150">Pour plus d'informations sur chaque document, reportez-vous aux rubriques correspondantes de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="89b75-150">For more information about each document, see the respective window topics.</span></span>  

### <a name="terminology"></a><span data-ttu-id="89b75-151">Terminologie</span><span class="sxs-lookup"><span data-stu-id="89b75-151">Terminology</span></span>  
<span data-ttu-id="89b75-152">Pour s'aligner avec les concepts financiers d'achats et de ventes, la documentation d'entrepôt [!INCLUDE[d365fin](includes/d365fin_md.md)] fait référence aux termes suivants pour la circulation des articles dans l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="89b75-152">To align with the financial concepts of purchases and sales, [!INCLUDE[d365fin](includes/d365fin_md.md)] warehouse documentation refers to the following terms for item flow in the warehouse.</span></span>  

|<span data-ttu-id="89b75-153">Terme</span><span class="sxs-lookup"><span data-stu-id="89b75-153">Term</span></span>|<span data-ttu-id="89b75-154">Description</span><span class="sxs-lookup"><span data-stu-id="89b75-154">Description</span></span>|  
|----------|---------------------------------------|  
|<span data-ttu-id="89b75-155">Flux entrant</span><span class="sxs-lookup"><span data-stu-id="89b75-155">Inbound flow</span></span>|<span data-ttu-id="89b75-156">Articles qui se déplacent dans l'emplacement entrepôt, par exemple les achats et les transferts entrants.</span><span class="sxs-lookup"><span data-stu-id="89b75-156">Items moving into the warehouse location, such as purchases and inbound transfers.</span></span>|  
|<span data-ttu-id="89b75-157">Flux interne</span><span class="sxs-lookup"><span data-stu-id="89b75-157">Internal flow</span></span>|<span data-ttu-id="89b75-158">Articles qui se déplacent au sein de l'emplacement entrepôt, par exemple les composantes de production et leur résultat.</span><span class="sxs-lookup"><span data-stu-id="89b75-158">Items moving inside the warehouse location, such as production components and output.</span></span>|  
|<span data-ttu-id="89b75-159">Flux sortant</span><span class="sxs-lookup"><span data-stu-id="89b75-159">Outbound flow</span></span>|<span data-ttu-id="89b75-160">Articles qui se déplacent hors de l'emplacement entrepôt, par exemple les ventes et les transferts sortants.</span><span class="sxs-lookup"><span data-stu-id="89b75-160">Items moving out of the warehouse location, such as sales and outbound transfers.</span></span>|  

## <a name="see-also"></a><span data-ttu-id="89b75-161">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="89b75-161">See Also</span></span>  
 [<span data-ttu-id="89b75-162">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="89b75-162">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)

