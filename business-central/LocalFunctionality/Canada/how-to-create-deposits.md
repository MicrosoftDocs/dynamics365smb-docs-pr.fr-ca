---
title: 'Procédure : créer des dépôts | Microsoft Docs'
description: Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 2c9649ed540c5ce44882a55d4fa0bea689f03036
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3180843"
---
# <a name="create-deposits"></a><span data-ttu-id="87834-103">Créer des dépôts</span><span class="sxs-lookup"><span data-stu-id="87834-103">Create Deposits</span></span>
<span data-ttu-id="87834-104">Vous pouvez créer des dépôts pour tenir à jour un enregistrement de transaction contenant des renseignements pouvant être appliqués aux notes de crédit et factures en attente.</span><span class="sxs-lookup"><span data-stu-id="87834-104">You can make deposits to maintain a transaction record that contains information that can be applied to outstanding invoices and credit memos.</span></span>  

## <a name="to-create-a-deposit"></a><span data-ttu-id="87834-105">Pour créer un dépôt</span><span class="sxs-lookup"><span data-stu-id="87834-105">To create a deposit</span></span>  
1.  <span data-ttu-id="87834-106">Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "Icône Page ou rapport pour la recherche"), entrez **Dépôts**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="87834-106">Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Deposits**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="87834-107">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="87834-107">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="87834-108">Sous le raccourci **Général**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="87834-108">On the **General** FastTab, fill in the required fields as described in the following table.</span></span>  

    |<span data-ttu-id="87834-109">Champ</span><span class="sxs-lookup"><span data-stu-id="87834-109">Field</span></span>|<span data-ttu-id="87834-110">Description</span><span class="sxs-lookup"><span data-stu-id="87834-110">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="87834-111">**N°**</span><span class="sxs-lookup"><span data-stu-id="87834-111">**No.**</span></span>|<span data-ttu-id="87834-112">Numéro d'identification unique du dépôt.</span><span class="sxs-lookup"><span data-stu-id="87834-112">The unique identification number for the deposit.</span></span>|  
    |<span data-ttu-id="87834-113">**N° de compte bancaire**</span><span class="sxs-lookup"><span data-stu-id="87834-113">**Bank Account No.**</span></span>|<span data-ttu-id="87834-114">Numéro de compte bancaire pour le dépôt.</span><span class="sxs-lookup"><span data-stu-id="87834-114">The bank account number for the deposit.</span></span>|  
    |<span data-ttu-id="87834-115">**Montant total de dépôt**</span><span class="sxs-lookup"><span data-stu-id="87834-115">**Total Deposit Amount**</span></span>|<span data-ttu-id="87834-116">Montant total du dépôt reporté sur le grand livre bancaire.</span><span class="sxs-lookup"><span data-stu-id="87834-116">The total deposit amount posted to the bank ledger.</span></span><br /><br /> <span data-ttu-id="87834-117">Vous pouvez reporter ce dépôt uniquement si la somme des lignes dépôt est égale à la valeur de ce champ.</span><span class="sxs-lookup"><span data-stu-id="87834-117">You can post this deposit only if the sum of the deposit lines is equal to the value in this field.</span></span>|  
    |<span data-ttu-id="87834-118">**Date de report**</span><span class="sxs-lookup"><span data-stu-id="87834-118">**Posting Date**</span></span>|<span data-ttu-id="87834-119">Date de report du dépôt.</span><span class="sxs-lookup"><span data-stu-id="87834-119">The posting date for the deposit.</span></span>|  
    |<span data-ttu-id="87834-120">**Date du document**</span><span class="sxs-lookup"><span data-stu-id="87834-120">**Document Date**</span></span>|<span data-ttu-id="87834-121">Date du document du dépôt.</span><span class="sxs-lookup"><span data-stu-id="87834-121">The deposit document date.</span></span>|  
4.  <span data-ttu-id="87834-122">Sous le raccourci **Lignes**, renseignez les champs requis comme indiqué dans le tableau ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="87834-122">On the **Lines** FastTab, fill in the required fields as described in the following table.</span></span>  

    |<span data-ttu-id="87834-123">Champ</span><span class="sxs-lookup"><span data-stu-id="87834-123">Field</span></span>|<span data-ttu-id="87834-124">Description</span><span class="sxs-lookup"><span data-stu-id="87834-124">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="87834-125">**Type compte**</span><span class="sxs-lookup"><span data-stu-id="87834-125">**Account Type**</span></span>|<span data-ttu-id="87834-126">Type de compte.</span><span class="sxs-lookup"><span data-stu-id="87834-126">The account type.</span></span>|  
    |<span data-ttu-id="87834-127">**N° compte**</span><span class="sxs-lookup"><span data-stu-id="87834-127">**Account No.**</span></span>|<span data-ttu-id="87834-128">Numéro de compte d'identification unique associé au type de compte sélectionné, sur lequel l'écriture sera reportée.</span><span class="sxs-lookup"><span data-stu-id="87834-128">The unique identification account number that is associated with the selected account type, to which the entry will be posted.</span></span>|  
    |<span data-ttu-id="87834-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="87834-129">**Description**</span></span>|<span data-ttu-id="87834-130">Description de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="87834-130">The journal line entry description.</span></span>|  
    |<span data-ttu-id="87834-131">**Date du document**</span><span class="sxs-lookup"><span data-stu-id="87834-131">**Document Date**</span></span>|<span data-ttu-id="87834-132">Date de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="87834-132">The journal line entry document date.</span></span>|  
    |<span data-ttu-id="87834-133">**Type document**</span><span class="sxs-lookup"><span data-stu-id="87834-133">**Document Type**</span></span>|<span data-ttu-id="87834-134">Type de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="87834-134">The journal line entry document type.</span></span>|  
    |<span data-ttu-id="87834-135">**N° du document**</span><span class="sxs-lookup"><span data-stu-id="87834-135">**Document No.**</span></span>|<span data-ttu-id="87834-136">Numéro de document de l'écriture ligne journal.</span><span class="sxs-lookup"><span data-stu-id="87834-136">The journal line entry document number.</span></span>|  
    |<span data-ttu-id="87834-137">**Montant crédit**</span><span class="sxs-lookup"><span data-stu-id="87834-137">**Credit Amount**</span></span>|<span data-ttu-id="87834-138">Montant total du crédit sur la ligne journal.</span><span class="sxs-lookup"><span data-stu-id="87834-138">The total credit amount on the journal line.</span></span>|  

5.  <span data-ttu-id="87834-139">Éventuellement, choisissez l'action **Dimensions**, puis ajoutez les dimensions correspondantes sur la page **Écritures de l'ensemble de dimensions**.</span><span class="sxs-lookup"><span data-stu-id="87834-139">Optionally, choose the **Dimensions** action, and then add relevant dimensions on the **Dimension Set Entries** page.</span></span>  

<span data-ttu-id="87834-140">Après avoir créé un dépôt, vous devez le reporter.</span><span class="sxs-lookup"><span data-stu-id="87834-140">After you have created a deposit, you must post it.</span></span>  

## <a name="to-post-a-deposit"></a><span data-ttu-id="87834-141">Reporter un dépôt</span><span class="sxs-lookup"><span data-stu-id="87834-141">To post a deposit</span></span>  
1. <span data-ttu-id="87834-142">Sélectionnez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="87834-142">Choose the **Post** action.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="87834-143">Vous pouvez reporter un dépôt uniquement si le montant affiché dans le champ **Lignes de dépôt total** est égal au montant figurant dans le champ **Montant total de dépôt**.</span><span class="sxs-lookup"><span data-stu-id="87834-143">You can post a deposit only if the amount displayed in the **Total Deposit Lines** field is equal to the amount in the **Total Deposit Amount** field.</span></span>  

<span data-ttu-id="87834-144">Ensuite, vous pouvez utiliser le rapport Test des dépôts et les rapports Dépôt pour rapprocher vos dépôts reportés avec vos notes de crédit et factures en attente.</span><span class="sxs-lookup"><span data-stu-id="87834-144">Next, you can use the Deposit Test Report and Deposit reports to reconcile your posted deposits with outstanding invoices and credit memos.</span></span>  

## <a name="see-also"></a><span data-ttu-id="87834-145">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="87834-145">See Also</span></span>  
[<span data-ttu-id="87834-146">Fonctionnalités locales Canada</span><span class="sxs-lookup"><span data-stu-id="87834-146">Canada Local Functionality</span></span>](canada-local-functionality.md)  
[<span data-ttu-id="87834-147">Finance</span><span class="sxs-lookup"><span data-stu-id="87834-147">Finance</span></span>](../../finance.md)  
[<span data-ttu-id="87834-148">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="87834-148">Setting Up Finance</span></span>](../../finance.md)  
