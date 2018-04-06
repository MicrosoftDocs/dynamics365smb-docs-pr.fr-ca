---
title: "Procédure de création de soldes ouverts journal | Microsoft Docs"
description: "Business Central inclut plusieurs traitements en lot qui sont fournis pour aider au transfert des soldes de compte hérités vers une compagnie nouvellement configurée. Vous pouvez facilement transférer ces données avec des reports de journal."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: be45ed1de52c92722d801da344163fdffc2a9073
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-journal-opening-balances"></a><span data-ttu-id="45cfb-104">Créer des soldes ouverts journal</span><span class="sxs-lookup"><span data-stu-id="45cfb-104">Create Journal Opening Balances</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="45cfb-105"> inclut plusieurs traitements par lots qui sont livrés pour aider au transfert des soldes de compte hérité vers une société nouvellement configurée.</span><span class="sxs-lookup"><span data-stu-id="45cfb-105"> includes several batch jobs that are provided to help in the transfer of legacy account balances to a newly configured company.</span></span> <span data-ttu-id="45cfb-106">Vous pouvez facilement transférer ces données avec le journal clients, le journal fournisseurs, le journal articles ou le journal GL.</span><span class="sxs-lookup"><span data-stu-id="45cfb-106">You can easily transfer this data with the customer journal, the vendor journal, the item journal, or the G/L journal.</span></span>

<span data-ttu-id="45cfb-107">La première étape consiste à créer un package de configuration incluant les tables de configuration pour ces journaux.</span><span class="sxs-lookup"><span data-stu-id="45cfb-107">The first step is to create a configuration package that includes the setup tables for those journals.</span></span> <span data-ttu-id="45cfb-108">La procédure suivante est basée sur l’hypothèse que cette étape est terminée.</span><span class="sxs-lookup"><span data-stu-id="45cfb-108">The following procedure assumes that this step is completed.</span></span> <span data-ttu-id="45cfb-109">Pour plus d'informations, voir [Définir une configuration de compagnie](admin-set-up-company-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="45cfb-109">For more information, see [Set Up Company Configuration](admin-set-up-company-configuration.md).</span></span> <span data-ttu-id="45cfb-110">Cette procédure explique les étapes suivantes, comme le lettrage du package qui est fourni par un partenaire.</span><span class="sxs-lookup"><span data-stu-id="45cfb-110">This procedure describes the subsequent steps, which include applying the package that is provided by a partner.</span></span>  

<span data-ttu-id="45cfb-111">Avant de commencer, vérifiez que vous vous trouvez sur la page du tableau de bord Responsable de l'implémentation de RapidStart Services, car elle fournit le contexte correct pour votre travail de configuration.</span><span class="sxs-lookup"><span data-stu-id="45cfb-111">Before you start, make sure that you are on the RapidStart Services Implementer Role Center page as it provides the correct context for your configuration work.</span></span> <span data-ttu-id="45cfb-112">Pour plus d'informations, voir [Modification des paramètres de base](ui-change-basic-settings.md).</span><span class="sxs-lookup"><span data-stu-id="45cfb-112">For more information, see [Changing Basic Settings](ui-change-basic-settings.md).</span></span>

## <a name="to-apply-the-entries-in-a-journal-to-a-new-company"></a><span data-ttu-id="45cfb-113">Pour affecter les écritures d'un journal à une compagnie</span><span class="sxs-lookup"><span data-stu-id="45cfb-113">To apply the entries in a journal to a new company</span></span>  
1. <span data-ttu-id="45cfb-114">Configurez une nouvelle compagnie et appliquez-lui un package de configuration.</span><span class="sxs-lookup"><span data-stu-id="45cfb-114">Configure a new company and apply a configuration package to it.</span></span> <span data-ttu-id="45cfb-115">Pour plus d'informations, voir [Configurer une compagnie avec l’assistant RapidStart](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="45cfb-115">For more information, see [Configure a Company with the RapidStart Wizard](admin-how-to-configure-a-company-with-the-rapidstart-wizard.md).</span></span>  

    <span data-ttu-id="45cfb-116">La nouvelle compagnie ne contient pas d’informations sur les soldes ouverts journal.</span><span class="sxs-lookup"><span data-stu-id="45cfb-116">The new company does not contain information about journal opening balances.</span></span>  

2. <span data-ttu-id="45cfb-117">Ouvrez la feuille configuration et importez les données existantes à propos des clients, des articles, des fournisseurs et du grand livre.</span><span class="sxs-lookup"><span data-stu-id="45cfb-117">Open the configuration worksheet and import existing data about customers, items, vendors, and the general ledger.</span></span> <span data-ttu-id="45cfb-118">Pour plus d'informations, voir [Migrer des données client](admin-migrate-customer-data.md).</span><span class="sxs-lookup"><span data-stu-id="45cfb-118">For more information, see [Migrate Customer Data](admin-migrate-customer-data.md).</span></span>  
3. <span data-ttu-id="45cfb-119">Choisissez, par exemple, l'action **Créer lignes feuille compta**.</span><span class="sxs-lookup"><span data-stu-id="45cfb-119">Choose, for example, the **Create G/L Journal Lines** action.</span></span>  
4. <span data-ttu-id="45cfb-120">Renseignez le raccourci **Options** de la manière appropriée, puis définissez les filtres selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="45cfb-120">Fill in the **Options** FastTab as appropriate, and set filters as needed.</span></span> <span data-ttu-id="45cfb-121">Par exemple, dans le champ **Modèle feuille**, entrez un nom.</span><span class="sxs-lookup"><span data-stu-id="45cfb-121">For example, in the **Journal Template** field, enter a name.</span></span>  
5. <span data-ttu-id="45cfb-122">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="45cfb-122">Choose the **OK** button.</span></span> <span data-ttu-id="45cfb-123">Les enregistrements se trouvent maintenant dans le journal, mais les montants sont vides.</span><span class="sxs-lookup"><span data-stu-id="45cfb-123">The records are now in the journal, but the amounts are empty.</span></span>  
6. <span data-ttu-id="45cfb-124">Exportez la table journal vers Excel, puis entrez manuellement le report et les informations de compte de solde à partir des données héritées.</span><span class="sxs-lookup"><span data-stu-id="45cfb-124">Export the journal table to Excel and manually enter the posting and balancing account information from the legacy data.</span></span>
7. <span data-ttu-id="45cfb-125">Importez et appliquez les informations de table dans la nouvelle compagnie.</span><span class="sxs-lookup"><span data-stu-id="45cfb-125">Import and apply the table information into the new company.</span></span> <span data-ttu-id="45cfb-126">Les lignes journal sont prêtes pour le report.</span><span class="sxs-lookup"><span data-stu-id="45cfb-126">The journal lines are ready for posting.</span></span>  
8. <span data-ttu-id="45cfb-127">Dans la feuille configuration, sélectionnez la table ligne journal, puis sélectionnez l'action **Données de base de données**.</span><span class="sxs-lookup"><span data-stu-id="45cfb-127">In the configuration worksheet, select the journal line table, and then choose the **Database Data** action.</span></span>  
9. <span data-ttu-id="45cfb-128">Examinez les informations, puis sélectionnez l'action **Reporter**.</span><span class="sxs-lookup"><span data-stu-id="45cfb-128">Review the information, and then choose the **Post** action.</span></span>  
10. <span data-ttu-id="45cfb-129">Répétez les étapes pour importer et reporter les autres soldes ouverts.</span><span class="sxs-lookup"><span data-stu-id="45cfb-129">Repeat the steps to import and post any other opening balances.</span></span>  

## <a name="see-also"></a><span data-ttu-id="45cfb-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="45cfb-130">See Also</span></span>  
[<span data-ttu-id="45cfb-131">Appliquer des configurations à de nouvelles compagnies</span><span class="sxs-lookup"><span data-stu-id="45cfb-131">Apply Configurations to New Companies</span></span>](admin-apply-configuration-to-new-companies.md)  
[<span data-ttu-id="45cfb-132">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="45cfb-132">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="45cfb-133">Administration</span><span class="sxs-lookup"><span data-stu-id="45cfb-133">Administration</span></span>](admin-setup-and-administration.md)

