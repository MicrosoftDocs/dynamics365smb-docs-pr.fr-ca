---
title: Procédure de création de soldes ouverts journal | Microsoft Docs
description: Business Central inclut plusieurs traitements en lot qui sont fournis pour aider au transfert des soldes de compte hérités vers une compagnie nouvellement configurée. Vous pouvez facilement transférer ces données avec des reports de journal.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 9e1d936901f1a42991895c9e4b797a3238a24710
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5378283"
---
# <a name="create-journal-opening-balances"></a><span data-ttu-id="4dfdf-104">Créer des soldes ouverts journal</span><span class="sxs-lookup"><span data-stu-id="4dfdf-104">Create Journal Opening Balances</span></span>

[!INCLUDE[prod_short](includes/prod_short.md)] <span data-ttu-id="4dfdf-105">inclut plusieurs traitements par lots qui sont livrés pour aider au transfert des soldes de compte hérité vers une société nouvellement configurée.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-105">includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company.</span></span> <span data-ttu-id="4dfdf-106">Vous pouvez facilement transférer ces données avec le journal clients, le journal fournisseurs, le journal articles ou le journal GL.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-106">You can easily transfer this data with the customer journal, the vendor journal, the item journal, or the G/L journal.</span></span>

<span data-ttu-id="4dfdf-107">La première étape consiste à créer un package de configuration incluant les tables de configuration pour ces journaux.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-107">The first step is to create a configuration package that includes the setup tables for those journals.</span></span> <span data-ttu-id="4dfdf-108">La procédure suivante est basée sur l’hypothèse que cette étape est terminée.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-108">The following procedure assumes that this step is completed.</span></span> <span data-ttu-id="4dfdf-109">Pour plus d'informations, voir [Définir une configuration de compagnie](admin-set-up-company-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="4dfdf-109">For more information, see [Set Up Company Configuration](admin-set-up-company-configuration.md).</span></span> <span data-ttu-id="4dfdf-110">Cette procédure explique les étapes suivantes, comme le lettrage du package qui est fourni par un partenaire.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-110">This procedure describes the subsequent steps, which include applying the package that is provided by a partner.</span></span>  

<span data-ttu-id="4dfdf-111">Avant de commencer, vérifiez que vous utilisez la page Tableau de bord Administration, car elle fournit le contexte correct pour votre travail de configuration.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-111">Before you start, make sure that you are using the Administration Role Center page because it provides the correct context for your configuration work.</span></span> <span data-ttu-id="4dfdf-112">Pour plus d'informations, voir [Modifier les paramètres de base](ui-change-basic-settings.md).</span><span class="sxs-lookup"><span data-stu-id="4dfdf-112">For more information, see [Change Basic Settings](ui-change-basic-settings.md).</span></span>

## <a name="to-apply-the-entries-in-a-journal-to-a-new-company"></a><span data-ttu-id="4dfdf-113">Pour affecter les écritures d'un journal à une compagnie</span><span class="sxs-lookup"><span data-stu-id="4dfdf-113">To apply the entries in a journal to a new company</span></span>

1. <span data-ttu-id="4dfdf-114">Configurez une nouvelle compagnie et appliquez-lui un package configuration.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-114">Configure a new company and apply a configuration package to it.</span></span> <span data-ttu-id="4dfdf-115">Pour plus d'informations, voir [Configurer une compagnie avec l’assistant RapidStart](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="4dfdf-115">For more information, see [Configure a Company with the RapidStart Wizard](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).</span></span>  

    <span data-ttu-id="4dfdf-116">La nouvelle compagnie ne contient pas d’informations sur les soldes ouverts journal.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-116">The new company does not contain information about journal opening balances.</span></span>  

2. <span data-ttu-id="4dfdf-117">Ouvrez la feuille configuration et importez les données existantes à propos des clients, des articles, des fournisseurs et du grand livre.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-117">Open the configuration worksheet and import existing data about customers, items, vendors, and the general ledger.</span></span> <span data-ttu-id="4dfdf-118">Pour plus d'informations, voir [Migrer des données client](admin-migrate-customer-data.md).</span><span class="sxs-lookup"><span data-stu-id="4dfdf-118">For more information, see [Migrate Customer Data](admin-migrate-customer-data.md).</span></span>  

    <span data-ttu-id="4dfdf-119">Les données de base sont maintenant en place.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-119">Now you have master data in place.</span></span> <span data-ttu-id="4dfdf-120">Ensuite, vous ajoutez les soldes d'ouverture.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-120">Next, you add the opening balances.</span></span> <span data-ttu-id="4dfdf-121">Les étapes suivantes décrivent comment créer des lignes journal pour les comptes du grand livre, mais la même procédure s'applique à la création de lignes journal pour les clients, les fournisseurs et les articles.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-121">The following steps describe how to create journal lines for G/L accounts, but the same apply to creating journal lines for customers, vendors, and items.</span></span>  
3. <span data-ttu-id="4dfdf-122">Choisissez l'action **Créer lignes journal compte du grand livre**.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-122">Choose the **Create G/L Acct. Journal Lines** action.</span></span>  
4. <span data-ttu-id="4dfdf-123">Renseignez le raccourci **Options** de la manière appropriée, puis définissez les filtres selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-123">Fill in the **Options** FastTab as appropriate, and set filters as needed.</span></span> <span data-ttu-id="4dfdf-124">Par exemple, dans le champ **Modèle feuille**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-124">For example, in the **Journal Template** field, enter a name.</span></span>  
5. <span data-ttu-id="4dfdf-125">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-125">Choose the **OK** button.</span></span> <span data-ttu-id="4dfdf-126">Les enregistrements se trouvent maintenant dans le journal, mais les montants sont vides.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-126">The records are now in the journal, but the amounts are empty.</span></span>  
6. <span data-ttu-id="4dfdf-127">Exportez la table journal vers Excel, puis entrez manuellement le report et les informations de compte de solde à partir des données héritées.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-127">Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data.</span></span>
7. <span data-ttu-id="4dfdf-128">Importez et appliquez les informations de table dans la nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-128">Import and apply the table information into the new company.</span></span> <span data-ttu-id="4dfdf-129">Les lignes journal sont prêtes pour le report.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-129">The journal lines are ready for posting.</span></span>  
8. <span data-ttu-id="4dfdf-130">Dans la feuille configuration, sélectionnez la table ligne journal, puis sélectionnez l'action **Données de base de données**.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-130">In the configuration worksheet, select the journal line table, and then choose the **Database Data** action.</span></span>  
9. <span data-ttu-id="4dfdf-131">Examinez les informations, puis sélectionnez l'action **Reporter**.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-131">Review the information, and then choose the **Post** action.</span></span>  
10. <span data-ttu-id="4dfdf-132">Répétez les étapes pour importer et reporter les autres soldes ouverts.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-132">Repeat the steps to import and post any other opening balances.</span></span>  

> [!TIP]
> <span data-ttu-id="4dfdf-133">Vous pouvez utiliser les mêmes traitements en lot pour ajouter des soldes d'ouverture chaque fois que vous enregistrez un nouveau client ou fournisseur avec lequel vous avez déjà traité mais qui n'est pas enregistré dans [!INCLUDE [prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="4dfdf-133">You can use the same batch jobs to add opening balances whenever you register a new customer or vendor that you have done business with before but not registered in [!INCLUDE [prod_short](includes/prod_short.md)].</span></span> <span data-ttu-id="4dfdf-134">Recherchez simplement la tâche appropriée, puis choisissez le lien approprié.</span><span class="sxs-lookup"><span data-stu-id="4dfdf-134">Just search for the relevant task, and then choose the relevant link.</span></span>

## <a name="see-also"></a><span data-ttu-id="4dfdf-135">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4dfdf-135">See Also</span></span>

[<span data-ttu-id="4dfdf-136">Appliquer des configurations à de nouvelles compagnies</span><span class="sxs-lookup"><span data-stu-id="4dfdf-136">Apply Configurations to New Companies</span></span>](admin-apply-configuration-to-new-companies.md)  
[<span data-ttu-id="4dfdf-137">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="4dfdf-137">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="4dfdf-138">Administration</span><span class="sxs-lookup"><span data-stu-id="4dfdf-138">Administration</span></span>](admin-setup-and-administration.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]