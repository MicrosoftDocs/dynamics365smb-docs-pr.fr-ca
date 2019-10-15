---
title: Procédure de création de packages de configuration de compagnie personnalisés | Microsoft Docs
description: À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 6fd35133d16056b947db6680cc9a76cfccaa6a3c
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2308097"
---
# <a name="create-custom-company-configuration-packages"></a><span data-ttu-id="075af-104">Créer des packages de configuration de compagnie personnalisés</span><span class="sxs-lookup"><span data-stu-id="075af-104">Create Custom Company Configuration Packages</span></span>
<span data-ttu-id="075af-105">À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients.</span><span class="sxs-lookup"><span data-stu-id="075af-105">As you grow your business, you will likely come to rely on a set of company types that you use with most of your customers.</span></span> <span data-ttu-id="075af-106">Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.</span><span class="sxs-lookup"><span data-stu-id="075af-106">You can streamline your implementation process by turning these types into company configuration packages that are available for reuse.</span></span>  

<span data-ttu-id="075af-107">En général, créez un colis configuration par domaine fonctionnel, par exemple, créez un colis pour la fonctionnalité de fabrication.</span><span class="sxs-lookup"><span data-stu-id="075af-107">In general, create a configuration package per functional area, for example, create a package for your manufacturing functionality.</span></span> <span data-ttu-id="075af-108">Cela vous permet d’appliquer et de configurer de nouveaux domaines au sein d’une compagnie en fonction de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="075af-108">That lets you apply and set up new areas in a company as you need them</span></span>  

<span data-ttu-id="075af-109">Autrement, vous pouvez créer un colis qui inclut les tables qui définissent la configuration, par exemple :</span><span class="sxs-lookup"><span data-stu-id="075af-109">Another approach would be to create a package that includes the tables that define setup, such as the following:</span></span>  

-   <span data-ttu-id="075af-110">Configuration des immobilisations</span><span class="sxs-lookup"><span data-stu-id="075af-110">Fixed Asset Setup</span></span>  
-   <span data-ttu-id="075af-111">Configuration du grand livre</span><span class="sxs-lookup"><span data-stu-id="075af-111">General Ledger Setup</span></span>  
-   <span data-ttu-id="075af-112">Configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="075af-112">Inventory Setup</span></span>  
-   <span data-ttu-id="075af-113">Configuration de la fabrication</span><span class="sxs-lookup"><span data-stu-id="075af-113">Manufacturing Setup</span></span>  
-   <span data-ttu-id="075af-114">Configuration achats et à payer</span><span class="sxs-lookup"><span data-stu-id="075af-114">Purchases and Payables Setup</span></span>  
-   <span data-ttu-id="075af-115">Configuration du marketing</span><span class="sxs-lookup"><span data-stu-id="075af-115">Marketing Setup</span></span>  
-   <span data-ttu-id="075af-116">Configuration de service</span><span class="sxs-lookup"><span data-stu-id="075af-116">Service Setup</span></span>  
-   <span data-ttu-id="075af-117">Config. ventes et à recevoir</span><span class="sxs-lookup"><span data-stu-id="075af-117">Sales and Receivables Setup</span></span>  
-   <span data-ttu-id="075af-118">Configuration d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="075af-118">Warehouse Setup</span></span>  
-   <span data-ttu-id="075af-119">Config. paramètres report</span><span class="sxs-lookup"><span data-stu-id="075af-119">General Posting Setup</span></span>  
-   <span data-ttu-id="075af-120">Configuration report de taxe</span><span class="sxs-lookup"><span data-stu-id="075af-120">VAT Posting Setup</span></span>  
-   <span data-ttu-id="075af-121">Configuration du report d'inventaire</span><span class="sxs-lookup"><span data-stu-id="075af-121">Inventory Posting Setup</span></span>  

<span data-ttu-id="075af-122">Pour visualiser la liste complète des tables de configuration, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration manuelle**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="075af-122">To see a complete list of setup tables, Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Manual Setup**, and then choose the related link.</span></span>  

## <a name="to-create-a-custom-company-configuration-package"></a><span data-ttu-id="075af-123">Pour créer un package de configuration de compagnie personnalisé</span><span class="sxs-lookup"><span data-stu-id="075af-123">To create a custom company configuration package</span></span>  
1.  <span data-ttu-id="075af-124">Créer une nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="075af-124">Create a new company.</span></span> <span data-ttu-id="075af-125">Pour plus d'informations, voir [Création de compagnies dans Business Central](about-new-company.md).</span><span class="sxs-lookup"><span data-stu-id="075af-125">For more information, see [Creating New Companies in Business Central](about-new-company.md).</span></span>  
3.  <span data-ttu-id="075af-126">Configurez la nouvelle compagnie en tenant compte de vos besoins.</span><span class="sxs-lookup"><span data-stu-id="075af-126">Set up the new company in the way you need.</span></span> <span data-ttu-id="075af-127">Renseignez toutes les tables de configuration nécessaires.</span><span class="sxs-lookup"><span data-stu-id="075af-127">Fill in all required setup tables.</span></span>  
4.  <span data-ttu-id="075af-128">Ouvrir la nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="075af-128">Open the new company.</span></span>
5. <span data-ttu-id="075af-129">Ouvrir la page **Feuille configuration**.</span><span class="sxs-lookup"><span data-stu-id="075af-129">Open the **Configuration Worksheet** page.</span></span>  
6.  <span data-ttu-id="075af-130">Ajoutez les tables que vous souhaitez transférer vers une autre compagnie à la feuille.</span><span class="sxs-lookup"><span data-stu-id="075af-130">Add the tables that you want to transfer to another company to the worksheet.</span></span> <span data-ttu-id="075af-131">Affecter des lignes feuille au colis.</span><span class="sxs-lookup"><span data-stu-id="075af-131">Assign the worksheet lines to the package.</span></span>  
7.  <span data-ttu-id="075af-132">Créez un questionnaire pour les tables de configuration les plus souvent utilisées.</span><span class="sxs-lookup"><span data-stu-id="075af-132">Create a questionnaire for the most frequently used setup tables.</span></span>  
8.  <span data-ttu-id="075af-133">Créez des modèles de configuration pour faciliter la création de données de base, telles que les clients ou les articles.</span><span class="sxs-lookup"><span data-stu-id="075af-133">Create configuration templates to make it easier to create master data, such as customers or items.</span></span>  
9.  <span data-ttu-id="075af-134">Exportez votre package comme fichier .rapidstart.</span><span class="sxs-lookup"><span data-stu-id="075af-134">Export your package as a .rapidstart file.</span></span>  

## <a name="see-also"></a><span data-ttu-id="075af-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="075af-135">See Also</span></span>  
[<span data-ttu-id="075af-136">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="075af-136">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="075af-137">Administration</span><span class="sxs-lookup"><span data-stu-id="075af-137">Administration</span></span>](admin-setup-and-administration.md)
