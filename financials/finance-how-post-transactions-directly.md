---
title: Enregistrer les frais ou les revenus directement dans le grand livre| Microsoft Docs
description: "Pour les activités économiques qui ne sont pas représentées par un document, comme de plus petits frais ou règlements, vous pouvez créer les transactions associées en reportant des lignes de journal dans la fenêtre Journal général."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct posting, general ledger
ms.date: 06/15/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 7fa0d6b604a60e000208287546d831690a914931
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="how-to-post-transactions-directly-to-the-general-ledger"></a><span data-ttu-id="3c5c3-103">Procédure : reporter les transactions directement dans le grand livre</span><span class="sxs-lookup"><span data-stu-id="3c5c3-103">How to: Post Transactions Directly to the General Ledger</span></span>
<span data-ttu-id="3c5c3-104">La plupart des transactions financières sont reportées dans le grand livre via les documents commerciaux dédiés, tels que des factures achat et des documents de vente.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-104">Most financial transactions are posted to the general ledger through dedicated business documents, such as purchase invoices and sales orders.</span></span> <span data-ttu-id="3c5c3-105">Pour les activités économiques qui ne sont pas représentés par un document dans [!INCLUDE[d365fin](includes/d365fin_md.md)], comme de plus petits frais ou règlements, vous pouvez créer les transactions associées en validant des lignes de feuille dans la fenêtre **Feuille comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-105">For business activities that are not represented by a document in [!INCLUDE[d365fin](includes/d365fin_md.md)], such as smaller expenses or cash receipts, you can create the related transactions by posting journal lines in the **General Journal** window.</span></span>

<span data-ttu-id="3c5c3-106">Les journaux généraux reportent les transactions financières directement dans les comptes GL et d'autres comptes tels que les comptes bancaires, clients et fournisseurs.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-106">General journals post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, and vendor accounts.</span></span> <span data-ttu-id="3c5c3-107">Le report avec un journal général crée toujours des écritures dans les comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-107">Posting with a general journal always creates entries on general ledger accounts.</span></span> <span data-ttu-id="3c5c3-108">C'est le cas même lorsque, par exemple, vous reportez une ligne journal sur un compte client, parce qu'une écriture est reportée dans un compte client du grand livre via un groupe de report.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-108">This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group.</span></span> <span data-ttu-id="3c5c3-109">Vous pouvez personnaliser votre version d'un journal général en configurant un lot ou un modèle journal.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-109">You can personalize your version of a general journal by setting up a journal batch or template.</span></span> <span data-ttu-id="3c5c3-110">Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).</span><span class="sxs-lookup"><span data-stu-id="3c5c3-110">For more information, see [Working with General Journals](ui-work-general-journals.md).</span></span>

<span data-ttu-id="3c5c3-111">Contrairement aux écritures qui sont reportées avec des documents qui nécessitent un processus de note de crédit, vous pouvez correctement inverser les écritures reportées avec le journal général.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-111">Unlike for entries that are posted with documents, which require a credit memo process, you can correctly reverse entries that are posted with the general journal.</span></span> <span data-ttu-id="3c5c3-112">Pour plus d'informations, reportez-vous à [Procédure : inversion d'une validation feuille](finance-how-reverse-journal-posting.md).</span><span class="sxs-lookup"><span data-stu-id="3c5c3-112">For more information, see [How to: Reverse Journal Posting](finance-how-reverse-journal-posting.md).</span></span>

## <a name="to-post-a-transaction-directly-to-a-general-ledger-account"></a><span data-ttu-id="3c5c3-113">Pour reporter une transaction directement dans le compte GL</span><span class="sxs-lookup"><span data-stu-id="3c5c3-113">To post a transaction directly to a general ledger account</span></span>
1. <span data-ttu-id="3c5c3-114">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles comptabilité**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="3c5c3-115">Ouvrez le lot journal général approprié.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-115">Open the relevant general journal batch.</span></span> <span data-ttu-id="3c5c3-116">Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).</span><span class="sxs-lookup"><span data-stu-id="3c5c3-116">For more information, see [Working with General Journals](ui-work-general-journals.md).</span></span>
3. <span data-ttu-id="3c5c3-117">Sur une nouvelle ligne journal, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-117">On a new journal line, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    
4. <span data-ttu-id="3c5c3-118">Répétez l'étape 3 pour toutes les transactions distinctes que vous souhaitez reporter.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-118">Repeat step 3 for all the separate transactions that you want to post.</span></span>

    > [!TIP]  
    > <span data-ttu-id="3c5c3-119">Si vous souhaitez saisir les lignes de transaction au-dessus d'une ligne compte contrepartie, par exemple, pour un compte bancaire, activez la case à cocher **Suggérer le montant contrepartie** de la ligne pour votre lot dans la fenêtre **Noms feuilles comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-119">If you want to enter multiple transaction lines above one balance-account line, for example, for one bank account, then select the **Suggest Balancing Amount** check box on the line for your batch in the **General Journal Batches** window.</span></span> <span data-ttu-id="3c5c3-120">Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les transactions.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-120">Then the **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the transactions.</span></span>
5. <span data-ttu-id="3c5c3-121">Choisissez l'action **Valider** pour enregistrer les transactions sur les comptes généraux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="3c5c3-121">Choose the **Post** action to record the transactions on the specified G/L accounts.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c5c3-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c5c3-122">See Also</span></span>
[<span data-ttu-id="3c5c3-123">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="3c5c3-123">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="3c5c3-124">Procédure : inversion d'une validation feuille</span><span class="sxs-lookup"><span data-stu-id="3c5c3-124">How to: Reverse Journal Posting</span></span>](finance-how-reverse-journal-posting.md)  
[<span data-ttu-id="3c5c3-125">Finances</span><span class="sxs-lookup"><span data-stu-id="3c5c3-125">Finance</span></span>](finance.md)  
<span data-ttu-id="3c5c3-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="3c5c3-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  

