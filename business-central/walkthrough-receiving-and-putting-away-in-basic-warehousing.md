---
title: "Procédure pas à pas : Réception et rangement dans les configurations de stockage de base | Microsoft Docs"
description: "Dans Business Central, les processus entrants de réception et de rangement peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: e1b6b57448264bddee9bdfc4a81a2f926a7938c7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="walkthrough-receiving-and-putting-away-in-basic-warehouse-configurations"></a><span data-ttu-id="0b097-103">Procédure pas à pas : Réception et rangement dans les configurations de stockage de base</span><span class="sxs-lookup"><span data-stu-id="0b097-103">Walkthrough: Receiving and Putting Away in Basic Warehouse Configurations</span></span>
<span data-ttu-id="0b097-104">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les processus entrants de réception et de rangement peuvent être effectués de quatre manières, à l'aide de différentes fonctionnalités en fonction du niveau de complexité de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0b097-104">In [!INCLUDE[d365fin](includes/d365fin_md.md)], the inbound processes for receiving and putting away can be performed in four ways using different functionalities depending on the warehouse complexity level.</span></span>  

|<span data-ttu-id="0b097-105">Méthode</span><span class="sxs-lookup"><span data-stu-id="0b097-105">Method</span></span>|<span data-ttu-id="0b097-106">Processus entrant</span><span class="sxs-lookup"><span data-stu-id="0b097-106">Inbound process</span></span>|<span data-ttu-id="0b097-107">Zones</span><span class="sxs-lookup"><span data-stu-id="0b097-107">Bins</span></span>|<span data-ttu-id="0b097-108">Reçus</span><span class="sxs-lookup"><span data-stu-id="0b097-108">Receipts</span></span>|<span data-ttu-id="0b097-109">Rangements</span><span class="sxs-lookup"><span data-stu-id="0b097-109">Put-aways</span></span>|<span data-ttu-id="0b097-110">Niveau de complexité (Voir [Détails de conception : configuration d'entrepôt](design-details-warehouse-setup.md))</span><span class="sxs-lookup"><span data-stu-id="0b097-110">Complexity level (See [Design Details: Warehouse Setup](design-details-warehouse-setup.md))</span></span>|  
|------------|---------------------|----------|--------------|----------------|--------------------------------------------------------------------------------------------------------------------|  
|<span data-ttu-id="0b097-111">A</span><span class="sxs-lookup"><span data-stu-id="0b097-111">A</span></span>|<span data-ttu-id="0b097-112">Report de la réception et du rangement à partir de la ligne commande</span><span class="sxs-lookup"><span data-stu-id="0b097-112">Post receipt and put-away from the order line</span></span>|<span data-ttu-id="0b097-113">X</span><span class="sxs-lookup"><span data-stu-id="0b097-113">X</span></span>|||<span data-ttu-id="0b097-114">2</span><span class="sxs-lookup"><span data-stu-id="0b097-114">2</span></span>|  
|<span data-ttu-id="0b097-115">B</span><span class="sxs-lookup"><span data-stu-id="0b097-115">B</span></span>|<span data-ttu-id="0b097-116">Report de la réception et du rangement à partir d'un document de rangement inventaire</span><span class="sxs-lookup"><span data-stu-id="0b097-116">Post receipt and put-away from an inventory put-away document</span></span>|||<span data-ttu-id="0b097-117">X</span><span class="sxs-lookup"><span data-stu-id="0b097-117">X</span></span>|<span data-ttu-id="0b097-118">3</span><span class="sxs-lookup"><span data-stu-id="0b097-118">3</span></span>|  
|<span data-ttu-id="0b097-119">C</span><span class="sxs-lookup"><span data-stu-id="0b097-119">C</span></span>|<span data-ttu-id="0b097-120">Report de la réception et du rangement à partir d'un document réception entrepôt</span><span class="sxs-lookup"><span data-stu-id="0b097-120">Post receipt and put-away from a warehouse receipt document</span></span>||<span data-ttu-id="0b097-121">X</span><span class="sxs-lookup"><span data-stu-id="0b097-121">X</span></span>||<span data-ttu-id="0b097-122">4/5/6</span><span class="sxs-lookup"><span data-stu-id="0b097-122">4/5/6</span></span>|  
|<span data-ttu-id="0b097-123">J</span><span class="sxs-lookup"><span data-stu-id="0b097-123">D</span></span>|<span data-ttu-id="0b097-124">Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt</span><span class="sxs-lookup"><span data-stu-id="0b097-124">Post receipt from a warehouse receipt document and post put-away from a warehouse put-away document</span></span>||<span data-ttu-id="0b097-125">X</span><span class="sxs-lookup"><span data-stu-id="0b097-125">X</span></span>|<span data-ttu-id="0b097-126">X</span><span class="sxs-lookup"><span data-stu-id="0b097-126">X</span></span>|<span data-ttu-id="0b097-127">4/5/6</span><span class="sxs-lookup"><span data-stu-id="0b097-127">4/5/6</span></span>|  

<span data-ttu-id="0b097-128">Pour plus d'informations, reportez\-vous à [Détails de conception : flux d'enlogement](design-details-inbound-warehouse-flow.md).</span><span class="sxs-lookup"><span data-stu-id="0b097-128">For more information, see [Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md).</span></span>  

<span data-ttu-id="0b097-129">La procédure pas à pas suivante illustre la méthode B dans la table précédente.</span><span class="sxs-lookup"><span data-stu-id="0b097-129">The following walkthrough demonstrates method B in the previous table.</span></span>  

## <a name="about-this-walkthrough"></a><span data-ttu-id="0b097-130">À propos de cette procédure pas à pas</span><span class="sxs-lookup"><span data-stu-id="0b097-130">About This Walkthrough</span></span>  
<span data-ttu-id="0b097-131">Pour les configurations entrepôt de base, lorsque votre emplacement est configuré pour exiger un traitement des rangements mais pas un traitement des réceptions, vous utilisez la fenêtre **Rangement inventaire** pour enregistrer et reporter les informations de rangement et de réception pour vos documents sources entrants.</span><span class="sxs-lookup"><span data-stu-id="0b097-131">In basic warehouse configurations where your location is set up to require put-away processing but not receive processing, you use the **Inventory Put-away** window to record and post put-away and receipt information for your inbound source documents.</span></span> <span data-ttu-id="0b097-132">Le document source entrant peut être un bon de commande, un retour vente, un ordre de transfert entrant ou un bon de production dont la production est prête à être rangée.</span><span class="sxs-lookup"><span data-stu-id="0b097-132">The inbound source document can be a purchase order, sales return order, inbound transfer order, or production order with output that is ready to be put away.</span></span>

> [!NOTE]
> <span data-ttu-id="0b097-133">Bien que les paramètres soient appelés **Prélèvement requis** et **Rangement requis**, vous pouvez quand même reporter les réceptions et les livraisons directement à partir des documents commerciaux sources dans les emplacements où vous cochez ces cases.</span><span class="sxs-lookup"><span data-stu-id="0b097-133">Even though the settings are called **Require Pick** and **Require Put-away**, you can still post receipts and shipments directly from the source business documents at locations where you select these check boxes.</span></span>  

<span data-ttu-id="0b097-134">Cette procédure pas à pas présente les tâches suivantes.</span><span class="sxs-lookup"><span data-stu-id="0b097-134">This walkthrough demonstrates the following tasks.</span></span>  

-   <span data-ttu-id="0b097-135">Configuration de l'emplacement ARGENT pour les rangements inventaire.</span><span class="sxs-lookup"><span data-stu-id="0b097-135">Setting up SILVER location for inventory put aways.</span></span>  
-   <span data-ttu-id="0b097-136">Configuration de l'emplacement ARGENT pour la gestion de zone.</span><span class="sxs-lookup"><span data-stu-id="0b097-136">Setting up SILVER location for bin handling.</span></span>  
-   <span data-ttu-id="0b097-137">Définissez une zone par défaut pour l'article LS-81.</span><span class="sxs-lookup"><span data-stu-id="0b097-137">Defining a default bin for item LS-81.</span></span> <span data-ttu-id="0b097-138">(LS-75 est déjà défini dans CRONUS.)</span><span class="sxs-lookup"><span data-stu-id="0b097-138">(LS-75 is already set up in CRONUS.)</span></span>  
-   <span data-ttu-id="0b097-139">Créez un bon de commande pour le fournisseur 10 000 pour 40 haut-parleurs.</span><span class="sxs-lookup"><span data-stu-id="0b097-139">Creating a purchase order for vendor 10000 for 40 loudspeakers.</span></span>  
-   <span data-ttu-id="0b097-140">Vérifier que les zones de rangement sont prédéfinies par la configuration.</span><span class="sxs-lookup"><span data-stu-id="0b097-140">Verifying that the put-away bins are preset by setup.</span></span>  
-   <span data-ttu-id="0b097-141">Lancement du bon de commande pour le traitement en entrepôt.</span><span class="sxs-lookup"><span data-stu-id="0b097-141">Releasing the purchase order for warehouse handling.</span></span>  
-   <span data-ttu-id="0b097-142">Création d'un rangement inventaire sur la base d'un document source libéré.</span><span class="sxs-lookup"><span data-stu-id="0b097-142">Creating an inventory put-away based on a released source document.</span></span>  
-   <span data-ttu-id="0b097-143">Vérifier que les zones de rangement sont héritées du bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0b097-143">Verifying that the put-away bins are inherited from the purchase order.</span></span>  
-   <span data-ttu-id="0b097-144">Enregistrement d'un mouvement entrepôt dans l'entrepôt et en même temps report de la réception achat pour le bon de commande d'origine.</span><span class="sxs-lookup"><span data-stu-id="0b097-144">Registering the warehouse movement into the warehouse and at the same time posting the purchase receipt for the source purchase order.</span></span>  

## <a name="roles"></a><span data-ttu-id="0b097-145">Rôles</span><span class="sxs-lookup"><span data-stu-id="0b097-145">Roles</span></span>  
<span data-ttu-id="0b097-146">Cette procédure pas à pas présente les tâches effectuées par les rôles utilisateur suivants :</span><span class="sxs-lookup"><span data-stu-id="0b097-146">This walkthrough demonstrates tasks that are performed by the following user roles:</span></span>  

-   <span data-ttu-id="0b097-147">Gestionnaire d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="0b097-147">Warehouse Manager</span></span>  
-   <span data-ttu-id="0b097-148">Agent d'achats</span><span class="sxs-lookup"><span data-stu-id="0b097-148">Purchasing Agent</span></span>  
-   <span data-ttu-id="0b097-149">Magasinier</span><span class="sxs-lookup"><span data-stu-id="0b097-149">Warehouse Worker</span></span>  

## <a name="prerequisites"></a><span data-ttu-id="0b097-150">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="0b097-150">Prerequisites</span></span>  
<span data-ttu-id="0b097-151">Pour exécuter ce processus pas à pas, vous devez :</span><span class="sxs-lookup"><span data-stu-id="0b097-151">To complete this walkthrough, you will need:</span></span>  

-   <span data-ttu-id="0b097-152">avoir CRONUS International Ltd. installé.</span><span class="sxs-lookup"><span data-stu-id="0b097-152">CRONUS International Ltd. installed.</span></span>  
-   <span data-ttu-id="0b097-153">Pour devenir magasinier dans un emplacement ARGENT, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0b097-153">To make yourself a warehouse employee at SILVER location by following these steps:</span></span>  

    1.  <span data-ttu-id="0b097-154">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Employés entrepôt**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0b097-154">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Warehouse Employees**, and then choose the related link.</span></span>  
    2.  <span data-ttu-id="0b097-155">Choisissez le champ **ID utilisateur** et sélectionnez votre propre compte utilisateur dans la fenêtre **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="0b097-155">Choose the **User ID** field, and select your own user account in the **Users** window.</span></span>  
    3.  <span data-ttu-id="0b097-156">Dans le champ **Code magasin**, entrez ARGENT.</span><span class="sxs-lookup"><span data-stu-id="0b097-156">In the **Location Code** field, enter SILVER.</span></span>  
    4.  <span data-ttu-id="0b097-157">Sélectionnez le champ **Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="0b097-157">Select the **Default** field.</span></span>  

## <a name="story"></a><span data-ttu-id="0b097-158">Scénario</span><span class="sxs-lookup"><span data-stu-id="0b097-158">Story</span></span>  
<span data-ttu-id="0b097-159">Ellen, responsable d'entrepôt chez CRONUS International Ltd., crée un bon de commande de 10 unités de l'article LS-75 et 30 unités de l'article LS-81 du fournisseur 10000, qui doivent être approvisionnés à l'entrepôt ARGENT.</span><span class="sxs-lookup"><span data-stu-id="0b097-159">Ellen, the warehouse manager at CRONUS International Ltd., creates a purchase order for 10 units of item LS-75 and 30 units of item LS-81 from vendor 10000 to be delivered to SILVER Warehouse.</span></span> <span data-ttu-id="0b097-160">Lorsque la livraison arrive à l'entrepôt, Jean, l'employé de l'entrepôt, range les articles dans les zones par défaut définies pour les articles.</span><span class="sxs-lookup"><span data-stu-id="0b097-160">When the delivery arrives at the warehouse, John, the warehouse worker, puts the items away in default bins defined for the items.</span></span> <span data-ttu-id="0b097-161">Lorsque Jean reporte le rangement, les articles sont reportés comme étant reçus dans l'inventaire et disponibles à la vente ou pour d'autres demandes.</span><span class="sxs-lookup"><span data-stu-id="0b097-161">When John posts the put-away, the items are posted as received into inventory and available for sale or other demand.</span></span>  

## <a name="setting-up-the-location"></a><span data-ttu-id="0b097-162">Configuration de l'emplacement</span><span class="sxs-lookup"><span data-stu-id="0b097-162">Setting up the Location</span></span>  
 <span data-ttu-id="0b097-163">La configuration de la fenêtre **Fiche magasin** définit les flux d'entrepôt de la société.</span><span class="sxs-lookup"><span data-stu-id="0b097-163">The setup of the **Location Card** window defines the company’s warehouse flows.</span></span>  

### <a name="to-set-up-the-location"></a><span data-ttu-id="0b097-164">Pour configurer l'emplacement</span><span class="sxs-lookup"><span data-stu-id="0b097-164">To set up the location</span></span>  

1.  <span data-ttu-id="0b097-165">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="0b097-165">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Locations**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="0b097-166">Ouvrez la fiche emplacement ARGENT.</span><span class="sxs-lookup"><span data-stu-id="0b097-166">Open the SILVER location card.</span></span>  
3.  <span data-ttu-id="0b097-167">Activez la case à cocher **Rangement requis**.</span><span class="sxs-lookup"><span data-stu-id="0b097-167">Select the **Require Put-away** check box.</span></span>  

    <span data-ttu-id="0b097-168">Configurez une zone par défaut pour les deux numéros d'article afin de contrôler l'endroit où ils sont rangés.</span><span class="sxs-lookup"><span data-stu-id="0b097-168">Proceed to set up a default bin for the two item numbers to control where they are put away.</span></span>  

4.  <span data-ttu-id="0b097-169">Choisissez l'action **Zones**.</span><span class="sxs-lookup"><span data-stu-id="0b097-169">Choose the **Bins** action.</span></span>  
5.  <span data-ttu-id="0b097-170">Sélectionnez la première ligne, pour la zone S-01-0001, puis choisissez l'action **Contenu**.</span><span class="sxs-lookup"><span data-stu-id="0b097-170">Select the first row, for bin S-01-0001, and then choose the **Contents** action.</span></span>  

    <span data-ttu-id="0b097-171">Remarquez dans la fenêtre **Contenu de la zone** que l'article LS-75 est déjà configuré comme contenu dans la zone S-01-0001.</span><span class="sxs-lookup"><span data-stu-id="0b097-171">Notice in the **Bin Content** window that item LS-75 is already set up as content in bin S-01-0001.</span></span>  

6.  <span data-ttu-id="0b097-172">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0b097-172">Choose the **New** action.</span></span>  
7.  <span data-ttu-id="0b097-173">Sélectionnez les champs **Fixe** et **Par défaut**.</span><span class="sxs-lookup"><span data-stu-id="0b097-173">Select the **Fixed** and the **Default** fields.</span></span>  
8.  <span data-ttu-id="0b097-174">Dans le champ **N° article**, saisissez LS-81.</span><span class="sxs-lookup"><span data-stu-id="0b097-174">In the **Item No.** field, enter LS-81.</span></span>  

## <a name="creating-the-purchase-order"></a><span data-ttu-id="0b097-175">Création du bon de commande</span><span class="sxs-lookup"><span data-stu-id="0b097-175">Creating the Purchase Order</span></span>  
<span data-ttu-id="0b097-176">Les bons de commande sont le type de document source entrant le plus répandu.</span><span class="sxs-lookup"><span data-stu-id="0b097-176">Purchase orders are the most common type of inbound source document.</span></span>  

### <a name="to-create-the-purchase-order"></a><span data-ttu-id="0b097-177">Pour créer le bon de commande</span><span class="sxs-lookup"><span data-stu-id="0b097-177">To create the purchase order</span></span>  

1.  <span data-ttu-id="0b097-178">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Bons de commande**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0b097-178">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Purchase Orders**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="0b097-179">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0b097-179">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="0b097-180">Créez un bon de commande pour le fournisseur 10 000 à la date de travail (23 janvier) comportant les lignes bon de commande suivantes.</span><span class="sxs-lookup"><span data-stu-id="0b097-180">Create a purchase order for vendor 10000 on the work date (January 23) with the following purchase order lines.</span></span>  

    |<span data-ttu-id="0b097-181">Article</span><span class="sxs-lookup"><span data-stu-id="0b097-181">Item</span></span>|<span data-ttu-id="0b097-182">Code d'emplacement</span><span class="sxs-lookup"><span data-stu-id="0b097-182">Location code</span></span>|<span data-ttu-id="0b097-183">Code de zone</span><span class="sxs-lookup"><span data-stu-id="0b097-183">Bin code</span></span>|<span data-ttu-id="0b097-184">Quantité</span><span class="sxs-lookup"><span data-stu-id="0b097-184">Quantity</span></span>|  
    |----------|-------------------|--------------|--------------|  
    |<span data-ttu-id="0b097-185">LS_75</span><span class="sxs-lookup"><span data-stu-id="0b097-185">LS_75</span></span>|<span data-ttu-id="0b097-186">ARGENTE</span><span class="sxs-lookup"><span data-stu-id="0b097-186">SILVER</span></span>|<span data-ttu-id="0b097-187">S-01-0001</span><span class="sxs-lookup"><span data-stu-id="0b097-187">S-01-0001</span></span>|<span data-ttu-id="0b097-188">10</span><span class="sxs-lookup"><span data-stu-id="0b097-188">10</span></span>|  
    |<span data-ttu-id="0b097-189">LS-81</span><span class="sxs-lookup"><span data-stu-id="0b097-189">LS-81</span></span>|<span data-ttu-id="0b097-190">ARGENTE</span><span class="sxs-lookup"><span data-stu-id="0b097-190">SILVER</span></span>|<span data-ttu-id="0b097-191">S-01-0001</span><span class="sxs-lookup"><span data-stu-id="0b097-191">S-01-0001</span></span>|<span data-ttu-id="0b097-192">30</span><span class="sxs-lookup"><span data-stu-id="0b097-192">30</span></span>|  

    > [!NOTE]  
    >  <span data-ttu-id="0b097-193">Le code de zone est renseigné automatiquement en fonction de la configuration effectuée dans la section « Configuration de l'emplacement ».</span><span class="sxs-lookup"><span data-stu-id="0b097-193">The bin code is entered automatically according to the setup that you performed in the “Setting up the Location” section.</span></span>  

    <span data-ttu-id="0b097-194">Informez l'entrepôt que le bon de commande est prêt pour le traitement en entrepôt lorsque la livraison arrive.</span><span class="sxs-lookup"><span data-stu-id="0b097-194">Proceed to notify the warehouse that the purchase order is ready for warehouse handling when the delivery arrives.</span></span>  

4.  <span data-ttu-id="0b097-195">Sélectionnez l'action **Lancer**.</span><span class="sxs-lookup"><span data-stu-id="0b097-195">Choose the **Release** action.</span></span>  

    <span data-ttu-id="0b097-196">La livraison des haut-parleurs provenant du fournisseur 10000 est arrivée dans l'entrepôt ARGENT. Jean procède à leur rangement.</span><span class="sxs-lookup"><span data-stu-id="0b097-196">The delivery of loudspeakers from vendor 10000 has arrived at SILVER warehouse, and John proceeds to put them away.</span></span>  

## <a name="receiving-and-putting-the-items-away"></a><span data-ttu-id="0b097-197">Réception et rangement des articles</span><span class="sxs-lookup"><span data-stu-id="0b097-197">Receiving and Putting the Items Away</span></span>  
<span data-ttu-id="0b097-198">Dans la fenêtre **Rangement inventaire**, vous pouvez gérer toutes les activités enlogement pour un document source spécifique, tel qu'un bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0b097-198">In the **Inventory Put-away** window, you can manage all inbound warehouse activities for a specific source document, such as a purchase order.</span></span>  

### <a name="to-receive-and-put-the-items-away"></a><span data-ttu-id="0b097-199">Pour recevoir et ranger des articles</span><span class="sxs-lookup"><span data-stu-id="0b097-199">To receive and put the items away</span></span>  

1.  <span data-ttu-id="0b097-200">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Rangements stock**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="0b097-200">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Inventory Put-aways**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="0b097-201">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="0b097-201">Choose the **New** action.</span></span>  
3.  <span data-ttu-id="0b097-202">Sélectionnez le champ **Document source**, puis sélectionnez **Bon de commande**.</span><span class="sxs-lookup"><span data-stu-id="0b097-202">Select the **Source Document** field, and then select **Purchase Order**.</span></span>  
4.  <span data-ttu-id="0b097-203">Sélectionnez le champ **N° origine**, sélectionnez la ligne correspondant à l'achat au fournisseur 10000, puis cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b097-203">Select the **Source No.** field, select the line for the purchase from vendor 10000, and then choose the **OK** button.</span></span>  

    <span data-ttu-id="0b097-204">Sinon, sous l'onglet **Actions**, dans le groupe **Fonctions**, choisissez **Extraire document origine**, puis sélectionnez le bon de commande.</span><span class="sxs-lookup"><span data-stu-id="0b097-204">Alternatively, on the **Actions** tab, in the **Functions** group, choose **Get Source Document**, and then select the purchase order.</span></span>  

5.  <span data-ttu-id="0b097-205">Choisissez l'action **Remplir automatiquement la quantité à traiter**.</span><span class="sxs-lookup"><span data-stu-id="0b097-205">Choose the **Autofill Qty. to Handle** action.</span></span>  

    <span data-ttu-id="0b097-206">Sinon, dans le champ **Qté à traiter**, saisissez respectivement 10 et 30 sur les deux lignes rangement inventaire.</span><span class="sxs-lookup"><span data-stu-id="0b097-206">Alternatively, in the **Qty. to Handle** field, enter 10 and 30 respectively on the two inventory put-away lines.</span></span>  

6.  <span data-ttu-id="0b097-207">Choisissez l'action **Reporter**, sélectionnez l'action **Réceptionner**, puis choisissez le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="0b097-207">Choose the **Post** action, select the **Receive** action, and then choose the **OK** button.</span></span>  

    <span data-ttu-id="0b097-208">Les 40 haut-parleurs sont à présent enregistrés comme rangés dans la zone S-01-0001, et une écriture article positive est créée pour refléter la réception achat reportée.</span><span class="sxs-lookup"><span data-stu-id="0b097-208">The 40 loudspeakers are now registered as put away in bin S-01-0001, and a positive item ledger entry is created reflecting the posted purchase receipt.</span></span>  

## <a name="see-also"></a><span data-ttu-id="0b097-209">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0b097-209">See Also</span></span>  
 <span data-ttu-id="0b097-210">[Ranger des articles avec le rangement stock](warehouse-how-to-put-items-away-with-inventory-put-aways.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-210">[Put Items Away with Inventory Put-aways](warehouse-how-to-put-items-away-with-inventory-put-aways.md) </span></span>  
 <span data-ttu-id="0b097-211">[Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-211">[Set Up Basic Warehouses with Operations Areas](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md) </span></span>  
 <span data-ttu-id="0b097-212">[Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-212">[Move Components to an Operation Area in Basic Warehouse Configurations](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md) </span></span>  
 <span data-ttu-id="0b097-213">[Prélever pour la fabrication et l'assemblage](warehouse-how-to-pick-for-production.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-213">[Pick for Production or Assembly](warehouse-how-to-pick-for-production.md) </span></span>  
 <span data-ttu-id="0b097-214">[Déplacer des articles ad hoc dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-214">[Move Items Ad Hoc in Basic Warehouse Configurations](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md) </span></span>  
 <span data-ttu-id="0b097-215">[Détails de conception : flux d'enlogement](design-details-inbound-warehouse-flow.md) </span><span class="sxs-lookup"><span data-stu-id="0b097-215">[Design Details: Inbound Warehouse Flow](design-details-inbound-warehouse-flow.md) </span></span>  
 [<span data-ttu-id="0b097-216">Procédures pas à pas liées au processus entreprise</span><span class="sxs-lookup"><span data-stu-id="0b097-216">Business Process Walkthroughs</span></span>](walkthrough-business-process-walkthroughs.md)  
 <span data-ttu-id="0b097-217">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="0b097-217">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
