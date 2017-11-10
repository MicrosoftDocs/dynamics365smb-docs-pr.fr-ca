---
title: "Détails de conception - Rester sous le niveau de dépassement de capacité | Microsoft Docs"
description: "Lors de l'utilisation de Qté maximum et Qté fixe de commande, le système de planification se concentre sur l'inventaire prévisionnel dans la plage de temps donnée uniquement. Cela signifie que le système de planification peut vous proposer l'approvisionnement superflu lorsqu'une demande négative ou des changements d'approvisionnement positifs se produisent en dehors de la plage de temps donnée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: bbfafc41f22a5582b90683bdacf8135e78e46843
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="design-details-staying-under-the-overflow-level"></a><span data-ttu-id="cec8c-104">Détails de conception : rester sous le niveau de dépassement de capacité</span><span class="sxs-lookup"><span data-stu-id="cec8c-104">Design Details: Staying under the Overflow Level</span></span>
<span data-ttu-id="cec8c-105">Lors de l'utilisation des stratégies Qté maximum et Qté fixe de commande, le système de planification se concentre sur l'inventaire prévisionnel dans la plage de temps donnée uniquement.</span><span class="sxs-lookup"><span data-stu-id="cec8c-105">When using the Maximum Qty. and Fixed Reorder Qty. policies, the planning system focuses on the projected inventory in the given time-bucket only.</span></span> <span data-ttu-id="cec8c-106">Cela signifie que le système de planification peut vous proposer l'approvisionnement superflu lorsqu'une demande négative ou des changements d'approvisionnement positifs se produisent en dehors de l'intervalle de planification donné.</span><span class="sxs-lookup"><span data-stu-id="cec8c-106">This means that the planning system may suggest superfluous supply when negative demand or positive supply changes occur outside of the given time bucket.</span></span> <span data-ttu-id="cec8c-107">Si, pour cette raison, un approvisionnement superflu est proposé, le système de planification calcule la quantité à soustraire (ou supprimer) de l'approvisionnement pour éviter l'approvisionnement superflu.</span><span class="sxs-lookup"><span data-stu-id="cec8c-107">If, for this reason, a superfluous supply is suggested, the planning system calculates which quantity the supply should be decreased to (or deleted) to avoid the superfluous supply.</span></span> <span data-ttu-id="cec8c-108">Cette quantité est appelée « niveau de dépassement de capacité ».</span><span class="sxs-lookup"><span data-stu-id="cec8c-108">This quantity is called the “overflow level.”</span></span> <span data-ttu-id="cec8c-109">Le dépassement de capacité est communiqué comme ligne de planification avec une action **Changer qté (diminuer)** ou **Annuler** et le message d'avertissement suivant :</span><span class="sxs-lookup"><span data-stu-id="cec8c-109">The overflow is communicated as a planning line with a **Change Qty. (Decrease)** or **Cancel** action and the following warning message:</span></span>  

<span data-ttu-id="cec8c-110">*Attention : l'inventaire prévisionnel [xx] est supérieur au niveau de dépassement de capacité [xx] à la date d'échéance [xx].*</span><span class="sxs-lookup"><span data-stu-id="cec8c-110">*Attention: The projected inventory [xx] is higher than the overflow level [xx] on the Due Date [xx].*</span></span>  

<span data-ttu-id="cec8c-111">![Niveau de dépassement de capacité d'inventaire](media/supplyplanning_2_overflow1_new.png "supplyplanning_2_overflow1_new")</span><span class="sxs-lookup"><span data-stu-id="cec8c-111">![Inventory overflow level](media/supplyplanning_2_overflow1_new.png "supplyplanning_2_overflow1_new")</span></span>  

##  <a name="calculating-the-overflow-level"></a><span data-ttu-id="cec8c-112">Calcul du niveau de dépassement de capacité</span><span class="sxs-lookup"><span data-stu-id="cec8c-112">Calculating the Overflow Level</span></span>  
<span data-ttu-id="cec8c-113">Le niveau de dépassement de capacité est calculé de différentes manières en fonction de la configuration de planification.</span><span class="sxs-lookup"><span data-stu-id="cec8c-113">The overflow level is calculated in different ways depending on planning setup.</span></span>  

### <a name="maximum-qty-reordering-policy"></a><span data-ttu-id="cec8c-114">Méthode de réapprovisionnement Qté maximum</span><span class="sxs-lookup"><span data-stu-id="cec8c-114">Maximum Qty. reordering policy</span></span>  
<span data-ttu-id="cec8c-115">Niveau de dépassement de capacité = Inventaire maximum</span><span class="sxs-lookup"><span data-stu-id="cec8c-115">Overflow level = Maximum Inventory</span></span>  

> [!NOTE]  
>  <span data-ttu-id="cec8c-116">Si une quantité de commande minimum existe, elle sera ajoutée comme suit : Niveau de dépassement de capacité = Inventaire maximum + Quantité commande minimum.</span><span class="sxs-lookup"><span data-stu-id="cec8c-116">If a minimum order quantity exists, then it will be added as follows: Overflow level = Maximum Inventory + Minimum Order Quantity.</span></span>  

### <a name="fixed-reorder-qty-reordering-policy"></a><span data-ttu-id="cec8c-117">Méthode de réapprovisionnement Qté fixe de commande</span><span class="sxs-lookup"><span data-stu-id="cec8c-117">Fixed Reorder Qty. reordering policy</span></span>  
<span data-ttu-id="cec8c-118">Niveau de dépassement de capacité = Quantité de réappro. + Point de commande</span><span class="sxs-lookup"><span data-stu-id="cec8c-118">Overflow level = Reorder Quantity + Reorder Point</span></span>  

> [!NOTE]  
>  <span data-ttu-id="cec8c-119">Si la quantité minimum commande est supérieure au point de commande, alors elle remplace comme suit : Niveau de dépassement de capacité = Quantité de réappro. + Quantité minimum commande</span><span class="sxs-lookup"><span data-stu-id="cec8c-119">If the minimum order quantity is higher than the reorder point, then it will replace as follows: Overflow Level = Reorder Quantity + Minimum Order Quantity</span></span>  

### <a name="order-multiple"></a><span data-ttu-id="cec8c-120">Commande multiple</span><span class="sxs-lookup"><span data-stu-id="cec8c-120">Order Multiple</span></span>  
<span data-ttu-id="cec8c-121">Si un multiple de commande existe, il ajuste le niveau de dépassement de capacité pour les deux méthodes de réapprovisionnement Qté maximum et Qté fixe de commande.</span><span class="sxs-lookup"><span data-stu-id="cec8c-121">If an order multiple exists, then it will adjust the overflow level for both Maximum Qty. and Fixed Reorder Qty. reordering policies.</span></span>  

##  <a name="creating-the-planning-line-with-overflow-warning"></a><span data-ttu-id="cec8c-122">Création de la ligne planification avec l'avertissement de dépassement capacité</span><span class="sxs-lookup"><span data-stu-id="cec8c-122">Creating the Planning Line with Overflow Warning</span></span>  
<span data-ttu-id="cec8c-123">Lorsqu'un approvisionnement existant rend l'inventaire prévisionnel supérieur au niveau de dépassement de capacité à la fin d'une plage de temps, une ligne planification est créée.</span><span class="sxs-lookup"><span data-stu-id="cec8c-123">When an existing supply causes the projected inventory to be higher than the overflow level at the end of a time bucket, a planning line is created.</span></span> <span data-ttu-id="cec8c-124">Pour avertir sur le potentiel approvisionnement superflu, la ligne de planification a un message d'avertissement, le champ **Accept Action Message** n'est pas sélectionné, et le message d'action est Cancel ou Change Qty.</span><span class="sxs-lookup"><span data-stu-id="cec8c-124">To warn about the potential superfluous supply, the planning line has a warning message, the **Accept Action Message** field is not selected, and the action message is either Cancel or Change Qty.</span></span>  

### <a name="calculating-the-planning-line-quantity"></a><span data-ttu-id="cec8c-125">Calcul de la quantité pour la ligne planification</span><span class="sxs-lookup"><span data-stu-id="cec8c-125">Calculating the Planning Line Quantity</span></span>  
<span data-ttu-id="cec8c-126">Quantité pour la ligne planification = Quantité d'approvisionnement actif – (Inventaire prévisionnel – Niveau de dépassement de capacité)</span><span class="sxs-lookup"><span data-stu-id="cec8c-126">Planning Line Quantity = Current Supply Quantity – (Projected Inventory – Overflow Level)</span></span>  

> [!NOTE]  
>  <span data-ttu-id="cec8c-127">Comme pour toutes les lignes d'avertissement, les quantités maximales/minimales de commande ou les multiples de commande sont ignorés.</span><span class="sxs-lookup"><span data-stu-id="cec8c-127">As with all warning lines, any maximum/minimum order quantity or order multiple will be ignored.</span></span>  

### <a name="defining-the-action-message-type"></a><span data-ttu-id="cec8c-128">Définir le type de message d'action</span><span class="sxs-lookup"><span data-stu-id="cec8c-128">Defining the Action Message Type</span></span>  

-   <span data-ttu-id="cec8c-129">Si la quantité de la ligne planification est supérieure à 0, le message d'action est Changer qté.</span><span class="sxs-lookup"><span data-stu-id="cec8c-129">If the planning line quantity is higher than 0, then the action message is Change Qty.</span></span>  
-   <span data-ttu-id="cec8c-130">Si la quantité de la ligne planification est égale ou inférieure à 0, le message d'action est Annuler</span><span class="sxs-lookup"><span data-stu-id="cec8c-130">If the planning line quantity is equal to or lower than 0, then the action message is Cancel</span></span>  

### <a name="composing-the-warning-message"></a><span data-ttu-id="cec8c-131">Composition du message d'avertissement</span><span class="sxs-lookup"><span data-stu-id="cec8c-131">Composing the Warning Message</span></span>  
<span data-ttu-id="cec8c-132">Dans le cas d'un dépassement de capacité, la fenêtre **Éléments planification sans suivi** affiche un message d'avertissement avec les informations suivantes :</span><span class="sxs-lookup"><span data-stu-id="cec8c-132">In case of overflow, the **Untracked Planning Elements** window displays a warning message with the following information:</span></span>  

-   <span data-ttu-id="cec8c-133">Le niveau d'inventaire prévisionnel qui a déclenché l'avertissement</span><span class="sxs-lookup"><span data-stu-id="cec8c-133">The projected inventory level that triggered the warning</span></span>  
-   <span data-ttu-id="cec8c-134">Niveau de dépassement de capacité calculé</span><span class="sxs-lookup"><span data-stu-id="cec8c-134">The calculated overflow level</span></span>  
-   <span data-ttu-id="cec8c-135">Date d'échéance d'un événement d'approvisionnement.</span><span class="sxs-lookup"><span data-stu-id="cec8c-135">The due date of the supply event.</span></span>  

<span data-ttu-id="cec8c-136">Exemple : « L'inventaire prévisionnel 120 est supérieur au niveau de dépassement de capacité 60 au 28/01/11 »</span><span class="sxs-lookup"><span data-stu-id="cec8c-136">Example: “The projected inventory 120 is higher than the overflow level 60 on 28-01-11”</span></span>  

## <a name="scenario"></a><span data-ttu-id="cec8c-137">Scénario</span><span class="sxs-lookup"><span data-stu-id="cec8c-137">Scenario</span></span>  
<span data-ttu-id="cec8c-138">Dans ce scénario, un client modifie une document de vente de 70 à 40 pièces entre deux exécutions de planification.</span><span class="sxs-lookup"><span data-stu-id="cec8c-138">In this scenario, a customer changes a sales order from 70 to 40 pieces between two planning runs.</span></span> <span data-ttu-id="cec8c-139">La fonction de dépassement de capacité intervient pour réduire l'achat qui a été proposé pour la quantité de ventes initiale.</span><span class="sxs-lookup"><span data-stu-id="cec8c-139">The overflow feature sets in to reduce the purchase that was suggested for the initial sales quantity.</span></span>  

### <a name="item-setup"></a><span data-ttu-id="cec8c-140">Configuration d'article</span><span class="sxs-lookup"><span data-stu-id="cec8c-140">Item setup</span></span>  

|<span data-ttu-id="cec8c-141">Politique réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="cec8c-141">Reordering Policy</span></span>|<span data-ttu-id="cec8c-142">Qté maximum</span><span class="sxs-lookup"><span data-stu-id="cec8c-142">Maximum Qty.</span></span>|  
|-----------------------|------------------|  
|<span data-ttu-id="cec8c-143">Quantité maximum commande</span><span class="sxs-lookup"><span data-stu-id="cec8c-143">Maximum Order Quantity</span></span>|<span data-ttu-id="cec8c-144">100</span><span class="sxs-lookup"><span data-stu-id="cec8c-144">100</span></span>|  
|<span data-ttu-id="cec8c-145">Point de réapprovisionnement</span><span class="sxs-lookup"><span data-stu-id="cec8c-145">Reorder Point</span></span>|<span data-ttu-id="cec8c-146">50</span><span class="sxs-lookup"><span data-stu-id="cec8c-146">50</span></span>|  
|<span data-ttu-id="cec8c-147">Stocks</span><span class="sxs-lookup"><span data-stu-id="cec8c-147">Inventory</span></span>|<span data-ttu-id="cec8c-148">80</span><span class="sxs-lookup"><span data-stu-id="cec8c-148">80</span></span>|  

### <a name="situation-before-sales-decrease"></a><span data-ttu-id="cec8c-149">Situation avant la sortie de vente</span><span class="sxs-lookup"><span data-stu-id="cec8c-149">Situation before sales decrease</span></span>  

|<span data-ttu-id="cec8c-150">Evénement</span><span class="sxs-lookup"><span data-stu-id="cec8c-150">Event</span></span>|<span data-ttu-id="cec8c-151">Changer qté</span><span class="sxs-lookup"><span data-stu-id="cec8c-151">Change Qty.</span></span>|<span data-ttu-id="cec8c-152">Inventaire projeté</span><span class="sxs-lookup"><span data-stu-id="cec8c-152">Projected Inventory</span></span>|  
|-----------|-----------------|-------------------------|  
|<span data-ttu-id="cec8c-153">Un jour</span><span class="sxs-lookup"><span data-stu-id="cec8c-153">Day one</span></span>|<span data-ttu-id="cec8c-154">Aucun</span><span class="sxs-lookup"><span data-stu-id="cec8c-154">None</span></span>|<span data-ttu-id="cec8c-155">80</span><span class="sxs-lookup"><span data-stu-id="cec8c-155">80</span></span>|  
|<span data-ttu-id="cec8c-156">Vente</span><span class="sxs-lookup"><span data-stu-id="cec8c-156">Sale</span></span>|<span data-ttu-id="cec8c-157">-70</span><span class="sxs-lookup"><span data-stu-id="cec8c-157">-70</span></span>|<span data-ttu-id="cec8c-158">10</span><span class="sxs-lookup"><span data-stu-id="cec8c-158">10</span></span>|  
|<span data-ttu-id="cec8c-159">Fin de la plage de temps</span><span class="sxs-lookup"><span data-stu-id="cec8c-159">End of time bucket</span></span>|<span data-ttu-id="cec8c-160">Aucun</span><span class="sxs-lookup"><span data-stu-id="cec8c-160">None</span></span>|<span data-ttu-id="cec8c-161">10</span><span class="sxs-lookup"><span data-stu-id="cec8c-161">10</span></span>|  
|<span data-ttu-id="cec8c-162">Suggérer un nouveau bon de commande</span><span class="sxs-lookup"><span data-stu-id="cec8c-162">Suggest new purchase order</span></span>|<span data-ttu-id="cec8c-163">+90</span><span class="sxs-lookup"><span data-stu-id="cec8c-163">+90</span></span>|<span data-ttu-id="cec8c-164">100</span><span class="sxs-lookup"><span data-stu-id="cec8c-164">100</span></span>|  

### <a name="situation-after-sales-decrease"></a><span data-ttu-id="cec8c-165">Situation après la sortie de vente</span><span class="sxs-lookup"><span data-stu-id="cec8c-165">Situation after sales decrease</span></span>  

|<span data-ttu-id="cec8c-166">Activer</span><span class="sxs-lookup"><span data-stu-id="cec8c-166">Change</span></span>|<span data-ttu-id="cec8c-167">Changer qté</span><span class="sxs-lookup"><span data-stu-id="cec8c-167">Change Qty.</span></span>|<span data-ttu-id="cec8c-168">Inventaire projeté</span><span class="sxs-lookup"><span data-stu-id="cec8c-168">Projected Inventory</span></span>|  
|------------|-----------------|-------------------------|  
|<span data-ttu-id="cec8c-169">Un jour</span><span class="sxs-lookup"><span data-stu-id="cec8c-169">Day one</span></span>|<span data-ttu-id="cec8c-170">Aucun</span><span class="sxs-lookup"><span data-stu-id="cec8c-170">None</span></span>|<span data-ttu-id="cec8c-171">80</span><span class="sxs-lookup"><span data-stu-id="cec8c-171">80</span></span>|  
|<span data-ttu-id="cec8c-172">Vente</span><span class="sxs-lookup"><span data-stu-id="cec8c-172">Sale</span></span>|<span data-ttu-id="cec8c-173">-40</span><span class="sxs-lookup"><span data-stu-id="cec8c-173">-40</span></span>|<span data-ttu-id="cec8c-174">40</span><span class="sxs-lookup"><span data-stu-id="cec8c-174">40</span></span>|  
|<span data-ttu-id="cec8c-175">Achat</span><span class="sxs-lookup"><span data-stu-id="cec8c-175">Purchase</span></span>|<span data-ttu-id="cec8c-176">+90</span><span class="sxs-lookup"><span data-stu-id="cec8c-176">+90</span></span>|<span data-ttu-id="cec8c-177">130</span><span class="sxs-lookup"><span data-stu-id="cec8c-177">130</span></span>|  
|<span data-ttu-id="cec8c-178">Fin de l'intervalle de planification</span><span class="sxs-lookup"><span data-stu-id="cec8c-178">End of time bucket</span></span>|<span data-ttu-id="cec8c-179">Aucun</span><span class="sxs-lookup"><span data-stu-id="cec8c-179">None</span></span>|<span data-ttu-id="cec8c-180">130</span><span class="sxs-lookup"><span data-stu-id="cec8c-180">130</span></span>|  
|<span data-ttu-id="cec8c-181">Proposer de réduire l'achat</span><span class="sxs-lookup"><span data-stu-id="cec8c-181">Suggest to decrease purchase</span></span><br /><br /> <span data-ttu-id="cec8c-182">achat de 90 à 60</span><span class="sxs-lookup"><span data-stu-id="cec8c-182">order from 90 to 60</span></span>|<span data-ttu-id="cec8c-183">-30</span><span class="sxs-lookup"><span data-stu-id="cec8c-183">-30</span></span>|<span data-ttu-id="cec8c-184">100</span><span class="sxs-lookup"><span data-stu-id="cec8c-184">100</span></span>|  

### <a name="resulting-planning-lines"></a><span data-ttu-id="cec8c-185">Lignes planification résultantes</span><span class="sxs-lookup"><span data-stu-id="cec8c-185">Resulting Planning Lines</span></span>  
 <span data-ttu-id="cec8c-186">Une ligne planification (avertissement) est créée pour réduire l'achat de 30 pour passer de 90 à 60 pour conserver l'inventaire prévisionnel à 100 conformément au niveau de dépassement de capacité.</span><span class="sxs-lookup"><span data-stu-id="cec8c-186">One planning line (warning) is created to reduce the purchase with 30 from 90 to 60 to keep the projected inventory on 100 according to the overflow level.</span></span>  

<span data-ttu-id="cec8c-187">![Planifier en fonction du niveau de dépassement de capacité](media/nav_app_supply_planning_2_overflow2.png "nav_app_supply_planification_2_overflow2")</span><span class="sxs-lookup"><span data-stu-id="cec8c-187">![Plan according to overflow level](media/nav_app_supply_planning_2_overflow2.png "nav_app_supply_planning_2_overflow2")</span></span>  

> [!NOTE]  
>  <span data-ttu-id="cec8c-188">Sans la fonction Dépassement de capacité, aucun avertissement n'est créé si le niveau d'inventaire prévisionnel dépasse l'inventaire maximum.</span><span class="sxs-lookup"><span data-stu-id="cec8c-188">Without the Overflow feature, no warning is created if the projected inventory level is above maximum inventory.</span></span> <span data-ttu-id="cec8c-189">Cela pourrait entraîner un approvisionnement superflu de 30.</span><span class="sxs-lookup"><span data-stu-id="cec8c-189">This could cause a superfluous supply of 30.</span></span>  

## <a name="see-also"></a><span data-ttu-id="cec8c-190">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="cec8c-190">See Also</span></span>  
<span data-ttu-id="cec8c-191">[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="cec8c-191">[Design Details: Reordering Policies](design-details-reordering-policies.md) </span></span>  
<span data-ttu-id="cec8c-192">[Détails de conception : paramètres de planification](design-details-planning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="cec8c-192">[Design Details: Planning Parameters](design-details-planning-parameters.md) </span></span>  
<span data-ttu-id="cec8c-193">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="cec8c-193">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
[<span data-ttu-id="cec8c-194">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="cec8c-194">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)
