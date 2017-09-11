---
title: "Affecter des écritures dans des devises différentes| Microsoft Docs"
description: "Vous pouvez affecter des écritures du grand livre dans différentes devises, par exemple si vous vendez à un client dans une devise et recevez le paiement dans une autre devise."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: multiple currencies, payment, reconcile
ms.date: 06/02/2017
ms.author: edupont
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 035f4c0e98e3b7ba308319c2017568de832e26c5
ms.contentlocale: fr-ca
ms.lasthandoff: 09/11/2017

---
# <a name="how-to-enable-application-of-ledger-entries-in-different-currencies"></a><span data-ttu-id="5520a-103">Procédure : activer l'affectation des écritures en devises différentes</span><span class="sxs-lookup"><span data-stu-id="5520a-103">How to: Enable Application of Ledger Entries in Different Currencies</span></span>
<span data-ttu-id="5520a-104">Si vous achetez des produits auprès d'un fournisseur dans une devise et que vous payez ces produits dans une autre devise, vous pouvez affecter le paiement à l'achat.</span><span class="sxs-lookup"><span data-stu-id="5520a-104">If you purchase from a vendor in one currency and submit payment in another currency, you can apply the payment to the purchase.</span></span>

<span data-ttu-id="5520a-105">De même, si vous effectuez une vente à un client dans une devise et recevez le règlement dans une autre devise, vous pouvez affecter le règlement à la facture vente.</span><span class="sxs-lookup"><span data-stu-id="5520a-105">Likewise, if you sell to a customer in one currency and receive payment in another currency, you can apply the payment to the sales invoice.</span></span>

<span data-ttu-id="5520a-106">La procédure suivante indique comment configurer cela pour les écritures comptables fournisseur dans la fenêtre **Paramètres achats**.</span><span class="sxs-lookup"><span data-stu-id="5520a-106">The following procedure describes how to set this up for vendor ledger entries in the **Purchases & Payables Setup** window.</span></span> <span data-ttu-id="5520a-107">La configuration est semblable à celle des écritures comptables client dans la fenêtre **Paramètres ventes**.</span><span class="sxs-lookup"><span data-stu-id="5520a-107">The setup is similar for customer ledger entries in the **Sales & Receivables Setup** window.</span></span>

> [!NOTE]  
>   <span data-ttu-id="5520a-108">Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**.</span><span class="sxs-lookup"><span data-stu-id="5520a-108">This functionality requires that your experience is set to **Suite**.</span></span> <span data-ttu-id="5520a-109">Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).</span><span class="sxs-lookup"><span data-stu-id="5520a-109">For more information, see [Customizing Your [!INCLUDE[d365fin](includes/d365fin_md.md)] Experience](ui-experiences.md).</span></span>

## <a name="to-enable-application-of-vendor-ledger-entries-in-different-currencies"></a><span data-ttu-id="5520a-110">Pour activer l'affectation des écritures fournisseur en devises différentes</span><span class="sxs-lookup"><span data-stu-id="5520a-110">To enable application of vendor ledger entries in different currencies</span></span>
1. <span data-ttu-id="5520a-111">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Paramètres achats**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="5520a-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchases & Payables Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="5520a-112">Dans le champ **Lettrage entre devises**, sélectionnez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="5520a-112">In the **Appln. between Currencies** field, select one of the following options.</span></span>

| <span data-ttu-id="5520a-113">Option</span><span class="sxs-lookup"><span data-stu-id="5520a-113">Option</span></span> | <span data-ttu-id="5520a-114">Description</span><span class="sxs-lookup"><span data-stu-id="5520a-114">Description</span></span> |
| --- | --- |
| <span data-ttu-id="5520a-115">Aucun</span><span class="sxs-lookup"><span data-stu-id="5520a-115">None</span></span> |<span data-ttu-id="5520a-116">L'affectation entre devises n'est pas autorisée.</span><span class="sxs-lookup"><span data-stu-id="5520a-116">Application between currencies is not allowed.</span></span> |
| <span data-ttu-id="5520a-117">Devises U.M.E.</span><span class="sxs-lookup"><span data-stu-id="5520a-117">EMU</span></span> |<span data-ttu-id="5520a-118">L'affectation entre devises UME est autorisée.</span><span class="sxs-lookup"><span data-stu-id="5520a-118">Application between EMU currencies is allowed.</span></span> |
| <span data-ttu-id="5520a-119">Tout</span><span class="sxs-lookup"><span data-stu-id="5520a-119">All</span></span> |<span data-ttu-id="5520a-120">L'affectation entre toutes les devises est autorisée.</span><span class="sxs-lookup"><span data-stu-id="5520a-120">Application between all currencies is allowed.</span></span> |

## <a name="see-also"></a><span data-ttu-id="5520a-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="5520a-121">See Also</span></span>
[<span data-ttu-id="5520a-122">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="5520a-122">Managing Payables</span></span>](payables-manage-payables.md)  
[<span data-ttu-id="5520a-123">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="5520a-123">Managing Receivables</span></span>](receivables-manage-receivables.md)  
<span data-ttu-id="5520a-124">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="5520a-124">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

