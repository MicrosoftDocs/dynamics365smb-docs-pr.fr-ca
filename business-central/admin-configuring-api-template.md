---
title: "Configuration des modèles d'API | Microsoft Docs"
description: "Décrit la procédure à suivre pour configurer des modèles d'API pour Dynamics 365 Business Central."
services: project-madeira
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: API templates, configuring templates
ms.date: 05/16/2018
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: ad1b888d475c0523c5a905e804a3f89ab4531b28
ms.openlocfilehash: 1695a6950dabc1b2f0a2f85ad9e0c565012c92e1
ms.contentlocale: fr-ca
ms.lasthandoff: 05/17/2018

---

# <a name="configuring-api-templates"></a><span data-ttu-id="ff080-103">Configuration des modèles d'API</span><span class="sxs-lookup"><span data-stu-id="ff080-103">Configuring API Templates</span></span>
<span data-ttu-id="ff080-104">La bibliothèque d'API de [!INCLUDE[d365fin_md](includes/d365fin_md.md)] fournit une représentation simplifiée des entités sous-jacentes.</span><span class="sxs-lookup"><span data-stu-id="ff080-104">The API library for [!INCLUDE[d365fin_md](includes/d365fin_md.md)] provides a simplified representation of the underlying entities.</span></span> <span data-ttu-id="ff080-105">Toutes les propriétés de l'application ne sont pas exposées via l'API associée.</span><span class="sxs-lookup"><span data-stu-id="ff080-105">All the properties in the application are not exposed through the associated API.</span></span> <span data-ttu-id="ff080-106">La fenêtre **Configuration API** permet de définir des modèles qui sont utilisés pour renseigner les propriétés vides d'une entité lorsque vous créez une action REPORTER via l'API.</span><span class="sxs-lookup"><span data-stu-id="ff080-106">The **API Setup** window allows you to define templates that are used to populate empty properties on an entity when you create a POST action through the API.</span></span> 

<span data-ttu-id="ff080-107">Par exemple, si un modèle de configuration est défini pour l'entité article, lorsqu'un nouvel enregistrement d'article est créé via l'API de l'article, les propriétés du nouvel article qui ne sont pas définies dans l'appel de l'API sont remplies à partir du modèle sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ff080-107">For example, if a configuration template is defined for the item entity, when a new item record is created through the items API, any properties for the new item that are not defined in the API call will be populated from the selected template.</span></span> <span data-ttu-id="ff080-108">Si, par exemple, aucune valeur n'est définie pour le champ **Groupe de report de produit** via l'API, mais qu'une valeur est définie dans le modèle sélectionné, la valeur du groupe de report définie dans le modèle est appliquée au nouvel article.</span><span class="sxs-lookup"><span data-stu-id="ff080-108">If, for example, no value is defined for the **Gen. Prod. Posting Group** field through the API, but a value is defined in the selected template, then the posting group value defined in the template will be applied to the new item.</span></span> 

## <a name="setting-up-the-entity-template"></a><span data-ttu-id="ff080-109">Configuration du modèle d'entité</span><span class="sxs-lookup"><span data-stu-id="ff080-109">Setting up the Entity Template</span></span>
<span data-ttu-id="ff080-110">Pour utiliser les modèles avec la bibliothèque d'API, vous devez d'abord configurer et définir les propriétés des modèles.</span><span class="sxs-lookup"><span data-stu-id="ff080-110">To use templates with the API library, you must first set up and define properties for the templates.</span></span> <span data-ttu-id="ff080-111">Vous pouvez configurer ces modèles dans la fenêtre **Modèles configuration**.</span><span class="sxs-lookup"><span data-stu-id="ff080-111">You can set up these templates in the **Configuration Templates** window.</span></span> <span data-ttu-id="ff080-112">Pour plus d'informations, voir [Préparer la migration des données client](admin-use-templates-to-prepare-customer-data-for-migration.md).</span><span class="sxs-lookup"><span data-stu-id="ff080-112">For more information, see [Prepare to Migrate Customer Data](admin-use-templates-to-prepare-customer-data-for-migration.md).</span></span> 

## <a name="assign-the-template-to-an-api"></a><span data-ttu-id="ff080-113">Affecter le modèle à une API</span><span class="sxs-lookup"><span data-stu-id="ff080-113">Assign the template to an API</span></span>

<span data-ttu-id="ff080-114">Pour affecter un modèle à une API, vous devez effectuer les actions suivantes.</span><span class="sxs-lookup"><span data-stu-id="ff080-114">To assign a template to an API, you must go through the following steps.</span></span>

1. <span data-ttu-id="ff080-115">Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration API**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ff080-115">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **API Setup**, and choose the related link.</span></span>
2. <span data-ttu-id="ff080-116">Choisissez **Nouveau**, puis la valeur **Ordre** pour l'enregistrement.</span><span class="sxs-lookup"><span data-stu-id="ff080-116">Choose **New**, and then choose the **Order** value for the record.</span></span>  
<span data-ttu-id="ff080-117">Si plusieurs modèles sont sélectionnés pour une API (Code page), les modèles sont appliqués dans l'ordre défini dans la colonne **Ordre**.</span><span class="sxs-lookup"><span data-stu-id="ff080-117">If there is more than one template selected for an API (Page ID), the templates are applied in the order defined in the **Order** column.</span></span>   
<span data-ttu-id="ff080-118">Lorsque chaque modèle est appliqué, les valeurs de champ définies dans le modèle sont uniquement appliquées aux champs sans valeur déjà définie, soit explicitement dans l'API ou dans un modèle précédemment appliqué dans l'ordre.</span><span class="sxs-lookup"><span data-stu-id="ff080-118">When each template is applied, field values defined in the template are only applied to fields that have not already had a value defined, either explicitly in the API, or in a previously applied template in the order.</span></span> 
3. <span data-ttu-id="ff080-119">Sélectionnez une valeur **Code page**.</span><span class="sxs-lookup"><span data-stu-id="ff080-119">Select a **Page ID** value.</span></span>  
<span data-ttu-id="ff080-120">Il s'agit de la page de l'API à laquelle le modèle est appliqué.</span><span class="sxs-lookup"><span data-stu-id="ff080-120">This is the page for the API to which the template will be applied.</span></span> <span data-ttu-id="ff080-121">La recherche **Code page** fournit la liste de toutes les API disponibles dans la bibliothèque.</span><span class="sxs-lookup"><span data-stu-id="ff080-121">The **Page ID** lookup provides a list of all APIs available in the library.</span></span>
4. <span data-ttu-id="ff080-122">Sélectionnez une valeur dans le champ **Code modèle**.</span><span class="sxs-lookup"><span data-stu-id="ff080-122">Select a value in the **Template Code** field.</span></span>  
<span data-ttu-id="ff080-123">Le code modèle est le code du modèle qui a été défini dans la fenêtre **Modèles configuration**.</span><span class="sxs-lookup"><span data-stu-id="ff080-123">The template code is the code for the template that was defined in the **Configuration Templates** window.</span></span> <span data-ttu-id="ff080-124">Les valeurs de modèle définies sont appliquées à l'API.</span><span class="sxs-lookup"><span data-stu-id="ff080-124">The template values defined are applied to the API.</span></span> 
5. <span data-ttu-id="ff080-125">Dans le champ **Conditions**, spécifiez le modèle à appliquer.</span><span class="sxs-lookup"><span data-stu-id="ff080-125">In the **Conditions** field, specify which template should be applied.</span></span>  
<span data-ttu-id="ff080-126">Le modèle défini est appliqué à un nouvel enregistrement créé via l'API si, et seulement si, les conditions définies dans le champ **Conditions** sont remplies par les valeurs déjà définies pour la nouvelle instance de l'entité.</span><span class="sxs-lookup"><span data-stu-id="ff080-126">The defined template is applied to a new record created through the API if, and only if, the conditions defined in the **Conditions** field are met by the values already defined for the new instance of the entity.</span></span>

## <a name="see-also"></a><span data-ttu-id="ff080-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ff080-127">See Also</span></span>
[<span data-ttu-id="ff080-128">Documentation sur les API</span><span class="sxs-lookup"><span data-stu-id="ff080-128">API Documentation</span></span>](/dynamics-nav/fin-graph)  
<span data-ttu-id="ff080-129">[Développement d'applications connectées pour [!INCLUDE[d365fin_md](includes/d365fin_md.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)</span><span class="sxs-lookup"><span data-stu-id="ff080-129">[Developing Connect Apps for [!INCLUDE[d365fin_md](includes/d365fin_md.md)]](/dynamics365/business-central/dev-itpro/developer/devenv-develop-connect-apps)</span></span>  
[<span data-ttu-id="ff080-130">Activation des API</span><span class="sxs-lookup"><span data-stu-id="ff080-130">Enabling the APIs</span></span>](/dynamics-nav/enabling-apis-for-dynamics-nav)  
[<span data-ttu-id="ff080-131">Points de terminaison des API</span><span class="sxs-lookup"><span data-stu-id="ff080-131">Endpoints for the APIs</span></span>](/dynamics-nav/endpoints-apis-for-dynamics)  
[<span data-ttu-id="ff080-132">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="ff080-132">Setting Up a Company with RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="ff080-133">Administration</span><span class="sxs-lookup"><span data-stu-id="ff080-133">Administration</span></span>](admin-setup-and-administration.md)
