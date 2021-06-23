---
title: Détails de conception - Demande et approvisionnement | Microsoft Docs
description: Cette rubrique présente le concept de demande, qui désigne toute sorte de demande brute, par exemple un document de vente et un besoin composante d'un bon de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, demand, supply, inventory, planning
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: 62abcd0e37a9871efd6158a898538b7c18b6b47f
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6215338"
---
# <a name="design-details-demand-at-blank-location"></a><span data-ttu-id="9b71f-103">Détails de conception : demande à un magasin vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-103">Design Details: Demand at Blank Location</span></span>
<span data-ttu-id="9b71f-104">Quand un utilisateur crée un événement de demande, comme une ligne document de vente, le programme lui permet parfois de spécifier un code d'emplacement et parfois non, autrement dit il doit utiliser un emplacement vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-104">When a user creates a demand event, such as a sales order line, the program allows the user to sometimes specify a location code and other times not, that is, use blank location.</span></span>

<span data-ttu-id="9b71f-105">Pour la demande avec ou sans code d'emplacement, le système de planification opère directement lorsque :</span><span class="sxs-lookup"><span data-stu-id="9b71f-105">For demand with or without location codes, the planning system operates in a straight forward way when:</span></span>

- <span data-ttu-id="9b71f-106">Les lignes demande comportent toujours des codes d'emplacement et le système exploite intégralement les unités de stock, y compris la configuration d'emplacement pertinente.</span><span class="sxs-lookup"><span data-stu-id="9b71f-106">Demand lines always carry location codes and the system fully uses SKUs, including the relevant location setup.</span></span>
- <span data-ttu-id="9b71f-107">Les lignes demande ne comportent jamais de codes d'emplacement, et le système n'utilise ni les unités de stock ni la configuration d'emplacement (reportez-vous au dernier cas de figure dans la section suivante).</span><span class="sxs-lookup"><span data-stu-id="9b71f-107">Demand lines never carry location codes, and the system does not use SKUs or any location setup (see the last scenario in the following section).</span></span>

<span data-ttu-id="9b71f-108">Toutefois, si des événements de demande ont parfois des codes d'emplacement et parfois pas, le système de planification suit certaines règles en fonction de la configuration.</span><span class="sxs-lookup"><span data-stu-id="9b71f-108">However, if demand events sometimes have location codes and other times do not, the planning system will follow certain rules depending on setup.</span></span>

## <a name="demand-at-location"></a><span data-ttu-id="9b71f-109">Demande à l'emplacement</span><span class="sxs-lookup"><span data-stu-id="9b71f-109">Demand at Location</span></span>
<span data-ttu-id="9b71f-110">Lorsque le système de planification détecte une demande dans un emplacement, il peut procéder de plusieurs manières en fonction de trois valeurs de configuration critiques.</span><span class="sxs-lookup"><span data-stu-id="9b71f-110">When the planning system detects demand at a location, it will behave in different ways depending on three critical setup values.</span></span> <span data-ttu-id="9b71f-111">Lors de l'exécution d'une planification, le système recherche trois valeurs de configuration l'une après l'autre et effectue la planification en conséquence.</span><span class="sxs-lookup"><span data-stu-id="9b71f-111">During a planning run, the system checks for three setup values in sequence and plans accordingly.</span></span>

1. <span data-ttu-id="9b71f-112">Le champ **Magasin obligatoire** est-il activé ?</span><span class="sxs-lookup"><span data-stu-id="9b71f-112">Is there a check mark in the **Location Mandatory** field?</span></span>

    <span data-ttu-id="9b71f-113">Si oui :</span><span class="sxs-lookup"><span data-stu-id="9b71f-113">If yes, then:</span></span>

2. <span data-ttu-id="9b71f-114">Existe-t-il une unité de stock pour l'article ?</span><span class="sxs-lookup"><span data-stu-id="9b71f-114">Does SKU exist for the item?</span></span>

    <span data-ttu-id="9b71f-115">Si oui :</span><span class="sxs-lookup"><span data-stu-id="9b71f-115">If yes, then:</span></span>

    <span data-ttu-id="9b71f-116">L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.</span><span class="sxs-lookup"><span data-stu-id="9b71f-116">The item is planned according to planning parameters on the SKU card.</span></span>

    <span data-ttu-id="9b71f-117">Si non :</span><span class="sxs-lookup"><span data-stu-id="9b71f-117">If no, then:</span></span>

3. <span data-ttu-id="9b71f-118">Le champ Mag. composant par déf contient-il le code magasin demandé ?</span><span class="sxs-lookup"><span data-stu-id="9b71f-118">Does the Components at Location field contain the demanded location code?</span></span>

  <span data-ttu-id="9b71f-119">Si oui :</span><span class="sxs-lookup"><span data-stu-id="9b71f-119">If yes, then:</span></span>

  <span data-ttu-id="9b71f-120">L'article est planifié en fonction des paramètres de planification de la fiche article.</span><span class="sxs-lookup"><span data-stu-id="9b71f-120">The item is planned according to planning parameters on the item card.</span></span>

  <span data-ttu-id="9b71f-121">Si non :</span><span class="sxs-lookup"><span data-stu-id="9b71f-121">If no, then:</span></span>

  <span data-ttu-id="9b71f-122">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour lot, Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide. Les articles pour lesquels Méthode réapprovisionnement = Commande continuent à utiliser Commande, tout comme les autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="9b71f-122">The item is planned according to: Reordering Policy = Lot-for-Lot, Include Inventory = Yes, all other planning parameters = Empty, items using Reordering Policy = Order will remain using Order along with the other settings.</span></span>

> [!NOTE]
> <span data-ttu-id="9b71f-123">La configuration de planification exceptionnelle produite en dernière réaction à l'étape 3 ci-dessus est appelée dans ce qui suit « solution minimale ».</span><span class="sxs-lookup"><span data-stu-id="9b71f-123">The exceptional planning setup that is output as the last reaction in step 3 above is referred to in the following as the “minimal alternative”.</span></span> <span data-ttu-id="9b71f-124">Cette configuration de planification ne couvre que la demande exacte, et tous les autres configuration de planification sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="9b71f-124">This planning setup only covers the exact demand, and all other planning parameters are ignored.</span></span>

<span data-ttu-id="9b71f-125">Pour plus d'informations sur les variations de cette logique de planification, voir la section Scénarios ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="9b71f-125">For information about variations of this planning logic, see the Scenarios section below.</span></span>

## <a name="demand-at-blank-location"></a><span data-ttu-id="9b71f-126">Demande dans un emplacement vide</span><span class="sxs-lookup"><span data-stu-id="9b71f-126">Demand at Blank Location</span></span>
<span data-ttu-id="9b71f-127">Même si le champ **Emplacement obligatoire** est sélectionné, le programme autorise la création de lignes demande sans code d'emplacement, ce que l'on appelle également un emplacement vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-127">Even if the **Location Mandatory** field is selected, the program will allow demand lines to be created without a location code, also referred to as blank location.</span></span> <span data-ttu-id="9b71f-128">Il s'agit d'un écart pour le système, car il a plusieurs valeurs de configuration accordées pour gérer les emplacements (voir ci-dessus) et, par conséquent, le moteur de planification ne crée pas de ligne planification pour une telle ligne demande.</span><span class="sxs-lookup"><span data-stu-id="9b71f-128">This is a deviation for the system because it has various setup values tuned to dealing with locations (see above) and as a result, the planning engine will not create a planning line for such a demand line.</span></span>

<span data-ttu-id="9b71f-129">Si le champ **Emplacement obligatoire** n'est pas activé mais que des valeurs de configuration d'emplacement ont été définies, cela est également considéré comme un écart, et le système de planification réagira en utilisant la « solution minimale » : l'article est planifié comme suit : Méthode réapprovisionnement = Lot pour lot (la commande conserve la valeur Commande), Inclure inventaire = Oui, Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-129">If the **Location Mandatory** field is not selected but any of the location setup values exist, it is also considered a deviation, and the planning system will react by using the “minimal alternative”: The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

## <a name="scenarios"></a><span data-ttu-id="9b71f-130">Cas de figure</span><span class="sxs-lookup"><span data-stu-id="9b71f-130">Scenarios</span></span>
<span data-ttu-id="9b71f-131">Les scénarios suivants décrivent les variations de la demande dans un emplacement vide et la manière dont le système de planification opte pour la « solution minimale ».</span><span class="sxs-lookup"><span data-stu-id="9b71f-131">The following scenarios describe variations of demand at blank location and how the planning system resolves to the “minimal alternative.”</span></span>

### <a name="setup-1"></a><span data-ttu-id="9b71f-132">Configuration 1 :</span><span class="sxs-lookup"><span data-stu-id="9b71f-132">Setup 1:</span></span>
<span data-ttu-id="9b71f-133">Emplacement obligatoire = Oui</span><span class="sxs-lookup"><span data-stu-id="9b71f-133">Location Mandatory = Yes</span></span>

<span data-ttu-id="9b71f-134">L'unité de stock a pour valeur ROUGE</span><span class="sxs-lookup"><span data-stu-id="9b71f-134">SKU is set up for RED</span></span>

<span data-ttu-id="9b71f-135">Composantes à l'emplacement = BLEU</span><span class="sxs-lookup"><span data-stu-id="9b71f-135">Components at Location = BLUE</span></span>

#### <a name="case-11-demand-is-at-red-location"></a><span data-ttu-id="9b71f-136">Situation 1.1 : la demande concerne un emplacement ROUGE.</span><span class="sxs-lookup"><span data-stu-id="9b71f-136">Case 1.1: Demand is at RED location</span></span>
<span data-ttu-id="9b71f-137">L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.</span><span class="sxs-lookup"><span data-stu-id="9b71f-137">The item is planned according to planning parameters on the SKU card.</span></span>

#### <a name="case-12-demand-is-at-blue-location"></a><span data-ttu-id="9b71f-138">Situation 1.2 : la demande concerne un emplacement BLEU.</span><span class="sxs-lookup"><span data-stu-id="9b71f-138">Case 1.2: Demand is at BLUE location</span></span>
<span data-ttu-id="9b71f-139">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-139">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

#### <a name="case-13-demand-is-at-green-location"></a><span data-ttu-id="9b71f-140">Situation 1.3 : la demande concerne un emplacement VERT.</span><span class="sxs-lookup"><span data-stu-id="9b71f-140">Case 1.3: Demand is at GREEN location</span></span>
<span data-ttu-id="9b71f-141">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-141">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

#### <a name="case-14-demand-is-at-blank-location"></a><span data-ttu-id="9b71f-142">Situation 1.4 : la demande concerne un emplacement BLANC.</span><span class="sxs-lookup"><span data-stu-id="9b71f-142">Case 1.4: Demand is at BLANK location</span></span>
<span data-ttu-id="9b71f-143">L'article n'est pas planifié, car aucun emplacement n'est défini sur la ligne de réquisition.</span><span class="sxs-lookup"><span data-stu-id="9b71f-143">The item is not planned because no location is defined on the demand line.</span></span>

### <a name="setup-2"></a><span data-ttu-id="9b71f-144">Configuration 2 :</span><span class="sxs-lookup"><span data-stu-id="9b71f-144">Setup 2:</span></span>
<span data-ttu-id="9b71f-145">Emplacement obligatoire = Oui</span><span class="sxs-lookup"><span data-stu-id="9b71f-145">Location Mandatory = Yes</span></span>

<span data-ttu-id="9b71f-146">Il n'existe pas d'unité de stock</span><span class="sxs-lookup"><span data-stu-id="9b71f-146">No SKU exists</span></span>

<span data-ttu-id="9b71f-147">Composantes à l'emplacement = BLEU</span><span class="sxs-lookup"><span data-stu-id="9b71f-147">Components at Location = BLUE</span></span>

#### <a name="case-21-demand-is-at-red-location"></a><span data-ttu-id="9b71f-148">Situation 2.1 : la demande concerne un emplacement ROUGE.</span><span class="sxs-lookup"><span data-stu-id="9b71f-148">Case 2.1: Demand is at RED location</span></span>
<span data-ttu-id="9b71f-149">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-149">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

#### <a name="case-22-demand-is-at-blue-location"></a><span data-ttu-id="9b71f-150">Situation 2.2 : la demande concerne un emplacement BLEU.</span><span class="sxs-lookup"><span data-stu-id="9b71f-150">Case 2.2: Demand is at BLUE location</span></span>
<span data-ttu-id="9b71f-151">L'article est planifié en fonction des paramètres de planification de la fiche article.</span><span class="sxs-lookup"><span data-stu-id="9b71f-151">The item is planned according to planning parameters on the item card.</span></span>

### <a name="setup-3"></a><span data-ttu-id="9b71f-152">Configuration 3 :</span><span class="sxs-lookup"><span data-stu-id="9b71f-152">Setup 3:</span></span>
<span data-ttu-id="9b71f-153">Emplacement obligatoire = Non</span><span class="sxs-lookup"><span data-stu-id="9b71f-153">Location Mandatory = No</span></span>

<span data-ttu-id="9b71f-154">Il n'existe pas d'unité de stock</span><span class="sxs-lookup"><span data-stu-id="9b71f-154">No SKU exists</span></span>

<span data-ttu-id="9b71f-155">Composantes à l'emplacement = BLEU</span><span class="sxs-lookup"><span data-stu-id="9b71f-155">Components at Location = BLUE</span></span>

#### <a name="case-31-demand-is-at-red-location"></a><span data-ttu-id="9b71f-156">Situation 3.1 : la demande concerne un emplacement ROUGE.</span><span class="sxs-lookup"><span data-stu-id="9b71f-156">Case 3.1: Demand is at RED location</span></span>
<span data-ttu-id="9b71f-157">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-157">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

#### <a name="case-32-demand-is-at-blue-location"></a><span data-ttu-id="9b71f-158">Situation 3.2 : la demande concerne un emplacement BLEU.</span><span class="sxs-lookup"><span data-stu-id="9b71f-158">Case 3.2: Demand is at BLUE location</span></span>
<span data-ttu-id="9b71f-159">L'article est planifié en fonction des paramètres de planification de la fiche article.</span><span class="sxs-lookup"><span data-stu-id="9b71f-159">The item is planned according to planning parameters on the item card.</span></span>

#### <a name="case-33-demand-is-at-blank-location"></a><span data-ttu-id="9b71f-160">Situation 3.3 : la demande concerne un emplacement BLANC.</span><span class="sxs-lookup"><span data-stu-id="9b71f-160">Case 3.3: Demand is at BLANK location</span></span>
<span data-ttu-id="9b71f-161">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-161">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

### <a name="setup-4"></a><span data-ttu-id="9b71f-162">Configuration 4 :</span><span class="sxs-lookup"><span data-stu-id="9b71f-162">Setup 4:</span></span>
<span data-ttu-id="9b71f-163">Emplacement obligatoire = Non</span><span class="sxs-lookup"><span data-stu-id="9b71f-163">Location Mandatory = No</span></span>

<span data-ttu-id="9b71f-164">Il n'existe pas d'unité de stock</span><span class="sxs-lookup"><span data-stu-id="9b71f-164">No SKU exists</span></span>

<span data-ttu-id="9b71f-165">Composantes à l'emplacement = VIDE</span><span class="sxs-lookup"><span data-stu-id="9b71f-165">Components at Location = BLANK</span></span>

#### <a name="case-41-demand-is-at-blue-location"></a><span data-ttu-id="9b71f-166">Situation 4.1 : la demande concerne un emplacement BLEU.</span><span class="sxs-lookup"><span data-stu-id="9b71f-166">Case 4.1: Demand is at BLUE location</span></span>
<span data-ttu-id="9b71f-167">L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.</span><span class="sxs-lookup"><span data-stu-id="9b71f-167">The item is planned according to: Reordering Policy = Lot-for-Lot (Order remains Order), Include Inventory = Yes, all other planning parameters = Empty.</span></span>

#### <a name="case-42-demand-is-at-blank-location"></a><span data-ttu-id="9b71f-168">Situation 4.2 : la demande concerne un emplacement BLANC.</span><span class="sxs-lookup"><span data-stu-id="9b71f-168">Case 4.2: Demand is at BLANK location</span></span>
<span data-ttu-id="9b71f-169">L'article est planifié en fonction des paramètres de planification de la fiche article.</span><span class="sxs-lookup"><span data-stu-id="9b71f-169">The item is planned according to planning parameters on the item card.</span></span>

<span data-ttu-id="9b71f-170">Comme illustré dans le dernier cas de figure, le seul moyen d'obtenir des résultats corrects pour une ligne demande sans code emplacement consiste à désactiver toutes les valeurs de configuration relatives aux emplacements.</span><span class="sxs-lookup"><span data-stu-id="9b71f-170">As illustrated in the last scenario, the only way to get a correct result for a demand line without a location code is to disable all setup values relating to locations.</span></span> <span data-ttu-id="9b71f-171">De la même manière, le seul moyen d'obtenir des résultats de planification stables pour les demandes dans des emplacements consiste à utiliser des unités de stock.</span><span class="sxs-lookup"><span data-stu-id="9b71f-171">Similarly, the only way to get stable planning results for demand at locations is to use SKUs.</span></span> <span data-ttu-id="9b71f-172">Par conséquent, si les compagnies planifient souvent des demandes dans des emplacements, il leur est fortement recommandé d'utiliser le module Unités de stock.</span><span class="sxs-lookup"><span data-stu-id="9b71f-172">Therefore, if companies often plan for demand at locations, they are strongly advised to use the Stockkeeping Units granule.</span></span>

## <a name="see-also"></a><span data-ttu-id="9b71f-173">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9b71f-173">See Also</span></span>  
<span data-ttu-id="9b71f-174">[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md) </span><span class="sxs-lookup"><span data-stu-id="9b71f-174">[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md) </span></span>  
<span data-ttu-id="9b71f-175">[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md) </span><span class="sxs-lookup"><span data-stu-id="9b71f-175">[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md) </span></span>  
[<span data-ttu-id="9b71f-176">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="9b71f-176">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]