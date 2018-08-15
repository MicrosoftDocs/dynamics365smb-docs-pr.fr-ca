---
title: "Aperçu des tâches permettant de gérer la comptabilité client | Microsoft Docs"
description: "Décrit les tâches permettant de gérer les montant à recevoir et d'affecter les paiements aux écritures client ou fournisseur."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customer payment, debtor, balance due, AR
ms.date: 04/30/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2286b728a464943841b192031cfea13644441013
ms.openlocfilehash: b53bd7b78744d61cdb783d1e973be8c730117d57
ms.contentlocale: fr-ca
ms.lasthandoff: 06/28/2018

---
# <a name="managing-receivables"></a><span data-ttu-id="80d6c-103">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="80d6c-103">Managing Receivables</span></span>
<span data-ttu-id="80d6c-104">Une étape normale de n'importe quelle opération financière consiste à rapprocher des comptes bancaires, ce qui nécessite d'affecter les paiements entrants avec des écritures fournisseur ou client pour fermer les factures vente et les notes de crédit achat comme payées.</span><span class="sxs-lookup"><span data-stu-id="80d6c-104">A regular step in any financial rhythm is to reconcile bank accounts, which requires that you apply incoming payments to customer or vendor ledger entries to close sales invoices and purchase credit memos as paid.</span></span>

<span data-ttu-id="80d6c-105">Bien que la plupart des clients dans les environnements B2B payent un certain temps après la livraison en laissant les factures vente reportées ouvertes jusqu'à ce qu'elles soient fermées (affectées) par le département Comptabilité client à la réception du paiement, certaines factures vente peuvent être payées immédiatement, par exemple avec PayPal.</span><span class="sxs-lookup"><span data-stu-id="80d6c-105">While most customers in B2B environments pay some time after delivery, leaving the posted sales invoices open for the Accounts Receivable department to close (apply) when payment is received, some sales invoices can be paid immediately, for example with PayPal.</span></span> <span data-ttu-id="80d6c-106">Ces factures sont immédiatement affectées comme payées lors de leur report et n'apparaissent donc pas comme paiements à traiter dans la Comptabilité client.</span><span class="sxs-lookup"><span data-stu-id="80d6c-106">Such invoices are immediately applied as paid when they are posted and, therefore, do not appear as payments to be processes in AR.</span></span> <span data-ttu-id="80d6c-107">Pour plus d'informations, voir [Facturation des ventes](sales-how-invoice-sales.md), par exemple.</span><span class="sxs-lookup"><span data-stu-id="80d6c-107">For more information, see, for example, [Invoice Sales](sales-how-invoice-sales.md).</span></span>  

<span data-ttu-id="80d6c-108">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], l'une des méthodes les plus rapides pour enregistrer les paiements à partir de la fenêtre **Feuille rapprochement bancaire** consiste à importer un fichier ou un flux de relevé bancaire.</span><span class="sxs-lookup"><span data-stu-id="80d6c-108">In [!INCLUDE[d365fin](includes/d365fin_md.md)], one of the fastest ways to register payments from the **Payment Reconciliation Journal** window by importing a bank statement file or feed.</span></span> <span data-ttu-id="80d6c-109">Les paiements sont affectés aux écritures client ou fournisseur ouvertes selon les correspondances entre le texte de paiement et les informations d'écriture.</span><span class="sxs-lookup"><span data-stu-id="80d6c-109">The payments are applied to open customer or vendor ledger entries based on data matches between payment text and entry information.</span></span> <span data-ttu-id="80d6c-110">Vous pouvez consulter et modifier les correspondances avant de reporter le journal, puis fermer les écritures compte bancaire pour les écritures lorsque vous reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="80d6c-110">You can review and change the matches before you post the journal, and close bank account ledger entries for ledger entries when you post the journal.</span></span> <span data-ttu-id="80d6c-111">Le compte bancaire est rapproché lorsque tous les paiements sont affectés.</span><span class="sxs-lookup"><span data-stu-id="80d6c-111">The bank account is reconciled when all payments are applied.</span></span>

<span data-ttu-id="80d6c-112">D'autres fenêtres vous permettent d'affecter des paiements ou de rapprocher des comptes bancaires :</span><span class="sxs-lookup"><span data-stu-id="80d6c-112">Other windows exist where you can either apply payments or reconcile bank accounts:</span></span>

* <span data-ttu-id="80d6c-113">La fenêtre **Rapprochements bancaires** qui vous permet de rapprocher des comptes bancaires en mettant en correspondance les lignes de relevé bancaire importées avec les écritures de compte bancaire du système.</span><span class="sxs-lookup"><span data-stu-id="80d6c-113">The **Bank Account Reconciliations** window, where you reconcile bank accounts by matching imported bank statement lines with your system bank account ledger entries.</span></span> <span data-ttu-id="80d6c-114">Vous pouvez également rapprocher des paiements par chèque.</span><span class="sxs-lookup"><span data-stu-id="80d6c-114">Here, you can also reconcile check payments.</span></span> <span data-ttu-id="80d6c-115">Pour plus d'informations, reportez vous à [Rapprocher des comptes bancaires séparément](bank-how-reconcile-bank-accounts-separately.md).</span><span class="sxs-lookup"><span data-stu-id="80d6c-115">For more information, see [Reconcile Bank Accounts Separately](bank-how-reconcile-bank-accounts-separately.md).</span></span> <span data-ttu-id="80d6c-116">Vous ne pouvez pas affecter des paiements.</span><span class="sxs-lookup"><span data-stu-id="80d6c-116">Here, you cannot apply payments.</span></span>
* <span data-ttu-id="80d6c-117">La fenêtre **Enregistrement de paiement** qui vous permet d'affecter manuellement les paiements reçus en liquide, par chèque ou par transaction bancaire par rapport à une liste générée de documents vente impayés.</span><span class="sxs-lookup"><span data-stu-id="80d6c-117">The **Payment Registration** window, where you can manually apply payments received as cash, check, or bank transaction against a generated list of unpaid sales documents.</span></span> <span data-ttu-id="80d6c-118">Notez que cette fonctionnalité est uniquement disponible pour les documents vente.</span><span class="sxs-lookup"><span data-stu-id="80d6c-118">Note that this functionality is available only for sales documents.</span></span> <span data-ttu-id="80d6c-119">Vous ne pouvez pas affecter des paiements sortants, et vous ne pouvez pas rapprocher des comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="80d6c-119">Here, you cannot apply outgoing payments, and you cannot reconcile bank accounts.</span></span>
* <span data-ttu-id="80d6c-120">La fenêtre **Feuille règlement** où vous pouvez valider manuellement les réceptions dans un compte général, client ou autre en saisissant une ligne règlement.</span><span class="sxs-lookup"><span data-stu-id="80d6c-120">The **Cash Receipt Journal** window, where you manually post receipts to the relevant general ledger, customer, or other account by entering a payment line.</span></span> <span data-ttu-id="80d6c-121">Vous pouvez affecter la réception ou le remboursement à une ou plusieurs écritures ouvertes avant de reporter le journal des encaissements, ou à partir des écritures client.</span><span class="sxs-lookup"><span data-stu-id="80d6c-121">You can either apply the receipt or refund to one or more open entries before you post the cash receipt journal, or from the customer ledger entries.</span></span> <span data-ttu-id="80d6c-122">Vous ne pouvez pas rapprocher des comptes bancaires.</span><span class="sxs-lookup"><span data-stu-id="80d6c-122">Here, you cannot reconcile bank accounts.</span></span>  

<span data-ttu-id="80d6c-123">Une autre tâche de gestion des comptes client consiste à collecter des soldes restants, notamment pour gérer les frais financiers et l'émission de rappels.</span><span class="sxs-lookup"><span data-stu-id="80d6c-123">Another part of managing receivables is to collect outstanding balances, including finance charges, and issue reminders.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="80d6c-124"> offre d'autres méthodes pour effectuer ces opérations.</span><span class="sxs-lookup"><span data-stu-id="80d6c-124"> offers ways to do those things as well.</span></span> <span data-ttu-id="80d6c-125">Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).</span><span class="sxs-lookup"><span data-stu-id="80d6c-125">For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).</span></span>  

<span data-ttu-id="80d6c-126">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="80d6c-126">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>  

| <span data-ttu-id="80d6c-127">À</span><span class="sxs-lookup"><span data-stu-id="80d6c-127">To</span></span> | <span data-ttu-id="80d6c-128">Voir</span><span class="sxs-lookup"><span data-stu-id="80d6c-128">See</span></span> |
| --- | --- |
| <span data-ttu-id="80d6c-129">Affecter des paiements aux écritures client ou fournisseur ouvertes sur la base d'un fichier ou flux de relevé de compte bancaire importé, et rapprocher le compte bancaire lorsque tous les paiements sont affectés.</span><span class="sxs-lookup"><span data-stu-id="80d6c-129">Apply payments to open customer or vendor ledger entries based on an imported bank statement file or feed, and reconcile the bank account when all payments are applied.</span></span> |[<span data-ttu-id="80d6c-130">Lettrage automatique des paiements et rapprochement des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="80d6c-130">Applying Payments Automatically and Reconciling Bank Accounts</span></span>](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| <span data-ttu-id="80d6c-131">Affectez des paiements à des écritures client ouvertes selon la saisie manuelle dans la liste des documents vente non payés.</span><span class="sxs-lookup"><span data-stu-id="80d6c-131">Apply payments to open customer ledger entries based on manual entry in a list of unpaid sales documents.</span></span> |[<span data-ttu-id="80d6c-132">Rapprocher les paiements client manuellement à partir de la liste des documents vente échus</span><span class="sxs-lookup"><span data-stu-id="80d6c-132">Reconcile Customer Payments Manually From a List of Unpaid Sales Documents</span></span>](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md) |
| <span data-ttu-id="80d6c-133">Reportez des encaissements ou des remboursements pour des clients dans le journal des encaissements et affectez-les à des écritures client, à partir du journal ou des écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="80d6c-133">Post cash receipts or refunds for customers in the cash receipt journal and apply to customer ledger entries, either from the journal or from posted ledger entries.</span></span> |[<span data-ttu-id="80d6c-134">Rapprocher les paiements client manuellement</span><span class="sxs-lookup"><span data-stu-id="80d6c-134">Reconcile Customer Payments Manually</span></span>](receivables-how-apply-sales-transactions-manually.md) |
| <span data-ttu-id="80d6c-135">Rappeler aux clients les soldes échus, calculer les intérêts et les frais financiers, et gérer les comptes clients.</span><span class="sxs-lookup"><span data-stu-id="80d6c-135">Remind customers of overdue amounts, calculate interest and finance charges, and manage accounts receivable.</span></span> |[<span data-ttu-id="80d6c-136">Collecte des soldes restants</span><span class="sxs-lookup"><span data-stu-id="80d6c-136">Collect Outstanding Balances</span></span>](receivables-collect-outstanding-balances.md) |
|<span data-ttu-id="80d6c-137">Assurez-vous de connaître le coût des articles livrés en affectant les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez après la vente.</span><span class="sxs-lookup"><span data-stu-id="80d6c-137">Ensure that you know the cost of shipped items by assigning added item costs, such as freight, physical handling, insurance, and transportation that you incur after selling.</span></span>|[<span data-ttu-id="80d6c-138">Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires</span><span class="sxs-lookup"><span data-stu-id="80d6c-138">Use Item Charges to Account for Additional Trade Costs</span></span>](payables-how-assign-item-charges.md)|
|<span data-ttu-id="80d6c-139">Configurer une valeur de tolérance selon laquelle le système ferme une facture même si le paiement, tenant compte d'éventuels escomptes, ne couvre pas intégralement le montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="80d6c-139">Set up a tolerance by which the system closes an invoice even though the payment, including any discount, does not fully cover the amount on the invoice.</span></span>|[<span data-ttu-id="80d6c-140">Utilisation des tolérances de règlement et des tolérances d'escompte de paiement</span><span class="sxs-lookup"><span data-stu-id="80d6c-140">Work with Payment Tolerances and Payment Discount Tolerances</span></span>](finance-payment-tolerance-and-payment-discount-tolerance.md)|
## <a name="see-also"></a><span data-ttu-id="80d6c-141">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80d6c-141">See Also</span></span>
[<span data-ttu-id="80d6c-142">Vente</span><span class="sxs-lookup"><span data-stu-id="80d6c-142">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="80d6c-143">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="80d6c-143">Managing Payables</span></span>](payables-manage-payables.md)  
<span data-ttu-id="80d6c-144">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="80d6c-144">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="80d6c-145">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="80d6c-145">General Business Functionality</span></span>](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 
