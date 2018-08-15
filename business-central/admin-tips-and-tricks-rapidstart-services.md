---
title: Conseils - RapidStart Services | Microsoft Docs
description: "Lorsque vous configurez des compagnies avec RapidStart Services, il est recommandé de suivre certains conseils pour faciliter votre implémentation."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/05/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 4e8dc4436b01f69292a01afbc7a5d0381b544a77
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="tips-and-tricks-rapidstart-services"></a><span data-ttu-id="7b275-103">Conseils : services RapidStart</span><span class="sxs-lookup"><span data-stu-id="7b275-103">Tips and Tricks: RapidStart Services</span></span>
<span data-ttu-id="7b275-104">Lorsque vous configurez des compagnies avec RapidStart Services, il est recommandé de suivre certains conseils pour faciliter votre implémentation.</span><span class="sxs-lookup"><span data-stu-id="7b275-104">When you configure companies using RapidStart Services, there are some tips and tricks that you can take advantage of to help your implementation go smoothly.</span></span>  

## <a name="take-advantage-of-configuration-templates"></a><span data-ttu-id="7b275-105">Optimisation des modèles de société</span><span class="sxs-lookup"><span data-stu-id="7b275-105">Take advantage of configuration templates</span></span>  
<span data-ttu-id="7b275-106">Les modèles de configuration peuvent vous aider à rationaliser votre processus d’implémentation.</span><span class="sxs-lookup"><span data-stu-id="7b275-106">Configuration templates can help you streamline your implementation process.</span></span> <span data-ttu-id="7b275-107">Ces modèles vous permettent d'inclure des clients similaires dans des segments, puis de développer un protocole d'implémentation qui traite tous les clients d'un segment de la même façon.</span><span class="sxs-lookup"><span data-stu-id="7b275-107">By using them, you can include similar customers in segments and then develop an implementation protocol that treats all customers in a segment in a similar manner.</span></span> <span data-ttu-id="7b275-108">Vous pouvez ainsi appliquer un niveau de préconfiguration à chaque segment et procéder rapidement à une implémentation.</span><span class="sxs-lookup"><span data-stu-id="7b275-108">In that way, you can apply a level of preconfiguration to each segment and continue with a rapid implementation.</span></span>  

## <a name="configuration-questionnaires"></a><span data-ttu-id="7b275-109">Questionnaires de configuration</span><span class="sxs-lookup"><span data-stu-id="7b275-109">Configuration questionnaires</span></span>  
<span data-ttu-id="7b275-110">Pour faciliter le remplissage d’un questionnaire de configuration, envisagez de définir des réponses par défaut pour indiquer des recommandations.</span><span class="sxs-lookup"><span data-stu-id="7b275-110">To aid the process of filling out a configuration questionnaire, consider defining default answers to indicate best practices.</span></span>  

## <a name="batch-creation-of-journal-lines"></a><span data-ttu-id="7b275-111">Création de lignes journal par lots</span><span class="sxs-lookup"><span data-stu-id="7b275-111">Batch creation of journal lines</span></span>  
<span data-ttu-id="7b275-112">Il est recommandé d'utiliser les outils de migration de données fournis pour migrer des écritures journal.</span><span class="sxs-lookup"><span data-stu-id="7b275-112">We recommend that you use the data migration tools provided to migrate journal entries.</span></span> <span data-ttu-id="7b275-113">Sinon, si vous utilisez le traitement en lot pour créer des lignes journal, celui-ci a une portée limitée et ne génère que des champs par défaut dans un journal.</span><span class="sxs-lookup"><span data-stu-id="7b275-113">Otherwise, if you use a batch job to create journal lines, that has a limited scope and only generates pre-default fields into a journal.</span></span> <span data-ttu-id="7b275-114">Le reste du journal doit ensuite être renseigné manuellement.</span><span class="sxs-lookup"><span data-stu-id="7b275-114">The rest of the journal then has to be completed manually.</span></span>  

## <a name="migrating-transactions"></a><span data-ttu-id="7b275-115">Migration des transactions</span><span class="sxs-lookup"><span data-stu-id="7b275-115">Migrating transactions</span></span>  
<span data-ttu-id="7b275-116">Il est recommandé de migrer des soldes ouverts dans l'ordre suivant.</span><span class="sxs-lookup"><span data-stu-id="7b275-116">We recommend that you migrate opening balances in the following order.</span></span>  

1.  <span data-ttu-id="7b275-117">Migrez les soldes ouverts du grand livre sans utiliser la comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="7b275-117">Migrate general ledger opening balances without using the general ledger account subledgers.</span></span> <span data-ttu-id="7b275-118">Utilisez des comptes de compensation propres aux soldes ouverts, avec une configuration pour chaque comptabilité auxiliaire.</span><span class="sxs-lookup"><span data-stu-id="7b275-118">Use specific opening balance offsetting accounts, one set up for each subledger.</span></span> <span data-ttu-id="7b275-119">Configurez les comptes de compensation de manière à activer les imputations directes.</span><span class="sxs-lookup"><span data-stu-id="7b275-119">Set up the offsetting accounts to enable direct postings.</span></span>  
2.  <span data-ttu-id="7b275-120">Migration des écritures client ouvertes.</span><span class="sxs-lookup"><span data-stu-id="7b275-120">Migrate open customer ledger entries.</span></span>  
3.  <span data-ttu-id="7b275-121">Effectuez la migration des écritures du grand livre d'articles ouvertes.</span><span class="sxs-lookup"><span data-stu-id="7b275-121">Migrate open item ledger entries.</span></span>  
4.  <span data-ttu-id="7b275-122">Migrez les écritures comptables immobilisation ouvertes.</span><span class="sxs-lookup"><span data-stu-id="7b275-122">Migrate open fixed asset entries.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b275-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7b275-123">See Also</span></span>  
[<span data-ttu-id="7b275-124">Configuration d'une compagnie avec RapidStart Services</span><span class="sxs-lookup"><span data-stu-id="7b275-124">Setting Up a Company With RapidStart Services</span></span>](admin-set-up-a-company-with-rapidstart.md)  
[<span data-ttu-id="7b275-125">Administration</span><span class="sxs-lookup"><span data-stu-id="7b275-125">Administration</span></span>](admin-setup-and-administration.md)
