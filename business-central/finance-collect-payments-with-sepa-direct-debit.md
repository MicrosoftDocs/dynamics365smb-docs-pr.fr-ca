---
title: "Prélèvement SEPA dans Business Central | Microsoft Docs"
description: "Vous pouvez collecter les paiements directement à partir du compte bancaire du client en fonction du format SEPA."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 557d6411540cc778a8f6810e747d4113fccd8f4c
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="collecting-payments-with-sepa-direct-debit"></a><span data-ttu-id="c18ce-103">Recouvrement de paiements par prélèvement automatique SEPA</span><span class="sxs-lookup"><span data-stu-id="c18ce-103">Collecting Payments with SEPA Direct Debit</span></span>
<span data-ttu-id="c18ce-104">Avec le consentement de votre client, vous pouvez collecter les paiements directement à partir du compte bancaire du client en fonction du format SEPA.</span><span class="sxs-lookup"><span data-stu-id="c18ce-104">With your customer’s consent, you can collect payments directly from the customer’s bank account according to the SEPA format.</span></span>  

 <span data-ttu-id="c18ce-105">Tout d'abord, définissez le format d'exportation du fichier bancaire qui indique à votre banque comment effectuer un prélèvement automatique.</span><span class="sxs-lookup"><span data-stu-id="c18ce-105">First, set up the export format of the bank file that instructs your bank to perform a direct debit.</span></span> <span data-ttu-id="c18ce-106">Ensuite, paramétrez le mode de paiement du client.</span><span class="sxs-lookup"><span data-stu-id="c18ce-106">Then, set up the customer’s payment method.</span></span> <span data-ttu-id="c18ce-107">Enfin, configurez le mandat de prélèvement qui reflète votre entente avec le client pour collecter leurs paiements pendant une certaine durée.</span><span class="sxs-lookup"><span data-stu-id="c18ce-107">Last, set up the direct-debit mandate that reflects your agreement with the customer to collect their payments in a certain agreement period.</span></span>  

 <span data-ttu-id="c18ce-108">Pour demander à la banque de transférer le montant du paiement du compte bancaire du client vers le compte de votre compagnie, vous créez une écriture de recouvrement de prélèvement, qui conserve des informations sur les comptes bancaires, les factures de vente concernées et le mandat de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c18ce-108">To instruct the bank to transfer the payment amount from the customer’s bank account to your company’s account, you create a direct-debit collection entry, which holds information about bank accounts, the affected sales invoices, and the direct-debit mandate.</span></span> <span data-ttu-id="c18ce-109">Vous exportez ensuite un fichier XML basé sur l'écriture de collection, que vous envoyez à votre banque pour traitement.</span><span class="sxs-lookup"><span data-stu-id="c18ce-109">You then export an XML file that is based on the collection entry, which you send to your bank for processing.</span></span> <span data-ttu-id="c18ce-110">La banque vous communiquera tous les paiements impossibles à traiter, et vous devez rejeter manuellement les écritures de collection prélèvement automatique en question.</span><span class="sxs-lookup"><span data-stu-id="c18ce-110">Any payments that could not be processed will be communicated to you by your bank, and you must then manually reject the direct debit-collection entries in question.</span></span>  

 <span data-ttu-id="c18ce-111">Vous pouvez définir des codes vente client standard avec les informations de mode et de mandat de prélèvement.</span><span class="sxs-lookup"><span data-stu-id="c18ce-111">You can set up standard customer sales codes with the direct-debit payment method and mandate information.</span></span> <span data-ttu-id="c18ce-112">Vous pouvez ensuite utiliser le traitement en lot **Créer factures client standard** pour générer plusieurs factures vente avec les informations de prélèvement automatique préremplies.</span><span class="sxs-lookup"><span data-stu-id="c18ce-112">You can then use the **Create Standard Cust. Invoices** batch job to generate multiple sales invoices with the direct-debit information prefilled.</span></span> <span data-ttu-id="c18ce-113">Ceci peut être effectué manuellement ou automatiquement, en fonction de la date d'échéance du paiement.</span><span class="sxs-lookup"><span data-stu-id="c18ce-113">This is can be done manually or automatically, according to the payment due date.</span></span>  

 <span data-ttu-id="c18ce-114">Lorsque les paiements sont traités avec succès, tel que communiqué par votre banque, vous pouvez valider les réceptions de paiement directement à partir de la fenêtre **Écritures recouvrement prélèvement**, ou en déplaçant les lignes paiement vers la feuille où vous validez des réceptions de paiement, tels que la fenêtre **Feuille règlement**.</span><span class="sxs-lookup"><span data-stu-id="c18ce-114">When payments are successfully processed, as communicated by your bank, you can post the payment receipts either directly from the **Direct Debit Collect. Entries** window or by moving the payment lines to the journal where you post payment receipts, such as the **Cash Receipt Journal** window.</span></span> <span data-ttu-id="c18ce-115">Sinon, en fonction de votre processus de gestion de trésorerie, vous pouvez attendre et affecter les paiements lors du rapprochement bancaire.</span><span class="sxs-lookup"><span data-stu-id="c18ce-115">Alternatively, depending on your cash management process, you can wait and just apply the payments as a part of bank reconciliation.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="c18ce-116">Pour réunir les paiements à l'aide du prélèvement SEPA, la devise sur la facture vente doit être l'EURO.</span><span class="sxs-lookup"><span data-stu-id="c18ce-116">To collect payments using SEPA Direct Debit, the currency on the sales invoice must be EURO.</span></span>  

 <span data-ttu-id="c18ce-117">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="c18ce-117">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>   

|<span data-ttu-id="c18ce-118">**Pour**</span><span class="sxs-lookup"><span data-stu-id="c18ce-118">**To**</span></span>|<span data-ttu-id="c18ce-119">**Voir**</span><span class="sxs-lookup"><span data-stu-id="c18ce-119">**See**</span></span>|  
|------------|-------------|  
|<span data-ttu-id="c18ce-120">Préparez les formats de compte bancaire, les modes de paiement et les accords clients pour le prélèvement automatique SEPA.</span><span class="sxs-lookup"><span data-stu-id="c18ce-120">Prepare bank account formats, payment methods, and customer agreements for SEPA direct debit.</span></span>|[<span data-ttu-id="c18ce-121">Configurer un prélèvement SEPA</span><span class="sxs-lookup"><span data-stu-id="c18ce-121">Set Up SEPA Direct Debit</span></span>](finance-how-to-set-up-sepa-direct-debit.md)|  
|<span data-ttu-id="c18ce-122">Demander à votre banque de transférer les montants de paiement des comptes bancaires de vos clients vers le compte de votre compagnie en fonction de votre configuration du prélèvement automatique SEPA.</span><span class="sxs-lookup"><span data-stu-id="c18ce-122">Instruct your bank to transfer payment amounts from your customers’ bank accounts to your company’s account according to your setup of SEPA direct debit.</span></span>|[<span data-ttu-id="c18ce-123">Créer des écritures de collection prélèvement automatique SEPA et les exporter vers un fichier bancaire</span><span class="sxs-lookup"><span data-stu-id="c18ce-123">Create SEPA Direct Debit Collection Entries and Export to a Bank File</span></span>](finance-how-create-sepa-direct-debit-collection-entries-export-bank-file.md)|  
|<span data-ttu-id="c18ce-124">Paramétrez des codes vente client standard pour les factures de prélèvement automatique et générez des factures vente avec les informations de prélèvement automatique lorsque les factures sont échues.</span><span class="sxs-lookup"><span data-stu-id="c18ce-124">Set up standard customer sales codes for direct-debit invoices and generate sales invoices with direct-debit information when the invoices are due for payment.</span></span>|[<span data-ttu-id="c18ce-125">Créer des lignes ventes et achat récurrentes</span><span class="sxs-lookup"><span data-stu-id="c18ce-125">Create Recurring Sales and Purchase Lines</span></span>](sales-how-work-standard-lines.md)|  
|<span data-ttu-id="c18ce-126">Reporter les paiements effectués comme prélèvements SEPA.</span><span class="sxs-lookup"><span data-stu-id="c18ce-126">Post payments made as SEPA direct debits.</span></span>|[<span data-ttu-id="c18ce-127">Reporter des réceptions règlement de prélèvement SEPA</span><span class="sxs-lookup"><span data-stu-id="c18ce-127">Post SEPA Direct Debit Payment Receipts</span></span>](finance-how-to-post-sepa-direct-debit-payment-receipts.md)|  

## <a name="see-also"></a><span data-ttu-id="c18ce-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c18ce-128">See Also</span></span>  
[<span data-ttu-id="c18ce-129">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="c18ce-129">Managing Receivables</span></span>](receivables-manage-receivables.md)
