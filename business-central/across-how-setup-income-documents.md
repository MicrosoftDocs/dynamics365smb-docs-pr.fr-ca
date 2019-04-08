---
title: Configurer les documents entrants| Microsoft Docs
description: Utilisez la fonctionnalité Documents entrants pour créer des documents électroniques, gérer des tâches OCR, importer des factures, et convertir des fichiers images.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 6072dcf536211ddad76c6423421033dd43f534b0
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "812938"
---
# <a name="set-up-incoming-documents"></a><span data-ttu-id="90adc-103">Configurer des documents entrants</span><span class="sxs-lookup"><span data-stu-id="90adc-103">Set Up Incoming Documents</span></span>
<span data-ttu-id="90adc-104">Si vous créez des lignes journal général à partir des enregistrements de documents entrants, vous devez spécifier sur la page **Configuration des documents entrants** quels modèle et lot de journal utiliser.</span><span class="sxs-lookup"><span data-stu-id="90adc-104">If you create general journal lines from incoming document records, you must specify on the **Incoming Documents Setup** page which journal template and batch to use.</span></span>

<span data-ttu-id="90adc-105">Si vous ne souhaitez pas que les utilisateurs créent des factures ou des lignes journal général à partir d'enregistrements de documents entrants, sauf si les documents ont été préalablement approuvés, vous devez configurer des approbateurs sur la page **Approbateurs de document entrant**.</span><span class="sxs-lookup"><span data-stu-id="90adc-105">If you do not want users to create invoices or general journal lines from incoming document records unless the documents are first approved, you must set up approvers on the **Incoming Document Approvers** page.</span></span>

<span data-ttu-id="90adc-106">Pour convertir les fichiers PDF et image en documents électroniques que vous pouvez convertir, par exemple, en factures achat dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez d'abord configurer la fonctionnalité OCR et activer le service.</span><span class="sxs-lookup"><span data-stu-id="90adc-106">To turn PDF and image files into electronic documents that you can convert to, for example, purchase invoices inside [!INCLUDE[d365fin](includes/d365fin_md.md)], you must first set up the OCR feature and enable the service.</span></span>

<span data-ttu-id="90adc-107">Une fois que la fonctionnalité Documents entrants est configurée, vous pouvez utiliser différentes fonctions pour examiner les reçus de dépenses, gérer les tâches OCR et convertir les fichiers document entrant, manuellement ou automatiquement, en documents ou lignes journal appropriés.</span><span class="sxs-lookup"><span data-stu-id="90adc-107">When the Incoming Documents feature is set up, you can use different functions to review expense receipts, manage OCR tasks, and convert incoming document files, manually or automatically, to the relevant documents or journal lines.</span></span> <span data-ttu-id="90adc-108">Les fichiers externes peuvent être joints à n'importe quelle étape du processus, notamment en ce qui concerne les documents reportés et les écritures fournisseur, client et grand livre résultantes.</span><span class="sxs-lookup"><span data-stu-id="90adc-108">The external files can be attached at any process stage, including to posted documents and to the resulting vendor, customer, and general ledger entries.</span></span> <span data-ttu-id="90adc-109">Pour plus d'informations, voir la section [Traitement des documents entrants](across-process-income-documents.md).</span><span class="sxs-lookup"><span data-stu-id="90adc-109">For more information, see [Processing Incoming Documents](across-process-income-documents.md).</span></span>

## <a name="to-set-up-the-incoming-documents-feature"></a><span data-ttu-id="90adc-110">Configurer la fonctionnalité Documents entrants</span><span class="sxs-lookup"><span data-stu-id="90adc-110">To set up the Incoming Documents feature</span></span>
1. <span data-ttu-id="90adc-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration document entrant**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="90adc-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Document Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="90adc-112">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="90adc-112">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-approvers-of-incoming-document-records"></a><span data-ttu-id="90adc-113">Configurer des approbateurs d'enregistrements document entrant</span><span class="sxs-lookup"><span data-stu-id="90adc-113">To set up approvers of incoming document records</span></span>
1. <span data-ttu-id="90adc-114">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration document entrant**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="90adc-114">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Incoming Document Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="90adc-115">Sur la page **Configuration des documents entrants**, sélectionnez l'action **Approbateurs**.</span><span class="sxs-lookup"><span data-stu-id="90adc-115">On the **Incoming Documents Setup** page, choose the **Approvers** action.</span></span>

    <span data-ttu-id="90adc-116">La page **Approbateurs de document entrant** affiche tous les utilisateurs configurés dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="90adc-116">The **Incoming Document Approvers** page shows all users that are set up in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>  
3. <span data-ttu-id="90adc-117">Sélectionnez un ou plusieurs utilisateurs pouvant approuver un document entrant avant de pouvoir créer un document ou une ligne journal correspondante.</span><span class="sxs-lookup"><span data-stu-id="90adc-117">Select one or more users that can approve an incoming document before a related document or journal line can be created.</span></span>

<span data-ttu-id="90adc-118">Lorsque des approbateurs ont été configurés sur la page **Approbateurs de document entrant**, seuls ces utilisateurs peuvent approuver un document entrant si la case **Exiger une approbation pour créer** est cochée sur la page **Configuration des documents entrants**.</span><span class="sxs-lookup"><span data-stu-id="90adc-118">When approvers have been set up on the **Incoming Document Approvers** page, only those users can approve an incoming document if the **Require Approval To Create** check box on the **Incoming Documents Setup** page is selected.</span></span>

> [!NOTE]  
>   <span data-ttu-id="90adc-119">Cette configuration d'approbation n'est pas liée aux flux d'approbation.</span><span class="sxs-lookup"><span data-stu-id="90adc-119">This approval setup is not related to approval workflows.</span></span> <span data-ttu-id="90adc-120">Pour plus d'informations, reportez-vous à [Utilisation des flux d'approbation](across-how-use-approval-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="90adc-120">For more information, see [Use Approval Workflows](across-how-use-approval-workflows.md).</span></span>

## <a name="to-set-up-an-ocr-service"></a><span data-ttu-id="90adc-121">Configurer un service ROC</span><span class="sxs-lookup"><span data-stu-id="90adc-121">To set up an OCR service</span></span>
1. <span data-ttu-id="90adc-122">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration du service OCR**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="90adc-122">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **OCR Service Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="90adc-123">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="90adc-123">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> <span data-ttu-id="90adc-124">Vos données d'ouverture de session sont automatiquement chiffrées.</span><span class="sxs-lookup"><span data-stu-id="90adc-124">You login data is automatically encrypted.</span></span>

## <a name="see-also"></a><span data-ttu-id="90adc-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90adc-125">See Also</span></span>
[<span data-ttu-id="90adc-126">Traiter les documents entrants</span><span class="sxs-lookup"><span data-stu-id="90adc-126">Process Incoming Documents</span></span>](across-process-income-documents.md)  
[<span data-ttu-id="90adc-127">Documents entrants</span><span class="sxs-lookup"><span data-stu-id="90adc-127">Incoming Documents</span></span>](across-income-documents.md)  
[<span data-ttu-id="90adc-128">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="90adc-128">Purchasing</span></span>](purchasing-manage-purchasing.md)  
<span data-ttu-id="90adc-129">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="90adc-129">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
