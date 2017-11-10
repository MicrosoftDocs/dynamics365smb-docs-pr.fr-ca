---
title: "Envoyer les rapports TVA destinés à l'administration fiscale | Microsoft Docs"
description: "Apprendre à préparer les rapports qui répertorient la TVA des ventes au cours d'une période, ou à partir des ventes et achats, et envoyer le rapport à l'administration fiscale."
author: bholtorf
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: VAT, tax, report, EC sales list, statement
ms.date: 07/17/2017
ms.author: bholtorf
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 2f1e4016df9932b0441d664e203be947e1fa643e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---

# <a name="how-to-report-vat-to-a-tax-authority"></a><span data-ttu-id="d5fd5-103">Procédure : déclarer la TVA à une administration fiscale</span><span class="sxs-lookup"><span data-stu-id="d5fd5-103">How To: Report VAT to a Tax Authority</span></span>
<span data-ttu-id="d5fd5-104">Cette rubrique décrit les rapports dans [!INCLUDE[d365fin](includes/d365fin_md.md)] que vous pouvez utiliser pour envoyer des informations sur les montants de la taxe sur la valeur ajoutée (TVA) relatifs aux ventes et achats à l'administration fiscale de votre région.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-104">This topic describes the reports in [!INCLUDE[d365fin](includes/d365fin_md.md)] that you can use to submit information about value-added tax (VAT) amounts for sales and purchases to tax authorities in your region.</span></span>

<span data-ttu-id="d5fd5-105">Vous pouvez utiliser les rapports suivants :</span><span class="sxs-lookup"><span data-stu-id="d5fd5-105">You can use the following reports :</span></span>

* <span data-ttu-id="d5fd5-106">La déclaration de liste des ventes de l'Union européenne (EU) **Liste des ventes UE** répertorie les montants de la taxe sur la valeur ajoutée (TVA) que vous avez collectés pour les ventes aux clients enregistrés dans les pays de l'Union européenne (UE).</span><span class="sxs-lookup"><span data-stu-id="d5fd5-106">The **EC Sales List** European Community (EC) Sales List report lists the value added tax (VAT) amounts that you have collected for sales to VAT-registered customers in the European Union (EU) countries.</span></span>  
* <span data-ttu-id="d5fd5-107">Le rapport **Retour TVA** inclut la TVA pour les ventes et les achats aux clients dans tous les pays utilisant la TVA.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-107">The **VAT Return** report includes VAT for sales and purchases to customers in all countries that use VAT.</span></span>

<span data-ttu-id="d5fd5-108">Si vous souhaitez afficher un historique complet des écritures TVA, chaque report impliquant la TVA crée une écriture dans la page **Écritures TVA**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-108">If you want to view a complete history of VAT entries, every posting that involves VAT creates an entry on the **VAT Entries** page.</span></span> <span data-ttu-id="d5fd5-109">Ces écritures sont utilisées pour calculer le montant du relevé de TVA, tel que paiement et remboursement, pour une période donnée.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-109">These entries are used to calculate your VAT settlement amount, such as your payment and refund, for a specific period.</span></span> <span data-ttu-id="d5fd5-110">Pour afficher les écritures TVA, choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Écritures TVA**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-110">To view VAT entries, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Entries**, and then choose the related link.</span></span>

## <a name="about-the-ec-sales-list-report"></a><span data-ttu-id="d5fd5-111">À propos du rapport Liste des ventes UE</span><span class="sxs-lookup"><span data-stu-id="d5fd5-111">About the EC Sales List report</span></span>
<span data-ttu-id="d5fd5-112">Au Royaume-Uni, toutes les compagnies qui vendent des marchandises et des services aux clients enregistrés à la TVA, y compris les clients dans d'autres pays de l'Union européenne (UE), doivent envoyer une version électronique du rapport Liste des ventes de la Communauté européenne (CE) au format XML sur le site Web du service de la fiscalité et des douanes du Royaume-Uni.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-112">In the UK, all companies that sell goods and services to VAT-registered customers, including customers in other European Union (EU) countries, must submit an electronic version of the European Community (EC) Sales List report in XML format through Her Majesty's Revenue and Customs (HMRC) website.</span></span> <span data-ttu-id="d5fd5-113">Le rapport de liste des ventes de l'Union européenne ne fonctionne que pour les pays de l'UE.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-113">The EC Sales List report works only for countries in the EU.</span></span>

<span data-ttu-id="d5fd5-114">Le rapport comprend une ligne pour chaque type de transaction avec le client, et affiche le montant total pour chaque type de transaction.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-114">The report includes one line for each type of transaction with the customer, and displays the total amount for each type of transactions.</span></span> <span data-ttu-id="d5fd5-115">Il peut inclure trois types de transactions :</span><span class="sxs-lookup"><span data-stu-id="d5fd5-115">There are three types of transactions that the report can include:</span></span>  

* <span data-ttu-id="d5fd5-116">Marchandises B2B</span><span class="sxs-lookup"><span data-stu-id="d5fd5-116">B2B Goods</span></span>  
* <span data-ttu-id="d5fd5-117">Services B2B</span><span class="sxs-lookup"><span data-stu-id="d5fd5-117">B2B Services</span></span>  
* <span data-ttu-id="d5fd5-118">Marchandises triangulées B2B</span><span class="sxs-lookup"><span data-stu-id="d5fd5-118">B2B Triangulated Goods</span></span>  

<span data-ttu-id="d5fd5-119">Les biens et services B2B indiquent si vous avez vendu un bien ou un service, et sont contrôlés par le paramètre **Service UE** de la configuration du report TVA.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-119">B2B goods and services specify whether you sold a good or a service, and are controlled by the **EU Service** setting in the VAT posting setup.</span></span> <span data-ttu-id="d5fd5-120">Les marchandises triangulées B2B indiquent si vous vous êtes engagé dans des transactions avec un tiers, et sont contrôlées par le paramètre **Trans. tripartite UE** sur les documents vente, comme des documents de vente, des factures, des notes de crédit, etc.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-120">B2B Triangulated Goods indicate whether you engaged in trade with a 3rd party, and are controlled by the **EU 3-Party Trade** setting on sales documents, such as sales orders, invoices, credit memos, and so on.</span></span>  

<span data-ttu-id="d5fd5-121">Une fois que l'administration fiscale aura examiné votre rapport, elle devra envoyer un courriel au contact de votre compagnie.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-121">After the tax authority reviews your report, they will send an email to the contact person for your company.</span></span> <span data-ttu-id="d5fd5-122">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], le contact est spécifié sur la page **Informations société**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-122">In [!INCLUDE[d365fin](includes/d365fin_md.md)], the contact person is specified on the **Company Information** page.</span></span> <span data-ttu-id="d5fd5-123">Avant de soumettre le rapport, assurez-vous qu'un contact a été sélectionné.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-123">Before you submit the report, make sure that a contact person is chosen.</span></span>

## <a name="about-the-vat-return-report"></a><span data-ttu-id="d5fd5-124">À propos du rapport Retour TVA</span><span class="sxs-lookup"><span data-stu-id="d5fd5-124">About the VAT Return report</span></span>
<span data-ttu-id="d5fd5-125">Utilisez ce rapport pour envoyer les documents relatifs à la TVA sur les ventes et les achats, tels que les commandes d'achat et de vente, les factures et les notes de crédit.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-125">Use this report to submit VAT for sales and purchase documents, such as purchase and sales orders, invoices, and credit memos.</span></span> <span data-ttu-id="d5fd5-126">Les informations de ce rapport ont le même format que dans la déclaration de l'administration fiscale et douanière.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-126">The information in the report is in the same format as on the declaration form from the customs and tax authorities.</span></span>  

<span data-ttu-id="d5fd5-127">La TVA est calculée sur la base de la configuration du report TVA et des groupes de report TVA que vous avez définis.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-127">VAT is calculated based on the VAT posting setup and the VAT posting groups that you have set up.</span></span>

<span data-ttu-id="d5fd5-128">Pour le retour TVA, vous pouvez spécifier les écritures pour :</span><span class="sxs-lookup"><span data-stu-id="d5fd5-128">For the VAT return, you can specify the entries to include:</span></span>

* <span data-ttu-id="d5fd5-129">Envoyer les transactions ouvertes uniquement, ou ouvertes et fermées.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-129">Submit open transactions only, or open and closed.</span></span> <span data-ttu-id="d5fd5-130">Par exemple, cela est utile lorsque vous préparez votre retour TVA annuel final.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-130">For example, this is useful when you prepare your final annual VAT return.</span></span>
* <span data-ttu-id="d5fd5-131">Envoyer uniquement les écritures des périodes définies, ou inclure également les écritures des périodes précédentes.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-131">Submit only entries from the specified periods, or also include entries from previous periods.</span></span> <span data-ttu-id="d5fd5-132">Cette fonction est utile pour mettre à jour un retour TVA déjà envoyé, par exemple, si un fournisseur vous envoie une facture échue.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-132">This is useful for updating a VAT return that you have already submitted, for example, if a vendor sends you a late invoice.</span></span>    

## <a name="to-connect-to-your-tax-authoritys-web-service"></a><span data-ttu-id="d5fd5-133">Pour vous connecter au service Web de votre administration fiscale</span><span class="sxs-lookup"><span data-stu-id="d5fd5-133">To connect to your tax authority's web service</span></span>
[!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="d5fd5-134"> fournit des connexions de service à des sites Web d'administrations fiscales.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-134"> provides service connections to tax authority websites.</span></span> <span data-ttu-id="d5fd5-135">Par exemple, si vous vous trouvez au Royaume-uni, vous pouvez activer la connexion de service **GovTalk** pour envoyer la liste des ventes UE et les rapports Retour TVA par voie électronique.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-135">For example, if you are in the UK, you can enable the **GovTalk** service connection to submit the EC Sales List and VAT Return reports electronically.</span></span> <span data-ttu-id="d5fd5-136">Si vous souhaitez envoyer le rapport manuellement, par exemple en entrant vos données sur le site Web de l'administration fiscale, cela n'est pas nécessaire.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-136">If you want to submit the report manually, for example by entering your data on the tax authority's website, this is not required.</span></span>   

<span data-ttu-id="d5fd5-137">Pour déclarer la TVA à une administration par voie électronique, vous devez connecter [!INCLUDE[d365fin](includes/d365fin_md.md)] au service Web de l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-137">To report VAT to a tax authority electronically, you need to connect [!INCLUDE[d365fin](includes/d365fin_md.md)] to the tax authority's web service.</span></span> <span data-ttu-id="d5fd5-138">Cela suppose que vous configuriez un compte avec votre administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-138">This requires that you set up an account with your tax authority.</span></span> <span data-ttu-id="d5fd5-139">Lorsque vous avez un compte, vous pouvez activer une connexion de service que nous fournissons dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="d5fd5-139">When you have an account, you can enable a service connection that we provide in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>

1. <span data-ttu-id="d5fd5-140">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Connexions au service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-140">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Connections**, and then choose appropriate link.</span></span>
2. <span data-ttu-id="d5fd5-141">Renseignez les champs requis.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-141">Fill in the required fields.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    > [!NOTE]  
>   <span data-ttu-id="d5fd5-142">Il est judicieux de tester votre connexion.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-142">It's a good idea to test your connection.</span></span> <span data-ttu-id="d5fd5-143">Pour cela, choisissez la case à cocher **Mode test**, puis préparez et envoyez votre rapport TVA comme décrit dans la section _Préparer et envoyer un rapport TVA_.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-143">To do this, choose the **Test Mode** check box, then prepare and submit your VAT report as described in the _To prepare and submit a VAT report_ section.</span></span> <span data-ttu-id="d5fd5-144">En mode Test, le service vérifie si l'administration fiscale peut recevoir votre rapport, et l'état du rapport indiquera si l'envoi du test a réussi.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-144">While in Test Mode, the service tests whether the tax authority can receive your report, and the status of the report will indicate whether the test submission was successful.</span></span> <span data-ttu-id="d5fd5-145">Il est important de retenir que ce n'est pas un envoi réel.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-145">It's important to remember that this is not an actual submission.</span></span> <span data-ttu-id="d5fd5-146">Pour réellement envoyer le rapport, vous devez désactiver la case à cocher **Mode test**, puis répéter le processus d'envoi.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-146">To submit the report for real, you must clear the **Test Mode** check box, and then repeat the submission process.</span></span>

## <a name="to-set-up-vat-reports-in-included365finincludesd365finmdmd"></a><span data-ttu-id="d5fd5-147">Pour configurer les rapports TVA dans [!INCLUDE[d365fin](includes/d365fin_md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5fd5-147">To set up VAT reports in [!INCLUDE[d365fin](includes/d365fin_md.md)]</span></span>
1. <span data-ttu-id="d5fd5-148">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration rapport TVA**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-148">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **VAT Report Setup**, and then choose the related link.</span></span>  
2. <span data-ttu-id="d5fd5-149">Pour laisser des utilisateurs modifier et retourner ce rapport, sélectionnez la case à cocher **Modifier les rapports soumis**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-149">To let users change and resubmit this report, choose the **Modify Submitted Reports** check box.</span></span>  
3. <span data-ttu-id="d5fd5-150">Choisissez la série de numéros à utiliser pour chaque rapport.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-150">Choose the number series to use for each report.</span></span>  

## <a name="to-prepare-and-submit-a-vat-report"></a><span data-ttu-id="d5fd5-151">Pour préparer et soumettre un rapport TVA</span><span class="sxs-lookup"><span data-stu-id="d5fd5-151">To prepare and submit a VAT report</span></span>
1. <span data-ttu-id="d5fd5-152">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Liste des ventes UE** ou **Retour TVA**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-152">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **EC Sales List** or **VAT Return**, and then choose the related link.</span></span>  
2. <span data-ttu-id="d5fd5-153">Sélectionnez **Nouveau**, puis renseignez les champs requis.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-153">Choose **New**, and then fill in the required fields.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="d5fd5-154">Pour générer le contenu de l'état, sélectionnez l'action **Proposer lignes**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-154">To generate the content of the report, choose the **Suggest Lines** action.</span></span>  

    > [!NOTE]  
>   <span data-ttu-id="d5fd5-155">Pour le rapport Liste des ventes UE, vous pouvez consulter les transactions incluses dans les lignes de rapport avant d'envoyer le rapport.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-155">For the EC Sales List report, you can review the transactions included in the report lines before you submit the report.</span></span> <span data-ttu-id="d5fd5-156">Pour cela, sélectionnez la ligne, puis cliquez sur l'action **Afficher écritures TVA**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-156">To do that, choose the line, and then choose the **Show VAT Entries** action.</span></span>  
4. <span data-ttu-id="d5fd5-157">Pour valider et préparer le rapport pour l'envoi, choisissez l'action **Libérer**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-157">To validate and prepare the report for submission, choose the **Release** action.</span></span>  

    >  [!NOTE]  
>   [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="d5fd5-158"> confirme que l'état est configuré correctement.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-158"> validates whether the report is set up correctly.</span></span> <span data-ttu-id="d5fd5-159">Si la validation échoue, les erreurs sont affichées sous **Erreurs et avertissements**, de sorte que vous sachiez quoi corriger.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-159">If the validation fails, the errors display under **Errors and Warnings** so that you know what to fix.</span></span> <span data-ttu-id="d5fd5-160">Généralement, si le message concerne un paramètre manquant dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez cliquer sur le message pour ouvrir la page contenant les informations à corriger.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-160">Typically, if the message is about a missing setting in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can click the message to open the page that contains the information to correct.</span></span>  
5. <span data-ttu-id="d5fd5-161">Pour envoyer l'état, sélectionnez l'action **Soumettre**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-161">To submit the report, choose the **Submit** action.</span></span>  

<span data-ttu-id="d5fd5-162">Une fois que vous envoyez la déclaration, [!INCLUDE[d365fin](includes/d365fin_md.md)] surveille le service et conserve un enregistrement de vos communications.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-162">After you submit the report, [!INCLUDE[d365fin](includes/d365fin_md.md)] monitors the service and keeps a record of your communications.</span></span> <span data-ttu-id="d5fd5-163">Le champ **Statut** indique l'état de la déclaration en cours.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-163">The **Status** field indicates where the report is in the process.</span></span> <span data-ttu-id="d5fd5-164">Par exemple, lorsque l'administration traite votre déclaration, le statut de celle-ci passe à **Réussie**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-164">For example, when the authorities process your report, the status of the report changes to **Succeeded**.</span></span> <span data-ttu-id="d5fd5-165">Si l'administration fiscale trouve des erreurs dans la déclaration que vous avez envoyée, le statut de celle-ci est **Échec**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-165">If the tax authority found mistakes in the report you submitted, the status of the report will be **Failed**.</span></span> <span data-ttu-id="d5fd5-166">Vous pouvez afficher les erreurs sous **Erreurs et avertissements**, corrigez-les, puis envoyez le rapport.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-166">You can view the errors under **Errors and Warnings**, correct them, and then submit the report again.</span></span> <span data-ttu-id="d5fd5-167">Pour visualiser une liste de toutes vos déclarations de liste des ventes UE, consultez la page **États de liste des ventes UE**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-167">To view a list of all your EC Sales List reports, go to the **EC Sales List Reports** page.</span></span>  

## <a name="viewing-communications-with-your-tax-authority"></a><span data-ttu-id="d5fd5-168">Affichage de l’historique des communications avec votre administration fiscale</span><span class="sxs-lookup"><span data-stu-id="d5fd5-168">Viewing communications with your tax authority</span></span>
<span data-ttu-id="d5fd5-169">Dans certains pays, vous échangez des messages avec l'administration fiscale lorsque vous envoyez des états.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-169">In some countries, you exchange messages with the tax authority when you submit reports.</span></span> <span data-ttu-id="d5fd5-170">Vous pouvez afficher le premier et le dernier message que vous avez envoyés ou reçus en choisissant **Télécharger le message d’envoi** et les actions **Télécharger le message de réponse**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-170">You can view the first and the last message you sent or received by choosing the **Download Submission Message** and **Download Response Message** actions.</span></span>  

## <a name="submitting-vat-reports-manually"></a><span data-ttu-id="d5fd5-171">Envoi manuel des rapports TVA</span><span class="sxs-lookup"><span data-stu-id="d5fd5-171">Submitting VAT reports manually</span></span>
<span data-ttu-id="d5fd5-172">Si vous utilisez une autre méthode pour envoyer l'état, par exemple en exportant le XML et en le téléchargeant sur le site Web d'une administration fiscale, vous pouvez ensuite choisir **Marquer comme Soumis** pour clôturer la période de référence.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-172">If you use another method to submit the report, for example by exporting the XML and uploading it to a tax authority website, afterward you can choose **Mark as Submitted** to close the reporting period.</span></span> <span data-ttu-id="d5fd5-173">Lorsque vous signalez le rapport comme libéré, vous ne pouvez plus le modifier.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-173">When you mark the report as released, it becomes non-editable.</span></span> <span data-ttu-id="d5fd5-174">Si vous devez modifier le rapport après l'avoir signalé comme libéré, vous devez le rouvrir.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-174">If you must change the report after you mark it as released, you must reopen it.</span></span>

## <a name="vat-settlement"></a><span data-ttu-id="d5fd5-175">Relevé de TVA</span><span class="sxs-lookup"><span data-stu-id="d5fd5-175">VAT settlement</span></span>
<span data-ttu-id="d5fd5-176">Périodiquement, vous devez régler la TVA nette aux autorités fiscales.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-176">Periodically, you must remit the net VAT to the tax authorities.</span></span> <span data-ttu-id="d5fd5-177">Si vous devez effectuer des relevés de TVA fréquemment, vous pouvez exécuter le traitement en lot **Calculer et reporter le relevé de TVA** pour fermer les écritures TVA ouvertes et transférer les montants TVA achat et vente au compte de relevé de TVA.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-177">If you need to settle VAT frequently, you can run the **Calc. and Post VAT Settlement** batch job to close the open VAT entries and transfer purchase and sales VAT amounts to the VAT settlement account.</span></span>

<span data-ttu-id="d5fd5-178">Lors du transfert des montants TVA vers le compte de déclaration, le compte TVA achat est crédité et le compte TVA vente est débité sur la base des montants calculés pour la période spécifiée.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-178">When you transfer VAT amounts to the settlement account, the purchase VAT account is credited, and the sales VAT account is debited with the amounts calculated for the specified period.</span></span> <span data-ttu-id="d5fd5-179">Le montant net est crédité ou débité, si le montant TVA achat est supérieur, sur le compte du relevé de TVA.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-179">The net amount is credited or debited, if the purchase VAT amount is larger, to the VAT settlement account.</span></span> <span data-ttu-id="d5fd5-180">Vous pouvez reporter la déclaration immédiatement ou imprimer d'abord un rapport de test.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-180">You can post the settlement immediately or print a test report first.</span></span>

>    [!NOTE]  
>    <span data-ttu-id="d5fd5-181">Lorsque vous utilisez le traitement en lot **Calculer et reporter le relevé de TVA**, si vous ne spécifiez pas un **Groupe de report de marché TVA** et un **Groupe de report produit TVA**, les écritures contenant tous les groupes de report de marché et tous les groupes de report de produit sont incluses.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-181">When you use the **Calc. and Post VAT Settlement** batch job, if you don't specify a **VAT Bus. Posting Group** and a **VAT Prod. Posting group**, entries with all business posting groups and product posting group codes are included.</span></span>

## <a name="configuring-your-own-vat-reports"></a><span data-ttu-id="d5fd5-182">Configuration de vos propres états de TVA</span><span class="sxs-lookup"><span data-stu-id="d5fd5-182">Configuring your own VAT reports</span></span>
<span data-ttu-id="d5fd5-183">Vous pouvez utiliser le rapport Liste des ventes UE prédéfini, cependant, vous pouvez également créer vos propres rapports.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-183">You can use the EC Sales List report out-of-the-box, however, you can also create your own reports.</span></span> <span data-ttu-id="d5fd5-184">Cela nécessite de créer des codeunits.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-184">This requires that you create a few codeunits.</span></span> <span data-ttu-id="d5fd5-185">Si vous avez besoin de l'aide à cette fin, contactez un partenaire certifié Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-185">If you need help with that, contact a Microsoft Partner.</span></span>  

<span data-ttu-id="d5fd5-186">Le tableau suivant décrit les codeunits que vous devez créer pour votre rapport.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-186">The following table describes the codeunits that you must create for your report.</span></span>

| <span data-ttu-id="d5fd5-187">Codeunit</span><span class="sxs-lookup"><span data-stu-id="d5fd5-187">Codeunit</span></span> | <span data-ttu-id="d5fd5-188">Ce qu'il doit effectuer</span><span class="sxs-lookup"><span data-stu-id="d5fd5-188">What it must do</span></span> |
|----|-----|
|<span data-ttu-id="d5fd5-189">Proposer lignes</span><span class="sxs-lookup"><span data-stu-id="d5fd5-189">Suggest Lines</span></span>| <span data-ttu-id="d5fd5-190">Extraire les informations de la table Écritures TVA, et les afficher sur les lignes du rapport TVA.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-190">Fetch information from the VAT Entries table, and display it in lines on the VAT report.</span></span>|
|<span data-ttu-id="d5fd5-191">Contenu</span><span class="sxs-lookup"><span data-stu-id="d5fd5-191">Content</span></span> | <span data-ttu-id="d5fd5-192">Contrôler le format du rapport.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-192">Control the format of the report.</span></span> <span data-ttu-id="d5fd5-193">Par exemple, si c'est un fichier XML ou JSON.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-193">For example, whether it is XML or JSON.</span></span> <span data-ttu-id="d5fd5-194">Le format à utiliser dépend des besoins du service Web de votre administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-194">The format to use depends on the requirements of your tax authority's web service.</span></span> |
|<span data-ttu-id="d5fd5-195">Soumission</span><span class="sxs-lookup"><span data-stu-id="d5fd5-195">Submission</span></span> | <span data-ttu-id="d5fd5-196">Contrôler comment et quand vous envoyez le rapport selon les besoins de votre administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-196">Control how, and when, you submit the report based on the requirements of your tax authority.</span></span> |
|<span data-ttu-id="d5fd5-197">Gestionnaire de réponse</span><span class="sxs-lookup"><span data-stu-id="d5fd5-197">Response Handler</span></span> | <span data-ttu-id="d5fd5-198">Gérer le retour de l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-198">Handle the return from the tax authority.</span></span> <span data-ttu-id="d5fd5-199">Par exemple, elle peut envoyer un courriel au contact de votre compagnie.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-199">For example, it might send an email message to your company's contact person.</span></span> |
|<span data-ttu-id="d5fd5-200">Annuler</span><span class="sxs-lookup"><span data-stu-id="d5fd5-200">Cancel</span></span> | <span data-ttu-id="d5fd5-201">Envoyer une annulation d'un rapport TVA qui a été envoyé précédemment à votre administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-201">Send a cancellation of a VAT report that was submitted earlier to your tax authority.</span></span> |

> [!NOTE]  
>   <span data-ttu-id="d5fd5-202">Lorsque vous créez des codeunits pour l'état, faites attention à la valeur du champ **Version de la déclaration TVA**.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-202">When you create codeunits for the report, pay attention to the value in the **VAT Report Version** field.</span></span> <span data-ttu-id="d5fd5-203">Ce champ doit refléter la version du rapport qui est ou a été requis par l'administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-203">This field must reflect the version of the report that is, or was, required by the tax authority.</span></span> <span data-ttu-id="d5fd5-204">Par exemple, vous pouvez saisir **2017** dans le champ pour indiquer que l'état remplit les conditions qui étaient en place cette année.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-204">For example, you might enter **2017** in the field to indicate that the report conforms to the requirements that were in place that year.</span></span> <span data-ttu-id="d5fd5-205">Pour trouver la version en cours, contactez votre administration fiscale.</span><span class="sxs-lookup"><span data-stu-id="d5fd5-205">To find the current version, contact your tax authority.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d5fd5-206">Voir aussi .</span><span class="sxs-lookup"><span data-stu-id="d5fd5-206">See also</span></span>
[<span data-ttu-id="d5fd5-207">Configuration des méthodes de calcul et de report de la taxe sur la valeur ajoutée</span><span class="sxs-lookup"><span data-stu-id="d5fd5-207">Setting Up to Calculations and Posting Methods for Value-Added Tax</span></span>](finance-setup-vat.md)  
[<span data-ttu-id="d5fd5-208">Procédure : utiliser la TVA sur les ventes et les achats</span><span class="sxs-lookup"><span data-stu-id="d5fd5-208">How to: Work with VAT on Sales and Purchases</span></span>](finance-work-with-vat.md)  
[<span data-ttu-id="d5fd5-209">Configuration des ventes</span><span class="sxs-lookup"><span data-stu-id="d5fd5-209">Set Up Sales</span></span>](sales-setup-sales.md)  
[<span data-ttu-id="d5fd5-210">Procédure : facturer des ventes</span><span class="sxs-lookup"><span data-stu-id="d5fd5-210">How to: Invoice Sales</span></span>](sales-setup-sales.md)  
