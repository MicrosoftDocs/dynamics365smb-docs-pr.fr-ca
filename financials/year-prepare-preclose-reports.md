---
title: "Aperçu des rapports préalables à la fermeture pour vérifier l'exactitude des comptes | Microsoft Docs"
description: "Fournit un aperçu des rapports qui vous permettent de vérifier l'exactitude des comptes avant de fermer les registres à la fin d'un exercice ou d'une période."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 06/02/2017
ms.author: jswymer
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: ead7f45583b8edbdc00b6d41ae335d4b8adb14cf
ms.contentlocale: fr-ca
ms.lasthandoff: 09/11/2017


---
# <a name="using-pre-closing-reports"></a><span data-ttu-id="59c02-103">Utilisation des rapports préalables à la fermeture</span><span class="sxs-lookup"><span data-stu-id="59c02-103">Using Pre-Closing Reports</span></span>
<span data-ttu-id="59c02-104">Il existe de nombreux rapports standard qui vous permettent de vérifier la précision des comptes avant de fermer les registres à la fin d'un exercice ou d'une période.</span><span class="sxs-lookup"><span data-stu-id="59c02-104">There are many standard reports that you can use to verify the accuracy of the accounts before closing the books at the end of a year or period.</span></span> <span data-ttu-id="59c02-105">Par exemple, vous pouvez utiliser l'état **Clients : Balance** pour vérifier que le solde d'un groupe comptabilisation client est égal au solde du compte général correspondant à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="59c02-105">For example, you can use the **Customer - Trial Balance** report to verify that the balance for a customer posting group is equal to the balance on the corresponding general ledger account on a certain date.</span></span>

<span data-ttu-id="59c02-106">Le tableau suivant décrit un certain nombre d'états qui peuvent être utiles dans ce processus.</span><span class="sxs-lookup"><span data-stu-id="59c02-106">The following table describes a number of reports that may be useful in this process.</span></span>

| <span data-ttu-id="59c02-107">À</span><span class="sxs-lookup"><span data-stu-id="59c02-107">To</span></span> | <span data-ttu-id="59c02-108">Afficher ce rapport</span><span class="sxs-lookup"><span data-stu-id="59c02-108">See this report</span></span> |
| --- | --- |
| <span data-ttu-id="59c02-109">Imprimer un rapport Balance de vérification détaillé pour un ou plusieurs comptes bancaires avec des informations supplémentaires sur des écritures individuelles.</span><span class="sxs-lookup"><span data-stu-id="59c02-109">Print a detailed trial balance report for one or more bank accounts with additional information about individual entries.</span></span> |<span data-ttu-id="59c02-110">Banque :</span><span class="sxs-lookup"><span data-stu-id="59c02-110">Bank Acc.</span></span> <span data-ttu-id="59c02-111">Grand livre</span><span class="sxs-lookup"><span data-stu-id="59c02-111">- Detail Trial Bal.</span></span> |
| <span data-ttu-id="59c02-112">Imprimer une balance de vérification détaillée pour les clients sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="59c02-112">Print a detail trial balance for selected customers.</span></span> |<span data-ttu-id="59c02-113">Clients : Balance</span><span class="sxs-lookup"><span data-stu-id="59c02-113">Customer - Trial Balance</span></span> |
| <span data-ttu-id="59c02-114">Imprimer une balance de vérification détaillée avec des informations détaillées sur des écritures individuelles pour les clients sélectionnés et durant une période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="59c02-114">Print a detail trial balance with detailed information about individual entries, for selected customers during a selected period.</span></span> |<span data-ttu-id="59c02-115">Clients : Grand livre client</span><span class="sxs-lookup"><span data-stu-id="59c02-115">Customer - Detail Trial Bal.</span></span> |
| <span data-ttu-id="59c02-116">Imprimer une balance de vérification détaillée pour les fournisseurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="59c02-116">Print a detail trial balance for selected vendors.</span></span> |<span data-ttu-id="59c02-117">Fournisseur - Balance de vérification</span><span class="sxs-lookup"><span data-stu-id="59c02-117">Vendor - Trial Balance</span></span> |
| <span data-ttu-id="59c02-118">Imprimer une balance de vérification détaillée avec des informations détaillées sur des écritures individuelles pour les fournisseurs sélectionnés et durant une période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="59c02-118">Print a detail trial balance with detailed information about individual entries, for selected vendors during a selected period.</span></span> |<span data-ttu-id="59c02-119">Fourn. - Bal. vérif. détaillée</span><span class="sxs-lookup"><span data-stu-id="59c02-119">Vendor - Detail Trial Balance</span></span> |
| <span data-ttu-id="59c02-120">Imprimer une balance de vérification avec les chiffres de l'exercice en cours et de l'exercice précédent.</span><span class="sxs-lookup"><span data-stu-id="59c02-120">Print a trial balance with the current year's and the previous year's figures.</span></span> |<span data-ttu-id="59c02-121">Balance de vérification de fermeture</span><span class="sxs-lookup"><span data-stu-id="59c02-121">Closing Trial Balance</span></span> |
| <span data-ttu-id="59c02-122">Imprimer un rapport Balance de vérification détaillé pour les soldes des comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="59c02-122">Print a detailed trial balance report for general ledger account balances.</span></span> |<span data-ttu-id="59c02-123">Grand livre</span><span class="sxs-lookup"><span data-stu-id="59c02-123">Detail Trial Balance</span></span> |
| <span data-ttu-id="59c02-124">Imprimer un rapport Balance de vérification comprenant les soldes et les soldes période pour les comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="59c02-124">Print a trial balance report with balances and net changes for general ledger accounts.</span></span> |<span data-ttu-id="59c02-125">Balance de vérification</span><span class="sxs-lookup"><span data-stu-id="59c02-125">Trial Balance</span></span> |
| <span data-ttu-id="59c02-126">Imprimez une balance de vérification pour une compagnie consolidée.</span><span class="sxs-lookup"><span data-stu-id="59c02-126">Print a trial balance for a consolidated company.</span></span> |<span data-ttu-id="59c02-127">Balance de vérification consolidée</span><span class="sxs-lookup"><span data-stu-id="59c02-127">Consolidated Trial Balance</span></span> |

<span data-ttu-id="59c02-128">Pour afficher un état, sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez le nom tel qu'il s'affiche dans la table, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="59c02-128">To see a report, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, type the name as it appears in the table, and then choose the related link.</span></span>

## <a name="see-also"></a><span data-ttu-id="59c02-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59c02-129">See Also</span></span>
[<span data-ttu-id="59c02-130">Clôture des exercices et des périodes</span><span class="sxs-lookup"><span data-stu-id="59c02-130">Closing Years and Periods</span></span>](year-close-years-periods.md)  
<span data-ttu-id="59c02-131">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="59c02-131">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>


