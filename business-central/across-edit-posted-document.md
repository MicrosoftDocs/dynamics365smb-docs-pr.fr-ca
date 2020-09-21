---
title: Modifier les documents vente et achat reportés | Microsoft Docs
description: En savoir plus sur les différentes fonctions de report pour reporter des documents achat et la manière de mettre à jour les documents reportés.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 07/21/2020
ms.author: edupont
ms.openlocfilehash: 867fddce799fb7e005a5a34a4c22975336375801
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3780745"
---
# <a name="edit-posted-documents"></a><span data-ttu-id="1c6cd-103">Modifier les documents reportés</span><span class="sxs-lookup"><span data-stu-id="1c6cd-103">Edit Posted Documents</span></span>

<span data-ttu-id="1c6cd-104">Parfois, vous devez mettre à jour un document reporté, car les informations pertinentes pour le document ont été modifiées.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-104">Sometimes you have to update a posted document because information that is relevant to the document has changed.</span></span> <span data-ttu-id="1c6cd-105">Sur un document vente reporté, il peut s'agir du numéro de suivi du colis du de l'agent de livraison, par exemple.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-105">On a posted sales document, this can be the shipping agent's package tracking number, for example.</span></span> <span data-ttu-id="1c6cd-106">Sur un document achat reporté, il peut s'agir d'un texte de référence de paiement.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-106">On a posted purchase document, this can be a payment reference text.</span></span>

<span data-ttu-id="1c6cd-107">Vous effectuez la modification sur une version modifiable du document d'origine, indiquée par «  **- Mettre à jour** » dans le titre de la page.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-107">You perform the change on an editable version of the original document, indicated by "**- Update**" in the page title.</span></span> <span data-ttu-id="1c6cd-108">La page contient un sous-ensemble des champs sur le document d'origine, dont certains sont des champs non modifiables affichés uniquement à titre d'information.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-108">The page contains a subset of the fields on the original document, of which some are non-editable fields that are shown for information only.</span></span>

<span data-ttu-id="1c6cd-109">La fonctionnalité est disponible pour les documents suivants dans tous les marchés pris en charge :</span><span class="sxs-lookup"><span data-stu-id="1c6cd-109">The functionality is available for the following documents across all supported markets:</span></span>

- <span data-ttu-id="1c6cd-110">Livraison vente reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-110">Posted Sales Shipment</span></span>
- <span data-ttu-id="1c6cd-111">Facture achat reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-111">Posted Purchase Invoice</span></span>
- <span data-ttu-id="1c6cd-112">Livraison de retour reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-112">Posted Return Shipment</span></span>
- <span data-ttu-id="1c6cd-113">Réception retour reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-113">Posted Return Receipt</span></span>

<span data-ttu-id="1c6cd-114">Les documents supplémentaires suivants peuvent être modifiés dans les pays ou régions spécifiés :</span><span class="sxs-lookup"><span data-stu-id="1c6cd-114">The following additional documents can be edited in the specified countries or regions:</span></span>

- <span data-ttu-id="1c6cd-115">ES : facture vente reportée, note de crédit vente reportée, note de crédit achat reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-115">ES: Posted Sales Invoice, Posted Sales Credit Memo, Posted Purchase Credit Memo</span></span>
- <span data-ttu-id="1c6cd-116">APAC : note de crédit vente reportée, note de crédit achat reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-116">APAC: Posted Sales Credit Memo, Posted Purchase Credit Memo</span></span>
- <span data-ttu-id="1c6cd-117">RU : note de crédit vente reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-117">RU: Posted Sales Credit Memo</span></span>
- <span data-ttu-id="1c6cd-118">IT : livraison de transfert reportée, livraison de service reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-118">IT: Posted Transfer Shipment, Posted Service Shipment</span></span>

## <a name="to-edit-a-posted-sales-shipment"></a><span data-ttu-id="1c6cd-119">Pour modifier une livraison vente reportée</span><span class="sxs-lookup"><span data-stu-id="1c6cd-119">To edit a posted sales shipment</span></span>

<span data-ttu-id="1c6cd-120">Voici comment modifier une livraison vente reportée.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-120">The following explains how to edit a posted sales shipment.</span></span> <span data-ttu-id="1c6cd-121">Les étapes sont similaires pour les autres documents pris en charge.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-121">The steps are similar for the other supported documents.</span></span>

1. <span data-ttu-id="1c6cd-122">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons vente reportées**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-122">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Posted Sales Shipments**, and then choose the related link.</span></span>
2. <span data-ttu-id="1c6cd-123">Sélectionnez le document que vous souhaitez modifier, puis sélectionnez l'action **Mettre à jour le document**.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-123">Select the document that you want to edit, and then choose the **Update Document** action.</span></span> <span data-ttu-id="1c6cd-124">Sinon, ouvrez le document, puis choisissez l'action.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-124">Alternatively, open the document and then choose the action.</span></span>
3. <span data-ttu-id="1c6cd-125">Sur la page **Livraison vente reportée - Mettre à jour**, modifiez le champ **N° de suivi du colis**</span><span class="sxs-lookup"><span data-stu-id="1c6cd-125">On the **Posted Sales Shipment - Update** page, edit the **Package Tracking No.**</span></span> <span data-ttu-id="1c6cd-126">par exemple.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-126">field, for example.</span></span>
4. <span data-ttu-id="1c6cd-127">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-127">Choose the **OK** button.</span></span>

<span data-ttu-id="1c6cd-128">La livraison vente reportée est mise à jour.</span><span class="sxs-lookup"><span data-stu-id="1c6cd-128">The posted sales shipment is updated.</span></span>

## <a name="see-also"></a><span data-ttu-id="1c6cd-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1c6cd-129">See Also</span></span>

[<span data-ttu-id="1c6cd-130">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="1c6cd-130">General Business Functionality</span></span>](ui-across-business-areas.md)  
[<span data-ttu-id="1c6cd-131">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="1c6cd-131">Purchasing</span></span>](purchasing-manage-purchasing.md)  
[<span data-ttu-id="1c6cd-132">Validation des documents et des feuilles</span><span class="sxs-lookup"><span data-stu-id="1c6cd-132">Posting Documents and Journals</span></span>](ui-post-documents-journals.md)  
<span data-ttu-id="1c6cd-133">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="1c6cd-133">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
