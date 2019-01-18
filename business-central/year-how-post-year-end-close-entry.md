---
title: "Vérifier et reporter l'écriture de fermeture de fin d'exercice | Microsoft Docs"
description: "Décrit comment ouvrir le journal spécifié dans le traitement en lot Fermer l'état des résultats, puis examiner et reporter l'écriture de fermeture de fin d'exercice."
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
ms.openlocfilehash: cd555cc389ff7d9e306645475ef042f7ee9bc934
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="post-the-year-end-closing-entry"></a><span data-ttu-id="c59bc-103">Reporter l'écriture de fermeture d'exercice</span><span class="sxs-lookup"><span data-stu-id="c59bc-103">Post the Year-End Closing Entry</span></span>
<span data-ttu-id="c59bc-104">Après avoir utilisé le traitement par lots **Solder les comptes de gestion** pour générer les écritures de clôture d'exercice, vous devez ouvrir la feuille spécifiée dans le traitement par lots, puis consulter et valider les écritures.</span><span class="sxs-lookup"><span data-stu-id="c59bc-104">After you use the **Close Income Statement** batch job to generate the year-end closing entry or entries, you must open the journal you specified in the batch job, and then review and post the entries.</span></span>

## <a name="to-post-the-year-end-closing-entry"></a><span data-ttu-id="c59bc-105">Pour reporter l'écriture de fermeture de fin d'exercice</span><span class="sxs-lookup"><span data-stu-id="c59bc-105">To post the year end closing entry</span></span>
1. <span data-ttu-id="c59bc-106">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal général**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c59bc-106">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **General Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="c59bc-107">Sur la page **Journal général**, dans le champ **Nom de lot**, sélectionnez le lot qui contient les écritures de fermeture.</span><span class="sxs-lookup"><span data-stu-id="c59bc-107">On the **General Journal** page, in the **Batch Name** field, select the batch that contains the closing entries.</span></span>
3. <span data-ttu-id="c59bc-108">Examinez les écritures.</span><span class="sxs-lookup"><span data-stu-id="c59bc-108">Review the entries.</span></span>
4. <span data-ttu-id="c59bc-109">Pour valider la feuille, sélectionnez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="c59bc-109">To post the journal, choose the **Post** action.</span></span>

> [!NOTE]  
>   <span data-ttu-id="c59bc-110">En cas de détection d'une erreur, un message d'erreur s'affiche.</span><span class="sxs-lookup"><span data-stu-id="c59bc-110">If an error is detected, an error message is displayed.</span></span> <span data-ttu-id="c59bc-111">Si le report réussit, les entrées reportées sont supprimées du journal.</span><span class="sxs-lookup"><span data-stu-id="c59bc-111">If the posting is successful, the posted entries are removed from the journal.</span></span> <span data-ttu-id="c59bc-112">Une fois le report terminé, une entrée est reportée sur chaque compte état des résultats, de façon à ce que son solde indique zéro et à ce que les résultats de l'exercice soient transférés dans le bilan.</span><span class="sxs-lookup"><span data-stu-id="c59bc-112">After posting is complete, an entry is posted to each income statement account so that its balance becomes zero and the year's result is transferred to the balance sheet.</span></span>

## <a name="see-also"></a><span data-ttu-id="c59bc-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c59bc-113">See Also</span></span>
[<span data-ttu-id="c59bc-114">Fermer des périodes comptables</span><span class="sxs-lookup"><span data-stu-id="c59bc-114">Close Accounting Periods</span></span>](year-close-account-periods.md)  
[<span data-ttu-id="c59bc-115">Clôture plans</span><span class="sxs-lookup"><span data-stu-id="c59bc-115">Closing Books</span></span>](year-close-books.md)  
[<span data-ttu-id="c59bc-116">Clôturer exercice comptable</span><span class="sxs-lookup"><span data-stu-id="c59bc-116">Close Income Statement</span></span>](year-close-income-statement.md)  
<span data-ttu-id="c59bc-117">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="c59bc-117">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

