---
title: "Méthodes TEC pour calculer et enregistrer la progression d'un projet| Microsoft Docs"
description: "Décrit les différentes méthodes de travaux en cours (TEC) qui peuvent être utilisées pour reporter, surveiller et calculer les données financières des projets en cours."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: work in process, work in progress, calculate project WIP
ms.date: 06/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 85724fd6f43c684007dd22b34665438bf22bf99a
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="understanding-wip-methods"></a><span data-ttu-id="4397b-103">Comprendre les méthodes TEC</span><span class="sxs-lookup"><span data-stu-id="4397b-103">Understanding WIP Methods</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="4397b-104"> prend en charge les méthodes suivantes pour calculer et enregistrer la valeur des travaux en cours.</span><span class="sxs-lookup"><span data-stu-id="4397b-104"> supports the following methods of calculating and recording the value of work in process.</span></span>

| <span data-ttu-id="4397b-105">Méthode TEC</span><span class="sxs-lookup"><span data-stu-id="4397b-105">WIP Method</span></span> | <span data-ttu-id="4397b-106">Formule de calcul</span><span class="sxs-lookup"><span data-stu-id="4397b-106">Calculation Formula</span></span> | <span data-ttu-id="4397b-107">Description du calcul</span><span class="sxs-lookup"><span data-stu-id="4397b-107">Calculation Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="4397b-108">Valeur de coût</span><span class="sxs-lookup"><span data-stu-id="4397b-108">Cost Value</span></span> |<span data-ttu-id="4397b-109">Revenus réceptionnés = Facturable (prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-109">Recognized Revenue = Billable Invoiced Price</span></span><br /><br /> <span data-ttu-id="4397b-110">Coûts totaux estimés = Facturable (prix total) x Coût budgétaire (ratio)</span><span class="sxs-lookup"><span data-stu-id="4397b-110">Estimated Total Costs = Billable Total Price x Budget Cost Ratio</span></span><br /><br /> <span data-ttu-id="4397b-111">Coûts TEC = (Pourcentage avancement - % facturé) x Coûts totaux estimés</span><span class="sxs-lookup"><span data-stu-id="4397b-111">WIP Costs = (Percentage of Completion - Invoiced %) x Estimated Total Costs</span></span><br /><br /> <span data-ttu-id="4397b-112">Pourcentage avancement = Utilisation (coûts indiqués) / Budget (coûts indiqués)</span><span class="sxs-lookup"><span data-stu-id="4397b-112">Percentage of Completion = Usage Total Costs / Budget Total Costs</span></span><br /> <span data-ttu-id="4397b-113">% facturé = Facturable (prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-113">Invoiced % = Billable Invoiced Price</span></span><br /><br /> <span data-ttu-id="4397b-114">Coûts réceptionnés facturables (prix total)= Utilisation (coûts indiqués) - TEC</span><span class="sxs-lookup"><span data-stu-id="4397b-114">Billable Total Price Recognized Costs = Usage Total Costs - WIP</span></span> |<span data-ttu-id="4397b-115">Le calcul Valeur de coût commence par calculer la valeur du montant fourni en prenant une proportion des coûts totaux estimés basée sur le pourcentage d'achèvement.</span><span class="sxs-lookup"><span data-stu-id="4397b-115">Cost value calculations start by calculating the value of what has been provided by taking a proportion of the estimated total costs based on percentage of completion.</span></span> <span data-ttu-id="4397b-116">Les coûts facturés sont soustraits en prenant une proportion des coûts totaux estimés basée sur le pourcentage facturé.</span><span class="sxs-lookup"><span data-stu-id="4397b-116">Invoiced costs are subtracted by taking a proportion of the estimated total costs based on the invoiced percentage.</span></span><br /><br /> <span data-ttu-id="4397b-117">Ce calcule nécessite que le prix total facturable, le prix total du budget et les coûts budgétaires totaux soient correctement renseignés pour l'ensemble du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-117">This calculation requires that the billable total price, budget total price, and budget total costs be correctly entered for the whole job.</span></span> |
| <span data-ttu-id="4397b-118">Coût des ventes</span><span class="sxs-lookup"><span data-stu-id="4397b-118">Cost of Sales</span></span> |<span data-ttu-id="4397b-119">Revenus réceptionnés = Facturable (prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-119">Recognized Revenue = Billable Invoiced Price</span></span><br /><br /> <span data-ttu-id="4397b-120">Coûts réceptionnés = Coût total du budget x Pourcentage facturé</span><span class="sxs-lookup"><span data-stu-id="4397b-120">Recognized Costs = Budget Total Cost x Invoiced Percentage</span></span><br /><br /> <span data-ttu-id="4397b-121">% facturé = Facturable (prix facturé) / Facturable (prix total)</span><span class="sxs-lookup"><span data-stu-id="4397b-121">Invoiced % = Billable Invoiced Price / Billable Total Price</span></span><br /><br /> <span data-ttu-id="4397b-122">(Le % facturé apparaît sous forme de colonne dans les lignes tâche projet)</span><span class="sxs-lookup"><span data-stu-id="4397b-122">(Invoiced % exists as column on job task lines)</span></span><br /><br /> <span data-ttu-id="4397b-123">Coûts TEC = Utilisation (coûts indiqués) – Coûts réceptionnés</span><span class="sxs-lookup"><span data-stu-id="4397b-123">WIP Costs = Usage Total Costs – Recognized Costs</span></span> |<span data-ttu-id="4397b-124">Le calcul Coût des ventes commence par calculer les coûts réceptionnés.</span><span class="sxs-lookup"><span data-stu-id="4397b-124">Cost of sales calculations begin by calculating the recognized costs.</span></span> <span data-ttu-id="4397b-125">Les coûts sont réceptionnés proportionnellement sur la base des coûts budgétaires totaux.</span><span class="sxs-lookup"><span data-stu-id="4397b-125">Costs are recognized proportionally based on budget total costs.</span></span><br /><br /> <span data-ttu-id="4397b-126">Ce calcule nécessite que le prix total facturable et les coûts budgétaires totaux soient correctement renseignés pour l'ensemble du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-126">This calculation requires that the billable total price and budget total costs be correctly entered for the whole job.</span></span> |
| <span data-ttu-id="4397b-127">Valeur des ventes</span><span class="sxs-lookup"><span data-stu-id="4397b-127">Sales Value</span></span> |<span data-ttu-id="4397b-128">Coûts réceptionnés = Utilisation (coûts indiqués)</span><span class="sxs-lookup"><span data-stu-id="4397b-128">Recognized Costs = Usage Total Costs</span></span><br /><br /> <span data-ttu-id="4397b-129">Revenus réceptionnés = Utilisation (prix total) x Facturation prévue (ratio)</span><span class="sxs-lookup"><span data-stu-id="4397b-129">Recognized Revenue = Usage Total Price x Expected invoicing ratio</span></span><br /><br /> <span data-ttu-id="4397b-130">% recouvrement des coûts = Facturable (prix total)/Prix total du budget</span><span class="sxs-lookup"><span data-stu-id="4397b-130">Cost Recovery % = Billable Total Price / Budget Total Price</span></span><br /><br /> <span data-ttu-id="4397b-131">Vente TEC = Ventes réceptionnées - Facturable (prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-131">WIP Sales = Recognized Sales - Billable Invoiced Price</span></span> |<span data-ttu-id="4397b-132">Le calcul Valeur des ventes réceptionne les revenus proportionnellement sur la base de l'utilisation (coûts indiqués) et du ratio attendu de recouvrement des coûts.</span><span class="sxs-lookup"><span data-stu-id="4397b-132">Sales value calculations recognize revenue proportionally based on usage total costs and the expected cost recovery ratio.</span></span><br /><br /> <span data-ttu-id="4397b-133">Ce calcule nécessite que le prix total facturable et le prix budgétaire total soient correctement renseignés pour l'ensemble du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-133">This calculation requires that the billable total price and budget total price be correctly entered for the whole job.</span></span> |
| <span data-ttu-id="4397b-134">Pourcentage d'achèvement</span><span class="sxs-lookup"><span data-stu-id="4397b-134">Percentage of Completion</span></span> |<span data-ttu-id="4397b-135">Coûts réceptionnés = Utilisation (coûts indiqués)</span><span class="sxs-lookup"><span data-stu-id="4397b-135">Recognized Costs = Usage Total Costs</span></span><br /><br /> <span data-ttu-id="4397b-136">Revenus réceptionnés = Facturable (prix total) x Pourcentage avancement</span><span class="sxs-lookup"><span data-stu-id="4397b-136">Recognized Revenue = Billable Total Price x Percentage of Completion</span></span><br /><br /> <span data-ttu-id="4397b-137">Pourcentage avancement = Utilisation (coûts indiqués) / Budget (coûts indiqués)</span><span class="sxs-lookup"><span data-stu-id="4397b-137">Percentage of Completion = Usage Total Costs / Budget Total Costs</span></span><br /> <span data-ttu-id="4397b-138">(Appelé « % achèvement coût » dans les lignes tâche projet)</span><span class="sxs-lookup"><span data-stu-id="4397b-138">(Referred to as "Cost Completion %" on job task lines)</span></span><br /><br /> <span data-ttu-id="4397b-139">Vente TEC = Ventes réceptionnées - Facturable (prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-139">WIP Sales = Recognized Sales - Billable Invoiced Price</span></span> |<span data-ttu-id="4397b-140">Le calcul Pourcentage avancement réceptionne les revenus proportionnellement sur la base du pourcentage d'achèvement, soit l'utilisation (coûts indiqués) par rapport aux coûts budgétés.</span><span class="sxs-lookup"><span data-stu-id="4397b-140">Percentage of completion calculations recognize revenue proportionally based on the percentage of completion, that is, usage total costs vs. budget costs.</span></span><br /><br /> <span data-ttu-id="4397b-141">Ce calcule nécessite que le prix total facturable et les coûts budgétaires totaux soient correctement renseignés pour l'ensemble du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-141">This calculation requires that the billable total price and budget total costs be correctly entered for the whole job.</span></span> |
| <span data-ttu-id="4397b-142">Contrat complété</span><span class="sxs-lookup"><span data-stu-id="4397b-142">Completed Contract</span></span> |<span data-ttu-id="4397b-143">Montant TEC = Coût indiqué TEC = Utilisation (coût total)</span><span class="sxs-lookup"><span data-stu-id="4397b-143">WIP Amount = WIP Cost Amount = Usage (Total Cost)</span></span><br /><br /> <span data-ttu-id="4397b-144">Montant vente TEC = Facturable (Prix facturé)</span><span class="sxs-lookup"><span data-stu-id="4397b-144">WIP Sales Amount = Billable (Invoiced Price)</span></span> |<span data-ttu-id="4397b-145">La méthode Fin de contrat ne réceptionne pas les revenus et les coûts avant la fin du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-145">Completed contract does not recognize revenue and costs until the job is complete.</span></span> <span data-ttu-id="4397b-146">Cela peut être utile lorsque l'estimation des coûts et des revenus du projet est excessivement difficile.</span><span class="sxs-lookup"><span data-stu-id="4397b-146">You may want to do this when there is high uncertainty around the estimates of costs and revenue for the job.</span></span><br /><br /> <span data-ttu-id="4397b-147">L'ensemble de l'utilisation est reporté dans le compte Coûts TEC (actif) et toutes les ventes facturées sont reportées dans le compte Ventes facturées TEC (passif) jusqu'à la fin du projet.</span><span class="sxs-lookup"><span data-stu-id="4397b-147">All usage is posted to the WIP Costs account (asset) and all invoiced sales are posted to the WIP Invoiced Sales account (liability) until the job is complete.</span></span> |

## <a name="see-also"></a><span data-ttu-id="4397b-148">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4397b-148">See Also</span></span>
[<span data-ttu-id="4397b-149">Gestion de projets</span><span class="sxs-lookup"><span data-stu-id="4397b-149">Project Management</span></span>](projects-manage-projects.md)  
[<span data-ttu-id="4397b-150">Finance</span><span class="sxs-lookup"><span data-stu-id="4397b-150">Finance</span></span>](finance.md)  
<span data-ttu-id="4397b-151">[Achats](purchasing-manage-purchasing.md)       </span><span class="sxs-lookup"><span data-stu-id="4397b-151">[Purchasing](purchasing-manage-purchasing.md)       </span></span>  
<span data-ttu-id="4397b-152">[Ventes](sales-manage-sales.md)    </span><span class="sxs-lookup"><span data-stu-id="4397b-152">[Sales](sales-manage-sales.md)    </span></span>  
<span data-ttu-id="4397b-153">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="4397b-153">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
