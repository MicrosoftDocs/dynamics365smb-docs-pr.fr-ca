---
title: "Procédure : gérer les renseignements sur le crédit client | Microsoft Docs"
description: "Dans [!INCLUDE[d365fin](../../includes/d365fin_md.md)], vous pouvez ajouter des commentaires aux renseignements sur le crédit client. Vous pouvez aussi mettre en attente et bloquer des clients présentant une mauvaise situation de crédit avant la livraison ou la facturation."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/11/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 2eb3d0183185158495c717a3fd83bff750678e5f
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-manage-customer-credit-information"></a><span data-ttu-id="ca048-104">Procédure : gérer les renseignements sur le crédit client</span><span class="sxs-lookup"><span data-stu-id="ca048-104">How to: Manage Customer Credit Information</span></span>
<span data-ttu-id="ca048-105">Dans [!INCLUDE[d365fin](../../includes/d365fin_md.md)], vous pouvez ajouter des commentaires aux renseignements sur le crédit client.</span><span class="sxs-lookup"><span data-stu-id="ca048-105">In [!INCLUDE[d365fin](../../includes/d365fin_md.md)], you can add comments to customer credit information.</span></span> <span data-ttu-id="ca048-106">Vous pouvez aussi mettre en attente et bloquer des clients présentant une mauvaise situation de crédit avant la livraison ou la facturation.</span><span class="sxs-lookup"><span data-stu-id="ca048-106">You can also hold and block customers with bad credit before shipping or invoicing occurs.</span></span>  

## <a name="to-add-comments-to-customer-credit-information"></a><span data-ttu-id="ca048-107">Pour ajouter des commentaires aux renseignements sur le crédit client</span><span class="sxs-lookup"><span data-stu-id="ca048-107">To add comments to customer credit information</span></span>  
1.  <span data-ttu-id="ca048-108">Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Gestion de crédit**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ca048-108">Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Credit Management**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ca048-109">Dans la fenêtre **Liste des clients - Gestion de crédit**, sélectionnez un client, puis choisissez l'action **Commentaires**.</span><span class="sxs-lookup"><span data-stu-id="ca048-109">In the **Customer List - Credit Mgmt.** window, select a customer, and then choose the **Comments** action.</span></span>  
3.  <span data-ttu-id="ca048-110">Dans la fenêtre **Feuille de commentaires**, renseignez les champs comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ca048-110">In the **Comment Sheet** window, fill in the fields as described in the following table.</span></span>  

    |<span data-ttu-id="ca048-111">Champ</span><span class="sxs-lookup"><span data-stu-id="ca048-111">Field</span></span>|<span data-ttu-id="ca048-112">Description</span><span class="sxs-lookup"><span data-stu-id="ca048-112">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="ca048-113">**Date**</span><span class="sxs-lookup"><span data-stu-id="ca048-113">**Date**</span></span>|<span data-ttu-id="ca048-114">Date du commentaire.</span><span class="sxs-lookup"><span data-stu-id="ca048-114">The date of the comment.</span></span>|  
    |<span data-ttu-id="ca048-115">**Commentaire**</span><span class="sxs-lookup"><span data-stu-id="ca048-115">**Comment**</span></span>|<span data-ttu-id="ca048-116">Commentaire sur le client.</span><span class="sxs-lookup"><span data-stu-id="ca048-116">The comment about the customer.</span></span> <span data-ttu-id="ca048-117">Vous pouvez entrer 80 caractères alphanumériques maximum.</span><span class="sxs-lookup"><span data-stu-id="ca048-117">You can enter a maximum of 80 alphanumeric characters.</span></span>|  

4.  <span data-ttu-id="ca048-118">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca048-118">Choose the **OK** button.</span></span>  

## <a name="to-prevent-an-order-from-shipping-or-invoicing"></a><span data-ttu-id="ca048-119">Pour éviter la livraison ou la facturation d'une commande</span><span class="sxs-lookup"><span data-stu-id="ca048-119">To prevent an order from shipping or invoicing</span></span>  
1.  <span data-ttu-id="ca048-120">Sélectionnez l'icône ![Page ou état pour la recherche](../../media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="ca048-120">Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ca048-121">Sélectionnez le client, puis choisissez l'action **Écritures**.</span><span class="sxs-lookup"><span data-stu-id="ca048-121">Select the customer, and the choose the **Ledger Entries** action.</span></span>  
3.  <span data-ttu-id="ca048-122">Dans le champ **En attente**, entrez les initiales du client.</span><span class="sxs-lookup"><span data-stu-id="ca048-122">In the **On Hold** field, enter the initials of the customer.</span></span>  
4.  <span data-ttu-id="ca048-123">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca048-123">Choose the **OK** button.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="ca048-124">Vous devez disposer d'une autorisation de sécurité adéquate pour ajouter ou supprimer des mises en attente de documents de vente spécifiques à l'aide du champ **En attente**.</span><span class="sxs-lookup"><span data-stu-id="ca048-124">You must have the proper security clearance to add or remove holds on individual sales orders using the **On Hold** field.</span></span>  

## <a name="to-block-a-sales-order-for-a-customer"></a><span data-ttu-id="ca048-125">Pour bloquer un document de vente pour un client</span><span class="sxs-lookup"><span data-stu-id="ca048-125">To block a sales order for a customer</span></span>  
1.  <span data-ttu-id="ca048-126">Choisissez l'icône ![Page ou rapport pour la recherche](../../media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Clients**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="ca048-126">Choose the ![Search for Page or Report](../../media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="ca048-127">Sélectionnez un client, puis cliquez sur l'action **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="ca048-127">Select a customer, and then choose the **Edit** action.</span></span>  
3.  <span data-ttu-id="ca048-128">Sur le raccourci **Général**, dans le champ **Bloqué**, sélectionnez une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="ca048-128">On the **General** FastTab, in the **Blocked** field, select one of the following options:</span></span>  

    -   <span data-ttu-id="ca048-129">**<Blank>** – La transaction est autorisée pour ce client.</span><span class="sxs-lookup"><span data-stu-id="ca048-129">**<Blank>** – Transaction is allowed for this customer.</span></span>  
    -   <span data-ttu-id="ca048-130">**Livrer** – Il n'est pas possible de créer de nouvelles commandes ni de nouvelles livraisons pour ce client.</span><span class="sxs-lookup"><span data-stu-id="ca048-130">**Ship** – New orders and new shipments cannot be created for this customer.</span></span> <span data-ttu-id="ca048-131">Les livraisons existantes qui ne sont pas encore facturées peuvent être facturées.</span><span class="sxs-lookup"><span data-stu-id="ca048-131">Existing shipments not yet invoiced can be invoiced.</span></span>  
    -   <span data-ttu-id="ca048-132">**Facturer** – Il n'est pas possible de créer de nouvelles commandes, de nouvelles livraisons ni de nouvelles factures pour ce client.</span><span class="sxs-lookup"><span data-stu-id="ca048-132">**Invoice** – New orders, new shipments, and new invoices cannot be created for this customer.</span></span> <span data-ttu-id="ca048-133">Les livraisons existantes qui ne sont pas encore facturées ne peuvent pas être facturées.</span><span class="sxs-lookup"><span data-stu-id="ca048-133">Existing shipments not yet invoiced cannot be invoiced.</span></span>  
    -   <span data-ttu-id="ca048-134">**Tout** – Aucune transaction n'est autorisée pour ce client, y compris les paiements.</span><span class="sxs-lookup"><span data-stu-id="ca048-134">**All** – No transaction is allowed for this customer, including payments.</span></span>  
4.  <span data-ttu-id="ca048-135">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="ca048-135">Choose the **OK** button.</span></span>  

## <a name="see-also"></a><span data-ttu-id="ca048-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ca048-136">See Also</span></span>  
[<span data-ttu-id="ca048-137">Fonctionnalités locales Canada</span><span class="sxs-lookup"><span data-stu-id="ca048-137">Canada Local Functionality</span></span>](canada-local-functionality.md)  
[<span data-ttu-id="ca048-138">Finance</span><span class="sxs-lookup"><span data-stu-id="ca048-138">Finance</span></span>](../../finance.md)  
[<span data-ttu-id="ca048-139">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="ca048-139">Setting Up Finance</span></span>](../../finance.md)
