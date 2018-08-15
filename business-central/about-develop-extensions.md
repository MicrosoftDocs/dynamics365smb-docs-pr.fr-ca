---
title: "Personnaliser Dynamics 365 Business Central | Microsoft Docs"
description: "Concevoir, présenter et promouvoir vos applications et extensions pour Business Central."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: app, add-in, manifest, customize
ms.date: 04/12/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 2286b728a464943841b192031cfea13644441013
ms.openlocfilehash: 69f660f8a19bd1fd9cb39a79d5be7977e68d3a47
ms.contentlocale: fr-ca
ms.lasthandoff: 06/28/2018

---
# <a name="extending-included365finlongincludesd365finlongmdmd"></a><span data-ttu-id="6492b-103">Extension de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]</span><span class="sxs-lookup"><span data-stu-id="6492b-103">Extending [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]</span></span>
<span data-ttu-id="6492b-104">Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] est une solution de gestion d'entreprise qui aide les compagnies à connecter leurs finances, ventes, services et opérations pour rationnaliser les processus d'entreprise, améliorer les interactions avec le client et prendre de meilleures décisions.</span><span class="sxs-lookup"><span data-stu-id="6492b-104">Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] is a business management solution that helps companies connect their financials, sales, service, and operations to streamline business processes, improve customer interactions, and make better decisions.</span></span> [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]<span data-ttu-id="6492b-105"> est accessible dans le cloud et aux utilisateurs sur différents types d'appareils, et est mis à jour régulièrement.</span><span class="sxs-lookup"><span data-stu-id="6492b-105"> is available in the cloud and to users across various multiple types of devices, which is always up-to-date.</span></span> <span data-ttu-id="6492b-106">Cette plate-forme d'entreprise moderne vous permet de personnaliser, d'étendre et de créer facilement et rapidement des applications en fonction de vos besoins spécifiques, avec peu ou pas de développement de code.</span><span class="sxs-lookup"><span data-stu-id="6492b-106">With this modern business platform you can easily and quickly tailor, extend, and build applications so they fit your specific needs — with little to no code development.</span></span>  

<span data-ttu-id="6492b-107">Il existe de nombreux avantages à utiliser [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] comme plateforme pour les constructeurs d'applications, notamment :</span><span class="sxs-lookup"><span data-stu-id="6492b-107">There are plenty of benefits of using [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] as a platform for App builders, which includes:</span></span>

* <span data-ttu-id="6492b-108">Prise en main en toute confiance grâce à une expérience d'intégration transparente</span><span class="sxs-lookup"><span data-stu-id="6492b-108">Get started with confidence through a seamless onboarding experience</span></span> 
* <span data-ttu-id="6492b-109">Utilisation des services Go-To-Market de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6492b-109">Use Microsoft’s Go-To-Market services</span></span>
* <span data-ttu-id="6492b-110">Personnalisation de votre page de liste d'applications</span><span class="sxs-lookup"><span data-stu-id="6492b-110">Customize your app listing page</span></span> 
* <span data-ttu-id="6492b-111">Communication directe avec les décisionnaires et ciblage d'un plus grand nombre de clients</span><span class="sxs-lookup"><span data-stu-id="6492b-111">Connect directly with decision-makers and reach more customers</span></span>
* <span data-ttu-id="6492b-112">Amélioration de la valeur commerciale et augmentation du volume des transactions avec les clients existants et nouveaux</span><span class="sxs-lookup"><span data-stu-id="6492b-112">Enhance business value and increase deal size with existing and new customers</span></span>
* <span data-ttu-id="6492b-113">Faites-en plus avec une plate-forme qui fournit une expérience moderne et offre une évolutivité</span><span class="sxs-lookup"><span data-stu-id="6492b-113">Achieve more with a platform that delivers a modern experience and offers scale</span></span>  
* <span data-ttu-id="6492b-114">Accès à des informations exploitables sur les performances de vos listings via le portail Cloud Partner ou le processus de publication de l'application Office</span><span class="sxs-lookup"><span data-stu-id="6492b-114">Get actionable insights on the performance of your listings via the Cloud Partner Portal or the Office app publishing process</span></span>
* <span data-ttu-id="6492b-115">Associée à des applications professionnelles intelligentes telles que PowerApps, Flow, Power BI, Cortana Intelligence et bien d'autres encore</span><span class="sxs-lookup"><span data-stu-id="6492b-115">Bundle with intelligent business apps such as PowerApps, Flow, Power BI, Cortana Intelligence, and many more</span></span>  

<span data-ttu-id="6492b-116">Importez vos services [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] dans Microsoft AppSource en tant que :</span><span class="sxs-lookup"><span data-stu-id="6492b-116">Bring your [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] services to Microsoft AppSource as:</span></span> 

<span data-ttu-id="6492b-117">**Applications individuelles** – pour apporter votre expertise du secteur sur le marché.</span><span class="sxs-lookup"><span data-stu-id="6492b-117">**Individual Apps** – where you bring your industry expertise to market.</span></span>  
<span data-ttu-id="6492b-118">**Offre groupée de services de consultation** – pour apporter une offre groupée d'engagements prêts à l'emploi sur le marché.</span><span class="sxs-lookup"><span data-stu-id="6492b-118">**Packaged Consulting Services** – where you bring ready-made packaged engagements to market.</span></span>

<span data-ttu-id="6492b-119">Les nouveaux outils de développement vous permettent de créer des extensions pour les utilisateurs [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6492b-119">The new development tools enable to you to build extensions for [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] users.</span></span> <span data-ttu-id="6492b-120">Si vous souhaitez vous familiariser avec les nouveaux outils ou en savoir plus sur les extensions 2.0, consultez [aka.ms/GetStartedWithApps](http://aka.ms/GetStartedWithApps).</span><span class="sxs-lookup"><span data-stu-id="6492b-120">If you want to familiarize yourself with the new tools or learn about extensions 2.0, have a look at [aka.ms/GetStartedWithApps](http://aka.ms/GetStartedWithApps).</span></span>  

<span data-ttu-id="6492b-121">Vous trouverez des informations sur les applications et les services de consultation actuellement disponibles sur [Microsoft AppSource](https://appsource.microsoft.com/en-us/marketplace/consulting-services?country=US&page=1).</span><span class="sxs-lookup"><span data-stu-id="6492b-121">Find information on apps and consulting services that are currently available on [Microsoft AppSource](https://appsource.microsoft.com/en-us/marketplace/consulting-services?country=US&page=1).</span></span>

<span data-ttu-id="6492b-122">Pour aider les utilisateurs à démarrer rapidement, Microsoft a ajouté à AppSource un catalogue d'offres de services de consultation pour les solutions basées sur [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], Power BI et PowerApps.</span><span class="sxs-lookup"><span data-stu-id="6492b-122">To help business users get started quickly, Microsoft has added a catalog of consulting services offerings for solutions based on [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], Power BI, and PowerApps to AppSource.</span></span> <span data-ttu-id="6492b-123">En savoir plus sur les [Services de consultation](/dynamics-nav/developer/readiness/readiness-consulting).</span><span class="sxs-lookup"><span data-stu-id="6492b-123">Learn more about the [Consulting Services](/dynamics-nav/developer/readiness/readiness-consulting).</span></span>

## <a name="choosing-which-services-to-offer-with-included365finlongincludesd365finlongmdmd"></a><span data-ttu-id="6492b-124">Choix des services à offrir avec [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]</span><span class="sxs-lookup"><span data-stu-id="6492b-124">Choosing which Services to Offer with [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]</span></span> 

### <a name="integrate-a-3rd-party-solution"></a><span data-ttu-id="6492b-125">Intégrer une solution tierce</span><span class="sxs-lookup"><span data-stu-id="6492b-125">Integrate a 3rd Party Solution</span></span>
[!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]<span data-ttu-id="6492b-126"> propose plusieurs API prêtes à l'emploi pour les [applications connectées](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-connect-apps) pour faciliter l'intégration entre votre service et [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6492b-126"> exposes many ready-to-use APIs for [Connect apps](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-connect-apps) to make a seamless integration between your service and [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)].</span></span> <span data-ttu-id="6492b-127">Vous pouvez regrouper vos services avec une version [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] et offrir une expérience intégrée à vos clients.</span><span class="sxs-lookup"><span data-stu-id="6492b-127">You can bundle your services with a [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] and give your customers an integrated experience.</span></span> <span data-ttu-id="6492b-128">En savoir plus l'[Intégration d'une solution tierce](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-thirdparty-solution).</span><span class="sxs-lookup"><span data-stu-id="6492b-128">Learn more about [Integrating a 3rd Party Solution](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-thirdparty-solution).</span></span>

### <a name="development-of-a-vertical-solution"></a><span data-ttu-id="6492b-129">Développement d'une solution verticale</span><span class="sxs-lookup"><span data-stu-id="6492b-129">Development of a Vertical Solution</span></span>
<span data-ttu-id="6492b-130">Créez un application spécialisée dans un secteur d'activité spécifique.</span><span class="sxs-lookup"><span data-stu-id="6492b-130">Create an app that is specialized within a specific industry.</span></span> <span data-ttu-id="6492b-131">Avec une [application intégrée](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-embed-apps), vous pouvez étendre et personnaliser l'application [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] existante et enrichir l'expérience de l'utilisateur final avec une fonctionnalité spécifique au secteur d'activité en utilisant les outils de développement nouveaux et modernes et les extensions version 2.0.</span><span class="sxs-lookup"><span data-stu-id="6492b-131">With [Embed app](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-embed-apps), you can extend and customize the existing [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] application and enrich the end-user experience with an industry specific functionality using the new and modern development tools and Extensions version 2.0.</span></span> <span data-ttu-id="6492b-132">En savoir plus sur le [Développement d'une solution verticale](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-vertical).</span><span class="sxs-lookup"><span data-stu-id="6492b-132">Learn more about the [Development of a Vertical Solution](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-vertical).</span></span>

### <a name="development-of-a-horizontal-solution"></a><span data-ttu-id="6492b-133">Développement d'une solution horizontale</span><span class="sxs-lookup"><span data-stu-id="6492b-133">Development of a Horizontal Solution</span></span>
<span data-ttu-id="6492b-134">Étendez l'expérience et les capacités de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] en créant une [application complémentaire](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-add-on-apps) qui s'intègre dans l'expérience utilisateur de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)].</span><span class="sxs-lookup"><span data-stu-id="6492b-134">Extend the experience and capability of [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] by creating an [Add-on app](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-add-on-apps) which integrates into user experience of [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)].</span></span> <span data-ttu-id="6492b-135">Créez une interface basée sur le mode de transfert de vos données entre [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] et vos services.</span><span class="sxs-lookup"><span data-stu-id="6492b-135">Build an interface based on how you want your data to flow between [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] and your services.</span></span> <span data-ttu-id="6492b-136">En savoir plus sur le [Développement d'une solution horizontale](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-horizontal).</span><span class="sxs-lookup"><span data-stu-id="6492b-136">Learn more about the [Development of a Horizontal Solution](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-horizontal).</span></span> 

### <a name="development-of-a-localization-solution"></a><span data-ttu-id="6492b-137">Développement d'une solution de localisation</span><span class="sxs-lookup"><span data-stu-id="6492b-137">Development of a Localization Solution</span></span>
<span data-ttu-id="6492b-138">Conformez-vous aux capacités réglementaires locales pour [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], qui adapte les zones fonctionnelles aux exigences du marché local et au [Service de traduction de Dynamics 365](/dynamics365/unified-operations/dev-itpro/lifecycle-services/translation-service-overview).</span><span class="sxs-lookup"><span data-stu-id="6492b-138">Comply with local regulatory capabilities by developing for [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], which adapts functional areas to the requirements of the local market along with [Dynamics 365 Translation Service](/dynamics365/unified-operations/dev-itpro/lifecycle-services/translation-service-overview).</span></span> <span data-ttu-id="6492b-139">Alignez les capacités de base des exigences légales locales et étendez les fonctionnalités existantes pour soutenir la concurrence sur le marché local.</span><span class="sxs-lookup"><span data-stu-id="6492b-139">Align the core capabilities of local legal requirement and extend existing functionality to successfully compete on your local market.</span></span> <span data-ttu-id="6492b-140">En savoir plus sur le [Développement d'une solution de localisation](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-localization).</span><span class="sxs-lookup"><span data-stu-id="6492b-140">Learn more about the [Development of a Localization Solution](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-develop-localization).</span></span>

### <a name="reseller-solution"></a><span data-ttu-id="6492b-141">Solution de revendeur</span><span class="sxs-lookup"><span data-stu-id="6492b-141">Reseller Solution</span></span>
<span data-ttu-id="6492b-142">Comme chaque entreprise est unique, la [Personnalisation des abonnés](/dynamics-nav/developer/readiness/readiness-customizing-tenants) vous permet de mettre en correspondance la manière dont vous utilisez vos processus rationnalisés et votre terminologie avec la manière dont vos employés ou services communiquent et collaborent.</span><span class="sxs-lookup"><span data-stu-id="6492b-142">Since every business is unique, with [Customizing Tenants](/dynamics-nav/developer/readiness/readiness-customizing-tenants), you can match how you work with your streamlined processes, your terminology, and how your employees or departments connect and collaborate.</span></span> <span data-ttu-id="6492b-143">En outre, vous pouvez choisir de revendre et d'adapter [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] aux besoins de vos clients en fournissant des [Services de consultation](/dynamics-nav/developer/readiness/readiness-consulting).</span><span class="sxs-lookup"><span data-stu-id="6492b-143">Additionally, you can choose to resell and adjust [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] to the individual needs of your customers by providing [Consulting Services](/dynamics-nav/developer/readiness/readiness-consulting).</span></span> <span data-ttu-id="6492b-144">Vous pouvez également utiliser Microsoft Flow, Power Apps et Power BI pour créer des [Flux de travail personnalisés](/dynamics-nav/developer/readiness/readiness-no-code), des applications et des rapports d'analyse sans avoir à écrire de code.</span><span class="sxs-lookup"><span data-stu-id="6492b-144">Or, use Microsoft Flow, Power Apps, and Power BI to create [Customized Workflows](/dynamics-nav/developer/readiness/readiness-no-code), apps and business insight reports without having to write any code.</span></span> <span data-ttu-id="6492b-145">En savoir plus sur le [Revendeur Dynamics 365 (VAR)](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-reseller).</span><span class="sxs-lookup"><span data-stu-id="6492b-145">Learn more about [Dynamics 365 Reseller (VARs)](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-reseller).</span></span> 

## <a name="where-do-i-learn-more"></a><span data-ttu-id="6492b-146">Informations utiles</span><span class="sxs-lookup"><span data-stu-id="6492b-146">Where do I Learn more?</span></span>
<span data-ttu-id="6492b-147">Pour plus d'informations sur les offres de services de consultation de Microsoft AppSource, sélectionnez les liens suivants :</span><span class="sxs-lookup"><span data-stu-id="6492b-147">To learn more about the Microsoft AppSource consulting services offerings, select the following links:</span></span> 

[<span data-ttu-id="6492b-148">Offres de services de consultation de AppSource</span><span class="sxs-lookup"><span data-stu-id="6492b-148">AppSource Consulting Offerings</span></span>](https://appsource.microsoft.com/en-us/marketplace/consulting-services?country=US&page=1)  
[<span data-ttu-id="6492b-149">Éligibilité des partenaires</span><span class="sxs-lookup"><span data-stu-id="6492b-149">Partner Eligibility</span></span>](https://smp-cdn-prod.azureedge.net/documents/Microsoft%20AppSource%20Partner%20Listing%20Guidelines.pdf)  
[<span data-ttu-id="6492b-150">Formulaire de nomination des partenaires</span><span class="sxs-lookup"><span data-stu-id="6492b-150">Partner Nomination Form</span></span>](https://appsource.microsoft.com/en-us/partners/list-consulting-service)  

## <a name="the-ready-to-go-program"></a><span data-ttu-id="6492b-151">Programme Ready to Go</span><span class="sxs-lookup"><span data-stu-id="6492b-151">The Ready to Go Program</span></span>
<span data-ttu-id="6492b-152">Le programme Ready to Go est conçu à vous aider à importer vos offres Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] dans Microsoft Appsource.</span><span class="sxs-lookup"><span data-stu-id="6492b-152">The Ready to Go program is designed to support you in bringing your Microsoft [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] offers into Microsoft Appsource.</span></span> <span data-ttu-id="6492b-153">Le programme contient :</span><span class="sxs-lookup"><span data-stu-id="6492b-153">The program holds:</span></span> 

- [<span data-ttu-id="6492b-154">Apprentissage en ligne</span><span class="sxs-lookup"><span data-stu-id="6492b-154">Online learning</span></span>](http://aka.ms/ReadyToGoOnlineLearning)
- [<span data-ttu-id="6492b-155">Formation et ateliers</span><span class="sxs-lookup"><span data-stu-id="6492b-155">Training and workshops</span></span>](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-ready-to-go#the-ready-to-go-coaching)
- [<span data-ttu-id="6492b-156">Plateforme Microsoft Collaborate</span><span class="sxs-lookup"><span data-stu-id="6492b-156">Microsoft Collaborate platform</span></span>](http://aka.ms/Collaborate)

<span data-ttu-id="6492b-157">Pour plus d'informations sur la création d'une offre [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)], consultez les détails du [Programme Ready to Go](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-ready-to-go).</span><span class="sxs-lookup"><span data-stu-id="6492b-157">Learn more on how you can build a [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)] offering in the [Ready to Go program](/dynamics365/business-central/dev-itpro/developer/readiness/readiness-ready-to-go) details.</span></span> <span data-ttu-id="6492b-158">Si vous avez des questions ou des commentaires concernant le programme **Ready to Go**, vous pouvez [nous contacter](mailto:dyn365bep@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="6492b-158">If you have questions or feedback about the **Ready to Go** program offering, you can [contact us](mailto:dyn365bep@microsoft.com).</span></span> 

## <a name="see-also"></a><span data-ttu-id="6492b-159">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6492b-159">See Also</span></span>
[<span data-ttu-id="6492b-160">Mise en route</span><span class="sxs-lookup"><span data-stu-id="6492b-160">Getting Started</span></span>](product-get-started.md)  
<span data-ttu-id="6492b-161">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="6492b-161">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)</span></span>  
[https://appsource.microsoft.com](https://appsource.microsoft.com/en-us/marketplace/apps?product=dynamics-365-for-financials&page=1)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 
