---
title: "Affecter un niveau de priorité à un fournisseur | Microsoft Docs"
description: "Vous pouvez affecter des numéros à vos fournisseurs pour les classer par ordre de priorité et faciliter des propositions de paiement dans Business Central."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: supplier, payment priority
ms.date: 03/29/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: f7834f0f99b775125425eb7209c3c648de4ccd1f
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="prioritize-vendors"></a><span data-ttu-id="f921c-103">Octroyer une priorité aux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="f921c-103">Prioritize Vendors</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="f921c-104"> peut proposer différents paiements aux fournisseurs, par exemple les paiements arrivant à échéance ou les paiements donnant lieu à un escompte.</span><span class="sxs-lookup"><span data-stu-id="f921c-104"> can suggest various payments to vendors, for example, payments that will be due soon or payments where a discount is available.</span></span> <span data-ttu-id="f921c-105">Pour plus d'informations, reportez vous à [Proposer des paiements fournisseur](payables-how-suggest-vendor-payments.md).</span><span class="sxs-lookup"><span data-stu-id="f921c-105">For more information, see [Suggest Vendor Payments](payables-how-suggest-vendor-payments.md).</span></span>

<span data-ttu-id="f921c-106">Tout d'abord, vous devez attribuer une priorité à vos fournisseurs en leur affectant des numéros.</span><span class="sxs-lookup"><span data-stu-id="f921c-106">First, you must prioritize your vendors by assigning numbers to them.</span></span>

## <a name="to-prioritize-vendors"></a><span data-ttu-id="f921c-107">Pour octroyer une priorité à des fournisseurs</span><span class="sxs-lookup"><span data-stu-id="f921c-107">To prioritize vendors</span></span>
1. <span data-ttu-id="f921c-108">Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Comptes bancaires**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="f921c-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Vendors**, and then choose the related link.</span></span>
2. <span data-ttu-id="f921c-109">Sélectionnez le fournisseur approprié, puis sélectionnez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="f921c-109">Select the relevant vendor, and then choose **Edit**.</span></span>
3. <span data-ttu-id="f921c-110">Dans le champ **Priorité**, entrez un numéro.</span><span class="sxs-lookup"><span data-stu-id="f921c-110">In the **Priority** field, enter a number.</span></span>

[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="f921c-111"> donne le degré de priorité le plus élevé au chiffre le plus bas, excepté 0.</span><span class="sxs-lookup"><span data-stu-id="f921c-111"> considers the lowest number, except 0, to have the highest priority.</span></span> <span data-ttu-id="f921c-112">Ainsi, si vous utilisez 1, 2 et 3, le chiffre 1 a le degré de priorité le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="f921c-112">So, for example, if you use 1, 2, and 3, then 1 will have the highest priority.</span></span>

<span data-ttu-id="f921c-113">Si vous ne souhaitez pas attribuer de priorité à un fournisseur, laissez le champ **Priorité** blanc.</span><span class="sxs-lookup"><span data-stu-id="f921c-113">If you do not want to prioritize a vendor, leave the **Priority** field blank.</span></span> <span data-ttu-id="f921c-114">Par la suite, lorsque vous utilisez la fonction de proposition de paiements, ce fournisseur est répertorié après tous les fournisseurs possédant un numéro prioritaire.</span><span class="sxs-lookup"><span data-stu-id="f921c-114">Then, if you use the payment suggestion feature, the vendor will be listed after all the vendors that have a priority number.</span></span> <span data-ttu-id="f921c-115">Vous pouvez saisir autant de niveaux de priorité que nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f921c-115">You can enter as many priority levels as necessary.</span></span>

## <a name="see-also"></a><span data-ttu-id="f921c-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f921c-116">See Also</span></span>
[<span data-ttu-id="f921c-117">Définition des achats</span><span class="sxs-lookup"><span data-stu-id="f921c-117">Setting Up Purchasing</span></span>](purchasing-setup-purchasing.md)  
[<span data-ttu-id="f921c-118">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="f921c-118">Managing Payables</span></span>](payables-manage-payables.md)  
<span data-ttu-id="f921c-119">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f921c-119">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
