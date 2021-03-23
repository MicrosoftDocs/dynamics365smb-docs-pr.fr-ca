---
title: Configurer les documents entrants| Microsoft Docs
description: Utilisez la fonctionnalité Documents entrants pour créer des documents électroniques, gérer des tâches OCR, importer des factures, et convertir des fichiers images.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 00bfa89376a361bedc71ba76630906d761989ead
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5384609"
---
# <a name="set-up-incoming-documents"></a><span data-ttu-id="afd85-103">Configurer des documents entrants</span><span class="sxs-lookup"><span data-stu-id="afd85-103">Set Up Incoming Documents</span></span>

<span data-ttu-id="afd85-104">Si vous créez des lignes journal général à partir des enregistrements de documents entrants, vous devez spécifier sur la page **Configuration des documents entrants** quels modèle et lot de journal utiliser.</span><span class="sxs-lookup"><span data-stu-id="afd85-104">If you create general journal lines from incoming document records, you must specify on the **Incoming Documents Setup** page which journal template and batch to use.</span></span>

<span data-ttu-id="afd85-105">Si vous ne souhaitez pas que les utilisateurs créent des factures ou des lignes journal général à partir d'enregistrements document entrant, sauf si les documents ont été préalablement approuvés, vous devez configurer des approbateurs de flux de travail.</span><span class="sxs-lookup"><span data-stu-id="afd85-105">If you do not want users to create invoices or general journal lines from incoming document records unless the documents are first approved, you must set up workflow approvers.</span></span>

<span data-ttu-id="afd85-106">Pour convertir les fichiers PDF et image en documents électroniques que vous pouvez convertir, par exemple, en factures achat dans [!INCLUDE[prod_short](includes/prod_short.md)], vous devez d'abord configurer la fonctionnalité OCR et activer le service.</span><span class="sxs-lookup"><span data-stu-id="afd85-106">To turn PDF and image files into electronic documents that you can convert to, for example, purchase invoices inside [!INCLUDE[prod_short](includes/prod_short.md)], you must first set up the OCR feature and enable the service.</span></span> <span data-ttu-id="afd85-107">Choisissez un package de services adapté à votre organisation et/ou votre pays/région.</span><span class="sxs-lookup"><span data-stu-id="afd85-107">Choose a service package that is appropriate for your organization and/or country/region.</span></span> <span data-ttu-id="afd85-108">Vous pouvez également créer des écritures manuellement pour représenter les documents externes.</span><span class="sxs-lookup"><span data-stu-id="afd85-108">Alternatively, you can create entries manually to represent the external documents.</span></span>  

<span data-ttu-id="afd85-109">Une fois que la fonctionnalité Documents entrants est configurée, vous pouvez utiliser différentes fonctions pour examiner les reçus de dépenses, gérer les tâches OCR et convertir les fichiers document entrant, manuellement ou automatiquement, en documents ou lignes journal appropriés.</span><span class="sxs-lookup"><span data-stu-id="afd85-109">When the Incoming Documents feature is set up, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines.</span></span> <span data-ttu-id="afd85-110">Les fichiers externes peuvent être joints à n'importe quelle étape du processus, notamment en ce qui concerne les documents reportés et les écritures fournisseur, client et grand livre résultantes.</span><span class="sxs-lookup"><span data-stu-id="afd85-110">The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.</span></span> <span data-ttu-id="afd85-111">Pour plus d'informations, voir la section [Traitement des documents entrants](across-process-income-documents.md).</span><span class="sxs-lookup"><span data-stu-id="afd85-111">For more information, see [Processing Incoming Documents](across-process-income-documents.md).</span></span>

## <a name="to-set-up-the-incoming-documents-feature"></a><span data-ttu-id="afd85-112">Configurer la fonctionnalité Documents entrants</span><span class="sxs-lookup"><span data-stu-id="afd85-112">To set up the Incoming Documents feature</span></span>

1. <span data-ttu-id="afd85-113">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration des documents entrants**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="afd85-113">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Document Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="afd85-114">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="afd85-114">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

<span data-ttu-id="afd85-115">Dans le cadre de la configuration, vous devez décider si vous souhaitez exiger l'approbation des documents entrants.</span><span class="sxs-lookup"><span data-stu-id="afd85-115">As part of the setup, you must decide if you want to require approval of incoming documents.</span></span> <span data-ttu-id="afd85-116">Pour demander une approbation, vous devez configurer des approbateurs et des flux de travail approbation.</span><span class="sxs-lookup"><span data-stu-id="afd85-116">To require approval, you must set up approvers and approval workflows.</span></span> <span data-ttu-id="afd85-117">Si votre organisation n'a pas l'intention d'exiger l'approbation, vous pouvez ignorer la section suivante.</span><span class="sxs-lookup"><span data-stu-id="afd85-117">If your organization does not intend to require approval, you can skip the next section.</span></span>  

<span data-ttu-id="afd85-118">Enfin, si vous utilisez un service pour convertir des fichiers PDF ou image représentant des documents entrants, vous devez le configurer.</span><span class="sxs-lookup"><span data-stu-id="afd85-118">Finally, you if you use a service to convert PDF or image files representing incoming documents, you must it set up.</span></span> <span data-ttu-id="afd85-119">Sinon, vous pouvez également ignorer cette section.</span><span class="sxs-lookup"><span data-stu-id="afd85-119">Otherwise, you can also skip that section.</span></span>  

## <a name="to-set-up-approvers-of-incoming-document-records"></a><span data-ttu-id="afd85-120">Configurer des approbateurs d'enregistrements document entrant</span><span class="sxs-lookup"><span data-stu-id="afd85-120">To set up approvers of incoming document records</span></span>

<span data-ttu-id="afd85-121">Vous pouvez éventuellement configurer un processus d'approbation pour les documents entrants.</span><span class="sxs-lookup"><span data-stu-id="afd85-121">Optionally, set up an approval process for the incoming documents.</span></span> <span data-ttu-id="afd85-122">Les approbateurs de documents entrants doivent être paramétrés comme des utilisateurs de flux de travail approbation.</span><span class="sxs-lookup"><span data-stu-id="afd85-122">Approvers of incoming documents must be set up as approval workflow users.</span></span>

<span data-ttu-id="afd85-123">Avant de pouvoir créer des workflows qui impliquent des étapes d'approbation, vous devez configurer les utilisateurs du workflow qui sont impliqués dans les processus d'approbation.</span><span class="sxs-lookup"><span data-stu-id="afd85-123">Before you can create workflows that involve approval steps, you must set up the workflow users who are involved in approval processes.</span></span> <span data-ttu-id="afd85-124">Sur la page **Configuration d'utilisateur d'approbation**, vous pouvez également définir les limites pour des types spécifiques de demandes et définir des approbateurs remplaçants à qui des demandes d'approbation sont déléguées lorsque l'approbateur initial est absent.</span><span class="sxs-lookup"><span data-stu-id="afd85-124">On the **Approval User Setup** page, you also set amount limits for specific types of requests and define substitute approvers to whom approval requests are delegated when the original approver is absent.</span></span> <span data-ttu-id="afd85-125">Pour plus d'informations, voir [Configurer des utilisateurs d'approbation](across-how-to-set-up-approval-users.md).</span><span class="sxs-lookup"><span data-stu-id="afd85-125">For more information, see [Set Up Approval Users](across-how-to-set-up-approval-users.md).</span></span>

## <a name="to-set-up-an-ocr-service"></a><span data-ttu-id="afd85-126">Configurer un service ROC</span><span class="sxs-lookup"><span data-stu-id="afd85-126">To set up an OCR service</span></span>

1. <span data-ttu-id="afd85-127">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration service OCR**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="afd85-127">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **OCR Service Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="afd85-128">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="afd85-128">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> <span data-ttu-id="afd85-129">Vos données d'ouverture de session sont automatiquement chiffrées.</span><span class="sxs-lookup"><span data-stu-id="afd85-129">You login data is automatically encrypted.</span></span>

<span data-ttu-id="afd85-130">Pour en savoir plus, voir [Utiliser un service OCR pour convertir des fichiers PDF et image en documents électroniques](across-how-use-ocr-pdf-images-files.md).</span><span class="sxs-lookup"><span data-stu-id="afd85-130">For more information, see [Use OCR to Turn PDF and Image Files into Electronic Documents](across-how-use-ocr-pdf-images-files.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="afd85-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="afd85-131">See Also</span></span>

[<span data-ttu-id="afd85-132">Traiter les documents entrants</span><span class="sxs-lookup"><span data-stu-id="afd85-132">Process Incoming Documents</span></span>](across-process-income-documents.md)  
[<span data-ttu-id="afd85-133">Documents entrants</span><span class="sxs-lookup"><span data-stu-id="afd85-133">Incoming Documents</span></span>](across-income-documents.md)  
[<span data-ttu-id="afd85-134">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="afd85-134">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="afd85-135">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="afd85-135">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]