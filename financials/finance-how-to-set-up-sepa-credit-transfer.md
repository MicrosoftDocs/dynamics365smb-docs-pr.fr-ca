---
title: Configurer des virements SEPA | Microsoft Docs
description: "Découvrez comment configurer des virements SEPA dans Dynamics 365 for Financials."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sepa, credit, transfer, payment,
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 88ac086fa0532892af9c770c14134723e0da2eaf
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-sepa-credit-transfer"></a><span data-ttu-id="1856d-103">Procédure : configurer des virements SEPA</span><span class="sxs-lookup"><span data-stu-id="1856d-103">How to: Set Up SEPA Credit Transfer</span></span>
<span data-ttu-id="1856d-104">Dans la fenêtre **Journal paiement**, vous pouvez exporter des paiements vers un fichier à charger sur votre banque électronique afin de traiter les transferts d'argent associés.</span><span class="sxs-lookup"><span data-stu-id="1856d-104">From the **Payment Journal** window, you can export payments to a file for upload to your electronic bank for processing of the related money transfers.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="1856d-105"> prend en charge le format de virement SEPA, mais dans votre pays/région, d'autres formats de paiements électroniques peuvent être disponibles.</span><span class="sxs-lookup"><span data-stu-id="1856d-105"> supports the SEPA Credit Transfer format, but in your country/region, other formats for electronic payments may be available.</span></span>  

<span data-ttu-id="1856d-106">Pour activer l'exportation de formats de fichiers bancaires qui ne sont pas pris en charge en natif dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez configurer une définition d'échange de données à l'aide de l'infrastructure d'échange de données.</span><span class="sxs-lookup"><span data-stu-id="1856d-106">To enable export of a bank file formats that are not supported out of the box in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can set up a data exchange definition by using the data exchange framework.</span></span> <span data-ttu-id="1856d-107">Pour plus d'informations, reportez vous à [Procédure : configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="1856d-107">For more information, see [How to: Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).</span></span>  

<span data-ttu-id="1856d-108">Avant de pouvoir traiter le paiement par voie électronique lorsque vous exportez des fichiers paiement au format de virement SEPA, vous devez exécuter les étapes de configuration suivantes :</span><span class="sxs-lookup"><span data-stu-id="1856d-108">Before you can process payment electronically by exporting payment files in the SEPA Credit Transfer format, you must perform the following setup steps:</span></span>  

* <span data-ttu-id="1856d-109">Paramétrer le compte bancaire concerné pour traiter le format de virement SEPA</span><span class="sxs-lookup"><span data-stu-id="1856d-109">Set up the bank account in question to handle the SEPA Credit Transfer format</span></span>  
* <span data-ttu-id="1856d-110">Configurer des fiches fournisseur pour traiter les paiements en exportant les fichiers au format de virement SEPA</span><span class="sxs-lookup"><span data-stu-id="1856d-110">Set up vendor cards to process payments by exporting files in the SEPA Credit Transfer format</span></span>  
* <span data-ttu-id="1856d-111">Configurer le lot journal général associé pour activer l'export de paiement à partir de la fenêtre **Journal de paiement**</span><span class="sxs-lookup"><span data-stu-id="1856d-111">Set up the related general journal batch to enable payment export from the **Payment Journal** window</span></span>  
* <span data-ttu-id="1856d-112">Lier la définition d'échange de données pour un ou plusieurs types de règlement au(x) mode(s) de règlement approprié(s)</span><span class="sxs-lookup"><span data-stu-id="1856d-112">Connect the data exchange definition for one or more payment types with the relevant payment method or methods</span></span>  

### <a name="to-set-up-a-bank-account-for-sepa-credit-transfer"></a><span data-ttu-id="1856d-113">Pour configurer un compte bancaire pour SEPA Credit Transfer</span><span class="sxs-lookup"><span data-stu-id="1856d-113">To set up a bank account for SEPA Credit Transfer</span></span>  
1. <span data-ttu-id="1856d-114">Dans la zone **Rechercher**, saisissez **Comptes bancaires**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1856d-114">In the **Search** box, enter **Bank Accounts**, and then choose the related link.</span></span>  
2. <span data-ttu-id="1856d-115">Ouvrez la fiche du compte bancaire à partir duquel vous exporterez des fichiers paiement au format de virement SEPA.</span><span class="sxs-lookup"><span data-stu-id="1856d-115">Open the card of the bank account from which you will export payment files in the SEPA Credit Transfer format.</span></span>  
3. <span data-ttu-id="1856d-116">Sur le raccourci **Transfert**, dans le champ **Format exportation paiement**, choisissez **SEPADD**.</span><span class="sxs-lookup"><span data-stu-id="1856d-116">On the **Transfer** FastTab, in the **Payment Export Format** field, choose **SEPADD**.</span></span>  
4. <span data-ttu-id="1856d-117">Dans le champ **Séries de n° Code Msg Virement SEPA**, sélectionnez une série de numéros dont les numéros sont affectés aux écritures de virement SEPA.</span><span class="sxs-lookup"><span data-stu-id="1856d-117">In the **SEPA CT Msg. ID No. Series** field, choose a number series from which numbers are assigned to SEPA credit transfer entries.</span></span>  
5. <span data-ttu-id="1856d-118">Assurez-vous que le champ **IBAN** est renseigné.</span><span class="sxs-lookup"><span data-stu-id="1856d-118">Make sure the **IBAN** field is filled.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="1856d-119">Le champ **Code devise** doit avoir la valeur **EUR**, car les virements SEPA ne peuvent être effectués que dans la devise EURO.</span><span class="sxs-lookup"><span data-stu-id="1856d-119">The **Currency Code** field must be set to **EUR**, because SEPA credit transfers can only be made in the EURO currency.</span></span>  

### <a name="to-set-up-a-vendor-card-for-sepa-credit-transfer"></a><span data-ttu-id="1856d-120">Pour configurer une fiche fournisseur pour SEPA Credit Transfer</span><span class="sxs-lookup"><span data-stu-id="1856d-120">To set up a vendor card for SEPA Credit Transfer</span></span>  
1. <span data-ttu-id="1856d-121">Dans la zone **Rechercher**, entrez **Fournisseurs**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1856d-121">In the **Search** box, enter **Vendors**, and then choose the related link.</span></span>  
2. <span data-ttu-id="1856d-122">Ouvrez la fiche du fournisseur que vous allez payer par voie électronique en exportant des fichiers paiement au format de virement SEPA.</span><span class="sxs-lookup"><span data-stu-id="1856d-122">Open the card of the vendor whom you will pay electronically by export payment files in the SEPA Credit Transfer format.</span></span>  
3. <span data-ttu-id="1856d-123">Sur le raccourci **Paiement**, dans le champ **Code mode de règlement**, sélectionnez **BANQUE**.</span><span class="sxs-lookup"><span data-stu-id="1856d-123">On the **Payment** FastTab, in the **Payment Method Code** field, choose **BANK**.</span></span>  
4. <span data-ttu-id="1856d-124">Dans le champ **Compte bancaire préféré**, cliquez sur la banque sur laquelle l'argent est transféré lorsqu'il est traité par votre banque électronique.</span><span class="sxs-lookup"><span data-stu-id="1856d-124">In the **Preferred Bank Account** field, choose the bank to which the money will be transferred when it is processed by your electronic bank.</span></span>  

     <span data-ttu-id="1856d-125">La valeur du champ **Compte bancaire préféré** est copiée dans le champ **Cpte bancaire destinataire** de la fenêtre **Journal paiement**.</span><span class="sxs-lookup"><span data-stu-id="1856d-125">The value in the **Preferred Bank Account** field is copied to the **Recipient Bank Account** field in the **Payment Journal** window.</span></span>  

### <a name="to-set-the-payment-journal-up-to-export-payment-files"></a><span data-ttu-id="1856d-126">Pour définir le journal de paiement jusqu'aux fichiers de paiement d'exportation</span><span class="sxs-lookup"><span data-stu-id="1856d-126">To set the payment journal up to export payment files</span></span>  
1. <span data-ttu-id="1856d-127">Dans la zone **Rechercher**, entrez **Feuilles paiement**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1856d-127">In the **Search** box, enter **Payment Journals**, and then choose the related link.</span></span>  
2. <span data-ttu-id="1856d-128">Ouvrez le journal paiement que vous utilisez pour traiter les paiements en exportant les fichiers au format de virement SEPA.</span><span class="sxs-lookup"><span data-stu-id="1856d-128">Open the payment journal that you use to process payments by exporting files in the SEPA Credit Transfer format.</span></span>  
3. <span data-ttu-id="1856d-129">Dans le champ **Nom de la feuille**, choisissez le bouton déroulant.</span><span class="sxs-lookup"><span data-stu-id="1856d-129">In the **Batch Name** field, choose the drop\-down button.</span></span>  
4. <span data-ttu-id="1856d-130">Dans la fenêtre **Lots journal général**, sous l'onglet **Accueil**, dans le groupe **Gérer**, choisissez **Modifier la liste**.</span><span class="sxs-lookup"><span data-stu-id="1856d-130">In the **General Journal Batches** window, on the **Home** tab, in the **Manage** group, choose **Edit List**.</span></span>  
5. <span data-ttu-id="1856d-131">Sur la ligne du journal paiement que vous allez utiliser pour exporter des paiements, cochez la case **Autoriser exportation paiement**.</span><span class="sxs-lookup"><span data-stu-id="1856d-131">On the line for the payment journal that you will use to export payments, select the **Allow Payment Export** check box.</span></span>  

### <a name="to-connect-the-data-exchange-definition-for-one-or-more-payment-types-with-the-relevant-payment-method-or-methods"></a><span data-ttu-id="1856d-132">Pour lier la définition d'échange de données pour un ou plusieurs types de règlement au(x) mode(s) de règlement approprié(s)</span><span class="sxs-lookup"><span data-stu-id="1856d-132">To connect the data exchange definition for one or more payment types with the relevant payment method or methods</span></span>  
1. <span data-ttu-id="1856d-133">Dans la zone **Rechercher**, entrez **Modes de règlement**, puis choisissez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="1856d-133">In the **Search** box, enter **Payment Methods**, and then choose the related link.</span></span>  
2. <span data-ttu-id="1856d-134">Dans la fenêtre **Modes de règlement**, sélectionnez le mode de paiement qui est utilisé pour exporter des paiements, puis cliquez sur le champ **Définition ligne exportation paiem.**</span><span class="sxs-lookup"><span data-stu-id="1856d-134">In the **Payment Methods** window, select the payment method that is used to export payments from, and then choose the **Pmt. Export Line Definition** field.</span></span>  
3. <span data-ttu-id="1856d-135">Dans la fenêtre **Définitions ligne exportation paiem.**, sélectionnez le code spécifié dans le champ **Code** du raccourci **Définitions ligne** à l'étape 4 de la section « Pour décrire le formatage des lignes et des colonnes dans le fichier » dans la [Procédure : configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="1856d-135">In the **Pmt. Export Line Definitions** window, select the code that you specified in the **Code** field on the **Line Definitions** FastTab in step 4 in the “To describe the formatting of lines and columns in the file” section in the [How to: Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) procedure.</span></span>  

    <span data-ttu-id="1856d-136">Le mandat de prélèvement est automatiquement inséré dans le champ **Code mandat de prélèvement** lorsque vous créez une facture vente pour le client que vous avez sélectionné à l'étape 2.</span><span class="sxs-lookup"><span data-stu-id="1856d-136">The direct-debit mandate is automatically inserted in the **Direct Debit Mandate ID** field when you create a sales invoice for the customer that you selected in step 2.</span></span> <span data-ttu-id="1856d-137">Pour plus d'informations, voir [Procédure : créer des lignes vente et achat récurrentes](sales-how-work-standard-lines.md).</span><span class="sxs-lookup"><span data-stu-id="1856d-137">For more information, see [How to: Create Recurring Sales and Purchase Lines](sales-how-work-standard-lines.md).</span></span>  

## <a name="see-also"></a><span data-ttu-id="1856d-138">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1856d-138">See Also</span></span>  
[<span data-ttu-id="1856d-139">Recouvrement de paiements par prélèvement automatique SEPA</span><span class="sxs-lookup"><span data-stu-id="1856d-139">Collect Payments with SEPA Direct Debit</span></span>](finance-collect-payments-with-sepa-direct-debit.md)  
[<span data-ttu-id="1856d-140">Procédure : configurer les définitions d'échange de données</span><span class="sxs-lookup"><span data-stu-id="1856d-140">How to: Set Up Data Exchange Definitions</span></span>](across-how-to-set-up-data-exchange-definitions.md)  
[<span data-ttu-id="1856d-141">Procédure : Créer des lignes ventes et achat récurrentes</span><span class="sxs-lookup"><span data-stu-id="1856d-141">How to: Create Recurring Sales and Purchase Lines</span></span>](sales-how-work-standard-lines.md)  
[<span data-ttu-id="1856d-142">Échange de données en tant que documents électroniques</span><span class="sxs-lookup"><span data-stu-id="1856d-142">Exchanging Data as Electronic Documents</span></span>](across-data-exchange.md)  
