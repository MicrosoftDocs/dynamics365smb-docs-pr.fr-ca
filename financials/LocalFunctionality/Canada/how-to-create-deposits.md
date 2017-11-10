---
title: "Procédure : créer des dépôts | Microsoft Docs"
description: "Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 2c585c1db897667bd43933f4d28b252e3630e6df
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-create-deposits"></a><span data-ttu-id="8c847-103">Procédure : créer des dépôts</span><span class="sxs-lookup"><span data-stu-id="8c847-103">How to: Create Deposits</span></span>
<span data-ttu-id="8c847-104">Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.</span><span class="sxs-lookup"><span data-stu-id="8c847-104">You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.</span></span>  

## <a name="to-create-a-deposit"></a><span data-ttu-id="8c847-105">Pour créer un dépôt</span><span class="sxs-lookup"><span data-stu-id="8c847-105">To create a deposit</span></span>  
1.  <span data-ttu-id="8c847-106">Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Dépôts**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8c847-106">Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Deposits**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="8c847-107">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="8c847-107">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="8c847-108">Sous le raccourci **Général**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8c847-108">On the **General** FastTab, fill in the required fields as described in the following table.</span></span>  

    |<span data-ttu-id="8c847-109">Champ</span><span class="sxs-lookup"><span data-stu-id="8c847-109">Field</span></span>|<span data-ttu-id="8c847-110">Description</span><span class="sxs-lookup"><span data-stu-id="8c847-110">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="8c847-111">**N°**</span><span class="sxs-lookup"><span data-stu-id="8c847-111">**No.**</span></span>|<span data-ttu-id="8c847-112">Numéro d'identification unique du dépôt.</span><span class="sxs-lookup"><span data-stu-id="8c847-112">The unique identification number for the deposit.</span></span>|  
    |<span data-ttu-id="8c847-113">**N° de compte bancaire**</span><span class="sxs-lookup"><span data-stu-id="8c847-113">**Bank Account No.**</span></span>|<span data-ttu-id="8c847-114">Numéro de compte bancaire pour le dépôt.</span><span class="sxs-lookup"><span data-stu-id="8c847-114">The bank account number for the deposit.</span></span>|  
    |<span data-ttu-id="8c847-115">**Montant total de dépôt**</span><span class="sxs-lookup"><span data-stu-id="8c847-115">**Total Deposit Amount**</span></span>|<span data-ttu-id="8c847-116">Montant total du dépôt reporté sur le grand livre bancaire.</span><span class="sxs-lookup"><span data-stu-id="8c847-116">The total deposit amount posted to the bank ledger.</span></span><br /><br /> <span data-ttu-id="8c847-117">Vous pouvez reporter ce dépôt uniquement si la somme des lignes dépôt est égale à la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="8c847-117">You can post this deposit only if the sum of the deposit lines is equal to the value in this field.</span></span>|  
    |<span data-ttu-id="8c847-118">**Date de report**</span><span class="sxs-lookup"><span data-stu-id="8c847-118">**Posting Date**</span></span>|<span data-ttu-id="8c847-119">Date de report du dépôt.</span><span class="sxs-lookup"><span data-stu-id="8c847-119">The posting date for the deposit.</span></span>|  
    |<span data-ttu-id="8c847-120">**Date du document**</span><span class="sxs-lookup"><span data-stu-id="8c847-120">**Document Date**</span></span>|<span data-ttu-id="8c847-121">Date du document du dépôt.</span><span class="sxs-lookup"><span data-stu-id="8c847-121">The deposit document date.</span></span>|  
4.  <span data-ttu-id="8c847-122">Sous le raccourci **Lignes**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="8c847-122">On the **Lines** FastTab, fill in the required fields as described in the following table.</span></span>  

    |<span data-ttu-id="8c847-123">Champ</span><span class="sxs-lookup"><span data-stu-id="8c847-123">Field</span></span>|<span data-ttu-id="8c847-124">Description</span><span class="sxs-lookup"><span data-stu-id="8c847-124">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="8c847-125">**Type compte**</span><span class="sxs-lookup"><span data-stu-id="8c847-125">**Account Type**</span></span>|<span data-ttu-id="8c847-126">Type de compte.</span><span class="sxs-lookup"><span data-stu-id="8c847-126">The account type.</span></span>|  
    |<span data-ttu-id="8c847-127">**N° compte**</span><span class="sxs-lookup"><span data-stu-id="8c847-127">**Account No.**</span></span>|<span data-ttu-id="8c847-128">Numéro de compte d'identification unique associé au type de compte sélectionné, sur lequel l'écriture sera reportée.</span><span class="sxs-lookup"><span data-stu-id="8c847-128">The unique identification account number that is associated with the selected account type, to which the entry will be posted.</span></span>|  
    |<span data-ttu-id="8c847-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="8c847-129">**Description**</span></span>|<span data-ttu-id="8c847-130">Description de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="8c847-130">The journal line entry description.</span></span>|  
    |<span data-ttu-id="8c847-131">**Date du document**</span><span class="sxs-lookup"><span data-stu-id="8c847-131">**Document Date**</span></span>|<span data-ttu-id="8c847-132">Date de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="8c847-132">The journal line entry document date.</span></span>|  
    |<span data-ttu-id="8c847-133">**Type document**</span><span class="sxs-lookup"><span data-stu-id="8c847-133">**Document Type**</span></span>|<span data-ttu-id="8c847-134">Type de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="8c847-134">The journal line entry document type.</span></span>|  
    |<span data-ttu-id="8c847-135">**N° du document**</span><span class="sxs-lookup"><span data-stu-id="8c847-135">**Document No.**</span></span>|<span data-ttu-id="8c847-136">Numéro de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="8c847-136">The journal line entry document number.</span></span>|  
    |<span data-ttu-id="8c847-137">**Montant crédit**</span><span class="sxs-lookup"><span data-stu-id="8c847-137">**Credit Amount**</span></span>|<span data-ttu-id="8c847-138">Montant total du crédit sur la ligne journal.</span><span class="sxs-lookup"><span data-stu-id="8c847-138">The total credit amount on the journal line.</span></span>|  

5.  <span data-ttu-id="8c847-139">Éventuellement, sous l'onglet **Naviguer**, choisissez **Dimensions**, puis ajoutez les dimensions correspondantes dans la fenêtre **Écritures de l'ensemble de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="8c847-139">Optionally, on the **Navigate** tab, choose **Dimensions**, and then add relevant dimensions in the **Dimension Set Entries** window.</span></span>  

<span data-ttu-id="8c847-140">Après avoir créé un dépôt, vous devez le reporter.</span><span class="sxs-lookup"><span data-stu-id="8c847-140">After you have created a deposit, you must post it.</span></span>  

## <a name="to-post-a-deposit"></a><span data-ttu-id="8c847-141">Reporter un dépôt</span><span class="sxs-lookup"><span data-stu-id="8c847-141">To post a deposit</span></span>  
1. <span data-ttu-id="8c847-142">Sélectionnez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8c847-142">Choose the **Post** action.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="8c847-143">Vous pouvez reporter un dépôt uniquement si le montant affiché dans le champ **Lignes de dépôt total** est égal au montant figurant dans le champ **Montant total de dépôt**.</span><span class="sxs-lookup"><span data-stu-id="8c847-143">You can post a deposit only if the amount displayed in the **Total Deposit Lines** field is equal to the amount in the **Total Deposit Amount** field.</span></span>  

<span data-ttu-id="8c847-144">Ensuite, vous pouvez utiliser le rapport Test des dépôts et les rapports Dépôt pour rapprocher vos dépôts reportés avec vos notes de crédit et factures en attente.</span><span class="sxs-lookup"><span data-stu-id="8c847-144">Next, you can use the Deposit Test Report and Deposit reports to reconcile your posted deposits with outstanding invoices and credit memos.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8c847-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8c847-145">See Also</span></span>  
[<span data-ttu-id="8c847-146">Fonctionnalités locales Canada</span><span class="sxs-lookup"><span data-stu-id="8c847-146">Canada Local Functionality</span></span>](canada-local-functionality.md)  
[<span data-ttu-id="8c847-147">Finance</span><span class="sxs-lookup"><span data-stu-id="8c847-147">Finance</span></span>](../../finance.md)  
[<span data-ttu-id="8c847-148">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="8c847-148">Setting Up Finance</span></span>](../../finance.md)  
