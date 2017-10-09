---
title: "Transfert automatique et écritures combinées | Microsoft Docs"
description: "En comptabilité analytique, vous pouvez transférer les écritures vers un type de coût à l'aide d'un report combiné. Vous pouvez spécifier si un type de coût reçoit des écritures combinées dans le champ **Combiner écritures** dans la définition du type de coût. Le tableau suivant décrit les différentes options."
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
ms.openlocfilehash: bd80d0a7a701256dfdae3346e899b84eeb990a40
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="automatic-transfer-and-combined-entries"></a><span data-ttu-id="16fa6-105">Transfert automatique et écritures combinées</span><span class="sxs-lookup"><span data-stu-id="16fa6-105">Automatic Transfer and Combined Entries</span></span>
<span data-ttu-id="16fa6-106">En comptabilité analytique, vous pouvez transférer les écritures vers un type de coût à l'aide d'un report combiné.</span><span class="sxs-lookup"><span data-stu-id="16fa6-106">In cost accounting, you can transfer general ledger entries to a cost type by using a combined posting.</span></span> <span data-ttu-id="16fa6-107">Vous pouvez spécifier si un type de coût reçoit des écritures combinées dans le champ **Combiner écritures** dans la définition du type de coût.</span><span class="sxs-lookup"><span data-stu-id="16fa6-107">You can specify if a cost type receives combined entries in the **Combine Entries** field in the cost type definition.</span></span> <span data-ttu-id="16fa6-108">Le tableau suivant décrit les différentes options.</span><span class="sxs-lookup"><span data-stu-id="16fa6-108">The following table describes the different options.</span></span>  

|<span data-ttu-id="16fa6-109">Combiner des écritures</span><span class="sxs-lookup"><span data-stu-id="16fa6-109">Combine entries</span></span>|<span data-ttu-id="16fa6-110">Description</span><span class="sxs-lookup"><span data-stu-id="16fa6-110">Description</span></span>|  
|---------------------|-----------------|  
|<span data-ttu-id="16fa6-111">Aucun</span><span class="sxs-lookup"><span data-stu-id="16fa6-111">None</span></span>|<span data-ttu-id="16fa6-112">Chaque écriture est transférée individuellement vers le type de coût correspondant.</span><span class="sxs-lookup"><span data-stu-id="16fa6-112">Each general ledger entry is transferred individually to the corresponding cost type.</span></span>|  
|<span data-ttu-id="16fa6-113">Jour</span><span class="sxs-lookup"><span data-stu-id="16fa6-113">Day</span></span>|<span data-ttu-id="16fa6-114">Les écritures, dont la date de report est identique, sont transférées en une seule écriture vers le type de coût correspondant.</span><span class="sxs-lookup"><span data-stu-id="16fa6-114">General ledger entries with the same posting date are transferred as one entry to the corresponding cost type.</span></span>|  
|<span data-ttu-id="16fa6-115">Mois</span><span class="sxs-lookup"><span data-stu-id="16fa6-115">Month</span></span>|<span data-ttu-id="16fa6-116">Toutes les écritures du même mois calendaire sont transférées en une seul écriture vers le type de coût correspondant.</span><span class="sxs-lookup"><span data-stu-id="16fa6-116">All general ledger entries in the same calendar month are transferred as one entry to the corresponding cost type.</span></span>|  

> [!IMPORTANT]  
>  <span data-ttu-id="16fa6-117">Si vous avez coché la case **Transférer automatiquement à partir du GL** dans la fenêtre **Configuration de la comptabilité analytique**, [!INCLUDE[d365fin](includes/d365fin_md.md)] met à jour la comptabilité analytique après chaque report dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="16fa6-117">If you have selected the **Auto Transfer from G/L** check box in the **Cost Accounting Setup** window, [!INCLUDE[d365fin](includes/d365fin_md.md)] updates the cost accounting after every posting in the general ledger.</span></span> <span data-ttu-id="16fa6-118">Les écritures combinées ne sont pas possibles.</span><span class="sxs-lookup"><span data-stu-id="16fa6-118">Combined entries are not possible.</span></span>  

## <a name="see-also"></a><span data-ttu-id="16fa6-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16fa6-119">See Also</span></span>  
 <span data-ttu-id="16fa6-120">[Comment transférer les écritures comptables vers les écritures de coûts](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="16fa6-120">[How to: Transfer General Ledger Entries to Cost Entries](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span></span>  
 <span data-ttu-id="16fa6-121">[Critères de transfert des écritures comptables vers les écritures de coûts](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="16fa6-121">[Criteria for Transferring General Ledger Entries to Cost Entries](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span></span>  
 <span data-ttu-id="16fa6-122">[Résultats du transfert](finance-results-of-the-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="16fa6-122">[Results of the Transfer](finance-results-of-the-transfer.md) </span></span>  
 [<span data-ttu-id="16fa6-123">Transfert et report des écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="16fa6-123">Transferring and Posting Cost Entries</span></span>](finance-transfer-and-post-cost-entries.md)  
 <span data-ttu-id="16fa6-124">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="16fa6-124">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

