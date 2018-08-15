---
title: "Créer une facture vente ou un document de vente | Microsoft Docs"
description: "Décrit comment créer une facture vente, un document de vente ou, enregistrer votre entente avec un client pour vendre des produits à des conditions spécifiques."
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bill, sale, invoice, order
ms.date: 04/30/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 046a42582dc66368fded90a4bb45add71a95d979
ms.openlocfilehash: 97116be5c1a0fbbef2564120ac95030f488aafbc
ms.contentlocale: fr-ca
ms.lasthandoff: 07/02/2018

---
# <a name="invoice-sales"></a><span data-ttu-id="ee9ab-103">Facturer des ventes</span><span class="sxs-lookup"><span data-stu-id="ee9ab-103">Invoice Sales</span></span>
<span data-ttu-id="ee9ab-104">Vous créez une facture vente ou un document de vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines méthodes de livraison et de paiement.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-104">You create a sales invoice or sales order to record your agreement with a customer to sell certain products on certain delivery and payment terms.</span></span>  

<span data-ttu-id="ee9ab-105">Dans certains scénarios, vous devez utiliser un document de vente au lieu d'une facture vente :</span><span class="sxs-lookup"><span data-stu-id="ee9ab-105">There are a couple of scenarios where you must use a sales order instead of a sales invoice:</span></span>  

* <span data-ttu-id="ee9ab-106">Si vous devez livrer uniquement une partie d'une quantité de commande, par exemple, si la quantité totale n'est pas disponible.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-106">If you need to ship only part of an order quantity, for example, because the full quantity is not on hand.</span></span>  
* <span data-ttu-id="ee9ab-107">Si vous vendez des articles que votre fournisseur fournit directement à votre client (une livraison directe).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-107">If you sell items that your vendor delivers directly to your customer, known as drop shipment.</span></span> <span data-ttu-id="ee9ab-108">Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-108">For more information, see [Make Drop Shipments](sales-how-drop-shipment.md).</span></span>  

<span data-ttu-id="ee9ab-109">Pour tous les autres aspects, les commandes vente et les factures vente fonctionnent de la même manière.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-109">In all other aspects, sales orders and sales invoices work in the same way.</span></span> <span data-ttu-id="ee9ab-110">Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-110">For more information, see [Sell Products](sales-how-sell-products.md).</span></span>

<span data-ttu-id="ee9ab-111">Vous pouvez négocier avec le client en créant d'abord un devis, que vous pouvez convertir en facture vente lorsque vous êtes d'accord sur la vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-111">You can negotiate with the customer by first creating a sales quote, which you can convert to a sales invoice when you agree on the sale.</span></span> <span data-ttu-id="ee9ab-112">Pour plus d'informations, voir [Créer des devis](sales-how-make-offers.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-112">For more information, see [Make Sales Quotes](sales-how-make-offers.md).</span></span>

<span data-ttu-id="ee9ab-113">Si le client décide d'acheter, vous reportez la facture vente pour créer les écritures quantité et valeur associées.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-113">If the customer decides to buy, you post the sales invoice to create the related quantity and value entries.</span></span> <span data-ttu-id="ee9ab-114">Lorsque vous reportez la facture vente, vous pouvez également envoyer par courriel le document en pièce jointe au format PDF.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-114">When you post the sales invoice, you can also email the document as a PDF attachment.</span></span> <span data-ttu-id="ee9ab-115">Vous pouvez faire en sorte que le corps du message soit prérempli avec un résumé des informations de facturation et de paiement, par exemple un lien vers Paypal.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-115">You can have the email body prefilled with a summary of the invoice and payment information, such as a link to PayPal.</span></span> <span data-ttu-id="ee9ab-116">Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-116">For more information, see [Send Documents by Email](ui-how-send-documents-email.md).</span></span>

<span data-ttu-id="ee9ab-117">Dans les environnements d'entreprise où le client paie un certain temps après la livraison, conformément aux conditions de paiement, une facture vente reportée reste ouverte (impayée) jusqu'à ce que le département Comptabilité client vérifie la réception du paiement et affecte le paiement à la facture vente reportée.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-117">In business environments where the customer pays some time after delivery, according to the payment term, a posted sales invoice remains open (unpaid) until the Accounts Receivable department verifies that payment is received and applies the payment to the posted sales invoice.</span></span> <span data-ttu-id="ee9ab-118">Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-118">For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).</span></span>

<span data-ttu-id="ee9ab-119">Dans les environnements d'entreprise où le client paie immédiatement, par exemple par PayPal ou en espèces, le paiement est enregistré immédiatement lorsque vous reportez la facture vente, c'est-à-dire la facture vente reportée est fermée comme entièrement affectée.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-119">In business environments where the customer pays immediately, for example by PayPal or cash, payment is recorded immediately when you post the sales invoice, that is, the posted sales invoice is closed as fully applied.</span></span> <span data-ttu-id="ee9ab-120">Vous sélectionnez la méthode appropriée dans le champ **Code mode de paiement** du document de vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-120">You select the relevant method in the **Payment Method Code** field on the sales order.</span></span> <span data-ttu-id="ee9ab-121">Voir l'étape 8.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-121">See under step 8.</span></span> <span data-ttu-id="ee9ab-122">Pour les paiements électroniques, tels que PayPal, vous devez également renseigner le champ **Service de paiement**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-122">For electronic payments, such as PayPal, you must also fill in the **Payment Service** field.</span></span> <span data-ttu-id="ee9ab-123">Pour plus d'informations, voir [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-123">For more information, see [Enable Customer Payments Through Payment Services](sales-how-enable-payment-service-extensions.md).</span></span>

<span data-ttu-id="ee9ab-124">Vous pouvez même créer des factures à paiement direct pour les clients non enregistrés en configurant une fiche « client en espèces », vers laquelle vous pointez sur la facture vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-124">You can even create directly-paid invoices for non-registered customers by first setting up a "cash customer" card, which you point to on the sales invoice.</span></span> <span data-ttu-id="ee9ab-125">Pour plus d'informations, reportez-vous à [Configurer des clients effectuant un achat au comptoir](finance-how-to-set-up-cash-customers.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-125">For more information, see [Set Up Cash Customers](finance-how-to-set-up-cash-customers.md).</span></span>  

<span data-ttu-id="ee9ab-126">Vous pouvez facilement corriger ou annuler une facture vente reportée avant qu'elle ne soit payée.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-126">You can easily correct or cancel a posted sales invoice before it is paid.</span></span> <span data-ttu-id="ee9ab-127">Cela est utile, par exemple, si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-127">For example, this is useful if you want to correct a typing mistake or if the customer requests a change early in the order process.</span></span> <span data-ttu-id="ee9ab-128">Pour plus d'informations, voir [Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-128">For more information, see [Correct or Cancel Unpaid Sales Invoices](sales-how-correct-cancel-sales-invoice.md).</span></span> <span data-ttu-id="ee9ab-129">Si la facture vente reportée est payée, vous devez créer une note de crédit vente pour inverser la vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-129">If the posted sales invoice is paid, then you must create a sales credit memo to reverse the sale.</span></span> <span data-ttu-id="ee9ab-130">Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-130">For more information, see [Process Sales Returns or Cancellations](sales-how-process-sales-returns-cancellations.md).</span></span>

<span data-ttu-id="ee9ab-131">Les articles peuvent être des articles en inventaire et des services, représentés par le type **Inventaire** ou **Service** sur la fiche article.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-131">Items can be both inventory items and services, denoted by the **Inventory** or **Service** type on the item card.</span></span> <span data-ttu-id="ee9ab-132">Le processus de facture vente est identique pour les deux types d'article.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-132">The sales invoice process is the same for both item types.</span></span> <span data-ttu-id="ee9ab-133">Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-133">For more information, see [Register New Items](inventory-how-register-new-items.md).</span></span>

<span data-ttu-id="ee9ab-134">Vous pouvez remplir les champs relatifs au client sur la facture vente de deux façons selon que le client est déjà enregistré ou non.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-134">You can fill customer fields on the sales invoice in two ways depending on whether the customer is already registered.</span></span> <span data-ttu-id="ee9ab-135">Reportez-vous aux étapes 2 et 3 de la procédure ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-135">See steps 2 and 3 in the following procedure.</span></span>

## <a name="to-create-a-sales-invoice"></a><span data-ttu-id="ee9ab-136">Pour créer une facture vente :</span><span class="sxs-lookup"><span data-stu-id="ee9ab-136">To create a sales invoice</span></span>
1. <span data-ttu-id="ee9ab-137">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures vente**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-137">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Invoices**, and then choose the related link.</span></span>  
2. <span data-ttu-id="ee9ab-138">Dans le champ **Client**, entrez le nom d'un client existant.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-138">In the **Customer** field, enter the name of an existing customer.</span></span>

   <span data-ttu-id="ee9ab-139">D'autres champs de la fenêtre **Facture vente** contiennent des informations standard sur le client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-139">Other fields in the **Sales Invoice** window contain standard information about the selected customer.</span></span> <span data-ttu-id="ee9ab-140">Si le client n'est pas enregistré, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="ee9ab-140">If the customer is not registered, follow these steps:</span></span>
3. <span data-ttu-id="ee9ab-141">Dans le champ **Client**, entrez le nom du nouveau client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-141">In the **Customer** field, enter the name of the new customer.</span></span>
4. <span data-ttu-id="ee9ab-142">Dans la boîte de dialogue d'enregistrement du nouveau client, cliquez sur le bouton **Oui**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-142">In the dialog box about registering the new customer, choose the **Yes** button.</span></span>
5. <span data-ttu-id="ee9ab-143">Dans la fenêtre **Sélectionnez un modèle pour un nouveau client**, sélectionnez un modèle sur lequel baser la nouvelle fiche client, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-143">In the **Select a template for a new customer** window, choose a template to base the new customer card on, and then choose the **OK** button.</span></span>
6. <span data-ttu-id="ee9ab-144">Une nouvelle fiche client affiche des informations sur le modèle client sélectionné.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-144">A new customer card displays the information on the selected customer template.</span></span> <span data-ttu-id="ee9ab-145">Renseignez les champs restants.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-145">Fill in the remaining fields.</span></span> <span data-ttu-id="ee9ab-146">Pour plus d'informations, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-146">For more information, see [Register New Customers](sales-how-register-new-customers.md).</span></span>  
7. <span data-ttu-id="ee9ab-147">Lorsque vous avez terminé la fiche client, cliquez sur le bouton **OK** pour revenir à la fenêtre **Facture vente**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-147">When you have completed the customer card, choose the **OK** button to return to the **Sales Invoice** window.</span></span>

   <span data-ttu-id="ee9ab-148">Plusieurs champs de la facture vente sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-148">Several fields on the sales invoice are now filled with information that you specified on the new customer card.</span></span>  
8. <span data-ttu-id="ee9ab-149">Renseignez les champs restants de la fenêtre **Facture vente**, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-149">Fill in the remaining fields in the **Sales Invoice** window as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > <span data-ttu-id="ee9ab-150">Si vous autorisez le client à payer immédiatement, par exemple, en liquide ou par PayPal, renseignez le champ **Code mode de règlement**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-150">If you allow the customer to pay immediately, for example, by cash or by PayPal, then fill in the **Payment Method Code** field.</span></span> <span data-ttu-id="ee9ab-151">Le paiement est ensuite enregistré dès que vous reportez la facture vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-151">The payment is then recorded as soon as you post the sales invoice.</span></span> <span data-ttu-id="ee9ab-152">Si vous sélectionnez ESPÈCES, le paiement est enregistré dans un compte de contrepartie spécifié.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-152">If you select CASH, then the payment is recorded in a specified balancing account.</span></span>

    <span data-ttu-id="ee9ab-153">Vous êtes maintenant prêt à renseigner les lignes facture vente pour les produits que vous vendez au client ou pour toute transaction avec le client que vous souhaitez enregistrer dans un compte du grand livre.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-153">You are now ready to fill in the sales invoice lines for products that you are selling to the customer or for any transaction with the customer that you want to record in a G/L account.</span></span>   

    <span data-ttu-id="ee9ab-154">Si vous avez défini des lignes vente récurrentes pour le client, tel qu'un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l'intermédiaire de l'action **Extraire les lignes vente récurrentes**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-154">If you have set up recurring sales lines for the customer, such as a monthly replenishment order, then you can insert these lines on the order by choosing the **Get Recurring Sales Lines** action.</span></span>  
9. <span data-ttu-id="ee9ab-155">Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à valider pour le client avec la ligne vente.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-155">On the **Lines** FastTab, in the **Type** field, select what type of product, charge, or transaction that you will post for the customer with the sales line.</span></span>
10. <span data-ttu-id="ee9ab-156">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="ee9ab-156">In the **No.**</span></span> <span data-ttu-id="ee9ab-157">sélectionnez un enregistrement à valider en fonction de la valeur du champ **Type**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-157">field, select a record to post according to the value in the **Type** field.</span></span>

    <span data-ttu-id="ee9ab-158">Laissez le champ **N°**</span><span class="sxs-lookup"><span data-stu-id="ee9ab-158">You leave the **No.**</span></span> <span data-ttu-id="ee9ab-159">vide dans les cas suivants :</span><span class="sxs-lookup"><span data-stu-id="ee9ab-159">field empty in the following cases:</span></span>

    * <span data-ttu-id="ee9ab-160">Si la ligne est destinée à un commentaire.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-160">If the line is for a comment.</span></span> <span data-ttu-id="ee9ab-161">Saisissez le commentaire dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-161">Write the comment in the **Description** field.</span></span>
    * <span data-ttu-id="ee9ab-162">Si la ligne est destinée à un article non stocké.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-162">If the line is for a nonstock item.</span></span> <span data-ttu-id="ee9ab-163">Sélectionnez l'action **Sélectionner articles non stockés**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-163">Choose the **Select Nonstock Items** action.</span></span> <span data-ttu-id="ee9ab-164">Pour en savoir plus, voir [Utiliser des articles non stockés](inventory-how-work-nonstock-items.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-164">For more information, see [Work With Nonstock Items](inventory-how-work-nonstock-items.md).</span></span>

11. <span data-ttu-id="ee9ab-165">Dans le champ **Quantité**, entrez le nombre d'unités du produit, de frais ou de la transaction que la ligne enregistre pour le client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-165">In the **Quantity** field, enter how many units of the product, charge, or transaction that the line will record for the customer.</span></span>  

    > [!NOTE]  
    >   <span data-ttu-id="ee9ab-166">Si l'article est de type **Service** ou si le champ **Type** contient **Ressource**, la quantité est une unité de temps, par exemple heures, comme indiqué dans le champ **Code unité de mesure** de la ligne.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-166">If the item is of type **Service**, or the **Type** field contains **Resource**, then the quantity is a time unit, such as hours, as indicated in the **Unit of Measure Code** field on the line.</span></span>  

    <span data-ttu-id="ee9ab-167">La valeur du champ **Montant ligne** est calculée comme suit : *Prix unitaire* x *Quantité*.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-167">The value in the **Line Amount** field is calculated as *Unit Price* x *Quantity*.</span></span>  

    <span data-ttu-id="ee9ab-168">Le prix et les montants ligne sont affichés avec ou sans la taxe de vente en fonction de la valeur que vous avez sélectionnée dans le champ **Prix incluant les taxes** de la fiche client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-168">The price and line amounts are with or without sales tax, depending on what you selected in the **Prices Including Tax** field on the customer card.</span></span>  
12. <span data-ttu-id="ee9ab-169">Si vous souhaitez accorder une remise, saisissez un pourcentage dans le champ **% remise ligne**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-169">If you want to give a discount, enter a percentage in the **Line Discount %** field.</span></span> <span data-ttu-id="ee9ab-170">La valeur du champ **Montant ligne** est mise à jour en conséquence.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-170">The value in the **Line Amount** field updates accordingly.</span></span>  

    <span data-ttu-id="ee9ab-171">Si des prix article spéciaux sont définis sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne vente sont automatiquement mis à jour si les critères de prix convenus sont réunis.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-171">If special item prices are set up on the **Sales Prices and Sales Line Discounts** FastTab on the customer or item card, the price and amount on the sales line automatically update if the price criteria is met.</span></span> <span data-ttu-id="ee9ab-172">Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-172">For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).</span></span>  
13. <span data-ttu-id="ee9ab-173">Répétez les étapes 9 à 12 pour chaque produit ou frais que vous souhaitez facturer au client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-173">Repeat steps 9 through 12 for every product or charge that you want to invoice the customer for.</span></span>  

    <span data-ttu-id="ee9ab-174">Les totaux sous les lignes sont calculés automatiquement au fur et à mesure que vous créez ou modifiez des lignes.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-174">The totals under the lines are automatically calculated as you create or modify lines.</span></span>  
14. <span data-ttu-id="ee9ab-175">Dans le champ **Montant remise facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-175">In the **Invoice Discount Amount** field, enter an amount that should be deducted from the value shown in the **Total Incl. Tax** field.</span></span>

    <span data-ttu-id="ee9ab-176">Si vous avez défini des remises facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% remise facture** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant remise facture sans TVA**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-176">If you have set up invoice discounts for the customer, then the specified percentage value is automatically inserted in the **Invoice Discount %** field if the criteria are met, and the related amount is inserted in the **Inv. Discount Amount Excl. Tax** field.</span></span> <span data-ttu-id="ee9ab-177">Pour plus d'informations, reportez-vous à [Enregistrement des prix de vente, des remises et des accords sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-177">For more information, see [Record Sales Price, Discount, and Payment Agreements](sales-how-record-sales-price-discount-payment-agreements.md).</span></span>  
15. <span data-ttu-id="ee9ab-178">Lorsque les lignes facture vente sont renseignées, sélectionnez l'action **Valider et envoyer**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-178">When the sales invoice lines are completed, choose the **Post and Send** action.</span></span>  

<span data-ttu-id="ee9ab-179">La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode de réception de documents par défaut du client.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-179">The **Post and Send Confirmation** dialog box displays the customer's preferred method of receiving documents.</span></span> <span data-ttu-id="ee9ab-180">Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-180">You can change the sending method by choosing the lookup button for the **Send Document to** field.</span></span> <span data-ttu-id="ee9ab-181">Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ee9ab-181">For more information, see [Set Up Document Sending Profiles](sales-how-setup-document-send-profiles.md).</span></span>

<span data-ttu-id="ee9ab-182">Les écritures article et client associées sont à présent créées dans votre système, et la facture vente est sortie en tant que document au format PDF.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-182">The related item and customer ledger entries are now created in your system, and the sales invoice is output as a PDF document.</span></span> <span data-ttu-id="ee9ab-183">La facture vente est supprimée de la liste des factures vente et remplacée par un nouveau document dans la liste des factures vente reportées.</span><span class="sxs-lookup"><span data-stu-id="ee9ab-183">The sales invoice is removed from the list of sales invoices and replaced with a new document in the list of posted sales invoices.</span></span>

## <a name="see-also"></a><span data-ttu-id="ee9ab-184">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="ee9ab-184">See Also</span></span>
[<span data-ttu-id="ee9ab-185">Ventes</span><span class="sxs-lookup"><span data-stu-id="ee9ab-185">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="ee9ab-186">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="ee9ab-186">Setting Up Sales</span></span>](sales-setup-sales.md)  
[<span data-ttu-id="ee9ab-187">Stock</span><span class="sxs-lookup"><span data-stu-id="ee9ab-187">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="ee9ab-188">Envoyer des documents par courriel</span><span class="sxs-lookup"><span data-stu-id="ee9ab-188">Send Documents by Email</span></span>](ui-how-send-documents-email.md)  
[<span data-ttu-id="ee9ab-189">Facturation en vrac à partir de Microsoft Bookings dans Business Central</span><span class="sxs-lookup"><span data-stu-id="ee9ab-189">Bulk Invoicing from Microsoft Bookings in Business Central </span></span>](finance-bookings.md)  
<span data-ttu-id="ee9ab-190">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="ee9ab-190">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
