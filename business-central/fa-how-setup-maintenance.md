---
title: Configurer l'entretien des immobilisations| Microsoft Docs
description: "Pour gérer les réparations et l'entretien des immobilisations, spécifiez les informations générales d'entretien, les codes du type de travail, ainsi qu'un compte de report pour les coûts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: repair, service
ms.date: 06/02/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: b730e880a3cf9f2ba3a2abaa25a1b80848f52e97
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-fixed-asset-maintenance"></a><span data-ttu-id="60dcd-103">Configurer l'entretien d'une immobilisation</span><span class="sxs-lookup"><span data-stu-id="60dcd-103">Set Up Fixed Asset Maintenance</span></span>
<span data-ttu-id="60dcd-104">Pour gérer l'entretien des immobilisations, vous devez configurer tout d'abord certaines informations générales d'entretien, un compte de report pour les coûts d'entretien et les codes d'entretien pour les types de travaux, tels que le service de routine ou la réparation.</span><span class="sxs-lookup"><span data-stu-id="60dcd-104">To manage fixed asset maintenance, you must first set up some general maintenance information, a posting account for maintenance costs, and maintenance codes for types of work, such as Routine Service or Repair.</span></span>

## <a name="to-set-up-general-maintenance-information"></a><span data-ttu-id="60dcd-105">Pour configurer les informations générales d'entretien</span><span class="sxs-lookup"><span data-stu-id="60dcd-105">To set up general maintenance information</span></span>
<span data-ttu-id="60dcd-106">Si vous configurez les champs pour l'entretien, vous pouvez reporter des dépenses d'entretien à partir du journal immobilisation.</span><span class="sxs-lookup"><span data-stu-id="60dcd-106">If you set up the fields for maintenance, you can post maintenance expenses from the fixed asset journal.</span></span>

1. <span data-ttu-id="60dcd-107">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Immobilisations**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="60dcd-107">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Fixed Assets**, and then choose the related link.</span></span>
2. <span data-ttu-id="60dcd-108">Sélectionnez l'immobilisation pour laquelle vous souhaitez définir la couverture d'assurance, puis sélectionnez l'action **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="60dcd-108">Select the fixed asset that you to define insurance coverage for, and then choose the **Edit** action.</span></span>
3. <span data-ttu-id="60dcd-109">Sur le raccourci **Maintenance**, complétez les champs, comme nécessaire.</span><span class="sxs-lookup"><span data-stu-id="60dcd-109">On the **Maintenance** FastTab, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-maintenance-codes"></a><span data-ttu-id="60dcd-110">Pour configurer des codes entretien</span><span class="sxs-lookup"><span data-stu-id="60dcd-110">To set up maintenance codes</span></span>
<span data-ttu-id="60dcd-111">Lorsque vous validez des coûts de maintenance à partir d'une feuille comptabilité, vous renseignez le champ **Code maintenance** pour enregistrer le type de maintenance effectuée, telle qu'un service de routine ou une réparation.</span><span class="sxs-lookup"><span data-stu-id="60dcd-111">When you post maintenance costs from a general journal, you fill in the **Maintenance Code** field to record what kind of maintenance has been performed, such as routine service or repair.</span></span>

1. <span data-ttu-id="60dcd-112">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Maintenance**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="60dcd-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Maintenance**, and then choose the related link.</span></span>
2. <span data-ttu-id="60dcd-113">Dans la fenêtre **Maintenance**, configurez les codes pour les différents types de travaux de maintenance.</span><span class="sxs-lookup"><span data-stu-id="60dcd-113">In the **Maintenance** window, set up codes for different types of maintenance work.</span></span>

## <a name="to-set-up-maintenance-expense-accounts"></a><span data-ttu-id="60dcd-114">Pour configurer des comptes frais d'entretien</span><span class="sxs-lookup"><span data-stu-id="60dcd-114">To set up maintenance expense accounts</span></span>
<span data-ttu-id="60dcd-115">Pour valider les coûts de maintenance, vous devez tout d'abord saisir un numéro de compte dans la fenêtre **Groupes compta. immo**.</span><span class="sxs-lookup"><span data-stu-id="60dcd-115">To post maintenance costs, you must first enter an account number in the **FA Posting Groups** window.</span></span>

1. <span data-ttu-id="60dcd-116">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Groupes compta. immo.**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="60dcd-116">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **FA Posting Groups**, and then choose the related link.</span></span>
2. <span data-ttu-id="60dcd-117">Renseignez le champ **Compte frais maintenance** pour chaque groupe comptabilisation.</span><span class="sxs-lookup"><span data-stu-id="60dcd-117">Fill in the **Maintenance Expense Account** field for each posting group.</span></span>

> [!NOTE]  
>   <span data-ttu-id="60dcd-118">Pour définir que les coûts d'entretien sont affectés aux départements ou projets, configurez une clé d'affectation.</span><span class="sxs-lookup"><span data-stu-id="60dcd-118">To define that maintenance costs are allocated to departments or projects, set up an allocation keys.</span></span> <span data-ttu-id="60dcd-119">Pour en savoir plus, voir [Configurer des fonctionnalités d'immobilisations](fa-how-setup-general.md).</span><span class="sxs-lookup"><span data-stu-id="60dcd-119">For more information, see [Set Up General Fixed Assets Features](fa-how-setup-general.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60dcd-120">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="60dcd-120">See Also</span></span>
[<span data-ttu-id="60dcd-121">Paramétrage d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="60dcd-121">Setting Up Fixed Assets</span></span>](fa-setup.md)  
[<span data-ttu-id="60dcd-122">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="60dcd-122">Fixed Assets</span></span>](fa-manage.md)  
[<span data-ttu-id="60dcd-123">Finance</span><span class="sxs-lookup"><span data-stu-id="60dcd-123">Finance</span></span>](finance.md)  
[<span data-ttu-id="60dcd-124">Mise en route</span><span class="sxs-lookup"><span data-stu-id="60dcd-124">Getting Started</span></span>](product-get-started.md)  
<span data-ttu-id="60dcd-125">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="60dcd-125">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
