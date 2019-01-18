---
title: "Fermer des périodes comptables pour un exercice financier | Microsoft Docs"
description: "Décrit comment fermer les périodes comptables de l'exercice financier."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: year closing, close accounting period, close fiscal year, bank account detailed trial balance
ms.date: 10/01/2018
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: c8f086e0dc7479ece62ab28b64f9553ba2d13b82
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="close-accounting-periods"></a><span data-ttu-id="a3188-103">Fermer des périodes comptables</span><span class="sxs-lookup"><span data-stu-id="a3188-103">Close Accounting Periods</span></span>
<span data-ttu-id="a3188-104">Lorsqu'un exercice financier est terminé, vous devez fermer les périodes qui le composent.</span><span class="sxs-lookup"><span data-stu-id="a3188-104">When a fiscal year is over, you must close the periods that comprise it.</span></span>

## <a name="to-close-accounting-periods"></a><span data-ttu-id="a3188-105">Pour fermer des périodes comptables</span><span class="sxs-lookup"><span data-stu-id="a3188-105">To close accounting periods</span></span>
1. <span data-ttu-id="a3188-106">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Périodes comptables**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a3188-106">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Accounting Periods**, and then choose the related link.</span></span>
2. <span data-ttu-id="a3188-107">Sur la page **Périodes comptables**, sélectionnez l'action **Fermer exercice**.</span><span class="sxs-lookup"><span data-stu-id="a3188-107">On the **Accounting Periods** page, choose the **Close Year** action.</span></span>

    <span data-ttu-id="a3188-108">Si plusieurs exercices financiers sont ouverts, le plus ancien est automatiquement sélectionné pour la fermeture.</span><span class="sxs-lookup"><span data-stu-id="a3188-108">If more than one fiscal year is open, the earliest one is automatically selected to be closed.</span></span> <span data-ttu-id="a3188-109">Un message identifiant l'exercice qu'il compte fermer s'affiche et indique les conséquences de la fermeture.</span><span class="sxs-lookup"><span data-stu-id="a3188-109">A message displays identifying the year that will close and the consequences of closing the year.</span></span>
3. <span data-ttu-id="a3188-110">Pour clôturer l'exercice, cliquez sur **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a3188-110">To close the year, choose the **Yes** button.</span></span>

<span data-ttu-id="a3188-111">L'exercice comptable est désormais clôturé, et les champs **Fermé** et **Verrouillage date** sont sélectionnés pour toutes les périodes de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="a3188-111">The fiscal year is closed, and the **Closed** and **Date Locked** fields for all the periods in the year are selected.</span></span> <span data-ttu-id="a3188-112">Vous ne pouvez pas rouvrir l'exercice comptable ni supprimer la coche des champs **Fermé** et **Verrouillage date**.</span><span class="sxs-lookup"><span data-stu-id="a3188-112">The fiscal year cannot be opened again and you cannot remove the check mark from the **Closed** or **Date Locked** fields.</span></span>

> [!NOTE]  
>   <span data-ttu-id="a3188-113">Vous ne pouvez pas fermer un exercice financier avant d'en avoir créé un nouveau.</span><span class="sxs-lookup"><span data-stu-id="a3188-113">You cannot close a fiscal year before you create a new one.</span></span> <span data-ttu-id="a3188-114">Sachez que lorsqu'un exercice financier est fermé, vous ne pouvez pas modifier la date début de l'exercice financier suivant.</span><span class="sxs-lookup"><span data-stu-id="a3188-114">Notice that when a fiscal year has been closed, you cannot change the starting date of the following fiscal year.</span></span>

<span data-ttu-id="a3188-115">Même si un exercice financier a été fermé, vous pouvez toujours y reporter des écritures.</span><span class="sxs-lookup"><span data-stu-id="a3188-115">Even though a fiscal year has been closed, you can still post general ledger entries to it.</span></span> <span data-ttu-id="a3188-116">Dans ce cas, les écritures sont marquées comme validées dans un exercice comptable clôturé et le champ **Ecr. exercice précédent** est activé.</span><span class="sxs-lookup"><span data-stu-id="a3188-116">When you do this, the entries will be marked as posted to a closed fiscal year and the **Prior-Year Entry** field will be selected.</span></span>

<span data-ttu-id="a3188-117">Une fois qu'un exercice financier a été fermé, vous devez fermer les comptes d'état des résultats et transférer les résultats de l'exercice sur un compte du bilan.</span><span class="sxs-lookup"><span data-stu-id="a3188-117">After a fiscal year is closed, you must close the income statement accounts and transfer the year's results to an account in the balance sheet.</span></span> <span data-ttu-id="a3188-118">Vous pouvez répéter cette opération chaque fois que vous effectuez un report dans l'exercice financier fermé.</span><span class="sxs-lookup"><span data-stu-id="a3188-118">You can repeat this every time that you post to the closed fiscal year.</span></span>

## <a name="see-also"></a><span data-ttu-id="a3188-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a3188-119">See Also</span></span>
[<span data-ttu-id="a3188-120">Clôture plans</span><span class="sxs-lookup"><span data-stu-id="a3188-120">Closing Books</span></span>](year-close-books.md)  
[<span data-ttu-id="a3188-121">Reporter l'écriture de fermeture d'exercice</span><span class="sxs-lookup"><span data-stu-id="a3188-121">Post the Year-End Closing Entry</span></span>](year-how-post-year-end-close-entry.md)  
[<span data-ttu-id="a3188-122">Ouvrir un nouvel exercice financier</span><span class="sxs-lookup"><span data-stu-id="a3188-122">Open a New Fiscal Year</span></span>](finance-how-open-new-fiscal-year.md)  
<span data-ttu-id="a3188-123">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a3188-123">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

