---
title: Enregistrer les frais ou les revenus directement dans le grand livre| Microsoft Docs
description: Pour les activités économiques qui ne sont pas représentés par un document, comme de plus petits frais ou encaissements, vous pouvez créer les transactions associées en reportant des lignes de journal sur la page Journal général.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct posting, general ledger
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: e0beff15352fb8e57f57c9d0ffdcd76bc28afbb9
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5782390"
---
# <a name="post-transactions-directly-to-the-general-ledger"></a><span data-ttu-id="d4664-103">Reporter les transactions directement dans le grand livre</span><span class="sxs-lookup"><span data-stu-id="d4664-103">Post Transactions Directly to the General Ledger</span></span>

<span data-ttu-id="d4664-104">Les journaux généraux vous permettent de reporter des transactions financières directement dans les comptes GL et dans d'autres comptes tels que les comptes bancaires, client, fournisseur et employé.</span><span class="sxs-lookup"><span data-stu-id="d4664-104">You use general journals to post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts.</span></span>  

<span data-ttu-id="d4664-105">Une utilisation classique du journal général est de reporter les dépenses des employés avec leurs fonds propres au cours des activités professionnelles, pour un remboursement ultérieur.</span><span class="sxs-lookup"><span data-stu-id="d4664-105">A typical use of the general journal is to post employees' expenditure of own money during business activities, for later reimbursement.</span></span> <span data-ttu-id="d4664-106">Pour plus d'informations, voir [Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md).</span><span class="sxs-lookup"><span data-stu-id="d4664-106">For more information, see [Record and Reimburse Employees' Expenses](finance-how-record-reimburse-employee-expenses.md).</span></span>

<span data-ttu-id="d4664-107">Les journaux généraux reportent les transactions financières directement sur les comptes du grand livre et d'autres comptes tels que les comptes bancaires, clients, fournisseurs et employés.</span><span class="sxs-lookup"><span data-stu-id="d4664-107">General journals post financial transactions directly to general ledger accounts and other accounts, such as bank, customer, vendor, and employee accounts.</span></span> <span data-ttu-id="d4664-108">Le report avec un journal général crée toujours des écritures dans les comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="d4664-108">Posting with a general journal always creates entries on general ledger accounts.</span></span> <span data-ttu-id="d4664-109">C'est le cas même lorsque, par exemple, vous reportez une ligne journal sur un compte client, parce qu'une écriture est reportée dans un compte client du grand livre via un groupe de report.</span><span class="sxs-lookup"><span data-stu-id="d4664-109">This is true even when, for example, you post a journal line to a customer account, because an entry is posted to a general ledger receivables account through a posting group.</span></span> <span data-ttu-id="d4664-110">Vous pouvez personnaliser votre version d'un journal général en configurant un lot ou un modèle journal.</span><span class="sxs-lookup"><span data-stu-id="d4664-110">You can personalize your version of a general journal by setting up a journal batch or template.</span></span> <span data-ttu-id="d4664-111">Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).</span><span class="sxs-lookup"><span data-stu-id="d4664-111">For more information, see [Working with General Journals](ui-work-general-journals.md).</span></span>

<span data-ttu-id="d4664-112">Contrairement aux écritures qui sont reportées avec des documents qui nécessitent un processus de note de crédit, vous pouvez correctement inverser les écritures reportées avec le journal général.</span><span class="sxs-lookup"><span data-stu-id="d4664-112">Unlike for entries that are posted with documents, which require a credit memo process, you can correctly reverse entries that are posted with the general journal.</span></span> <span data-ttu-id="d4664-113">Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).</span><span class="sxs-lookup"><span data-stu-id="d4664-113">For more information, see [Reverse Journal Postings and Undo Receipts/Shipments](finance-how-reverse-journal-posting.md).</span></span>

## <a name="to-post-a-transaction-directly-to-a-general-ledger-account"></a><span data-ttu-id="d4664-114">Pour reporter une transaction directement dans le compte GL</span><span class="sxs-lookup"><span data-stu-id="d4664-114">To post a transaction directly to a general ledger account</span></span>

1. <span data-ttu-id="d4664-115">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d4664-115">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="d4664-116">Ouvrez le lot journal général approprié.</span><span class="sxs-lookup"><span data-stu-id="d4664-116">Open the relevant general journal batch.</span></span> <span data-ttu-id="d4664-117">Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).</span><span class="sxs-lookup"><span data-stu-id="d4664-117">For more information, see [Working with General Journals](ui-work-general-journals.md).</span></span>
3. <span data-ttu-id="d4664-118">Sur une nouvelle ligne journal, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="d4664-118">On a new journal line, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    

    > [!NOTE]
    > [!INCLUDE[journal-showhide-columns-inline-tip](includes/journal-showhide-columns-inline-tip.md)]
4. <span data-ttu-id="d4664-119">Répétez l'étape 3 pour toutes les transactions distinctes que vous souhaitez reporter.</span><span class="sxs-lookup"><span data-stu-id="d4664-119">Repeat step 3 for all the separate transactions that you want to post.</span></span>

    > [!TIP]  
    > <span data-ttu-id="d4664-120">Si vous souhaitez saisir plusieurs lignes de transaction au-dessus d'une ligne compte contrepartie, par exemple, pour un compte bancaire, activez la case à cocher **Suggérer le montant contrepartie** de la ligne pour votre lot sur la page **Lots journal général**.</span><span class="sxs-lookup"><span data-stu-id="d4664-120">If you want to enter multiple transaction lines above one balance-account line, for example, for one bank account, then select the **Suggest Balancing Amount** check box on the line for your batch on the **General Journal Batches** page.</span></span> <span data-ttu-id="d4664-121">Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les transactions.</span><span class="sxs-lookup"><span data-stu-id="d4664-121">Then the **Amount** field on the balance-account line is automatically prefilled with the value that is required to balance the transactions.</span></span>
5. <span data-ttu-id="d4664-122">Choisissez l'action **Valider** pour enregistrer les transactions sur les comptes généraux spécifiés.</span><span class="sxs-lookup"><span data-stu-id="d4664-122">Choose the **Post** action to record the transactions on the specified G/L accounts.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4664-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d4664-123">See Also</span></span>

[<span data-ttu-id="d4664-124">Utilisation de journaux généraux</span><span class="sxs-lookup"><span data-stu-id="d4664-124">Working with General Journals</span></span>](ui-work-general-journals.md)  
[<span data-ttu-id="d4664-125">Enregistrer et rembourser les frais des employés</span><span class="sxs-lookup"><span data-stu-id="d4664-125">Record and Reimburse Employees' Expenses</span></span>](finance-how-record-reimburse-employee-expenses.md)  
[<span data-ttu-id="d4664-126">Inverser des reports journal et annuler des réceptions/livraisons</span><span class="sxs-lookup"><span data-stu-id="d4664-126">Reverse Journal Postings and Undo Receipts/Shipments</span></span>](finance-how-reverse-journal-posting.md)  
[<span data-ttu-id="d4664-127">Finance</span><span class="sxs-lookup"><span data-stu-id="d4664-127">Finance</span></span>](finance.md)  
<span data-ttu-id="d4664-128">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="d4664-128">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>  


[!INCLUDE[footer-include](includes/footer-banner.md)]