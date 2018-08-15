---
title: "Créer des nouvelles écritures valeur pour des articles de l'inventaire Microsoft Docs"
description: "Décrit comment réévaluer ou amortir les entrées valeur d'un ou de plusieurs articles dans l'inventaire en reportant leur valeur actuelle calculée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: costing, inventory cost, value entries
ms.date: 08/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 6f52795bf47b3ebddd446105b92d526a83748fc8
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="revalue-inventory"></a><span data-ttu-id="8a48f-103">Réévaluer l'inventaire</span><span class="sxs-lookup"><span data-stu-id="8a48f-103">Revalue Inventory</span></span>
<span data-ttu-id="8a48f-104">Pour réévaluer ou amortir un article ou une écriture article spécifique, vous devez utiliser le journal réévaluation.</span><span class="sxs-lookup"><span data-stu-id="8a48f-104">If you want to appreciate or depreciate an item or a specific item ledger entry, you must use the revaluation journal.</span></span>

## <a name="to-revalue-inventory"></a><span data-ttu-id="8a48f-105">Pour réévaluer l'inventaire</span><span class="sxs-lookup"><span data-stu-id="8a48f-105">To revalue inventory</span></span>
1. <span data-ttu-id="8a48f-106">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Feuille réévaluation**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="8a48f-106">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Revaluation Journal**, and then choose the related link.</span></span>
2. <span data-ttu-id="8a48f-107">Choisissez l'action **Calculer valeur stock**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-107">Choose the **Calculate Inventory Value** action.</span></span>
3. <span data-ttu-id="8a48f-108">Dans la fenêtre **Calculer valeur stock**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="8a48f-108">In the **Calculate Inventory Value** window, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="8a48f-109">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-109">Choose the **OK** button.</span></span>
5. <span data-ttu-id="8a48f-110">Sur chaque ligne de la fenêtre **Feuille réévaluation**, indiquez le nouveau coût unitaire dans le champ **Coût unitaire (réévalué)**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-110">On each line in the **Revaluation Journal** window, in the **Unit Cost (Revalued)** field, enter the new unit cost.</span></span> <span data-ttu-id="8a48f-111">Vous pouvez aussi indiquer le nouveau montant total dans le champ **Valeur stock (réévaluée)**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-111">Alternatively, enter the new total amount in the **Inventory Value (Revalued)** field.</span></span>

    <span data-ttu-id="8a48f-112">Les champs appropriés sont automatiquement mis à jour.</span><span class="sxs-lookup"><span data-stu-id="8a48f-112">The relevant fields are automatically updated.</span></span> <span data-ttu-id="8a48f-113">Remarque : le champ **Montant** affiche la modification réelle de la valeur du stock pour l'écriture comptable article sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8a48f-113">Note that the **Amount** field shows the actual change in inventory value for the selected item ledger entry.</span></span> <span data-ttu-id="8a48f-114">Il calcule la différence entre les champs **Valeur stock (calculée)** et **Valeur stock (réévaluée)**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-114">It calculates the difference between the **Inventory Value (Calculated)** field and the **Inventory Value (Revalued)** field.</span></span>
6. <span data-ttu-id="8a48f-115">Lorsque vous avez renseigné toutes les lignes de la feuille réévaluation, choisissez l'action **Valider**.</span><span class="sxs-lookup"><span data-stu-id="8a48f-115">When you have completed all lines in the revaluation journal, choose the **Post** action.</span></span>

<span data-ttu-id="8a48f-116">Les nouvelles écritures valeur sont alors créées pour refléter les appréciations que vous avez reportées.</span><span class="sxs-lookup"><span data-stu-id="8a48f-116">New value entries are now created to reflect the revaluations that you have posted.</span></span> <span data-ttu-id="8a48f-117">Vous pouvez visualiser les nouvelles valeurs dans les fiches article concernées.</span><span class="sxs-lookup"><span data-stu-id="8a48f-117">You can see the new values on the respective item cards.</span></span>

## <a name="see-also"></a><span data-ttu-id="8a48f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8a48f-118">See Also</span></span>
[<span data-ttu-id="8a48f-119">Détails de conception : réévaluation</span><span class="sxs-lookup"><span data-stu-id="8a48f-119">Design Details: Revaluation</span></span>](design-details-revaluation.md)  
[<span data-ttu-id="8a48f-120">Stocks</span><span class="sxs-lookup"><span data-stu-id="8a48f-120">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="8a48f-121">Vente</span><span class="sxs-lookup"><span data-stu-id="8a48f-121">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="8a48f-122">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="8a48f-122">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="8a48f-123">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="8a48f-123">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
