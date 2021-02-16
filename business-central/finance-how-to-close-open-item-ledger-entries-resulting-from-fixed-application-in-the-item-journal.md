---
title: Fermer des écritures article provenant de l’utilisation d’une affectation fixe
description: Découvrez comment vous pouvez créer une affectation fixe entre une transaction entrante et la transaction sortante initiale dans le journal article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 01/14/2020
ms.author: edupont
ms.openlocfilehash: 2cc663d580da4738247b9fcdbe5fc4504c37fa73
ms.sourcegitcommit: 311e86d6abb9b59a5483324d8bb4cd1be7949248
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/15/2021
ms.locfileid: "5013881"
---
# <a name="close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal"></a><span data-ttu-id="50710-103">Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article</span><span class="sxs-lookup"><span data-stu-id="50710-103">Close Open Item Ledger Entries Resulting from Fixed Application in the Item Journal</span></span>

<span data-ttu-id="50710-104">Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale.</span><span class="sxs-lookup"><span data-stu-id="50710-104">You can use the **Applies-from Entry** field on the **Item Journal** page to create a fixed application between an inbound transaction and the original outbound transaction.</span></span> <span data-ttu-id="50710-105">Par exemple, pour corriger la transaction sortante ou pour traiter un retour.</span><span class="sxs-lookup"><span data-stu-id="50710-105">For example, to correct the outbound transaction or to process its return.</span></span>  

> [!IMPORTANT]  
> <span data-ttu-id="50710-106">Les affectations fixes exécutées de cette manière s'appliquent uniquement au coût et non à la quantité.</span><span class="sxs-lookup"><span data-stu-id="50710-106">Fixed applications made in this manner only apply the cost, not the quantity.</span></span> <span data-ttu-id="50710-107">Par conséquent, l'écriture du grand livre d'articles positive reportée ne ferme pas l'écriture sortante affectée et demeure ouverte elle-même.</span><span class="sxs-lookup"><span data-stu-id="50710-107">Accordingly, the posted positive item ledger entry will not close the applied outbound entry and will itself remain open.</span></span> <span data-ttu-id="50710-108">Cela s'applique également lorsque vous reportez une affectation fixe pour une écriture positive vers une écriture négative qui n'a pas été fermée par une écriture positive ordinaire ; les écritures négatives et positives restent ouvertes.</span><span class="sxs-lookup"><span data-stu-id="50710-108">This also applies when you post a fixed application for a positive entry to a negative entry that has not been closed by a regular positive entry, then both the negative and the positive entries will remain open.</span></span>  
>
> <span data-ttu-id="50710-109">Cela signifie également que vous ne pouvez pas fermer une période d'inventaire si une telle écriture existe.</span><span class="sxs-lookup"><span data-stu-id="50710-109">This also means that you cannot close an inventory period if such an entry exists.</span></span>  

<span data-ttu-id="50710-110">Vous pouvez modifier et affecter à nouveau des écritures d'affectation dans certaines conditions à l’aide de la page **Feuille affectation**.</span><span class="sxs-lookup"><span data-stu-id="50710-110">You can change and reapply application entries under certain conditions by using the **Application Worksheet** page.</span></span>  

<span data-ttu-id="50710-111">La procédure suivante explique comment fermer des écritures de ce genre au cours de deux reports de correction dans le journal article.</span><span class="sxs-lookup"><span data-stu-id="50710-111">The following procedure shows how to close such entries by performing two corrective postings in the item journal.</span></span>  

## <a name="to-close-open-item-ledger-entries-that-result-from-a-fixed-application-in-the-item-journal"></a><span data-ttu-id="50710-112">Pour fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal d'articles</span><span class="sxs-lookup"><span data-stu-id="50710-112">To close open item ledger entries that result from a fixed application in the item journal</span></span>  

1. <span data-ttu-id="50710-113">Utilisez le champ **Écriture affectée de** pour reporter un ajustement positif avec la quantité correspondante.</span><span class="sxs-lookup"><span data-stu-id="50710-113">Use the **Applies-from Entry** field to post a positive adjustment with the corresponding quantity.</span></span> <span data-ttu-id="50710-114">Cela permet de fermer l'écriture négative initiale par une affectation fixe.</span><span class="sxs-lookup"><span data-stu-id="50710-114">This closes the original negative entry with a fixed application.</span></span>  

    <span data-ttu-id="50710-115">Le champ **Écriture référence** spécifie le numéro de l’écriture article sortant dont le coût est transmis à l’écriture article entrant lorsque vous reportez une transaction entrante de type **Ajustement positif** ou **Achat** avec le journal article.</span><span class="sxs-lookup"><span data-stu-id="50710-115">The **Applies-from Entry** field specifies the number of the outbound item ledger entry whose cost is forwarded to the inbound item ledger entry when you post an inbound transaction of type **Positive Adjmt.** or **Purchase** with the item journal.</span></span>  
2. <span data-ttu-id="50710-116">Utilisez le champ **Écriture affectée à** pour reporter un ajustement négatif.</span><span class="sxs-lookup"><span data-stu-id="50710-116">Use the **Applies-to Entry** field to post a negative adjustment.</span></span> <span data-ttu-id="50710-117">Cela permet de fermer l'écriture positive de correction initiale par une affectation fixe.</span><span class="sxs-lookup"><span data-stu-id="50710-117">This closes the original corrective positive entry with a fixed application.</span></span>  

    <span data-ttu-id="50710-118">Le champ **Écriture référence** spécifie si la quantité dans la ligne journal article doit être affectée à un document déjà reporté.</span><span class="sxs-lookup"><span data-stu-id="50710-118">The **Applies-to Entry** field specifies if the quantity in the item journal line should be applied to an already-posted document.</span></span> <span data-ttu-id="50710-119">Si c’est le cas, entrez le numéro de l’écriture article à laquelle la ligne journal article doit être affectée.</span><span class="sxs-lookup"><span data-stu-id="50710-119">If this is the case, enter the entry number of the item ledger entry to which the item journal line should be applied.</span></span>

## <a name="see-also"></a><span data-ttu-id="50710-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="50710-120">See Also</span></span>

[<span data-ttu-id="50710-121">Supprimer et appliquer à nouveau des écritures article</span><span class="sxs-lookup"><span data-stu-id="50710-121">Remove and Reapply Item Ledger Entries</span></span>](finance-how-to-remove-and-reapply-item-entries.md)  
[<span data-ttu-id="50710-122">Traiter les retours et annulations de ventes</span><span class="sxs-lookup"><span data-stu-id="50710-122">Process Sales Returns and Cancellations</span></span>](sales-how-process-sales-returns-cancellations.md)  
[<span data-ttu-id="50710-123">Configuration de l'évaluation de l'inventaire et des coûts</span><span class="sxs-lookup"><span data-stu-id="50710-123">Setting Up Inventory Valuation and Costing</span></span>](finance-set-up-inventory-valuation-and-costing.md)  
[<span data-ttu-id="50710-124">Gestion des coûts ajustés</span><span class="sxs-lookup"><span data-stu-id="50710-124">Managing Inventory Costs</span></span>](finance-manage-inventory-costs.md)  
[<span data-ttu-id="50710-125">Détails de conception : modes évaluation stock</span><span class="sxs-lookup"><span data-stu-id="50710-125">Design Details: Costing Methods</span></span>](design-details-costing-methods.md)
