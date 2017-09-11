---
title: "Créer des nouvelles écritures valeur pour des articles de l'inventaire Microsoft Docs"
description: "Décrit comment réévaluer ou amortir les entrées valeur d'un ou de plusieurs articles dans l'inventaire en reportant leur valeur actuelle calculée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: costing, inventory cost, value entries
ms.date: 06/02/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 1935f53db068047921e44109cd4b23bbb51f0890
ms.contentlocale: fr-ca
ms.lasthandoff: 09/11/2017

---
# <a name="how-to-revalue-inventory"></a><span data-ttu-id="5729e-103">Procédure : réévaluer l'inventaire</span><span class="sxs-lookup"><span data-stu-id="5729e-103">How to: Revalue Inventory</span></span>
<span data-ttu-id="5729e-104">Pour réévaluer ou amortir un article ou une écriture article spécifique, vous devez utiliser le journal réévaluation.</span><span class="sxs-lookup"><span data-stu-id="5729e-104">If you want to appreciate or depreciate an item or a specific item ledger entry, you must use the revaluation journal.</span></span>

## <a name="to-revalue-inventory"></a><span data-ttu-id="5729e-105">Pour réévaluer l'inventaire</span><span class="sxs-lookup"><span data-stu-id="5729e-105">To revalue inventory</span></span>
1. <span data-ttu-id="5729e-106">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille réévaluation**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="5729e-106">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Revaluation Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="5729e-107">Choisissez l'action **Calculer valeur stock**.</span><span class="sxs-lookup"><span data-stu-id="5729e-107">Choose the **Calculate Inventory Value** action.</span></span>
3. <span data-ttu-id="5729e-108">Dans la fenêtre **Calculer valeur stock**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="5729e-108">In the **Calculate Inventory Value** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="5729e-109">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="5729e-109">Choose the **OK** button.</span></span>
5. <span data-ttu-id="5729e-110">Sur chaque ligne de la fenêtre **Feuille réévaluation**, indiquez le nouveau coût unitaire dans le champ **Coût unitaire (réévalué)**.</span><span class="sxs-lookup"><span data-stu-id="5729e-110">On each line in the **Revaluation Journal** window, in the **Unit Cost (Revalued)** field, enter the new unit cost.</span></span> <span data-ttu-id="5729e-111">Vous pouvez aussi indiquer le nouveau montant total dans le champ **Valeur stock (réévaluée)**.</span><span class="sxs-lookup"><span data-stu-id="5729e-111">Alternatively, enter the new total amount in the **Inventory Value (Revalued)** field.</span></span>

    <span data-ttu-id="5729e-112">Les champs appropriés sont automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="5729e-112">The relevant fields are automatically updated.</span></span> <span data-ttu-id="5729e-113">Remarque : le champ **Montant** affiche la modification réelle de la valeur du stock pour l'écriture comptable article sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="5729e-113">Note that the **Amount** field shows the actual change in inventory value for the selected item ledger entry.</span></span> <span data-ttu-id="5729e-114">Il calcule la différence entre les champs **Valeur stock (calculée)** et **Valeur stock (réévaluée)**.</span><span class="sxs-lookup"><span data-stu-id="5729e-114">It calculates the difference between the **Inventory Value (Calculated)** field and the **Inventory Value (Revalued)** field.</span></span>
6. <span data-ttu-id="5729e-115">Lorsque vous avez renseigné toutes les lignes de la feuille réévaluation, choisissez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="5729e-115">When you have completed all lines in the revaluation journal, choose the **Post** action.</span></span>

<span data-ttu-id="5729e-116">Les nouvelles écritures valeur sont alors créées pour refléter les appréciations que vous avez reportées.</span><span class="sxs-lookup"><span data-stu-id="5729e-116">New value entries are now created to reflect the revaluations that you have posted.</span></span> <span data-ttu-id="5729e-117">Vous pouvez visualiser les nouvelles valeurs dans les fiches article concernées.</span><span class="sxs-lookup"><span data-stu-id="5729e-117">You can see the new values on the respective item cards.</span></span>

## <a name="see-also"></a><span data-ttu-id="5729e-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5729e-118">See Also</span></span>
[<span data-ttu-id="5729e-119">Stock</span><span class="sxs-lookup"><span data-stu-id="5729e-119">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="5729e-120">Ventes</span><span class="sxs-lookup"><span data-stu-id="5729e-120">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="5729e-121">Achats</span><span class="sxs-lookup"><span data-stu-id="5729e-121">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="5729e-122">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="5729e-122">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

