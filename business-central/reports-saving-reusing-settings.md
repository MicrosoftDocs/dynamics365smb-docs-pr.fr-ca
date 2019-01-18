---
title: "Affecter et modifier les paramètres enregistrés dans des rapports | Microsoft Docs"
description: "Décrit l'utilisation d'options et filtre prédéfinis pour personnaliser un rapport et pour générer les données exactes."
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 10/01/2018
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: caf7cf5afe370af0c4294c794c0ff9bc8ff4c31c
ms.openlocfilehash: 9fd086831c0d145570d87c33c62a003c166aca87
ms.contentlocale: fr-ca
ms.lasthandoff: 11/22/2018

---
# <a name="managing-saved-settings-on-reports"></a><span data-ttu-id="b29aa-103">Gestion des paramètres enregistrés dans les rapports</span><span class="sxs-lookup"><span data-stu-id="b29aa-103">Managing Saved Settings on Reports</span></span>
<span data-ttu-id="b29aa-104">Lors de l'exécution d'un rapport, les utilisateurs voient généralement une page qui leur permet de définir certaines options et certains filtres pour modifier les données incluses dans le rapport généré.</span><span class="sxs-lookup"><span data-stu-id="b29aa-104">When running a reports, users are typically presented with a page that lets them set certain options and filters for changing the data that is included in the generated report.</span></span> <span data-ttu-id="b29aa-105">Cette page est appelée la page de demande du rapport.</span><span class="sxs-lookup"><span data-stu-id="b29aa-105">This page is called the report request page.</span></span> <span data-ttu-id="b29aa-106">Un rapport peut inclure un ou plusieurs *paramètres enregistrés* que les utilisateurs peuvent appliquer au rapport à partir de la page de demande.</span><span class="sxs-lookup"><span data-stu-id="b29aa-106">A report can include one or more *saved settings* that users can apply to the report from the request page.</span></span> <span data-ttu-id="b29aa-107">Les *Paramètres enregistrés* sont essentiellement des options et des filtres prédéfinis.</span><span class="sxs-lookup"><span data-stu-id="b29aa-107">*Saved settings* are basically predefined options and filters.</span></span> <span data-ttu-id="b29aa-108">Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates.</span><span class="sxs-lookup"><span data-stu-id="b29aa-108">Using saved settings is a fast and reliable way to consistently generate reports that contain the correct data.</span></span> <span data-ttu-id="b29aa-109">Pour plus d'informations sur l'utilisation des paramètres enregistrés, voir [Utilisation des paramètres enregistrés](ui-work-report.md#SavedSettings).</span><span class="sxs-lookup"><span data-stu-id="b29aa-109">For more information about how saved settings are used, see [Using Saved Settings](ui-work-report.md#SavedSettings).</span></span>

<span data-ttu-id="b29aa-110">Si vous avez les bonnes autorisations, vous pouvez visualiser, créer et modifier les paramètres enregistrés pour tous les rapports pour tous les utilisateurs de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="b29aa-110">If you have the proper permissions, you can view, create, and modify the saved settings for all reports for all users in company.</span></span> <span data-ttu-id="b29aa-111">Vous pouvez attribuer les paramètres enregistrés d'un rapport à des utilisateurs en particulier ou à tous les utilisateurs de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="b29aa-111">You can assign saved settings for a report to individual users or all users in the company.</span></span>

<!-- 
## Apply saved settings to a report
1. Open the report.

   The report request page appears.    
2. In the **Saved Settings** section of the page, set the **Name** field  to the saved settings that you want to use.

   The **Saved Settings** section only appears if the report has been run before or if there are existing saved settings entries. The saved settings entry called **Last used options and filters** is always available. These settings are the option and filter values that were used the last time you ran the report.

-->

## <a name="create-and-modify-saved-settings-for-all-users"></a><span data-ttu-id="b29aa-112">Créer et modifier les paramètres enregistrés pour tous les utilisateurs</span><span class="sxs-lookup"><span data-stu-id="b29aa-112">Create and modify saved settings for all users</span></span>
<span data-ttu-id="b29aa-113">Vous gérez les paramètres enregistrés à partir de la page **1560 Paramètres des rapports**.</span><span class="sxs-lookup"><span data-stu-id="b29aa-113">You manage saved settings from page **1560 Reports Settings**.</span></span> <span data-ttu-id="b29aa-114">Deux méthodes sont disponibles pour ouvrir cette page :</span><span class="sxs-lookup"><span data-stu-id="b29aa-114">There are two ways to open this page:</span></span>
-   <span data-ttu-id="b29aa-115">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Paramètres du rapport**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="b29aa-115">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Report Settings**, and then choose the related link.</span></span>
-   <span data-ttu-id="b29aa-116">Ouvrez un rapport, sélectionnez la fonction de recherche en regard de la zone **Utiliser les valeurs par défaut de :**, puis choisissez **Sélectionner dans la liste complète**.</span><span class="sxs-lookup"><span data-stu-id="b29aa-116">Open a report, choose the lookup next to the **Used default values from:** box, choose **Select from full list**.</span></span>

<span data-ttu-id="b29aa-117">La page affiche toutes les entrées de paramètres enregistrés existants pour tous les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="b29aa-117">The page displays all the existing save settings entries for all users.</span></span> <span data-ttu-id="b29aa-118">Si un nom d'utilisateur est indiqué dans la colonne **Affecté à**, seul cet utilisateur peut utiliser les paramètres enregistrés pour le rapport associé.</span><span class="sxs-lookup"><span data-stu-id="b29aa-118">If there is a user name in the **Assigned to** column, only that user can use the saved settings for the associated report.</span></span> <span data-ttu-id="b29aa-119">Si la colonne **Partager avec tous les utilisateurs** est cochée, tous les utilisateurs peuvent utiliser les paramètres enregistrés pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="b29aa-119">If there is a check mark in the **Share with all users** column, all users can use the saved settings for the report.</span></span>

<span data-ttu-id="b29aa-120">Dans la page **Paramètres du rapport**, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="b29aa-120">From the **Report Settings** page, you can:</span></span>
-   <span data-ttu-id="b29aa-121">Sélectionner **Nouveau** pour créer une nouvelle entrée de paramètres enregistrés.</span><span class="sxs-lookup"><span data-stu-id="b29aa-121">Choose **New** to create a new saved settings entry from scratch.</span></span>
-   <span data-ttu-id="b29aa-122">Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir **Copier** pour créer une copie.</span><span class="sxs-lookup"><span data-stu-id="b29aa-122">Select a saved settings entry from the list, and choose **Copy** to create a copy.</span></span>
-   <span data-ttu-id="b29aa-123">Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir **Modifier** pour la modifier.</span><span class="sxs-lookup"><span data-stu-id="b29aa-123">Select a saved settings entry from the list, and choose **Edit** to modify a saved settings entry.</span></span>


> [!Important]
> <span data-ttu-id="b29aa-124">Définir le nom que vous souhaitez affecter à une entrée de paramètres enregistrés.</span><span class="sxs-lookup"><span data-stu-id="b29aa-124">Consider the name that you give a saved settings entry.</span></span> <span data-ttu-id="b29aa-125">Si vous créez une entrée de paramètres enregistrés pour tous les utilisateurs et vous lui donnez le même nom que l'entrée de paramètres enregistrés existants qui est affectée à un utilisateur spécifique, alors cet utilisateur ne pourra pas utiliser l'entrée de paramètres enregistrés qui est affectée à tous.</span><span class="sxs-lookup"><span data-stu-id="b29aa-125">If you create a saved settings entry for all users, and you give it the same name as an existing saved settings entry that is assigned to a specific user only, then that user will not be able to use the saved settings entry that is assigned to everyone.</span></span>  <span data-ttu-id="b29aa-126">Sous **Paramètres enregistrés** dans la page de demande du rapport, l'utilisateur verra deux entrées de paramètres enregistrés portant le même nom.</span><span class="sxs-lookup"><span data-stu-id="b29aa-126">Under **Saved Settings** on the report request page, the user will see two saved settings entries with the same name.</span></span> <span data-ttu-id="b29aa-127">Toutefois, peu importe l'option qu'il choisit, l'entrée de paramètres enregistrés qui lui est spécifique sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="b29aa-127">However, no matter which option he chooses, the user-specific saved settings entry will be used.</span></span>

> [!NOTE]
> <span data-ttu-id="b29aa-128">La fonctionnalité Paramètres enregistrés n'est disponible que pour les rapports où la [propriété SaveValues](https://docs.microsoft.com/en-us/dynamics-nav/savevalues-property) de la page de demande du rapport est définie sur `Yes`.</span><span class="sxs-lookup"><span data-stu-id="b29aa-128">The saved settings feature is available only on reports where the [SaveValues property](https://docs.microsoft.com/en-us/dynamics-nav/savevalues-property) of the report's request page is set to `Yes`.</span></span> <span data-ttu-id="b29aa-129">La propriété **SaveValues** est définie dans l'environnement de développement.</span><span class="sxs-lookup"><span data-stu-id="b29aa-129">The **SaveValues** property is set in the development environment.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b29aa-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b29aa-130">See Also</span></span>
[<span data-ttu-id="b29aa-131">Utilisation des rapports</span><span class="sxs-lookup"><span data-stu-id="b29aa-131">Working with Reports</span></span>](ui-work-report.md)  

