---
title: Transfert de fonds à la banque
description: Vous pouvez transférer des montants d'un compte bancaire à un autre, y compris dans différentes devises, en reportant la transaction dans le journal général.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bank account transfer, multiple currencies
ms.date: 04/29/2021
ms.author: edupont
ms.openlocfilehash: da9c8711751040cecb267a3b2209bad2534b618b
ms.sourcegitcommit: 08ca5798cf3f04fc3ea38fff40c1860196a70adf
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/06/2021
ms.locfileid: "5985397"
---
# <a name="transfer-bank-funds"></a><span data-ttu-id="0774b-103">Transfert de fonds à la banque</span><span class="sxs-lookup"><span data-stu-id="0774b-103">Transfer Bank Funds</span></span>

<span data-ttu-id="0774b-104">Il peut vous arriver de devoir transférer un montant d'un compte bancaire dans [!INCLUDE[prod_short](includes/prod_short.md)] vers un autre.</span><span class="sxs-lookup"><span data-stu-id="0774b-104">You may sometimes need to transfer an amount from one bank account in [!INCLUDE[prod_short](includes/prod_short.md)] to another.</span></span> <span data-ttu-id="0774b-105">Pour ce faire, vous devez reporter la transaction sur la page **Journal général**.</span><span class="sxs-lookup"><span data-stu-id="0774b-105">To do this, you must post the transaction on the **General Journal** page.</span></span> <span data-ttu-id="0774b-106">La tâche varie selon que les comptes bancaires utilisent la même devise ou des devises différentes.</span><span class="sxs-lookup"><span data-stu-id="0774b-106">The task varies depending on whether the bank accounts use the same currency or different currencies.</span></span>

## <a name="to-post-a-transfer-between-bank-accounts-with-the-same-currency-code"></a><span data-ttu-id="0774b-107">Pour reporter un transfert entre comptes bancaires avec le même code devise</span><span class="sxs-lookup"><span data-stu-id="0774b-107">To post a transfer between bank accounts with the same currency code</span></span>

1. <span data-ttu-id="0774b-108">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal général**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0774b-108">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="0774b-109">Dans une ligne journal, renseignez les champs **Date de report** et **N° document** .</span><span class="sxs-lookup"><span data-stu-id="0774b-109">On a journal line, fill in the **Posting Date** and **Document No.** fields.</span></span>
3. <span data-ttu-id="0774b-110">Cliquez sur le champ **Type compte**, sélectionnez le **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="0774b-110">In the **Account Type** field, select **Bank Account**.</span></span>
4. <span data-ttu-id="0774b-111">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="0774b-111">In the **Account No.** field, select the bank from which you want to transfer the funds.</span></span>
5. <span data-ttu-id="0774b-112">Dans le champ **Montant**, entrez le total à transférer.</span><span class="sxs-lookup"><span data-stu-id="0774b-112">In the **Amount** field, enter the amount to be transferred.</span></span>

    <span data-ttu-id="0774b-113">Ensuite, vous devez spécifier le compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="0774b-113">Next, you must specify the balancing account.</span></span> <span data-ttu-id="0774b-114">Si vous ne visualisez pas les champs appropriés, choisissez l′action **Afficher plus de colonnes** pour afficher tous les champs disponibles.</span><span class="sxs-lookup"><span data-stu-id="0774b-114">If you can't see the relevant fields, then choose the **Show More Columns** action to view all available fields.</span></span>
6. <span data-ttu-id="0774b-115">Dans le champ **Type compte contrepartie**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="0774b-115">In the **Bal. Account Type** field, select **Bank Account**.</span></span>
7. <span data-ttu-id="0774b-116">Dans le champ **N° compte contrepartie**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="0774b-116">In the **Bal. Account No.** field, select the bank account to which you want to transfer the funds.</span></span>
8. <span data-ttu-id="0774b-117">Reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="0774b-117">Post the journal.</span></span>

## <a name="to-post-a-transfer-between-bank-accounts-with-different-currency-codes"></a><span data-ttu-id="0774b-118">Pour reporter des transferts entre comptes bancaires dotés de codes devise différents</span><span class="sxs-lookup"><span data-stu-id="0774b-118">To post a transfer between bank accounts with different currency codes</span></span>

<span data-ttu-id="0774b-119">Pour transférer des fonds entre des comptes bancaires qui utilisent des devises différentes, vous devez reporter deux lignes journal général.</span><span class="sxs-lookup"><span data-stu-id="0774b-119">To transfer funds between bank accounts that use different currencies, you must post two general journal lines.</span></span>

1. <span data-ttu-id="0774b-120">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal général**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0774b-120">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="0774b-121">Créez deux lignes journal, et renseignez les champs **Date de report** et **N° document**.</span><span class="sxs-lookup"><span data-stu-id="0774b-121">Create two journal lines, and fill in the **Posting Date** and **Document No.** fields.</span></span>
3. <span data-ttu-id="0774b-122">Sur la première ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="0774b-122">On the first journal line, in the **Type** field, select **Bank Account**.</span></span>
4. <span data-ttu-id="0774b-123">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="0774b-123">In the **Account No.** field, select the bank account from which you want to transfer the funds.</span></span>
5. <span data-ttu-id="0774b-124">Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire avec ou sans signe moins.</span><span class="sxs-lookup"><span data-stu-id="0774b-124">In the **Amount** field, enter the amount in the currency of the bank account with or without a minus sign.</span></span>

    > [!TIP]
    > <span data-ttu-id="0774b-125">Un montant sans signe est un débit et un montant avec un signe moins est un crédit.</span><span class="sxs-lookup"><span data-stu-id="0774b-125">An amount without a sign is a debit, and an amount with a minus sign is a credit.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0774b-126">Certaines compagnies préfèrent effectuer des transferts entre comptes sur des lignes journal distinctes.</span><span class="sxs-lookup"><span data-stu-id="0774b-126">Some companies prefer to transfer between accounts on separate journal lines.</span></span> <span data-ttu-id="0774b-127">D′autres compagnies préfèrent tout reporter sur une seule ligne journal en utilisant un compte de contrepartie.</span><span class="sxs-lookup"><span data-stu-id="0774b-127">Other companies prefer to post everything on one journal line by using a balancing account.</span></span> <span data-ttu-id="0774b-128">Consultez votre expert local si vous ne savez pas quoi faire.</span><span class="sxs-lookup"><span data-stu-id="0774b-128">Check with your local expert if you're not sure what to do.</span></span>
    >
    > <span data-ttu-id="0774b-129">Si votre compagnie préfère utiliser un compte de contrepartie, définissez le champ **Type compte de contrepartie** sur **Compte bancaire** et définissez le champ **N° compte de contrepartie** sur le compte bancaire sur lequel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="0774b-129">If your company prefers to use a balancing account, then set the **Bal. Account Type** field to **Bank Account**, and set the **Bal. Account No.** field to the bank account to which you want to transfer the funds.</span></span> <span data-ttu-id="0774b-130">Passez ensuite à l′étape 9 ou 10.</span><span class="sxs-lookup"><span data-stu-id="0774b-130">Then proceed to step 9 or 10.</span></span>
    >
    > <span data-ttu-id="0774b-131">Si votre compagnie préfère utiliser une ligne journal distincte, passez à l′étape suivante.</span><span class="sxs-lookup"><span data-stu-id="0774b-131">If your company prefers to use a separate journal line, then move on to the next step.</span></span>
6. <span data-ttu-id="0774b-132">Sur la seconde ligne feuille, dans le champ **Type**, sélectionnez **Compte bancaire**.</span><span class="sxs-lookup"><span data-stu-id="0774b-132">On the second journal line, in the **Type** field, select **Bank Account**.</span></span>
7. <span data-ttu-id="0774b-133">Dans le champ **N° compte**, sélectionnez le compte bancaire à partir duquel vous souhaitez transférer les fonds.</span><span class="sxs-lookup"><span data-stu-id="0774b-133">In the **Account No.** field, select the bank account to which you want to transfer the funds.</span></span>
8. <span data-ttu-id="0774b-134">Dans le champ **Montant**, saisissez le montant dans la devise du compte bancaire avec ou sans signe moins.</span><span class="sxs-lookup"><span data-stu-id="0774b-134">In the **Amount** field, enter the amount in the currency of the bank account with or without a minus sign.</span></span>

    > [!TIP]
    > <span data-ttu-id="0774b-135">Un montant sans signe est un débit et un montant avec un signe moins est un crédit.</span><span class="sxs-lookup"><span data-stu-id="0774b-135">An amount without a sign is a debit, and an amount with a minus sign is a credit.</span></span>
9. <span data-ttu-id="0774b-136">Si les taux de change utilisés dans le journal sont différents des taux de change de la page **Taux de change devise**, saisissez une nouvelle ligne journal pour les pertes ou les gains sur taux de change.</span><span class="sxs-lookup"><span data-stu-id="0774b-136">If the exchange rates used in the journal are different than the exchange rates on the **Currency Exchange Rates** page, enter a new journal line for the exchange rate gain or loss.</span></span>  

    1. <span data-ttu-id="0774b-137">Entrez **Compte général** dans le champ **Type compte**.</span><span class="sxs-lookup"><span data-stu-id="0774b-137">Enter **G/L Account** in the **Account Type** field.</span></span>  

    2. <span data-ttu-id="0774b-138">Entrez le numéro de compte du grand livre pour les gains ou les pertes liés au taux de change dans le champ **N° compte**.</span><span class="sxs-lookup"><span data-stu-id="0774b-138">Enter the G/L account number for exchange rate gain or loss in the **Account No.** field.</span></span>  

    3. <span data-ttu-id="0774b-139">Saisissez le gain ou la perte sur taux de change dans le champ **Montant** avec ou sans signe moins.</span><span class="sxs-lookup"><span data-stu-id="0774b-139">Enter the exchange rate gain or loss in the **Amount** field with or without a minus sign.</span></span>

    > [!TIP]
    > <span data-ttu-id="0774b-140">Un montant sans signe est un débit et un montant avec un signe moins est un crédit.</span><span class="sxs-lookup"><span data-stu-id="0774b-140">An amount without a sign is a debit, and an amount with a minus sign is a credit.</span></span>
10. <span data-ttu-id="0774b-141">Reportez le journal.</span><span class="sxs-lookup"><span data-stu-id="0774b-141">Post the journal.</span></span>

## <a name="see-also"></a><span data-ttu-id="0774b-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0774b-142">See Also</span></span>

[<span data-ttu-id="0774b-143">Rapprochement de comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="0774b-143">Reconciling Bank Accounts</span></span>](bank-manage-bank-accounts.md)  
[<span data-ttu-id="0774b-144">Paramétrage des opérations bancaires</span><span class="sxs-lookup"><span data-stu-id="0774b-144">Setting Up Banking</span></span>](bank-setup-banking.md)  
[<span data-ttu-id="0774b-145">Utilisation de journaux généraux</span><span class="sxs-lookup"><span data-stu-id="0774b-145">Working with General Journals</span></span>](ui-work-general-journals.md)  
<span data-ttu-id="0774b-146">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="0774b-146">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]