---
title: "Procédure de création de packages de configuration de compagnie personnalisés | Microsoft Docs"
description: "À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: e26174fcf723e13ef5a9ed0b386006c0439e1c7a
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="create-custom-company-configuration-packages"></a><span data-ttu-id="45a04-104">Créer des packages de configuration de compagnie personnalisés</span><span class="sxs-lookup"><span data-stu-id="45a04-104">Create Custom Company Configuration Packages</span></span>
<span data-ttu-id="45a04-105">À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients.</span><span class="sxs-lookup"><span data-stu-id="45a04-105">As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers.</span></span> <span data-ttu-id="45a04-106">Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.</span><span class="sxs-lookup"><span data-stu-id="45a04-106">You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.</span></span>  

<span data-ttu-id="45a04-107">En général, créez un colis configuration par domaine fonctionnel, par exemple, créez un colis pour la fonctionnalité de fabrication.</span><span class="sxs-lookup"><span data-stu-id="45a04-107">In general, create a configuration package per functional area, for example, create a package for your manufacturing functionality.</span></span> <span data-ttu-id="45a04-108">Cela vous permet d’appliquer et de configurer de nouveaux domaines au sein d’une compagnie en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="45a04-108">That lets you apply and set up new areas in a company as you need them</span></span>  

<span data-ttu-id="45a04-109">Autrement, vous pouvez créer un colis qui inclut les tables qui définissent la configuration, par exemple :</span><span class="sxs-lookup"><span data-stu-id="45a04-109">Another approach would be to create a package that includes the tables that define setup, such as the following:</span></span>  

-   <span data-ttu-id="45a04-110">Configuration des immobilisations</span><span class="sxs-lookup"><span data-stu-id="45a04-110">Fixed Asset Setup</span></span>  
-   <span data-ttu-id="45a04-111">Configuration du grand livre</span><span class="sxs-lookup"><span data-stu-id="45a04-111">General Ledger Setup</span></span>  
-   <span data-ttu-id="45a04-112">Configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="45a04-112">Inventory Setup</span></span>  
-   <span data-ttu-id="45a04-113">Configuration de la fabrication</span><span class="sxs-lookup"><span data-stu-id="45a04-113">Manufacturing Setup</span></span>  
-   <span data-ttu-id="45a04-114">Configuration achats et à payer</span><span class="sxs-lookup"><span data-stu-id="45a04-114">Purchases and Payables Setup</span></span>  
-   <span data-ttu-id="45a04-115">Configuration du marketing</span><span class="sxs-lookup"><span data-stu-id="45a04-115">Marketing Setup</span></span>  
-   <span data-ttu-id="45a04-116">Configuration de service</span><span class="sxs-lookup"><span data-stu-id="45a04-116">Service Setup</span></span>  
-   <span data-ttu-id="45a04-117">Config. ventes et à recevoir</span><span class="sxs-lookup"><span data-stu-id="45a04-117">Sales and Receivables Setup</span></span>  
-   <span data-ttu-id="45a04-118">Configuration d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="45a04-118">Warehouse Setup</span></span>  
-   <span data-ttu-id="45a04-119">Config. paramètres report</span><span class="sxs-lookup"><span data-stu-id="45a04-119">General Posting Setup</span></span>  
-   <span data-ttu-id="45a04-120">Configuration report de taxe</span><span class="sxs-lookup"><span data-stu-id="45a04-120">VAT Posting Setup</span></span>  
-   <span data-ttu-id="45a04-121">Configuration du report d'inventaire</span><span class="sxs-lookup"><span data-stu-id="45a04-121">Inventory Posting Setup</span></span>  

<span data-ttu-id="45a04-122">Pour visualiser la liste complète des tables de configuration, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="45a04-122">To see a complete list of setup tables, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Setup**, and then choose the related link.</span></span>  

## <a name="to-create-a-custom-company-configuration-package"></a><span data-ttu-id="45a04-123">Pour créer un package de configuration de compagnie personnalisé</span><span class="sxs-lookup"><span data-stu-id="45a04-123">To create a custom company configuration package</span></span>  
1.  <span data-ttu-id="45a04-124">Créez une [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="45a04-124">Create a new [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="45a04-125">***Lien NON POSSIBLE pour aider à la « création d'un abonné »***.</span><span class="sxs-lookup"><span data-stu-id="45a04-125">***NOT POSSIBLE Link to help for "Creating a New Tenant"***.</span></span>   
2.  <span data-ttu-id="45a04-126">Créez une compagnie pour le modèle solution ou secteur d'utilisation.</span><span class="sxs-lookup"><span data-stu-id="45a04-126">Create a new company for the industry or solution template.</span></span> <span data-ttu-id="45a04-127">Pour plus d’informations, voir [Créer une compagnie](admin-how-to-create-a-new-company.md).</span><span class="sxs-lookup"><span data-stu-id="45a04-127">For more information, see [Create a New Company](admin-how-to-create-a-new-company.md).</span></span>  
3.  <span data-ttu-id="45a04-128">Configurer la nouvelle compagnie en tenant compte de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="45a04-128">Setup the new company in the way you need.</span></span> <span data-ttu-id="45a04-129">Renseignez toutes les tables de configuration nécessaires.</span><span class="sxs-lookup"><span data-stu-id="45a04-129">Fill in all required setup tables.</span></span>  
4.  <span data-ttu-id="45a04-130">Ouvrir la nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="45a04-130">Open the new company.</span></span>
5. <span data-ttu-id="45a04-131">Ouvrez la fenêtre **Feuille configuration**.</span><span class="sxs-lookup"><span data-stu-id="45a04-131">Open the **Configuration Worksheet** window.</span></span>  
6.  <span data-ttu-id="45a04-132">Ajoutez les tables que vous souhaitez transférer vers une autre compagnie à la feuille.</span><span class="sxs-lookup"><span data-stu-id="45a04-132">Add the tables that you want to transfer to another company to the worksheet.</span></span> <span data-ttu-id="45a04-133">Affecter des lignes feuille au colis.</span><span class="sxs-lookup"><span data-stu-id="45a04-133">Assign the worksheet lines to the package.</span></span>  
7.  <span data-ttu-id="45a04-134">Créez un questionnaire pour les tables de configuration les plus souvent utilisées.</span><span class="sxs-lookup"><span data-stu-id="45a04-134">Create a questionnaire for the most frequently used setup tables.</span></span>  
8.  <span data-ttu-id="45a04-135">Créez des modèles de configuration pour faciliter la création de données de base, telles que les clients ou les articles.</span><span class="sxs-lookup"><span data-stu-id="45a04-135">Create configuration templates to make it easier to create master data, such as customers or items.</span></span>  
9.  <span data-ttu-id="45a04-136">Exportez votre package comme fichier .rapidstart.</span><span class="sxs-lookup"><span data-stu-id="45a04-136">Export your package as a .rapidstart file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="45a04-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45a04-137">See Also</span></span>  
[<span data-ttu-id="45a04-138">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="45a04-138">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="45a04-139">Administration</span><span class="sxs-lookup"><span data-stu-id="45a04-139">Administration</span></span>](admin-setup-and-administration.md)

