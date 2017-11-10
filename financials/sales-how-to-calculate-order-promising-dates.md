---
title: "Procédure : calculer des dates promesse livraison | Microsoft Docs"
description: "La fonction de configuration des promesses livraison est un outil permettant de calculer la date la plus proche à laquelle un article est disponible pour la livraison. Cette fonction crée également des lignes demande achat pour les dates que vous acceptez."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/10/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: ff83b7e5b61cd265bb3cb1af0bd5db3513c26072
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-calculate-order-promising-dates"></a><span data-ttu-id="d07d3-104">Comment calculer des dates promesse livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-104">How to: Calculate Order Promising Dates</span></span>
<span data-ttu-id="d07d3-105">Une compagnie doit pouvoir informer ses clients des dates de livraison de commande.</span><span class="sxs-lookup"><span data-stu-id="d07d3-105">A company must be able to inform their customers of order delivery dates.</span></span> <span data-ttu-id="d07d3-106">La fenêtre **Lignes promesse de livraison** vous permet d'effectuer cette opération à partir d'une ligne document de vente.</span><span class="sxs-lookup"><span data-stu-id="d07d3-106">The **Order Promising Lines** window enables you to do this from a sales order line.</span></span>  

<span data-ttu-id="d07d3-107">À partir des dates de disponibilité connues et attendues d'un article, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule immédiatement les dates de livraison, qui peuvent être annoncées au client.</span><span class="sxs-lookup"><span data-stu-id="d07d3-107">Based on an item’s known and expected availability dates, [!INCLUDE[d365fin](includes/d365fin_md.md)] instantly calculates shipment and delivery dates, which can then be promised to the customer.</span></span>  

<span data-ttu-id="d07d3-108">Si vous spécifiez une date de livraison demandée sur une ligne document de vente, alors cette date est utilisée comme point de départ du calcul suivant :</span><span class="sxs-lookup"><span data-stu-id="d07d3-108">If you specify a requested delivery date on a sales order line, then that date is used as the starting point for the following calculations:</span></span>  

- <span data-ttu-id="d07d3-109">date livraison demandée - délai livraison = date de livraison planifiée</span><span class="sxs-lookup"><span data-stu-id="d07d3-109">requested delivery date - shipping time = planned shipment date</span></span>  
- <span data-ttu-id="d07d3-110">date de livraison planifiée - délai désenlogement = date de livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-110">planned shipment date - outbound whse. handling time = shipment date</span></span>  

<span data-ttu-id="d07d3-111">Si les articles peuvent être prélevés à la date de livraison, alors le processus vente peut continuer.</span><span class="sxs-lookup"><span data-stu-id="d07d3-111">If the items are available to pick on the shipment date, then the sales process can continue.</span></span> <span data-ttu-id="d07d3-112">Si les articles ne peuvent pas être prélevés à la date de livraison, alors une alerte rupture de stock est affichée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-112">If the items are not available to be picked on the shipment date, then a stock-out warning is displayed.</span></span>  

<span data-ttu-id="d07d3-113">Si vous ne spécifiez aucune date livraison demandée sur une ligne de document de vente ou si la date livraison demandée ne peut pas être respectée, alors la première date à laquelle les articles sont disponibles est calculée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-113">If you do not specify a requested delivery date on a sales order line, or if the requested delivery date cannot be met, then the earliest date on which that the items are available is calculated.</span></span> <span data-ttu-id="d07d3-114">Cette date est ensuite renseignée dans le champ **Date de livraison** sur la ligne, et la date à laquelle vous prévoyez de livrer les articles, ainsi que la date à laquelle ces derniers seront livrés au client sont calculées à l'aide des calculs suivants :</span><span class="sxs-lookup"><span data-stu-id="d07d3-114">That date is then entered in the **Shipment Date** field on the line, and the date on which you plan to ship the items as well as the date on which they will be delivered to the customer are calculated using the following calculations:</span></span>  

- <span data-ttu-id="d07d3-115">date de livraison + délai désenlogement = date de livraison planifiée</span><span class="sxs-lookup"><span data-stu-id="d07d3-115">shipment date + outbound whse. handling time = planned shipment date</span></span>  
- <span data-ttu-id="d07d3-116">date de livraison planifiée + délai de livraison = date de livraison planifiée</span><span class="sxs-lookup"><span data-stu-id="d07d3-116">planned shipment date + shipping time = planned delivery date</span></span>  

## <a name="about-order-promising"></a><span data-ttu-id="d07d3-117">À propos de la promesse de livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-117">About Order Promising</span></span>
<span data-ttu-id="d07d3-118">La fonctionnalité de promesse de livraison vous permet de promettre la livraison d'une commande à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-118">The Order Promising functionality enables you to promise an order to be shipped or delivered on a specific date.</span></span> <span data-ttu-id="d07d3-119">La date à laquelle un article est disponible afin de le promettre ou de pouvoir le promettre est calculée, et des lignes commande sont créées pour les dates que vous acceptez.</span><span class="sxs-lookup"><span data-stu-id="d07d3-119">The date that an item is available to promise or capable to promise is calculated, and order lines are created for those dates that you accept.</span></span> <span data-ttu-id="d07d3-120">Cette fonctionnalité calcule la date la plus proche à laquelle un article est disponible pour livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-120">The functionality calculates the earliest possible date that an item is available for shipment or delivery.</span></span> <span data-ttu-id="d07d3-121">Elle crée également des lignes de réquisition, dans le cas où les articles doivent d'abord être achetés, pour les dates que vous acceptez.</span><span class="sxs-lookup"><span data-stu-id="d07d3-121">It also creates requisition lines, in case the items must first be purchases, for those dates that you accept.</span></span>

[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="d07d3-122"> utilise deux concepts essentiels :</span><span class="sxs-lookup"><span data-stu-id="d07d3-122"> uses two fundamental concepts:</span></span>  

- <span data-ttu-id="d07d3-123">Disponible à la vente (DAV)</span><span class="sxs-lookup"><span data-stu-id="d07d3-123">Available to Promise (ATP)</span></span>  
- <span data-ttu-id="d07d3-124">Simulation de délai (SDD)</span><span class="sxs-lookup"><span data-stu-id="d07d3-124">Capable to Promise (CTP)</span></span>  

### <a name="available-to-promise"></a><span data-ttu-id="d07d3-125">Disponible à la vente</span><span class="sxs-lookup"><span data-stu-id="d07d3-125">Available to Promise</span></span>  
<span data-ttu-id="d07d3-126">La fonction Disponible à la vente (ATP) calcule les dates sur la base du système de réservation.</span><span class="sxs-lookup"><span data-stu-id="d07d3-126">Available to promise (ATP) calculates dates based on the reservation system.</span></span> <span data-ttu-id="d07d3-127">Elle effectue une vérification de la disponibilité des quantités non réservées en inventaire vis-à-vis de la production, des achats, des transferts et des retours vente planifiés.</span><span class="sxs-lookup"><span data-stu-id="d07d3-127">It performs an availability check of the unreserved quantities in inventory with regard to planned production, purchases, transfers, and sales returns.</span></span> <span data-ttu-id="d07d3-128">En fonction de ces informations, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule automatiquement la date de livraison de la commande du client dans la mesure où les articles sont disponibles (en inventaire ou sur réceptions planifiées).</span><span class="sxs-lookup"><span data-stu-id="d07d3-128">Based on this information, [!INCLUDE[d365fin](includes/d365fin_md.md)] automatically calculates the delivery date of the customer’s order because the items are available, either in inventory or on planned receipts.</span></span>  

### <a name="capable-to-promise"></a><span data-ttu-id="d07d3-129">Simulation de délai</span><span class="sxs-lookup"><span data-stu-id="d07d3-129">Capable to Promise</span></span>  
<span data-ttu-id="d07d3-130">La fonction Capacité à promettre (CTP) considère un scénario basé sur l'hypothèse où l'article n'est pas en inventaire et aucune commande n'est programmée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-130">Capable to promise (CTP) assumes a “what if” scenario where the item is not in inventory and no orders are scheduled.</span></span> <span data-ttu-id="d07d3-131">En fonction de ce scénario, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule la date la plus proche à laquelle cet article sera disponible s'il doit être produit, acheté ou transféré.</span><span class="sxs-lookup"><span data-stu-id="d07d3-131">Based on this scenario, [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the earliest date that the item can be available if it is to be produced, purchased, or transferred.</span></span>  


### <a name="calculations"></a><span data-ttu-id="d07d3-132">Calculs</span><span class="sxs-lookup"><span data-stu-id="d07d3-132">Calculations</span></span>  
<span data-ttu-id="d07d3-133">Lorsque [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule la date de livraison du client, il effectue deux tâches :</span><span class="sxs-lookup"><span data-stu-id="d07d3-133">When [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates the customer’s delivery date, it performs two tasks:</span></span>  

- <span data-ttu-id="d07d3-134">Calcule la première date de livraison possible lorsque le client n'a pas demandé une date de livraison spécifique.</span><span class="sxs-lookup"><span data-stu-id="d07d3-134">Calculates the earliest delivery date when the customer has not requested a specific delivery date.</span></span>  
- <span data-ttu-id="d07d3-135">Vérifie si la date de livraison demandée par le client ou confirmée au client est réaliste.</span><span class="sxs-lookup"><span data-stu-id="d07d3-135">Verifies if the delivery date requested by the customer or promised to the customer is realistic.</span></span>  

<span data-ttu-id="d07d3-136">Si le client ne demande pas de date de livraison spécifique, la date de livraison est configurée comme la date de travail, et la disponibilité est ensuite basée sur cette date.</span><span class="sxs-lookup"><span data-stu-id="d07d3-136">If the customer does not request a specific delivery date, the shipment date is set to equal the work date, and availability is then based on that date.</span></span> <span data-ttu-id="d07d3-137">Si l'article est en inventaire, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule à l'avance pour déterminer quand la commande peut être livrée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-137">If the item is in inventory, [!INCLUDE[d365fin](includes/d365fin_md.md)] calculates forward in time to determine when the order can be delivered.</span></span> <span data-ttu-id="d07d3-138">Ceci est accompli par les formules suivantes :</span><span class="sxs-lookup"><span data-stu-id="d07d3-138">This is accomplished by the following formulas:</span></span>  

- <span data-ttu-id="d07d3-139">Date de livraison + Sortie entrepôt + Livraison planifiée + Durée de traitement = Date</span><span class="sxs-lookup"><span data-stu-id="d07d3-139">Shipment Date + Outbound Warehouse + Planned Shipment + Handling Time = Date</span></span>  
- <span data-ttu-id="d07d3-140">Date de livraison planifiée + délai de livraison = date de livraison planifiée</span><span class="sxs-lookup"><span data-stu-id="d07d3-140">Planned Shipment Date + Shipping Time = Planned Delivery Date</span></span>  

<span data-ttu-id="d07d3-141">Ensuite, [!INCLUDE[d365fin](includes/d365fin_md.md)] vérifie si la date de livraison calculée est réaliste en calculant en amont dans le temps, pour déterminer quand l'article doit être disponible pour respecter la date confirmée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-141">[!INCLUDE[d365fin](includes/d365fin_md.md)] then verifies if the calculated delivery date is realistic by calculating backward in time to determine when the item must be available to meet the promised date.</span></span> <span data-ttu-id="d07d3-142">Ceci est accompli par les formules suivantes :</span><span class="sxs-lookup"><span data-stu-id="d07d3-142">This is accomplished by the following formulas:</span></span>  

- <span data-ttu-id="d07d3-143">Date de livraison planifiée - délai de livraison = date de livraison planifiée</span><span class="sxs-lookup"><span data-stu-id="d07d3-143">Planned Delivery Date - Shipping Time = Planned Shipment Date</span></span>  
- <span data-ttu-id="d07d3-144">Date de livraison planifiée - Désenlogement = Date de livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-144">Planned Shipment Date - Outbound Warehouse Handling = Shipment Date</span></span>  

<span data-ttu-id="d07d3-145">La date de livraison est utilisée pour effectuer la vérification de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="d07d3-145">The shipment date is used to make the availability check.</span></span> <span data-ttu-id="d07d3-146">Si l'article est disponible à cette date, [!INCLUDE[d365fin](includes/d365fin_md.md)] confirme que la livraison demandée/promise peut être respectée en configurant la date de livraison planifiée à la date de livraison demandée/confirmée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-146">If the item is available on this date, [!INCLUDE[d365fin](includes/d365fin_md.md)] confirms that therequested/promised delivery can be met by setting the planned delivery date to equal the requested/promised delivery date.</span></span> <span data-ttu-id="d07d3-147">Si l'article n'est pas disponible, il renvoie une date vide et le préparateur de commandes peut alors utiliser la fonctionnalité CTP.</span><span class="sxs-lookup"><span data-stu-id="d07d3-147">If the item is unavailable, it returns a blank date and the order processor can then use the CTP functionality.</span></span>  

<span data-ttu-id="d07d3-148">Sur la base des nouvelles dates et heures, toutes les dates liées sont calculées en fonction des formules répertoriées précédemment dans cette section.</span><span class="sxs-lookup"><span data-stu-id="d07d3-148">Based on new dates and times, all related dates are calculated according to the formulas listed earlier in this section.</span></span> <span data-ttu-id="d07d3-149">Le calcul CTP prend plus de temps, mais donne une date précise à laquelle le client peut attendre la livraison de l'article.</span><span class="sxs-lookup"><span data-stu-id="d07d3-149">The CTP calculation takes longer but it gives an accurate date when the customer can expect to have the item delivered.</span></span> <span data-ttu-id="d07d3-150">Les dates qui sont calculées à partir de CAP sont présentées dans les champs **Date de livraison planifiée** et **Date de livraison au plus tôt** dans la fenêtre **Lignes promesse de livraison**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-150">The dates that are calculated from CTP are presented in the **Planned Delivery Date** and **Earliest Shipment Date** fields in the **Order Promising Lines** window.</span></span>  

<span data-ttu-id="d07d3-151">Le préparateur de commandes finit le processus CTP en acceptant les dates.</span><span class="sxs-lookup"><span data-stu-id="d07d3-151">The order processor finishes the CTP process by accepting the dates.</span></span> <span data-ttu-id="d07d3-152">Cela signifie qu'une ligne de planification et une écriture de réservation sont créées pour l'article avant les dates calculées pour assurer que la commande est satisfaite.</span><span class="sxs-lookup"><span data-stu-id="d07d3-152">This means that a planning line and a reservation entry are created for the item before the calculated dates to ensure that the order is fulfilled.</span></span>  

<span data-ttu-id="d07d3-153">En plus de la promesse de livraison externe que vous pouvez effectuer dans la fenêtre **Lignes promesse de livraison**, vous pouvez également promettre des dates de livraison internes ou externes pour les articles de nomenclature.</span><span class="sxs-lookup"><span data-stu-id="d07d3-153">In addition to the external order promising that you can perform in the **Order Promising Lines** window, you can also promise internal or external delivery dates for bill-of-material items.</span></span> <span data-ttu-id="d07d3-154">Pour plus d'informations, voir [Procédure : voir la disponibilité des articles](inventory-how-availability-overview.md).</span><span class="sxs-lookup"><span data-stu-id="d07d3-154">For more information, see [How to: View the Availability of Items](inventory-how-availability-overview.md).</span></span>

## <a name="to-set-up-order-promising"></a><span data-ttu-id="d07d3-155">Pour configurer une promesse livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-155">To set up order promising</span></span>  
1. <span data-ttu-id="d07d3-156">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration de promesse de commande**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d07d3-156">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Order Promising Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="d07d3-157">Entrez un numéro et un code unité de temps dans le champ **Décalage (durée)**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-157">Enter a number and time unit code in the **Offset(Time)** field.</span></span> <span data-ttu-id="d07d3-158">Sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="d07d3-158">Select one of the following codes.</span></span>  

    |<span data-ttu-id="d07d3-159">Code</span><span class="sxs-lookup"><span data-stu-id="d07d3-159">Code</span></span>|<span data-ttu-id="d07d3-160">Description</span><span class="sxs-lookup"><span data-stu-id="d07d3-160">Description</span></span>|  
    |----------|-----------------|  
    |<span data-ttu-id="d07d3-161">**j**</span><span class="sxs-lookup"><span data-stu-id="d07d3-161">**d**</span></span>|<span data-ttu-id="d07d3-162">Jour du calendrier</span><span class="sxs-lookup"><span data-stu-id="d07d3-162">Calendar day</span></span>|  
    |<span data-ttu-id="d07d3-163">**t**</span><span class="sxs-lookup"><span data-stu-id="d07d3-163">**w**</span></span>|<span data-ttu-id="d07d3-164">Semaine</span><span class="sxs-lookup"><span data-stu-id="d07d3-164">Week</span></span>|  
    |<span data-ttu-id="d07d3-165">**m**</span><span class="sxs-lookup"><span data-stu-id="d07d3-165">**m**</span></span>|<span data-ttu-id="d07d3-166">Mois</span><span class="sxs-lookup"><span data-stu-id="d07d3-166">Month</span></span>|  
    |<span data-ttu-id="d07d3-167">**t**</span><span class="sxs-lookup"><span data-stu-id="d07d3-167">**q**</span></span>|<span data-ttu-id="d07d3-168">Trimestre</span><span class="sxs-lookup"><span data-stu-id="d07d3-168">Quarter</span></span>|  
    |<span data-ttu-id="d07d3-169">**a**</span><span class="sxs-lookup"><span data-stu-id="d07d3-169">**y**</span></span>|<span data-ttu-id="d07d3-170">Année</span><span class="sxs-lookup"><span data-stu-id="d07d3-170">Year</span></span>|  

    <span data-ttu-id="d07d3-171">Par exemple, « 3S » indique que le décalage est de trois semaines.</span><span class="sxs-lookup"><span data-stu-id="d07d3-171">For example, "3w" indicates that the offset time is three weeks.</span></span> <span data-ttu-id="d07d3-172">Pour indiquer la période en cours, utilisez le préfixe « c » devant l'un de ces codes.</span><span class="sxs-lookup"><span data-stu-id="d07d3-172">To indicate the current period, prefix to any of these codes with the letter “c”.</span></span> <span data-ttu-id="d07d3-173">Par exemple, si vous souhaitez que le décalage porte sur le mois en cours, entrez **mc**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-173">For example, if you want the offset time to be the current month, enter **cm**.</span></span>  
3. <span data-ttu-id="d07d3-174">Entrez une série de numéros dans le champ **N° promesse de livraison** en sélectionnant une ligne dans la liste de la fenêtre **Séries de n°**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-174">Enter a number series in the **Order Promising Nos.** field by selecting a line from the list in the **No. Series** window.</span></span>  
4. <span data-ttu-id="d07d3-175">Entrez un modèle promesse de livraison dans le champ **Modèle promesse de livraison** en sélectionnant une ligne de la liste de la fenêtre **Liste des modèles demande achat**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-175">Enter an order promising template in the **Order Promising Template** field by selecting a line from the list in the **Req. Worksheet Template List** window.</span></span>  
5. <span data-ttu-id="d07d3-176">Entrez une feuille de réquisition dans le champ **Feuille promesse de livraison** en sélectionnant une ligne de la liste de la fenêtre **Noms feuilles de réquisition**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-176">Enter a requisition worksheet in the **Order Promising Worksheet** field by selecting a line from the list on the **Req. Wksh. Names** window.</span></span>

### <a name="to-enter-inbound-warehouse-handling-time-in-the-inventory-setup-window"></a><span data-ttu-id="d07d3-177">Pour entrer un délai enlogement dans la fenêtre de configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="d07d3-177">To enter inbound warehouse handling time in the inventory setup window</span></span>  
<span data-ttu-id="d07d3-178">Vous pouvez configurer un délai entrepôt par défaut pour l'inventaire et votre emplacement, à inclure dans le calcul de promesse livraison sur la ligne achat.</span><span class="sxs-lookup"><span data-stu-id="d07d3-178">If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory and for your location.</span></span>    
1. <span data-ttu-id="d07d3-179">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres stock**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d07d3-179">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="d07d3-180">Sur le raccourci **Général**, dans le champ **Délai enlogement**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-180">On the **General** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="d07d3-181">Si vous avez renseigné le champ **Délai enlogement** dans la **fiche magasin** pour votre magasin, ce champ est utilisé en tant que délai d'enlogement par défaut.</span><span class="sxs-lookup"><span data-stu-id="d07d3-181">If you have filled in the **Inbound Whse. Handling Time** field on the **Location Card** for your location this field is used as the default inbound warehouse handling time.</span></span>  

### <a name="to-enter-inbound-warehouse-handling-time-on-location-cards"></a><span data-ttu-id="d07d3-182">Pour entrer des délais d'enlogement dans les fiches emplacement</span><span class="sxs-lookup"><span data-stu-id="d07d3-182">To enter inbound warehouse handling time on location cards</span></span>  
1. <span data-ttu-id="d07d3-183">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Emplacement**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d07d3-183">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Location**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="d07d3-184">Ouvrez la fiche emplacement appropriée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-184">Open the relevant location card.</span></span>  
3.  <span data-ttu-id="d07d3-185">Sur le raccourci **Entrepôt**, dans le champ **Délai enlogement**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-185">On the **Warehouse** FastTab, in the **Inbound Whse. Handling Time** field, enter the number of days that you want to be included in the order promising calculation.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="d07d3-186">Si vous laissez le champ **Délai enlogement** vide, le calcul utilise la valeur de la fenêtre **Paramètres stock**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-186">If you leave the **Inbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  window.</span></span>

### <a name="to-enter-outbound-warehouse-handling-time-in-the-inventory-setup-window"></a><span data-ttu-id="d07d3-187">Pour entrer un délai désenlogement dans la fenêtre de configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="d07d3-187">To enter outbound warehouse handling time in the inventory setup window</span></span>  
<span data-ttu-id="d07d3-188">Vous pouvez configurer un délai désenlogement par défaut pour l'inventaire, à inclure dans le calcul de promesse livraison sur la ligne de vente.</span><span class="sxs-lookup"><span data-stu-id="d07d3-188">If you want to set up an outbound warehouse handling time to be included in the order promising calculation on the sales line, you can set this up as a default for the inventory.</span></span>

1. <span data-ttu-id="d07d3-189">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres stock**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d07d3-189">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="d07d3-190">Sur le raccourci **Général**, dans le champ **Délai enlogement sortant**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-190">On the **General** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days you want to include in the order promising calculation.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="d07d3-191">Si vous avez renseigné le champ **Délai enlogement sortant** dans la fiche magasin pour votre magasin, ce champ est utilisé en tant que délai d'enlogement sortant par défaut.</span><span class="sxs-lookup"><span data-stu-id="d07d3-191">If you have filled in the **Outbound Whse. Handling Time** field on the Location card for your location, this field is used as the default outbound warehouse handling time.</span></span>  

### <a name="to-enter-outbound-warehouse-handling-time-on-location-cards"></a><span data-ttu-id="d07d3-192">Pour entrer un délai de désenlogement sortant dans les fiches emplacement</span><span class="sxs-lookup"><span data-stu-id="d07d3-192">To enter outbound warehouse handling time on location cards</span></span>  
1.  <span data-ttu-id="d07d3-193">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d07d3-193">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="d07d3-194">Ouvrez la fiche emplacement appropriée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-194">Open the relevant location card.</span></span>  
3.  <span data-ttu-id="d07d3-195">Sur le raccourci **Entrepôt**, dans le champ **Délai enlogement sortant**, indiquez le nombre de jours que vous souhaitez inclure dans le calcul de la promesse de livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-195">On the **Warehouse** FastTab, in the **Outbound Whse. Handling Time** field, enter the number of days that you want to include in the order promising calculation.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="d07d3-196">Si vous laissez le champ **Délai désenlogement** vide, le calcul utilise la valeur de la fenêtre **Paramètres stock**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-196">If you leave the **Outbound Whse. Handling Time** field blank, then the calculation uses the value in the **Inventory Setup**  window.</span></span>

## <a name="to-make-an-item-critical"></a><span data-ttu-id="d07d3-197">Pour affecter le statut critique à un article</span><span class="sxs-lookup"><span data-stu-id="d07d3-197">To make an item critical</span></span>  
<span data-ttu-id="d07d3-198">Avant qu'un article puisse être inclus dans le calcul de la promesse de livraison, il doit être signalé comme critique.</span><span class="sxs-lookup"><span data-stu-id="d07d3-198">Before an item can be included in the order promising calculation, it must be marked as critical.</span></span> <span data-ttu-id="d07d3-199">Cette configuration garantit que les articles non critiques ne génèrent pas de calculs inutiles de promesse de livraison.</span><span class="sxs-lookup"><span data-stu-id="d07d3-199">This setup ensures that non-critical items do not cause irrelevant order promising calculations.</span></span>   
1.  <span data-ttu-id="d07d3-200">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Articles**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d07d3-200">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="d07d3-201">Ouvrez la fiche article appropriée.</span><span class="sxs-lookup"><span data-stu-id="d07d3-201">Open the relevant item card.</span></span>  
3.  <span data-ttu-id="d07d3-202">Sur le raccourci **Planifié**, sélectionnez le champ **Critique**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-202">On the **Planning** FastTab, select the **Critical** field.</span></span>  

## <a name="to-calculate-an-order-promising-date"></a><span data-ttu-id="d07d3-203">Pour calculer une date promesse livraison</span><span class="sxs-lookup"><span data-stu-id="d07d3-203">To calculate an order promising date</span></span>  
1.  <span data-ttu-id="d07d3-204">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Document de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d07d3-204">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Order**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="d07d3-205">Ouvrez le document de vente approprié et sélectionnez les lignes de document de vente que vous souhaitez que le programme calcule.</span><span class="sxs-lookup"><span data-stu-id="d07d3-205">Open the relevant sales order and select the sales order lines that you want the program to calculate.</span></span>  
3.  <span data-ttu-id="d07d3-206">Choisissez l'action **Promesse de livraison**, puis sélectionnez l'action **Lignes promesse de livraison**.</span><span class="sxs-lookup"><span data-stu-id="d07d3-206">Choose the **Order Promising** action, and then choose the **Order Promising Lines** action.</span></span>  
4.  <span data-ttu-id="d07d3-207">Sélectionnez une ligne, puis l'une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="d07d3-207">Select a line, and then select one of the following options:</span></span>  

    - <span data-ttu-id="d07d3-208">Choisissez **Disponible à la vente** si vous souhaitez calculer la date la plus proche à laquelle l'article sera disponible pour ce qui est de l'inventaire, des réceptions programmées, et des besoins bruts.</span><span class="sxs-lookup"><span data-stu-id="d07d3-208">Select **Available-to-Promise** if you want to calculate the earliest date that the item will be available with respect to inventory, scheduled receipts, and gross requirements.</span></span>  
    - <span data-ttu-id="d07d3-209">Choisissez **Simulation de délai** si vous savez que l'article est actuellement en rupture de stock et que vous souhaitez calculer la date la plus proche à laquelle cet article sera disponible grâce à l'émission de demandes de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="d07d3-209">Select **Capable-to-Promise** if you know that the item is presently out of stock and you want to calculate the earliest date that the item can be available by issuing new replenishment requisitions.</span></span>  
5.  <span data-ttu-id="d07d3-210">Choisissez le bouton **Accepter** pour accepter la date d'expédition disponible la plus proche.</span><span class="sxs-lookup"><span data-stu-id="d07d3-210">Choose the **Accept** button to accept the earliest shipment date available.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d07d3-211">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d07d3-211">See Also</span></span>  
[<span data-ttu-id="d07d3-212">Vente</span><span class="sxs-lookup"><span data-stu-id="d07d3-212">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="d07d3-213">Calcul de la date des achats</span><span class="sxs-lookup"><span data-stu-id="d07d3-213">Date Calculation for Purchases</span></span>](purchasing-date-calculation-for-purchases.md)  
<span data-ttu-id="d07d3-214">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="d07d3-214">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
