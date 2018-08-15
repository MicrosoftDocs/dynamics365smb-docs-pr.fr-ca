---
title: "Détails de conception - Traiter les commandes avant la date début de la planification | Microsoft Docs"
description: "Cette rubrique décrit les règles appliquées par la planification aux commandes dans la zone gelée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: planning, frozen, design serial, lot
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 4fc4afa14f9f2a989fae0b1ca8ee0e61fe24fd21
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-dealing-with-orders-before-the-planning-starting-date"></a><span data-ttu-id="50065-103">Détails de conception : traiter les commandes avant la date début de la planification</span><span class="sxs-lookup"><span data-stu-id="50065-103">Design Details: Dealing with Orders Before the Planning Starting Date</span></span>
<span data-ttu-id="50065-104">Pour éviter qu'un programme d'approvisionnement affiche des suggestions impossibles et donc inutiles, le système de planification considère la période jusqu'à la date début de la planification comme une zone gelée pour laquelle rien n'est programmé.</span><span class="sxs-lookup"><span data-stu-id="50065-104">To avoid that a supply plan shows impossible and therefore useless suggestions, the planning system regards the period up until the planning starting date a frozen zone where nothing is planned for.</span></span> <span data-ttu-id="50065-105">La règle suivante affecte la zone gelée :</span><span class="sxs-lookup"><span data-stu-id="50065-105">The following rule applies to the frozen zone:</span></span>  
  
<span data-ttu-id="50065-106">L'ensemble de l'offre et de la demande antérieur à la date début de la période de planification sera considéré comme faisant partie de l'inventaire ou comme étant livré.</span><span class="sxs-lookup"><span data-stu-id="50065-106">All supply and demand before the starting date of the planning period will be considered a part of inventory or shipped.</span></span>  
  
<span data-ttu-id="50065-107">Par conséquent, le système de planification, à quelques exceptions près, ne va suggérer aucune modification des commandes approvisionnement de la zone gelée. Par ailleurs, aucun lien de chaînage n'est créé ou mis à jour pour cette période.</span><span class="sxs-lookup"><span data-stu-id="50065-107">Accordingly, the planning system will not, with a few exceptions, suggest any changes to supply orders in the frozen zone, and no order tracking links are created or maintained for that period.</span></span>  
  
<span data-ttu-id="50065-108">Les exceptions à cette règle sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="50065-108">The exceptions to this rule are as follows:</span></span>  
  
* <span data-ttu-id="50065-109">Si l'inventaire disponible prévu, y compris la somme de la demande et de l'approvisionnement dans la zone gelée, est inférieur à zéro.</span><span class="sxs-lookup"><span data-stu-id="50065-109">If the projected available inventory, including the sum of supply and demand in the frozen zone, is below zero.</span></span>  
* <span data-ttu-id="50065-110">Si les numéros de série/lot sont nécessaires sur la ou les commandes antidatées.</span><span class="sxs-lookup"><span data-stu-id="50065-110">If serial/lot numbers are required on the backdated order(s).</span></span>  
* <span data-ttu-id="50065-111">Si l'ensemble demande-approvisionnement est lié par une stratégie ordre pour ordre.</span><span class="sxs-lookup"><span data-stu-id="50065-111">If the supply-demand set is linked by an order-to-order policy.</span></span>  
  
<span data-ttu-id="50065-112">Si l'inventaire disponible d'origine est inférieur à zéro, le système de planification suggère une commande approvisionnement d'urgence la veille de la période de planification pour couvrir la quantité manquante.</span><span class="sxs-lookup"><span data-stu-id="50065-112">If the initial available inventory is below zero, the planning system suggests an emergency supply order on the day before the planning period to cover the missing quantity.</span></span> <span data-ttu-id="50065-113">Par conséquent, l'inventaire disponible prévu est toujours au moins à zéro lorsque la planification de la période future commence.</span><span class="sxs-lookup"><span data-stu-id="50065-113">Consequently, the projected and available inventory will always be at least zero when planning for the future period begins.</span></span> <span data-ttu-id="50065-114">La ligne planification de cette commande approvisionnement affiche une icône d'avertissement Urgence et des informations supplémentaires sont fournies lors de la recherche.</span><span class="sxs-lookup"><span data-stu-id="50065-114">The planning line for this supply order will display an Emergency warning icon and additional information is provided upon lookup.</span></span>  
  
## <a name="seriallot-numbers-and-order-to-order-links-are-exempt-from-the-frozen-zone"></a><span data-ttu-id="50065-115">Les numéros de série et/ou de lot et les liens ordre pour ordre sont exempts de la zone gelée</span><span class="sxs-lookup"><span data-stu-id="50065-115">Serial/Lot Numbers and Order-to-Order Links are Exempt from the Frozen Zone</span></span>  
<span data-ttu-id="50065-116">Si les numéros de série/lot sont requis ou si un lien ordre pour ordre existe, le système de planification ignore la zone gelée et incorpore ces quantités antidatées à partir de la date début et propose éventuellement des actions de correction si la demande et l'approvisionnement ne sont pas synchronisés.</span><span class="sxs-lookup"><span data-stu-id="50065-116">If serial/lot numbers are required or an order-to-order link exists, the planning system will disregard the frozen zone and incorporate such quantities that are back-dated from the starting date and potentially suggest corrective actions if demand and supply is not synchronized.</span></span> <span data-ttu-id="50065-117">La raison commerciale de ce principe est que ces ensembles approvisionnement-demande spécifiques doivent correspondre pour garantir que cette demande spécifique soit satisfaite.</span><span class="sxs-lookup"><span data-stu-id="50065-117">The business reason for this principle is that such specific demand-supply sets must match to ensure that this specific demand is fulfilled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50065-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50065-118">See Also</span></span>  
<span data-ttu-id="50065-119">[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md) </span><span class="sxs-lookup"><span data-stu-id="50065-119">[Design Details: Balancing Demand and Supply](design-details-balancing-demand-and-supply.md) </span></span>  
<span data-ttu-id="50065-120">[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md) </span><span class="sxs-lookup"><span data-stu-id="50065-120">[Design Details: Central Concepts of the Planning System](design-details-central-concepts-of-the-planning-system.md) </span></span>  
[<span data-ttu-id="50065-121">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="50065-121">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)