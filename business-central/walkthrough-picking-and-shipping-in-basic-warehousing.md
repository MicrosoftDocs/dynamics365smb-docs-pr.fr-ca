---
title: Prélèvement et expédition dans les configurations de stockage de base | Microsoft Docs
description: Dans Business Central, les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/24/2020
ms.author: edupont
ms.openlocfilehash: d607037d76f0778aa0f1037ac9540cfd3d497dbd
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3786831"
---
# <a name="walkthrough-picking-and-shipping-in-basic-warehouse-configurations"></a><span data-ttu-id="e6f1e-103">Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base</span><span class="sxs-lookup"><span data-stu-id="e6f1e-103">Walkthrough: Picking and Shipping in Basic Warehouse Configurations</span></span>

[!INCLUDE[complete_sample_data](includes/complete_sample_data.md)]

<span data-ttu-id="e6f1e-104">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les processus sortants de prélèvement et d'expédition peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-104">In [!INCLUDE[d365fin](includes/d365fin_md.md)], the outbound processes for picking and shipping can be performed in four ways using different functionalities depending on the warehouse complexity level.</span></span>  

|<span data-ttu-id="e6f1e-105">Méthode</span><span class="sxs-lookup"><span data-stu-id="e6f1e-105">Method</span></span>|<span data-ttu-id="e6f1e-106">Processus entrant</span><span class="sxs-lookup"><span data-stu-id="e6f1e-106">Inbound process</span></span>|<span data-ttu-id="e6f1e-107">Zones</span><span class="sxs-lookup"><span data-stu-id="e6f1e-107">Bins</span></span>|<span data-ttu-id="e6f1e-108">Prélèvements</span><span class="sxs-lookup"><span data-stu-id="e6f1e-108">Picks</span></span>|<span data-ttu-id="e6f1e-109">Livraisons</span><span class="sxs-lookup"><span data-stu-id="e6f1e-109">Shipments</span></span>|<span data-ttu-id="e6f1e-110">Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](design-details-warehouse-setup.md))</span><span class="sxs-lookup"><span data-stu-id="e6f1e-110">Complexity level (See [Design Details: Warehouse Setup](design-details-warehouse-setup.md))</span></span>|  
|------------|---------------------|----------|-----------|---------------|--------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="e6f1e-111">A</span><span class="sxs-lookup"><span data-stu-id="e6f1e-111">A</span></span>|<span data-ttu-id="e6f1e-112">Report du prélèvement et de la livraison à partir de la ligne commande</span><span class="sxs-lookup"><span data-stu-id="e6f1e-112">Post pick and shipment from the order line</span></span>|<span data-ttu-id="e6f1e-113">X</span><span class="sxs-lookup"><span data-stu-id="e6f1e-113">X</span></span>|||<span data-ttu-id="e6f1e-114">2</span><span class="sxs-lookup"><span data-stu-id="e6f1e-114">2</span></span>|  
|<span data-ttu-id="e6f1e-115">B</span><span class="sxs-lookup"><span data-stu-id="e6f1e-115">B</span></span>|<span data-ttu-id="e6f1e-116">Report du prélèvement et de la livraison à partir d'un document prélèvement inventaire</span><span class="sxs-lookup"><span data-stu-id="e6f1e-116">Post pick and shipment from an inventory pick document</span></span>||<span data-ttu-id="e6f1e-117">X</span><span class="sxs-lookup"><span data-stu-id="e6f1e-117">X</span></span>||<span data-ttu-id="e6f1e-118">3</span><span class="sxs-lookup"><span data-stu-id="e6f1e-118">3</span></span>|  
|<span data-ttu-id="e6f1e-119">C</span><span class="sxs-lookup"><span data-stu-id="e6f1e-119">C</span></span>|<span data-ttu-id="e6f1e-120">Report du prélèvement et de la livraison à partir d'un document livraison entrepôt</span><span class="sxs-lookup"><span data-stu-id="e6f1e-120">Post pick and shipment from a warehouse shipment document</span></span>|||<span data-ttu-id="e6f1e-121">X</span><span class="sxs-lookup"><span data-stu-id="e6f1e-121">X</span></span>|<span data-ttu-id="e6f1e-122">4/5/6</span><span class="sxs-lookup"><span data-stu-id="e6f1e-122">4/5/6</span></span>|  
|<span data-ttu-id="e6f1e-123">J</span><span class="sxs-lookup"><span data-stu-id="e6f1e-123">D</span></span>|<span data-ttu-id="e6f1e-124">Report du prélèvement à partir d'un document prélèvement entrepôt et report de la livraison à partir d'un document livraison entrepôt</span><span class="sxs-lookup"><span data-stu-id="e6f1e-124">Post pick from a warehouse pick document and post shipment from a warehouse shipment document</span></span>||<span data-ttu-id="e6f1e-125">X</span><span class="sxs-lookup"><span data-stu-id="e6f1e-125">X</span></span>|<span data-ttu-id="e6f1e-126">X</span><span class="sxs-lookup"><span data-stu-id="e6f1e-126">X</span></span>|<span data-ttu-id="e6f1e-127">4/5/6</span><span class="sxs-lookup"><span data-stu-id="e6f1e-127">4/5/6</span></span>|  

<span data-ttu-id="e6f1e-128">Pour plus d'informations, reportez\-vous à [Détails de conception : flux de désenlogement](design-details-outbound-warehouse-flow.md).</span><span class="sxs-lookup"><span data-stu-id="e6f1e-128">For more information, see [Design Details: Outbound Warehouse Flow](design-details-outbound-warehouse-flow.md).</span></span>  

<span data-ttu-id="e6f1e-129">La procédure pas à pas suivante illustre la méthode B dans la table précédente.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-129">The following walkthrough demonstrates method B in the previous table.</span></span>  

## <a name="about-this-walkthrough"></a><span data-ttu-id="e6f1e-130">À propos de cette procédure pas à pas</span><span class="sxs-lookup"><span data-stu-id="e6f1e-130">About This Walkthrough</span></span>

<span data-ttu-id="e6f1e-131">Pour les configurations d'entrepôt de base, lorsqu'un emplacement est défini pour exiger un traitement des prélèvements mais pas un traitement des livraisons, vous utilisez la page **Prélèvement inventaire** pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents origine sortants.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-131">In basic warehouse configurations where your location is set up to require pick processing but not ship processing, you use the **Inventory Pick** page to record and post pick and ship information for your outbound source documents.</span></span> <span data-ttu-id="e6f1e-132">Le document origine sortant peut être un document de vente, un retour achat, un transfert sortant ou un bon de production avec un besoin de composantes.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-132">The outbound source document can be a sales order, purchase return order, outbound transfer order, or a production order with component need.</span></span>  

<span data-ttu-id="e6f1e-133">Cette procédure pas à pas présente les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="e6f1e-133">This walkthrough demonstrates the following tasks:</span></span>  

- <span data-ttu-id="e6f1e-134">Configuration d'un emplacement ARGENT pour les prélèvements inventaire.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-134">Setting up SILVER location for inventory picks.</span></span>  
- <span data-ttu-id="e6f1e-135">Créez un document de vente pour le client 10000 pour 30 haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-135">Creating a sales order for customer 10000 for 30 loudspeakers.</span></span>  
- <span data-ttu-id="e6f1e-136">Libération du document de vente pour la gestion entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-136">Releasing the sales order for warehouse handling.</span></span>  
- <span data-ttu-id="e6f1e-137">Créez un prélèvement inventaire sur la base d'un document origine libéré.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-137">Creating an inventory pick based on a released source document.</span></span>  
- <span data-ttu-id="e6f1e-138">Enregistrement d'un mouvement entrepôt à partir de l'entrepôt et report simultané de la livraison vente pour le document de vente d'origine.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-138">Registering the warehouse movement from the warehouse and at the same time posting the sales shipment for the source sales order.</span></span>  

## <a name="roles"></a><span data-ttu-id="e6f1e-139">Rôles</span><span class="sxs-lookup"><span data-stu-id="e6f1e-139">Roles</span></span>

<span data-ttu-id="e6f1e-140">Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :</span><span class="sxs-lookup"><span data-stu-id="e6f1e-140">This walkthrough demonstrates tasks that are performed by the following user roles:</span></span>  

- <span data-ttu-id="e6f1e-141">Gestionnaire d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="e6f1e-141">Warehouse Manager</span></span>  
- <span data-ttu-id="e6f1e-142">Préparateur de commandes</span><span class="sxs-lookup"><span data-stu-id="e6f1e-142">Order Processor</span></span>  
- <span data-ttu-id="e6f1e-143">Magasinier</span><span class="sxs-lookup"><span data-stu-id="e6f1e-143">Warehouse Worker</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="e6f1e-144">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="e6f1e-144">Prerequisites</span></span>

<span data-ttu-id="e6f1e-145">Pour exécuter ce processus pas à pas, vous devez :</span><span class="sxs-lookup"><span data-stu-id="e6f1e-145">To complete this walkthrough, you will need:</span></span>  

- <span data-ttu-id="e6f1e-146">Pour [!INCLUDE[prodshort](includes/prodshort.md)] en ligne, une compagnie basée sur l'option **Évaluation avancée - exemples de données complètes** dans un environnement sandbox.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-146">For [!INCLUDE[prodshort](includes/prodshort.md)] online, a company based on the **Advanced Evaluation - Complete Sample Data** option in a sandbox environment.</span></span> <span data-ttu-id="e6f1e-147">Pour [!INCLUDE[prodshort](includes/prodshort.md)] sur site, CRONUS International Ltd. installé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-147">For [!INCLUDE[prodshort](includes/prodshort.md)] on-premises, CRONUS International Ltd. installed.</span></span>  
- <span data-ttu-id="e6f1e-148">Pour devenir employé d'entrepôt dans un emplacement ARGENT, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="e6f1e-148">To make yourself a warehouse employee at the location SILVER by following these steps:</span></span>  

  1. <span data-ttu-id="e6f1e-149">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Employés d'entrepôt**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-149">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Warehouse Employees**, and then choose the related link.</span></span>  
  2. <span data-ttu-id="e6f1e-150">Choisissez le champ **Code utilisateur** et sélectionnez votre propre compte utilisateur sur la page **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-150">Choose the **User ID** field, and select your own user account on the **Users** page.</span></span>  
  3. <span data-ttu-id="e6f1e-151">Dans le champ **Code magasin**, entrez ARGENT.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-151">In the **Location Code** field, enter SILVER.</span></span>  
  4. <span data-ttu-id="e6f1e-152">Sélectionnez le champ **Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-152">Select the **Default** field.</span></span>  

- <span data-ttu-id="e6f1e-153">Rend l'article LS-81 disponible dans l'emplacement ARGENT en suivant cette procédure :</span><span class="sxs-lookup"><span data-stu-id="e6f1e-153">Make item LS-81 available at SILVER location by following these steps:</span></span>  

  1. <span data-ttu-id="e6f1e-154">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journaux article**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-154">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Item Journals**, and then choose the related link.</span></span>  
  2. <span data-ttu-id="e6f1e-155">Ouvrez le journal par défaut, puis créez deux lignes journal article avec les informations de date de travail suivantes (23 janvier).</span><span class="sxs-lookup"><span data-stu-id="e6f1e-155">Open the default journal, and then create two item journal lines with the following information about the work date (January 23).</span></span>  

        |<span data-ttu-id="e6f1e-156">Type écriture</span><span class="sxs-lookup"><span data-stu-id="e6f1e-156">Entry Type</span></span>|<span data-ttu-id="e6f1e-157">Numéro d'article</span><span class="sxs-lookup"><span data-stu-id="e6f1e-157">Item Number</span></span>|<span data-ttu-id="e6f1e-158">Code d'emplacement</span><span class="sxs-lookup"><span data-stu-id="e6f1e-158">Location Code</span></span>|<span data-ttu-id="e6f1e-159">Code de zone</span><span class="sxs-lookup"><span data-stu-id="e6f1e-159">Bin Code</span></span>|<span data-ttu-id="e6f1e-160">Quantité</span><span class="sxs-lookup"><span data-stu-id="e6f1e-160">Quantity</span></span>|  
        |----------------|-----------------|-------------------|--------------|--------------|  
        |<span data-ttu-id="e6f1e-161">Positif (ajust.)</span><span class="sxs-lookup"><span data-stu-id="e6f1e-161">Positive Adjmt.</span></span>|<span data-ttu-id="e6f1e-162">LS-81</span><span class="sxs-lookup"><span data-stu-id="e6f1e-162">LS-81</span></span>|<span data-ttu-id="e6f1e-163">ARGENTE</span><span class="sxs-lookup"><span data-stu-id="e6f1e-163">SILVER</span></span>|<span data-ttu-id="e6f1e-164">S-01-0001</span><span class="sxs-lookup"><span data-stu-id="e6f1e-164">S-01-0001</span></span>|<span data-ttu-id="e6f1e-165">20</span><span class="sxs-lookup"><span data-stu-id="e6f1e-165">20</span></span>|  
        |<span data-ttu-id="e6f1e-166">Positif (ajust.)</span><span class="sxs-lookup"><span data-stu-id="e6f1e-166">Positive Adjmt.</span></span>|<span data-ttu-id="e6f1e-167">LS-81</span><span class="sxs-lookup"><span data-stu-id="e6f1e-167">LS-81</span></span>|<span data-ttu-id="e6f1e-168">ARGENTE</span><span class="sxs-lookup"><span data-stu-id="e6f1e-168">SILVER</span></span>|<span data-ttu-id="e6f1e-169">S-01-0002</span><span class="sxs-lookup"><span data-stu-id="e6f1e-169">S-01-0002</span></span>|<span data-ttu-id="e6f1e-170">20</span><span class="sxs-lookup"><span data-stu-id="e6f1e-170">20</span></span>|  

  3. <span data-ttu-id="e6f1e-171">Choisissez l'action **Reporter**, puis cliquez sur le bouton **Oui**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-171">Choose the **Post** action, and then select the **Yes** button.</span></span>  

## <a name="story"></a><span data-ttu-id="e6f1e-172">Scénario</span><span class="sxs-lookup"><span data-stu-id="e6f1e-172">Story</span></span>

<span data-ttu-id="e6f1e-173">Ellen, la gestionnaire d'entrepôt de CRONUS, configure l'entrepôt ARGENT pour le prélèvement de base dans lequel les magasiniers traitent les commandes sortantes individuellement.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-173">Ellen, the warehouse manager at CRONUS, sets up SILVER warehouse for basic pick handling where warehouse workers process outbound orders individually.</span></span> <span data-ttu-id="e6f1e-174">Susan, préparatrice de commandes, crée un document de vente pour 30 unités de l'article LS-81 à livrer au client 10000 depuis l'entrepôt ARGENT.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-174">Susan, the order processor, creates a sales order for 30 units of item LS-81 to be shipped to customer 10000 from the SILVER Warehouse.</span></span> <span data-ttu-id="e6f1e-175">Jean, le magasinier, doit s'assurer que la livraison est préparée et livrée au client.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-175">John, the warehouse worker must make sure that the shipment is prepared and delivered to the customer.</span></span> <span data-ttu-id="e6f1e-176">Jean gère toutes les tâches impliquées sur la page **Prélèvement inventaire**, qui indique automatiquement les zones où LS-81 est stocké.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-176">John manages all involved tasks on the **Inventory Pick** page, which automatically points to the bins where LS-81 is stored.</span></span>  

## <a name="setting-up-the-location"></a><span data-ttu-id="e6f1e-177">Configuration de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="e6f1e-177">Setting Up the Location</span></span>

<span data-ttu-id="e6f1e-178">La configuration de la page **Fiche emplacement** définit les flux d'entrepôt de la compagnie.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-178">The setup of the **Location Card** page defines the company’s warehouse flows.</span></span>  

### <a name="to-set-up-the-location"></a><span data-ttu-id="e6f1e-179">Pour configurer l'emplacement</span><span class="sxs-lookup"><span data-stu-id="e6f1e-179">To set up the location</span></span>

1. <span data-ttu-id="e6f1e-180">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacements**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-180">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Locations**, and then choose the related link.</span></span>  
2. <span data-ttu-id="e6f1e-181">Ouvrez la fiche emplacement ARGENT.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-181">Open the SILVER location card.</span></span>  
3. <span data-ttu-id="e6f1e-182">Sur le raccourci **Entrepôt**, cochez la case **Prélèvement requis**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-182">On the **Warehouse** FastTab, choose the **Require Pick** check box.</span></span>  

## <a name="creating-the-sales-order"></a><span data-ttu-id="e6f1e-183">Création du document de vente</span><span class="sxs-lookup"><span data-stu-id="e6f1e-183">Creating the Sales Order</span></span>

<span data-ttu-id="e6f1e-184">Les commandes vente sont le type de document d'origine sortant le plus répandu.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-184">Sales orders are the most common type of outbound source document.</span></span>  

### <a name="to-create-the-sales-order"></a><span data-ttu-id="e6f1e-185">Pour créer le document de vente</span><span class="sxs-lookup"><span data-stu-id="e6f1e-185">To create the sales order</span></span>

1. <span data-ttu-id="e6f1e-186">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-186">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2. <span data-ttu-id="e6f1e-187">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-187">Choose the **New** action.</span></span>  
3. <span data-ttu-id="e6f1e-188">Créez une document de vente pour le client 10000 à la date de travail (23 janvier) comportant la ligne document de vente suivante.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-188">Create a sales order for customer 10000 on the work date (January 23) with the following sales order line.</span></span>  

    |<span data-ttu-id="e6f1e-189">Article</span><span class="sxs-lookup"><span data-stu-id="e6f1e-189">Item</span></span>|<span data-ttu-id="e6f1e-190">Code d'emplacement</span><span class="sxs-lookup"><span data-stu-id="e6f1e-190">Location Code</span></span>|<span data-ttu-id="e6f1e-191">Quantité</span><span class="sxs-lookup"><span data-stu-id="e6f1e-191">Quantity</span></span>|  
    |----|-------------|--------|  
    |<span data-ttu-id="e6f1e-192">LS_81</span><span class="sxs-lookup"><span data-stu-id="e6f1e-192">LS_81</span></span>|<span data-ttu-id="e6f1e-193">ARGENTE</span><span class="sxs-lookup"><span data-stu-id="e6f1e-193">SILVER</span></span>|<span data-ttu-id="e6f1e-194">30</span><span class="sxs-lookup"><span data-stu-id="e6f1e-194">30</span></span>|  

     <span data-ttu-id="e6f1e-195">Informez l'entrepôt que le document de vente est prêt pour la gestion entrepôt.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-195">Proceed to notify the warehouse that the sales order is ready for warehouse handling.</span></span>  

4. <span data-ttu-id="e6f1e-196">Sélectionnez l'action **Lancer**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-196">Choose the **Release** action.</span></span>  

    <span data-ttu-id="e6f1e-197">Jean procède au prélèvement et à la livraison des articles vendus.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-197">John proceeds to pick and ship the sold items.</span></span>  

## <a name="picking-and-shipping-items"></a><span data-ttu-id="e6f1e-198">Prélèvement et livraison d'articles</span><span class="sxs-lookup"><span data-stu-id="e6f1e-198">Picking and Shipping Items</span></span>

<span data-ttu-id="e6f1e-199">Sur la page **Prélèvement inventaire**, vous pouvez gérer toutes les activités entrepôt sortantes pour un document d'origine spécifique, tel qu'un document de vente.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-199">On the **Inventory Pick** page, you can manage all outbound warehouse activities for a specific source document, such as a sales order.</span></span> [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

### <a name="to-pick-and-ship-items"></a><span data-ttu-id="e6f1e-200">Pour prélever et livrer des articles</span><span class="sxs-lookup"><span data-stu-id="e6f1e-200">To pick and ship items</span></span>

1. <span data-ttu-id="e6f1e-201">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvements inventaire**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-201">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Picks**, and then choose the related link.</span></span>  
2. <span data-ttu-id="e6f1e-202">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-202">Choose the **New** action.</span></span>  

    <span data-ttu-id="e6f1e-203">Assurez-vous que le champ **N°**</span><span class="sxs-lookup"><span data-stu-id="e6f1e-203">Make sure that the **No.**</span></span> <span data-ttu-id="e6f1e-204">du raccourci **Général** est rempli.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-204">field on the **General** FastTab is filled in.</span></span>
3. <span data-ttu-id="e6f1e-205">Sélectionnez le champ **Document origine**, puis sélectionnez **Commande vente**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-205">Select the **Source Document** field, and then select **Sales Order**.</span></span>  
4. <span data-ttu-id="e6f1e-206">Sélectionnez le champ **N° origine**, sélectionnez la ligne correspondant à la vente au client 10000, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-206">Select the **Source No.** field, select the line for the sale to customer 10000, and then choose the **OK** button.</span></span>  

    <span data-ttu-id="e6f1e-207">Sinon, choisissez l'action **Extraire document origine**, puis sélectionnez le document de vente.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-207">Alternatively, choose the **Get Source Document** action, and then select the sales order.</span></span>  
5. <span data-ttu-id="e6f1e-208">Choisissez l'action **Remplir automatiquement la quantité à traiter**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-208">Choose the **Autofill Qty. to Handle** action.</span></span>  

    <span data-ttu-id="e6f1e-209">Sinon, dans le champ **Qté à traiter**, saisissez respectivement 10 et 20 sur les deux lignes prélèvement stock.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-209">Alternatively, in the **Qty. to Handle** field, enter 10 and 20 respectively on the two inventory pick lines.</span></span>  
6. <span data-ttu-id="e6f1e-210">Choisissez l'action **Reporter**, sélectionnez **Livrer**, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-210">Choose the **Post** action, select **Ship**, and then choose the **OK** button.</span></span>  

    <span data-ttu-id="e6f1e-211">Les 30 haut-parleurs sont à présent enregistrés comme prélevés depuis les zones S-01-0001 et S-01-0002, et une écriture article négative est créée pour refléter la livraison vente reportée.</span><span class="sxs-lookup"><span data-stu-id="e6f1e-211">The 30 loudspeakers are now registered as picked from bins S-01-0001 and S-01-0002, and a negative item ledger entry is created reflecting the posted sales shipment.</span></span>  

## <a name="see-also"></a><span data-ttu-id="e6f1e-212">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e6f1e-212">See Also</span></span>

[<span data-ttu-id="e6f1e-213">Prélever des articles avec les prélèvements inventaire</span><span class="sxs-lookup"><span data-stu-id="e6f1e-213">Pick Items with Inventory Picks</span></span>](warehouse-how-to-pick-items-with-inventory-picks.md)  
[<span data-ttu-id="e6f1e-214">Prélever des articles pour une livraison entrepôt</span><span class="sxs-lookup"><span data-stu-id="e6f1e-214">Pick Items for Warehouse Shipment</span></span>](warehouse-how-to-pick-items-for-warehouse-shipment.md)  
[<span data-ttu-id="e6f1e-215">Configurer des entrepôts de base avec les zones d'opérations</span><span class="sxs-lookup"><span data-stu-id="e6f1e-215">Set Up Basic Warehouses with Operations Areas</span></span>](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md)  
[<span data-ttu-id="e6f1e-216">Déplacer les composantes vers une zone opérations dans les configurations de stockage de base</span><span class="sxs-lookup"><span data-stu-id="e6f1e-216">Move Components to an Operation Area in Basic Warehouse Configurations</span></span>](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  
[<span data-ttu-id="e6f1e-217">Prélever pour la fabrication et l'assemblage</span><span class="sxs-lookup"><span data-stu-id="e6f1e-217">Pick for Production or Assembly</span></span>](warehouse-how-to-pick-for-production.md)  
[<span data-ttu-id="e6f1e-218">Déplacer des articles ad hoc dans les configurations de stockage de base</span><span class="sxs-lookup"><span data-stu-id="e6f1e-218">Move Items Ad Hoc in Basic Warehouse Configurations</span></span>](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)  
[<span data-ttu-id="e6f1e-219">Détails de conception : flux de désenlogement</span><span class="sxs-lookup"><span data-stu-id="e6f1e-219">Design Details: Outbound Warehouse Flow</span></span>](design-details-outbound-warehouse-flow.md)  
[<span data-ttu-id="e6f1e-220">Procédures pas à pas liées au processus entreprise</span><span class="sxs-lookup"><span data-stu-id="e6f1e-220">Business Process Walkthroughs</span></span>](walkthrough-business-process-walkthroughs.md)  
<span data-ttu-id="e6f1e-221">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="e6f1e-221">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
