---
title: Activités facultatives pour les périodes de fermeture | Microsoft Docs
description: Cette rubrique décrit les processus et activités facultatifs pour la fermeture des périodes comptables dans Business Central.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, aging, creditor payments, vendor payments
ms.date: 04/01/2019
ms.author: jswymer
ms.openlocfilehash: cbbfb06052f8286822f4ab722d00706de303dc02
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1248709"
---
# <a name="overview-of-tasks-to-close-accounting-periods"></a><span data-ttu-id="171a6-103">Aperçu des tâches de fermeture des périodes comptables</span><span class="sxs-lookup"><span data-stu-id="171a6-103">Overview of Tasks to Close Accounting Periods</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="171a6-104">ne vous oblige pas à clôturer les périodes. Toutefois, il existe de nombreuses activités de clôture de période (fin de mois) que vous pouvez effectuer.</span><span class="sxs-lookup"><span data-stu-id="171a6-104">does not force you to close periods, however, there are many period-end (month-end) activities that you can do.</span></span> <span data-ttu-id="171a6-105">Cette rubrique présente un aperçu des activités et processus facultatifs pour la fermeture de périodes.</span><span class="sxs-lookup"><span data-stu-id="171a6-105">This topic provides an overview of optional processes and activities for closing periods.</span></span>  

## <a name="general-ledger"></a><span data-ttu-id="171a6-106">Écritures comptables</span><span class="sxs-lookup"><span data-stu-id="171a6-106">General Ledger</span></span>
* <span data-ttu-id="171a6-107">Spécifiez des périodes de report à l'échelle du système et spécifiques à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="171a6-107">Specify system-wide and user-specific posting periods.</span></span>  

    <span data-ttu-id="171a6-108">Cela spécifie les dates entre lesquelles les reports sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="171a6-108">This specifies the dates between which you allow posting.</span></span> <span data-ttu-id="171a6-109">En fonction des besoins de votre activité, vous pouvez autoriser le report au début de la période ou vers la fin.</span><span class="sxs-lookup"><span data-stu-id="171a6-109">Depending on your business, you may want to allow posting at the start of the period, or toward the end.</span></span> <span data-ttu-id="171a6-110">Pour plus d'informations, reportez vous à [Spécifier des périodes de report](finance-how-specify-posting-periods.md).</span><span class="sxs-lookup"><span data-stu-id="171a6-110">For more information, see [Specify Posting Periods](finance-how-specify-posting-periods.md).</span></span>  
* <span data-ttu-id="171a6-111">Effectuez tous les ajustements nécessaires dans le GL.</span><span class="sxs-lookup"><span data-stu-id="171a6-111">Make all necessary G/L adjustments.</span></span>  
* <span data-ttu-id="171a6-112">Mettez à jour et reportez les journaux récurrents.</span><span class="sxs-lookup"><span data-stu-id="171a6-112">Update and post Recurring Journals.</span></span>  
  <!--* Process Consolidations-->
* <span data-ttu-id="171a6-113">Exécutez les tableaux d'analyse comme suit :</span><span class="sxs-lookup"><span data-stu-id="171a6-113">Run account schedules as follows:</span></span>  
  * <span data-ttu-id="171a6-114">Ouvrez la page **Tableau d'analyse**, puis sélectionnez l'action **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="171a6-114">Open the **Account Schedule** page, and then choose the **Print** action.</span></span>  

## <a name="sales-and-receivables"></a><span data-ttu-id="171a6-115">Ventes</span><span class="sxs-lookup"><span data-stu-id="171a6-115">Sales and Receivables</span></span>
* <span data-ttu-id="171a6-116">Reportez l'ensemble des documents de vente, factures, notes de crédit et retours vente.</span><span class="sxs-lookup"><span data-stu-id="171a6-116">Post all sales orders, invoices, credit memos, and return orders.</span></span>  
* <span data-ttu-id="171a6-117">Reportez l'ensemble des journaux des encaissements.</span><span class="sxs-lookup"><span data-stu-id="171a6-117">Post all cash receipt journals.</span></span>  
* <span data-ttu-id="171a6-118">Mettez à jour et reportez les journaux récurrents associés aux ventes.</span><span class="sxs-lookup"><span data-stu-id="171a6-118">Update and post recurring journals that are related to sales and receivables.</span></span>  
* <span data-ttu-id="171a6-119">Rapprocher les comptes clients avec le grand livre.</span><span class="sxs-lookup"><span data-stu-id="171a6-119">Reconcile accounts receivable to the general ledger.</span></span>  
* <span data-ttu-id="171a6-120">Exécutez le traitement par lots **Supprimer cdes vente facturées**.</span><span class="sxs-lookup"><span data-stu-id="171a6-120">Run the **Delete Invoiced Sales Orders** batch job.</span></span>  

## <a name="purchases-and-payables"></a><span data-ttu-id="171a6-121">Achats</span><span class="sxs-lookup"><span data-stu-id="171a6-121">Purchases and Payables</span></span>
* <span data-ttu-id="171a6-122">Reportez l'ensemble des bons de commande, factures, notes de crédit et retours achat.</span><span class="sxs-lookup"><span data-stu-id="171a6-122">Post all purchase orders, invoices, credit memos, and return orders.</span></span>  
* <span data-ttu-id="171a6-123">Reportez l'ensemble des journaux paiement.</span><span class="sxs-lookup"><span data-stu-id="171a6-123">Post all payment journals.</span></span>  
* <span data-ttu-id="171a6-124">Mettez à jour et validez les feuilles abonnement associées aux achats.</span><span class="sxs-lookup"><span data-stu-id="171a6-124">Update and post recurring journals that are related to purchases & payables.</span></span>  
* <span data-ttu-id="171a6-125">Générez l'état **Comptabilité fournisseur âgée** et rapprochez la comptabilité fournisseur de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="171a6-125">Run the **Aged Accounts Payable** report and reconcile accounts payable to the general ledger.</span></span>  
* <span data-ttu-id="171a6-126">Exécutez le traitement par lots **Supprimer cdes achat facturées**.</span><span class="sxs-lookup"><span data-stu-id="171a6-126">Run the **Delete Invoiced Purchase Orders** batch job.</span></span>  

<span data-ttu-id="171a6-127">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="171a6-127">Fixed Assets</span></span>
* <span data-ttu-id="171a6-128">Vérifiez que tous les frais d'entretien ont été reportés via les journaux immobilisation ou les factures.</span><span class="sxs-lookup"><span data-stu-id="171a6-128">Post all maintenance costs have been posted through the fixed asset journals or invoices.</span></span>
* <span data-ttu-id="171a6-129">Reportez les ajustements.</span><span class="sxs-lookup"><span data-stu-id="171a6-129">Post adjustments.</span></span>
* <span data-ttu-id="171a6-130">Reportez l'appréciation.</span><span class="sxs-lookup"><span data-stu-id="171a6-130">Post appreciation.</span></span>
* <span data-ttu-id="171a6-131">Reportez l'amortissement.</span><span class="sxs-lookup"><span data-stu-id="171a6-131">Post depreciation.</span></span>
* <span data-ttu-id="171a6-132">Mettez à jour et reportez le journal immobilisations récurrentes.</span><span class="sxs-lookup"><span data-stu-id="171a6-132">Update and post the recurring fixed asset journal.</span></span>

<span data-ttu-id="171a6-133">Intersociétés</span><span class="sxs-lookup"><span data-stu-id="171a6-133">Intercompany</span></span>
* <span data-ttu-id="171a6-134">Traitement des transactions intersociétés</span><span class="sxs-lookup"><span data-stu-id="171a6-134">Process Intercompany Transactions</span></span>

## <a name="calculate-and-process-sales-tax"></a><span data-ttu-id="171a6-135">Calculez et traitez la taxe de vente.</span><span class="sxs-lookup"><span data-stu-id="171a6-135">Calculate and Process Sales Tax</span></span>
* <span data-ttu-id="171a6-136">Renseignez les déclarations de TVA.</span><span class="sxs-lookup"><span data-stu-id="171a6-136">Complete Tax Statements.</span></span>  

## <a name="see-also"></a><span data-ttu-id="171a6-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="171a6-137">See Also</span></span>
[<span data-ttu-id="171a6-138">Clôture des exercices et des périodes</span><span class="sxs-lookup"><span data-stu-id="171a6-138">Closing Years and Periods</span></span>](year-close-years-periods.md)  
[<span data-ttu-id="171a6-139">Clôture plans</span><span class="sxs-lookup"><span data-stu-id="171a6-139">Closing Books</span></span>](year-close-books.md)  
<span data-ttu-id="171a6-140">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="171a6-140">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
