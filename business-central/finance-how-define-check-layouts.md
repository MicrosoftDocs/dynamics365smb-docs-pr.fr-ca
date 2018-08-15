---
title: "Spécifier la mise en page d'un chèque| Microsoft Docs"
description: "Vous pouvez concevoir et imprimer vos chèques dans différents formats pour respecter des normes."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: print check, customize
ms.date: 06/15/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: d48b7954402b96c1bb5d3a2a63c70f48c6a4f9d7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="define-check-layouts"></a><span data-ttu-id="eea98-103">Définir les mises en page de chèques</span><span class="sxs-lookup"><span data-stu-id="eea98-103">Define Check Layouts</span></span>
<span data-ttu-id="eea98-104">Vous pouvez concevoir vos chèques de sorte à respecter les normes fixées par les autorités locales.</span><span class="sxs-lookup"><span data-stu-id="eea98-104">You can design your checks to conform with the standards set by the local authorities.</span></span> <span data-ttu-id="eea98-105">Vous pouvez imprimer des images de chèques en anglais, en français ou en espagnol.</span><span class="sxs-lookup"><span data-stu-id="eea98-105">Check images can be printed in English, French, or Spanish.</span></span>

<span data-ttu-id="eea98-106">Les chèques sont conçus pour être imprimés aux formats d'image de chèques américains et canadiens, soit au format chèque-talon-chèque, soit au format talon-talon-chèque.</span><span class="sxs-lookup"><span data-stu-id="eea98-106">Checks are designed to print in both the United States and Canadian check image formats in either a check-stub-check format or a stub-stub-check format.</span></span>

## <a name="to-define-check-layouts"></a><span data-ttu-id="eea98-107">Pour définir les mises en page de chèques</span><span class="sxs-lookup"><span data-stu-id="eea98-107">To define check layouts</span></span>
1. <span data-ttu-id="eea98-108">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Sélection des états - Compte bancaire**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eea98-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Selections Bank Account**, and then choose the related link.</span></span>
2. <span data-ttu-id="eea98-109">Dans la fenêtre **Sélection du rapport - compte bancaire**, dans le champ **Utilisation**, sélectionnez **Chèque**.</span><span class="sxs-lookup"><span data-stu-id="eea98-109">In the **Report Selection - Bank Acc.** window, in the **Usage** field, select **Check**.</span></span>
3. <span data-ttu-id="eea98-110">Sélectionnez l'un des codes rapport suivants.</span><span class="sxs-lookup"><span data-stu-id="eea98-110">Select one of the following report IDs.</span></span>

| <span data-ttu-id="eea98-111">Code rapport</span><span class="sxs-lookup"><span data-stu-id="eea98-111">Report ID</span></span> | <span data-ttu-id="eea98-112">Nom du rapport</span><span class="sxs-lookup"><span data-stu-id="eea98-112">Report Name</span></span> | <span data-ttu-id="eea98-113">Description</span><span class="sxs-lookup"><span data-stu-id="eea98-113">Description</span></span> |
| --- | --- | --- |
| <span data-ttu-id="eea98-114">1401</span><span class="sxs-lookup"><span data-stu-id="eea98-114">1401</span></span> |<span data-ttu-id="eea98-115">Activer</span><span class="sxs-lookup"><span data-stu-id="eea98-115">Check</span></span> |<span data-ttu-id="eea98-116">Il s'agit du rapport par défaut.</span><span class="sxs-lookup"><span data-stu-id="eea98-116">This is the default report.</span></span> |
| <span data-ttu-id="eea98-117">10401</span><span class="sxs-lookup"><span data-stu-id="eea98-117">10401</span></span> |<span data-ttu-id="eea98-118">Chèque (Talon/Talon/Chèque)</span><span class="sxs-lookup"><span data-stu-id="eea98-118">Check (Stub/Stub/Check)</span></span> |<span data-ttu-id="eea98-119">Ce rapport est conçu pour imprimer des chèques au format talon/talon/chèque.</span><span class="sxs-lookup"><span data-stu-id="eea98-119">This report is designed to print checks in a stub/stub/check format.</span></span> |
| <span data-ttu-id="eea98-120">10411</span><span class="sxs-lookup"><span data-stu-id="eea98-120">10411</span></span> |<span data-ttu-id="eea98-121">Chèque (Talon/Chèque/Talon)</span><span class="sxs-lookup"><span data-stu-id="eea98-121">Check (Stub/Check/Stub)</span></span> |<span data-ttu-id="eea98-122">Ce rapport est conçu pour imprimer des chèques au format chèque/talon/chèque.</span><span class="sxs-lookup"><span data-stu-id="eea98-122">This report is designed to print checks in a check/stub/check format.</span></span> |

<span data-ttu-id="eea98-123">Une fois que vous avez défini les mises en page de chèques, vous pouvez imprimer des chèques à partir de la fenêtre **Feuille paiement**.</span><span class="sxs-lookup"><span data-stu-id="eea98-123">When you have set up check layouts, you can print checks from the **Payment Journal** window.</span></span> <span data-ttu-id="eea98-124">Pour plus d'informations, reportez-vous à [Utilisation des chèques](payables-how-work-checks.md).</span><span class="sxs-lookup"><span data-stu-id="eea98-124">For more information, see [Work with Checks](payables-how-work-checks.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="eea98-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eea98-125">See Also</span></span>
[<span data-ttu-id="eea98-126">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="eea98-126">Managing Payables</span></span>](payables-manage-payables.md)  
<span data-ttu-id="eea98-127">[Gestion des comptes bancaires](bank-manage-bank-accounts.md) </span><span class="sxs-lookup"><span data-stu-id="eea98-127">[Managing Bank Accounts](bank-manage-bank-accounts.md) </span></span>  
[<span data-ttu-id="eea98-128">Exécution des processus de clôture d'exercice</span><span class="sxs-lookup"><span data-stu-id="eea98-128">Completing Period-End Processes</span></span>](year-how-complete-period-end-processes.md)  
<span data-ttu-id="eea98-129">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="eea98-129">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="eea98-130">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="eea98-130">General Business Functionality</span></span>](ui-across-business-areas.md)
