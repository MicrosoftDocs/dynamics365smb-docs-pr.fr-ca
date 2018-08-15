---
title: "Comment configurer des modèles rangement | Microsoft Docs"
description: "À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 7fecd72242d30291d3741ee99fcb3ee5bc09af9f
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-put-away-templates"></a><span data-ttu-id="13126-103">Configurer des modèles rangement</span><span class="sxs-lookup"><span data-stu-id="13126-103">Set Up Put-away Templates</span></span>
<span data-ttu-id="13126-104">À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes.</span><span class="sxs-lookup"><span data-stu-id="13126-104">With directed put-away and pick functionality, the most appropriate bin for your items at any given time is suggested, according to the put-away template that you have set up for the warehouse, the bin rankings you have given to the bins, and the minimum and maximum quantities that you have set up for fixed bins.</span></span>  

<span data-ttu-id="13126-105">Vous pouvez configurer un certain nombre de modèles rangement et en sélectionner un pour gérer les rangements dans votre entrepôt.</span><span class="sxs-lookup"><span data-stu-id="13126-105">You can set up a number of put-away templates and select one of them to govern put-aways in general in your warehouse.</span></span> <span data-ttu-id="13126-106">Vous pouvez également sélectionner un modèle rangement pour un article ou une unité de stock disposant d'exigences spéciales en matière de rangement.</span><span class="sxs-lookup"><span data-stu-id="13126-106">You can also select a put-away template for any item or stockkeeping unit that might have special put-away requirements.</span></span>  

## <a name="to-set-up-put-away-templates"></a><span data-ttu-id="13126-107">Pour configurer des modèles rangement</span><span class="sxs-lookup"><span data-stu-id="13126-107">To set up put-away templates</span></span>  
1.  <span data-ttu-id="13126-108">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles de rangement**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="13126-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Put-away Templates**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="13126-109">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="13126-109">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="13126-110">Entrez un code représentant l'identificateur unique du modèle que vous allez créer.</span><span class="sxs-lookup"><span data-stu-id="13126-110">Enter a code that is the unique identifier of the template you are about to create.</span></span>  
4.  <span data-ttu-id="13126-111">Saisissez éventuellement une brève description.</span><span class="sxs-lookup"><span data-stu-id="13126-111">Enter a short description, if you wish.</span></span>  
5.  <span data-ttu-id="13126-112">Renseignez la première ligne avec les exigences de zone à satisfaire en priorité lors de la proposition d'un rangement.</span><span class="sxs-lookup"><span data-stu-id="13126-112">Fill in the first line with the bin requirements that you want fulfilled first and foremost when suggesting a put-away.</span></span>  
6.  <span data-ttu-id="13126-113">Renseignez la deuxième ligne avec les exigences de zone à satisfaire en deuxième lieu lors de la recherche d'une zone de rangement.</span><span class="sxs-lookup"><span data-stu-id="13126-113">Fill in the second line with the bin requirements that would be your second choice to fulfill in finding a bin for put-away.</span></span> <span data-ttu-id="13126-114">La deuxième ligne est utilisée uniquement si une zone répondant aux exigences de la première ligne ne peut être trouvée.</span><span class="sxs-lookup"><span data-stu-id="13126-114">The second line is used only if a bin that meets the requirements of the first line cannot be found.</span></span>  
7.  <span data-ttu-id="13126-115">Continuez à renseigner les lignes jusqu'à ce que vous ayez décrit toutes les zones acceptables à utiliser au cours du rangement.</span><span class="sxs-lookup"><span data-stu-id="13126-115">Continue to fill in the lines until you have described all the acceptable bin placements that you want to use in the put-away process.</span></span>  
8.  <span data-ttu-id="13126-116">Sur la dernière ligne du modèle rangement, cochez la case **Rechercher zone dynamique**.</span><span class="sxs-lookup"><span data-stu-id="13126-116">On the last line in the put-away template, select the **Find Floating Bin** check box.</span></span>  

<span data-ttu-id="13126-117">Vous pouvez créer plusieurs modèles rangement et les appliquer comme vous le souhaitez.</span><span class="sxs-lookup"><span data-stu-id="13126-117">You can create various put-away templates and then apply them as you see fit.</span></span> <span data-ttu-id="13126-118">On se réfère d'abord au modèle rangement sélectionné éventuel pour l'article ou l'unité de stock.</span><span class="sxs-lookup"><span data-stu-id="13126-118">The put-away template that you selected for the item or stockkeeping unit, if any is used first.</span></span> <span data-ttu-id="13126-119">Si ces champs ne sont pas renseignés, alors le modèle rangement sélectionné pour l'entrepôt sur le raccourci **Politiques de zones** de la fiche emplacement sera utilisé.</span><span class="sxs-lookup"><span data-stu-id="13126-119">If these fields are not filled in, then the put-away template that you selected for the warehouse on the **Bin Policies** FastTab on the location card is used.</span></span>  

## <a name="see-also"></a><span data-ttu-id="13126-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="13126-120">See Also</span></span>  
[<span data-ttu-id="13126-121">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="13126-121">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="13126-122">Stock</span><span class="sxs-lookup"><span data-stu-id="13126-122">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="13126-123">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="13126-123">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="13126-124">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="13126-124">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="13126-125">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="13126-125">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="13126-126">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="13126-126">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
