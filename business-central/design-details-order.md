---
title: Détails de conception - Commande | Microsoft Docs
description: Cette rubrique fournit des informations sur les liens commande-à-commande dans un environnement de fabrication à la commande.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, order
ms.date: 10/01/2018
ms.author: sgroespe
redirect_url: design-details-handling-reordering-policies
ms.openlocfilehash: 4152dfb744215034383239ea98847fbf7b5751e9
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813489"
---
# <a name="design-details-order"></a><span data-ttu-id="ad94f-103">Détails de conception : commande</span><span class="sxs-lookup"><span data-stu-id="ad94f-103">Design Details: Order</span></span>
<span data-ttu-id="ad94f-104">Dans un environnement de fabrication à la commande, un article est acheté ou produit pour couvrir exclusivement une demande spécifique.</span><span class="sxs-lookup"><span data-stu-id="ad94f-104">In a make-to-order environment, an item is purchased or produced to exclusively cover a specific demand.</span></span> <span data-ttu-id="ad94f-105">Généralement, il se rapporte aux articles A, et la motivation pour choisir cette méthode de réapprovisionnement de commande peut être que la demande n'est pas fréquente, le délai de production est insignifiant ou les attributs requis varient.</span><span class="sxs-lookup"><span data-stu-id="ad94f-105">Typically it relates to A-items, and the motivation for choosing the order reordering policy can be that the demand is infrequent, the lead-time is insignificant, or the required attributes vary.</span></span>  

<span data-ttu-id="ad94f-106">Le programme crée un lien commande à commande, qui agit en tant que connexion préliminaire entre l'approvisionnement, une commande d'approvisionnement ou un inventaire, et la demande qu'il va traiter.</span><span class="sxs-lookup"><span data-stu-id="ad94f-106">The program creates an order-to-order link, which acts as a preliminary connection between the supply, a supply order or inventory, and the demand that it is going to fulfill.</span></span>  

<span data-ttu-id="ad94f-107">Outre l'utilisation de la méthode de commande, le lien commande à commande peut s'appliquer lors de la planification, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ad94f-107">Apart from using the Order policy, the order-to-order link can be applied during planning in the following ways:</span></span>  

* <span data-ttu-id="ad94f-108">Lors de l'utilisation de la méthode de fabrication Prod. pour commande pour créer des bons de production de type multiniveau ou projet (la production avait besoin de composantes sur le même bon de production).</span><span class="sxs-lookup"><span data-stu-id="ad94f-108">When using the Make-to-Order manufacturing policy to create multi-level or project type production orders (producing needed components on the same production order).</span></span>  
* <span data-ttu-id="ad94f-109">Lors de l'utilisation de la fonction Planification document de vente pour créer un bon de production à partir d'un document de vente.</span><span class="sxs-lookup"><span data-stu-id="ad94f-109">When using the Sales Order Planning feature to create a production order from a sales order.</span></span>  

<span data-ttu-id="ad94f-110">Même si une compagnie manufacturière se considère comme un environnement de fabrication à la commande, il peut être préférable d'utiliser une méthode de réapprovisionnement Lot pour lot si les articles sont des standards purs sans variation au niveau des attributs.</span><span class="sxs-lookup"><span data-stu-id="ad94f-110">Even if a manufacturing company considers itself as a make-to-order environment, it might be best to use a Lot-for-Lot reordering policy if the items are pure standard without variation in attributes.</span></span> <span data-ttu-id="ad94f-111">Par conséquent, le système utilise l'inventaire non planifié et additionne uniquement les documents de vente ayant la même date de livraison ou faisant partie d'une plage de temps définie.</span><span class="sxs-lookup"><span data-stu-id="ad94f-111">As a result, the system will use unplanned inventory and only accumulates sales orders with the same shipment date or within a defined time bucket.</span></span>  

## <a name="order-to-order-links-and-past-due-dates"></a><span data-ttu-id="ad94f-112">Liens commande à commande et dates d'échéance passées</span><span class="sxs-lookup"><span data-stu-id="ad94f-112">Order-to-Order Links and Past Due Dates</span></span>  
<span data-ttu-id="ad94f-113">Contrairement à la plupart des ensembles approvisionnement-demande, les commandes liées avec des dates d'échéance antérieures à la date début de la planification sont entièrement planifiées par le système.</span><span class="sxs-lookup"><span data-stu-id="ad94f-113">Unlike most supply-demand sets, linked orders with due dates before the planning starting date are fully planned for by the system.</span></span> <span data-ttu-id="ad94f-114">La raison commerciale de cette exception est que les ensembles spécifiques approvisionnement-demande doivent être synchronisés jusqu'à l'exécution.</span><span class="sxs-lookup"><span data-stu-id="ad94f-114">The business reason for this exception is that specific demand-supply sets must be synchronized through to execution.</span></span> <span data-ttu-id="ad94f-115">Pour plus d'informations sur la zone gelée qui s'applique à la plupart des types de demande-approvisionnement, voir [Détails de conception : traiter les commandes avant la date début de la planification](design-details-dealing-with-orders-before-the-planning-starting-date.md).</span><span class="sxs-lookup"><span data-stu-id="ad94f-115">For more information about the frozen zone that applies to most demand-supply types, see [Design Details: Dealing with Orders Before the Planning Starting Date](design-details-dealing-with-orders-before-the-planning-starting-date.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="ad94f-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ad94f-116">See Also</span></span>  
<span data-ttu-id="ad94f-117">[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="ad94f-117">[Design Details: Reordering Policies](design-details-reordering-policies.md) </span></span>  
<span data-ttu-id="ad94f-118">[Détails de conception : paramètres de planification](design-details-planning-parameters.md) </span><span class="sxs-lookup"><span data-stu-id="ad94f-118">[Design Details: Planning Parameters](design-details-planning-parameters.md) </span></span>  
<span data-ttu-id="ad94f-119">[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) </span><span class="sxs-lookup"><span data-stu-id="ad94f-119">[Design Details: Handling Reordering Policies](design-details-handling-reordering-policies.md) </span></span>  
[<span data-ttu-id="ad94f-120">Détails de conception : planification de l'approvisionnement</span><span class="sxs-lookup"><span data-stu-id="ad94f-120">Design Details: Supply Planning</span></span>](design-details-supply-planning.md)
