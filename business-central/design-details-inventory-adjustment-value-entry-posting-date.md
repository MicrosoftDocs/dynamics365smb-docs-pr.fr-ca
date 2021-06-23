---
title: Date de report des écritures valeur
description: Découvrez comment le traitement en lot Ajuster coûts - Écr. article identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: 918a450ea40676447f872ba95eb489c7cc210211
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6215113"
---
# <a name="design-details-posting-date-on-adjustment-value-entry"></a><span data-ttu-id="531fa-103">Détails de conception : date de report de l'écriture valeur d'ajustement</span><span class="sxs-lookup"><span data-stu-id="531fa-103">Design Details: Posting Date on Adjustment Value Entry</span></span>
<span data-ttu-id="531fa-104">Cet article fournit des instructions aux utilisateurs de la fonctionnalité Évaluation stock dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="531fa-104">This article provides guidance for users of the Inventory Costing functionality in [!INCLUDE[prod_short](includes/prod_short.md)].</span></span> <span data-ttu-id="531fa-105">L'article spécifique donne des informations sur la façon dont le traitement en lot **Ajuster coûts - Écr. article** identifie et affecte une date de report aux écritures valeur que le traitement en lot est sur le point de créer.</span><span class="sxs-lookup"><span data-stu-id="531fa-105">The specific article is providing guidance in how the **Adjust Cost - Item Entries** batch job identifies and assigns a posting date to the value entries that the batch job is about to create.</span></span>  

<span data-ttu-id="531fa-106">Tout d'abord, le concept du processus est passé en revue, c'est-à-dire la manière dont le traitement en lot identifie et affecte la date de report à l'écriture valeur à créer.</span><span class="sxs-lookup"><span data-stu-id="531fa-106">First the concept of the process is reviewed, how the batch job identifies and assigns the Posting Date to the Value Entry to be created.</span></span> <span data-ttu-id="531fa-107">Ensuite, des scénarios communs que l’équipe de support rencontre parfois sont décrits. Enfin, les concepts utilisés sont résumés.</span><span class="sxs-lookup"><span data-stu-id="531fa-107">Thereafter there are some scenarios shared that we in the support team come across from time to time and finally there is a summary of the concepts used.</span></span>  

## <a name="the-concept"></a><span data-ttu-id="531fa-108">Le concept</span><span class="sxs-lookup"><span data-stu-id="531fa-108">The Concept</span></span>  
<span data-ttu-id="531fa-109">Le traitement en lot **Ajuster coûts - Écr. article** affecte une date de report à l’écriture valeur qu’il est sur le point de créer dans les étapes suivantes :</span><span class="sxs-lookup"><span data-stu-id="531fa-109">The **Adjust Cost – Item Entries** batch job assigns a posting date to the value entry it is about to create in the following steps:</span></span>  

1.  <span data-ttu-id="531fa-110">Initialement, la date de report de l'écriture à créer est la même que celle de l'écriture qu'elle ajuste.</span><span class="sxs-lookup"><span data-stu-id="531fa-110">Initially the Posting Date of the entry to be created is the same date as the entry it adjusts.</span></span>  

2.  <span data-ttu-id="531fa-111">La date de report est validée par rapport aux périodes d'inventaire et/ou à la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-111">The Posting Date is validated against Inventory Periods and/or General Ledger Setup.</span></span>  

3.  <span data-ttu-id="531fa-112">Affectation d'une date de report : si la date de report initiale n'est pas comprise dans la plage de dates de report autorisées, le traitement en lot affecte une date de report autorisée à partir de la Configuration du grand livre ou de la Période d'inventaire.</span><span class="sxs-lookup"><span data-stu-id="531fa-112">Assignment of Posting Date; If the initial Posting Date is not within allowed posting date range the batch job will assign an allowed Posting Date from either General Ledger Setup or Inventory Period.</span></span> <span data-ttu-id="531fa-113">Si les périodes d'inventaire et les dates de report autorisées dans la configuration du grand livre sont définies, la date la plus récente des deux est affectée à l'écriture valeur d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="531fa-113">If both Inventory Periods and allowed posting dates in General Ledger Setup are defined, the later date of the two will be assigned to the Adjustment Value Entry.</span></span>  

 <span data-ttu-id="531fa-114">Examinons ce processus plus en détail.</span><span class="sxs-lookup"><span data-stu-id="531fa-114">Let’s review this process more in practice.</span></span> <span data-ttu-id="531fa-115">Supposons que nous avons une écriture article de type Vente.</span><span class="sxs-lookup"><span data-stu-id="531fa-115">Assume we have an Item Ledger Entry of Sale.</span></span> <span data-ttu-id="531fa-116">L’article a été livré le 5 septembre 2013 et il a été facturé le jour suivant.</span><span class="sxs-lookup"><span data-stu-id="531fa-116">The item was shipped on September 5, 2013 and it was invoiced the day after.</span></span>  

<span data-ttu-id="531fa-117">![Province des écritures article dans le scénario](media/helene/TechArticleAdjustcost1.png "Province des écritures article dans le scénario")</span><span class="sxs-lookup"><span data-stu-id="531fa-117">![State of item ledger entries in the scenario](media/helene/TechArticleAdjustcost1.png "State of item ledger entries in the scenario")</span></span>  

<span data-ttu-id="531fa-118">La première écriture valeur (379) représente la livraison et utilise la même date de report que l'écriture article parent.</span><span class="sxs-lookup"><span data-stu-id="531fa-118">Below, the first Value Entry (379) represents the shipment and carry the same Posting Date as the parent Item ledger Entry.</span></span>  

<span data-ttu-id="531fa-119">La deuxième écriture valeur (381) représente la facture.</span><span class="sxs-lookup"><span data-stu-id="531fa-119">The second Value Entry (381) represents the invoice.</span></span>  

 <span data-ttu-id="531fa-120">La troisième écriture valeur (391) est un ajustement de l'écriture valeur de facturation (381)</span><span class="sxs-lookup"><span data-stu-id="531fa-120">The third Value Entry (391) is an Adjustment of the invoicing Value Entry (381)</span></span>  

 <span data-ttu-id="531fa-121">![Province des écritures valeur dans le scénario](media/helene/TechArticleAdjustcost2.png "Province des écritures valeur dans le scénario")</span><span class="sxs-lookup"><span data-stu-id="531fa-121">![State of value entries in the scenario](media/helene/TechArticleAdjustcost2.png "State of value entries in the scenario")</span></span>  

 <span data-ttu-id="531fa-122">Étape 1 : l'écriture valeur d'ajustement à créer a la même date de report que l'écriture qu'elle ajuste, comme illustré ci-dessus par l'écriture valeur 391.</span><span class="sxs-lookup"><span data-stu-id="531fa-122">Step 1: Adjustment Value Entry to be created is assigned same Posting Date as the entry it adjusts, illustrated above by Value entry 391.</span></span>  

 <span data-ttu-id="531fa-123">Étape 2 : validation de la date de report affectée initiale.</span><span class="sxs-lookup"><span data-stu-id="531fa-123">Step 2: Validation of initial assigned Posting Date.</span></span>  

<span data-ttu-id="531fa-124">Le traitement en lot **Ajuster coûts - Écr. article** détermine si la date de report initiale de l'écriture valeur d'ajustement est comprise dans la plage de dates de report autorisées en fonction des périodes d'inventaire et/ou de la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-124">The **Adjust Cost – Item Entries** batch job determines if the initial Posting Date of the Adjustment Value Entry is within allowed posting date range based upon Inventory Periods and/or General Ledger Setup.</span></span>  

 <span data-ttu-id="531fa-125">Examinons la vente mentionnée ci-dessus en ajoutant la configuration des plages de dates de report autorisées.</span><span class="sxs-lookup"><span data-stu-id="531fa-125">Let’s review the above mentioned Sale by adding setup of allowed posting date ranges.</span></span>  

 <span data-ttu-id="531fa-126">Périodes d'inventaire :</span><span class="sxs-lookup"><span data-stu-id="531fa-126">Inventory Periods:</span></span>  

<span data-ttu-id="531fa-127">![Périodes d'inventaire dans le scénario](media/helene/TechArticleAdjustcost3.png "Périodes d'inventaire dans le scénario")</span><span class="sxs-lookup"><span data-stu-id="531fa-127">![Inventory periods in the scenario](media/helene/TechArticleAdjustcost3.png "Inventory periods in the scenario")</span></span>

 <span data-ttu-id="531fa-128">La première date de report autorisée est le premier jour de la première période ouverte.</span><span class="sxs-lookup"><span data-stu-id="531fa-128">First allowed posting date is the first day in the first open period.</span></span> <span data-ttu-id="531fa-129">1 septembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-129">September 1, 2013.</span></span>  

 <span data-ttu-id="531fa-130">Configuration du grand livre :</span><span class="sxs-lookup"><span data-stu-id="531fa-130">General Ledger Setup:</span></span>  

<span data-ttu-id="531fa-131">![Configuration grand livre dans le scénario](media/helene/TechArticleAdjustcost4.png "Configuration grand livre dans le scénario")</span><span class="sxs-lookup"><span data-stu-id="531fa-131">![G/L Setup in the scenario](media/helene/TechArticleAdjustcost4.png "G/L Setup in the scenario")</span></span>

 <span data-ttu-id="531fa-132">La première date de report autorisée est la date indiquée dans le champ Début période report : 10 septembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-132">First allowed posting date is the date stated in field Allow Posting From: September 10, 2013.</span></span>  

 <span data-ttu-id="531fa-133">Si les périodes d'inventaire et les dates de report autorisées dans la configuration du grand livre sont définies, la date la plus récente des deux définit la plage de dates de report autorisées.</span><span class="sxs-lookup"><span data-stu-id="531fa-133">If both Inventory Periods and allowed posting dates in General Ledger Setup are defined, the later date of the two will define the allowed posting date range.</span></span>  

 <span data-ttu-id="531fa-134">Étape 3 : affectation d'une date de report autorisée.</span><span class="sxs-lookup"><span data-stu-id="531fa-134">Step 3: Assignment of an allowed posting date;</span></span>  

 <span data-ttu-id="531fa-135">La date de report initiale était le 6 septembre, comme illustré à l’étape 1.</span><span class="sxs-lookup"><span data-stu-id="531fa-135">The initial assigned Posting Date was September 6 as illustrated in step 1.</span></span> <span data-ttu-id="531fa-136">Toutefois, dans la 2e étape, le traitement en lot Ajuster coûts - Écr. article identifie que la date de report autorisée la plus proche est le 10 septembre et affecte donc le 10 septembre à l'écriture valeur d'ajustement ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="531fa-136">However, in the second step the Adjust Cost – Item entries batch job identifies that earliest allowed Posting Date is September 10 and thereby assigns September 10 to the Adjustment Value Entry, below.</span></span>  

 <span data-ttu-id="531fa-137">![Province des écritures valeur dans le scénario 2](media/helene/TechArticleAdjustcost5.png "Province des écritures valeur dans le scénario 2")</span><span class="sxs-lookup"><span data-stu-id="531fa-137">![State of value entries in the scenario 2](media/helene/TechArticleAdjustcost5.png "State of value entries in the scenario 2")</span></span>

 <span data-ttu-id="531fa-138">Nous avons passé en revue le concept d'affectation de dates de report aux écritures valeur créées par le traitement en lot Ajuster coûts - Écr. article.</span><span class="sxs-lookup"><span data-stu-id="531fa-138">We have now reviewed the concept for assigning Posting Dates to Value Entries created by the Adjust Cost - Item entries batch job.</span></span>  

 <span data-ttu-id="531fa-139">Examinons maintenant certains scénarios que l'équipe de support rencontre parfois pour les dates de report affectées dans le traitement en lot Ajuster coûts – Écr article et les configurations associées.</span><span class="sxs-lookup"><span data-stu-id="531fa-139">Let’s continue to review some scenarios that we in the support team comes across from time to time in relation to assigned Posting Dates in the Adjust Cost – Item entries batch job and related setups.</span></span>  

## <a name="scenarios"></a><span data-ttu-id="531fa-140">Cas de figure</span><span class="sxs-lookup"><span data-stu-id="531fa-140">Scenarios</span></span>  

### <a name="scenario-i-posting-date-is-not-within-your-range-of-allowed-posting-dates"></a><span data-ttu-id="531fa-141">Scénario I : « La date de report n'est pas incluse dans la plage de dates de report autorisées... »</span><span class="sxs-lookup"><span data-stu-id="531fa-141">Scenario I: “Posting Date is not within your range of allowed posting dates…”</span></span>  
 <span data-ttu-id="531fa-142">Dans ce scénario, l'utilisateur reçoit le message d'erreur indiqué lorsque le traitement en lot Ajuster coûts – Écr article est exécuté.</span><span class="sxs-lookup"><span data-stu-id="531fa-142">This is a scenario where a user is experiencing mentioned error message when the Adjust Cost – Item entries batch job is run.</span></span>  

 <span data-ttu-id="531fa-143">Dans la section précédente qui décrit le concept d'affectation de dates de report, l'intention du traitement en lot Ajuster coûts – Écr article est de créer une écriture valeur avec la date de report du 10 septembre.</span><span class="sxs-lookup"><span data-stu-id="531fa-143">In the previous section, describing the concept of assigning posting dates, the intention of the Adjust Cost – Item entries batch job is to create a Value Entry with Posting Date September 10th.</span></span>  

<span data-ttu-id="531fa-144">![Message d'erreur sur la date de report](media/helene/TechArticleAdjustcost6.png "Message d'erreur sur la date de report")</span><span class="sxs-lookup"><span data-stu-id="531fa-144">![Error message about posting date](media/helene/TechArticleAdjustcost6.png "Error message about posting date")</span></span>

 <span data-ttu-id="531fa-145">Nous passons à la configuration des utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="531fa-145">We follow up on the User Setup:</span></span>  

<span data-ttu-id="531fa-146">![Configuration des dates de report autorisées de l'utilisateur](media/helene/TechArticleAdjustcost7.png "Configuration des dates de report autorisées de l'utilisateur")</span><span class="sxs-lookup"><span data-stu-id="531fa-146">![User's allowed posting dates setup](media/helene/TechArticleAdjustcost7.png "User's allowed posting dates setup")</span></span>

 <span data-ttu-id="531fa-147">L'utilisateur dans ce cas a une plage de dates de report autorisées allant du 11 au 30 septembre et n'est donc pas autorisé à reporter l'écriture valeur d'ajustement avec la date de report du 10 septembre.</span><span class="sxs-lookup"><span data-stu-id="531fa-147">The user in this case has an allowed posting date range from September 11 to September 30 and is thereby not allowed to post the Adjustment Value Entry with Posting Date September 10th.</span></span>  

<span data-ttu-id="531fa-148">![Aperçu de la configuration de la date de report impliquée](media/helene/TechArticleAdjustcost8.png "Aperçu de la configuration de la date de report impliquée")</span><span class="sxs-lookup"><span data-stu-id="531fa-148">![Overview of involved posting date setup](media/helene/TechArticleAdjustcost8.png "Overview of involved posting date setup")</span></span>

 <span data-ttu-id="531fa-149">L’article de la Base de connaissances [952996](https://mbs2.microsoft.com/Knowledgebase/kbdisplay.aspx?WTNTZSMNWUKNTMMYXUPYZQPOUXNXSPSYOQQYYMLUQLOYYMWP) décrit des scénarios supplémentaires associés au message d’erreur indiqué.</span><span class="sxs-lookup"><span data-stu-id="531fa-149">Knowledge Base article [952996](https://mbs2.microsoft.com/Knowledgebase/kbdisplay.aspx?WTNTZSMNWUKNTMMYXUPYZQPOUXNXSPSYOQQYYMLUQLOYYMWP) discusses more scenarios related to mentioned error message.</span></span>  

### <a name="scenario-ii-posting-date-on-adjustment-value-entry-versus-posting-date-on-entry-causing-the-adjustment-such-as-revaluation-or-item-charge"></a><span data-ttu-id="531fa-150">Scénario II : comparaison entre la date de report de l'écriture valeur d'ajustement et la date de report de l'écriture à l'origine de l'ajustement, comme une réévaluation ou des frais annexes.</span><span class="sxs-lookup"><span data-stu-id="531fa-150">Scenario II: Posting Date on Adjustment Value Entry versus Posting Date on entry causing the adjustment such as Revaluation or Item charge.</span></span>  

### <a name="revaluation-scenario"></a><span data-ttu-id="531fa-151">Scénario de réévaluation :</span><span class="sxs-lookup"><span data-stu-id="531fa-151">Revaluation scenario:</span></span>  
 <span data-ttu-id="531fa-152">Conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="531fa-152">Prerequisites:</span></span>  

 <span data-ttu-id="531fa-153">Configuration de l'inventaire :</span><span class="sxs-lookup"><span data-stu-id="531fa-153">Inventory setup:</span></span>  

-   <span data-ttu-id="531fa-154">Report coûts automatique = Oui</span><span class="sxs-lookup"><span data-stu-id="531fa-154">Automatic Cost Posting = Yes</span></span>  

-   <span data-ttu-id="531fa-155">Ajustement automatique des coûts = Toujours</span><span class="sxs-lookup"><span data-stu-id="531fa-155">Automatic Cost Adjustment=Always</span></span>  

-   <span data-ttu-id="531fa-156">Type calcul coût moyen = Article</span><span class="sxs-lookup"><span data-stu-id="531fa-156">Average Cost Calc. Type=item</span></span>  

-   <span data-ttu-id="531fa-157">Période coût moyen = Jour</span><span class="sxs-lookup"><span data-stu-id="531fa-157">Average Cost Period=Day</span></span>  

 <span data-ttu-id="531fa-158">Configuration du grand livre :</span><span class="sxs-lookup"><span data-stu-id="531fa-158">General Ledger Setup:</span></span>  

-   <span data-ttu-id="531fa-159">Début période report = 1er janvier 2014</span><span class="sxs-lookup"><span data-stu-id="531fa-159">Allow Posting From = January 1, 2014</span></span>  

-   <span data-ttu-id="531fa-160">Fin période report = Vide</span><span class="sxs-lookup"><span data-stu-id="531fa-160">Allow Posting To = empty</span></span>  

 <span data-ttu-id="531fa-161">Configuration des utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="531fa-161">User Setup:</span></span>  

-   <span data-ttu-id="531fa-162">Début période report = 1er décembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-162">Allow Posting From = December 1, 2013.</span></span>  

-   <span data-ttu-id="531fa-163">Fin période report = Vide</span><span class="sxs-lookup"><span data-stu-id="531fa-163">Allow Posting to = empty</span></span>  

##### <a name="to-test-the-scenario"></a><span data-ttu-id="531fa-164">Pour tester le scénario</span><span class="sxs-lookup"><span data-stu-id="531fa-164">To test the scenario</span></span>  

1.  <span data-ttu-id="531fa-165">Créez un article TEST :</span><span class="sxs-lookup"><span data-stu-id="531fa-165">Create item TEST:</span></span>  

     <span data-ttu-id="531fa-166">Unité de mesure de base = PCS</span><span class="sxs-lookup"><span data-stu-id="531fa-166">Base unit of measure = PCS</span></span>  

     <span data-ttu-id="531fa-167">Mode évaluation stock = Moyen</span><span class="sxs-lookup"><span data-stu-id="531fa-167">Costing Method = Average</span></span>  

     <span data-ttu-id="531fa-168">Sélectionnez des groupes de report facultatifs.</span><span class="sxs-lookup"><span data-stu-id="531fa-168">Select optional posting groups.</span></span>  

2.  <span data-ttu-id="531fa-169">Ouvrez le journal article, puis créez et reportez une ligne comme suit :</span><span class="sxs-lookup"><span data-stu-id="531fa-169">Open Item Journal, create, and post a line as follows:</span></span>  

     <span data-ttu-id="531fa-170">Date de report = 15 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-170">Posting Date = December 15, 2013</span></span>  

     <span data-ttu-id="531fa-171">Article = TEST</span><span class="sxs-lookup"><span data-stu-id="531fa-171">Item = TEST</span></span>  

     <span data-ttu-id="531fa-172">Type écriture = Achat</span><span class="sxs-lookup"><span data-stu-id="531fa-172">Entry Type = Purchase</span></span>  

     <span data-ttu-id="531fa-173">Quantité = 100</span><span class="sxs-lookup"><span data-stu-id="531fa-173">Quantity = 100</span></span>  

     <span data-ttu-id="531fa-174">Montant unitaire = 10</span><span class="sxs-lookup"><span data-stu-id="531fa-174">Unit Amount = 10</span></span>  

3.  <span data-ttu-id="531fa-175">Ouvrez le journal article, puis créez et reportez une ligne comme suit :</span><span class="sxs-lookup"><span data-stu-id="531fa-175">Open Item Journal, create, and post a line as follows:</span></span>  

     <span data-ttu-id="531fa-176">Date = 20 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-176">Date = December 20, 2013</span></span>  

     <span data-ttu-id="531fa-177">Article = TEST</span><span class="sxs-lookup"><span data-stu-id="531fa-177">Item = TEST</span></span>  

     <span data-ttu-id="531fa-178">Type écriture = Ajustement négatif</span><span class="sxs-lookup"><span data-stu-id="531fa-178">Entry Type = Negative Adjustment</span></span>  

     <span data-ttu-id="531fa-179">Quantité = 2</span><span class="sxs-lookup"><span data-stu-id="531fa-179">Quantity = 2</span></span>  

4.  <span data-ttu-id="531fa-180">Ouvrez le journal article, puis créez et reportez une ligne comme suit :</span><span class="sxs-lookup"><span data-stu-id="531fa-180">Open Item Journal, create, and post a line as follows:</span></span>  

     <span data-ttu-id="531fa-181">Date = 15 janvier 2014</span><span class="sxs-lookup"><span data-stu-id="531fa-181">Date = January 15, 2014</span></span>  

     <span data-ttu-id="531fa-182">Article = TEST</span><span class="sxs-lookup"><span data-stu-id="531fa-182">Item = TEST</span></span>  

     <span data-ttu-id="531fa-183">Type écriture = Ajustement négatif</span><span class="sxs-lookup"><span data-stu-id="531fa-183">Entry Type = Negative Adjustment</span></span>  

     <span data-ttu-id="531fa-184">Quantité = 3</span><span class="sxs-lookup"><span data-stu-id="531fa-184">Quantity = 3</span></span>  

5.  <span data-ttu-id="531fa-185">Ouvrez le journal réévaluation, puis créez et reportez une ligne comme suit :</span><span class="sxs-lookup"><span data-stu-id="531fa-185">Open Revaluation Journal, create, and post a line as follows:</span></span>  

     <span data-ttu-id="531fa-186">Article = TEST</span><span class="sxs-lookup"><span data-stu-id="531fa-186">Item = TEST</span></span>  

     <span data-ttu-id="531fa-187">Écriture référence = Sélectionnez l'écriture achat reportée à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="531fa-187">Applies-to Entry = select Purchase entry posted at step 2.</span></span> <span data-ttu-id="531fa-188">La date de report de la réévaluation est identique à l'écriture qu'elle ajuste.</span><span class="sxs-lookup"><span data-stu-id="531fa-188">The Posting Date of the revaluation will be the same as the entry it adjusts.</span></span>  

     <span data-ttu-id="531fa-189">Coût unitaire réévalué = 40</span><span class="sxs-lookup"><span data-stu-id="531fa-189">Unit Cost Revalued = 40</span></span>  

 <span data-ttu-id="531fa-190">Les écritures article et les écritures valeur suivantes ont été reportées :</span><span class="sxs-lookup"><span data-stu-id="531fa-190">The following Item Ledger and Value Entries have been posted:</span></span>  

<span data-ttu-id="531fa-191">![Aperçu des écritures article et valeur article résultantes 1](media/helene/TechArticleAdjustcost9.png "Aperçu des écritures article et valeur article résultantes 1")</span><span class="sxs-lookup"><span data-stu-id="531fa-191">![Overview of resulting item ledger and value entries 1](media/helene/TechArticleAdjustcost9.png "Overview of resulting item ledger and value entries 1")</span></span>

 <span data-ttu-id="531fa-192">![Aperçu des écritures article et valeur article résultantes 2](media/helene/TechArticleAdjustcost10.png "Aperçu des écritures article et valeur article résultantes 2")</span><span class="sxs-lookup"><span data-stu-id="531fa-192">![Overview of resulting item ledger and value entries 2](media/helene/TechArticleAdjustcost10.png "Overview of resulting item ledger and value entries 2")</span></span>

 <span data-ttu-id="531fa-193">Le traitement en lot Ajuster coûts – Écr article a identifié une modification du coût et ajusté les ajustements négatifs.</span><span class="sxs-lookup"><span data-stu-id="531fa-193">The Adjust Cost – Item entries batch job has recognized a change in cost and adjusted the Negative Adjustments.</span></span>  

 <span data-ttu-id="531fa-194">**Révision des dates de report des écritures valeur d'ajustement créées :** la date de report autorisée la plus proche à laquelle le traitement en lot Ajuster coûts – Écr article doit faire référence est le 1er janvier 2014, comme indiqué dans la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-194">**Review of Posting Dates on created Adjustment Value Entries:** The earliest allowed Posting Date the Adjust Cost - Item Entries batch job has to relate to is January 1, 2014 as stated in the General Ledger Setup.</span></span>  

 <span data-ttu-id="531fa-195">**Ajustement négatif à l'étape 3 :** la date de report affectée est le 1er janvier, qui est fournie par la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-195">**Negative Adjustment in step 3:** assigned Posting Date is January 1, provided by General Ledger Setup.</span></span> <span data-ttu-id="531fa-196">La date de report de l'écriture valeur concernée par l'ajustement est le 20 décembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-196">The Posting Date of the Value Entry in scope for adjustment is December 20, 2013.</span></span> <span data-ttu-id="531fa-197">Selon la configuration du grand livre, la date n'est pas comprise dans la plage de dates de report autorisées.</span><span class="sxs-lookup"><span data-stu-id="531fa-197">According to General Ledger Setup, the date is not within allowed posting date range.</span></span> <span data-ttu-id="531fa-198">Par conséquent, la date de report indiquée dans le champ Début période report de la configuration du grand livre est affectée à l'écriture valeur d'ajustement.</span><span class="sxs-lookup"><span data-stu-id="531fa-198">Therefore the Posting Date stated in the Allow Posting From field in the General Ledger Setup is assigned to the Adjustment Value Entry.</span></span>  

 <span data-ttu-id="531fa-199">**Ajustement négatif à l’étape 4 :** la date de report affectée est le 15 janvier.</span><span class="sxs-lookup"><span data-stu-id="531fa-199">**Negative Adjustment in step 4:** assigned Posting Date is January 15.</span></span> <span data-ttu-id="531fa-200">L’écriture valeur concernée par l’ajustement a une date de report fixée au 15 janvier, qui est comprise dans la plage de dates de report autorisées selon la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-200">The Value Entry in scope of adjustment has Posting Date January 15, which is within the allowed posting date range according to General Ledger Setup.</span></span>  

 <span data-ttu-id="531fa-201">L'ajustement effectué pour l'ajustement négatif à l'étape 3 fait l'objet d'une discussion.</span><span class="sxs-lookup"><span data-stu-id="531fa-201">The adjustment made for the Negative Adjustment in step 3 causes discussion.</span></span> <span data-ttu-id="531fa-202">La date de report favorable pour l'écriture valeur d'ajustement aurait été le 20 décembre ou au moins une date en décembre, car la réévaluation à l'origine du changement de COGS a été reportée en décembre.</span><span class="sxs-lookup"><span data-stu-id="531fa-202">The favorable Posting Date for the Adjustment Value Entry would have been December 20 or at least within December as the revaluation causing the change in COGS was posted in December.</span></span>  

 <span data-ttu-id="531fa-203">Pour procéder à l'ajustement en décembre de l'ajustement négatif à l'étape 3, le champ Début période report dans la configuration du grand livre doit indiquer une date en décembre.</span><span class="sxs-lookup"><span data-stu-id="531fa-203">To achieve adjustment in December of the Negative Adjustment in step 3, the General Ledger Setup, Allow Posting From field, need to state a date in December.</span></span>  

 <span data-ttu-id="531fa-204">**Conclusion :**</span><span class="sxs-lookup"><span data-stu-id="531fa-204">**Conclusion:**</span></span>  

 <span data-ttu-id="531fa-205">Avec les expériences tirées de ce scénario et en tenant compte de la configuration la plus appropriée de la plage de dates de report autorisées pour une compagnie, l’information suivante peut s’avérer utile : tant que vous autorisez le report des modifications de la valeur d'inventaire dans une période, décembre en l’occurrence, la configuration utilisée par la compagnie pour les plages de dates de report autorisées doit être alignée sur cette décision.</span><span class="sxs-lookup"><span data-stu-id="531fa-205">With the experiences from this scenario, considering most suitable setup of allowed posting date range for a company, you might want to consider the following information: As long as you allow changes in inventory value to be posted in a period, December in this case, the setup that the company uses for allowed posting date ranges should be aligned with this decision.</span></span> <span data-ttu-id="531fa-206">Lorsque l'option Début période report dans la configuration du grand livre est définie sur le 1er décembre, la réévaluation effectuée en décembre peut être transférée vers les écritures sortantes affectées dans la même période.</span><span class="sxs-lookup"><span data-stu-id="531fa-206">The Allow Posting From in the General Ledger Setup, stating December 1, would allow the revaluation made in December to be forwarded to affected outbound entries in the same period.</span></span>  

 <span data-ttu-id="531fa-207">Les groupes d'utilisateurs qui ne sont pas autorisés à effectuer des reports en décembre mais en janvier, ce qui était probablement censé être limité par la configuration du grand livre dans ce scénario, devront plutôt être gérés via la configuration des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="531fa-207">User groups not allowed to post in December but in January, which was probably intended to be limited by the General Ledger Setup in this scenario, should instead be addressed via the User setup.</span></span>  

### <a name="item-charge-scenario"></a><span data-ttu-id="531fa-208">Scénario de frais annexes :</span><span class="sxs-lookup"><span data-stu-id="531fa-208">Item charge scenario:</span></span>  
 <span data-ttu-id="531fa-209">Conditions préalables :</span><span class="sxs-lookup"><span data-stu-id="531fa-209">Prerequisites:</span></span>  

 <span data-ttu-id="531fa-210">Configuration de l'inventaire :</span><span class="sxs-lookup"><span data-stu-id="531fa-210">Inventory setup:</span></span>  

-   <span data-ttu-id="531fa-211">Report coûts automatique = Oui</span><span class="sxs-lookup"><span data-stu-id="531fa-211">Automatic Cost Posting = Yes</span></span>  

-   <span data-ttu-id="531fa-212">Ajustement automatique des coûts = Toujours</span><span class="sxs-lookup"><span data-stu-id="531fa-212">Automatic Cost Adjustment=Always</span></span>  

-   <span data-ttu-id="531fa-213">Type calcul coût moyen = Article</span><span class="sxs-lookup"><span data-stu-id="531fa-213">Average Cost Calc. Type=item</span></span>  

-   <span data-ttu-id="531fa-214">Période coût moyen = Jour</span><span class="sxs-lookup"><span data-stu-id="531fa-214">Average Cost Period=Day</span></span>  

 <span data-ttu-id="531fa-215">Configuration du grand livre :</span><span class="sxs-lookup"><span data-stu-id="531fa-215">General Ledger Setup:</span></span>  

-   <span data-ttu-id="531fa-216">Début période report = 1er décembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-216">Allow Posting From = December 1, 2013.</span></span>  

-   <span data-ttu-id="531fa-217">Fin période report = Vide</span><span class="sxs-lookup"><span data-stu-id="531fa-217">Allow Posting To = empty</span></span>  

 <span data-ttu-id="531fa-218">Configuration des utilisateurs :</span><span class="sxs-lookup"><span data-stu-id="531fa-218">User Setup:</span></span>  

-   <span data-ttu-id="531fa-219">Début période report = 1er décembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-219">Allow Posting From = December 1, 2013.</span></span>  

-   <span data-ttu-id="531fa-220">Fin période report = Vide</span><span class="sxs-lookup"><span data-stu-id="531fa-220">Allow Posting to = empty</span></span>  

##### <a name="to-test-the-scenario"></a><span data-ttu-id="531fa-221">Pour tester le scénario</span><span class="sxs-lookup"><span data-stu-id="531fa-221">To test the scenario</span></span>  

1.  <span data-ttu-id="531fa-222">Créez des frais annexes :</span><span class="sxs-lookup"><span data-stu-id="531fa-222">Create item charge:</span></span>  

     <span data-ttu-id="531fa-223">Unité de mesure de base = PCS</span><span class="sxs-lookup"><span data-stu-id="531fa-223">Base unit of measure = PCS</span></span>  

     <span data-ttu-id="531fa-224">Mode évaluation stock = Moyen</span><span class="sxs-lookup"><span data-stu-id="531fa-224">Costing Method = Average</span></span>  

     <span data-ttu-id="531fa-225">Sélectionnez des groupes de report facultatifs.</span><span class="sxs-lookup"><span data-stu-id="531fa-225">Select optional posting groups.</span></span>  

2.  <span data-ttu-id="531fa-226">Créer un bon de commande</span><span class="sxs-lookup"><span data-stu-id="531fa-226">Create new purchase order</span></span>  

     <span data-ttu-id="531fa-227">Numéro du fournisseur : 10000</span><span class="sxs-lookup"><span data-stu-id="531fa-227">Buy-from Vendor No.: 10000</span></span>  

     <span data-ttu-id="531fa-228">Date de report = 15 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-228">Posting Date = December 15, 2013</span></span>  

     <span data-ttu-id="531fa-229">N° facture fournisseur : 1234</span><span class="sxs-lookup"><span data-stu-id="531fa-229">Vendor Invoice No.: 1234</span></span>  

     <span data-ttu-id="531fa-230">Sur la ligne bon de commande :</span><span class="sxs-lookup"><span data-stu-id="531fa-230">On the purchase order line:</span></span>  

     <span data-ttu-id="531fa-231">Article = FRAIS</span><span class="sxs-lookup"><span data-stu-id="531fa-231">Item = CHARGE</span></span>  

     <span data-ttu-id="531fa-232">Quantité = 1</span><span class="sxs-lookup"><span data-stu-id="531fa-232">Quantity = 1</span></span>  

     <span data-ttu-id="531fa-233">Coût unitaire direct = 100</span><span class="sxs-lookup"><span data-stu-id="531fa-233">Direct Unit Cost = 100</span></span>  

     <span data-ttu-id="531fa-234">Reportez la réception et la facture.</span><span class="sxs-lookup"><span data-stu-id="531fa-234">Post Receive and Invoice.</span></span>  

3.  <span data-ttu-id="531fa-235">Créez un document de vente :</span><span class="sxs-lookup"><span data-stu-id="531fa-235">Create new sales order:</span></span>  

     <span data-ttu-id="531fa-236">N° débiteur : 10000</span><span class="sxs-lookup"><span data-stu-id="531fa-236">Sell-to Customer No.: 10000</span></span>  

     <span data-ttu-id="531fa-237">Date de report = 16 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-237">Posting Date = December 16, 2013</span></span>  

     <span data-ttu-id="531fa-238">Sur la ligne document de vente :</span><span class="sxs-lookup"><span data-stu-id="531fa-238">On the sales order line:</span></span>  

     <span data-ttu-id="531fa-239">Article = FRAIS</span><span class="sxs-lookup"><span data-stu-id="531fa-239">Item = CHARGE</span></span>  

     <span data-ttu-id="531fa-240">Quantité = 1</span><span class="sxs-lookup"><span data-stu-id="531fa-240">Quantity = 1</span></span>  

     <span data-ttu-id="531fa-241">Prix unitaire = 135</span><span class="sxs-lookup"><span data-stu-id="531fa-241">Unit Price = 135</span></span>  

     <span data-ttu-id="531fa-242">Reportez la livraison et la facture.</span><span class="sxs-lookup"><span data-stu-id="531fa-242">Post Ship and Invoice.</span></span>  

4.  <span data-ttu-id="531fa-243">Configuration du grand livre :</span><span class="sxs-lookup"><span data-stu-id="531fa-243">General Ledger Setup:</span></span>  

     <span data-ttu-id="531fa-244">Début période report = 1er janvier 2014</span><span class="sxs-lookup"><span data-stu-id="531fa-244">Allow Posting From = January 1, 2014</span></span>  

     <span data-ttu-id="531fa-245">Fin période report = Vide</span><span class="sxs-lookup"><span data-stu-id="531fa-245">Allow Posting To = blank</span></span>  

5.  <span data-ttu-id="531fa-246">Créez un bon de commande :</span><span class="sxs-lookup"><span data-stu-id="531fa-246">Create new purchase order:</span></span>  

     <span data-ttu-id="531fa-247">Numéro du fournisseur : 10000</span><span class="sxs-lookup"><span data-stu-id="531fa-247">Buy-from Vendor No.: 10000</span></span>  

     <span data-ttu-id="531fa-248">Date de report = 2 janvier 2014</span><span class="sxs-lookup"><span data-stu-id="531fa-248">Posting Date = January 2, 2014</span></span>  

     <span data-ttu-id="531fa-249">N° facture fournisseur : 2345</span><span class="sxs-lookup"><span data-stu-id="531fa-249">Vendor Invoice No.: 2345</span></span>  

     <span data-ttu-id="531fa-250">Sur la ligne bon de commande :</span><span class="sxs-lookup"><span data-stu-id="531fa-250">On the purchase order line:</span></span>  

     <span data-ttu-id="531fa-251">Frais annexes = JB-FREIGHT</span><span class="sxs-lookup"><span data-stu-id="531fa-251">Item Charge = JB-FREIGHT</span></span>  

     <span data-ttu-id="531fa-252">Quantité = 1</span><span class="sxs-lookup"><span data-stu-id="531fa-252">Quantity = 1</span></span>  

     <span data-ttu-id="531fa-253">Coût unitaire direct = 3</span><span class="sxs-lookup"><span data-stu-id="531fa-253">Direct Unit Cost = 3</span></span>  

     <span data-ttu-id="531fa-254">Affectez les frais annexes à la réception achat à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="531fa-254">Assign Item Charge to Purchase Receipt from step 2.</span></span>  

     <span data-ttu-id="531fa-255">Reportez la réception et la facture.</span><span class="sxs-lookup"><span data-stu-id="531fa-255">Post Receipt and Invoice.</span></span>  

     <span data-ttu-id="531fa-256">![Aperçu des écritures article et valeur article résultantes 3](media/helene/TechArticleAdjustcost11.png "Aperçu des écritures article et valeur article résultantes 3")</span><span class="sxs-lookup"><span data-stu-id="531fa-256">![Overview of resulting item ledger and value entries 3](media/helene/TechArticleAdjustcost11.png "Overview of resulting item ledger and value entries 3")</span></span>

6.  <span data-ttu-id="531fa-257">À la date du 3 janvier arrive une facture achat, contenant des frais annexes supplémentaires pour l’achat effectué à l’étape 2.</span><span class="sxs-lookup"><span data-stu-id="531fa-257">On work date January 3, a purchase invoice arrives, containing an additional item charge to the purchase made in step 2.</span></span> <span data-ttu-id="531fa-258">La date de document de cette facture est le 30 décembre, elle est donc reportée avec la date de report du 30 décembre 2013.</span><span class="sxs-lookup"><span data-stu-id="531fa-258">This invoice has document date December 30 and is therefore posted with Posting Date December 30, 2013.</span></span>  

     <span data-ttu-id="531fa-259">Créez un bon de commande :</span><span class="sxs-lookup"><span data-stu-id="531fa-259">Create new purchase order:</span></span>  

     <span data-ttu-id="531fa-260">Numéro du fournisseur : 10000</span><span class="sxs-lookup"><span data-stu-id="531fa-260">Buy-from Vendor No.: 10000</span></span>  

     <span data-ttu-id="531fa-261">Date de report = 30 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-261">Posting Date = December 30, 2013</span></span>  

     <span data-ttu-id="531fa-262">N° facture fournisseur : 3456</span><span class="sxs-lookup"><span data-stu-id="531fa-262">Vendor Invoice No.: 3456</span></span>  

     <span data-ttu-id="531fa-263">Sur la ligne bon de commande :</span><span class="sxs-lookup"><span data-stu-id="531fa-263">On the purchase order line:</span></span>  

     <span data-ttu-id="531fa-264">Frais annexes = JB-FREIGHT</span><span class="sxs-lookup"><span data-stu-id="531fa-264">Item Charge = JB-FREIGHT</span></span>  

     <span data-ttu-id="531fa-265">Quantité = 1</span><span class="sxs-lookup"><span data-stu-id="531fa-265">Quantity = 1</span></span>  

     <span data-ttu-id="531fa-266">Coût unitaire direct = 2</span><span class="sxs-lookup"><span data-stu-id="531fa-266">Direct Unit Cost = 2</span></span>  

     <span data-ttu-id="531fa-267">Affectez les frais annexes à la réception achat à l'étape 2</span><span class="sxs-lookup"><span data-stu-id="531fa-267">Assign Item Charge to Purchase Receipt from step 2</span></span>  

     <span data-ttu-id="531fa-268">Reportez la réception et la facture.</span><span class="sxs-lookup"><span data-stu-id="531fa-268">Post Receipt and Invoice.</span></span>  

   <span data-ttu-id="531fa-269">![Aperçu des écritures article et valeur article résultantes 4](media/helene/TechArticleAdjustcost12.png "Aperçu des écritures article et valeur article résultantes 4")</span><span class="sxs-lookup"><span data-stu-id="531fa-269">![Overview of resulting item ledger and value entries 4](media/helene/TechArticleAdjustcost12.png "Overview of resulting item ledger and value entries 4")</span></span>

 <span data-ttu-id="531fa-270">Le rapport Évaluation de l'inventaire est imprimé à la date du 31 décembre 2013</span><span class="sxs-lookup"><span data-stu-id="531fa-270">Inventory Valuation report is printed as of Date December 31 , 2013</span></span>  

<span data-ttu-id="531fa-271">![Contenu du rapport d'évaluation de l'inventaire](media/helene/TechArticleAdjustcost13.png "Contenu du rapport d'évaluation de l'inventaire")</span><span class="sxs-lookup"><span data-stu-id="531fa-271">![Content of the Inventory Valuation report](media/helene/TechArticleAdjustcost13.png "Content of the Inventory Valuation report")</span></span>

 <span data-ttu-id="531fa-272">**Résumé du scénario :**</span><span class="sxs-lookup"><span data-stu-id="531fa-272">**Summary of scenario:**</span></span>  

 <span data-ttu-id="531fa-273">Le scénario décrit se termine avec un rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur = 2.</span><span class="sxs-lookup"><span data-stu-id="531fa-273">The described scenario ends up with an Inventory Valuation report demonstrating Quantity = 0 while the Value = 2.</span></span> <span data-ttu-id="531fa-274">Les frais annexes reportés à l'étape 11 font partie de la valeur d'augmentation d'inventaire de décembre alors que la diminution d'inventaire pour la même période n'est pas affectée.</span><span class="sxs-lookup"><span data-stu-id="531fa-274">The Item charge posted in step 11 is part of the Inventory Increase value of December while the Inventory Decrease of the same period is not affected.</span></span>  

 <span data-ttu-id="531fa-275">Définir l’option Début période report au 1er janvier dans la configuration du grand livre était recommandé pour les premiers frais annexes.</span><span class="sxs-lookup"><span data-stu-id="531fa-275">Having the General Ledger Setup stating Allow Posting From January 1 was a good thing for the first Item charge.</span></span> <span data-ttu-id="531fa-276">Les coûts de l'augmentation et de la diminution d'inventaire ont été enregistrés dans la même période.</span><span class="sxs-lookup"><span data-stu-id="531fa-276">The costs of the Inventory Increase and Decrease was recorded in the same period.</span></span> <span data-ttu-id="531fa-277">Cependant, pour les deuxièmes frais annexes, le changement de COGS est reconnu dans la période suivante.</span><span class="sxs-lookup"><span data-stu-id="531fa-277">For the second Item charge however, the General Ledger Setup causes the change in COGS to be recognized in the period after.</span></span>  

 <span data-ttu-id="531fa-278">**Conclusion :**</span><span class="sxs-lookup"><span data-stu-id="531fa-278">**Conclusion:**</span></span>  

 <span data-ttu-id="531fa-279">Il est difficile d'avoir le rapport Évaluation de l'inventaire indiquant Quantité = 0 alors que la valeur <> 0.</span><span class="sxs-lookup"><span data-stu-id="531fa-279">It’s a challenge to have the Inventory Valuation report to demonstrate Quantity = 0 while the Value <> 0.</span></span> <span data-ttu-id="531fa-280">Dans ce cas, il est également plus difficile d'exprimer des paramètres optimaux, étant donné que les factures achat arrivent le même jour mais couvrent différentes périodes ou même différents exercices financiers.</span><span class="sxs-lookup"><span data-stu-id="531fa-280">In this case it’s also more difficult to express the optimal settings, having purchase invoices arriving the same day but addressing different periods or even fiscal years.</span></span> <span data-ttu-id="531fa-281">Le passage à un nouvel exercice financier nécessite généralement une planification et à cet effet, le processus Ajuster coûts – Écr article qui reconnaît COGS, doit être pris en compte.</span><span class="sxs-lookup"><span data-stu-id="531fa-281">Crossing to a new fiscal year usually requires some planning and as part of that the insight of Adjust Cost – Item entries process, recognizing COGS, is to be considered.</span></span>  

 <span data-ttu-id="531fa-282">Dans ce scénario, une solution aurait pu être que le champ Début période report dans la Configuration du grand livre indique une date en décembre pour quelques jours de plus et que le report des premiers frais annexes soit postposé pour que tous les coûts de la période ou de l'exercice financier précédent soient reconnus pour la période à laquelle ils appartiennent. Ainsi, le traitement en lot Ajuster coûts – Écr. article serait exécuté et la date de report autorisée serait déplacée vers la nouvelle période ou le nouvel exercice financier.</span><span class="sxs-lookup"><span data-stu-id="531fa-282">In this scenario one option could have been to have the General Ledger Setup, field Allow Posting From, stating a date in December for a couple of more days and the posting of the first item charge postponed to allow all costs for the previous period/fiscal year to be recognized for the period they belong to first, having the Adjust Cost – Item entries batch job run and thereafter move the allowed posting date to the new period\/fiscal year.</span></span> <span data-ttu-id="531fa-283">Les premiers frais annexes avec la date de report du 2 janvier peuvent ensuite être reportés.</span><span class="sxs-lookup"><span data-stu-id="531fa-283">The first item charge with posting date January 2 could then be posted.</span></span>  

## <a name="history-of-adjust-cost--item-entries-batch-job"></a><span data-ttu-id="531fa-284">Historique du traitement en lot Ajuster coûts – Écr. article</span><span class="sxs-lookup"><span data-stu-id="531fa-284">History of Adjust Cost – Item entries batch job</span></span>  
 <span data-ttu-id="531fa-285">Voici un résumé du concept d’affectation de dates de report aux écritures valeur d’ajustement par le traitement en lot Ajuster coûts – Écr article.</span><span class="sxs-lookup"><span data-stu-id="531fa-285">Below is a summary of the concept assigning Posting Dates to Adjustment Value Entries by the Adjust Cost – Item entries batch job.</span></span>  

### <a name="about-the-request-form-posting-date"></a><span data-ttu-id="531fa-286">À propos de la date de report du formulaire de sélection :</span><span class="sxs-lookup"><span data-stu-id="531fa-286">About the request form posting date:</span></span>  
 <span data-ttu-id="531fa-287">Il n'est plus nécessaire d'indiquer une date de report dans le formulaire de demande du traitement en lot Ajuster coûts - Écr. article.</span><span class="sxs-lookup"><span data-stu-id="531fa-287">There is no longer a posting date to be stated in the request form of the Adjust Cost - Item entries batch job.</span></span> <span data-ttu-id="531fa-288">Le traitement en lot exécute toutes les modifications nécessaires et crée des écritures valeur avec la date de report de l'écriture valeur qu'il ajuste.</span><span class="sxs-lookup"><span data-stu-id="531fa-288">The batch job runs through all necessary changes and creates value entries with the posting date of the value entry it adjusts.</span></span> <span data-ttu-id="531fa-289">Si la date de report n'est pas comprise dans la plage de dates de report autorisées dans le champ Début période report de la configuration du grand livre ou si les périodes d'inventaire sont utilisées, la date la plus récente des deux sera utilisée.</span><span class="sxs-lookup"><span data-stu-id="531fa-289">If the posting date is not within allowed posting date range the posting date in the Allow Posting From field in the General Ledger Setup, OR if the Inventory periods are used, the later date of the two will be used.</span></span> <span data-ttu-id="531fa-290">Reportez-vous au concept décrit ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="531fa-290">See described concept above.</span></span>  

## <a name="history-of-post-inventory-cost-to-gl-batch-job"></a><span data-ttu-id="531fa-291">Historique du traitement en lot Reporter le coût de l'inventaire dans le grand livre</span><span class="sxs-lookup"><span data-stu-id="531fa-291">History of Post Inventory cost to G/L batch job</span></span>  
 <span data-ttu-id="531fa-292">Le traitement en lot Reporter le coût de l'inventaire dans le grand livre est étroitement lié au traitement en lot Ajuster coûts – Écr article. C'est pourquoi l'historique de ce traitement en lot est résumé et partagé ici également.</span><span class="sxs-lookup"><span data-stu-id="531fa-292">The Post Inventory Cost to G/L batch job is closely related to the Adjust Cost – Item entries batch job why the history of this batch job is summarized and shared here as well.</span></span>  
 
<span data-ttu-id="531fa-293">![Coût réel comparé au coût prévu](media/helene/TechArticleAdjustcost14.png "Coût réel comparé au coût prévu")</span><span class="sxs-lookup"><span data-stu-id="531fa-293">![Actual cost versus expected cost](media/helene/TechArticleAdjustcost14.png "Actual cost versus expected cost")</span></span>

### <a name="about-the-posting-date"></a><span data-ttu-id="531fa-294">À propos de la date de report</span><span class="sxs-lookup"><span data-stu-id="531fa-294">About the posting date</span></span>
 <span data-ttu-id="531fa-295">Il n'est plus nécessaire d'indiquer une date de report dans le formulaire de demande du traitement en lot Reporter le coût de l'inventaire dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-295">There is no longer a posting date to be stated in the request form of the Post Inventory Cost to G/L batch job.</span></span> <span data-ttu-id="531fa-296">L'écriture est créée avec la même date de report que l'écriture valeur associée.</span><span class="sxs-lookup"><span data-stu-id="531fa-296">The G/L entry is created with the same Posting Date as the related value entry.</span></span> <span data-ttu-id="531fa-297">Pour exécuter le traitement en lot, la plage de dates de report autorisées doit autoriser la date de report de l’écriture GL créée.</span><span class="sxs-lookup"><span data-stu-id="531fa-297">In order to complete the batch job, the allowed posting date range must allow the Posting Date of the created G/L entry.</span></span> <span data-ttu-id="531fa-298">Sinon, la plage de dates de report autorisées doit être temporairement rouverte en modifiant ou en supprimant les dates des champs Début période report et Fin période report dans la configuration du grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-298">If not, the allowed posting date range must be temporarily reopened by changing or removing the dates in the Allow Posting From and To fields in the General Ledger Setup.</span></span> <span data-ttu-id="531fa-299">Pour éviter les problèmes de rapprochement, la date de report de l’écriture GL doit correspondre à la date de report de l’écriture valeur.</span><span class="sxs-lookup"><span data-stu-id="531fa-299">To avoid reconciliation issues, it is required that Posting Date of the G/L Entry corresponds to the Posting Date of the Value Entry.</span></span>  

 <span data-ttu-id="531fa-300">Le traitement en lot analyse la table 5811 - Reporter l'écriture de valeur au GL pour identifier les écritures valeur concernées par le report au grand livre.</span><span class="sxs-lookup"><span data-stu-id="531fa-300">The batch job scans Table 5811 - Post Value Entry to G/L, to identify the Value Entries in scope for posting to General Ledger.</span></span> <span data-ttu-id="531fa-301">Une fois l’exécution réussie, la table est vidée.</span><span class="sxs-lookup"><span data-stu-id="531fa-301">After a successful run, the table is emptied.</span></span>

## <a name="see-also"></a><span data-ttu-id="531fa-302">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="531fa-302">See Also</span></span>  
[<span data-ttu-id="531fa-303">Détails de conception : Évaluation des coûts de l'inventaire</span><span class="sxs-lookup"><span data-stu-id="531fa-303">Design Details: Inventory Costing</span></span>](design-details-inventory-costing.md)  
[<span data-ttu-id="531fa-304">Détails de conception : Affectation article</span><span class="sxs-lookup"><span data-stu-id="531fa-304">Design Details: Item Application</span></span>](design-details-item-application.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
