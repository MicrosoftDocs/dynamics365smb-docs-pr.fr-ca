---
title: Extensions de migration vers le nuage
description: Utilisez les extensions de migration nuage pour migrer vos données locales vers Business Central Online. Ces extensions déplacent vos données locales vers le nuage afin que vous puissiez utiliser Business Central Online avec vos données existantes.
author: jenolson
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, import, implement
ms.reviewer: edupont
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: f02face497affd1fd1467c118e10e69f2be39b85
ms.sourcegitcommit: 951d3c9d541f0b1d26712d37e253c2958dae3321
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/13/2021
ms.locfileid: "5889134"
---
# <a name="cloud-migration-extensions-for-migrating-to-business-central-online"></a><span data-ttu-id="32474-104">Extensions de migration vers le nuage pour la migration vers Business Central Online</span><span class="sxs-lookup"><span data-stu-id="32474-104">Cloud Migration Extensions for Migrating to Business Central Online</span></span>

<span data-ttu-id="32474-105">En fonction de votre solution sur site, vous devez utiliser différentes extensions pour connecter vos données à [!INCLUDE[prod_short](includes/prod_short.md)] en ligne afin de migrer votre solution vers le nuage.</span><span class="sxs-lookup"><span data-stu-id="32474-105">Depending on your on-premises solution, you must use different extensions to connect your data with [!INCLUDE[prod_short](includes/prod_short.md)] online for purposes of migrating your solution to the cloud.</span></span>  

<span data-ttu-id="32474-106">Si vous utilisez l'un des produits sur site pris en charge, vous pouvez configurer votre environnement de nuage en fonction d'une extension basée sur le produit.</span><span class="sxs-lookup"><span data-stu-id="32474-106">If you are using one of the supported on-premises products, you can configure your cloud environment based on a product-specific extension.</span></span> <span data-ttu-id="32474-107">Une fois votre environnement de nuage configuré, vous pouvez migrer des données depuis votre solution sur site vers [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="32474-107">Once your cloud environment is configured, you will be able to migrate data from your on-premises solution to [!INCLUDE[prod_short](includes/prod_short.md)].</span></span> <span data-ttu-id="32474-108">Ceci vous permet de profiter pleinement des avantages que le nuage peut offrir à votre compagnie, comme les analyses optimisées de votre activité, l'intelligence artificielle, l'accès multipériphérique à tout moment et n'importe où.</span><span class="sxs-lookup"><span data-stu-id="32474-108">This will enable you to take full advantage of what the cloud has to offer your business such as, enhanced insights into your business, artificial intelligence, multiple device access, and anytime, anywhere access.</span></span>  

<span data-ttu-id="32474-109">Pour en savoir plus, voir la rubrique [Migration des données locales vers Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) dans le contenu d'administration pour [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="32474-109">For more information, see [Migrating On-Premises Data to Business Central Online](/dynamics365/business-central/dev-itpro/administration/migrate-data) in the administration content for [!INCLUDE[prod_short](includes/prod_short.md)].</span></span>  

## <a name="business-central-on-premises"></a><span data-ttu-id="32474-110">Business Central sur site</span><span class="sxs-lookup"><span data-stu-id="32474-110">Business Central on-premises</span></span>

<span data-ttu-id="32474-111">Si vous utilisez un déploiement sur site de [!INCLUDE[prod_short](includes/prod_short.md)], obtenez les extensions **Base du nuage intelligent** et **Nuage intelligent Business Central**, puis exécutez le guide de configuration assistée **Configuration de la migration nuage**.</span><span class="sxs-lookup"><span data-stu-id="32474-111">If you are using an on-premises deployment of [!INCLUDE[prod_short](includes/prod_short.md)], get the **Intelligent Cloud Base** extension and the **Business Central Intelligent Cloud** extension, and then run the **Cloud Migration Setup** assisted setup guide.</span></span>  

## <a name="dynamics-gp"></a><span data-ttu-id="32474-112">Dynamics GP</span><span class="sxs-lookup"><span data-stu-id="32474-112">Dynamics GP</span></span>

<span data-ttu-id="32474-113">Si vous utilisez Dynamics GP, obtenez les extensions **Base du nuage intelligent** et **Nuage intelligent Dynamics GP**, puis exécutez le guide de configuration assistée **Configuration de la migration nuage**.</span><span class="sxs-lookup"><span data-stu-id="32474-113">If you are using Dynamics GP,  get the **Intelligent Cloud Base Extension** extension and the **Dynamics GP Intelligent Cloud** extension, and then run the **Cloud Migration Setup** assisted setup guide.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="32474-114">La migration à partir de Dynamics GP à l'aide du guide de configuration assistée **Configuration de la migration nuage** n'est actuellement prise en charge que pour les marchés suivants : États-Unis, Canada, Royaume-Uni.</span><span class="sxs-lookup"><span data-stu-id="32474-114">Migrating from Dynamics GP using the **Cloud Migration Setup** assisted setup guide is currently only supported for the following markets: United States, Canada, United Kingdom.</span></span>

## <a name="dynamics-sl"></a><span data-ttu-id="32474-115">Dynamics SL</span><span class="sxs-lookup"><span data-stu-id="32474-115">Dynamics SL</span></span>

<span data-ttu-id="32474-116">Si vous utilisez Dynamics SL, obtenez l'extension **Base du nuage intelligent**, l'extension **Nuage intelligent Microsoft Dynamics SL** et l'extension **SmartLists historiques Microsoft Dynamics SL**, puis exécutez le guide de configuration assistée **Configuration de la migration nuage**.</span><span class="sxs-lookup"><span data-stu-id="32474-116">If you are using Dynamics SL, get the **Intelligent Cloud Base** extension, the **Microsoft Dynamics SL Intelligent Cloud** extension and the **Microsoft Dynamics SL History SmartLists** extension, and then run the **Cloud Migration Setup** assisted setup guide.</span></span>  

## <a name="see-also"></a><span data-ttu-id="32474-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32474-117">See Also</span></span>

[<span data-ttu-id="32474-118">Extension Base de migration vers le nuage</span><span class="sxs-lookup"><span data-stu-id="32474-118">Cloud Migration Base Extension</span></span>](ui-extensions-intelligent-cloud.md)  
[<span data-ttu-id="32474-119">Migration des données locales vers Business Central Online</span><span class="sxs-lookup"><span data-stu-id="32474-119">Migrating On-Premises Data to Business Central Online</span></span>](/dynamics365/business-central/dev-itpro/administration/migrate-data)  

[!INCLUDE[footer-include](includes/footer-banner.md)]