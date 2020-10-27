---
title: Aperçu des rapports préalables à la fermeture pour vérifier l'exactitude des comptes | Microsoft Docs
description: Fournit un aperçu des rapports qui vous permettent de vérifier l'exactitude des comptes avant de fermer les registres à la fin d'un exercice ou d'une période.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2020
ms.author: jswymer
ms.openlocfilehash: b270a7b1f9ffda71d68fa981885aacbe31f55eab
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3923130"
---
# <a name="using-pre-closing-reports"></a><span data-ttu-id="8ded7-103">Utilisation des rapports préalables à la fermeture</span><span class="sxs-lookup"><span data-stu-id="8ded7-103">Using Pre-Closing Reports</span></span>
<span data-ttu-id="8ded7-104">Il existe de nombreux rapports standard qui vous permettent de vérifier la précision des comptes avant de fermer les registres à la fin d'un exercice ou d'une période.</span><span class="sxs-lookup"><span data-stu-id="8ded7-104">There are many standard reports that you can use to verify the accuracy of the accounts before closing the books at the end of a year or period.</span></span> <span data-ttu-id="8ded7-105">Par exemple, vous pouvez utiliser l'état **Clients : Balance** pour vérifier que le solde d'un groupe comptabilisation client est égal au solde du compte général correspondant à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="8ded7-105">For example, you can use the **Customer - Trial Balance** report to verify that the balance for a customer posting group is equal to the balance on the corresponding general ledger account on a certain date.</span></span>

<span data-ttu-id="8ded7-106">Le tableau suivant décrit un certain nombre d'états qui peuvent être utiles dans ce processus.</span><span class="sxs-lookup"><span data-stu-id="8ded7-106">The following table describes a number of reports that may be useful in this process.</span></span>

| <span data-ttu-id="8ded7-107">À</span><span class="sxs-lookup"><span data-stu-id="8ded7-107">To</span></span> | <span data-ttu-id="8ded7-108">Afficher ce rapport</span><span class="sxs-lookup"><span data-stu-id="8ded7-108">See this report</span></span> |
| --- | --- |
| <span data-ttu-id="8ded7-109">Imprimer un rapport Balance de vérification détaillé pour un ou plusieurs comptes bancaires avec des informations supplémentaires sur des écritures individuelles.</span><span class="sxs-lookup"><span data-stu-id="8ded7-109">Print a detailed trial balance report for one or more bank accounts with additional information about individual entries.</span></span> |<span data-ttu-id="8ded7-110">Compte bancaire - Balance de vérification détaillée</span><span class="sxs-lookup"><span data-stu-id="8ded7-110">Bank Acc. - Detail Trial Bal.</span></span> |
| <span data-ttu-id="8ded7-111">Imprimer une balance de vérification détaillée pour les clients sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8ded7-111">Print a detail trial balance for selected customers.</span></span> |<span data-ttu-id="8ded7-112">Clients : Balance</span><span class="sxs-lookup"><span data-stu-id="8ded7-112">Customer - Trial Balance</span></span> |
| <span data-ttu-id="8ded7-113">Imprimer une balance de vérification détaillée avec des informations détaillées sur des écritures individuelles pour les clients sélectionnés et durant une période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8ded7-113">Print a detail trial balance with detailed information about individual entries, for selected customers during a selected period.</span></span> |<span data-ttu-id="8ded7-114">Clients : Grand livre client</span><span class="sxs-lookup"><span data-stu-id="8ded7-114">Customer - Detail Trial Bal.</span></span> |
| <span data-ttu-id="8ded7-115">Imprimer une balance de vérification détaillée pour les fournisseurs sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="8ded7-115">Print a detail trial balance for selected vendors.</span></span> |<span data-ttu-id="8ded7-116">Fournisseur - Balance de vérification</span><span class="sxs-lookup"><span data-stu-id="8ded7-116">Vendor - Trial Balance</span></span> |
| <span data-ttu-id="8ded7-117">Imprimer une balance de vérification détaillée avec des informations détaillées sur des écritures individuelles pour les fournisseurs sélectionnés et durant une période sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="8ded7-117">Print a detail trial balance with detailed information about individual entries, for selected vendors during a selected period.</span></span> |<span data-ttu-id="8ded7-118">Fourn. - Bal. vérif. détaillée</span><span class="sxs-lookup"><span data-stu-id="8ded7-118">Vendor - Detail Trial Balance</span></span> |
| <span data-ttu-id="8ded7-119">Imprimer une balance de vérification avec les chiffres de l'exercice en cours et de l'exercice précédent.</span><span class="sxs-lookup"><span data-stu-id="8ded7-119">Print a trial balance with the current year's and the previous year's figures.</span></span> |<span data-ttu-id="8ded7-120">Balance de vérification de fermeture</span><span class="sxs-lookup"><span data-stu-id="8ded7-120">Closing Trial Balance</span></span> |
| <span data-ttu-id="8ded7-121">Imprimer un rapport Balance de vérification détaillé pour les soldes des comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="8ded7-121">Print a detailed trial balance report for general ledger account balances.</span></span> |<span data-ttu-id="8ded7-122">Grand livre</span><span class="sxs-lookup"><span data-stu-id="8ded7-122">Detail Trial Balance</span></span> |
| <span data-ttu-id="8ded7-123">Imprimer un rapport Balance de vérification comprenant les soldes et les soldes période pour les comptes du grand livre.</span><span class="sxs-lookup"><span data-stu-id="8ded7-123">Print a trial balance report with balances and net changes for general ledger accounts.</span></span> |<span data-ttu-id="8ded7-124">Balance de vérification</span><span class="sxs-lookup"><span data-stu-id="8ded7-124">Trial Balance</span></span> |
| <span data-ttu-id="8ded7-125">Imprimez une balance de vérification pour une compagnie consolidée.</span><span class="sxs-lookup"><span data-stu-id="8ded7-125">Print a trial balance for a consolidated company.</span></span> |<span data-ttu-id="8ded7-126">Balance de vérification consolidée</span><span class="sxs-lookup"><span data-stu-id="8ded7-126">Consolidated Trial Balance</span></span> |

<span data-ttu-id="8ded7-127">Pour visualiser un rapport, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez le nom qui s'affiche dans la table, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8ded7-127">To see a report, choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, type the name as it appears in the table, and then choose the related link.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ded7-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8ded7-128">See Also</span></span>
[<span data-ttu-id="8ded7-129">Clôture des exercices et des périodes</span><span class="sxs-lookup"><span data-stu-id="8ded7-129">Closing Years and Periods</span></span>](year-close-years-periods.md)  
<span data-ttu-id="8ded7-130">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="8ded7-130">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

