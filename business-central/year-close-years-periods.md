---
title: Fermer un exercice financier et des périodes comptables | Microsoft Docs
description: Décrit les tâches permettant de fermer un exercice financier ou une période comptable, par exemple, en vérifiant que les documents et les journaux sont reportés et en vérifiant les soldes bancaires.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: 3dba46a74fb5f0f6f13c4a6f0fa2c93f5d2ba372
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5773321"
---
# <a name="closing-years-and-periods"></a><span data-ttu-id="9fa8b-103">Fermeture des exercices et des périodes</span><span class="sxs-lookup"><span data-stu-id="9fa8b-103">Closing Years and Periods</span></span>

<span data-ttu-id="9fa8b-104">À la fin d'un exercice financier, vous devez exécuter un certain nombre de tâches administratives, par exemple vous assurer que tous les documents et journaux sont reportés, veiller que les données de devise sont à jour, que les registres sont fermés, etc.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-104">At the end of a fiscal year, there are a number of administrative tasks that you have to perform, like making sure all documents and journals are posted, making sure currency data are up-to-date, closing the books, and more.</span></span> <span data-ttu-id="9fa8b-105">Les tâches réelles dépendent de votre compagnie.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-105">The actual tasks will depend your company.</span></span>

<span data-ttu-id="9fa8b-106">Le tableau suivant fournit un aperçu des tâches que vous devez généralement exécuter pour fermer un exercice financier et une période comptable.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-106">The following table provides an overview of tasks that you typically perform to close a year and period.</span></span>

| <span data-ttu-id="9fa8b-107">À</span><span class="sxs-lookup"><span data-stu-id="9fa8b-107">To</span></span> | <span data-ttu-id="9fa8b-108">Voir</span><span class="sxs-lookup"><span data-stu-id="9fa8b-108">See</span></span> |
| --- | --- |
| <span data-ttu-id="9fa8b-109">Définissez votre exercice financier, et séparez-le en périodes dans lesquelles rapporter le résultat financier.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-109">Define your fiscal year, and divide it into time periods for which to report financial performance.</span></span> | [<span data-ttu-id="9fa8b-110">Utilisation des périodes comptables et exercices financiers</span><span class="sxs-lookup"><span data-stu-id="9fa8b-110">Working with Accounting Periods and Fiscal Years</span></span>](finance-accounting-periods-and-fiscal-years.md)|
| <span data-ttu-id="9fa8b-111">Spécifier des plages de dates de report à l'échelle du système et spécifiques à l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-111">Specify system-wide and user-specific posting date ranges.</span></span> <span data-ttu-id="9fa8b-112">En fonction des besoins de votre activité, vous pouvez restreindre les plages de dates de report utilisateur au début du traitement de fin d'exercice ou après ce dernier.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-112">Depending on your business needs, you may want to restrict user posting date ranges at the start of the period-end process or after it.</span></span> |[<span data-ttu-id="9fa8b-113">Spécifier des périodes de report</span><span class="sxs-lookup"><span data-stu-id="9fa8b-113">Specify Posting Periods</span></span>](finance-how-specify-posting-periods.md) |
| <span data-ttu-id="9fa8b-114">Obtenir un aperçu des activités qui sont généralement effectuées à la fin d'une période, telles que le report de tous les documents et tous les journaux, ou l'exécution de tableaux d'analyse.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-114">Get an overview of activities that are commonly performed at the end of a period, such as posting all documents and journals, or running account schedules.</span></span> |[<span data-ttu-id="9fa8b-115">Clôture périodes</span><span class="sxs-lookup"><span data-stu-id="9fa8b-115">Closing Periods</span></span>](year-how-complete-period-end-processes.md) |
| <span data-ttu-id="9fa8b-116">Mettre à jour les taux de change devise et ajuster les taux de change des écritures client, fournisseur et compte bancaire reportées.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-116">Update currency exchange rates and adjust the exchange rates of posted customer, vendor, and bank account entries.</span></span> |[<span data-ttu-id="9fa8b-117">Mettre à jour des taux de change devise</span><span class="sxs-lookup"><span data-stu-id="9fa8b-117">Update Currency Exchange Rates</span></span>](finance-how-update-currencies.md) |
| <span data-ttu-id="9fa8b-118">Ventiler des coûts et des bénéfices dans des comptes et des axes.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-118">Allocate costs and income among accounts and dimensions.</span></span> |[<span data-ttu-id="9fa8b-119">Répartition des coûts et du revenu</span><span class="sxs-lookup"><span data-stu-id="9fa8b-119">Allocating Costs and Income</span></span>](year-allocate-costs-income.md) |
| <span data-ttu-id="9fa8b-120">Préparer la déclaration des montants de taxe sur la valeur ajoutée obtenus par le biais des ventes à soumettre au site Web des autorités fiscales.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-120">Prepare to report value-added tax amounts that you have collected for sales to the tax authorities' web service.</span></span> |[<span data-ttu-id="9fa8b-121">Déclarer la TVA aux autorités fiscales</span><span class="sxs-lookup"><span data-stu-id="9fa8b-121">Report VAT to Tax Authorities</span></span>](finance-how-report-vat.md)|
| <span data-ttu-id="9fa8b-122">Imprimer des rapports pour vérifier les soldes des comptes GL, client, fournisseur et bancaires avant de fermer une période.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-122">Print reports to verify general ledger, customer, vendor and bank account balances before closing a period.</span></span> |[<span data-ttu-id="9fa8b-123">Préparation des états préalables à la clôture</span><span class="sxs-lookup"><span data-stu-id="9fa8b-123">Preparing Pre-Closing Reports</span></span>](year-prepare-preclose-reports.md) |
| <span data-ttu-id="9fa8b-124">Fermer les périodes comptables et l'exercice financier, transférer des soldes d'état des résultats sur des comptes de bilan et reporter l'écriture de fermeture de fin d'exercice.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-124">Close accounting periods and fiscal year, transfer income statement balances to balance sheet accounts and post the year end closing entry.</span></span> |[<span data-ttu-id="9fa8b-125">Clôture plans</span><span class="sxs-lookup"><span data-stu-id="9fa8b-125">Closing Books</span></span>](year-close-books.md) |
| <span data-ttu-id="9fa8b-126">Imprimer des états qui peuvent vous aider à créer des états financiers.</span><span class="sxs-lookup"><span data-stu-id="9fa8b-126">Print reports that can assist you in creating financial statements.</span></span> |[<span data-ttu-id="9fa8b-127">Préparation des états de clôture</span><span class="sxs-lookup"><span data-stu-id="9fa8b-127">Preparing Closing Statements</span></span>](year-prepare-close-statement.md) |

## <a name="see-related-training-at-microsoft-learn"></a><span data-ttu-id="9fa8b-128">Voir la formation associée sur [Microsoft Learn](/learn/modules/close-fiscal-year-dynamics-365-business-central/index)</span><span class="sxs-lookup"><span data-stu-id="9fa8b-128">See Related Training at [Microsoft Learn](/learn/modules/close-fiscal-year-dynamics-365-business-central/index)</span></span>

## <a name="see-also"></a><span data-ttu-id="9fa8b-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9fa8b-129">See Also</span></span>

[<span data-ttu-id="9fa8b-130">Utiliser des périodes et exercices financiers comptables</span><span class="sxs-lookup"><span data-stu-id="9fa8b-130">Work with Accounting Periods and Fiscal Years</span></span>](finance-accounting-periods-and-fiscal-years.md)  
<span data-ttu-id="9fa8b-131">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="9fa8b-131">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]