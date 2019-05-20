---
title: Exporter des données | Invoicing
description: Découvrez comment exporter des données, par exemple supprimer des contacts dans le cadre d'une demande de sujet de données.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 09/12/2018
ms.author: edupont
ms.openlocfilehash: 384791aeadaaa4c374607ec529955171456ab7e4
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1254069"
---
# <a name="export-or-delete-data-from-included365invlongincludesd365invlongmd"></a><span data-ttu-id="5ca78-103">Exporter ou supprimer des données de [!INCLUDE[d365inv_long](includes/d365inv_long.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca78-103">Export or delete data from [!INCLUDE[d365inv_long](includes/d365inv_long.md)]</span></span>

<span data-ttu-id="5ca78-104">Si vous voulez supprimer un contact ou un client de [!INCLUDE[d365inv](includes/d365inv.md)], il est facile de le faire.</span><span class="sxs-lookup"><span data-stu-id="5ca78-104">If you want to delete a contact or customer from [!INCLUDE[d365inv](includes/d365inv.md)], it's easy to do.</span></span>  

## <a name="to-delete-an-existing-customer"></a><span data-ttu-id="5ca78-105">Pour supprimer un client existant</span><span class="sxs-lookup"><span data-stu-id="5ca78-105">To delete an existing customer</span></span>

1. <span data-ttu-id="5ca78-106">Sur la page d'accueil, choisissez **Clients** pour ouvrir la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="5ca78-106">On your Home page, choose **Customers** to open the list of customers.</span></span>
2. <span data-ttu-id="5ca78-107">Recherchez le contact, puis choisissez le nom pour ouvrir les détails.</span><span class="sxs-lookup"><span data-stu-id="5ca78-107">Find the contact, and then choose the name to open the details.</span></span>
3. <span data-ttu-id="5ca78-108">Cliquez sur l'action **Supprimer**.</span><span class="sxs-lookup"><span data-stu-id="5ca78-108">Choose the **Delete** action.</span></span>

> [!NOTE]
> <span data-ttu-id="5ca78-109">Si vous lui avez déjà envoyé une facture, vous ne pouvez pas supprimer le client.</span><span class="sxs-lookup"><span data-stu-id="5ca78-109">If you have already sent them an invoice, you cannot delete the customer.</span></span> <span data-ttu-id="5ca78-110">À la place, [!INCLUDE[d365inv](includes/d365inv.md)] peut marquer le client comme bloqué pour toute activité ultérieure.</span><span class="sxs-lookup"><span data-stu-id="5ca78-110">Instead, [!INCLUDE[d365inv](includes/d365inv.md)] can mark the customer as blocked for further business.</span></span> <span data-ttu-id="5ca78-111">Cela signifie que vous ne pouvez pas lui envoyer de nouvelles factures, par exemple.</span><span class="sxs-lookup"><span data-stu-id="5ca78-111">That means that you cannot send them new invoices, for example.</span></span>  

<span data-ttu-id="5ca78-112">Si le contact n'a pas été ajouté comme client, vous pouvez l'ajouter en créant une facture provisoire.</span><span class="sxs-lookup"><span data-stu-id="5ca78-112">If the contact has not been added as a customer, you can add them by creating a draft invoice.</span></span>

## <a name="to-add-a-contact-as-a-customer-and-then-delete-the-customer"></a><span data-ttu-id="5ca78-113">Pour ajouter un contact comme client et supprimer le client</span><span class="sxs-lookup"><span data-stu-id="5ca78-113">To add a contact as a customer and then delete the customer</span></span>

1. <span data-ttu-id="5ca78-114">Sur la page Accueil, choisissez **Nouvelle facture**</span><span class="sxs-lookup"><span data-stu-id="5ca78-114">On your Home page, choose **New Invoice**</span></span>
2. <span data-ttu-id="5ca78-115">Dans le champ **Nom du client**, commencez à saisir le nom du contact.</span><span class="sxs-lookup"><span data-stu-id="5ca78-115">In the **Customer Name** field, start typing the contact’s name.</span></span>
3. <span data-ttu-id="5ca78-116">Sélectionnez votre contact dans la recherche, puis fermez la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="5ca78-116">Select your contact from the look-up, and then tab out.</span></span>
4. <span data-ttu-id="5ca78-117">Supprimez la facture provisoire qui vient d'être créée.</span><span class="sxs-lookup"><span data-stu-id="5ca78-117">Delete the draft invoice that was just created.</span></span>
5. <span data-ttu-id="5ca78-118">Suivez les étapes pour supprimer le client comme décrit ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="5ca78-118">Follow the steps for deleting the customer as described above.</span></span>

## <a name="responding-to-requests-about-personal-data"></a><span data-ttu-id="5ca78-119">Réponse aux demandes relatives aux données personnelles</span><span class="sxs-lookup"><span data-stu-id="5ca78-119">Responding to Requests About Personal Data</span></span>

<span data-ttu-id="5ca78-120">Les sujets des données peuvent demander plusieurs types d'actions concernant leurs données personnelles.</span><span class="sxs-lookup"><span data-stu-id="5ca78-120">Data subjects can request several types of actions regarding their personal data.</span></span> <span data-ttu-id="5ca78-121">Par exemple, en vertu du Règlement général sur la protection des données (RGPD), les résidents de l'UE ont le droit de demander l'exportation, la suppression et la modification de leurs données personnelles.</span><span class="sxs-lookup"><span data-stu-id="5ca78-121">For example, under the General Data Protection Regulation (GDPR), EU residents have the right to request the export, deletion, and modification of their personal data.</span></span> <span data-ttu-id="5ca78-122">Cela est appelé *Demande du sujet des données*.</span><span class="sxs-lookup"><span data-stu-id="5ca78-122">This is known as a *Data Subject Request*.</span></span>  

### <a name="requests-for-deletion"></a><span data-ttu-id="5ca78-123">Demandes de suppression</span><span class="sxs-lookup"><span data-stu-id="5ca78-123">Requests for deletion</span></span>

<span data-ttu-id="5ca78-124">Un sujet des données peut demander la suppression de ses données personnelles.</span><span class="sxs-lookup"><span data-stu-id="5ca78-124">A data subject can request that you delete their personal data.</span></span> <span data-ttu-id="5ca78-125">Si un contact ou un client vous demande de le supprimer dans le cadre d'une demande de sujet de données, vous pouvez suivre les étapes décrites ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="5ca78-125">If a contact or customer asks you to be deleted in the context of a data subject request, you can follow the steps that are outlined above.</span></span>  

### <a name="requests-for-exporting-privacy-data"></a><span data-ttu-id="5ca78-126">Demandes d'exportation des données de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5ca78-126">Requests for exporting privacy data</span></span>

<span data-ttu-id="5ca78-127">Un sujet des données peut faire une demande de portabilité des données, ce qui signifie que vous devez exporter les données personnelles du sujet des données à partir de vos systèmes et les fournir dans un format couramment utilisé et structuré.</span><span class="sxs-lookup"><span data-stu-id="5ca78-127">A data subject can make a data portability request, meaning, in part, that you must export the data subject's personal data from your systems and provide it in in a structured, commonly used format.</span></span>  <span data-ttu-id="5ca78-128">Si un contact ou un client vous demande de lui envoyer ses informations à partir de [!INCLUDE[d365inv](includes/d365inv.md)], vous pouvez vous envoyer ses informations de contact par courriel.</span><span class="sxs-lookup"><span data-stu-id="5ca78-128">If a contact or customer asks you to send them their information from [!INCLUDE[d365inv](includes/d365inv.md)], you can email yourself their contact information.</span></span>  

#### <a name="to-export-privacy-data"></a><span data-ttu-id="5ca78-129">Pour exporter les données de confidentialité</span><span class="sxs-lookup"><span data-stu-id="5ca78-129">To export privacy data</span></span>

1. <span data-ttu-id="5ca78-130">Sur la page d'accueil, choisissez **Clients** pour ouvrir la liste des clients.</span><span class="sxs-lookup"><span data-stu-id="5ca78-130">On your Home page, choose **Customers** to open the list of customers.</span></span>
2. <span data-ttu-id="5ca78-131">Recherchez le contact approprié, puis choisissez le nom pour ouvrir les détails.</span><span class="sxs-lookup"><span data-stu-id="5ca78-131">Find the relevant customer, and then choose the name to open the details.</span></span>
3. <span data-ttu-id="5ca78-132">Développez l'onglet **Confidentialité**, puis choisissez **Exporter les données de confidentialité du client**.</span><span class="sxs-lookup"><span data-stu-id="5ca78-132">Expand the **Privacy** tab, and then choose **Export customer privacy data**.</span></span>
4. <span data-ttu-id="5ca78-133">Dans la page **Exporter les données du client**, vérifiez que vous êtes sur le point d'envoyer le courriel à vous-même, puis cliquez sur le bouton OK.</span><span class="sxs-lookup"><span data-stu-id="5ca78-133">In the **Export customer data** page, verify that you are about to send the email to yourself, and then choose the OK button.</span></span>

<span data-ttu-id="5ca78-134">Le courriel que vous recevez contient un classeur Excel avec des informations sur le client, notamment les factures que vous lui avez envoyées.</span><span class="sxs-lookup"><span data-stu-id="5ca78-134">The email that you receive includes an Excel book with information about the customer, including invoices that you have sent them.</span></span> <span data-ttu-id="5ca78-135">Selon la demande d'origine, vous pouvez choisir de supprimer une partie des informations avant de transférer le courriel au client.</span><span class="sxs-lookup"><span data-stu-id="5ca78-135">Depending on the original request, you can choose to delete part of the information before you forward the email to the customer.</span></span>  

### <a name="requests-for-correction"></a><span data-ttu-id="5ca78-136">Demandes de correction</span><span class="sxs-lookup"><span data-stu-id="5ca78-136">Requests for correction</span></span>

<span data-ttu-id="5ca78-137">Un sujet des données peut demander la correction des données personnelles incorrectes.</span><span class="sxs-lookup"><span data-stu-id="5ca78-137">A data subject can request that you correct inaccurate personal data.</span></span> <span data-ttu-id="5ca78-138">Si un contact ou un client vous demande de mettre à jour les informations le concernant dans [!INCLUDE[d365inv](includes/d365inv.md)], vous pouvez le faire dans les détails du client.</span><span class="sxs-lookup"><span data-stu-id="5ca78-138">If a contact or customer asks you to update the information about them in [!INCLUDE[d365inv](includes/d365inv.md)], you can do that in the customer details.</span></span>  

## <a name="see-also"></a><span data-ttu-id="5ca78-139">Voir aussi .</span><span class="sxs-lookup"><span data-stu-id="5ca78-139">See also</span></span>

[<span data-ttu-id="5ca78-140">Configurer les informations sur votre entreprise</span><span class="sxs-lookup"><span data-stu-id="5ca78-140">Set up your business information</span></span>](set-up-business-profile.md)  
[<span data-ttu-id="5ca78-141">Envoyer une facture à un nouveau client</span><span class="sxs-lookup"><span data-stu-id="5ca78-141">Send an invoice to a new customer</span></span>](send-invoice.md)  
[<span data-ttu-id="5ca78-142">Dépannage</span><span class="sxs-lookup"><span data-stu-id="5ca78-142">Troubleshooting</span></span>](about-troubleshooting.md)  
