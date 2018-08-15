---
title: "Procédure : suppression des écritures budget des coûts | Microsoft Docs"
description: "Vous utilisez le traitement par lots **Supprimer écritures budget des coûts** pour annuler les écritures de budget des coûts à partir du registre du budget des coûts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: acd8e0f25a3909ceab3dd63e04509ab48a300bb6
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="delete-cost-budget-entries"></a><span data-ttu-id="79761-103">Supprimer écritures budget des coûts</span><span class="sxs-lookup"><span data-stu-id="79761-103">Delete Cost Budget Entries</span></span>
<span data-ttu-id="79761-104">Vous utilisez le traitement par lots **Supprimer écritures budget des coûts** pour annuler les écritures de budget des coûts à partir du registre du budget des coûts.</span><span class="sxs-lookup"><span data-stu-id="79761-104">You use the **Delete Cost Budget Entries** batch job to cancel cost budget entries from the cost budget register.</span></span>  

<span data-ttu-id="79761-105">Pour empêcher tout écart dans les écritures du budget des coûts et les écritures du registre des coûts, vous ne pouvez pas supprimer une écriture unique ou un lot d'écritures dans la liste des écritures du registre.</span><span class="sxs-lookup"><span data-stu-id="79761-105">To prevent any gaps in the cost budget entries and cost register entries, you cannot delete a single entry or a batch of entries in the middle of the list of register entries.</span></span>  

### <a name="to-delete-a-cost-budget-entry"></a><span data-ttu-id="79761-106">Pour supprimer une écriture budget des coûts</span><span class="sxs-lookup"><span data-stu-id="79761-106">To delete a cost budget entry</span></span>  

1.  <span data-ttu-id="79761-107">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Supprimer écritures budget des coûts**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="79761-107">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Delete Cost Budget Entries**, and then choose the related link.</span></span>  

    <span data-ttu-id="79761-108">Le champ **N° hist. transaction de destination**</span><span class="sxs-lookup"><span data-stu-id="79761-108">The **To Register No.**</span></span> <span data-ttu-id="79761-109">affiche le numéro de la dernière écriture du registre et n'est pas modifiable.</span><span class="sxs-lookup"><span data-stu-id="79761-109">field contains the last register entry number and cannot be changed.</span></span>  

    <span data-ttu-id="79761-110">Vous pouvez utiliser le champ **N° hist. transaction d'origine**</span><span class="sxs-lookup"><span data-stu-id="79761-110">You can use the **From Register No.**</span></span> <span data-ttu-id="79761-111">pour sélectionner un numéro d'écriture du registre à partir duquel commencer la suppression.</span><span class="sxs-lookup"><span data-stu-id="79761-111">field to select a register entry number from which the deletion should begin.</span></span>  
2.  <span data-ttu-id="79761-112">Cliquez sur le bouton **OK** pour supprimer les écritures du budget des coûts sélectionnées.</span><span class="sxs-lookup"><span data-stu-id="79761-112">Choose the **OK** button to delete the selected cost budget entries.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="79761-113">Pour éviter une suppression accidentelle des écritures du budget des coûts, vous pouvez clôturer les écritures du registre en marquant les lignes comme **Clôturées** dans le champ **Clôturées** de la fenêtre **Registre du budget des coûts**.</span><span class="sxs-lookup"><span data-stu-id="79761-113">To avoid an accidental deletion of cost budget entries, you can close register entries by marking the lines as **Closed** in the **Closed** field in the **Cost Budget Registers** window.</span></span>  

## <a name="see-also"></a><span data-ttu-id="79761-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="79761-114">See Also</span></span>  
<span data-ttu-id="79761-115">[Comptabilité pour les coûts](finance-manage-cost-accounting.md)
[Création des budgets des coûts](finance-create-cost-budgets.md)</span><span class="sxs-lookup"><span data-stu-id="79761-115">[Accounting for Costs](finance-manage-cost-accounting.md)
[Creating Cost Budgets](finance-create-cost-budgets.md)</span></span>  
<span data-ttu-id="79761-116">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="79761-116">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
