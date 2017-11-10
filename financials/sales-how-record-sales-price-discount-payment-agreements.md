---
title: "Paramétrer les prix de vente spéciaux et les remises client | Microsoft Docs"
description: "Décrit comment définir les ententes secondaires de tarifs et d'escompte à affecter aux documents vente lors de la vente à différents clients."
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: special price, alternate price, pricing
ms.date: 09/08/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 3bb16f6f192e3a3ca29911cf6215fe1f00bfcb68
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-record-special-sales-prices-and-discounts"></a><span data-ttu-id="16ca4-103">Procédure : enregistrer les prix de vente spéciaux et les remises</span><span class="sxs-lookup"><span data-stu-id="16ca4-103">How to: Record Special Sales Prices and Discounts</span></span>
<span data-ttu-id="16ca4-104">Vous devez définir les différentes ententes de prix et d'escompte qui s'appliquent lors de la vente à différents clients de sorte que les valeurs et règles convenues s'appliquent aux documents vente créés à l'intention des clients.</span><span class="sxs-lookup"><span data-stu-id="16ca4-104">The different price and discount agreements that apply when selling to different customers must be defined so that the agreed rules and values are applied to sales documents that you create for the customers.</span></span>

<span data-ttu-id="16ca4-105">Lorsque vous avez enregistré des prix spéciaux et des remises de ligne pour les ventes et les achats, [!INCLUDE[d365fin](includes/d365fin_md.md)] s'assure que votre marge pour l'article est toujours optimale en calculant automatiquement le meilleur prix dans les documents achat et vente, sur le projet et les lignes feuille article.</span><span class="sxs-lookup"><span data-stu-id="16ca4-105">When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.</span></span> <span data-ttu-id="16ca4-106">Pour plus d'informations, voir la section « Calcul du meilleur prix ».</span><span class="sxs-lookup"><span data-stu-id="16ca4-106">For more information, see "Best Price Calculation" section.</span></span>

<span data-ttu-id="16ca4-107">En ce qui concerne les prix, un prix de vente spécial peut être inséré sur les lignes vente s'il existe une certaine combinaison de client, d'article, de quantité minimum, d'unité de mesure ou de date début/date de fin.</span><span class="sxs-lookup"><span data-stu-id="16ca4-107">Concerning prices, you can have a special sales price inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists.</span></span>

<span data-ttu-id="16ca4-108">En ce qui concerne les remises, vous pouvez définir et utiliser deux types de remises vente :</span><span class="sxs-lookup"><span data-stu-id="16ca4-108">Concerning discounts, you can set up and use two types of sales discounts:</span></span>

| <span data-ttu-id="16ca4-109">Type d'escompte</span><span class="sxs-lookup"><span data-stu-id="16ca4-109">Discount Type</span></span> | <span data-ttu-id="16ca4-110">Description</span><span class="sxs-lookup"><span data-stu-id="16ca4-110">Description</span></span> |
| --- | --- |
| <span data-ttu-id="16ca4-111">**Remise ligne vente**</span><span class="sxs-lookup"><span data-stu-id="16ca4-111">**Sales Line Discount**</span></span> |<span data-ttu-id="16ca4-112">Un escompte sous forme de montant inséré sur les lignes vente s'il existe une certaine combinaison de client, d'article, de quantité minimum, d'unité de mesure ou de date de début/date de fin.</span><span class="sxs-lookup"><span data-stu-id="16ca4-112">An amount discount that is inserted on sales lines if a certain combination of customer, item, minimum quantity, unit of measure, or starting/ending date exists.</span></span> <span data-ttu-id="16ca4-113">Cela fonctionne de la même manière que pour les prix de vente.</span><span class="sxs-lookup"><span data-stu-id="16ca4-113">This works in the same way as for sales prices.</span></span> |
| <span data-ttu-id="16ca4-114">**Remise facture**</span><span class="sxs-lookup"><span data-stu-id="16ca4-114">**Invoice Discount**</span></span> |<span data-ttu-id="16ca4-115">Un escompte sous forme de pourcentage qui est soustrait du total du document si la valeur de toutes les lignes d'un document vente dépasse un montant minimal donné.</span><span class="sxs-lookup"><span data-stu-id="16ca4-115">A percentage discount that is subtracted from the document total if the value amount of all lines on a sales document exceeds a certain minimum.</span></span> |

<span data-ttu-id="16ca4-116">Dans la mesure où les prix de vente et les escomptes ligne vente sont basés sur une combinaison article/client, vous pouvez également mettre en œuvre cette configuration à partir de la fiche article de l'article auquel les règles et valeurs s'appliquent.</span><span class="sxs-lookup"><span data-stu-id="16ca4-116">Because sales prices and sales line discounts are based on a combination of item and customer, you can also perform this configuration from the item card of the item where the rules and values apply.</span></span>

## <a name="to-set-up-a-sales-price-for-a-customer"></a><span data-ttu-id="16ca4-117">Pour définir un prix de vente pour un client</span><span class="sxs-lookup"><span data-stu-id="16ca4-117">To set up a sales price for a customer</span></span>
1. <span data-ttu-id="16ca4-118">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="16ca4-118">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.</span></span>
2. <span data-ttu-id="16ca4-119">Ouvrez la fiche client appropriée, puis sélectionnez l'action **Prix**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-119">Open the relevant customer card, and then choose the **Prices** action.</span></span>

    <span data-ttu-id="16ca4-120">Le champ **Type vente** est prérempli avec la valeur **Client** et le champ **Code vente** est prérempli avec le numéro du client.</span><span class="sxs-lookup"><span data-stu-id="16ca4-120">The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.</span></span>
3. <span data-ttu-id="16ca4-121">Renseignez les champs de la ligne selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="16ca4-121">Fill in the fields on the line as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]<span data-ttu-id="16ca4-122"> Renseignez une ligne pour chaque combinaison qui accorde un prix de vente spécial au client.</span><span class="sxs-lookup"><span data-stu-id="16ca4-122"> Fill a line for each combination that will grant a special sales price to the customer.</span></span>

## <a name="to-set-up-a-sales-line-discount-for-a-customer"></a><span data-ttu-id="16ca4-123">Pour définir un escompte de ligne vente pour un client</span><span class="sxs-lookup"><span data-stu-id="16ca4-123">To set up a sales line discount for a customer</span></span>
1. <span data-ttu-id="16ca4-124">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="16ca4-124">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.</span></span>
2. <span data-ttu-id="16ca4-125">Ouvrez la fiche client appropriée, puis sélectionnez l'action **Remises ligne**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-125">Open the relevant customer card, and then choose the **Line Discounts** action.</span></span>

    <span data-ttu-id="16ca4-126">Le champ **Type vente** est prérempli avec la valeur **Client** et le champ **Code vente** est prérempli avec le numéro du client.</span><span class="sxs-lookup"><span data-stu-id="16ca4-126">The **Sales Type** field is prefilled with **Customer**, and the **Sales Code** field is prefilled with the customer number.</span></span>
3. <span data-ttu-id="16ca4-127">Renseignez les champs de la ligne selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="16ca4-127">Fill in the fields on the line as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]<span data-ttu-id="16ca4-128"> Renseignez une ligne pour chaque combinaison qui accorde une remise ligne vente au client.</span><span class="sxs-lookup"><span data-stu-id="16ca4-128"> Fill a line for each combination that will grant a sales line discount to the customer.</span></span>

## <a name="to-set-up-an-invoice-discount-for-a-customer"></a><span data-ttu-id="16ca4-129">Pour configurer un escompte facture pour un client</span><span class="sxs-lookup"><span data-stu-id="16ca4-129">To set up an invoice discount for a customer</span></span>
<span data-ttu-id="16ca4-130">Une fois que vous avez décidé des clients pouvant faire l'objet d'escomptes facture, entrez le code escompte facture sur les fiches client et configurez les conditions pour chaque code.</span><span class="sxs-lookup"><span data-stu-id="16ca4-130">When you have decided which customers are eligible for invoice discounts, enter the invoice discount code on the customer cards and set up the terms for each code.</span></span>

1. <span data-ttu-id="16ca4-131">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Clients**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="16ca4-131">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customers**, and then choose the related link.</span></span>
2. <span data-ttu-id="16ca4-132">Ouvrez la fiche client d'un client pouvant faire l'objet de remises facture.</span><span class="sxs-lookup"><span data-stu-id="16ca4-132">Open the customer card for a customer that will be eligible for invoice discounts.</span></span>
3. <span data-ttu-id="16ca4-133">Dans le champ **Code remise facture**, sélectionnez un code pour les conditions de remise facture appropriées à utiliser pour calculer les remises facture pour le client.</span><span class="sxs-lookup"><span data-stu-id="16ca4-133">In the **Invoice Disc. Code** field, select a code for the relevant invoice discount terms to use to calculate invoice discounts for the customer.</span></span>

    > [!NOTE]  
>   <span data-ttu-id="16ca4-134">Les codes escompte facture sont représentés par les fiches client existantes.</span><span class="sxs-lookup"><span data-stu-id="16ca4-134">Invoice discount codes are represented by existing customer cards.</span></span> <span data-ttu-id="16ca4-135">Cela vous permet d'affecter rapidement les conditions d'escompte facture aux clients en sélectionnant le nom d'autres clients qui bénéficient des mêmes conditions.</span><span class="sxs-lookup"><span data-stu-id="16ca4-135">This enables you to quickly assign invoice discount terms to customers by picking the name of another customer who will have the same terms.</span></span>

    <span data-ttu-id="16ca4-136">Configurez de nouvelles conditions d'escompte facture pour les ventes.</span><span class="sxs-lookup"><span data-stu-id="16ca4-136">Proceed to set up new the sales invoice discount terms.</span></span>
4. <span data-ttu-id="16ca4-137">Dans la fenêtre **Fiche client**, sélectionnez l'action **Remises facture**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-137">In the **Customer Card** window, choose the **Invoice Discounts** action.</span></span> <span data-ttu-id="16ca4-138">La fenêtre **Remises facture client** s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="16ca4-138">The **Cust. Invoice Discounts** window opens.</span></span>
5. <span data-ttu-id="16ca4-139">Dans le champ **Code devise**, indiquez le code d'une devise à laquelle s'appliquent les conditions de remise facture.</span><span class="sxs-lookup"><span data-stu-id="16ca4-139">In the **Currency Code** field, enter the code for a currency that the invoice discount terms on the line applies to.</span></span> <span data-ttu-id="16ca4-140">Laissez le champ vierge si vous souhaitez configurer des conditions d'escompte facture en USD.</span><span class="sxs-lookup"><span data-stu-id="16ca4-140">Leave the field blank to set up invoice discount terms in USD.</span></span>
6. <span data-ttu-id="16ca4-141">Dans le champ **Montant minimum**, entrez le montant minimal qu'une facture doit présenter pour faire l'objet de la remise.</span><span class="sxs-lookup"><span data-stu-id="16ca4-141">In the **Minimum Amount** field, enter the minimum amount that an invoice must have to be eligible for the discount.</span></span>
7. <span data-ttu-id="16ca4-142">Dans le champ **% remise**, entrez la remise facture sous la forme d'un pourcentage du montant de la facture.</span><span class="sxs-lookup"><span data-stu-id="16ca4-142">In the **Discount %** field, enter the invoice discount as a percentage of the invoice amount.</span></span>
8. <span data-ttu-id="16ca4-143">Répétez les étapes 5 à 7 pour chaque devise pour laquelle le client recevra un escompte facture différent.</span><span class="sxs-lookup"><span data-stu-id="16ca4-143">Repeat steps 5 through 7 for each currency that the customer will receive a different invoice discount for.</span></span>

<span data-ttu-id="16ca4-144">L'escompte facture est désormais configuré et affecté au client concerné.</span><span class="sxs-lookup"><span data-stu-id="16ca4-144">The invoice discount is now set up and assigned to the customer in question.</span></span> <span data-ttu-id="16ca4-145">Lorsque vous sélectionnez le code client dans le champ **Code remise facture** dans d'autres fiches client, la même remise facture est affecté à ces clients.</span><span class="sxs-lookup"><span data-stu-id="16ca4-145">When you select the customer code in the **Invoice Disc. Code** field on other customer cards, the same invoice discount is assigned to those customers.</span></span>

## <a name="to-work-with-sales-invoice-discounts-and-service-charges"></a><span data-ttu-id="16ca4-146">Utiliser des escomptes facture vente et des frais forfaitaires</span><span class="sxs-lookup"><span data-stu-id="16ca4-146">To work with sales invoice discounts and service charges</span></span>
<span data-ttu-id="16ca4-147">Lorsque vous utilisez des escomptes de facture, la valeur du montant de la facture détermine celle de l'escompte accordé.</span><span class="sxs-lookup"><span data-stu-id="16ca4-147">When you use invoice discounts, the size of the invoice amount determines the size of the discount that is granted.</span></span>  

<span data-ttu-id="16ca4-148">Dans la fenêtre **Remises facture client**, vous pouvez également ajouter des frais forfaitaires aux factures supérieures à un montant donné.</span><span class="sxs-lookup"><span data-stu-id="16ca4-148">In the **Cust. Invoice Discounts** window, you can also add a service charge to invoices over a certain amount.</span></span>  

<span data-ttu-id="16ca4-149">Pour pouvoir utiliser les remises facture avec les ventes, vous devez saisir certaines informations dans le programme.</span><span class="sxs-lookup"><span data-stu-id="16ca4-149">Before you can use invoice discounts with sales, you must enter certain information in the program.</span></span> <span data-ttu-id="16ca4-150">Vous devez décider des éléments suivants</span><span class="sxs-lookup"><span data-stu-id="16ca4-150">You must decide:</span></span>  

- <span data-ttu-id="16ca4-151">les clients qui se verront accorder ce type d'escompte.</span><span class="sxs-lookup"><span data-stu-id="16ca4-151">which customers will be granted this type of discount.</span></span>  
- <span data-ttu-id="16ca4-152">les pourcentages d'escompte à utiliser.</span><span class="sxs-lookup"><span data-stu-id="16ca4-152">which discount percentages you will use.</span></span>  

<span data-ttu-id="16ca4-153">Dans la fenêtre **Paramètres ventes**, vous pouvez spécifier si les remises facture doivent être calculées automatiquement.</span><span class="sxs-lookup"><span data-stu-id="16ca4-153">If you invoice discounts to be calculated automatically, you can specify this in the **Sales & Receivables Setup** window.</span></span>  

<span data-ttu-id="16ca4-154">Pour chaque client, vous pouvez indiquer si vous accordez des remises facture si la condition est remplie (si le montant facture est suffisamment élevé).</span><span class="sxs-lookup"><span data-stu-id="16ca4-154">For each customer, you can specify whether you will grant invoice discounts if the requirement is satisfied (that is, if the invoice amount is large enough).</span></span> <span data-ttu-id="16ca4-155">Vous pouvez définir les conditions pour l'escompte facture en devise locale pour les clients nationaux et en devise étrangère pour les clients étrangers.</span><span class="sxs-lookup"><span data-stu-id="16ca4-155">You can define the terms of the invoice discount in local currency for domestic customers and in foreign currency for foreign customers.</span></span>  

<span data-ttu-id="16ca4-156">Vous liez les pourcentages de remise à des montants de facture spécifiques dans les fenêtres **Remises facture client**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-156">You link discount percentages to specific invoice amounts in **Cust. Invoice Discounts** windows.</span></span> <span data-ttu-id="16ca4-157">Vous pouvez entrer le nombre de pourcentages de votre choix dans chaque fenêtre.</span><span class="sxs-lookup"><span data-stu-id="16ca4-157">You can enter any number of percentages in each window.</span></span> <span data-ttu-id="16ca4-158">Chaque client peut avoir sa propre fenêtre, ou vous pouvez lier plusieurs clients à la même fenêtre.</span><span class="sxs-lookup"><span data-stu-id="16ca4-158">Each customer can have its own window, or you can link several customers to the same window.</span></span>  

<span data-ttu-id="16ca4-159">En plus du pourcentage d'escompte (ou à sa place), vous pouvez lier un montant de frais forfaitaires au montant d'une facture.</span><span class="sxs-lookup"><span data-stu-id="16ca4-159">In addition to (or instead of) a discount percentage, you can link a service charge amount to a specific invoice amount.</span></span>  

> [!TIP]  
>  <span data-ttu-id="16ca4-160">Avant de saisir ces informations dans le programme, il est conseillé de préparer la structure de l'escompte de paiement que vous souhaitez utiliser.</span><span class="sxs-lookup"><span data-stu-id="16ca4-160">Before you start entering this information in the program, it is a good idea to prepare an outline of the discount structure you want to use.</span></span> <span data-ttu-id="16ca4-161">Ainsi, vous pouvez visualiser plus facilement les clients pouvant être liés à la même fenêtre d'escompte de paiement facture.</span><span class="sxs-lookup"><span data-stu-id="16ca4-161">This makes it easier to see which customers can be linked to the same invoice discount window.</span></span> <span data-ttu-id="16ca4-162">Plus le nombre de fenêtres à configurer est faible, plus vous pouvez saisir rapidement les informations de base.</span><span class="sxs-lookup"><span data-stu-id="16ca4-162">The fewer windows you have to set up, the faster you can enter the basic information.</span></span>  

## <a name="best-price-calculation"></a><span data-ttu-id="16ca4-163">Calcul du meilleur prix</span><span class="sxs-lookup"><span data-stu-id="16ca4-163">Best Price Calculation</span></span>
<span data-ttu-id="16ca4-164">Lorsque vous avez enregistré des prix spéciaux et des remises de ligne pour les ventes et les achats, [!INCLUDE[d365fin](includes/d365fin_md.md)] s'assure que votre marge pour l'article est toujours optimale en calculant automatiquement le meilleur prix dans les documents achat et vente, sur le projet et les lignes feuille article.</span><span class="sxs-lookup"><span data-stu-id="16ca4-164">When you have recorded special prices and line discounts for sales and purchases, [!INCLUDE[d365fin](includes/d365fin_md.md)] ensures that your profit on item trade is always optimal by automatically calculating the best price on sales and purchase documents and on job and item journal lines.</span></span>

<span data-ttu-id="16ca4-165">Le meilleur prix est le prix le plus bas autorisé associé à l'escompte ligne le plus élevé autorisé à une date donnée.</span><span class="sxs-lookup"><span data-stu-id="16ca4-165">The best price is the lowest permissible price with the highest permissible line discount on a given date.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="16ca4-166"> calcule automatiquement cette valeur lorsqu'il insère le prix unitaire et le pourcentage de remise de ligne pour des articles dans le nouveau document et les lignes feuille.</span><span class="sxs-lookup"><span data-stu-id="16ca4-166"> automatically calculates this when it inserts the unit price and the line discount percentage for items on new document and journal lines.</span></span>

> [!NOTE]  
>   <span data-ttu-id="16ca4-167">Voici une description du calcul du meilleur prix pour la vente.</span><span class="sxs-lookup"><span data-stu-id="16ca4-167">The following describes how the best price is calculated for sales.</span></span> <span data-ttu-id="16ca4-168">Le calcul est le même pour les achats.</span><span class="sxs-lookup"><span data-stu-id="16ca4-168">The calculation is the same for purchases.</span></span>

1. [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="16ca4-169"> vérifie la combinaison client facturé et article, et calcule le prix unitaire applicable et le pourcentage remise de ligne à l'aide des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="16ca4-169"> checks the combination of the bill-to customer and the item and then calculates the applicable unit price and line discount percentage, using the following criteria:</span></span>

    - <span data-ttu-id="16ca4-170">Ce client a-t-il une entente pour des prix ou des escomptes ou appartient-il à un groupe bénéficiant d'un telle entente?</span><span class="sxs-lookup"><span data-stu-id="16ca4-170">Does the customer have a price/discount agreement, or does the customer belong to a group that does?</span></span>
    - <span data-ttu-id="16ca4-171">L'article ou le groupe escompte article sur la ligne est-il inclus dans l'une ou l'autre de ces ententes prix/escompte?</span><span class="sxs-lookup"><span data-stu-id="16ca4-171">Is the item or the item discount group on the line included in any of these price/discount agreements?</span></span>
    - <span data-ttu-id="16ca4-172">La date de commande (ou la date de report pour la facture et la note de crédit) est-elle comprise entre les dates début et de fin de l'entente prix/escompte?</span><span class="sxs-lookup"><span data-stu-id="16ca4-172">Is the order date (or the posting date for the invoice and credit memo) within the starting and ending date of the price/discount agreement?</span></span>
    - <span data-ttu-id="16ca4-173">Un code unité de mesure est-il spécifié?</span><span class="sxs-lookup"><span data-stu-id="16ca4-173">Is a unit of measure code specified?</span></span> <span data-ttu-id="16ca4-174">Si c'est le cas, [!INCLUDE[d365fin](includes/d365fin_md.md)] recherche des prix/remises possédant le même code unité, et des prix/remises sans code unité.</span><span class="sxs-lookup"><span data-stu-id="16ca4-174">If so, [!INCLUDE[d365fin](includes/d365fin_md.md)] checks for prices/discounts with the same unit of measure code, and prices/discounts with no unit of measure code.</span></span>

2. [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="16ca4-175"> vérifie si des accords prix/remise s'appliquent à des informations sur le document ou la ligne feuille, puis insère le prix unitaire applicable et le pourcentage remise de ligne, à l'aide des critères suivants :</span><span class="sxs-lookup"><span data-stu-id="16ca4-175"> checks if any price/discount agreements apply to information on the document or journal line, and then inserts the applicable unit price and line discount percentage, using the following criteria:</span></span>

    - <span data-ttu-id="16ca4-176">Existe-t-il une quantité minimum à respecter dans l'entente de prix/escompte?</span><span class="sxs-lookup"><span data-stu-id="16ca4-176">Is there a minimum quantity requirement in the price/discount agreement that is fulfilled?</span></span>
    - <span data-ttu-id="16ca4-177">Existe-t-il une exigence en matière de devise à respecter dans l'entente de prix/escompte?</span><span class="sxs-lookup"><span data-stu-id="16ca4-177">Is there a currency requirement in the price/discount agreement that is fulfilled?</span></span> <span data-ttu-id="16ca4-178">Si c'est le cas, le prix le plus bas et l'escompte ligne le plus élevé pour cette devise sont insérés, même si la devise locale permettrait d'offrir un meilleur prix.</span><span class="sxs-lookup"><span data-stu-id="16ca4-178">If so, the lowest price and the highest line discount for that currency are inserted, even if local currency would provide a better price.</span></span> <span data-ttu-id="16ca4-179">S'il n'existe aucune entente de prix/escompte pour le code devise indiqué, [!INCLUDE[d365fin](includes/d365fin_md.md)] insère le prix le plus bas et l'escompte de ligne le plus élevé dans votre devise locale.</span><span class="sxs-lookup"><span data-stu-id="16ca4-179">If there is no price/discount agreement for the specified currency code, [!INCLUDE[d365fin](includes/d365fin_md.md)] inserts the lowest price and the highest line discount in your local currency.</span></span>

<span data-ttu-id="16ca4-180">Si aucun prix spécial ne peut être calculé pour l'article de la ligne, alors soit le coût unitaire direct, soit le prix unitaire à partir de la fiche article est inséré.</span><span class="sxs-lookup"><span data-stu-id="16ca4-180">If no special price can be calculated for the item on the line, then either the last direct cost or the unit price from the item card is inserted.</span></span>

## <a name="to-copy-sales-prices"></a><span data-ttu-id="16ca4-181">Pour copier des prix de vente</span><span class="sxs-lookup"><span data-stu-id="16ca4-181">To copy sales prices</span></span>  
<span data-ttu-id="16ca4-182">Pour copier des prix de vente, comme les prix appliqués à un client et qui doivent être appliqués à tout un groupe de clients, vous devez lancer le traitement par lots **Suggérer prix vente**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-182">If you want to copy sales prices, such as an individual customer's sales prices to use for a customer price group, you must run the **Suggest Sales Price on Wksh.**</span></span> <span data-ttu-id="16ca4-183">traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="16ca4-183">batch job.</span></span> <span data-ttu-id="16ca4-184">Ce traitement est accessible dans la fenêtre **Feuille prix vente**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-184">You find the batch job in the **Sales Price Worksheet** window.</span></span>    

1.  <span data-ttu-id="16ca4-185">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille prix vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="16ca4-185">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Price Worksheet**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="16ca4-186">Sélectionnez l'action **Suggérer prix vente**</span><span class="sxs-lookup"><span data-stu-id="16ca4-186">Choose the **Suggest Sales Price on Wksh.**</span></span> <span data-ttu-id="16ca4-187"> </span><span class="sxs-lookup"><span data-stu-id="16ca4-187">action.</span></span>  
3.  <span data-ttu-id="16ca4-188">Sur le raccourci **Prix vente**, renseignez les champs **Type vente** et **Code vente** avec les prix de vente d'origine à copier.</span><span class="sxs-lookup"><span data-stu-id="16ca4-188">On the **Sales Prices** FastTab, fill in the **Sales Type** and **Sales Code** fields with the original sales prices you want to copy.</span></span>  
4.  <span data-ttu-id="16ca4-189">Dans la partie supérieure du formulaire de sélection, indiquez dans les champs **Type vente** et **Code vente** le type et le nom sous lesquels vous souhaitez copier les prix de vente.</span><span class="sxs-lookup"><span data-stu-id="16ca4-189">In the top section of the request window, fill in the **Sales Type** and **Sales Code** with the type and name you want the sales prices copied to.</span></span>  
5.  <span data-ttu-id="16ca4-190">Pour que le traitement par lots crée des prix, sélectionnez le champ **Créer nouveaux prix**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-190">If you want the batch job to create new prices, select the **Create New Prices** field.</span></span>  
6.  <span data-ttu-id="16ca4-191">Choisissez le bouton **OK** pour renseigner les lignes de la fenêtre **Feuille prix vente** avec les nouveaux prix proposés, en précisant qu'ils sont applicables au **type ventes** sélectionné.</span><span class="sxs-lookup"><span data-stu-id="16ca4-191">Choose the **OK** button to fill in the lines on the **Sales Price Worksheet** window with the suggested new prices, indicating that they are valid for the selected **Sales Type**.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="16ca4-192">Ce traitement en lot crée uniquement des propositions ; il n'effectue pas les modifications proposées.</span><span class="sxs-lookup"><span data-stu-id="16ca4-192">This batch job only creates suggestions and it does not implement the suggested changes.</span></span> <span data-ttu-id="16ca4-193">Si les propositions vous conviennent et que vous souhaitez les appliquer, c'est-à-dire les insérer dans la table **Prix vente**, vous pouvez utiliser le traitement par lots **Implémenter nouveaux prix**, accessible via l'onglet **Actions**, dans le groupe **Fonctions**, dans la fenêtre **Feuille prix vente**.</span><span class="sxs-lookup"><span data-stu-id="16ca4-193">If you are satisfied with the suggestions and want to implement them, that is insert them in the **Sales Prices** table, you can use the **Implement Price Changes** batch job, which is found on the **Actions** tab, in the **Functions** group, in the **Sales Price Worksheet** window.</span></span>

## <a name="see-also"></a><span data-ttu-id="16ca4-194">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="16ca4-194">See Also</span></span>
[<span data-ttu-id="16ca4-195">Définition des ventes</span><span class="sxs-lookup"><span data-stu-id="16ca4-195">Setting Up Sales</span></span>](sales-setup-sales.md)  
[<span data-ttu-id="16ca4-196">Vente</span><span class="sxs-lookup"><span data-stu-id="16ca4-196">Sales</span></span>](sales-manage-sales.md)  
<span data-ttu-id="16ca4-197">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="16ca4-197">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
