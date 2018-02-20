---
title: Configurer les processus financiers| Microsoft Docs
description: "En savoir plus sur les tâches pour paramétrer les finances de votre société afin de les adapter à votre comptabilité ou vos audits."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: accounting, auditing, bookkeeping
ms.date: 08/10/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: b34f276a764f0e828fbc1f015429df9852242a4c
ms.openlocfilehash: dafd94118c145e0435c1715e6677b206ec659fb0
ms.contentlocale: fr-ca
ms.lasthandoff: 02/02/2018

---
# <a name="setting-up-finance"></a><span data-ttu-id="038ac-103">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="038ac-103">Setting Up Finance</span></span>
<span data-ttu-id="038ac-104">Pour vous aider à démarrer rapidement, [!INCLUDE[d365fin](includes/d365fin_md.md)] inclut des configurations standard pour la plupart des processus financiers.</span><span class="sxs-lookup"><span data-stu-id="038ac-104">To help you get going quickly, [!INCLUDE[d365fin](includes/d365fin_md.md)] includes standard configurations for most financial processes.</span></span> <span data-ttu-id="038ac-105">Si vous devez modifier les configurations en fonction de votre activité, n'hésitez pas.</span><span class="sxs-lookup"><span data-stu-id="038ac-105">If you need to change the configurations to suit your business, go right ahead.</span></span> <span data-ttu-id="038ac-106">Par exemple, à partir de la page d'accueil, vous pouvez utiliser un guide de configuration assistée pour configurer la taxe de vente en fonction de votre situation géographique.</span><span class="sxs-lookup"><span data-stu-id="038ac-106">For example, from the Home page you can use an assisted setup guide to set up sales tax rate for your location.</span></span>  

<span data-ttu-id="038ac-107">Toutefois, il existe quelques éléments que vous devez configurer vous-même.</span><span class="sxs-lookup"><span data-stu-id="038ac-107">However, there are some things you need to set up yourself.</span></span> <span data-ttu-id="038ac-108">Par exemple, si vous souhaitez utiliser les axes analytiques comme base pour la veille économique.</span><span class="sxs-lookup"><span data-stu-id="038ac-108">For example, if you want to use dimensions as a basis for business intelligence.</span></span>  

<span data-ttu-id="038ac-109">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="038ac-109">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>

| <span data-ttu-id="038ac-110">À</span><span class="sxs-lookup"><span data-stu-id="038ac-110">To</span></span> | <span data-ttu-id="038ac-111">Voir</span><span class="sxs-lookup"><span data-stu-id="038ac-111">See</span></span> |
| --- | --- |
| <span data-ttu-id="038ac-112">Choisissez la méthode pour payer vos fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="038ac-112">Choose how you pay your vendors.</span></span> |[<span data-ttu-id="038ac-113">Définition des modes de règlement</span><span class="sxs-lookup"><span data-stu-id="038ac-113">Defining Payment Methods</span></span>](finance-payment-methods.md) |
| <span data-ttu-id="038ac-114">Spécifiez les groupes comptabilisation qui mappent des entités telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat dans des comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="038ac-114">Specify the posting groups that map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts.</span></span> |[<span data-ttu-id="038ac-115">Configuration de groupes comptabilisation</span><span class="sxs-lookup"><span data-stu-id="038ac-115">Setting Up Posting Groups</span></span>](finance-posting-groups.md)|
|<span data-ttu-id="038ac-116">Configurer une valeur de tolérance selon laquelle le système ferme une facture même si le paiement, tenant compte d'éventuels escomptes, ne couvre pas intégralement le montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="038ac-116">Set up a tolerance by which the system closes an invoice even though the payment, including any discount, does not fully cover the amount on the invoice.</span></span>|[<span data-ttu-id="038ac-117">Utilisation des tolérances de règlement et des tolérances d'escompte de paiement</span><span class="sxs-lookup"><span data-stu-id="038ac-117">Work with Payment Tolerances and Payment Discount Tolerances</span></span>](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| <span data-ttu-id="038ac-118">Définir les périodes fiscales.</span><span class="sxs-lookup"><span data-stu-id="038ac-118">Set up fiscal periods.</span></span> |[<span data-ttu-id="038ac-119">Ouvrir un nouvel exercice financier</span><span class="sxs-lookup"><span data-stu-id="038ac-119">Open a New Fiscal Year</span></span>](finance-how-open-new-fiscal-year.md) |
| <span data-ttu-id="038ac-120">Définissez comment déclarer les montants de taxe sur la valeur ajoutée que vous avez recueillis sur les ventes aux autorités fiscales.</span><span class="sxs-lookup"><span data-stu-id="038ac-120">Define how you report value-added tax amounts that you have collected for sales to the tax authorities.</span></span> |[<span data-ttu-id="038ac-121">Procédure : Déclarer la TVA aux autorités fiscales</span><span class="sxs-lookup"><span data-stu-id="038ac-121">How To: Report VAT to Tax Authorities</span></span>](finance-how-report-vat.md)|
| <span data-ttu-id="038ac-122">Définissez vos fonctionnalités Ventes et Achats pour gérer les paiements dans des devises étrangères.</span><span class="sxs-lookup"><span data-stu-id="038ac-122">Set your Sales and Purchases features up to handle payments in foreign currencies.</span></span>|[<span data-ttu-id="038ac-123">Activer l'affectation d'écritures en devises différentes</span><span class="sxs-lookup"><span data-stu-id="038ac-123">Enable Application of Ledger Entries in Different Currencies</span></span>](finance-how-enable-application-ledger-entries-different-currencies.md)
| <span data-ttu-id="038ac-124">Ajouter de nouveaux comptes au plan comptable existant.</span><span class="sxs-lookup"><span data-stu-id="038ac-124">Add new accounts to the existing chart of accounts.</span></span> |[<span data-ttu-id="038ac-125">Configuration du plan comptable</span><span class="sxs-lookup"><span data-stu-id="038ac-125">Setting Up the Chart of Accounts</span></span>](finance-setup-chart-accounts.md) |
| <span data-ttu-id="038ac-126">Configurez les graphiques de veille économique pour analyser la trésorerie.</span><span class="sxs-lookup"><span data-stu-id="038ac-126">Set up business intelligence (BI) charts to analyze cash flow.</span></span> |[<span data-ttu-id="038ac-127">Configuration d'une analyse de trésorerie</span><span class="sxs-lookup"><span data-stu-id="038ac-127">Setting Up Cash Flow Analysis</span></span>](finance-setup-cash-flow-analyses.md) |
|<span data-ttu-id="038ac-128">Activer la facturation d'un client qui n'est pas configuré dans le système.</span><span class="sxs-lookup"><span data-stu-id="038ac-128">Enable invoicing of a customer who is not set up in the system.</span></span>|[<span data-ttu-id="038ac-129">Configurer des clients effectuant un achat au comptoir</span><span class="sxs-lookup"><span data-stu-id="038ac-129">Set Up Cash Customers</span></span>](finance-how-to-set-up-cash-customers.md)|
| <span data-ttu-id="038ac-130">Configurez le rapport Intrastat et envoyez-le à une administration</span><span class="sxs-lookup"><span data-stu-id="038ac-130">Set up Intrastat reporting, and submit the report to an authority</span></span> | [<span data-ttu-id="038ac-131">Configurer et soumettre une déclaration Intrastat</span><span class="sxs-lookup"><span data-stu-id="038ac-131">Set Up and Report Intrastat</span></span>](finance-how-setup-report-intrastat.md)|

## <a name="see-also"></a><span data-ttu-id="038ac-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="038ac-132">See Also</span></span>
[<span data-ttu-id="038ac-133">Finance</span><span class="sxs-lookup"><span data-stu-id="038ac-133">Finance</span></span>](finance.md)  
[<span data-ttu-id="038ac-134">Gestion des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="038ac-134">Managing Bank Accounts</span></span>](bank-manage-bank-accounts.md)  
[<span data-ttu-id="038ac-135">Utilisation des axes analytiques</span><span class="sxs-lookup"><span data-stu-id="038ac-135">Working with Dimensions</span></span>](finance-dimensions.md)  
[<span data-ttu-id="038ac-136">Importation des données métier à partir d'autres systèmes financiers</span><span class="sxs-lookup"><span data-stu-id="038ac-136">Importing Business Data from Other Finance Systems</span></span>](upload-data.md)  
[<span data-ttu-id="038ac-137">Analyse de la trésorerie dans votre société</span><span class="sxs-lookup"><span data-stu-id="038ac-137">Analyzing Cash Flow in Your Company</span></span>](finance-analyze-cash-flow.md)  
<span data-ttu-id="038ac-138">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="038ac-138">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]

