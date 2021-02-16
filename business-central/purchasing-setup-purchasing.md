---
title: Aperçu des tâches permettant de paramétrer vos achats | Microsoft Docs
description: Décrit les tâches permettant de définir les stratégies d'approvisionnement de votre compagnie et de déterminer vos processus d'achat.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: procurement, supply, vendor order
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 219c1fcf1d4929a548f9a8d5849dde77f1c0b24a
ms.sourcegitcommit: 32bfc2acaaf3693afc9aeb86feea505fd328caa1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/19/2021
ms.locfileid: "5024597"
---
# <a name="setting-up-purchasing"></a><span data-ttu-id="9fd20-103">Définition des achats</span><span class="sxs-lookup"><span data-stu-id="9fd20-103">Setting Up Purchasing</span></span>
<span data-ttu-id="9fd20-104">Avant de pouvoir gérer les processus achat, vous devez configurer les règles et valeurs qui définissent les stratégies d'achat de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="9fd20-104">Before you can manage purchase processes, you must configure the rules and values that define the company's purchase policies.</span></span>

<span data-ttu-id="9fd20-105">Vous devez définir la configuration générale, notamment les documents achat requis et le mode de report des valeurs correspondantes.</span><span class="sxs-lookup"><span data-stu-id="9fd20-105">You must define the general setup, such as which purchase documents are required and how their values are posted.</span></span> <span data-ttu-id="9fd20-106">Celle-ci a généralement lieu une seule fois au cours de la phase initiale de l'implémentation.</span><span class="sxs-lookup"><span data-stu-id="9fd20-106">This general setup is typically performed once during the initial implementation.</span></span>

<span data-ttu-id="9fd20-107">Une série de tâches distincte en relation avec l'enregistrement de nouveaux fournisseurs consiste à enregistrer les ententes spéciales sur les prix ou escomptes établies avec chaque fournisseur.</span><span class="sxs-lookup"><span data-stu-id="9fd20-107">A separate series of tasks related to registering new vendors is to record any special price or discount agreements that you have with each vendor.</span></span>

<span data-ttu-id="9fd20-108">Les configurations relatives à la finance, telles que les modes de règlement et les devises, sont traitées dans la section Paramètres financiers.</span><span class="sxs-lookup"><span data-stu-id="9fd20-108">Finance-related purchase setup, such as payment methods and currencies, are covered in the Finance Setup section.</span></span> <span data-ttu-id="9fd20-109">Pour plus d'informations, reportez-vous à [Configuration de Finance](finance-setup-finance.md).</span><span class="sxs-lookup"><span data-stu-id="9fd20-109">For more information, see [Setting Up Finance](finance-setup-finance.md).</span></span>

| <span data-ttu-id="9fd20-110">À</span><span class="sxs-lookup"><span data-stu-id="9fd20-110">To</span></span> | <span data-ttu-id="9fd20-111">Voir</span><span class="sxs-lookup"><span data-stu-id="9fd20-111">See</span></span> |
| --- | --- |
| <span data-ttu-id="9fd20-112">Créer une fiche fournisseur pour chaque fournisseur auquel vous achetez des biens</span><span class="sxs-lookup"><span data-stu-id="9fd20-112">Create a vendor card for each vendor that you purchase from</span></span>|[<span data-ttu-id="9fd20-113">Enregistrer de nouveaux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="9fd20-113">Register New Vendors</span></span>](purchasing-how-register-new-vendors.md) |
| <span data-ttu-id="9fd20-114">Entrer les différents escomptes et prix spéciaux que vous accordent les fournisseurs en fonction de l'article, des quantités et/ou de la date</span><span class="sxs-lookup"><span data-stu-id="9fd20-114">Enter the different discounts and special prices that vendors grant you depending on item, quantities, and/or date</span></span> |[<span data-ttu-id="9fd20-115">Enregistrer des accords sur les prix d'achat, les remises et les paiements</span><span class="sxs-lookup"><span data-stu-id="9fd20-115">Record Purchase Price, Discount, and Payment Agreements</span></span>](purchasing-how-record-purchase-price-discount-payment-agreements.md) |
| <span data-ttu-id="9fd20-116">Octroyer une priorité aux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="9fd20-116">Prioritize vendors</span></span> |[<span data-ttu-id="9fd20-117">Octroyer une priorité aux fournisseurs</span><span class="sxs-lookup"><span data-stu-id="9fd20-117">Prioritize Vendors</span></span>](purchasing-how-prioritize-vendors.md) |
| <span data-ttu-id="9fd20-118">Configurer les acheteurs</span><span class="sxs-lookup"><span data-stu-id="9fd20-118">Set up purchasers</span></span> |[<span data-ttu-id="9fd20-119">Configurer les acheteurs</span><span class="sxs-lookup"><span data-stu-id="9fd20-119">Set Up Purchasers</span></span>](purchasing-how-setup-purchasers.md) |
|<span data-ttu-id="9fd20-120">Spécifiez les rapports par défaut à utiliser pour différents types de documents.</span><span class="sxs-lookup"><span data-stu-id="9fd20-120">Specify default reports to be used for different document types.</span></span>|[<span data-ttu-id="9fd20-121">Sélection des rapports dans Business Central</span><span class="sxs-lookup"><span data-stu-id="9fd20-121">Report Selection in Business Central</span></span>](across-report-selections.md)|

> [!TIP]
> <span data-ttu-id="9fd20-122">En fonction de votre emplacement géographique, certaines pages peuvent contenir des champs qui ne sont pas décrits dans les articles répertoriés ici, car ils s’appliquent à des fonctionnalités locales ou à des personnalisations.</span><span class="sxs-lookup"><span data-stu-id="9fd20-122">Depending on your geographical location, some pages can contain fields that are not described in the articles that are listed here because they apply to local functionality or customizations.</span></span> [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

## <a name="see-related-training-at-microsoft-learn"></a><span data-ttu-id="9fd20-123">Voir la formation associée sur [Microsoft Learn](/learn/paths/trade-get-started-dynamics-365-business-central/)</span><span class="sxs-lookup"><span data-stu-id="9fd20-123">See Related Training at [Microsoft Learn](/learn/paths/trade-get-started-dynamics-365-business-central/)</span></span>

## <a name="see-also"></a><span data-ttu-id="9fd20-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9fd20-124">See Also</span></span>

[<span data-ttu-id="9fd20-125">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="9fd20-125">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="9fd20-126">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="9fd20-126">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>
