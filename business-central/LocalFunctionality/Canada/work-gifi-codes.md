---
title: Codes IGRF au Canada | Microsoft Docs
Description: Au Canada, vous pouvez définir l'Index général des renseignements financiers (IGRF) et l'affecter aux comptes de report
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 6d9ae9d4631581d1d5497e3741ed160d403849ee
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3916436"
---
# <a name="work-with-gifi-codes"></a><span data-ttu-id="bcfaa-103">Utiliser des codes IGRF</span><span class="sxs-lookup"><span data-stu-id="bcfaa-103">Work With GIFI Codes</span></span>
<span data-ttu-id="bcfaa-104">Les informations fiscales peuvent inclure des comptes généraux, des états, des comptes de gestion, des bilans et des relevés des bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-104">Fiscal information can include general ledger accounts, reports, income statements, balance sheets, and statements of retained earnings.</span></span> <span data-ttu-id="bcfaa-105">Les informations fiscales sont classifiées par le biais de codes.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-105">Fiscal information is classified using codes.</span></span> <span data-ttu-id="bcfaa-106">L'utilisation de codes aide le gouvernemental à traiter les informations, à préparer l'archivage électronique et à valider les informations fiscales par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-106">The use of codes helps the government to process information, prepare for electronic filing, and validate tax information electronically.</span></span> <span data-ttu-id="bcfaa-107">L'utilisation de codes aide également les organisations statistiques à travailler plus efficacement, en rendant les données financières plus facilement disponibles.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-107">The use of codes also helps statistical organizations to work more efficiently, as financial information is more readily available.</span></span> <span data-ttu-id="bcfaa-108">Pour plus d'informations, reportez-vous au [site Web de l'Agence de revenu du Canada](https://www.cra-arc.gc.ca/).</span><span class="sxs-lookup"><span data-stu-id="bcfaa-108">For more information, see the [Canada Revenue Agency website](https://www.cra-arc.gc.ca/).</span></span>

<span data-ttu-id="bcfaa-109">L'Agence de revenu du Canada utilise les codes IGRF (Index général des renseignements financiers) pour recueillir, valider et traiter les informations financières et fiscales par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-109">The Canada Revenue Agency uses General Index of Financial Information (GIFI) codes to collect, validate, and process financial and tax information electronically.</span></span> <span data-ttu-id="bcfaa-110">Les meilleures pratiques suggèrent d'attribuer des codes IGRF uniquement aux comptes de report, afin que tous les totaux soient calculés par votre logiciel d'établissement des déclarations fiscales.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-110">It is a best practice to assign GIFI codes only to posting accounts, so that all totaling is done by your tax preparation software.</span></span>

<span data-ttu-id="bcfaa-111">Lorsqu'un compte est associé à un code IGRF, il est enregistré auprès de l'Agence de revenus sous ce code.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-111">When an account is associated with a GIFI code, it is reported to the revenue agency under that code.</span></span> <span data-ttu-id="bcfaa-112">Plusieurs comptes peuvent avoir le même code IGRF, mais chaque compte doit avoir un seul code IGRF.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-112">Multiple accounts can all have the same GIFI code, but each account can have only one GIFI code.</span></span>

<span data-ttu-id="bcfaa-113">Vous pouvez exporter les informations de solde par code IGRF et enregistrer le fichier exporté dans Excel, ce qui est utile pour transférer des informations vers votre logiciel d'établissement des déclarations fiscales.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-113">You can export balance information by GIFI code and save the exported file in Excel, which is useful for transferring information to your tax preparation software.</span></span>

## <a name="to-set-up-gifi-codes"></a><span data-ttu-id="bcfaa-114">Pour configurer des codes IGRF</span><span class="sxs-lookup"><span data-stu-id="bcfaa-114">To set up GIFI codes</span></span>
<span data-ttu-id="bcfaa-115">Dans [!INCLUDE[d365fin](../../includes/d365fin_md.md)], vous devez configurer des codes IGRF pour les comptes GL, les rapports, les bilans, les états de résultats et les relevés de bénéfices non répartis.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-115">In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you must set up GIFI codes for general ledger accounts, reports, balance sheets, income sheets, and statements of retained earnings.</span></span>

1. <span data-ttu-id="bcfaa-116">Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Codes IGRF**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-116">Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **GIFI Codes**, and then choose the related link.</span></span>
2. <span data-ttu-id="bcfaa-117">Sur la page **Codes IGRF**, sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-117">On the **GIFI Codes** page, choose the **New** action.</span></span>
3. <span data-ttu-id="bcfaa-118">Configurer les codes IGRF en renseignant les champs.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-118">Set up GIFI codes by filling the fields.</span></span> [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]

## <a name="to-associate-gifi-codes-with-gl-accounts"></a><span data-ttu-id="bcfaa-119">Pour associer des codes IGRF avec des comptes généraux</span><span class="sxs-lookup"><span data-stu-id="bcfaa-119">To associate GIFI codes with G/L accounts</span></span>
<span data-ttu-id="bcfaa-120">Pour enregistrer des données financières par code IGRF, chaque code IGRF doit être associé aux comptes appropriés dans le plan comptable.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-120">To report financial information by GIFI code, each GIFI code must be associated with the appropriate accounts in the chart of accounts.</span></span>

1. <span data-ttu-id="bcfaa-121">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Plan comptable**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-121">Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>
2. <span data-ttu-id="bcfaa-122">Sélectionnez un compte général approprié, puis sélectionnez l'action **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-122">Select a relevant general ledger account, and then choose the **Edit** action.</span></span>
3. <span data-ttu-id="bcfaa-123">Sur le raccourci **Comptabilité analytique**, dans le champ **Code IGRF**, sélectionnez un code IGRF approprié.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-123">On the **Cost Accounting** FastTab, in the **GIFI Code** field, select an appropriate GIFI code.</span></span>

## <a name="to-view-account-balances-using-the-gifi-code-report"></a><span data-ttu-id="bcfaa-124">Pour afficher les soldes de compte à l'aide du rapport de code IGRF</span><span class="sxs-lookup"><span data-stu-id="bcfaa-124">To view account balances using the GIFI code report</span></span>
<span data-ttu-id="bcfaa-125">Vous pouvez consulter vos soldes de compte par code IGRF par le biais de l'état **Soldes de compte par code IGRF**.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-125">You can review your account balances by GIFI code by using the **Account Balances by GIFI Code** report.</span></span>

1. <span data-ttu-id="bcfaa-126">Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Soldes de compte par code IGRF**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-126">Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Account Balances by GIFI Code**, and then choose the related link.</span></span>
2. <span data-ttu-id="bcfaa-127">Spécifiez les éléments à inclure dans le rapport en renseignant les champs.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-127">Specify what to include in the report by filling the fields.</span></span> [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="bcfaa-128">Cliquez sur le bouton **Imprimer** ou **Aperçu**.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-128">Choose the **Print** or the **Preview** button.</span></span>

## <a name="to-export-balance-information-using-gifi-codes"></a><span data-ttu-id="bcfaa-129">Pour exporter les informations de solde à l'aide de codes IGRF</span><span class="sxs-lookup"><span data-stu-id="bcfaa-129">To export balance information using GIFI codes</span></span>
<span data-ttu-id="bcfaa-130">Vous pouvez exporter les informations de solde à l'aide de codes IGRF et enregistrer le fichier exporté dans Excel.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-130">You can export balance information using GIFI codes and save the exported file in Excel.</span></span> <span data-ttu-id="bcfaa-131">Vous pouvez modifier, enregistrer ou supprimer, le fichier.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-131">You can modify, save, or delete the file.</span></span> <span data-ttu-id="bcfaa-132">Ce fichier vous permet de transférer des informations vers votre logiciel d'établissement des déclarations fiscales.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-132">You can use the file to transfer information to your tax preparation software.</span></span>

1. <span data-ttu-id="bcfaa-133">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Exporter données IGRF vers fichier Excel**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-133">Choose the ![Lightbulb that opens the Tell Me feature](../../media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Export GIFI Info. to Excel**, and then choose the related link.</span></span>
2. <span data-ttu-id="bcfaa-134">Spécifiez les éléments à exporter vers Excel en renseignant les champs.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-134">Specify what to export to Excel by filling the fields.</span></span> [!INCLUDE[tooltip-inline-tip](../../includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="bcfaa-135">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-135">Choose the **OK** button.</span></span>

> [!NOTE]  
>   <span data-ttu-id="bcfaa-136">Le fichier Excel est doté des caractéristiques suivantes :</span><span class="sxs-lookup"><span data-stu-id="bcfaa-136">The Excel file has the following characteristics:</span></span>

* <span data-ttu-id="bcfaa-137">Le solde est arrondi au point de pourcentage le plus proche, mais la valeur de la cellule indique le même pourcentage que dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-137">The balance is rounded to the nearest percentage, but the cell value maintains the same percentage as it does in the general ledger.</span></span>
* <span data-ttu-id="bcfaa-138">Les nombres négatifs sont représentés comme des nombres positifs entre parenthèses.</span><span class="sxs-lookup"><span data-stu-id="bcfaa-138">Negative numbers are represented as positive number in brackets.</span></span> <span data-ttu-id="bcfaa-139">Par conséquent, -123 est représenté comme suit : (123).</span><span class="sxs-lookup"><span data-stu-id="bcfaa-139">Accordingly, -123 is represented as (123).</span></span>

## <a name="see-also"></a><span data-ttu-id="bcfaa-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bcfaa-140">See Also</span></span>
[<span data-ttu-id="bcfaa-141">Fonctionnalités locales Canada</span><span class="sxs-lookup"><span data-stu-id="bcfaa-141">Canada Local Functionality</span></span>](canada-local-functionality.md)  
<span data-ttu-id="bcfaa-142">[Finance](../../finance.md) </span><span class="sxs-lookup"><span data-stu-id="bcfaa-142">[Finance](../../finance.md) </span></span>  
[<span data-ttu-id="bcfaa-143">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="bcfaa-143">Setting Up Finance</span></span>](../../finance.md)
