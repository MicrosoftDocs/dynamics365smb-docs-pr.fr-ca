---
title: "Transférer des fonds à la banque| Microsoft Docs"
description: "Vous pouvez transférer des montants d'un compte bancaire à un autre, y compris dans différentes devises, en reportant la transaction dans le journal général."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account transfer, multiple currencies
ms.date: 06/02/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 54e8a7bf7ca8761d6317b57d45e64f9ee628f4b8
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="transfer-bank-funds"></a><span data-ttu-id="fb82a-103">Transfert de fonds à la banque</span><span class="sxs-lookup"><span data-stu-id="fb82a-103">Transfer Bank Funds</span></span>
<span data-ttu-id="fb82a-104">Vous pouvez avoir à transférer un montant d'un compte bancaire à un autre.</span><span class="sxs-lookup"><span data-stu-id="fb82a-104">You may sometimes need to transfer an amount from one bank account to another.</span></span> <span data-ttu-id="fb82a-105">Pour cela, vous devez reporter une transaction dans le journal général.</span><span class="sxs-lookup"><span data-stu-id="fb82a-105">To do this, you must post the a transaction in the general journal.</span></span> <span data-ttu-id="fb82a-106">La tâche varie selon que les comptes bancaires utilisent la même devise ou des devises différentes.</span><span class="sxs-lookup"><span data-stu-id="fb82a-106">The task varies depending on whether the bank accounts use the same currency or different currencies.</span></span>

## <a name="to-post-a-transfer-between-bank-accounts-with-the-same-currency-code"></a><span data-ttu-id="fb82a-107">Pour reporter un transfert entre comptes bancaires avec le même code devise</span><span class="sxs-lookup"><span data-stu-id="fb82a-107">To post a transfer between bank accounts with the same currency code</span></span>
1. <span data-ttu-id="fb82a-108">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille comptabilité**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="fb82a-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="fb82a-109">Dans une ligne journal, renseignez les champs **Date de report** et **N° document** .</span><span class="sxs-lookup"><span data-stu-id="fb82a-109">On a journal line, fill in the **Posting Date** and **Document No.** fields.</span></span>
3. <span data-ttu-id="fb82a-110">Cliquez sur le champ **Type compte**, sélectionnez le **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-110">In the **Account Type** field, select **Bank Account**.</span></span>
4. <span data-ttu-id="fb82a-111">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-111">In the **Account No.** field, select the bank from which you want to transfer the funds.</span></span>
5. <span data-ttu-id="fb82a-112">Dans le champ **Montant**, entrez le total à transférer.</span><span class="sxs-lookup"><span data-stu-id="fb82a-112">In the **Amount** field, enter the amount to be transferred.</span></span>
6. <span data-ttu-id="fb82a-113">Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-113">In the **Bal. Account Type** field, select **Bank Account**.</span></span>
7. <span data-ttu-id="fb82a-114">Dans le champ **N° compte contrepartie**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-114">In the **Bal. Account No.** field, select the bank account to which you want to transfer the funds.</span></span>
8. <span data-ttu-id="fb82a-115">Reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="fb82a-115">Post the journal.</span></span>

## <a name="to-post-a-transfer-between-bank-accounts-with-different-currency-codes"></a><span data-ttu-id="fb82a-116">Pour reporter des transferts entre comptes bancaires dotés de codes devise différents</span><span class="sxs-lookup"><span data-stu-id="fb82a-116">To post a transfer between bank accounts with different currency codes</span></span>
<span data-ttu-id="fb82a-117">Pour transférer des fonds entre des comptes bancaires qui utilisent des devises différentes, vous devez reporter deux lignes journal général.</span><span class="sxs-lookup"><span data-stu-id="fb82a-117">To transfer funds between bank accounts that use different currencies, you must post two general journal lines.</span></span>

1. <span data-ttu-id="fb82a-118">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille comptabilité**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="fb82a-118">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="fb82a-119">Créez deux lignes journal, et renseignez les champs **Date de report** et **N° document**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-119">Create two journal lines, and fill in the **Posting Date** and **Document No.** fields.</span></span>
3. <span data-ttu-id="fb82a-120">Sur la première ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-120">On the first journal line, in the **Type** field, select **Bank Account**.</span></span>
4. <span data-ttu-id="fb82a-121">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-121">In the **Account No.** field, select the bank account from which you want to transfer the funds.</span></span>
5. <span data-ttu-id="fb82a-122">Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="fb82a-122">In the **Amount** field, enter the amount in the currency of the bank account.</span></span> <span data-ttu-id="fb82a-123">Entrez les montants de crédit précédés du signe moins.</span><span class="sxs-lookup"><span data-stu-id="fb82a-123">Enter credit amounts with a minus sign.</span></span> <span data-ttu-id="fb82a-124">Entrez les montants de débit sans signe moins.</span><span class="sxs-lookup"><span data-stu-id="fb82a-124">Enter debit amounts without a minus sign.</span></span>
6. <span data-ttu-id="fb82a-125">Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-125">In the **Bal. Account Type** field, select **Bank Account**.</span></span>
7. <span data-ttu-id="fb82a-126">Dans le champ **N° compte contrepartie**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-126">In the **Bal. Account No.** field, select the bank account to which you want to transfer the funds.</span></span>
8. <span data-ttu-id="fb82a-127">Sur la seconde ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-127">On the second journal line, in the **Type** field, select **Bank Account**.</span></span>
9. <span data-ttu-id="fb82a-128">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-128">In the **Account No.** field, select the bank account to which you want to transfer the funds.</span></span>
10. <span data-ttu-id="fb82a-129">Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="fb82a-129">In the **Amount** field, enter the amount in the currency of the bank account.</span></span> <span data-ttu-id="fb82a-130">Entrez les montants de crédit précédés du signe moins.</span><span class="sxs-lookup"><span data-stu-id="fb82a-130">Enter credit amounts with a minus sign.</span></span> <span data-ttu-id="fb82a-131">Entrez les montants de débit sans signe moins.</span><span class="sxs-lookup"><span data-stu-id="fb82a-131">Enter debit amounts without a minus sign.</span></span>
11. <span data-ttu-id="fb82a-132">Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-132">In the **Bal. Account Type** field, select **Bank Account**.</span></span>  
12. <span data-ttu-id="fb82a-133">Dans le champ **N° compte contrepartie**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="fb82a-133">In the **Bal. Account No.** field, select the bank account from which you want to transfer the funds.</span></span>

    > [!NOTE]  
>   <span data-ttu-id="fb82a-134">Si les taux de change utilisés dans la feuille sont différents des taux de change qui s'affichent dans la fenêtre **Taux de change devise**, entrez alors une troisième ligne pour les pertes ou gains liés au taux de change.</span><span class="sxs-lookup"><span data-stu-id="fb82a-134">If the exchange rates used in the journal are different than the exchange rates in the **Currency Exchange Rates** window, enter a third line for the exchange rate gain or loss.</span></span> <span data-ttu-id="fb82a-135">Entrez **Compte général** dans le champ **Type compte**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-135">Enter **G/L Account** in the **Account Type** field.</span></span> <span data-ttu-id="fb82a-136">Entrez le numéro de compte du grand livre pour les gains ou les pertes liés au taux de change dans le champ **N° compte**.</span><span class="sxs-lookup"><span data-stu-id="fb82a-136">Enter the G/L account number for exchange rate gain or loss in the **Account No.** field.</span></span> <span data-ttu-id="fb82a-137">Saisissez les gains ou les pertes liés au taux de change dans le champ **Montant** avec ou sans signe moins pour les crédits et les débits, respectivement.</span><span class="sxs-lookup"><span data-stu-id="fb82a-137">Enter the exchange rate gain or loss in the **Amount** field with or without a minus sign for credits and debits respectively.</span></span>
13. <span data-ttu-id="fb82a-138">Reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="fb82a-138">Post the journal.</span></span>

## <a name="see-also"></a><span data-ttu-id="fb82a-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fb82a-139">See Also</span></span>
[<span data-ttu-id="fb82a-140">Gestion des comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="fb82a-140">Managing Bank Accounts</span></span>](bank-manage-bank-accounts.md)  
[<span data-ttu-id="fb82a-141">Paramétrage des opérations bancaires</span><span class="sxs-lookup"><span data-stu-id="fb82a-141">Setting Up Banking</span></span>](bank-setup-banking.md)  
[<span data-ttu-id="fb82a-142">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="fb82a-142">Working with General Journals</span></span>](ui-work-general-journals.md)  
<span data-ttu-id="fb82a-143">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="fb82a-143">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
