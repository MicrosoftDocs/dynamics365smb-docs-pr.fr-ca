---
title: "Procédure : créer des commandes permanentes ventes | Microsoft Docs"
description: "Utilisez des commandes ouvertes quand un client a accepté d'acheter de grandes quantités à livrer en plusieurs expéditions de petite taille au cours d'une période déterminée."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 75e170f10927844ca37a001812e78e062e88c451
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="work-with-blanket-sales-orders"></a><span data-ttu-id="a144f-103">Utiliser des commandes permanentes ventes</span><span class="sxs-lookup"><span data-stu-id="a144f-103">Work with Blanket Sales Orders</span></span>
<span data-ttu-id="a144f-104">Une commande permanente ventes représente le cadre d'une entente à long terme entre votre client et vous.</span><span class="sxs-lookup"><span data-stu-id="a144f-104">A blanket sales order represents a framework for a long-term agreement between you and your customer.</span></span>

<span data-ttu-id="a144f-105">Une commande permanente est généralement établie quand un client s'est engagé à acheter de grandes quantités à livrer en plusieurs livraisons de plus petite taille au cours d'une période déterminée.</span><span class="sxs-lookup"><span data-stu-id="a144f-105">A blanket order is typically made when a customer has committed to purchasing large quantities that are to be delivered in several smaller shipments over a certain period of time.</span></span> <span data-ttu-id="a144f-106">Souvent, les commandes ouvertes ne couvrent qu'un article avec des dates de livraison prédéfinies.</span><span class="sxs-lookup"><span data-stu-id="a144f-106">Often blanket orders cover only one item with predetermined delivery dates.</span></span> <span data-ttu-id="a144f-107">La principale raison d'utiliser une commande ouverte plutôt qu'une document de vente est que les quantités entrées dans une commande ouverte n'affectent pas la disponibilité de l'article et peuvent donc être utilisées comme une journal à des fins de surveillance, de précision et de planification.</span><span class="sxs-lookup"><span data-stu-id="a144f-107">The main reason for using a blanket order rather than a sales order is that quantities entered on a blanket order do not affect item availability and thus can be used as a worksheet for monitoring, forecasting, and planning purposes.</span></span>

<span data-ttu-id="a144f-108">Sur la commande permanente, vous pouvez configurer chaque livraison comme une ligne commande distincte qui peut ensuite être convertie en document de vente au moment de la livraison.</span><span class="sxs-lookup"><span data-stu-id="a144f-108">On the blanket order, each separate shipment can be set up as an order line, which can then be converted into a sales order at the time of shipping.</span></span>

<span data-ttu-id="a144f-109">Vous pouvez utiliser une commande permanente ventes, par exemple, lorsqu'un client appelle pour passer une commande de 1 000 unités d'un article et souhaite des livraisons par lot de 250 unités chaque semaine du mois suivant.</span><span class="sxs-lookup"><span data-stu-id="a144f-109">An example of when a blanket sales order could be used is if a customer calls and places an order of 1000 units of an item and they want the items to be delivered in 250 units every week over the next month.</span></span>

> [!NOTE]
> <span data-ttu-id="a144f-110">Les commandes permanentes achats fonctionnent de la même manière que les commandes permanentes ventes.</span><span class="sxs-lookup"><span data-stu-id="a144f-110">Blanket purchase orders work in a similar way as blanket sales orders.</span></span> <span data-ttu-id="a144f-111">Cette documentation ne couvre pas les commandes permanentes achats.</span><span class="sxs-lookup"><span data-stu-id="a144f-111">This documentation does not cover blanket purchase orders.</span></span>

## <a name="to-create-a-blanket-sales-order"></a><span data-ttu-id="a144f-112">Pour créer une commande permanente ventes</span><span class="sxs-lookup"><span data-stu-id="a144f-112">To create a blanket sales order</span></span>  
1. <span data-ttu-id="a144f-113">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Commandes permanentes ventes**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a144f-113">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Sales Orders**, and then choose the related link.</span></span>  
2. <span data-ttu-id="a144f-114">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="a144f-114">Choose the **New** action.</span></span>  
3. <span data-ttu-id="a144f-115">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="a144f-115">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  <span data-ttu-id="a144f-116">Laissez vide le champ **Date commande**.</span><span class="sxs-lookup"><span data-stu-id="a144f-116">Leave the **Order Date** field blank.</span></span> <span data-ttu-id="a144f-117">Lors de la création de documents de vente séparés depuis la commande permanente, la date commande du document de vente est définie comme étant égale à la date du jour.</span><span class="sxs-lookup"><span data-stu-id="a144f-117">When the separate sales orders are created from the blanket order, the order date of the sales order is set to equal the actual work date.</span></span>
5. <span data-ttu-id="a144f-118">Dans le raccourci **Lignes**, créez des lignes distinctes pour chaque expédition.</span><span class="sxs-lookup"><span data-stu-id="a144f-118">On the **Lines** FastTab, create separate lines for each shipment.</span></span> <span data-ttu-id="a144f-119">Par exemple, si le client souhaite 1 000 unités réparties de façon uniforme sur quatre semaines, entrez quatre lignes distinctes de 250 unités chacune.</span><span class="sxs-lookup"><span data-stu-id="a144f-119">For instance, if your customer wants 1000 units split out equally between four weeks, you would enter four separate lines of 250 units each.</span></span>   

## <a name="to-create-a-sales-order-from-a-blanket-sales-order"></a><span data-ttu-id="a144f-120">Pour créer un document de vente à partir d'une commande permanente ventes</span><span class="sxs-lookup"><span data-stu-id="a144f-120">To create a sales order from a blanket sales order</span></span>  

1.  <span data-ttu-id="a144f-121">Pour créer une commande pour l'une des lignes de l'ordre d'assemblage ouvert, effacez la quantité du champ **Qté à expédier** de toutes les lignes que vous ne voulez PAS expédier actuellement.</span><span class="sxs-lookup"><span data-stu-id="a144f-121">To create an order for any of the lines in the blanket assembly order, remove the quantity in the **Qty. to Ship** field on all the lines that you DO NOT wish to ship at this time.</span></span>  
2.  <span data-ttu-id="a144f-122">Lorsque vous êtes prêt à créer les commandes, sélectionnez **Créer commande**, puis **Oui**.</span><span class="sxs-lookup"><span data-stu-id="a144f-122">When you are ready to create orders, choose the **Make Order**m action, and then choose **Yes**.</span></span> <span data-ttu-id="a144f-123">Un message s'affiche, vous informant que la commande ouverte a été associée à un numéro de commande.</span><span class="sxs-lookup"><span data-stu-id="a144f-123">A message appears informing you that the blanket order has been assigned an order number.</span></span> <span data-ttu-id="a144f-124">Remarquez que la commande ouverte n'a pas été supprimée.</span><span class="sxs-lookup"><span data-stu-id="a144f-124">Note that the blanket order has not been deleted.</span></span>  
3.  <span data-ttu-id="a144f-125">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="a144f-125">Choose the **OK** button.</span></span>  
4.  <span data-ttu-id="a144f-126">Pour afficher les résultats des étapes précédentes, sélectionnez l'action **Ligne**, l'action **Lignes non reportées**, puis l'action **Commandes**.</span><span class="sxs-lookup"><span data-stu-id="a144f-126">To see the results of the preceding steps, choose the **Line** action, choose the **Unposted Lines** action, and then choose the **Orders** action.</span></span>  
5.  <span data-ttu-id="a144f-127">Dans la fenêtre **Lignes vente**, sélectionnez le document de vente approprié, sélectionnez l'action **Ligne**, sélectionnez Ligne, puis sélectionnez l'action **Afficher document**.</span><span class="sxs-lookup"><span data-stu-id="a144f-127">In the **Sales Lines** window, select the appropriate sales order, choose the **Line** action, and then choose the **Show Document** action.</span></span>  

<span data-ttu-id="a144f-128">Ce qui suit affecte les documents de vente après leur création à partir de documents de vente ouverts :</span><span class="sxs-lookup"><span data-stu-id="a144f-128">The following applies to sales orders after they have been created from blanket sales orders:</span></span>  

- <span data-ttu-id="a144f-129">Une fois la commande permanente convertie en document de vente, celui-ci contient toutes les lignes de la commande permanente.</span><span class="sxs-lookup"><span data-stu-id="a144f-129">After the blanket order is converted into a sales order, the sales order contains all the lines from the blanket order.</span></span> <span data-ttu-id="a144f-130">Les lignes où la quantité figurant dans le champ **Qté à expédier** a été supprimée s'affichent mais avec les champs **Quantité** vides.</span><span class="sxs-lookup"><span data-stu-id="a144f-130">The lines where the quantity in the **Qty. to Ship** field was deleted appear, but with blank **Quantity** fields.</span></span> <span data-ttu-id="a144f-131">Vous pouvez décider de laisser, de modifier ou de supprimer les lignes.</span><span class="sxs-lookup"><span data-stu-id="a144f-131">You may choose to leave, edit, or delete the lines.</span></span>  
- <span data-ttu-id="a144f-132">N'oubliez pas que la quantité de la ligne document de vente ne peut pas dépasser celle de la ligne commande permanente associée.</span><span class="sxs-lookup"><span data-stu-id="a144f-132">It is important to remember that the sales order line quantity must not exceed the quantity of the associated blanket order line.</span></span> <span data-ttu-id="a144f-133">Sinon, le report du document de vente est impossible.</span><span class="sxs-lookup"><span data-stu-id="a144f-133">Otherwise, posting of the sales order will not be possible.</span></span>  
- <span data-ttu-id="a144f-134">Lorsque le document de vente est reporté comme livré et/ou facturé, les champs **Qté livrée** et **Quantité facturée** sont mis à jour sur la commande ouverte concernée.</span><span class="sxs-lookup"><span data-stu-id="a144f-134">When the sales order is posted as shipped and/or invoiced, the **Quantity Shipped** and **Quantity Invoiced** fields are updated on the related blanket order.</span></span>  
- <span data-ttu-id="a144f-135">Le numéro de commande ouverte et un numéro de ligne sont enregistrés comme propriétés des lignes vente en cas de création à partir d'une commande ouverte.</span><span class="sxs-lookup"><span data-stu-id="a144f-135">The blanket order number and line number are recorded as properties of the sales lines when created from a blanket order.</span></span>  
- <span data-ttu-id="a144f-136">Si les commandes vente ne sont pas créées directement depuis la commande ouverte mais ont trait à celle\-ci, il est possible de créer un lien entre une commande vente et une commande ouverte en entrant le numéro de commande ouverte associé dans le champ **N° commande ouverte**</span><span class="sxs-lookup"><span data-stu-id="a144f-136">When sales orders are not created directly from the blanket order but still relate to it, a link between a sales order and a blanket order can be established by entering the associated blanket order number in the **Blanket Order No.**</span></span> <span data-ttu-id="a144f-137">sur la ligne de document de vente.</span><span class="sxs-lookup"><span data-stu-id="a144f-137">field on the sales order line.</span></span>  
- <span data-ttu-id="a144f-138">Une fois le document de vente créé pour la quantité totale d'une ligne commande permanente, aucun autre document de vente ne peut être créé pour la même ligne.</span><span class="sxs-lookup"><span data-stu-id="a144f-138">After the sales order has been created for the total quantity of a blanket order line, no other sales order can be created for the same line.</span></span> <span data-ttu-id="a144f-139">Les utilisateurs ne peuvent plus entrer de quantité dans le champ **Qté à expédier**.</span><span class="sxs-lookup"><span data-stu-id="a144f-139">Users are prevented from entering a quantity in the **Qty. to Ship** field.</span></span> <span data-ttu-id="a144f-140">Toutefois, si des quantités supplémentaires doivent être ajoutées à une commande ouverte, il est possible d'augmenter la valeur du champ **Quantité** et de créer des commandes supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="a144f-140">If, however, additional quantities need to be added to a blanket order, the value in the **Quantity** field can be increased and additional orders can then be created.</span></span>  
- <span data-ttu-id="a144f-141">La commande ouverte vente facturée reste dans le système jusqu'à ce qu'elle soit supprimée, soit en supprimant les commandes ouvertes individuelles, soit en exécutant le traitement par lots **Suppr. cdes vente ouv. fact.**.</span><span class="sxs-lookup"><span data-stu-id="a144f-141">The invoiced blanket sales order remains in the system until it is deleted, either by deleting individual blanket orders or by running the **Delete Invoiced Blanket Sales Orders** batch job.</span></span>  
- <span data-ttu-id="a144f-142">Si un client est également enregistré comme contact dans le module Marketing et si vous avez spécifié un code modèle interaction pour les commandes vente ouvertes dans la fenêtre **Paramètres Marketing**, lorsque vous sélectionnez **Imprimer** pour imprimer la commande vente ouverte, une interaction est enregistrée automatiquement dans la table Écriture journal interaction.</span><span class="sxs-lookup"><span data-stu-id="a144f-142">If a customer is also recorded as a contact in the Marketing application area, and if you have specified an interaction template code for blanket sales order in the **Marketing Setup** window, an interaction is recorded in the Interaction Log Entry table when you select **Print** to print the blanket sales order.</span></span>

## <a name="to-view-the-status-of-a-blanket-purchase-order"></a><span data-ttu-id="a144f-143">Pour visualiser l'état d'une commande permanente achats</span><span class="sxs-lookup"><span data-stu-id="a144f-143">To view the status of a blanket purchase order</span></span>  
<span data-ttu-id="a144f-144">Vous pouvez visualiser l'état d'une commande permanente ventes dans la fenêtre **Statistiques Commande permanente achats**.</span><span class="sxs-lookup"><span data-stu-id="a144f-144">You can see the status of a blanket sales order in the **Purchase Blanket Order Statistics** window.</span></span> <span data-ttu-id="a144f-145">Ceci peut s'avérer utile lorsque vous commencez à facturer une commande créée à partir de la commande permanente achats.</span><span class="sxs-lookup"><span data-stu-id="a144f-145">This may be relevant when you start to invoice the order that is created from the blanket purchase order.</span></span>  

1.  <span data-ttu-id="a144f-146">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Commandes permanentes achats**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a144f-146">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Blanket Purchase Orders**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="a144f-147">Sélectionnez une commande permanente achats, puis choisissez l'action **Statistiques**.</span><span class="sxs-lookup"><span data-stu-id="a144f-147">Select a blanket purchase order, and then choose the **Statistics** action.</span></span>  
3.  <span data-ttu-id="a144f-148">Dans la fenêtre **Statistiques Commande ouverte achat**, sur le raccourci **Général**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la commande. Elles se basent sur la quantité totale des **champs Quantité** sur les lignes commande ouverte achat.</span><span class="sxs-lookup"><span data-stu-id="a144f-148">In the **Purchase Blanket Order Statistics** window, on the **General** FastTab, you can see summary information about the entire order based on the total quantity in the various **Quantity fields** on the blanket purchase order lines.</span></span>  

    - <span data-ttu-id="a144f-149">Sur le raccourci **Facturation**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la quantité dans les champs **Qté à facturer** des lignes commande ouverte achat.</span><span class="sxs-lookup"><span data-stu-id="a144f-149">On the **Invoicing** FastTab, you can see summary information based on the total quantity in the **Qty. to Invoice** fields on the purchase blanket order lines.</span></span>  
    - <span data-ttu-id="a144f-150">Sur le raccourci **Expédition**, vous pouvez visualiser des informations récapitulatives concernant l'intégralité de la quantité dans les champs **Qté à recevoir** des lignes commande ouverte achat.</span><span class="sxs-lookup"><span data-stu-id="a144f-150">On the **Shipping** FastTab, you can see summary information based on the total quantity in the **Qty. to Receive** fields on the purchase blanket order lines.</span></span>  
    - <span data-ttu-id="a144f-151">Sur le raccourci **Paiement anticipé**, vous pouvez visualiser des informations récapitulatives concernant les éventuels montants déjà payés.</span><span class="sxs-lookup"><span data-stu-id="a144f-151">On the **Prepayment** FastTab, you can see summary information about any prepaid amounts.</span></span>  
    - <span data-ttu-id="a144f-152">Sur le raccourci **Fournisseur**, vous pouvez visualiser certaines informations de base concernant le fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a144f-152">On the **Vendor** FastTab, you can see certain basic information about the vendor.</span></span>    

## <a name="to-view-unposted-and-posted-blanket-sales-order-lines"></a><span data-ttu-id="a144f-153">Pour afficher des lignes commande permanente ventes reportées et non reportées</span><span class="sxs-lookup"><span data-stu-id="a144f-153">To view unposted and posted blanket sales order lines</span></span>   
<span data-ttu-id="a144f-154">Le lien entre la commande permanente ventes et le document de vente d'origine, et n'importe quel autre document vente, est conservé après report en tant que liste des lignes facture reportées et non reportées de document de vente.</span><span class="sxs-lookup"><span data-stu-id="a144f-154">The link between the blanket sales order and the originating sales order, and any other sales document, is retained after posting as a list of posted and unposted sales order invoice lines.</span></span>  

1. <span data-ttu-id="a144f-155">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Commandes permanentes ventes**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="a144f-155">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon enter **Blanket Sales Orders**, and then choose the related link.</span></span>
2. <span data-ttu-id="a144f-156">Ouvrez la commande permanente ventes que vous souhaitez afficher.</span><span class="sxs-lookup"><span data-stu-id="a144f-156">Open the blanket sales order you want to view.</span></span>
3. <span data-ttu-id="a144f-157">Pour visualiser les écritures non reportées, sélectionnez la ligne en question, sélectionnez l'action **Ligne**, puis l'action **Lignes non reportées**.</span><span class="sxs-lookup"><span data-stu-id="a144f-157">To view unposted entries, select the line in question, choose the **Line** action, and then choose the **Unposted Lines** action.</span></span> <span data-ttu-id="a144f-158">Choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="a144f-158">Choose one of the following options.</span></span>  

    <table>
    <tr>
    <th><span data-ttu-id="a144f-159">Option</span><span class="sxs-lookup"><span data-stu-id="a144f-159">Option</span></span></th>
    <th><span data-ttu-id="a144f-160">Description</span><span class="sxs-lookup"><span data-stu-id="a144f-160">Description</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-161">**Commandes**</span><span class="sxs-lookup"><span data-stu-id="a144f-161">**Orders**</span></span></td>
    <td><span data-ttu-id="a144f-162">Spécifie les commandes ouvertes associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-162">Specifies open orders associated with the selected line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-163">**Factures**</span><span class="sxs-lookup"><span data-stu-id="a144f-163">**Invoices**</span></span></td>
    <td><span data-ttu-id="a144f-164">Spécifie les factures ouvertes associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-164">Specifies open invoices that have been associated with the selected line.</span></span> <span data-ttu-id="a144f-165">Ouvrez les factures associées manuellement à une commande ouverte en entrant le numéro de commande ouverte dans la ligne facture vente.</span><span class="sxs-lookup"><span data-stu-id="a144f-165">Open invoices are manually associated with a blanket order by entering the blanket order number on the sales invoice line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-166">**Retours**</span><span class="sxs-lookup"><span data-stu-id="a144f-166">**Return Orders**</span></span></td>
    <td><span data-ttu-id="a144f-167">Spécifie les commandes retour ouvertes associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-167">Specifies open return orders that have been associated with the selected line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-168">**Avoirs**</span><span class="sxs-lookup"><span data-stu-id="a144f-168">**Credit Memos**</span></span></td>
    <td><span data-ttu-id="a144f-169">Spécifie les avoirs ouverts associés à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-169">Specifies open credit memos that have been associated with the selected line.</span></span></td>
    </tr>
    </table><span data-ttu-id="a144f-170">
4. Pour visualiser les écritures reportées, sélectionnez la ligne en question, choisissez l'action **Ligne**, puis l'action **Lignes reportées**.</span><span class="sxs-lookup"><span data-stu-id="a144f-170">
4. To view posted entries, select the line in question, choose the **Line** action, and then choose the **Posted Lines** action.</span></span> <span data-ttu-id="a144f-171">Choisissez l'une des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="a144f-171">Choose one of the following options.</span></span>  

    <table>
    <tr>
    <th><span data-ttu-id="a144f-172">Option</span><span class="sxs-lookup"><span data-stu-id="a144f-172">Option</span></span></th>
    <th><span data-ttu-id="a144f-173">Description</span><span class="sxs-lookup"><span data-stu-id="a144f-173">Description</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-174">**Livraisons**</span><span class="sxs-lookup"><span data-stu-id="a144f-174">**Shipments**</span></span></td>
    <td><span data-ttu-id="a144f-175">Livraisons reportées associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-175">Posted shipments associated with the selected line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-176">**Factures**</span><span class="sxs-lookup"><span data-stu-id="a144f-176">**Invoices**</span></span></td>
    <td><span data-ttu-id="a144f-177">Factures reportées associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-177">Posted invoices associated with the selected line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-178">**Réceptions retour**</span><span class="sxs-lookup"><span data-stu-id="a144f-178">**Return Receipts**</span></span></td>
    <td><span data-ttu-id="a144f-179">Réceptions retour reportées associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-179">Posted return receipts that have been associated with the selected line.</span></span></td>
    </tr>
    <tr>
    <td><span data-ttu-id="a144f-180">**Avoirs**</span><span class="sxs-lookup"><span data-stu-id="a144f-180">**Credit Memos**</span></span></td>
    <td><span data-ttu-id="a144f-181">Notes de crédit reportées associées à la ligne sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="a144f-181">Posted credit memos that have been associated with the selected line.</span></span></td>
    </tr>
    </table><span data-ttu-id="a144f-182">
5. Dans la fenêtre **Lignes vente**, sélectionnez l'action **Afficher document** pour afficher l'écriture.</span><span class="sxs-lookup"><span data-stu-id="a144f-182">
5. In the **Sales Lines** window, choose the **Show Document** action to view the entry.</span></span>

## <a name="see-also"></a><span data-ttu-id="a144f-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a144f-183">See Also</span></span>
[<span data-ttu-id="a144f-184">Vente</span><span class="sxs-lookup"><span data-stu-id="a144f-184">Sales</span></span>](sales-manage-sales.md)  
[<span data-ttu-id="a144f-185">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="a144f-185">Setting Up Sales</span></span>](sales-setup-sales.md)  
<span data-ttu-id="a144f-186">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="a144f-186">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
