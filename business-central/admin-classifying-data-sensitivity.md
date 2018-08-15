---
title: "Classification de la sensibilité des données"
description: "Vous devez spécifier le type de données que vous stockez sur les personnes afin de pouvoir répondre aux demandes des sujets des données."
author: bholtorf
ms.author: bholtorf
ms.custom: na
ms.date: 03/09/2018
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 05d9630075ed533759f8225810e4e4a95c141b16
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---

# <a name="classifying-data-sensitivity"></a><span data-ttu-id="2b11b-103">Classification de la sensibilité des données</span><span class="sxs-lookup"><span data-stu-id="2b11b-103">Classifying Data Sensitivity</span></span>
<span data-ttu-id="2b11b-104">Pour classer les champs contenant des données sensibles ou personnelles, un partenaire Microsoft peut définir la propriété ```DataClassification``` des champs.</span><span class="sxs-lookup"><span data-stu-id="2b11b-104">To classify the fields that hold sensitive or personal data, a Microsoft partner can set the ```DataClassification``` property on fields.</span></span> <span data-ttu-id="2b11b-105">Cela nécessite un accès aux tables de base de données, par le biais de l'environnement de développement ou en exécutant un script Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b11b-105">This requires access to the database tables, either through the development environment or by running a Windows PowerShell script.</span></span> <span data-ttu-id="2b11b-106">Pour plus d'informations, voir [Classification des données](https://docs.microsoft.com/en-us/dynamics-nav/classifying-data).</span><span class="sxs-lookup"><span data-stu-id="2b11b-106">For more information, see [Classifying Data](https://docs.microsoft.com/en-us/dynamics-nav/classifying-data).</span></span>  

<span data-ttu-id="2b11b-107">En tant que client, vous pouvez ajouter un deuxième niveau de classification en spécifiant des niveaux de sensibilité pour les données que vous stockez dans les champs standard et personnalisés.</span><span class="sxs-lookup"><span data-stu-id="2b11b-107">As a customer, you can add a second level of classification by specifying sensitivity levels for the data you store in standard and custom fields.</span></span> <span data-ttu-id="2b11b-108">La classification de la sensibilité des données vous permet de savoir où vous conservez vos informations personnelles dans votre système, et de répondre facilement aux demandes des sujets des données.</span><span class="sxs-lookup"><span data-stu-id="2b11b-108">Classifying data sensitivity helps ensure that you know where you keep personal data in your system, and makes it easier to respond to requests from data subjects.</span></span> <span data-ttu-id="2b11b-109">Par exemple, si un contact ou un client vous demande d'exporter ses données personnelles.</span><span class="sxs-lookup"><span data-stu-id="2b11b-109">For example, if a contact or customer asks you to export their personal data.</span></span> <span data-ttu-id="2b11b-110">Pour plus d'informations, voir [Réponse aux demandes relatives aux données personnelles](admin-responding-to-requests-about-personal-data.md).</span><span class="sxs-lookup"><span data-stu-id="2b11b-110">For more information, see [Responding to Requests About Personal Data](admin-responding-to-requests-about-personal-data.md).</span></span>

> [!Important]
> <span data-ttu-id="2b11b-111">Microsoft fournit cette fonction de classification de la sensibilité des données pour votre convenance uniquement.</span><span class="sxs-lookup"><span data-stu-id="2b11b-111">Microsoft is providing this Data Sensitivity Classification feature as a matter of convenience only.</span></span> <span data-ttu-id="2b11b-112">Il vous incombe de classer les données de manière appropriée et de vous conformer aux lois et réglementations qui vous concernent.</span><span class="sxs-lookup"><span data-stu-id="2b11b-112">It's your responsibility to classify the data appropriately and comply with any laws and regulations that are applicable to you.</span></span> <span data-ttu-id="2b11b-113">Microsoft décline toute responsabilité en cas de réclamations liées à votre classification des données.</span><span class="sxs-lookup"><span data-stu-id="2b11b-113">Microsoft disclaims all responsibility towards any claims related to your classification of the data.</span></span>  

<span data-ttu-id="2b11b-114">Le tableau suivant décrit les niveaux de sensibilité des données que vous pouvez affecter.</span><span class="sxs-lookup"><span data-stu-id="2b11b-114">The following table describes data sensitivity levels you can assign.</span></span>

|<span data-ttu-id="2b11b-115">Sensibilité</span><span class="sxs-lookup"><span data-stu-id="2b11b-115">Sensitivity</span></span>|<span data-ttu-id="2b11b-116">Description</span><span class="sxs-lookup"><span data-stu-id="2b11b-116">Description</span></span>|
|----|----|
|<span data-ttu-id="2b11b-117">Sensible</span><span class="sxs-lookup"><span data-stu-id="2b11b-117">Sensitive</span></span> | <span data-ttu-id="2b11b-118">Informations sur l'origine raciale ou ethnique, les opinions politiques, les croyances religieuses, l'engagement syndical, la santé physique ou mentale, la sexualité d'un sujet des données, ou encore des détails sur les infractions criminelles.</span><span class="sxs-lookup"><span data-stu-id="2b11b-118">Information about a data subject's racial or ethnic origin, political opinions, religious beliefs, involvement with trade unions, physical or mental health, sexuality, or details about criminal offenses.</span></span> |
|<span data-ttu-id="2b11b-119">Personnel</span><span class="sxs-lookup"><span data-stu-id="2b11b-119">Personal</span></span> | <span data-ttu-id="2b11b-120">Informations permettant d'identifier un sujet des données, directement ou en combinaison avec d'autres données ou informations.</span><span class="sxs-lookup"><span data-stu-id="2b11b-120">Information that can be used to identify a data subject, either directly or in combination with other data or information.</span></span>|
|<span data-ttu-id="2b11b-121">Confidentiel</span><span class="sxs-lookup"><span data-stu-id="2b11b-121">Confidential</span></span> | <span data-ttu-id="2b11b-122">Données métier que vous utilisez à des fins comptables ou à d'autres fins commerciales et que vous ne souhaitez pas exposer à d'autres entités.</span><span class="sxs-lookup"><span data-stu-id="2b11b-122">Business data that you use for accounting or other business purposes, and do not want to expose to other entities.</span></span> <span data-ttu-id="2b11b-123">Cela peut inclure, par exemple, les écritures.</span><span class="sxs-lookup"><span data-stu-id="2b11b-123">For example, this might include ledger entries.</span></span>|
|<span data-ttu-id="2b11b-124">Normal </span><span class="sxs-lookup"><span data-stu-id="2b11b-124">Normal</span></span> | <span data-ttu-id="2b11b-125">Données générales qui n'appartiennent pas aux autres catégories.</span><span class="sxs-lookup"><span data-stu-id="2b11b-125">General data that does not belong to any other categories.</span></span>|

## <a name="how-do-i-classify-my-data"></a><span data-ttu-id="2b11b-126">Comment classer mes données ?</span><span class="sxs-lookup"><span data-stu-id="2b11b-126">How Do I Classify My Data?</span></span>
<span data-ttu-id="2b11b-127">Classer la sensibilité d'un grand nombre de champs un par un peut prendre beaucoup de temps.</span><span class="sxs-lookup"><span data-stu-id="2b11b-127">Classifying the sensitivity of a large number of fields one-by-one would take a long time.</span></span> <span data-ttu-id="2b11b-128">Pour aider à accélérer le processus, nous fournissons des outils qui permettent de classer en bloc la sensibilité des champs et d'affiner les classifications pour des champs spécifiques.</span><span class="sxs-lookup"><span data-stu-id="2b11b-128">To help speed up the process, we provide tools that you can use to bulk classify the sensitivity of fields, and then fine-tune classifications for specific fields.</span></span> <span data-ttu-id="2b11b-129">Vous trouverez les outils dans la feuille Classification des données, qui est disponible dans le tableau de bord Administration des utilisateurs, des groupes d'utilisateurs et des autorisations.</span><span class="sxs-lookup"><span data-stu-id="2b11b-129">You can find tools on the Data Classification worksheet, which is available on the Administration of users, user groups, and permissions Role Center.</span></span> <span data-ttu-id="2b11b-130">Vous devez être un administrateur système pour utiliser la feuille.</span><span class="sxs-lookup"><span data-stu-id="2b11b-130">You must be a system administrator to use the worksheet.</span></span>

> [!Important]
> <span data-ttu-id="2b11b-131">La feuille Classification des données est vide lorsque vous l'ouvrez pour la première fois.</span><span class="sxs-lookup"><span data-stu-id="2b11b-131">When you open the Data Classification worksheet for the first time, it will be empty.</span></span> <span data-ttu-id="2b11b-132">Vous devez exécuter le guide de classification des données pour générer la liste des champs.</span><span class="sxs-lookup"><span data-stu-id="2b11b-132">You must run the Data Classification guide to generate the list of fields.</span></span> <span data-ttu-id="2b11b-133">Pour démarrer le guide, choisissez l'action **Configuration des classifications de données**.</span><span class="sxs-lookup"><span data-stu-id="2b11b-133">To start the guide, choose the **Set Up Data Classifications** action.</span></span>

<span data-ttu-id="2b11b-134">Par exemple, la feuille Classification des données vous permet d'effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="2b11b-134">For example, the Data Classification worksheet lets you do things like:</span></span>  

* <span data-ttu-id="2b11b-135">Utilisez le guide de classification des données pour exporter les champs vers une feuille de calcul Excel dans laquelle vous pouvez les classer en bloc.</span><span class="sxs-lookup"><span data-stu-id="2b11b-135">Use the Data Classification guide to export your fields to an Excel worksheet where you can bulk classify them.</span></span> <span data-ttu-id="2b11b-136">L'utilisation de la feuille Excel est particulièrement utile si vous collaborez avec un partenaire Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2b11b-136">Using the Excel worksheet is particularly useful if you are collaborating with a Microsoft partner.</span></span> <span data-ttu-id="2b11b-137">Après avoir mis à jour la feuille, vous pouvez utiliser le guide pour importer et affecter les classifications.</span><span class="sxs-lookup"><span data-stu-id="2b11b-137">After you update the worksheet, you can use the guide to import and apply the classifications.</span></span> <span data-ttu-id="2b11b-138">Vous pouvez également utiliser le guide pour classer manuellement les champs.</span><span class="sxs-lookup"><span data-stu-id="2b11b-138">You can also use the guide to classify fields manually.</span></span>  
* <span data-ttu-id="2b11b-139">Choisissez un champ, puis filtrez la liste pour rechercher des champs similaires susceptibles d'appartenir à la même classification que le champ sur lequel est basée la recherche.</span><span class="sxs-lookup"><span data-stu-id="2b11b-139">Choose a field and then filter the list to find similar fields that are likely to belong to the same classification as the field you based the search on.</span></span>  
* <span data-ttu-id="2b11b-140">Examinez un champ en affichant son contenu.</span><span class="sxs-lookup"><span data-stu-id="2b11b-140">Investigate a field by viewing its contents.</span></span>  

> [!Tip]
> <span data-ttu-id="2b11b-141">Nous avons défini des exemples de classifications de la sensibilité pour les tables et les champs de la compagnie de démonstration Cronus.</span><span class="sxs-lookup"><span data-stu-id="2b11b-141">We have defined sample sensitivity classifications for the tables and fields in the Cronus demonstration company.</span></span> <span data-ttu-id="2b11b-142">Vous pouvez vous inspirer de ces classifications lorsque vous classez vos propres tables et champs.</span><span class="sxs-lookup"><span data-stu-id="2b11b-142">You can use those classifications as inspiration when you classify your own tables and fields.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b11b-143">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2b11b-143">See Also</span></span>
[<span data-ttu-id="2b11b-144">Classification des données</span><span class="sxs-lookup"><span data-stu-id="2b11b-144">Classifying Data</span></span>](https://docs.microsoft.com/en-us/dynamics-nav/classifying-data)  
