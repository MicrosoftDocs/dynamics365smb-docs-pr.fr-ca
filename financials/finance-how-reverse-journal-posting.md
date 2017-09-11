---
title: "Annuler un report journal en reportant une écriture de contrepassation| Microsoft Docs"
description: "Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 06/15/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 8126a53d59e72276eb1558fd65fe3c0cd53600cc
ms.contentlocale: fr-ca
ms.lasthandoff: 09/11/2017

---
# <a name="how-to-reverse-journal-posting"></a><span data-ttu-id="42a86-103">Procédure : inverser un report journal</span><span class="sxs-lookup"><span data-stu-id="42a86-103">How to: Reverse Journal Posting</span></span>
<span data-ttu-id="42a86-104">Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine.</span><span class="sxs-lookup"><span data-stu-id="42a86-104">To undo an erroneous journal posting, you select the entry and create a reverse entry (entries identical to the original entry but with opposite sign in the amount field) with the same document number and posting date as the original entry.</span></span> <span data-ttu-id="42a86-105">Une fois l'écriture inversée, créez l'écriture correcte.</span><span class="sxs-lookup"><span data-stu-id="42a86-105">After reversing an entry, you must make the correct entry.</span></span>

<span data-ttu-id="42a86-106">Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général.</span><span class="sxs-lookup"><span data-stu-id="42a86-106">You can only reverse entries that are posted from a general journal line.</span></span> <span data-ttu-id="42a86-107">Une écriture ne peut être inversée qu'une seule fois.</span><span class="sxs-lookup"><span data-stu-id="42a86-107">An entry can only be reversed once.</span></span>

<span data-ttu-id="42a86-108">Pour plus d'informations sur la validation d'une feuille comptabilité, voir [Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md).</span><span class="sxs-lookup"><span data-stu-id="42a86-108">For more information about posting from a general journal, see [How to: Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).</span></span>

<span data-ttu-id="42a86-109">Vous pouvez inverser des écritures dans toutes les fenêtres **Écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="42a86-109">You can reverse entries from all **Ledger Entries** windows.</span></span> <span data-ttu-id="42a86-110">La procédure suivante se base sur la fenêtre **Écritures comptables**.</span><span class="sxs-lookup"><span data-stu-id="42a86-110">The following procedure is based on the **General Ledger Entries** window.</span></span>

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a><span data-ttu-id="42a86-111">Pour inverser le report journal d'une écriture grand livre</span><span class="sxs-lookup"><span data-stu-id="42a86-111">To reverse the journal posting of a general ledger entry</span></span>
1. <span data-ttu-id="42a86-112">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ecritures comptables**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="42a86-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Ledger Entries**, and then choose the related link.</span></span>
2. <span data-ttu-id="42a86-113">Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**.</span><span class="sxs-lookup"><span data-stu-id="42a86-113">Select the entry that you want to reverse, and then choose the **Reverse Transaction** action.</span></span> <span data-ttu-id="42a86-114">Notez qu'elle doit provenir d'un report journal.</span><span class="sxs-lookup"><span data-stu-id="42a86-114">Note that is must originate from a journal posting.</span></span>
3. <span data-ttu-id="42a86-115">Dans la fenêtre **Contrepasser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Contrepasser**.</span><span class="sxs-lookup"><span data-stu-id="42a86-115">In the **Reverse Transaction Entries** window, select the relevant entry, and then choose the **Reverse** action.</span></span>
4. <span data-ttu-id="42a86-116">Choisissez le bouton **Oui** dans le message de confirmation.</span><span class="sxs-lookup"><span data-stu-id="42a86-116">Choose the **Yes** button on the confirmation message.</span></span>

## <a name="see-also"></a><span data-ttu-id="42a86-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="42a86-117">See Also</span></span>
[<span data-ttu-id="42a86-118">Procédure : Valider les transactions directement vers la comptabilité</span><span class="sxs-lookup"><span data-stu-id="42a86-118">How to: Post Transactions Directly to the General Ledger</span></span>](finance-how-post-transactions-directly.md)  
[<span data-ttu-id="42a86-119">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="42a86-119">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="42a86-120">Finances</span><span class="sxs-lookup"><span data-stu-id="42a86-120">Finance</span></span>](finance.md)  
<span data-ttu-id="42a86-121">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="42a86-121">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

