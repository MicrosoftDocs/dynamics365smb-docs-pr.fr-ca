---
title: Gestion de l’intégration de Microsoft Teams avec Business Central | Microsoft Docs
description: Gérez l’intégration Business Central avec Microsoft Teams.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Teams, MS Teams, Microsoft Teams, Skype, Link, Microsoft 365, collaborate, collaboration, teamwork
ms.date: 10/08/2020
ms.author: jswymer
ms.openlocfilehash: 3c04dfb2f77eba906b2567ca9438849e1cc20861
ms.sourcegitcommit: 4bca699d2a5ce182eb5572d72fac4fb478c4f293
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/12/2020
ms.locfileid: "3989369"
---
# <a name="managing-microsoft-teams-integration-with-business-central"></a><span data-ttu-id="249c8-103">Gestion de l’intégration Microsoft Teams avec Business Central</span><span class="sxs-lookup"><span data-stu-id="249c8-103">Managing Microsoft Teams Integration with Business Central</span></span>

[!INCLUDE [teams_preview.md](includes/teams_preview.md)]

<span data-ttu-id="249c8-104">Cet article fournit un aperçu de ce que vous pouvez faire en tant qu’administrateur pour contrôler l’intégration de Microsoft Teams avec [!INCLUDE [prodshort](includes/prodshort.md)].</span><span class="sxs-lookup"><span data-stu-id="249c8-104">This article provides an overview of what you can do as an administrator to control Microsoft Teams integration with [!INCLUDE [prodshort](includes/prodshort.md)].</span></span>

## <a name="in-microsoft-teams"></a><span data-ttu-id="249c8-105">Dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-105">In Microsoft Teams</span></span>

### <a name="minimum-requirements"></a><span data-ttu-id="249c8-106">Configuration minimale requise</span><span class="sxs-lookup"><span data-stu-id="249c8-106">Minimum requirements</span></span>

<span data-ttu-id="249c8-107">Cette section décrit la configuration minimale requise pour les fonctionnalités de l’application [!INCLUDE [prodshort](includes/prodshort.md)] pour travailler dans Teams.</span><span class="sxs-lookup"><span data-stu-id="249c8-107">This section describes the minimum requirements for the [!INCLUDE [prodshort](includes/prodshort.md)] app features to work in Teams.</span></span>

- <span data-ttu-id="249c8-108">Licences requises</span><span class="sxs-lookup"><span data-stu-id="249c8-108">Required licenses</span></span>

    <span data-ttu-id="249c8-109">Ce tableau vous donne un aperçu des licences nécessaires pour les fonctionnalités de l’application [!INCLUDE [prodshort](includes/prodshort.md)] pour travailler dans Teams.</span><span class="sxs-lookup"><span data-stu-id="249c8-109">This table gives you an overview of the licenses needed for the [!INCLUDE [prodshort](includes/prodshort.md)] app features to work in Teams.</span></span>

    |<span data-ttu-id="249c8-110">Quoi</span><span class="sxs-lookup"><span data-stu-id="249c8-110">What</span></span>|<span data-ttu-id="249c8-111">Licence Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-111">Teams license</span></span>|<span data-ttu-id="249c8-112">Licence Business Central</span><span class="sxs-lookup"><span data-stu-id="249c8-112">Business Central license</span></span>|
    |----|---|---|
    |<span data-ttu-id="249c8-113">Coller un lien vers un enregistrement [!INCLUDE [prodshort](includes/prodshort.md)] dans une conversation et l’envoyer sous forme de fiche.</span><span class="sxs-lookup"><span data-stu-id="249c8-113">Paste a link to a [!INCLUDE [prodshort](includes/prodshort.md)] record into a conversation, and send it as a card.</span></span>|<span data-ttu-id="249c8-114">![coche](media/check.png "coche")</span><span class="sxs-lookup"><span data-stu-id="249c8-114">![check mark](media/check.png "check")</span></span>|<span data-ttu-id="249c8-115">![coche](media/check.png "coche")</span><span class="sxs-lookup"><span data-stu-id="249c8-115">![check mark](media/check.png "check")</span></span>|
    |<span data-ttu-id="249c8-116">Afficher une fiche d’un enregistrement [!INCLUDE [prodshort](includes/prodshort.md)] dans une conversation.</span><span class="sxs-lookup"><span data-stu-id="249c8-116">View a card of a [!INCLUDE [prodshort](includes/prodshort.md)] record in a conversation.</span></span>|<span data-ttu-id="249c8-117">![coche](media/check.png "coche")</span><span class="sxs-lookup"><span data-stu-id="249c8-117">![check mark](media/check.png "check")</span></span>||
    |<span data-ttu-id="249c8-118">Afficher plus de détails d’une fiche pour un enregistrement [!INCLUDE [prodshort](includes/prodshort.md)] dans une conversation.</span><span class="sxs-lookup"><span data-stu-id="249c8-118">View more details of card for a [!INCLUDE [prodshort](includes/prodshort.md)] record in a conversation.</span></span>|<span data-ttu-id="249c8-119">![coche](media/check.png "coche")</span><span class="sxs-lookup"><span data-stu-id="249c8-119">![check mark](media/check.png "check")</span></span>|<span data-ttu-id="249c8-120">![coche](media/check.png "coche")</span><span class="sxs-lookup"><span data-stu-id="249c8-120">![check mark](media/check.png "check")</span></span>|

- <span data-ttu-id="249c8-121">Autoriser les aperçus d’URL</span><span class="sxs-lookup"><span data-stu-id="249c8-121">Allow URL previews</span></span>

    <span data-ttu-id="249c8-122">Le paramètre de stratégie **Autoriser les aperçus d’URL** doit être activé.</span><span class="sxs-lookup"><span data-stu-id="249c8-122">**Allow URL previews** policy setting must be turned on.</span></span> <span data-ttu-id="249c8-123">Sinon, une fiche ne peut pas être générée pour les liens Business Central collés dans une conversation Teams.</span><span class="sxs-lookup"><span data-stu-id="249c8-123">Otherwise, a card can't be generated for Business Central links pasted into a Teams conversation.</span></span> <span data-ttu-id="249c8-124">Pour plus d’informations sur ce paramètre, consultez [Gérer les stratégies de messagerie dans Teams](/microsoftteams/messaging-policies-in-teams).</span><span class="sxs-lookup"><span data-stu-id="249c8-124">For more information about this setting, see [Manage messaging policies in Teams](/microsoftteams/messaging-policies-in-teams).</span></span>

### <a name="managing-the-business-central-app-optional"></a><span data-ttu-id="249c8-125">Gérer l’application Business Central (facultatif)</span><span class="sxs-lookup"><span data-stu-id="249c8-125">Managing the Business Central app (optional)</span></span>

<span data-ttu-id="249c8-126">En tant qu’administrateur Teams, vous pouvez gérer toutes les applications de votre organisation, y compris l’application [!INCLUDE [prodshort](includes/prodshort.md)].</span><span class="sxs-lookup"><span data-stu-id="249c8-126">As a Teams administrator, you can manage all apps for your organization, including the [!INCLUDE [prodshort](includes/prodshort.md)] app.</span></span> <span data-ttu-id="249c8-127">Vous pouvez approuver ou installer l’application [!INCLUDE [prodshort](includes/prodshort.md)] pour votre organisation, empêcher l’utilisateur d’installer l’application, etc.</span><span class="sxs-lookup"><span data-stu-id="249c8-127">You can approve or install the [!INCLUDE [prodshort](includes/prodshort.md)] app for your organization, block user's from installing the app, and more.</span></span>

<span data-ttu-id="249c8-128">Pour plus d’informations, consultez les articles suivants dans la documentation Microsoft Teams :</span><span class="sxs-lookup"><span data-stu-id="249c8-128">For more information, see the following articles in the Microsoft Teams documentation:</span></span>

- [<span data-ttu-id="249c8-129">Gérer vos applications dans le centre d’administration Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-129">Manage your apps in the Microsoft Teams admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/manage-apps)
- [<span data-ttu-id="249c8-130">Gérer les stratégie de configuration des applications dans Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-130">Manage app setup policies in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-app-setup-policies)

## <a name="in-prodshort"></a><span data-ttu-id="249c8-131">Dans [!INCLUDE [prodshort](includes/prodshort.md)]</span><span class="sxs-lookup"><span data-stu-id="249c8-131">In [!INCLUDE [prodshort](includes/prodshort.md)]</span></span>

### <a name="minimum-requirements"></a><span data-ttu-id="249c8-132">Configuration minimale requise</span><span class="sxs-lookup"><span data-stu-id="249c8-132">Minimum requirements</span></span>

- <span data-ttu-id="249c8-133">Version de [!INCLUDE [prodshort](includes/prodshort.md)] :</span><span class="sxs-lookup"><span data-stu-id="249c8-133">[!INCLUDE [prodshort](includes/prodshort.md)] version:</span></span>

    <span data-ttu-id="249c8-134">Vague de lancement 2 de 2020 de [!INCLUDE [prodshort](includes/prodshort.md)] (version 17) ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="249c8-134">[!INCLUDE [prodshort](includes/prodshort.md)] 2020 release wave 2 (version 17) or later.</span></span> <span data-ttu-id="249c8-135">L’intégration de Teams n’est prise en charge que pour [!INCLUDE [prodshort](includes/prodshort.md)] en ligne ; pas en local.</span><span class="sxs-lookup"><span data-stu-id="249c8-135">Teams integration is only supported for [!INCLUDE [prodshort](includes/prodshort.md)] online; not on-premises.</span></span>

- <span data-ttu-id="249c8-136">Le codeunit **2718 Fournisseur résumé page** est publié en tant que service web :</span><span class="sxs-lookup"><span data-stu-id="249c8-136">Codeunit **2718 Page Summary Provider** is published as a web service:</span></span>

    <span data-ttu-id="249c8-137">Ce codeunit est publié en tant que service web par défaut.</span><span class="sxs-lookup"><span data-stu-id="249c8-137">This codeunit is published as a web service by default.</span></span> <span data-ttu-id="249c8-138">Le codeunit fait partie de l’application système [!INCLUDE [prodshort](includes/prodshort.md)].</span><span class="sxs-lookup"><span data-stu-id="249c8-138">The codeunit is part of the [!INCLUDE [prodshort](includes/prodshort.md)] system application.</span></span> <span data-ttu-id="249c8-139">Il est utilisé pour obtenir les données de champ pour une page [!INCLUDE [prodshort](includes/prodshort.md)] ajoutée à une conversation Teams.</span><span class="sxs-lookup"><span data-stu-id="249c8-139">It's used to get the field data for a [!INCLUDE [prodshort](includes/prodshort.md)] page added to a Teams conversation.</span></span> 

- <span data-ttu-id="249c8-140">Autorisations utilisateur :</span><span class="sxs-lookup"><span data-stu-id="249c8-140">User permissions:</span></span>

    <span data-ttu-id="249c8-141">Pour la plupart, les pages et les données que les utilisateurs peuvent afficher et modifier dans une conversation Teams sont contrôlées par leurs autorisations dans [!INCLUDE [prodshort](includes/prodshort.md)].</span><span class="sxs-lookup"><span data-stu-id="249c8-141">For the most part, the pages and data that users can view and edit in a Teams conversation is controlled by their permissions in [!INCLUDE [prodshort](includes/prodshort.md)].</span></span>
    
    - <span data-ttu-id="249c8-142">Pour coller un lien [!INCLUDE [prodshort](includes/prodshort.md)] dans une conversation Teams et le faire développer dans une fiche, les utilisateurs doivent avoir au moins une autorisation de lecture sur la page et ses données.</span><span class="sxs-lookup"><span data-stu-id="249c8-142">To paste a [!INCLUDE [prodshort](includes/prodshort.md)] link into a Teams conversation and have it expand into a card, users must have at least read permission on the page and its data.</span></span>
    - <span data-ttu-id="249c8-143">Une fois qu’une fiche est soumise à une conversation, tout utilisateur participant à cette conversation peut afficher cette fiche sans autorisation de Business Central.</span><span class="sxs-lookup"><span data-stu-id="249c8-143">Once a card is submitted into a conversation, any user in that conversation can view that card without permission to Business Central.</span></span>
    - <span data-ttu-id="249c8-144">Pour afficher plus de détails sur une fiche ou ouvrir l’enregistrement dans [!INCLUDE [prodshort](includes/prodshort.md)], les utilisateurs doivent avoir une autorisation de lecture sur la page et ses données.</span><span class="sxs-lookup"><span data-stu-id="249c8-144">To view more details for a card or open the record in [!INCLUDE [prodshort](includes/prodshort.md)], users must have read permission on the page and its data.</span></span>
    - <span data-ttu-id="249c8-145">Pour modifier les données, l’utilisateur doit modifier les autorisations.</span><span class="sxs-lookup"><span data-stu-id="249c8-145">To change data, user's need modify permissions.</span></span>
    
    <span data-ttu-id="249c8-146">Pour plus d’informations sur les autorisations, voir [Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="249c8-146">For information about permissions, see [Assign Permissions to Users and Groups](ui-define-granular-permissions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="249c8-147">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="249c8-147">See Also</span></span>
[<span data-ttu-id="249c8-148">Vue d’ensemble de l’intégration de Business Central et Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-148">Business Central and Microsoft Teams Integration Overview</span></span>](across-teams-overview.md)  
<span data-ttu-id="249c8-149">[Installer l’application [!INCLUDE [prodshort](includes/prodshort.md)] pour Microsoft Teams](across-install-app-for-teams.md)</span><span class="sxs-lookup"><span data-stu-id="249c8-149">[Install the [!INCLUDE [prodshort](includes/prodshort.md)] App for Microsoft Teams](across-install-app-for-teams.md)</span></span>  
[<span data-ttu-id="249c8-150">Développement pour l’intégration de Teams</span><span class="sxs-lookup"><span data-stu-id="249c8-150">Developing for Teams Integration</span></span>](/dynamics365/business-central/dev-itpro/developer/devenv-develop-for-teams)  
[<span data-ttu-id="249c8-151">Mise en route</span><span class="sxs-lookup"><span data-stu-id="249c8-151">Getting Started</span></span>](product-get-started.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
