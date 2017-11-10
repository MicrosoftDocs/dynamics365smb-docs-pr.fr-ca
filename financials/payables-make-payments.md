---
title: "Aperçu des tâches permettant de gérer les paiements aux fournisseurs| Microsoft Docs"
description: "Décrit les tâches permettant de gérer les paiements aux fournisseurs ou aux créditeurs, y compris le report de lignes paiement et l'obtention d'un aperçu du solde échu."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: print check, vendor payment, creditor, debt, balance due, AP
ms.date: 06/28/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 00792adb8b4c7deccee262982cd532423884c8f5
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="making-payments"></a><span data-ttu-id="1ad69-103">Effectuer des paiements</span><span class="sxs-lookup"><span data-stu-id="1ad69-103">Making Payments</span></span>
<span data-ttu-id="1ad69-104">Lorsque vous effectuez des paiements aux fournisseurs ou des remboursements aux employés, vous reportez les lignes paiement associées dans la fenêtre **Journal de paiement**.</span><span class="sxs-lookup"><span data-stu-id="1ad69-104">When you make payments to vendors or reimbursements to employees, you post the related payment lines in the **Payment Journal** window.</span></span> <span data-ttu-id="1ad69-105">Vous pouvez utiliser la fonction **Proposer paiements fournisseur** pour rechercher les paiements fournisseurs échus.</span><span class="sxs-lookup"><span data-stu-id="1ad69-105">You can use the **Suggest Vendor Payments** function to find vendor payments that are due.</span></span> <span data-ttu-id="1ad69-106">Vous pouvez également utiliser le rapport **Fournisseur - Chronologie sommaire** pour obtenir un aperçu des paiements fournisseurs échus.</span><span class="sxs-lookup"><span data-stu-id="1ad69-106">You can also use the **Vendor - Summary Aging** report to get an overview of due vendor payments.</span></span>

<span data-ttu-id="1ad69-107">À partir du journal paiement, vous pouvez imprimer des chèques informatisés ou effectuer un enregistrement lorsque les chèques sont rédigés.</span><span class="sxs-lookup"><span data-stu-id="1ad69-107">From the payment journal, you can print computer checks or record when checks are written.</span></span> <span data-ttu-id="1ad69-108">Si vous sélectionnez **Informatique** dans le champ **Mode émission paiement**, toutes les lignes représentant des chèques doivent être imprimées avant que les lignes feuille puissent être validées.</span><span class="sxs-lookup"><span data-stu-id="1ad69-108">If you select **Computer Check** in the **Bank Payment Type** field, then any lines representing checks must be printed before the payment journal can be posted.</span></span>

<span data-ttu-id="1ad69-109">Lorsque les paiements sont reportés, vous pouvez les exporter vers un fichier bancaire à télécharger vers votre banque pour traitement.</span><span class="sxs-lookup"><span data-stu-id="1ad69-109">When the payments are posted, you can export them to a bank file for upload to your bank for processing.</span></span>

<span data-ttu-id="1ad69-110">Une fois les paiements effectués au niveau de votre banque, vous devez les affecter à leurs écritures fournisseur ou employé ouvertes correspondantes.</span><span class="sxs-lookup"><span data-stu-id="1ad69-110">After the payments are made at your bank, you must apply them to their related open vendor or employee ledger entries.</span></span> <span data-ttu-id="1ad69-111">Vous pouvez le faire manuellement ou en important un fichier de relevé de compte bancaire et en affectant les paiements automatiquement.</span><span class="sxs-lookup"><span data-stu-id="1ad69-111">You can do this manually or by importing a bank statement file and applying the payments automatically.</span></span> <span data-ttu-id="1ad69-112">Pour plus d'informations, reportez-vous à [Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="1ad69-112">For more information, see [Apply Payments Automatically and Reconcile Bank Accounts](receivables-apply-payments-auto-reconcile-bank-accounts.md).</span></span>

<span data-ttu-id="1ad69-113">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="1ad69-113">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>

| <span data-ttu-id="1ad69-114">À</span><span class="sxs-lookup"><span data-stu-id="1ad69-114">To</span></span> | <span data-ttu-id="1ad69-115">Voir</span><span class="sxs-lookup"><span data-stu-id="1ad69-115">See</span></span> |
| --- | --- |
|<span data-ttu-id="1ad69-116">Utilisez la fenêtre **Journal de paiement**, qui est basée sur le journal général, pour reporter les paiements aux fournisseurs ou aux employés.</span><span class="sxs-lookup"><span data-stu-id="1ad69-116">Use the **Payment Journal** window, which is a based on the general journal, to post payments to vendors or employees.</span></span>|[<span data-ttu-id="1ad69-117">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="1ad69-117">Working with General Journals</span></span>](ui-work-general-journals.md)|
| <span data-ttu-id="1ad69-118">Utiliser une fonction pour proposer des paiements fournisseur en fonction de critères sélectionnés, tels que la date d'échéance, la possibilité d'escompte et vos liquidités.</span><span class="sxs-lookup"><span data-stu-id="1ad69-118">Use a function to suggest vendor payments according to selected criteria, such as due date, discount eligibility, and your liquidity.</span></span> |[<span data-ttu-id="1ad69-119">Procédure : proposer des paiements fournisseur</span><span class="sxs-lookup"><span data-stu-id="1ad69-119">How to: Suggest Vendor Payments</span></span>](payables-how-suggest-vendor-payments.md) |
|<span data-ttu-id="1ad69-120">Remboursez les frais personnels des employés pour leurs activités professionnelles en effectuant le paiement sur leur compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="1ad69-120">Reimburse employees for personal expenses during business activities by making payment to their bank account.</span></span>|[<span data-ttu-id="1ad69-121">Procédure : enregistrer et rembourser les frais des employés</span><span class="sxs-lookup"><span data-stu-id="1ad69-121">How to: Record and Reimburse Employees' Expenses</span></span>](finance-how-record-reimburse-employee-expenses.md)|
| <span data-ttu-id="1ad69-122">Émettre des chèques pour les paiements fournisseur, sous forme de documents imprimés ou de chèques informatiques.</span><span class="sxs-lookup"><span data-stu-id="1ad69-122">Issue checks for vendor payments, either as print-outs or as computer checks.</span></span> <span data-ttu-id="1ad69-123">Annuler des chèques avant ou après le report.</span><span class="sxs-lookup"><span data-stu-id="1ad69-123">Void checks before or after posting.</span></span> |[<span data-ttu-id="1ad69-124">Procédure : utilisation des chèques</span><span class="sxs-lookup"><span data-stu-id="1ad69-124">How to: Work With Checks</span></span>](payables-how-work-checks.md) |
| <span data-ttu-id="1ad69-125">Payez le fournisseur en liquide ou par chèque et reportez le paiement lorsque vous reportez la facture.</span><span class="sxs-lookup"><span data-stu-id="1ad69-125">Pay the vendor by cash or check, and post the payment when you post the invoice.</span></span> |[<span data-ttu-id="1ad69-126">Procédure : établir rapidement des factures achat</span><span class="sxs-lookup"><span data-stu-id="1ad69-126">How to: Settle Purchase Invoices Promptly</span></span>](finance-how-to-settle-purchase-invoices-promptly.md) |
| <span data-ttu-id="1ad69-127">Assurez-vous que la banque efface uniquement les chèques et les montants validés en envoyant un fichier contenant des informations de paiement, du chèque et du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="1ad69-127">Make sure that your bank only clears validated checks and amounts by sending them a file that contains vendor, check, and payment information.</span></span> |[<span data-ttu-id="1ad69-128">Procédure : exporter des fichiers Positive Pay</span><span class="sxs-lookup"><span data-stu-id="1ad69-128">How to: Export a Positive Pay file</span></span>](finance-how-positive-pay.md) |
|<span data-ttu-id="1ad69-129">Exporter des paiements à partir de la fenêtre **Feuille paiement** vers un fichier bancaire que vous téléchargez vers votre banque pour traitement, y compris un transfert électronique de fond (EFT) en Amérique du Nord.</span><span class="sxs-lookup"><span data-stu-id="1ad69-129">Export payments from the **Payment Journal** window to a bank file that you upload to your bank for processing, including EFT (electronic funds transfer) in North America.</span></span> |[<span data-ttu-id="1ad69-130">Procédure : exportation de paiements vers un fichier bancaire</span><span class="sxs-lookup"><span data-stu-id="1ad69-130">How to: Export Payments to a Bank File</span></span>](payables-how-export-payments-bank-file.md)|  

## <a name="see-also"></a><span data-ttu-id="1ad69-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1ad69-131">See Also</span></span>
[<span data-ttu-id="1ad69-132">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="1ad69-132">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="1ad69-133">Achats</span><span class="sxs-lookup"><span data-stu-id="1ad69-133">Purchasing</span></span>](purchasing-manage-purchasing.md)  
[<span data-ttu-id="1ad69-134">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="1ad69-134">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="1ad69-135">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1ad69-135">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
