---
title: "Gérer des comptes bancaires| Microsoft Docs"
description: "Vous devez régulièrement rapprocher les écritures bancaires dans Financials des transactions bancaires associées à vos comptes bancaires."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reconcile
ms.date: 06/02/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: dcefa921d7e8b901d906085e6bce01d6e0aa6ac4
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="managing-bank-accounts"></a><span data-ttu-id="c3c28-103">Gestion des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="c3c28-103">Managing Bank Accounts</span></span>
<span data-ttu-id="c3c28-104">Vous devez rapprocher régulièrement vos écritures comptables banque dans [!INCLUDE[d365fin](includes/d365fin_md.md)] avec les transactions bancaires associées dans les comptes bancaires de votre banque, puis valider le solde sur votre compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="c3c28-104">At regular intervals, you must reconcile your bank ledger entries in [!INCLUDE[d365fin](includes/d365fin_md.md)] with the related bank transactions in bank accounts at your bank, and then post the balance to your bank account.</span></span> <span data-ttu-id="c3c28-105">Vous pouvez effectuer cette tâche soit dans le cadre du traitement des paiements représentés sur un relevé bancaire dans la **Feuille rapprochement bancaire**.</span><span class="sxs-lookup"><span data-stu-id="c3c28-105">You can perform this task either as part of processing the payments represented on a bank statement in the **Payment Reconciliation Journal**.</span></span> <span data-ttu-id="c3c28-106">Sinon, vous pouvez effectuer la tâche séparément du traitement des paiements, dans la fenêtre **Rapprochement bancaire**, qui prend en charge des écritures comptables chèque.</span><span class="sxs-lookup"><span data-stu-id="c3c28-106">Alternatively, you can perform the task separately from payment processing, in the **Bank Acc. Reconciliation** window, which supports check ledger entries.</span></span> <span data-ttu-id="c3c28-107">Dans les deux cas, vous renseignez les fenêtres en important le relevé bancaire dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3c28-107">In both cases, you fill in the windows by importing the bank statement into [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>

<span data-ttu-id="c3c28-108">Parfois, vous devez transférer les montants entre comptes bancaires dans [!INCLUDE[d365fin](includes/d365fin_md.md)] pour refléter les transferts effectués au niveau de votre banque.</span><span class="sxs-lookup"><span data-stu-id="c3c28-108">Sometimes, you need to transfer amounts between bank account in [!INCLUDE[d365fin](includes/d365fin_md.md)] to reflect transfers at your bank.</span></span> <span data-ttu-id="c3c28-109">Vous effectuez cette tâche dans la fenêtre **Feuille comptabilité**, de différentes manières en fonction de la devise des fonds.</span><span class="sxs-lookup"><span data-stu-id="c3c28-109">You perform this task in the **General Journal** window, in different ways depending on the currency of the funds.</span></span>

<span data-ttu-id="c3c28-110">Avant de pouvoir gérer des comptes bancaires, vous devez configurer chaque compte bancaire en tant que fiche compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="c3c28-110">Before you can manage bank accounts, you must set each bank account up as a bank account card.</span></span> <span data-ttu-id="c3c28-111">En outre, vous devez configurer les services électroniques que vous pouvez utiliser pour l'importation de relevés bancaires et l'exportation de fichiers de paiement.</span><span class="sxs-lookup"><span data-stu-id="c3c28-111">In addition, you must set up electronic services that you may use for bank statement import and payment file export.</span></span> <span data-ttu-id="c3c28-112">Pour plus d'informations, reportez vous à [Configuration de comptes bancaires](bank-setup-banking.md).</span><span class="sxs-lookup"><span data-stu-id="c3c28-112">For more information, see [Set Up Bank Accounts](bank-setup-banking.md).</span></span>

<span data-ttu-id="c3c28-113">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="c3c28-113">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>

| <span data-ttu-id="c3c28-114">À</span><span class="sxs-lookup"><span data-stu-id="c3c28-114">To</span></span> | <span data-ttu-id="c3c28-115">Voir</span><span class="sxs-lookup"><span data-stu-id="c3c28-115">See</span></span> |
| --- | --- |
| <span data-ttu-id="c3c28-116">Rapprocher des comptes bancaires en relation avec le traitement des paiements dans la fenêtre **Feuille rapprochement bancaire**.</span><span class="sxs-lookup"><span data-stu-id="c3c28-116">Reconcile bank accounts in connection with payment processing in the **Payment Reconciliation Journal** window.</span></span> |[<span data-ttu-id="c3c28-117">Procédure : lettrage automatique des paiements et rapprochement des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="c3c28-117">Apply Payments Automatically and Reconcile Bank Accounts</span></span>](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| <span data-ttu-id="c3c28-118">Rapprocher des comptes bancaires, y compris les écritures comptables chèque, en tant que tâche distincte dans la fenêtre **Rapprochement bancaire**.</span><span class="sxs-lookup"><span data-stu-id="c3c28-118">Reconcile bank accounts, including check ledger entries, as a separate task in the **Bank Acc. Reconciliation** window.</span></span> |[<span data-ttu-id="c3c28-119">Procédure : rapprocher des comptes bancaires séparément</span><span class="sxs-lookup"><span data-stu-id="c3c28-119">How to: Reconcile Bank Accounts Separately</span></span>](bank-how-reconcile-bank-accounts-separately.md) |
| <span data-ttu-id="c3c28-120">Reporter des transferts entre comptes bancaires dans la même devise ou dans des devises différentes.</span><span class="sxs-lookup"><span data-stu-id="c3c28-120">Post transfers between bank accounts in the same currency or in different currencies.</span></span> |[<span data-ttu-id="c3c28-121">Procédure : transfert de fonds à la banque</span><span class="sxs-lookup"><span data-stu-id="c3c28-121">How to: Transfer Bank Funds</span></span>](bank-how-transfer-bank-funds.md) |

## <a name="see-also"></a><span data-ttu-id="c3c28-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c3c28-122">See Also</span></span>
[<span data-ttu-id="c3c28-123">Paramétrage des opérations bancaires</span><span class="sxs-lookup"><span data-stu-id="c3c28-123">Setting Up Banking</span></span>](bank-setup-banking.md)  
[<span data-ttu-id="c3c28-124">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="c3c28-124">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="c3c28-125">[Gestion des comptes fournisseur](payables-manage-payables.md)  </span><span class="sxs-lookup"><span data-stu-id="c3c28-125">[Managing Payables](payables-manage-payables.md)  </span></span>  
<span data-ttu-id="c3c28-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="c3c28-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="c3c28-127">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="c3c28-127">General Business Functionality</span></span>](ui-across-business-areas.md)  
