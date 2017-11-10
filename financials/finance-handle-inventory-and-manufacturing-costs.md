---
title: "Gestion des coûts inventaire et des coûts de fabrication | Microsoft Docs"
description: "Bien que la comptabilité analytique soit constituée de processus ne nécessitant pas d'interaction utilisateur, telle que l'affectation d'écritures et l'ajustement automatique des coûts, un certain nombre de champs, fenêtres et rapports sont destinés aux utilisateurs qui gèrent directement ou indirectement le coût des articles ou opérations."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/09/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 2745d8b06967549b32c8014a24ab9958c72c1c9d
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="handling-inventory-and-manufacturing-costs"></a><span data-ttu-id="face3-103">Gestion des coûts inventaire et des coûts de fabrication</span><span class="sxs-lookup"><span data-stu-id="face3-103">Handling Inventory and Manufacturing Costs</span></span>
<span data-ttu-id="face3-104">Bien que la comptabilité analytique soit constituée de processus ne nécessitant pas d'interaction utilisateur, telle que l'affectation d'écritures et l'ajustement automatique des coûts, un certain nombre de champs, fenêtres et rapports sont destinés aux utilisateurs qui gèrent directement ou indirectement le coût des articles ou opérations.</span><span class="sxs-lookup"><span data-stu-id="face3-104">Although much of the cost accounting functionality is expressed in underlying processes with no user interaction, such as entry application and automatic cost adjustment, a number of fields, windows, and reports are aimed at users who directly or indirectly manage the cost of items or operations.</span></span>  

 <span data-ttu-id="face3-105">L'affectation de frais annexes aux documents achat est un exemple d'une tâche de comptabilité analytique indirecte.</span><span class="sxs-lookup"><span data-stu-id="face3-105">Assigning item charges to purchase documents is an example of an indirect cost accounting task.</span></span> <span data-ttu-id="face3-106">La mise à jour du coût unitaire de l'article d'assemblage ou de nomenclature production est un exemple de tâche de comptabilité analytique directe.</span><span class="sxs-lookup"><span data-stu-id="face3-106">Updating the unit cost of assembly or production BOM item is an example of a more direct cost accounting task.</span></span>  

 <span data-ttu-id="face3-107">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="face3-107">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>   

|<span data-ttu-id="face3-108">**Pour**</span><span class="sxs-lookup"><span data-stu-id="face3-108">**To**</span></span>|<span data-ttu-id="face3-109">**Voir**</span><span class="sxs-lookup"><span data-stu-id="face3-109">**See**</span></span>|  
|------------|-------------|  
|<span data-ttu-id="face3-110">Mettre à jour périodiquement ou automatiquement le coût unitaire d'un ou plusieurs articles afin de faire suivre toutes les modifications de prix des écritures entrantes, telles que celles des achats ou des sorties de production, vers les écritures sortantes, telles que la consommation ou les transferts.</span><span class="sxs-lookup"><span data-stu-id="face3-110">Periodically or automatically update the unit cost of one or multiple items to forward any cost changes from inbound entries, such as those for purchases or production output, to the related outbound entries, such as consumption or transfers.</span></span>|[<span data-ttu-id="face3-111">Procédure : ajustement des coûts article</span><span class="sxs-lookup"><span data-stu-id="face3-111">How to: Adjust Item Costs</span></span>](inventory-how-adjust-item-costs.md)|  
|<span data-ttu-id="face3-112">Obtenir un aperçu de la dynamique coût moyen afin de prendre des décisions relatives aux prix ou de suivre les fluctuations des coûts causées par les erreurs de saisie.</span><span class="sxs-lookup"><span data-stu-id="face3-112">Get insight into average cost dynamics to make pricing decisions or to track cost fluctuations caused by data entry errors.</span></span>|[<span data-ttu-id="face3-113">Procédure : enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="face3-113">How to: Register New Items</span></span>](inventory-how-register-new-items.md)|  
|<span data-ttu-id="face3-114">Créer le coût standard d'un article de production en saisissant les trois éléments de coût : le coût matière, le coût capacité et le coût de sous-traitance.</span><span class="sxs-lookup"><span data-stu-id="face3-114">Create a manufacturing item's standard cost by entering the three cost elements: material cost, capacity cost, and subcontractor cost.</span></span>|[<span data-ttu-id="face3-115">À propos du calcul des coûts standard</span><span class="sxs-lookup"><span data-stu-id="face3-115">About Calculating Standard Cost</span></span>](finance-about-calculating-standard-cost.md)|  
|<span data-ttu-id="face3-116">Calculer le coût unitaire d'un article de nomenclature à partir des coûts unitaires de ses composants sous-jacents.</span><span class="sxs-lookup"><span data-stu-id="face3-116">Calculate the unit cost of a BOM item based on the unit costs of its underlying components.</span></span>|[<span data-ttu-id="face3-117">Procédure : utiliser les nomenclatures</span><span class="sxs-lookup"><span data-stu-id="face3-117">How to: Work with Bills of Material</span></span>](inventory-how-work-BOMs.md)|  
|<span data-ttu-id="face3-118">Terminer le cycle de vie de l'évaluation coût d'un article produit en ajustant les coûts et en rapprochant les écritures valeur du grand livre.</span><span class="sxs-lookup"><span data-stu-id="face3-118">Complete the costing life cycle of a produced item by adjusting the costs and reconciling the value entries with the general ledger.</span></span>|[<span data-ttu-id="face3-119">À propos des coûts des bons de production achevés</span><span class="sxs-lookup"><span data-stu-id="face3-119">About Finished Production Order Costs</span></span>](finance-about-finished-production-order-costs.md)|  
|<span data-ttu-id="face3-120">Modifiez la valeur d'un article dans l'inventaire ou la valeur d'une écriture du grand livre article, telle qu'une transaction d'achat.</span><span class="sxs-lookup"><span data-stu-id="face3-120">Change the value of an item in inventory or the value of one item ledger entry, such as a purchase transaction.</span></span>|[<span data-ttu-id="face3-121">Procédure : réévaluer le stock</span><span class="sxs-lookup"><span data-stu-id="face3-121">How to: Revalue Inventory</span></span>](inventory-how-revalue-inventory.md)|
|<span data-ttu-id="face3-122">Annulez manuellement l'affectation d'un article ou réaffectez des écritures article créées par le programme.</span><span class="sxs-lookup"><span data-stu-id="face3-122">Manually undo an item application or reapply item ledger entries created by the program.</span></span>|[<span data-ttu-id="face3-123">Procédure : supprimer et affecter à nouveau des écritures article</span><span class="sxs-lookup"><span data-stu-id="face3-123">How to: Remove and Reapply Item Ledger Entries</span></span>](finance-how-to-remove-and-reapply-item-entries.md)|  
|<span data-ttu-id="face3-124">Utilisez le champ **Écriture affectée de** dans le journal article pour créer manuellement une affectation fixe entre une transaction entrante et la transaction sortante initiale.</span><span class="sxs-lookup"><span data-stu-id="face3-124">Use the **Applies-from Entry** field in the item journal to manually create a fixed application between an inbound transaction and the original outbound transaction.</span></span>|[<span data-ttu-id="face3-125">Procédure : clôturer les écritures comptables article ouvertes qui résultent d'un lettrage fixe dans la feuille article</span><span class="sxs-lookup"><span data-stu-id="face3-125">How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal</span></span>](finance-how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal.md)|  

## <a name="see-also"></a><span data-ttu-id="face3-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="face3-126">See Also</span></span>  
<span data-ttu-id="face3-127">[Gestion des coûts ajustés](finance-manage-inventory-costs.md)
[Détails de conception : Évaluation stock](design-details-inventory-costing.md)</span><span class="sxs-lookup"><span data-stu-id="face3-127">[Manage Inventory Costs](finance-manage-inventory-costs.md)
[Design Details: Inventory Costing](design-details-inventory-costing.md)</span></span>
