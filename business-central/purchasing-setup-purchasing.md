---
title: Aperçu des tâches permettant de paramétrer vos achats | Microsoft Docs
description: Décrit les tâches permettant de définir les stratégies d'approvisionnement de votre compagnie et de déterminer vos processus d'achat.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: procurement, supply, vendor order
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 9d0058c707862144592278d08a494175adf67a2a
ms.sourcegitcommit: f9a190933eadf4608f591e2f1b04c69f1e5c0dc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115446"
---
# <a name="setting-up-purchasing"></a><span data-ttu-id="b2488-103">Définition des achats</span><span class="sxs-lookup"><span data-stu-id="b2488-103">Setting Up Purchasing</span></span>
<span data-ttu-id="b2488-104">Avant de pouvoir gérer les processus achat, vous devez configurer les règles et valeurs qui définissent les stratégies d'achat de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="b2488-104">Before you can manage purchase processes, you must configure the rules and values that define the company's purchase policies.</span></span>

<span data-ttu-id="b2488-105">Vous devez définir la configuration générale, notamment les documents achat requis et le mode de report des valeurs correspondantes.</span><span class="sxs-lookup"><span data-stu-id="b2488-105">You must define the general setup, such as which purchase documents are required and how their values are posted.</span></span> <span data-ttu-id="b2488-106">Celle-ci a généralement lieu une seule fois au cours de la phase initiale de l'implémentation.</span><span class="sxs-lookup"><span data-stu-id="b2488-106">This general setup is typically performed once during the initial implementation.</span></span>

<span data-ttu-id="b2488-107">Une série de tâches distincte en relation avec l'enregistrement de nouveaux fournisseurs consiste à enregistrer les ententes spéciales sur les prix ou escomptes établies avec chaque fournisseur.</span><span class="sxs-lookup"><span data-stu-id="b2488-107">A separate series of tasks related to registering new vendors is to record any special price or discount agreements that you have with each vendor.</span></span>

<span data-ttu-id="b2488-108">Les configurations relatives à la finance, telles que les modes de règlement et les devises, sont traitées dans la section Paramètres financiers.</span><span class="sxs-lookup"><span data-stu-id="b2488-108">Finance-related purchase setup, such as payment methods and currencies, are covered in the Finance Setup section.</span></span> <span data-ttu-id="b2488-109">Pour plus d'informations, reportez-vous à [Configuration de Finance](finance-setup-finance.md).</span><span class="sxs-lookup"><span data-stu-id="b2488-109">For more information, see [Setting Up Finance](finance-setup-finance.md).</span></span>

| <span data-ttu-id="b2488-110">À</span><span class="sxs-lookup"><span data-stu-id="b2488-110">To</span></span> | <span data-ttu-id="b2488-111">Voir</span><span class="sxs-lookup"><span data-stu-id="b2488-111">See</span></span> |
| --- | --- |
| <span data-ttu-id="b2488-112">Créer une fiche fournisseur pour chaque fournisseur auquel vous achetez des biens</span><span class="sxs-lookup"><span data-stu-id="b2488-112">Create a vendor card for each vendor that you purchase from</span></span>|[<span data-ttu-id="b2488-113">Enregistrer de nouveaux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b2488-113">Register New Vendors</span></span>](purchasing-how-register-new-vendors.md) |
| <span data-ttu-id="b2488-114">Entrer les différents escomptes et prix spéciaux que vous accordent les fournisseurs en fonction de l'article, des quantités et/ou de la date</span><span class="sxs-lookup"><span data-stu-id="b2488-114">Enter the different discounts and special prices that vendors grant you depending on item, quantities, and/or date</span></span> |[<span data-ttu-id="b2488-115">Enregistrer des accords sur les prix d'achat, les remises et les paiements</span><span class="sxs-lookup"><span data-stu-id="b2488-115">Record Purchase Price, Discount, and Payment Agreements</span></span>](purchasing-how-record-purchase-price-discount-payment-agreements.md) |
| <span data-ttu-id="b2488-116">Octroyer une priorité aux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b2488-116">Prioritize vendors</span></span> |[<span data-ttu-id="b2488-117">Octroyer une priorité aux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="b2488-117">Prioritize Vendors</span></span>](purchasing-how-prioritize-vendors.md) |
| <span data-ttu-id="b2488-118">Configurer les acheteurs</span><span class="sxs-lookup"><span data-stu-id="b2488-118">Set up purchasers</span></span> |[<span data-ttu-id="b2488-119">Configurer les acheteurs</span><span class="sxs-lookup"><span data-stu-id="b2488-119">Set Up Purchasers</span></span>](purchasing-how-setup-purchasers.md) |
|<span data-ttu-id="b2488-120">Spécifiez les rapports par défaut à utiliser pour différents types de documents.</span><span class="sxs-lookup"><span data-stu-id="b2488-120">Specify default reports to be used for different document types.</span></span>|[<span data-ttu-id="b2488-121">Sélection des rapports dans Business Central</span><span class="sxs-lookup"><span data-stu-id="b2488-121">Report Selection in Business Central</span></span>](across-report-selections.md)|

> [!TIP]
> <span data-ttu-id="b2488-122">En fonction de votre emplacement géographique, certaines pages peuvent contenir des champs qui ne sont pas décrits dans les articles répertoriés ici, car ils s’appliquent à des fonctionnalités locales ou à des personnalisations.</span><span class="sxs-lookup"><span data-stu-id="b2488-122">Depending on your geographical location, some pages can contain fields that are not described in the articles that are listed here because they apply to local functionality or customizations.</span></span> [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## <a name="external-document-number"></a><span data-ttu-id="b2488-123">Numéro de document externe</span><span class="sxs-lookup"><span data-stu-id="b2488-123">External document number</span></span>

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="see-related-training-at-microsoft-learn"></a><span data-ttu-id="b2488-124">Voir la formation associée sur [Microsoft Learn](/learn/paths/trade-get-started-dynamics-365-business-central/)</span><span class="sxs-lookup"><span data-stu-id="b2488-124">See Related Training at [Microsoft Learn](/learn/paths/trade-get-started-dynamics-365-business-central/)</span></span>

## <a name="see-also"></a><span data-ttu-id="b2488-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2488-125">See Also</span></span>

[<span data-ttu-id="b2488-126">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="b2488-126">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="b2488-127">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="b2488-127">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]