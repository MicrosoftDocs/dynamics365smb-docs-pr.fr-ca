---
title: "Procédure : créer des factures de paiement anticipé | Microsoft Docs"
description: "Découvrez comment gérer les situations où votre fournisseur ou vous-même exigez un paiement anticipé."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 314732d3f622aede09342d7246e28b4a910d08d9
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-prepayment-invoices"></a><span data-ttu-id="c2916-103">Créer des factures de paiement anticipé</span><span class="sxs-lookup"><span data-stu-id="c2916-103">Create Prepayment Invoices</span></span>
<span data-ttu-id="c2916-104">Si vous voulez que vos clients fassent des paiements avant de leur livrer une commande ou si votre fournisseur exige que vous fassiez un paiement avant de vous livrer une commande, vous pouvez utiliser la fonctionnalité Paiement anticipé.</span><span class="sxs-lookup"><span data-stu-id="c2916-104">If you require your customers to submit payment before you ship an order to them, or if your vendor requires you to submit payment before they ship an order to you, you can use the prepayment functionality.</span></span>  

<span data-ttu-id="c2916-105">Après avoir créé un document de vente ou un bon de commande, vous pouvez créer une facture paiement anticipé.</span><span class="sxs-lookup"><span data-stu-id="c2916-105">After you create a sales or purchase order, you can create a prepayment invoice.</span></span> <span data-ttu-id="c2916-106">Vous pouvez utiliser les pourcentages par défaut pour chaque ligne vente ou achat, ou ajuster le montant en fonction si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="c2916-106">You can use the default percentages for each sales or purchase line, or you can adjust the amount as necessary.</span></span> <span data-ttu-id="c2916-107">Par exemple, vous pouvez spécifier un montant total pour la commande entière.</span><span class="sxs-lookup"><span data-stu-id="c2916-107">For example, you can specify a total amount for the entire order.</span></span>  

<span data-ttu-id="c2916-108">La procédure suivante décrit comment facturer un paiement anticipé pour des documents de vente.</span><span class="sxs-lookup"><span data-stu-id="c2916-108">The following procedure describes how to invoice a prepayment for a sales orders.</span></span> <span data-ttu-id="c2916-109">La procédure est identique pour les bons de commande.</span><span class="sxs-lookup"><span data-stu-id="c2916-109">The steps are similar for purchase orders.</span></span>  

## <a name="to-create-a-prepayment-invoice"></a><span data-ttu-id="c2916-110">Pour créer une facture paiement anticipé</span><span class="sxs-lookup"><span data-stu-id="c2916-110">To create a prepayment invoice</span></span>  
1. <span data-ttu-id="c2916-111">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Commandes vente**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="c2916-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2. <span data-ttu-id="c2916-112">Créez un document de vente.</span><span class="sxs-lookup"><span data-stu-id="c2916-112">Create a new sales order.</span></span> <span data-ttu-id="c2916-113">Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).</span><span class="sxs-lookup"><span data-stu-id="c2916-113">For more information, see [sell Products](sales-how-sell-products.md).</span></span>  

    <span data-ttu-id="c2916-114">Sur le raccourci **Acompte** le champ **% acompte** est renseigné automatiquement si un pourcentage d'acompte par défaut figure sur la fiche client.</span><span class="sxs-lookup"><span data-stu-id="c2916-114">On the **Prepayment** FastTab, the **Prepayment %** field will be filled in automatically if there is a default prepayment percentage on the customer card.</span></span> <span data-ttu-id="c2916-115">Vous pouvez modifier le contenu du champ.</span><span class="sxs-lookup"><span data-stu-id="c2916-115">You can change the contents of the field.</span></span> <span data-ttu-id="c2916-116">Le pourcentage de paiement anticipé est uniquement copié à partir de l'en-tête vers les lignes qui ne copient pas le pourcentage de paiement anticipé par défaut à partir de l'article.</span><span class="sxs-lookup"><span data-stu-id="c2916-116">The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.</span></span>  

    <span data-ttu-id="c2916-117">La sélection du champ **Compresser acompte** signifie que les lignes sont combinées sur la facture si :</span><span class="sxs-lookup"><span data-stu-id="c2916-117">If the **Compress Prepayment** field is selected, lines will be combined on the invoice if:</span></span>  
    - <span data-ttu-id="c2916-118">Elles ont le même compte du grand livre pour les paiements anticipés,comme déterminé par la configuration de report générale.</span><span class="sxs-lookup"><span data-stu-id="c2916-118">They have the same general ledger account for prepayments as determined by the general posting setup.</span></span>  
    - <span data-ttu-id="c2916-119">Elles sont les mêmes dimensions.</span><span class="sxs-lookup"><span data-stu-id="c2916-119">They have the same dimensions.</span></span>  

    <span data-ttu-id="c2916-120">Laissez le champ vide si vous souhaitez spécifier une facture paiement anticipé avec une ligne pour chaque ligne document de vente à laquelle un pourcentage de paiement anticipé est associé.</span><span class="sxs-lookup"><span data-stu-id="c2916-120">Leave the field blank if you want to specify a prepayment invoice with one line for each sales order line that has a prepayment percentage.</span></span>  

3. <span data-ttu-id="c2916-121">Renseignez les lignes vente.</span><span class="sxs-lookup"><span data-stu-id="c2916-121">Fill in the sales lines.</span></span>  

    <span data-ttu-id="c2916-122">Si des pourcentages d'acompte par défaut ont été configurés pour vos articles, ils sont copiés automatiquement dans le champ **% acompte** sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="c2916-122">If default prepayment percentages have been set up for your items, they are automatically copied to the **Prepayment %** field on the line.</span></span> <span data-ttu-id="c2916-123">Sinon, le pourcentage de paiement anticipé est copié à partir de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="c2916-123">Otherwise, the prepayment percentage is copied from the header.</span></span> <span data-ttu-id="c2916-124">Vous pouvez modifier le contenu du champ **% acompte** sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="c2916-124">You can change the contents of the **Prepayment %** field on the line.</span></span>  
4. <span data-ttu-id="c2916-125">Si vous voulez appliquer un pourcentage d'acompte à la commande entière, modifiez le champ **% acompte** dans l'en\-tête après avoir renseigné les lignes.</span><span class="sxs-lookup"><span data-stu-id="c2916-125">If you want to apply one prepayment percentage to the entire order, change the **Prepayment %** field on the header after filling in the lines.</span></span>  
5. <span data-ttu-id="c2916-126">Pour visualiser le montant du paiement anticipé total, choisissez l'action **Statistiques**.</span><span class="sxs-lookup"><span data-stu-id="c2916-126">To view the total prepayment amount, choose the **Statistics** action.</span></span>

    <span data-ttu-id="c2916-127">Pour ajuster le montant d'acompte total pour la commande, vous pouvez modifier le contenu du champ **Montant acompte** de la fenêtre **Statistiques commande vente**.</span><span class="sxs-lookup"><span data-stu-id="c2916-127">If you want to adjust the total prepayment amount for the order, you can change the contents of the **Prepayment Amount** field in the **Sales Order Statistics** window.</span></span>  

    <span data-ttu-id="c2916-128">Si le champ **Prix TVA comprise** est sélectionné, le champ **Montant acompte TTC** est modifiable.</span><span class="sxs-lookup"><span data-stu-id="c2916-128">If the **Prices Including VAT** field is selected, the **Prepayment Amount Incl. VAT** field is editable.</span></span>  

    <span data-ttu-id="c2916-129">Si vous modifiez la valeur du champ **Montant acompte**, le montant est réparti de façon proportionnelle entre toutes les lignes, à l'exception de celles qui contiennent la valeur **0** dans le champ **% acompte**.</span><span class="sxs-lookup"><span data-stu-id="c2916-129">If you change the contents of the **Prepayment Amount** field, the amount will be distributed proportionately between all lines, except those that have **0** in the **Prepayment %** field.</span></span>  
6. <span data-ttu-id="c2916-130">Pour effectuer un rapport de test avant de reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis choisissez **Rapport de test de paiement anticipé**.</span><span class="sxs-lookup"><span data-stu-id="c2916-130">To print a test report before posting the prepayment invoice, choose the **Prepayment** action, and then choose the **Prepayment Test Report** action.</span></span>  
7. <span data-ttu-id="c2916-131">Pour reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis l'action **Reporter facture paiement anticipé**.</span><span class="sxs-lookup"><span data-stu-id="c2916-131">To post the prepayment invoice, choose the **Prepayment** action, and then choose the **Post Prepayment Invoice** action.</span></span>  

    <span data-ttu-id="c2916-132">Pour reporter et imprimer la facture paiement anticipé, choisissez l'action **Reporter et imprimer facture paiement anticipé**.</span><span class="sxs-lookup"><span data-stu-id="c2916-132">To post and print the prepayment invoice, choose the **Post and Print Prepmt. Invoice** action.</span></span>  

<span data-ttu-id="c2916-133">Vous pouvez émettre des factures paiement anticipé supplémentaires pour la commande.</span><span class="sxs-lookup"><span data-stu-id="c2916-133">You can issue additional prepayment invoices for the order.</span></span> <span data-ttu-id="c2916-134">Pour ce faire, augmentez le montant du paiement anticipé sur une ou plusieurs lignes, ajustez la date document si nécessaire, puis reportez la facture paiement anticipé.</span><span class="sxs-lookup"><span data-stu-id="c2916-134">To do this, increase the prepayment amount on one or more lines, adjust the document date if necessary, and post the prepayment invoice.</span></span> <span data-ttu-id="c2916-135">Une nouvelle facture est créée pour la différence entre les montants de paiement anticipé facturés jusqu'ici et le nouveau montant de paiement anticipé.</span><span class="sxs-lookup"><span data-stu-id="c2916-135">A new invoice will be created for the difference between the prepayment amounts invoiced so far and the new prepayment amount.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="c2916-136">Si vous êtes situé en Amérique du Nord, vous ne pouvez pas modifier le pourcentage de paiement anticipé après la facture paiement anticipé reportée.</span><span class="sxs-lookup"><span data-stu-id="c2916-136">If you are located in North America, you cannot change the prepayment percentage after the prepayment invoice has been posted.</span></span> <span data-ttu-id="c2916-137">Cela est empêché dans la version nord\-américaine de [!INCLUDE[d365fin](includes/d365fin_md.md)], car le calcul de la taxe sur les ventes est sinon incorrect.</span><span class="sxs-lookup"><span data-stu-id="c2916-137">This is prevented in the North American version of [!INCLUDE[d365fin](includes/d365fin_md.md)] because the calculation of sales tax will otherwise be incorrect.</span></span>  

 <span data-ttu-id="c2916-138">Lorsque vous êtes prêt à reporter le reste de la facture, reportez-le comme n'importe quelle facture. Le montant du paiement anticipé est automatiquement déduit du montant dû.</span><span class="sxs-lookup"><span data-stu-id="c2916-138">When you are ready to post the rest of the invoice, post it as you would post any invoice, and the prepayment amount will automatically be deducted from the amount due.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c2916-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c2916-139">See Also</span></span>  
[<span data-ttu-id="c2916-140">Facturation de paiements anticipés</span><span class="sxs-lookup"><span data-stu-id="c2916-140">Invoicing Prepayments</span></span>](finance-invoice-prepayments.md)  
[<span data-ttu-id="c2916-141">Procédure pas à pas : configuration et facturation d'acomptes</span><span class="sxs-lookup"><span data-stu-id="c2916-141">Walkthrough: Setting Up and Invoicing Sales Prepayments</span></span>](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[<span data-ttu-id="c2916-142">Finance</span><span class="sxs-lookup"><span data-stu-id="c2916-142">Finance</span></span>](finance.md)  
<span data-ttu-id="c2916-143">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="c2916-143">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

