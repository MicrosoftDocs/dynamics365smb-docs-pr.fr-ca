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
ms.date: 04/01/2020
ms.author: jswymer
ms.openlocfilehash: 2c1836d133c36ba5a8bf44bae0443c252bc13d8e
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3191773"
---
# <a name="overview-of-tasks-to-close-accounting-periods"></a><span data-ttu-id="e8305-103">Aperçu des tâches de fermeture des périodes comptables</span><span class="sxs-lookup"><span data-stu-id="e8305-103">Overview of Tasks to Close Accounting Periods</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)] <span data-ttu-id="e8305-104">ne vous oblige pas à clôturer les périodes. Toutefois, il existe de nombreuses activités de clôture de période (fin de mois) que vous pouvez effectuer.</span><span class="sxs-lookup"><span data-stu-id="e8305-104">does not force you to close periods, however, there are many period-end (month-end) activities that you can do.</span></span> <span data-ttu-id="e8305-105">Cette rubrique présente un aperçu des activités et processus facultatifs pour la fermeture de périodes.</span><span class="sxs-lookup"><span data-stu-id="e8305-105">This topic provides an overview of optional processes and activities for closing periods.</span></span>  

## <a name="general-ledger"></a><span data-ttu-id="e8305-106">Écritures comptables</span><span class="sxs-lookup"><span data-stu-id="e8305-106">General Ledger</span></span>
* <span data-ttu-id="e8305-107">Spécifiez des périodes de report à l'échelle du système et spécifiques à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="e8305-107">Specify system-wide and user-specific posting periods.</span></span>  

    <span data-ttu-id="e8305-108">Cela spécifie les dates entre lesquelles les reports sont autorisés.</span><span class="sxs-lookup"><span data-stu-id="e8305-108">This specifies the dates between which you allow posting.</span></span> <span data-ttu-id="e8305-109">En fonction des besoins de votre activité, vous pouvez autoriser le report au début de la période ou vers la fin.</span><span class="sxs-lookup"><span data-stu-id="e8305-109">Depending on your business, you may want to allow posting at the start of the period, or toward the end.</span></span> <span data-ttu-id="e8305-110">Pour plus d'informations, reportez vous à [Spécifier des périodes de report](finance-how-specify-posting-periods.md).</span><span class="sxs-lookup"><span data-stu-id="e8305-110">For more information, see [Specify Posting Periods](finance-how-specify-posting-periods.md).</span></span>  
* <span data-ttu-id="e8305-111">Effectuez tous les ajustements nécessaires dans le GL.</span><span class="sxs-lookup"><span data-stu-id="e8305-111">Make all necessary G/L adjustments.</span></span>  
* <span data-ttu-id="e8305-112">Mettez à jour et reportez les journaux récurrents.</span><span class="sxs-lookup"><span data-stu-id="e8305-112">Update and post Recurring Journals.</span></span>  
  <!--* Process Consolidations-->
* <span data-ttu-id="e8305-113">Exécutez les tableaux d'analyse comme suit :</span><span class="sxs-lookup"><span data-stu-id="e8305-113">Run account schedules as follows:</span></span>  
  * <span data-ttu-id="e8305-114">Ouvrez la page **Tableau d'analyse**, puis sélectionnez l'action **Imprimer**.</span><span class="sxs-lookup"><span data-stu-id="e8305-114">Open the **Account Schedule** page, and then choose the **Print** action.</span></span>  

## <a name="sales-and-receivables"></a><span data-ttu-id="e8305-115">Ventes</span><span class="sxs-lookup"><span data-stu-id="e8305-115">Sales and Receivables</span></span>
* <span data-ttu-id="e8305-116">Reportez l'ensemble des documents de vente, factures, notes de crédit et retours vente.</span><span class="sxs-lookup"><span data-stu-id="e8305-116">Post all sales orders, invoices, credit memos, and return orders.</span></span>  
* <span data-ttu-id="e8305-117">Reportez l'ensemble des journaux des encaissements.</span><span class="sxs-lookup"><span data-stu-id="e8305-117">Post all cash receipt journals.</span></span>  
* <span data-ttu-id="e8305-118">Mettez à jour et reportez les journaux récurrents associés aux ventes.</span><span class="sxs-lookup"><span data-stu-id="e8305-118">Update and post recurring journals that are related to sales and receivables.</span></span>  
* <span data-ttu-id="e8305-119">Rapprocher les comptes clients avec le grand livre.</span><span class="sxs-lookup"><span data-stu-id="e8305-119">Reconcile accounts receivable to the general ledger.</span></span>  
* <span data-ttu-id="e8305-120">Exécutez le traitement par lots **Supprimer cdes vente facturées**.</span><span class="sxs-lookup"><span data-stu-id="e8305-120">Run the **Delete Invoiced Sales Orders** batch job.</span></span>  

## <a name="purchases-and-payables"></a><span data-ttu-id="e8305-121">Achats</span><span class="sxs-lookup"><span data-stu-id="e8305-121">Purchases and Payables</span></span>
* <span data-ttu-id="e8305-122">Reportez l'ensemble des bons de commande, factures, notes de crédit et retours achat.</span><span class="sxs-lookup"><span data-stu-id="e8305-122">Post all purchase orders, invoices, credit memos, and return orders.</span></span>  
* <span data-ttu-id="e8305-123">Reportez l'ensemble des journaux paiement.</span><span class="sxs-lookup"><span data-stu-id="e8305-123">Post all payment journals.</span></span>  
* <span data-ttu-id="e8305-124">Mettez à jour et validez les feuilles abonnement associées aux achats.</span><span class="sxs-lookup"><span data-stu-id="e8305-124">Update and post recurring journals that are related to purchases & payables.</span></span>  
* <span data-ttu-id="e8305-125">Générez l'état **Comptabilité fournisseur âgée** et rapprochez la comptabilité fournisseur de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="e8305-125">Run the **Aged Accounts Payable** report and reconcile accounts payable to the general ledger.</span></span>  
* <span data-ttu-id="e8305-126">Exécutez le traitement par lots **Supprimer cdes achat facturées**.</span><span class="sxs-lookup"><span data-stu-id="e8305-126">Run the **Delete Invoiced Purchase Orders** batch job.</span></span>  

<span data-ttu-id="e8305-127">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="e8305-127">Fixed Assets</span></span>
* <span data-ttu-id="e8305-128">Vérifiez que tous les frais d'entretien ont été reportés via les journaux immobilisation ou les factures.</span><span class="sxs-lookup"><span data-stu-id="e8305-128">Post all maintenance costs have been posted through the fixed asset journals or invoices.</span></span>
* <span data-ttu-id="e8305-129">Reportez les ajustements.</span><span class="sxs-lookup"><span data-stu-id="e8305-129">Post adjustments.</span></span>
* <span data-ttu-id="e8305-130">Reportez l'appréciation.</span><span class="sxs-lookup"><span data-stu-id="e8305-130">Post appreciation.</span></span>
* <span data-ttu-id="e8305-131">Reportez l'amortissement.</span><span class="sxs-lookup"><span data-stu-id="e8305-131">Post depreciation.</span></span>
* <span data-ttu-id="e8305-132">Mettez à jour et reportez le journal immobilisations récurrentes.</span><span class="sxs-lookup"><span data-stu-id="e8305-132">Update and post the recurring fixed asset journal.</span></span>

<span data-ttu-id="e8305-133">Intersociétés</span><span class="sxs-lookup"><span data-stu-id="e8305-133">Intercompany</span></span>
* <span data-ttu-id="e8305-134">Traitement des transactions intersociétés</span><span class="sxs-lookup"><span data-stu-id="e8305-134">Process Intercompany Transactions</span></span>

## <a name="calculate-and-process-sales-tax"></a><span data-ttu-id="e8305-135">Calculez et traitez la taxe de vente.</span><span class="sxs-lookup"><span data-stu-id="e8305-135">Calculate and Process Sales Tax</span></span>
* <span data-ttu-id="e8305-136">Renseignez les déclarations de TVA.</span><span class="sxs-lookup"><span data-stu-id="e8305-136">Complete Tax Statements.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e8305-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e8305-137">See Also</span></span>
[<span data-ttu-id="e8305-138">Clôture des exercices et des périodes</span><span class="sxs-lookup"><span data-stu-id="e8305-138">Closing Years and Periods</span></span>](year-close-years-periods.md)  
[<span data-ttu-id="e8305-139">Clôture plans</span><span class="sxs-lookup"><span data-stu-id="e8305-139">Closing Books</span></span>](year-close-books.md)  
<span data-ttu-id="e8305-140">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="e8305-140">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
