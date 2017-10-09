---
title: "Procédure : fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article | Microsoft Docs"
description: "Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale. Par exemple, pour corriger la transaction sortante ou pour traiter un retour."
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
ms.openlocfilehash: d30a1316b48bd1b80ab4658ee99b14f0a0217478
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal"></a><span data-ttu-id="fb038-104">Procédure : fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal d'articles</span><span class="sxs-lookup"><span data-stu-id="fb038-104">How to: Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal</span></span>
<span data-ttu-id="fb038-105">Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale.</span><span class="sxs-lookup"><span data-stu-id="fb038-105">You can use the **Applies-from Entry** field in the **Item Journal** window to create a fixed application between an inbound transaction and the original outbound transaction.</span></span> <span data-ttu-id="fb038-106">Par exemple, pour corriger la transaction sortante ou pour traiter un retour.</span><span class="sxs-lookup"><span data-stu-id="fb038-106">For example, to correct the outbound transaction or to process its return.</span></span> <span data-ttu-id="fb038-107">Pour plus d'informations, voir Lettrage à partir écriture.</span><span class="sxs-lookup"><span data-stu-id="fb038-107">For more information, see Applies-from Entry.</span></span>  

> [!IMPORTANT]  
>  <span data-ttu-id="fb038-108">Les affectations fixes exécutées de cette manière s'appliquent uniquement au coût et non à la quantité.</span><span class="sxs-lookup"><span data-stu-id="fb038-108">Fixed applications made in this manner only apply the cost, not the quantity.</span></span> <span data-ttu-id="fb038-109">Par conséquent, l'écriture du grand livre d'articles positive reportée ne ferme pas l'écriture sortante affectée et demeure ouverte elle-même.</span><span class="sxs-lookup"><span data-stu-id="fb038-109">Accordingly, the posted positive item ledger entry will not close the applied outbound entry and will itself remain open.</span></span> <span data-ttu-id="fb038-110">Cela s'applique également lorsque vous reportez une affectation fixe pour une écriture positive vers une écriture négative qui n'a pas été fermée par une écriture positive ordinaire ; les écritures négatives et positives restent ouvertes.</span><span class="sxs-lookup"><span data-stu-id="fb038-110">This also applies when you post a fixed application for a positive entry to a negative entry that has not been closed by a regular positive entry, then both the negative and the positive entries will remain open.</span></span>  
>   
>  <span data-ttu-id="fb038-111">Cela signifie également que vous ne pouvez pas fermer une période d'inventaire si une telle écriture existe.</span><span class="sxs-lookup"><span data-stu-id="fb038-111">This also means that you cannot close an inventory period if such an entry exists.</span></span>  

<span data-ttu-id="fb038-112">La procédure suivante explique comment fermer des écritures de ce genre au cours de deux reports de correction dans le journal article.</span><span class="sxs-lookup"><span data-stu-id="fb038-112">The following procedure shows how to close such entries by performing two corrective postings in the item journal.</span></span>  

## <a name="to-close-open-item-ledger-entries-that-result-from-a-fixed-application-in-the-item-journal"></a><span data-ttu-id="fb038-113">Pour fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal d'articles</span><span class="sxs-lookup"><span data-stu-id="fb038-113">To close open item ledger entries that result from a fixed application in the item journal</span></span>  

1.  <span data-ttu-id="fb038-114">Utilisez le champ **Écriture affectée de** pour reporter un ajustement positif avec la quantité correspondante.</span><span class="sxs-lookup"><span data-stu-id="fb038-114">Use the **Applies-from Entry** field to post a positive adjustment with the corresponding quantity.</span></span> <span data-ttu-id="fb038-115">Cela permet de fermer l'écriture négative initiale par une affectation fixe.</span><span class="sxs-lookup"><span data-stu-id="fb038-115">This closes the original negative entry with a fixed application.</span></span>  
2.  <span data-ttu-id="fb038-116">Utilisez le champ **Écriture affectée à** pour reporter un ajustement négatif.</span><span class="sxs-lookup"><span data-stu-id="fb038-116">Use the **Applies-to Entry** field to post a negative adjustment.</span></span> <span data-ttu-id="fb038-117">Cela permet de fermer l'écriture positive de correction initiale par une affectation fixe.</span><span class="sxs-lookup"><span data-stu-id="fb038-117">This closes the original corrective positive entry with a fixed application.</span></span>  

## <a name="see-also"></a><span data-ttu-id="fb038-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb038-118">See Also</span></span>  
[<span data-ttu-id="fb038-119"> Procédure : supprimer et affecter à nouveau des écritures article</span><span class="sxs-lookup"><span data-stu-id="fb038-119"> How to: Remove and Reapply Item Ledger Entries</span></span>](finance-how-to-remove-and-reapply-item-entries.md)  
 <span data-ttu-id="fb038-120">[Procédure : traiter les retours et annulations de ventes](sales-how-process-sales-returns-cancellations.md) </span><span class="sxs-lookup"><span data-stu-id="fb038-120">[How to: Process Sales Returns and Cancellations](sales-how-process-sales-returns-cancellations.md) </span></span>  
 <span data-ttu-id="fb038-121">[Configuration de l'évaluation de l'inventaire et des coûts](finance-set-up-inventory-valuation-and-costing.md) </span><span class="sxs-lookup"><span data-stu-id="fb038-121">[Setting Up Inventory Valuation and Costing](finance-set-up-inventory-valuation-and-costing.md) </span></span>  
 <span data-ttu-id="fb038-122">[Gestion des coûts ajustés](finance-manage-inventory-costs.md) </span><span class="sxs-lookup"><span data-stu-id="fb038-122">[Managing Inventory Costs](finance-manage-inventory-costs.md) </span></span>  
 [<span data-ttu-id="fb038-123">Détails de conception : modes évaluation stock</span><span class="sxs-lookup"><span data-stu-id="fb038-123">Design Details: Costing Methods</span></span>](design-details-costing-methods.md)

