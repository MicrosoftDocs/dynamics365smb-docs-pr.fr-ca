---
title: "Détails de conception - Intégration avec l'inventaire | Microsoft Docs"
description: "Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 00a12f3f2203ed3b22cfee1af6aa8f155ca5fe4b
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="design-details-integration-with-inventory"></a><span data-ttu-id="ae1cd-103">Détails de conception : intégration avec l'inventaire</span><span class="sxs-lookup"><span data-stu-id="ae1cd-103">Design Details: Integration with Inventory</span></span>
<span data-ttu-id="ae1cd-104">Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-104">The Warehouse Management application area and the Inventory application area interact with one another in physical inventory and in inventory or warehouse adjustment.</span></span>  
  
## <a name="physical-inventory"></a><span data-ttu-id="ae1cd-105">Inventaire physique</span><span class="sxs-lookup"><span data-stu-id="ae1cd-105">Physical Inventory</span></span>  
 <span data-ttu-id="ae1cd-106">La fenêtre **Feuille inventaire entrepôt** est utilisée avec la fenêtre **Feuille inventaire** pour tous les entrepôts avancés.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-106">The **Whse. Phys. Inventory Journal** window is used with the **Phys. Inventory Journal** window for all advanced warehouse locations.</span></span> <span data-ttu-id="ae1cd-107">L'inventaire au niveau de la zone est calculé, et une liste imprimée est donnée au magasinier.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-107">The inventory on bin level is calculated, and a printed list is provided for the warehouse employee.</span></span> <span data-ttu-id="ae1cd-108">La liste indique les articles dans lesquels les emplacements doivent être comptabilisés.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-108">The list shows which items in which bins must be counted.</span></span>  
  
 <span data-ttu-id="ae1cd-109">Le magasinier entre la quantité comptée dans la fenêtre **Feuille inventaire entrepôt** puis valide la feuille.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-109">The warehouse employee enters the counted quantity in the **Whse. Phys. Inventory Journal** window and then posts the journal.</span></span>  
  
 <span data-ttu-id="ae1cd-110">Si la quantité comptée est supérieure à la quantité indiquée sur la ligne journal, un mouvement est reporté pour cette différence à partir de la zone d'ajustement par défaut vers la zone dans laquelle les articles ont été comptés.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-110">If the counted quantity is greater than the quantity on the journal line, a movement is posted for this difference from the default adjustment bin to the counted bin.</span></span> <span data-ttu-id="ae1cd-111">Cela augmente la quantité dans la zone ayant fait l'objet du comptage et diminue la quantité dans la zone d'ajustement par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-111">This increases the quantity in the counted bin and decreases the quantity in the default adjustment bin.</span></span>  
  
 <span data-ttu-id="ae1cd-112">Si la quantité comptée est inférieure à la quantité indiquée sur la ligne journal, un mouvement pour cette différence est reporté à partir de la zone ayant fait l'objet du comptage vers la zone d'ajustement par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-112">If the quantity counted is less than the quantity on the journal line, a movement for this difference is posted from the counted bin to the default adjustment bin.</span></span> <span data-ttu-id="ae1cd-113">Cela diminue la quantité dans la zone ayant fait l'objet du comptage et augmente la quantité dans la zone d'ajustement par défaut.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-113">This decreases the quantity in the counted bin and increases the quantity in the default adjustment bin.</span></span>  
  
 <span data-ttu-id="ae1cd-114">Dans les configurations d'entrepôt avancées, la valeur du champ **Quantité (calculée)** est extraite à partir des écritures article et celle du champ **Quantité (inventaire physique)** est extraite à partir des écritures entrepôt, à l'exception du contenu de la zone d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-114">In advanced warehouse configurations, the value in the **Quantity (Calculated)** field is retrieved from item ledger entries and the value in the **Quantity (Phys. Inventory)** field is retrieved from warehouse entries, excluding the adjustment bin content.</span></span> <span data-ttu-id="ae1cd-115">Le champ **Quantité** spécifie la différence entre les deux premiers champs, qui doit être égale au contenu de l'emplacement ajustement.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-115">The **Quantity** field specifies the difference between the first two fields, which should be equal to the contents of the adjustment bin.</span></span>  
  
 <span data-ttu-id="ae1cd-116">Lorsque vous reportez le journal inventaire physique, l'inventaire et la zone d'ajustement par défaut sont mis à jour.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-116">When you post the physical inventory journal, the inventory and the default adjustment bin are updated.</span></span>  
  
### <a name="warehouse-adjustments-to-the-item-ledger"></a><span data-ttu-id="ae1cd-117">Ajustements entrepôt dans le grand livre article</span><span class="sxs-lookup"><span data-stu-id="ae1cd-117">Warehouse Adjustments to the Item Ledger</span></span>  
 <span data-ttu-id="ae1cd-118">Vous utilisez la fenêtre **Feuille article** et la fonction **Calculer ajustement entrepôt** pour ajuster le stock dans l'écriture article conformément à ajustement qui a été apporté sur la quantité d'un article dans un emplacement entrepôt.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-118">You use the **Item Journal** window and the **Calculate Whse. Adjustment** function to adjust inventory on the item ledger in accordance with an adjustment that has been made to the item quantity in a warehouse bin.</span></span> <span data-ttu-id="ae1cd-119">Pour créer un lien entre l'inventaire et l'entrepôt, vous devez définir une zone d'ajustement par défaut par emplacement.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-119">To create a link between the inventory and the warehouse, you must define a default adjustment bin per location.</span></span>  
  
 <span data-ttu-id="ae1cd-120">La zone d'ajustement par défaut enregistre les articles dans l'entrepôt lorsque vous reportez une augmentation dans l'inventaire.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-120">The default adjustment bin registers items in the warehouse when you post an increase for the inventory.</span></span> <span data-ttu-id="ae1cd-121">Toutefois, si vous reportez une diminution, la quantité sur la zone par défaut est également diminuée.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-121">However, if you post a decrease, the quantity on the default bin is also decreased.</span></span> <span data-ttu-id="ae1cd-122">Dans les deux cas, des écritures du grand livre d'articles et des écritures entrepôt sont créées.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-122">In both cases, item ledger entries and warehouse entries are created.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ae1cd-123">La zone d'ajustement n'est pas incluse dans le calcul de disponibilité.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-123">The adjustment bin is not included in the availability calculation.</span></span>  
  
 <span data-ttu-id="ae1cd-124">Si vous souhaitez ajuster le contenu de la zone, vous pouvez utiliser le journal article entrepôt, à partir duquel vous pouvez saisir le numéro d'article, le code de zone, le code de zone et la quantité que vous voulez ajuster.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-124">If you want to adjust the bin content, you can use the warehouse item journal, from which you can enter the item number, zone code, bin code, and quantity that you want to adjust.</span></span>  
  
 <span data-ttu-id="ae1cd-125">Si vous saisissez une quantité positive et reportez la ligne, l'inventaire enregistré dans la zone augmente, et la quantité de la zone d'ajustement par défaut diminue en conséquence.</span><span class="sxs-lookup"><span data-stu-id="ae1cd-125">If you enter a positive quantity and post the line, then the inventory stored in the bin increases, and the quantity of the default adjustment bin decreases correspondingly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae1cd-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ae1cd-126">See Also</span></span>  
 <span data-ttu-id="ae1cd-127">[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md) </span><span class="sxs-lookup"><span data-stu-id="ae1cd-127">[Design Details: Warehouse Management](design-details-warehouse-management.md) </span></span>  
 [<span data-ttu-id="ae1cd-128">Détails de conception : disponibilité dans l'entrepôt</span><span class="sxs-lookup"><span data-stu-id="ae1cd-128">Design Details: Availability in the Warehouse</span></span>](design-details-availability-in-the-warehouse.md)
