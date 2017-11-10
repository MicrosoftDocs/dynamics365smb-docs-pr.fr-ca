---
title: "Créer des compagnies contact| Microsoft Docs"
description: "Décrit comment créer un contact pour chaque nouvelle compagnie ou compagnie prospect avec laquelle vous collaborez ou entretenez des relations."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: relationship, prospect
ms.date: 06/06/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 6a1141c352dd93657d32bb83067ce32077901a47
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-create-contact-companies"></a><span data-ttu-id="4f1f4-103">Procédure : créer des compagnies contact</span><span class="sxs-lookup"><span data-stu-id="4f1f4-103">How to: Create Contact Companies</span></span>
<span data-ttu-id="4f1f4-104">Vous pouvez créer un contact pour chaque nouvelle compagnie avec laquelle vous êtes en contact, par exemple un client, un fournisseur, un prospect, une banque, un cabinet d'avocats, un consultant, et ainsi de suite.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-104">You can create a contact for each new company you interact with, for example, a customer, vendor, prospective customer, bank, law firm, consultant, and so on.</span></span>

<span data-ttu-id="4f1f4-105">Il existe deux méthodes permettant de créer un contact : à partir de zéro ou à partir d'un client, d'un fournisseur ou d'un compte bancaire existant.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-105">There are two ways to create a contact: from scratch or from an existing customer, vendor, or bank account.</span></span>

<span data-ttu-id="4f1f4-106">Avant de créer un contact, vous pouvez vérifier les paramètres dans la fenêtre **Paramètres Marketing**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-106">Before creating a contact, you may want to check the settings in the **Marketing Setup** window.</span></span> <span data-ttu-id="4f1f4-107">Pour plus d'informations, voir [Paramétrage de la Gestion des relations](marketing-setup-marketing.md).</span><span class="sxs-lookup"><span data-stu-id="4f1f4-107">For more information, see [Setting Up Relationship Management](marketing-setup-marketing.md).</span></span>

## <a name="create-a-company-contact-from-scratch"></a><span data-ttu-id="4f1f4-108">Créer un contact compagnie à partir de zéro</span><span class="sxs-lookup"><span data-stu-id="4f1f4-108">Create a company contact from scratch</span></span>
1. <span data-ttu-id="4f1f4-109">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Contacts**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-109">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Contacts**, and then choose the related link.</span></span>
2. <span data-ttu-id="4f1f4-110">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-110">Choose the **New** action.</span></span>
3. <span data-ttu-id="4f1f4-111">Dans le champ **N°**, saisissez le numéro du contact.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-111">In the **No. field**, enter a number for the contact.</span></span>

    <span data-ttu-id="4f1f4-112">Si vous avez configuré une souche de numéros pour les contacts dans la fenêtre **Paramètres Marketing**, appuyez sur la touche Entrée pour sélectionner le numéro de contact suivant.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-112">Alternatively, if you have set up a number series for contacts in the **Marketing Setup** window, you can press the Enter key to select the next available contact number.</span></span>  
4. <span data-ttu-id="4f1f4-113">Définissez **Type** à **Société**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-113">Set **Type** to **Company**.</span></span>
5. <span data-ttu-id="4f1f4-114">Renseignez les autres champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-114">Fill in the other fields as required.</span></span>

## <a name="to-create-a-company-contact-from-a-customer-vendor-or-bank-account"></a><span data-ttu-id="4f1f4-115">Pour créer un contact compagnie à partir d'un client, d'un fournisseur ou d'un compte bancaire</span><span class="sxs-lookup"><span data-stu-id="4f1f4-115">To create a company contact from a customer, vendor, or bank account</span></span>
<span data-ttu-id="4f1f4-116">Si vous avez configuré plusieurs clients, fournisseurs et comptes bancaires, vous pouvez créer des contacts sur la base des données existantes.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-116">If you have already set up a number of customers, vendors, and bank accounts, you can create contacts on the basis of the existing data.</span></span> <span data-ttu-id="4f1f4-117">Lorsque vous créez un contact de cette façon, les informations de contact sont synchronisées avec les informations du client, du fournisseur ou du compte bancaire.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-117">When you create a contact this way, the contact information is synchronized with the customer, vendor, or bank account information.</span></span>

> [!NOTE]  
>   <span data-ttu-id="4f1f4-118">Avant de créer des sociétés contact de cette manière, vous devez spécifier un code relation d'affaires pour les clients, les fournisseurs, ainsi que des comptes bancaires dans la fenêtre **Paramètres marketing**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-118">Before you can create contact companies this way, you must specify a business relation code for customers, vendors, and bank accounts in the **Marketing Setup** window.</span></span> <span data-ttu-id="4f1f4-119">Si vous devez créer des contacts à partir de comptes bancaires, vous devez également spécifier des souches de numéros pour les comptes bancaires dans la fenêtre **Paramètres comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-119">If you will be creating contacts from a bank accounts, you must also specify numbers series for bank accounts in the **General Ledger Setup** window.</span></span>

1. <span data-ttu-id="4f1f4-120">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez l'un des choix suivants, selon l'élément à partir duquel vous souhaitez créer des contacts, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-120">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter one of the following, depending on from where you want to create contacts, and then choose the related link.</span></span>
   * <span data-ttu-id="4f1f4-121">**Créer contacts à partir des clients**</span><span class="sxs-lookup"><span data-stu-id="4f1f4-121">**Create Contacts from Customers**</span></span>
   * <span data-ttu-id="4f1f4-122">**Créer contacts à partir des fournisseurs**</span><span class="sxs-lookup"><span data-stu-id="4f1f4-122">**Create Contacts from Vendors**</span></span>
   * <span data-ttu-id="4f1f4-123">**Créer contacts à partir des cptes banc**</span><span class="sxs-lookup"><span data-stu-id="4f1f4-123">**Create Contacts from Bank Accounts**</span></span>
2. <span data-ttu-id="4f1f4-124">Dans la fenêtre de traitement par lots qui s'affiche, dans la section **Client**, **Fournisseur** ou **Compte bancaire**, définissez des filtres si vous souhaitez créer des contacts à partir de clients, de fournisseurs ou de comptes bancaires spécifiques.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-124">In the batch job window that opens, in the **Customer**, **Vendor**, or **Bank Account** section, set filters if you want to create contacts from specific customers, vendors, or bank accounts.</span></span>
3. <span data-ttu-id="4f1f4-125">Pour démarrer la création de contacts, cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-125">Choose the **OK** button to start creating contacts.</span></span>

    <span data-ttu-id="4f1f4-126">Les numéros de contact suivants de la série de numéros sont affectés aux nouveaux contacts.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-126">The next contact numbers in the number series are assigned to the new contacts.</span></span> <span data-ttu-id="4f1f4-127">La relation d'affaires des fournisseurs qui est spécifiée dans la fenêtre **Paramètres Marketing** est affectée aux contacts nouvellement créés.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-127">The business relation for vendors that is specified in the **Marketing Setup** window is assigned to the newly created contacts.</span></span>

> [!TIP]  
>   <span data-ttu-id="4f1f4-128">Vous pouvez également créer un client, un fournisseur ou un compte bancaire à partir d'un contact.</span><span class="sxs-lookup"><span data-stu-id="4f1f4-128">You can also create a customer, vendor, or bank account from a contact.</span></span> <span data-ttu-id="4f1f4-129">Pour plus d'informations, reportez-vous à [Créer un client, un fournisseur ou un compte bancaire à partir d'un contact](marketing-how-create-contacts-new-customers-vendors-bank-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="4f1f4-129">For more information, see [Create a Customer, Vendor, or Bank Account From a Contact](marketing-how-create-contacts-new-customers-vendors-bank-accounts.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4f1f4-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="4f1f4-130">See Also</span></span>
[<span data-ttu-id="4f1f4-131">Synchronisation des contacts avec les clients, les fournisseurs et les comptes bancaires</span><span class="sxs-lookup"><span data-stu-id="4f1f4-131">Synchronizing Contacts With Customers, Vendors, and Bank Accounts</span></span>](marketing-synchronize-contacts-customers-vendors-bank-accounts.md)  
[<span data-ttu-id="4f1f4-132">Affecter des relations d'affaires à un contact</span><span class="sxs-lookup"><span data-stu-id="4f1f4-132">Assign Business Relations to a Contact</span></span>](marketing-business-relations.md#AssignBusRelContact)  
[<span data-ttu-id="4f1f4-133">Affecter des secteurs d'activité à un contact</span><span class="sxs-lookup"><span data-stu-id="4f1f4-133">Assign Industry Groups to a Contact</span></span>](marketing-industry-groups.md#AssignIndustryGroupContact)  
[<span data-ttu-id="4f1f4-134">Affecter des groupes de distribution à un contact</span><span class="sxs-lookup"><span data-stu-id="4f1f4-134">Assign Mailing Groups to a Contact</span></span>](marketing-mailing-groups.md#AssignMailGroupContact)  
[<span data-ttu-id="4f1f4-135">Procédure : créer des personnes contact</span><span class="sxs-lookup"><span data-stu-id="4f1f4-135">How to: Create Contact Persons</span></span>](marketing-create-contact-persons.md)  
[<span data-ttu-id="4f1f4-136">Utilisation de Financials</span><span class="sxs-lookup"><span data-stu-id="4f1f4-136">Working with Financials</span></span>](ui-work-product.md)
