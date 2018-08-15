---
title: "Critères de transfert des écritures GL vers les écritures de coûts | Microsoft Docs"
description: "Il est important de comprendre les critères pour le transfert des écritures aux écritures de coûts. Lors du transfert, le traitement par lots pour **Transférer les écritures comptables vers CA** applique les critères suivants pour déterminer si les écritures comptables sont transférées et comment."
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
ms.openlocfilehash: b1ac9d3d0ab7022d5a11ad1642cf496d07bc81ce
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="criteria-for-transferring-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="f8212-104">Critères de transfert des écritures vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="f8212-104">Criteria for Transferring General Ledger Entries to Cost Entries</span></span>
<span data-ttu-id="f8212-105">Il est important de comprendre les critères pour le transfert des écritures aux écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="f8212-105">It is important to understand the criteria for transferring general ledger entries to cost entries.</span></span> <span data-ttu-id="f8212-106">Lors du transfert, le traitement par lots pour **Transférer les écritures comptables vers CA** applique les critères suivants pour déterminer si les écritures comptables sont transférées et comment.</span><span class="sxs-lookup"><span data-stu-id="f8212-106">During the transfer, the **Transfer GL Entries to CA** batch job uses the following criteria to determine if and how the general ledger entries are transferred.</span></span>  

<span data-ttu-id="f8212-107">Les écritures sont transférées si :</span><span class="sxs-lookup"><span data-stu-id="f8212-107">General ledger entries are transferred if:</span></span>  

-   <span data-ttu-id="f8212-108">Les écritures ont des valeurs de dimension correspondant à un centre de coûts ou à un objet de coûts.</span><span class="sxs-lookup"><span data-stu-id="f8212-108">The entries have dimension values corresponding to either a cost center or a cost object.</span></span>  
-   <span data-ttu-id="f8212-109">Les écritures ont des valeurs de dimension correspondant à un centre de coûts et à un objet de coûts.</span><span class="sxs-lookup"><span data-stu-id="f8212-109">The entries have dimension values that correspond to a cost center and a cost object.</span></span> <span data-ttu-id="f8212-110">Pour ces écritures, le centre de coûts est prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f8212-110">For these entries, the cost center takes precedence.</span></span> <span data-ttu-id="f8212-111">Vous pouvez ainsi éviter qu'un type de coût apparaisse à la fois dans un objet de coûts et dans un centre de coûts, ce qui le comptabiliserait deux fois dans les statistiques.</span><span class="sxs-lookup"><span data-stu-id="f8212-111">This helps avoid a situation where a cost type appears in both a cost object and a cost center and is therefore counted twice in the statistics.</span></span>  
-   <span data-ttu-id="f8212-112">Le numéro de document dans les écritures est vide. C'est pourquoi, il s'affichera avec le numéro de document 0000 dans les écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="f8212-112">The document number in the entries is empty, so it will appear with a document number of 0000 in the cost entries.</span></span>  
-   <span data-ttu-id="f8212-113">Les écritures sont transférées vers un type de coût qui autorise les écritures combinées. Ces écritures sont transférées ainsi sur une base mensuelle ou journalière.</span><span class="sxs-lookup"><span data-stu-id="f8212-113">The entries are transferred to a cost type that allows for combined entries and these entries are transferred as a combined entry either monthly or daily.</span></span>  

<span data-ttu-id="f8212-114">Les écritures ne sont pas transférées si :</span><span class="sxs-lookup"><span data-stu-id="f8212-114">General ledger entries are not transferred if:</span></span>  

-   <span data-ttu-id="f8212-115">Les écritures ont des valeurs de dimension ne correspondant ni à un centre de coûts ni à un objet de coûts.</span><span class="sxs-lookup"><span data-stu-id="f8212-115">The entries have dimension values that do not correspond to a cost center or a cost object.</span></span>  
-   <span data-ttu-id="f8212-116">Les écritures sont égales à zéro.</span><span class="sxs-lookup"><span data-stu-id="f8212-116">The entries have an amount of zero.</span></span>  
-   <span data-ttu-id="f8212-117">Les écritures ont un compte du grand livre qui a été supprimé.</span><span class="sxs-lookup"><span data-stu-id="f8212-117">The entries have a general ledger account that has been deleted.</span></span>  
-   <span data-ttu-id="f8212-118">Les écritures ont un compte général qui n'est pas du type **Comptes de gestion**.</span><span class="sxs-lookup"><span data-stu-id="f8212-118">The entries have a general ledger account that is not of the type **Income Statement**.</span></span>  
-   <span data-ttu-id="f8212-119">Les écritures ont un compte du grand livre sans type de coût affecté.</span><span class="sxs-lookup"><span data-stu-id="f8212-119">The entries have a general ledger account that is not assigned a cost type.</span></span>  
-   <span data-ttu-id="f8212-120">La date de report des écritures est antérieure à la **Date début pour transfert grand livre**.</span><span class="sxs-lookup"><span data-stu-id="f8212-120">The entries have a posting date before the **Starting Date for G/L Transfer**.</span></span>  
-   <span data-ttu-id="f8212-121">Les écritures ont été reportées avec une date de fermeture.</span><span class="sxs-lookup"><span data-stu-id="f8212-121">The entries have been posted with a closing date.</span></span> <span data-ttu-id="f8212-122">Il s'agit généralement des écritures qui redéfinissent le solde des états des résultats sur la fin de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="f8212-122">These are typically entries that set back the balance of the income statement at the end of the year.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f8212-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f8212-123">See Also</span></span>  
[<span data-ttu-id="f8212-124">Comptabilité pour les coûts</span><span class="sxs-lookup"><span data-stu-id="f8212-124">Accounting for Costs</span></span>](finance-manage-cost-accounting.md)  
 <span data-ttu-id="f8212-125">[Transférer les écritures grand livre vers les écritures de coûts](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="f8212-125">[Transfer General Ledger Entries to Cost Entries](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span></span>  
 <span data-ttu-id="f8212-126">[Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="f8212-126">[Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md) </span></span>  
 [<span data-ttu-id="f8212-127">À propos de la comptabilité analytique</span><span class="sxs-lookup"><span data-stu-id="f8212-127">About Cost Accounting</span></span>](finance-about-cost-accounting.md)  
 <span data-ttu-id="f8212-128">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f8212-128">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
