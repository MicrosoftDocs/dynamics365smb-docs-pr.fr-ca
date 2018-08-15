---
title: "Aperçu des tâches permettant de gérer la comptabilité fournisseur | Microsoft Docs"
description: "Décrit comment gérer les activités des ventes."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: trade, sell
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 046a42582dc66368fded90a4bb45add71a95d979
ms.openlocfilehash: 6351f2b8a79afa201192addc4960bda6d59448eb
ms.contentlocale: fr-ca
ms.lasthandoff: 07/02/2018

---
# <a name="sales"></a><span data-ttu-id="d0ae8-103">Vente</span><span class="sxs-lookup"><span data-stu-id="d0ae8-103">Sales</span></span>
<span data-ttu-id="d0ae8-104">Vous créez une facture vente ou un document de vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines méthodes de livraison et de paiement.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-104">You create a sales invoice or sales order to record your agreement with a customer to sell certain products on certain delivery and payment terms.</span></span>

<span data-ttu-id="d0ae8-105">Vous devez utiliser des documents de vente si votre processus de vente requiert que vous livriez des parties d'une quantité de commande, par exemple, si la quantité totale est pas disponible d'un coup.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-105">You must use sales orders if your sales process requires that you can ship parts of an order quantity, for example, because the full quantity is not available at once.</span></span> <span data-ttu-id="d0ae8-106">Si vous commercialisez des articles en les livrant directement du fournisseur au client, vous devez également utiliser les documents de vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-106">If you sell items by delivering directly from your vendor to your customer, as a drop shipment, then you must also use sales orders.</span></span> <span data-ttu-id="d0ae8-107">Pour tous les autres aspects, les commandes vente fonctionnent de la même manière que les factures vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-107">In all other aspects, sales orders work the same way as sales invoices.</span></span> <span data-ttu-id="d0ae8-108">Dans les documents de vente, vous pouvez également utiliser la fonctionnalité de promesse de livraison pour assurer avec certitude des dates de livraison à vos clients.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-108">With sales orders, you can also use the Order Promising functionality to communicate certain delivery dates to your customers.</span></span>  

<span data-ttu-id="d0ae8-109">Vous pouvez négocier avec le client en créant d'abord un devis, que vous pouvez convertir en facture vente ou en document de vente lorsque vous êtes d'accord sur la vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-109">You can negotiate with the customer by first creating a sales quote, which you can convert to a sales invoice or sales order when you agree on the sale.</span></span> <span data-ttu-id="d0ae8-110">Une fois que le client a confirmé l'entente, vous pouvez envoyer une confirmation de commande pour enregistrer votre obligation de fournir les produits comme convenu.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-110">After the customer has confirmed the agreement, you can send an order confirmation to record your obligation to deliver the products as agreed.</span></span>

<span data-ttu-id="d0ae8-111">Vous pouvez facilement corriger ou annuler une facture vente reportée avant qu'elle ne soit payée.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-111">You can easily correct or cancel a posted sales invoice before it is paid.</span></span> <span data-ttu-id="d0ae8-112">Cela est utile si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-112">This is useful if you want to correct a typing mistake or if the customer requests a change early in the order process.</span></span> <span data-ttu-id="d0ae8-113">Si la facture vente reportée est payée, vous devez créer une note de crédit vente ou un retour vente pour inverser la vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-113">If the posted sales invoice is paid, then you must create a sales credit memo or a sales return order to reverse the sale.</span></span>

<span data-ttu-id="d0ae8-114">Les pratiques recommandées en matière de vente et de marketing reposent toutes sur la prise de décisions appropriées au bon moment.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-114">Good sales and marketing practices are all about how to make the best decisions at the right time.</span></span> <span data-ttu-id="d0ae8-115">La fonctionnalité Marketing de [!INCLUDE[d365fin](includes/d365fin_md.md)] fournit une vue d'ensemble précise et opportune de vos informations de contact afin d'offrir des services à vos prospects de manière plus efficace et d'accroître la satisfaction de la clientèle.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-115">Marketing functionality in [!INCLUDE[d365fin](includes/d365fin_md.md)] provides precise and timely overview of your contact information so that you can serve your prospective customers more efficiently and increase customer satisfaction.</span></span> <span data-ttu-id="d0ae8-116">Pour plus d'informations, reportez-vous à [Gestion des relations](marketing-relationship-management.md).</span><span class="sxs-lookup"><span data-stu-id="d0ae8-116">For more information, see [Relationship Management](marketing-relationship-management.md).</span></span>

<span data-ttu-id="d0ae8-117">Dans les environnements d'entreprise où le client doit payer avant la livraison des produits vendus (par exemple la vente au détail), vous devez attendre la réception du paiement avant de fournir les produits.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-117">In business environments where the customer must pay before products are delivered, such as in retail, you must wait for the receipt of payment before you deliver the products.</span></span> <span data-ttu-id="d0ae8-118">Dans la plupart des cas, vous traitez les paiements entrants plusieurs semaines après la livraison en affectant les paiements à leurs factures vente reportées et impayées associées.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-118">In most cases, you process incoming payments some weeks after delivery by applying the payments to their related posted, unpaid sales invoices.</span></span> <span data-ttu-id="d0ae8-119">Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).</span><span class="sxs-lookup"><span data-stu-id="d0ae8-119">For more information, see [Reconcile Payments Using Automatic Application](receivables-how-reconcile-payments-auto-application.md).</span></span>

<span data-ttu-id="d0ae8-120">Les documents de vente peuvent être envoyés sous forme de fichiers PDF joints au courriel.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-120">Sales documents can be sent as PDF files attached to email.</span></span> <span data-ttu-id="d0ae8-121">Le corps du message contient un extrait du document de vente, comme les produits, le montant total et un lien vers le site Paypal.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-121">The email body will contain an extract of the sales document, such as products, total amount, and a link to the PayPal site.</span></span> <span data-ttu-id="d0ae8-122">Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md).</span><span class="sxs-lookup"><span data-stu-id="d0ae8-122">For more information, see [Send Documents by Email](ui-how-send-documents-email.md).</span></span>

<span data-ttu-id="d0ae8-123">Pour tous les processus de vente, vous pouvez incorporer un flux de travail d'approbation, par exemple, pour exiger que les ventes en grande quantité à certains clients soient approuvés par le responsable de la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-123">For all sales processes, you can incorporate an approval workflow, for example, to require that large sales to certain customers are approved by the accounting manager.</span></span> <span data-ttu-id="d0ae8-124">Pour plus d'informations, voir [Utilisation des flux de travail](across-use-workflows.md).</span><span class="sxs-lookup"><span data-stu-id="d0ae8-124">For more information, see [Using Workflows](across-use-workflows.md).</span></span>

<span data-ttu-id="d0ae8-125">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-125">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>

| <span data-ttu-id="d0ae8-126">À</span><span class="sxs-lookup"><span data-stu-id="d0ae8-126">To</span></span> | <span data-ttu-id="d0ae8-127">Voir</span><span class="sxs-lookup"><span data-stu-id="d0ae8-127">See</span></span> |
| --- | --- |
| <span data-ttu-id="d0ae8-128">Créer un devis dans lequel vous proposer des biens selon des conditions négociables avant de convertir le devis en facture vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-128">Create a sales quote where you offer products on negotiable terms before converting the quote to a sales invoice.</span></span> |[<span data-ttu-id="d0ae8-129">Créer des devis</span><span class="sxs-lookup"><span data-stu-id="d0ae8-129">Make Sales Quotes</span></span>](sales-how-make-offers.md) |
| <span data-ttu-id="d0ae8-130">Créer une facture vente pour enregistrer votre entente avec un client pour vendre des biens selon certaines méthodes de livraison et de paiement.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-130">Create a sales invoice to record your agreement with a customer to sell products on certain delivery and payment terms.</span></span> |[<span data-ttu-id="d0ae8-131">Facturer des ventes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-131">Invoice Sales</span></span>](sales-how-invoice-sales.md) |
| <span data-ttu-id="d0ae8-132">Traiter une document de vente qui implique un envoi partiel ou une livraison directe.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-132">Process a sales order that involves partial shipping or drop shipment.</span></span> |[<span data-ttu-id="d0ae8-133">Vendre des produits</span><span class="sxs-lookup"><span data-stu-id="d0ae8-133">Sell Products</span></span>](sales-how-sell-products.md) |
|<span data-ttu-id="d0ae8-134">Paramétrez les lignes vente ou achat standard que vous pouvez rapidement insérer dans les documents, par exemple, pour les ordres de réapprovisionnement récurrents.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-134">Set up standard sales or purchase lines that you can quickly insert on documents, for example, for recurring replenishment orders.</span></span>|[<span data-ttu-id="d0ae8-135">Créer des lignes ventes et achat récurrentes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-135">Create Recurring Sales and Purchase Lines</span></span>](sales-how-work-standard-lines.md)|  
| <span data-ttu-id="d0ae8-136">Lier un document de vente à un bon de commande pour vendre un article qui sera livré directement de votre fournisseur à votre client.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-136">Link a sales order to a purchase order to sell a drop-shipment item that will be delivered directly from your vendor to your customer.</span></span> |[<span data-ttu-id="d0ae8-137">Effectuer des livraisons directes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-137">Make Drop Shipments</span></span>](sales-how-drop-shipment.md) |
|<span data-ttu-id="d0ae8-138">Faites livrer par un fournisseur un article ne figurant pas dans l'inventaire vers votre entrepôt pour pouvoir le livrer à votre client.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-138">Have a nonstock item shipped from a vendor to your warehouse so that you can ship the item on to your customer.</span></span>|[<span data-ttu-id="d0ae8-139">Créer des commandes spéciales</span><span class="sxs-lookup"><span data-stu-id="d0ae8-139">Create Special Orders</span></span>](sales-how-to-create-special-orders.md)|
| <span data-ttu-id="d0ae8-140">Effectuez une action sur une facture vente reportée impayée pour créer automatiquement une note de crédit et annulez la facture vente ou recréez-la pour que vous puissiez y apporter des corrections.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-140">Perform an action on an unpaid posted sales invoice to automatically create a credit memo and either cancel the sales invoice or recreate it so you can make corrections.</span></span> |[<span data-ttu-id="d0ae8-141">Corriger ou annuler des factures vente impayées</span><span class="sxs-lookup"><span data-stu-id="d0ae8-141">Correct or Cancel Unpaid Sales Invoices</span></span>](sales-how-correct-cancel-sales-invoice.md) |
| <span data-ttu-id="d0ae8-142">Créez une note de crédit vente pour rétablir une facture vente reportée spécifique pour indiquer quels produits sont retournés par le client et quel montant règlement vous rembourserez.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-142">Create a sales credit memo to revert a specific posted sales invoice to reflect which products the customer returns and which payment amount you will refund.</span></span> |[<span data-ttu-id="d0ae8-143">Traiter les retours ou annulations de ventes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-143">Process Sales Returns or Cancellations</span></span>](sales-how-process-sales-returns-cancellations.md) |
|<span data-ttu-id="d0ae8-144">Gérez l'engagement de vos clients à acheter de grandes quantités livrées en plusieurs livraisons réparties au fil du temps.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-144">Manage your customer's commitment to purchase large quantities delivered in several shipments over time.</span></span>|[<span data-ttu-id="d0ae8-145">Utiliser des commandes permanentes ventes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-145">Work with Blanket Sales Orders</span></span>](sales-how-to-create-blanket-sales-orders.md)|
|<span data-ttu-id="d0ae8-146">Vendez les éléments d'assemblage qui ne sont pas disponibles actuellement en créant un ordre d'assemblage associé pour fournir la quantité totale ou partielle du document de vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-146">Sell assembly items that are not currently available by creating a linked assembly order to supply the full or partial sales order quantity.</span></span>|[<span data-ttu-id="d0ae8-147">Vente d'articles à assembler pour commande</span><span class="sxs-lookup"><span data-stu-id="d0ae8-147">Sell Items Assembled to Order</span></span>](assembly-how-to-sell-items-assembled-to-order.md)|
|<span data-ttu-id="d0ae8-148">Facturez un client une seule fois pour plusieurs livraisons en combinant les livraisons sur une seule facture.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-148">Invoice a customer once for multiple shipments by combining the shipments on one invoice.</span></span>|[<span data-ttu-id="d0ae8-149">Regroupement de livraisons sur une seule facture</span><span class="sxs-lookup"><span data-stu-id="d0ae8-149">Combine Shipments on a Single Invoice</span></span>](sales-how-to-combine-shipments-on-a-single-invoice.md)|
|<span data-ttu-id="d0ae8-150">Informez vos clients des dates de livraison en calculant, soit la date de simulation de délai, soit la date disponible à la vente.</span><span class="sxs-lookup"><span data-stu-id="d0ae8-150">Inform your customers of order delivery dates by calculating either the capable-to-promise date or the available-to-promise date.</span></span>|[<span data-ttu-id="d0ae8-151">Calculer des dates promesse livraison</span><span class="sxs-lookup"><span data-stu-id="d0ae8-151">Calculate Order Promising Dates</span></span>](sales-how-to-calculate-order-promising-dates.md)|

## <a name="see-also"></a><span data-ttu-id="d0ae8-152">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d0ae8-152">See Also</span></span>
[<span data-ttu-id="d0ae8-153">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="d0ae8-153">Setting Up Sales</span></span>](sales-setup-sales.md)  
[<span data-ttu-id="d0ae8-154">Enregistrer de nouveaux clients</span><span class="sxs-lookup"><span data-stu-id="d0ae8-154">Register New Customers</span></span>](sales-how-register-new-customers.md)  
[<span data-ttu-id="d0ae8-155">Gestion des comptes client</span><span class="sxs-lookup"><span data-stu-id="d0ae8-155">Managing Receivables</span></span>](receivables-manage-receivables.md)  
[<span data-ttu-id="d0ae8-156">Gestion des comptes fournisseur</span><span class="sxs-lookup"><span data-stu-id="d0ae8-156">Managing Payables</span></span>](payables-manage-payables.md)  
<span data-ttu-id="d0ae8-157">[Gestion de projets](projects-manage-projects.md)  </span><span class="sxs-lookup"><span data-stu-id="d0ae8-157">[Project Management](projects-manage-projects.md)  </span></span>  
<span data-ttu-id="d0ae8-158">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="d0ae8-158">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="d0ae8-159">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="d0ae8-159">General Business Functionality</span></span>](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 
