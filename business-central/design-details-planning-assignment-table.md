---
title: "Détails de conception - tableau d'affectation de planification | Microsoft Docs"
description: "Cette rubrique donne un aperçu de ce qui se produit lorsque vous modifiez la planification d'un article."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 3e412c6fe82b3ee5640329c523b19d68f849f93a
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-planning-assignment-table"></a><span data-ttu-id="0d56f-103">Détails de conception : tableau d'affectation de planification</span><span class="sxs-lookup"><span data-stu-id="0d56f-103">Design Details: Planning Assignment Table</span></span>
<span data-ttu-id="0d56f-104">Tous les articles doivent être planifiés. Cependant, il n'existe aucune raison de calculer une planification pour un article à moins qu'il n'y ait eu une modification de la configuration de l'offre ou de la demande depuis la dernière fois qu'un plan a été calculé.</span><span class="sxs-lookup"><span data-stu-id="0d56f-104">All items should be planned for, however, there is no reason to calculate a plan for an item unless there has been a change in the demand or supply pattern since the last time a plan was calculated.</span></span>  
  
<span data-ttu-id="0d56f-105">Si l'utilisateur a saisi un document de vente ou en a modifié une existante, il existe un motif au recalcul de la planification.</span><span class="sxs-lookup"><span data-stu-id="0d56f-105">If the user has entered a new sales order or changed an existing one, there is reason to recalculate the plan.</span></span> <span data-ttu-id="0d56f-106">Les autres motifs sont notamment une modification de prévision ou la quantité de stock de sécurité souhaitée.</span><span class="sxs-lookup"><span data-stu-id="0d56f-106">Other reasons include a change in forecast or the desired safety stock quantity.</span></span> <span data-ttu-id="0d56f-107">La modification de nomenclatures lorsque vous ajoutez ou supprimez une composante indique très probablement une modification, mais pour la composante uniquement.</span><span class="sxs-lookup"><span data-stu-id="0d56f-107">Changing a bill of material by adding or removing a component would most likely indicate a change, but for the component item only.</span></span>  
  
<span data-ttu-id="0d56f-108">Pour plusieurs emplacements, l'affectation se fait au niveau de l'article par combinaison d'emplacements.</span><span class="sxs-lookup"><span data-stu-id="0d56f-108">For multiple locations, the assignment takes place at the level of item per location combination.</span></span> <span data-ttu-id="0d56f-109">Si, par exemple, un document de vente a été créée à un seul emplacement, le programme affecte l'article à cet emplacement spécifique pour la planification.</span><span class="sxs-lookup"><span data-stu-id="0d56f-109">If, for example, a sales order has been created at only one location, the program will assign the item at that specific location for planning.</span></span>  
  
<span data-ttu-id="0d56f-110">La raison de la sélection d'articles pour la planification est une question de performances système.</span><span class="sxs-lookup"><span data-stu-id="0d56f-110">The reason for selecting items for planning is a matter of system performance.</span></span> <span data-ttu-id="0d56f-111">Si aucune modification du motif demande-approvisionnement d'un article n'a été apportée, le système de planification ne propose aucune action à effectuer.</span><span class="sxs-lookup"><span data-stu-id="0d56f-111">If no change in an item’s demand-supply pattern has occurred, the planning system will not suggest any actions to be taken.</span></span> <span data-ttu-id="0d56f-112">Sans l'affectation de planification, le système devrait effectuer les calculs pour tous les articles afin de déterminer quoi planifier, et cela purgerait des ressources du système.</span><span class="sxs-lookup"><span data-stu-id="0d56f-112">Without the planning assignment, the system would have to perform the calculations for all items in order to find out what to plan for, and that would drain system resources.</span></span>  
  
<span data-ttu-id="0d56f-113">La table **Affectation planning** contrôle les événements d'offre et de demande et affecte les articles appropriés de façon à les planifier.</span><span class="sxs-lookup"><span data-stu-id="0d56f-113">The **Planning Assignment** table monitors demand and supply events and assigns the appropriate items for planning.</span></span> <span data-ttu-id="0d56f-114">Les événements suivants sont contrôlés :</span><span class="sxs-lookup"><span data-stu-id="0d56f-114">The following events are monitored:</span></span>  
  
* <span data-ttu-id="0d56f-115">Nouveau document de vente, bon de commande, bon de production, ordre d'assemblage ou ordre de transfert, nouvelle prévision ou composante.</span><span class="sxs-lookup"><span data-stu-id="0d56f-115">A new sales order, forecast, component, purchase order, production order, assembly order, or transfer order.</span></span>  
* <span data-ttu-id="0d56f-116">Modification d'un article, d'une quantité, d'un emplacement, d'une variante, ou d'une date sur un document de vente, d'une prévision, d'une composante, d'un bon de commande, d'un bon de production, d'un ordre d'assemblage ou d'un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="0d56f-116">Change of item, quantity, location, variant, or date on a sales order, forecast, component, purchase order, production order, assembly order, or transfer order.</span></span>  
* <span data-ttu-id="0d56f-117">Annulation d'un document de vente, d'une prévision, d'une composante, d'un bon de commande, d'un bon de production, d'un ordre d'assemblage ou d'un ordre de transfert.</span><span class="sxs-lookup"><span data-stu-id="0d56f-117">Cancellation of a sales order, forecast, component, purchase order, production order, assembly order, or transfer order.</span></span>  
* <span data-ttu-id="0d56f-118">Consommation d'autres articles que planifiés.</span><span class="sxs-lookup"><span data-stu-id="0d56f-118">Consumption of items other than planned.</span></span>  
* <span data-ttu-id="0d56f-119">Production d'autres articles que planifiés.</span><span class="sxs-lookup"><span data-stu-id="0d56f-119">Output of items other than planned.</span></span>  
* <span data-ttu-id="0d56f-120">Modifications non planifiées dans l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="0d56f-120">Unplanned changes in inventory.</span></span>  
  
<span data-ttu-id="0d56f-121">Pour ces déplacements directs de demande-approvisionnement, le système de suivi de commande et de messages d'action gère la table Affectation de planification et indique un motif de planification comme message d'action.</span><span class="sxs-lookup"><span data-stu-id="0d56f-121">For these direct supply-demand displacements, the order tracking and action messaging system maintains the Planning Assignment table and states a planning reason as an action message.</span></span>  
  
<span data-ttu-id="0d56f-122">Les modifications suivantes dans les données de base peuvent également provoquer un déséquilibre de planification :</span><span class="sxs-lookup"><span data-stu-id="0d56f-122">The following changes in master data can also cause a planning imbalance:</span></span>  
  
* <span data-ttu-id="0d56f-123">Modification de l'état sur Certifié dans l'en-tête de la nomenclature de production (pour tous les articles utilisant cet en-tête).</span><span class="sxs-lookup"><span data-stu-id="0d56f-123">Change of status to Certified in the production BOM header (for all items using that header).</span></span>  
* <span data-ttu-id="0d56f-124">Ligne supprimée (article enfant).</span><span class="sxs-lookup"><span data-stu-id="0d56f-124">Deleted line (child item).</span></span>  
* <span data-ttu-id="0d56f-125">Modification de l'état sur Certifié dans l'en-tête itinéraire (pour tous les articles avec cette itinéraire).</span><span class="sxs-lookup"><span data-stu-id="0d56f-125">Change of status to Certified in the routing header (for all items using that routing).</span></span>  
* <span data-ttu-id="0d56f-126">Modifications des champs suivants de la fiche article.</span><span class="sxs-lookup"><span data-stu-id="0d56f-126">Changes in the following item card fields.</span></span>  
* <span data-ttu-id="0d56f-127">Quantité du stock de sécurité ou délai de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0d56f-127">Safety Stock Quantity or Safety Lead Time.</span></span>  
* <span data-ttu-id="0d56f-128">Délai de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="0d56f-128">Lead Time Calculation.</span></span>  
* <span data-ttu-id="0d56f-129">Point de commande.</span><span class="sxs-lookup"><span data-stu-id="0d56f-129">Reorder Point.</span></span>  
* <span data-ttu-id="0d56f-130">N° de nomenclature de production (et tous les enfants de l'ancienne référence de nomenclature).</span><span class="sxs-lookup"><span data-stu-id="0d56f-130">Production BOM No. (and all children of old BOM reference).</span></span>  
* <span data-ttu-id="0d56f-131">N° procédure</span><span class="sxs-lookup"><span data-stu-id="0d56f-131">Routing No.</span></span>  
* <span data-ttu-id="0d56f-132">Méthode de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="0d56f-132">Reordering Policy.</span></span>  
  
<span data-ttu-id="0d56f-133">Dans ces cas, une nouvelle fonction, Gestion d'affectation de planification, met à jour la table et indique le motif de planification Solde période.</span><span class="sxs-lookup"><span data-stu-id="0d56f-133">In these cases, a new function, Planning Assignment Management, maintains the table and states the planning reason as Net Change.</span></span>  
  
<span data-ttu-id="0d56f-134">Les modifications suivantes n'entraînent pas une affectation de planification :</span><span class="sxs-lookup"><span data-stu-id="0d56f-134">The following changes do not cause a planning assignment:</span></span>  
  
* <span data-ttu-id="0d56f-135">Calendriers</span><span class="sxs-lookup"><span data-stu-id="0d56f-135">Calendars</span></span>  
* <span data-ttu-id="0d56f-136">Autres paramètres de planification sur la fiche article</span><span class="sxs-lookup"><span data-stu-id="0d56f-136">Other planning parameters on the item card</span></span>  
  
<span data-ttu-id="0d56f-137">Lors du calcul d'un MPS ou d'un MRP, les restrictions suivantes s'appliquent :</span><span class="sxs-lookup"><span data-stu-id="0d56f-137">When calculating an MPS or an MRP, the following restrictions apply:</span></span>  
  
* <span data-ttu-id="0d56f-138">PDP : Le système de planification vérifie que l'article indique une prévision de production ou un document de vente.</span><span class="sxs-lookup"><span data-stu-id="0d56f-138">MPS: The planning system checks that the item carries a production forecast or a sales order.</span></span> <span data-ttu-id="0d56f-139">Sinon, l'article n'est pas inclus dans le planning.</span><span class="sxs-lookup"><span data-stu-id="0d56f-139">If not, the item is not included in the plan.</span></span>  
* <span data-ttu-id="0d56f-140">MRP : si le système de planification détecte que l'article est réapprovisionné par une ligne planification PDP ou une commande approvisionnement PDP, l'article sera laissé en dehors de la planification.</span><span class="sxs-lookup"><span data-stu-id="0d56f-140">MRP: If the planning system detects that the item is being replenished by an MPS planning line or MPS supply order, the item will be left out of the planning.</span></span> <span data-ttu-id="0d56f-141">Toutefois, toute demande des composants pertinents est incluse.</span><span class="sxs-lookup"><span data-stu-id="0d56f-141">However, any demand from relevant components is included.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d56f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0d56f-142">See Also</span></span>  
<span data-ttu-id="0d56f-143">[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md) </span><span class="sxs-lookup"><span data-stu-id="0d56f-143">[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md) </span></span>  
<span data-ttu-id="0d56f-144">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="0d56f-144">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
<span data-ttu-id="0d56f-145">[Détails de conception : transferts de planification](design-details-transfers-in-planning.md) </span><span class="sxs-lookup"><span data-stu-id="0d56f-145">[Design Details: Transfers in Planning](design-details-transfers-in-planning.md) </span></span>  
[<span data-ttu-id="0d56f-146">Détails de conception : paramètres de planification</span><span class="sxs-lookup"><span data-stu-id="0d56f-146">Design Details: Planning Parameters</span></span>](design-details-planning-parameters.md)  
