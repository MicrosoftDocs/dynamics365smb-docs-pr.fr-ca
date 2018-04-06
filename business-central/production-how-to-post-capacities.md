---
title: "Procédure : reporter des capacités | Microsoft Docs"
description: "Le journal capacité vous permet de reporter les capacités consommées qui ne sont pas affectées au bon de production. Par exemple, les travaux d'entretien doivent être affectés à une capacité, mais non à un bon de production."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 6114149372b786c20ee7edbe13022abe688ed9a2
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="post-capacities"></a><span data-ttu-id="a6000-104">Reporter des capacités</span><span class="sxs-lookup"><span data-stu-id="a6000-104">Post Capacities</span></span>
<span data-ttu-id="a6000-105">Le journal capacité vous permet de reporter les capacités consommées qui ne sont pas affectées au bon de production.</span><span class="sxs-lookup"><span data-stu-id="a6000-105">In the capacity journal, you post consumed capacities that are not assigned to the production order.</span></span> <span data-ttu-id="a6000-106">Par exemple, les travaux d'entretien doivent être affectés à une capacité, mais non à un bon de production.</span><span class="sxs-lookup"><span data-stu-id="a6000-106">For example, maintenance work must be assigned to capacity, but not to a production order.</span></span>  

## <a name="to-post-capacities"></a><span data-ttu-id="a6000-107">Pour reporter les capacités</span><span class="sxs-lookup"><span data-stu-id="a6000-107">To post capacities</span></span>  
1.  <span data-ttu-id="a6000-108">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journaux capacité**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a6000-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Capacity Journals**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="a6000-109">Renseignez les champs **Date de report** et **N° document**.</span><span class="sxs-lookup"><span data-stu-id="a6000-109">Fill in the **Posting Date** and **Document No.** fields.</span></span>  
3.  <span data-ttu-id="a6000-110">Dans le champ **Type**, entrez le type de capacité, **Poste de charge** ou **Centre de charge**, que vous validez.</span><span class="sxs-lookup"><span data-stu-id="a6000-110">In the **Type** field, enter the type of the capacity, either **Machine Center** or **Work Center**, that you are posting.</span></span>  
4.  <span data-ttu-id="a6000-111">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="a6000-111">In the **No.**</span></span> <span data-ttu-id="a6000-112">saisissez le numéro de l'unité de production ou de l'atelier.</span><span class="sxs-lookup"><span data-stu-id="a6000-112">field, enter the number of the machine center or work center.</span></span>  
5.  <span data-ttu-id="a6000-113">Entrez les données nécessaires dans les autres champs, tels que **Heure début**, **Heure fin**, **Quantité**, et **Rebut**.</span><span class="sxs-lookup"><span data-stu-id="a6000-113">Enter the relevant data in the other fields, such as **Starting Time**, **Ending Time**, **Quantity**, and **Scrap**.</span></span>  
6.  <span data-ttu-id="a6000-114">Choisissez l'action **Reporter** pour reporter les capacités.</span><span class="sxs-lookup"><span data-stu-id="a6000-114">Choose the **Post** action to post the capacities.</span></span>  

## <a name="to-view-work-center-ledger-entries"></a><span data-ttu-id="a6000-115">Pour afficher les écritures de l'atelier</span><span class="sxs-lookup"><span data-stu-id="a6000-115">To view work center ledger entries</span></span>  
<span data-ttu-id="a6000-116">Dans les fenêtres **Fiche atelier** et **Fiche unité de production**, vous pouvez afficher les capacités reportées en tant que résultat des bons de production terminés.</span><span class="sxs-lookup"><span data-stu-id="a6000-116">In the **Work Center Card** and **Machine Center Card** windows, you can view the posted capacities as a result of finished production orders.</span></span>    
1.  <span data-ttu-id="a6000-117">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Ateliers**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a6000-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Work Centers**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="a6000-118">Ouvrez la fiche **Atelier** appropriée dans la liste, puis choisissez l'action **Écritures du grand livre de capacité**.</span><span class="sxs-lookup"><span data-stu-id="a6000-118">Open the relevant **Work Center** card from the list, and then choose the **Capacity Ledger Entries** action.</span></span>  

<span data-ttu-id="a6000-119">La fenêtre **Écritures comptables capacité** affiche les écritures validées relatives au centre de charge dans l'ordre de leur validation.</span><span class="sxs-lookup"><span data-stu-id="a6000-119">The **Capacity Ledger Entries** window displays the posted entries from the work center in the order they were posted.</span></span>   

## <a name="see-also"></a><span data-ttu-id="a6000-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a6000-120">See Also</span></span>  
<span data-ttu-id="a6000-121">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="a6000-121">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
[<span data-ttu-id="a6000-122">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="a6000-122">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
<span data-ttu-id="a6000-123">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="a6000-123">[Planning](production-planning.md)    </span></span>  
[<span data-ttu-id="a6000-124">Stock</span><span class="sxs-lookup"><span data-stu-id="a6000-124">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="a6000-125">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="a6000-125">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="a6000-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a6000-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

