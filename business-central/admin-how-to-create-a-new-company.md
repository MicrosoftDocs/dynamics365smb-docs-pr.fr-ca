---
title: Procédure de création d'une compagnie | Microsoft Docs
description: Lorsque vous utilisez RapidStart Services, des tables et des pages sont créées, mais elles ne contiennent pas de données.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 7583837e515a4fd5fb415fe1b482512e7edf6b5a
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4754018"
---
# <a name="create-a-new-company"></a><span data-ttu-id="16496-103">Créer une compagnie</span><span class="sxs-lookup"><span data-stu-id="16496-103">Create a New Company</span></span>
<span data-ttu-id="16496-104">Pour utiliser RapidStart Services pour [!INCLUDE[prod_short](includes/prod_short.md)], vous devez d'abord créer une compagnie pour laquelle vous souhaitez effectuer une implémentation client.</span><span class="sxs-lookup"><span data-stu-id="16496-104">To use RapidStart Services for [!INCLUDE[prod_short](includes/prod_short.md)], you first create a new company for which you want to perform a customer implementation.</span></span> <span data-ttu-id="16496-105">Lorsque vous créez une société, les tables et les pages standard de [!INCLUDE[prod_short](includes/prod_short.md)] sont créées, mais elles ne contiennent pas de données.</span><span class="sxs-lookup"><span data-stu-id="16496-105">When you create a new company, the standard [!INCLUDE[prod_short](includes/prod_short.md)] tables and pages are created, but there is no data in them.</span></span>

<span data-ttu-id="16496-106">Vous pouvez également appliquer des données de configuration spécifiques à votre compagnie après l’avoir initialisée.</span><span class="sxs-lookup"><span data-stu-id="16496-106">In addition, you can apply specific setup data to your company after you initialize it.</span></span> <span data-ttu-id="16496-107">Les informations sont fournies dans un package de configuration, un fichier .rapidstart, qui fournit le contenu sous un format compressé.</span><span class="sxs-lookup"><span data-stu-id="16496-107">The information is provided in a configuration package, a .rapidstart file, which delivers content in a compressed format.</span></span>  

<span data-ttu-id="16496-108">Des exemples de packages de configuration, qui comprennent des fichiers spécifiques à un pays/une région, sont inclus avec la compagnie de démonstration CRONUS.</span><span class="sxs-lookup"><span data-stu-id="16496-108">Example configuration packages, including country/region-specific files, are included with the CRONUS demonstration company.</span></span> <span data-ttu-id="16496-109">Suivez la procédure suivante pour utiliser l'exemple de package de configuration avec une nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="16496-109">Use the following procedures to use the example configuration package with a new company.</span></span>  

## <a name="to-use-the-sample-basicconfig-configuration-package"></a><span data-ttu-id="16496-110">Pour utiliser l'exemple de package de configuration BASICCONFIG</span><span class="sxs-lookup"><span data-stu-id="16496-110">To use the sample BASICCONFIG configuration package</span></span>  
1. <span data-ttu-id="16496-111">Ouvrez la compagnie CRONUS International Ltd.</span><span class="sxs-lookup"><span data-stu-id="16496-111">Open the CRONUS International Ltd. company.</span></span> <span data-ttu-id="16496-112">Pour plus d'informations, voir [Modifier les paramètres de base](ui-change-basic-settings.md).</span><span class="sxs-lookup"><span data-stu-id="16496-112">For more information, see [Change Basic Settings](ui-change-basic-settings.md).</span></span>
2. <span data-ttu-id="16496-113">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Packages configuration**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="16496-113">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Configuration Packages**, and then choose the related link.</span></span>  
3. <span data-ttu-id="16496-114">Sélectionnez le package BASICCONFIG dans la liste, puis sélectionnez l'action **Exporter package**.</span><span class="sxs-lookup"><span data-stu-id="16496-114">Choose the BASICCONFIG package from the list, and then choose the **Export Package** action.</span></span>  

<span data-ttu-id="16496-115">Suivez la procédure suivante pour créer une compagnie, puis utilisez le package BASICCONFIG dans le cadre du processus.</span><span class="sxs-lookup"><span data-stu-id="16496-115">Use the following procedure to create a new company, and use the BASICCONFIG package as part of the process.</span></span>  

## <a name="to-create-a-new-company"></a><span data-ttu-id="16496-116">Création d'une nouvelle compagnie</span><span class="sxs-lookup"><span data-stu-id="16496-116">To create a new company</span></span>  
1. <span data-ttu-id="16496-117">Créer une nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="16496-117">Create a new company.</span></span> <span data-ttu-id="16496-118">Pour plus d'informations, voir [Création de compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)]](about-new-company.md).</span><span class="sxs-lookup"><span data-stu-id="16496-118">For more information, see [Creating New Companies in [!INCLUDE[prod_short](includes/prod_short.md)]](about-new-company.md).</span></span>
2. <span data-ttu-id="16496-119">Dans le tableau de bord Responsable de l'implémentation de RapidStart Services, vous pouvez maintenant importer le package de configuration que vous avez exporté de la compagnie CRONUS International Ltd.</span><span class="sxs-lookup"><span data-stu-id="16496-119">From the RapidStart Services Implementer Role Center, you can now import the configuration package that you exported from the CRONUS International Ltd. company.</span></span>

<span data-ttu-id="16496-120">Une fois que vous avez créé une compagnie, certaines tables se renseignent automatiquement, même si aucun modèle de compagnie n'est appliqué.</span><span class="sxs-lookup"><span data-stu-id="16496-120">After you create a new company, some tables are automatically filled in, even if no company template is applied.</span></span> <span data-ttu-id="16496-121">Par exemple, vous pouvez consulter les codes standard pour les transactions par lots et le report sur la page **Code origine**.</span><span class="sxs-lookup"><span data-stu-id="16496-121">For example, you can review the standard codes for posting and batch transactions on the **Source Code** page.</span></span> <span data-ttu-id="16496-122">Si vous disposez d'une version locale de [!INCLUDE[prod_short](includes/prod_short.md)], consultez cette table en tenant compte d'éventuels problèmes de langue locale.</span><span class="sxs-lookup"><span data-stu-id="16496-122">If you provide a local version of [!INCLUDE[prod_short](includes/prod_short.md)], you should review this table and consider any local language issues.</span></span>

## <a name="about-data-tables"></a><span data-ttu-id="16496-123">À propos des tables de données</span><span class="sxs-lookup"><span data-stu-id="16496-123">About Data Tables</span></span>
[!INCLUDE[prod_short](includes/prod_short.md)]<span data-ttu-id="16496-124">, les tables de données existent en deux types de base : Principale et Configuration.</span><span class="sxs-lookup"><span data-stu-id="16496-124">, data tables come in two basic types: Master and Setup.</span></span> <span data-ttu-id="16496-125">Lorsque vous paramétrez une configuration de compagnie, vous pouvez utiliser ces types afin de cibler votre stratégie de configuration.</span><span class="sxs-lookup"><span data-stu-id="16496-125">When you are setting up a company configuration, you can use these types to focus your configuration strategy.</span></span>  

### <a name="master-data-tables"></a><span data-ttu-id="16496-126">Tables de données principales</span><span class="sxs-lookup"><span data-stu-id="16496-126">Master Data Tables</span></span>  
<span data-ttu-id="16496-127">Le tableau suivant répertorie certaines tables de données principales.</span><span class="sxs-lookup"><span data-stu-id="16496-127">The following table lists some of the master data tables.</span></span> <span data-ttu-id="16496-128">Lorsque vous lancez une nouvelle compagnie, ces tables sont vides.</span><span class="sxs-lookup"><span data-stu-id="16496-128">When you initialize a new company, these tables are empty.</span></span>  

|<span data-ttu-id="16496-129">N° table</span><span class="sxs-lookup"><span data-stu-id="16496-129">Table No.</span></span>|<span data-ttu-id="16496-130">Nom de table</span><span class="sxs-lookup"><span data-stu-id="16496-130">Table Name</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="16496-131">15</span><span class="sxs-lookup"><span data-stu-id="16496-131">15</span></span>|<span data-ttu-id="16496-132">Compte général</span><span class="sxs-lookup"><span data-stu-id="16496-132">G/L Account</span></span>|  
|<span data-ttu-id="16496-133">18</span><span class="sxs-lookup"><span data-stu-id="16496-133">18</span></span>|<span data-ttu-id="16496-134">Client</span><span class="sxs-lookup"><span data-stu-id="16496-134">Customer</span></span>|  
|<span data-ttu-id="16496-135">23</span><span class="sxs-lookup"><span data-stu-id="16496-135">23</span></span>|<span data-ttu-id="16496-136">Fournisseur</span><span class="sxs-lookup"><span data-stu-id="16496-136">Vendor</span></span>|  
|<span data-ttu-id="16496-137">27</span><span class="sxs-lookup"><span data-stu-id="16496-137">27</span></span>|<span data-ttu-id="16496-138">Article</span><span class="sxs-lookup"><span data-stu-id="16496-138">Item</span></span>|  
|<span data-ttu-id="16496-139">5050</span><span class="sxs-lookup"><span data-stu-id="16496-139">5050</span></span>|<span data-ttu-id="16496-140">Contact</span><span class="sxs-lookup"><span data-stu-id="16496-140">Contact</span></span>|  

### <a name="setup-data-tables"></a><span data-ttu-id="16496-141">Tables de données de configuration</span><span class="sxs-lookup"><span data-stu-id="16496-141">Setup Data Tables</span></span>  
<span data-ttu-id="16496-142">Le tableau suivant répertorie certaines tables de données de configuration à partir desquelles vous capturez les informations de configuration dans le questionnaire de configuration.</span><span class="sxs-lookup"><span data-stu-id="16496-142">The following table lists some of the setup data tables, in which you capture setup information in the configuration questionnaire.</span></span> <span data-ttu-id="16496-143">Ces tables contiennent des informations de base lors de la création de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="16496-143">These tables contain baseline information when the company is created.</span></span>  

|<span data-ttu-id="16496-144">Numéro table</span><span class="sxs-lookup"><span data-stu-id="16496-144">Table No.</span></span>|<span data-ttu-id="16496-145">Nom de table</span><span class="sxs-lookup"><span data-stu-id="16496-145">Table Name</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="16496-146">98</span><span class="sxs-lookup"><span data-stu-id="16496-146">98</span></span>|<span data-ttu-id="16496-147">Configuration du grand livre</span><span class="sxs-lookup"><span data-stu-id="16496-147">General Ledger Setup</span></span>|  
|<span data-ttu-id="16496-148">311</span><span class="sxs-lookup"><span data-stu-id="16496-148">311</span></span>|<span data-ttu-id="16496-149">Configuration ventes & à recevoir</span><span class="sxs-lookup"><span data-stu-id="16496-149">Sales & Receivables Setup</span></span>|  
|<span data-ttu-id="16496-150">312</span><span class="sxs-lookup"><span data-stu-id="16496-150">312</span></span>|<span data-ttu-id="16496-151">Configuration achats et à payer</span><span class="sxs-lookup"><span data-stu-id="16496-151">Purchases & Payables Setup</span></span>|  
|<span data-ttu-id="16496-152">313</span><span class="sxs-lookup"><span data-stu-id="16496-152">313</span></span>|<span data-ttu-id="16496-153">Configuration de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="16496-153">Inventory Setup</span></span>|  

<span data-ttu-id="16496-154">Outre des tables de données de configuration, [!INCLUDE[prod_short](includes/prod_short.md)] dispose également de tables de données de type configuration qui spécifient des informations de base sur la compagnie et ses processus entreprise.</span><span class="sxs-lookup"><span data-stu-id="16496-154">In addition to setup data tables, [!INCLUDE[prod_short](includes/prod_short.md)] also has setup-type data tables that specify core information about the company and its business processes.</span></span> <span data-ttu-id="16496-155">Le tableau suivant répertorie certaines d'entre elles.</span><span class="sxs-lookup"><span data-stu-id="16496-155">The following table lists some of them.</span></span>  

|<span data-ttu-id="16496-156">N° table</span><span class="sxs-lookup"><span data-stu-id="16496-156">Table No.</span></span>|<span data-ttu-id="16496-157">Nom de table</span><span class="sxs-lookup"><span data-stu-id="16496-157">Table Name</span></span>|  
|-------------------|--------------------|  
|<span data-ttu-id="16496-158">3</span><span class="sxs-lookup"><span data-stu-id="16496-158">3</span></span>|<span data-ttu-id="16496-159">Modalités de paiement</span><span class="sxs-lookup"><span data-stu-id="16496-159">Payment Terms</span></span>|  
|<span data-ttu-id="16496-160">4</span><span class="sxs-lookup"><span data-stu-id="16496-160">4</span></span>|<span data-ttu-id="16496-161">Devise</span><span class="sxs-lookup"><span data-stu-id="16496-161">Currency</span></span>|  
|<span data-ttu-id="16496-162">6</span><span class="sxs-lookup"><span data-stu-id="16496-162">6</span></span>|<span data-ttu-id="16496-163">Groupes prix client</span><span class="sxs-lookup"><span data-stu-id="16496-163">Customer Price Groups</span></span>|  
|<span data-ttu-id="16496-164">5700</span><span class="sxs-lookup"><span data-stu-id="16496-164">5700</span></span>|<span data-ttu-id="16496-165">Unité de stock</span><span class="sxs-lookup"><span data-stu-id="16496-165">Stockkeeping Unit</span></span>|

  

## <a name="see-also"></a><span data-ttu-id="16496-166">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16496-166">See Also</span></span>  
[<span data-ttu-id="16496-167">Appliquer des configurations à de nouvelles compagnies</span><span class="sxs-lookup"><span data-stu-id="16496-167">Apply Configurations to New Companies</span></span>](admin-apply-configuration-to-new-companies.md)  
[<span data-ttu-id="16496-168">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="16496-168">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="16496-169">Administration</span><span class="sxs-lookup"><span data-stu-id="16496-169">Administration</span></span>](admin-setup-and-administration.md)
