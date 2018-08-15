---
title: Effectuer le suivi des segments et des interactions correspondantes| Microsoft Docs
description: "En savoir plus sur la création de segments pour définir des groupes de contacts et spécifier des interactions pour des segments."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 06/06/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: e3917573a912a4e51416c4e926443c87513728fe
ms.openlocfilehash: 1962bd9d74f7b4d9600de11f85d1e312f6fb8c09
ms.contentlocale: fr-ca
ms.lasthandoff: 06/01/2018

---
# <a name="managing-interactions-for-segments"></a><span data-ttu-id="3a741-103">Gestion des interactions pour des segments</span><span class="sxs-lookup"><span data-stu-id="3a741-103">Managing Interactions for Segments</span></span>
<span data-ttu-id="3a741-104">La fenêtre **Segment** est un type de feuille activité dans laquelle vous pouvez effectuer les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="3a741-104">The **Segment** window is a type of worksheet where you can:</span></span>

* <span data-ttu-id="3a741-105">Création de segments</span><span class="sxs-lookup"><span data-stu-id="3a741-105">Create segments.</span></span>
* <span data-ttu-id="3a741-106">Enregistrement des critères de segmentation utilisés pour sélectionner des contacts.</span><span class="sxs-lookup"><span data-stu-id="3a741-106">Save the segmentation criteria you have used to select contacts.</span></span>
* <span data-ttu-id="3a741-107">Journalisation du segment et enregistrement des interactions impliquant les contacts du segment.</span><span class="sxs-lookup"><span data-stu-id="3a741-107">Log the segment and record interactions involving the contacts within the segment.</span></span>

## <a name="segmenting"></a><span data-ttu-id="3a741-108">Segmentation</span><span class="sxs-lookup"><span data-stu-id="3a741-108">Segmenting</span></span>
<span data-ttu-id="3a741-109">Il existe plusieurs méthodes de création de segments :</span><span class="sxs-lookup"><span data-stu-id="3a741-109">There are several ways to create segments:</span></span>

* <span data-ttu-id="3a741-110">Sur les lignes segment, vous pouvez saisir manuellement les contacts à inclure dans le segment.</span><span class="sxs-lookup"><span data-stu-id="3a741-110">You can manually enter the contacts you want to include in the segment in the segment lines.</span></span>
* <span data-ttu-id="3a741-111">Vous pouvez sélectionner des contacts.</span><span class="sxs-lookup"><span data-stu-id="3a741-111">You can select contacts.</span></span>
* <span data-ttu-id="3a741-112">Vous pouvez réutiliser un segment journalisé sur la base duquel vous créerez un nouveau segment.</span><span class="sxs-lookup"><span data-stu-id="3a741-112">You can reuse a logged segment as the basis to create a new one.</span></span>
* <span data-ttu-id="3a741-113">Vous pouvez réutiliser des critères de segmentation enregistrés.</span><span class="sxs-lookup"><span data-stu-id="3a741-113">You can reuse saved segmentation criteria.</span></span>

## <a name="interactions"></a><span data-ttu-id="3a741-114">Interactions</span><span class="sxs-lookup"><span data-stu-id="3a741-114">Interactions</span></span>
<span data-ttu-id="3a741-115">Dans la fenêtre **Segment**, vous pouvez créer simultanément des interactions pour plusieurs contacts.</span><span class="sxs-lookup"><span data-stu-id="3a741-115">In the **Segment** window, you can create interactions for several contacts simultaneously.</span></span> <span data-ttu-id="3a741-116">Par exemple, vous pouvez fusionner un segment avec un document Microsoft Word de manière à envoyer une lettre à tous les contacts inclus dans le segment.</span><span class="sxs-lookup"><span data-stu-id="3a741-116">For example, you can merge a segment with a Microsoft Word document, so that you can send a letter to all the contacts in the segment.</span></span>

<span data-ttu-id="3a741-117">Vous pouvez définir des données sur l'interaction pour le segment qui apparaît dans l'en-tête **Segment**.</span><span class="sxs-lookup"><span data-stu-id="3a741-117">You can specify information about the interaction for the segment on the **Segment** header.</span></span> <span data-ttu-id="3a741-118">Par exemple, vous pouvez choisir le modèle interaction à utiliser pour tous les contacts, saisir une description, définir un type correspondance, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="3a741-118">For example, you can decide which interaction template you want to use for all the contacts, specify a description, a correspondence type, and so on.</span></span> <span data-ttu-id="3a741-119">Vous pouvez cependant modifier ces données dans la ligne segment de chaque contact, par exemple en saisissant une description différente pour un contact.</span><span class="sxs-lookup"><span data-stu-id="3a741-119">However, you can modify this information in the segment line for each particular contact, for example, by specifying another description for one contact.</span></span> <span data-ttu-id="3a741-120">Si vous fusionnez un segment avec un document Microsoft Word, vous pouvez personnaliser le document à envoyer à un ou à plusieurs contacts inclus dans le segment, par exemple en ajoutant au document des commentaires spécifiques.</span><span class="sxs-lookup"><span data-stu-id="3a741-120">If you are merging a segment with a Microsoft Word document, you can personalize the document to be sent for one or several of the contacts within the segment, for example, by adding individualized comments to the document.</span></span>

## <a name="logging"></a><span data-ttu-id="3a741-121">Journalisation</span><span class="sxs-lookup"><span data-stu-id="3a741-121">Logging</span></span>
<span data-ttu-id="3a741-122">Dans la fenêtre **Segment**, lorsque vous cliquez sur **Journaliser**, l'application enregistre les interactions dans la fenêtre **Ecriture journal interaction** et journalise le segment.</span><span class="sxs-lookup"><span data-stu-id="3a741-122">In the **Segment** window, when you choose **Log**, the application records the interactions in the **Interaction Log Entry** window, and logs the segment.</span></span> <span data-ttu-id="3a741-123">Une fois le segment journalisé, il n'apparaît plus que dans la fenêtre **Segments journalisés**.</span><span class="sxs-lookup"><span data-stu-id="3a741-123">After you have logged the segment, you can only find it in the **Logged Segments** window.</span></span>

<span data-ttu-id="3a741-124">Dans la fenêtre **Segments journalisés**, vous pouvez choisir de créer un suivi segment contenant les mêmes contacts que le segment que vous avez journalisé.</span><span class="sxs-lookup"><span data-stu-id="3a741-124">In the **Logged Segments** window, you can decide to create a follow-up segment containing the same contacts as the segment you have logged.</span></span>

## <a name="see-also"></a><span data-ttu-id="3a741-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3a741-125">See Also</span></span>
[<span data-ttu-id="3a741-126">Création de segments</span><span class="sxs-lookup"><span data-stu-id="3a741-126">Create Segments</span></span>](marketing-how-create-segment.md)  
[<span data-ttu-id="3a741-127">Créer des interactions pour des segments</span><span class="sxs-lookup"><span data-stu-id="3a741-127">Create Interactions for Segments</span></span>](marketing-how-create-interactions.md)  
[<span data-ttu-id="3a741-128">Gestion des segments</span><span class="sxs-lookup"><span data-stu-id="3a741-128">Managing Segments</span></span>](marketing-segments.md)  
[<span data-ttu-id="3a741-129">Enregistrement des interactions avec les contacts</span><span class="sxs-lookup"><span data-stu-id="3a741-129">Recording Interactions With Contacts</span></span>](marketing-interactions.md)  
[<span data-ttu-id="3a741-130">Gestion des opportunités de ventes</span><span class="sxs-lookup"><span data-stu-id="3a741-130">Managing Sales Opportunities</span></span>](marketing-manage-sales-opportunities.md)  
[<span data-ttu-id="3a741-131">Création et gestion des contacts</span><span class="sxs-lookup"><span data-stu-id="3a741-131">Creating and Managing Contacts</span></span>](marketing-contacts.md)  
[<span data-ttu-id="3a741-132">Utilisation de Business Central</span><span class="sxs-lookup"><span data-stu-id="3a741-132">Working with Business Central</span></span>](ui-work-product.md)
