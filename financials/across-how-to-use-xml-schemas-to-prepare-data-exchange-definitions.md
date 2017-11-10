---
title: "Créer des objets XMLport basés sur des schémas XML | Microsoft Docs"
description: "Utilisez des schémas XML pour configurer l'infrastructure d'échange de documents."
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: c4b53c6a87148990102ba9eca235cf139a48396e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-use-xml-schemas-to-prepare-data-exchange-definitions"></a><span data-ttu-id="c43f3-103">Procédure : Utiliser des schémas XML pour préparer une définitions d'échange de données</span><span class="sxs-lookup"><span data-stu-id="c43f3-103">How to: Use XML Schemas to Prepare Data Exchange Definitions</span></span>
<span data-ttu-id="c43f3-104">Pour activer l'importation/exportation des données dans des fichiers XML à travers l'infrastructure d'échange de données de [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez utiliser des schémas XML pour définir les éléments de données à échanger avec [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c43f3-104">To enable import/export of data in XML files through the data exchange framework in [!INCLUDE[d365fin](includes/d365fin_md.md)], you can use XML schemas to define which data elements you want to exchange with [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="c43f3-105">Vous effectuez ce travail dans la fenêtre **Visionneuse de schéma XML** en chargeant le fichier de schéma XML, en sélectionnant les éléments de données appropriés, puis en initialisant soit une définition d'échange de données ou un XMLport.</span><span class="sxs-lookup"><span data-stu-id="c43f3-105">You perform this work in the **XML Schema Viewer** window by loading the XML schema file, selecting the relevant data elements, and then initializing either a data exchange definition or an XMLport.</span></span>  

 <span data-ttu-id="c43f3-106">Lorsque vous avez défini les éléments de données à inclure en fonction du schéma XML, vous pouvez utiliser l'action **Générer XMLport** pour créer l'objet XMLport.</span><span class="sxs-lookup"><span data-stu-id="c43f3-106">When you have defined which data elements to include based on the XML schema, you can use the **Generate XMLport** action to create the XMLport object.</span></span>  

 <span data-ttu-id="c43f3-107">Vous pouvez aussi utiliser l'action **Générer définition d'échange de données** pour initialiser une définition d'échange de données basée sur les éléments de données sélectionnés, que vous complétez dans l'infrastructure d'échange de données.</span><span class="sxs-lookup"><span data-stu-id="c43f3-107">Alternatively, you can use the **Generate Data Exchange Definition** action to initialize a data exchange definition based on the selected data elements, which you then complete in the Data Exchange Framework.</span></span> <span data-ttu-id="c43f3-108">Cela crée un enregistrement dans la fenêtre **Définitions échange report** où vous continuez en définissant les éléments de la liste des fichiers qui correspondent aux champs dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c43f3-108">This creates a record in the **Posting Exchange Definition** window where you continue by defining which elements in the file map to which fields in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="c43f3-109">Pour plus d'informations, reportez vous à [Procédure : configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="c43f3-109">For more information, see [How to: Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).</span></span>  

 <span data-ttu-id="c43f3-110">Cette rubrique contient les procédures suivantes :</span><span class="sxs-lookup"><span data-stu-id="c43f3-110">This topic contains the following procedures:</span></span>  

-   <span data-ttu-id="c43f3-111">Charger un fichier de schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-111">To load an XML schema file</span></span>  

-   <span data-ttu-id="c43f3-112">Sélectionner ou supprimer des nœuds dans un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-112">To select or clear nodes in an XML schema</span></span>  

-   <span data-ttu-id="c43f3-113">Générer une définition d'échange de données basée sur un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-113">To generate a data exchange definition that is based on an XML schema</span></span>  

-   <span data-ttu-id="c43f3-114">Générer un XMLport pour le fichier basé sur un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-114">To generate an XMLport for the file that is based on an XML schema</span></span>  

-   <span data-ttu-id="c43f3-115">Pour importer XMLport dans le Générateur d'objets</span><span class="sxs-lookup"><span data-stu-id="c43f3-115">To import an XMLport into the Object Designer</span></span>  

### <a name="to-load-an-xml-schema-file"></a><span data-ttu-id="c43f3-116">Charger un fichier de schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-116">To load an XML schema file</span></span>  

1.  <span data-ttu-id="c43f3-117">Assurez-vous que le fichier de schéma XML approprié est disponible.</span><span class="sxs-lookup"><span data-stu-id="c43f3-117">Make sure that the relevant XML schema file is available.</span></span> <span data-ttu-id="c43f3-118">L'extension du fichier est .xsd.</span><span class="sxs-lookup"><span data-stu-id="c43f3-118">The file extension is .xsd.</span></span>  

2.  <span data-ttu-id="c43f3-119">Dans la zone **Rechercher**, entrez **Schémas XML**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c43f3-119">In the **Search** box, enter **XML Schemas**, and then choose the related link.</span></span>  

3.  <span data-ttu-id="c43f3-120">Sous l'onglet de **Accueil**, dans le groupe **Nouveau**, choisissez **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-120">On the **Home** tab, in the **New** group, choose **New**.</span></span>  

4.  <span data-ttu-id="c43f3-121">Renseignez les champs comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c43f3-121">Fill the fields as described in the following table.</span></span>  

    |<span data-ttu-id="c43f3-122">Champ</span><span class="sxs-lookup"><span data-stu-id="c43f3-122">Field</span></span>|<span data-ttu-id="c43f3-123">[Description]</span><span class="sxs-lookup"><span data-stu-id="c43f3-123">[Description]</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="c43f3-124">**Code**</span><span class="sxs-lookup"><span data-stu-id="c43f3-124">**Code**</span></span>|<span data-ttu-id="c43f3-125">Indiquez un code pour identifier le schéma XML.</span><span class="sxs-lookup"><span data-stu-id="c43f3-125">Specify a code to identify the XML schema.</span></span>|  
    |<span data-ttu-id="c43f3-126">**Description**</span><span class="sxs-lookup"><span data-stu-id="c43f3-126">**Description**</span></span>|<span data-ttu-id="c43f3-127">Spécifiez une description du schéma XML.</span><span class="sxs-lookup"><span data-stu-id="c43f3-127">Specify a description of the XML schema.</span></span>|  

     <span data-ttu-id="c43f3-128">Le champ **Espace de noms cible** spécifie un espace de noms dans le fichier de schéma XML qui a été chargé pour la ligne.</span><span class="sxs-lookup"><span data-stu-id="c43f3-128">The **Target Namespace** field specifies any namespace in the XML schema file that has been loaded for the line.</span></span>  

5.  <span data-ttu-id="c43f3-129">Sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Charger schéma**, puis sélectionnez le fichier de schéma XML.</span><span class="sxs-lookup"><span data-stu-id="c43f3-129">On the **Home** tab, in the **Process** group, choose **Load Schema**, and then select the XML schema file.</span></span>  

     <span data-ttu-id="c43f3-130">Lorsque le fichier est chargé, les autres champs de la ligne sont renseignés à l'aide des informations du fichier, et la case **Le schéma est chargé** est cochée.</span><span class="sxs-lookup"><span data-stu-id="c43f3-130">When the file is loaded, the rest of the fields on the line are filled with information from the file, and the **Schema is Loaded** check box is selected.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="c43f3-131">L'arborescence du schéma XML chargé est réduite par défaut.</span><span class="sxs-lookup"><span data-stu-id="c43f3-131">The tree of the loaded XML schema is collapsed by default.</span></span> <span data-ttu-id="c43f3-132">Vous développez chaque nœud en choisissant le bouton **+** sur le nœud.</span><span class="sxs-lookup"><span data-stu-id="c43f3-132">You expand each node by choosing the **+** button on the node.</span></span> <span data-ttu-id="c43f3-133">Pour développer tous les nœuds, sélectionnez **Développer tout** sur le ruban.</span><span class="sxs-lookup"><span data-stu-id="c43f3-133">To expand all nodes, choose **Expand All** on the ribbon.</span></span>  

### <a name="to-select-or-clear-nodes-in-an-xml-schema"></a><span data-ttu-id="c43f3-134">Sélectionner ou supprimer des nœuds dans un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-134">To select or clear nodes in an XML schema</span></span>  

1.  <span data-ttu-id="c43f3-135">Dans la zone **Rechercher**, entrez **Visionneuse de schéma XML**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c43f3-135">In the **Search** box, enter **XML Schema Viewer**, and then choose the related link.</span></span>  

2.  <span data-ttu-id="c43f3-136">Renseignez les champs de l'en-tête, comme indiqué dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c43f3-136">Fill the fields on the header as described in the following table.</span></span>  

    |<span data-ttu-id="c43f3-137">Champ</span><span class="sxs-lookup"><span data-stu-id="c43f3-137">Field</span></span>|<span data-ttu-id="c43f3-138">Description</span><span class="sxs-lookup"><span data-stu-id="c43f3-138">Description</span></span>|  
    |---------------------------------|---------------------------------------|  
    |<span data-ttu-id="c43f3-139">**Code schéma XML**</span><span class="sxs-lookup"><span data-stu-id="c43f3-139">**XML Schema Code**</span></span>|<span data-ttu-id="c43f3-140">Spécifiez le fichier schéma XML que vous avez chargé à l'étape 5 dans la section « Pour charger un fichier schéma XML ».</span><span class="sxs-lookup"><span data-stu-id="c43f3-140">Specify the XML schema file that you loaded in step 5 in the “To load an XML schema file” section.</span></span>|  
    |<span data-ttu-id="c43f3-141">**Nouveau n° de XMLport**</span><span class="sxs-lookup"><span data-stu-id="c43f3-141">**New XMLport No.**</span></span>|<span data-ttu-id="c43f3-142">Spécifiez le numéro du XMLport qui est créé pour ce schéma XML lorsque vous sélectionnez l'action **Générer XMLport**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-142">Specify the number of the XMLport that is created from this XML schema when you choose the **Generate XMLport** action.</span></span>|  

     <span data-ttu-id="c43f3-143">Les lignes sont à présent remplies avec des nœuds représentant tous les éléments figurant dans le schéma XML.</span><span class="sxs-lookup"><span data-stu-id="c43f3-143">The lines are now filled with nodes representing all elements in the XML schema.</span></span> <span data-ttu-id="c43f3-144">Les nœuds des éléments qui sont obligatoires selon le schéma XML sont activés par défaut.</span><span class="sxs-lookup"><span data-stu-id="c43f3-144">Nodes for elements that are mandatory according to the XML schema are selected by default.</span></span>  

3.  <span data-ttu-id="c43f3-145">Sur la première ligne, dans la colonne **Nom noeud**, développez le nœud **Document**, puis développez progressivement les nœuds sous-jacents que vous souhaitez examiner.</span><span class="sxs-lookup"><span data-stu-id="c43f3-145">On the first line, in the **Node Name** column, expand the **Document** node, and then gradually expand underlying nodes that you want to review.</span></span>  

     <span data-ttu-id="c43f3-146">Sinon, cliquez avec le bouton droit sur un nœud, puis choisissez **Développer tout**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-146">Alternatively, right-click on a node and then choose **Expand All**.</span></span>  

4.  <span data-ttu-id="c43f3-147">Sous l'onglet **Accueil**, dans le groupe **Affichage**, choisissez l'une des actions suivantes pour modifier les nœuds qui sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-147">On the **Home** tab, in the **View** group, choose either of the following actions to change which nodes are displayed.</span></span>  

    |<span data-ttu-id="c43f3-148">**Action**</span><span class="sxs-lookup"><span data-stu-id="c43f3-148">**Action**</span></span>|<span data-ttu-id="c43f3-149">Description</span><span class="sxs-lookup"><span data-stu-id="c43f3-149">Description</span></span>|  
    |----------------|---------------------------------------|  
    |<span data-ttu-id="c43f3-150">**Afficher tout**</span><span class="sxs-lookup"><span data-stu-id="c43f3-150">**Show All**</span></span>|<span data-ttu-id="c43f3-151">Tous les nœuds sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-151">All nodes are shown.</span></span>|  
    |<span data-ttu-id="c43f3-152">**Masquer non obligatoire**</span><span class="sxs-lookup"><span data-stu-id="c43f3-152">**Hide Non-Mandatory**</span></span>|<span data-ttu-id="c43f3-153">Seuls les nœuds représentant les éléments qui sont obligatoires selon le schéma XML sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-153">Only nodes representing elements that are required according to the XML schema are shown.</span></span> <span data-ttu-id="c43f3-154">Les nœuds sont généralement indiqués par un **1** dans le champ **MinOccurs**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-154">These nodes are typically indicated by a **1** in the **MinOccurs** field.</span></span><br /><br /> <span data-ttu-id="c43f3-155">Choisissez **Afficher tout** pour rétablir l'affichage.</span><span class="sxs-lookup"><span data-stu-id="c43f3-155">Choose **Show All** to reverse the view.</span></span>|  
    |<span data-ttu-id="c43f3-156">**Masquer non sélectionné**</span><span class="sxs-lookup"><span data-stu-id="c43f3-156">**Hide Non-Selected**</span></span>|<span data-ttu-id="c43f3-157">Seuls les nœuds dont la case à cocher **Sélectionné** est activée sont affichés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-157">Only nodes where the **Selected** check box is selected are shown.</span></span><br /><br /> <span data-ttu-id="c43f3-158">Choisissez **Afficher tout** pour rétablir l'affichage.</span><span class="sxs-lookup"><span data-stu-id="c43f3-158">Choose **Show All** to reverse the view.</span></span>|  

5.  <span data-ttu-id="c43f3-159">Sous l'onglet **Accueil**, dans le groupe **Gestion**, choisissez **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-159">On the **Home** tab, in the **Manage** group, choose **Edit**.</span></span>  

6.  <span data-ttu-id="c43f3-160">Dans le champ **Sélectionné**, spécifiez pour chaque nœud si vous souhaitez que l'élément soit pris en charge dans la définition d'échange de données pour le fichier bancaire SEPA connexe.</span><span class="sxs-lookup"><span data-stu-id="c43f3-160">In the **Selected** check box, specify for each node if you want the element to be supported in the data exchange definition for the related SEPA bank file.</span></span>  

    > [!NOTE]  
    >  <span data-ttu-id="c43f3-161">Lorsque vous sélectionnez un nœud enfant obligatoire, tous les nœuds parents au-dessus de lui sont également sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-161">When you select a mandatory child node, all parent nodes above it are also selected.</span></span>  

7.  <span data-ttu-id="c43f3-162">Sélectionnez l'action **Sélectionner tous les éléments obligatoires** pour resélectionner tous les nœuds représentant des éléments qui sont obligatoires en fonction du schéma XML.</span><span class="sxs-lookup"><span data-stu-id="c43f3-162">Choose the **Select All Mandatory Elements** action to reselect all nodes that represent elements that are mandatory according to the XML schema.</span></span>  

8.  <span data-ttu-id="c43f3-163">Sélectionnez l'action **Désélectionner tout** pour désactiver toutes les options.</span><span class="sxs-lookup"><span data-stu-id="c43f3-163">Choose the **Deselect All** action to clear all selections.</span></span>  

     <span data-ttu-id="c43f3-164">Le champ **Choix** spécifie que le nœud a deux ou plusieurs nœuds frère qui fonctionnent comme options.</span><span class="sxs-lookup"><span data-stu-id="c43f3-164">The **Choice** field specifies that the node has two or more sibling nodes that function as options.</span></span>  

### <a name="to-generate-a-data-exchange-definition-that-is-based-on-an-xml-schema"></a><span data-ttu-id="c43f3-165">Générer une définition d'échange de données basée sur un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-165">To generate a data exchange definition that is based on an XML schema</span></span>  

1.  <span data-ttu-id="c43f3-166">Dans la zone **Rechercher**, entrez **Schémas XML**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c43f3-166">In the **Search** box, enter  **XML Schemas**, and then choose the related link.</span></span>  

2.  <span data-ttu-id="c43f3-167">Sélectionnez le schéma XML approprié, puis sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Ouvrir visionneuse de schéma XML**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-167">Select the relevant XML schema, and then on the on the **Home** tab, in the **Process** group, choose **Open XML Schema Viewer**.</span></span>  

3.  <span data-ttu-id="c43f3-168">Assurez-vous que les nœuds appropriés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-168">Make sure the relevant nodes are selected.</span></span> <span data-ttu-id="c43f3-169">Pour plus d'informations, reportez-vous à la section « Sélectionner ou supprimer des nœuds dans un schéma XML ».</span><span class="sxs-lookup"><span data-stu-id="c43f3-169">For more information, see the “To select or clear nodes in an XML schema” section.</span></span>  

4.  <span data-ttu-id="c43f3-170">Dans la fenêtre **Visionneuse de schéma XML**, sous l'onglet **Accueil**, dans le groupe **Processus**, sélectionnez **Générer définition d'échange de données**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-170">In the **XML Schema Viewer** window, on the **Home** tab, in the **Process** group, choose **Generate Data Exchange Definition**.</span></span>  

 <span data-ttu-id="c43f3-171">Une définition d'échange de données est créée dans la fenêtre **Définitions échange report**, que vous pouvez renseigner en indiquant les éléments de la liste des fichiers qui correspondent aux champs dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="c43f3-171">A data exchange definition is created in the **Posting Exchange Definition** window, which you can complete by specifying which elements in the file map to which fields in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="c43f3-172">Pour plus d'informations, reportez vous à [Procédure : configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md).</span><span class="sxs-lookup"><span data-stu-id="c43f3-172">For more information, see [How to: Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md).</span></span>  

> [!NOTE]  
>  <span data-ttu-id="c43f3-173">Vous pouvez également utiliser la fonction **Extraire structure de fichiers** de la fenêtre **Définitions échange report**, qui utilise la fonctionnalité de la fenêtre **Visionneuse de schéma XML** pour préremplir le raccourci **Définitions colonne**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-173">You can also use the **Get File Structure** function from the **Posting Exchange Definition** window, which uses the functionality of the **XML Schema Viewer** window to prefill the **Column Definitions** TastTab.</span></span>  

### <a name="to-generate-an-xmlport-that-is-based-on-an-xml-schema"></a><span data-ttu-id="c43f3-174">Générer un XMLport basé sur un schéma XML</span><span class="sxs-lookup"><span data-stu-id="c43f3-174">To generate an XMLport that is based on an XML schema</span></span>  

1.  <span data-ttu-id="c43f3-175">Dans la zone **Rechercher**, entrez **Schémas XML**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c43f3-175">In the **Search** box, enter  **XML Schemas**, and then choose the related link.</span></span>  

2.  <span data-ttu-id="c43f3-176">Sélectionnez le schéma XML approprié, puis sous l'onglet **Accueil**, dans le groupe **Processus**, choisissez **Ouvrir visionneuse de schéma XML**.</span><span class="sxs-lookup"><span data-stu-id="c43f3-176">Select the relevant XML schema, and then on the on the **Home** tab, in the **Process** group, choose **Open XML Schema Viewer**.</span></span>  

3.  <span data-ttu-id="c43f3-177">Dans le champ **Nouveau n° XMLport**,</span><span class="sxs-lookup"><span data-stu-id="c43f3-177">In the **New XMLport No.**</span></span> <span data-ttu-id="c43f3-178">spécifiez le numéro qui sera accordé au nouvel objet XMLport lorsqu'il sera généré.</span><span class="sxs-lookup"><span data-stu-id="c43f3-178">field, specify the number that the new XMLport object will be given when it is generated.</span></span>  

4.  <span data-ttu-id="c43f3-179">Assurez-vous que les nœuds appropriés sont sélectionnés.</span><span class="sxs-lookup"><span data-stu-id="c43f3-179">Make sure the relevant nodes are selected.</span></span> <span data-ttu-id="c43f3-180">Pour plus d'informations, reportez-vous à la section « Sélectionner ou supprimer des nœuds dans un schéma XML ».</span><span class="sxs-lookup"><span data-stu-id="c43f3-180">For more information, see the “To select or clear nodes in an XML schema” section.</span></span>  

5.  <span data-ttu-id="c43f3-181">Sous l'onglet **Accueil**, dans le groupe **Traitement**, choisissez **Générer XMLPort**, puis enregistrez l'objet en tant que fichier .txt dans un emplacement approprié.</span><span class="sxs-lookup"><span data-stu-id="c43f3-181">On the **Home** tab, in the **Process** group, choose **Generate XMLport**, and then save the object as a .txt file in an appropriate location.</span></span>  

6. <span data-ttu-id="c43f3-182">Importez le nouvel objet XMLport dans l'environnement de développement [!INCLUDE[d365fin](includes/d365fin_md.md)] et compilez-le.</span><span class="sxs-lookup"><span data-stu-id="c43f3-182">Import the new XMLport into the [!INCLUDE[d365fin](includes/d365fin_md.md)] development environment and compile it.</span></span>

## <a name="see-also"></a><span data-ttu-id="c43f3-183">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c43f3-183">See Also</span></span>  
<span data-ttu-id="c43f3-184">[Procédure : configurer les définitions d'échange de données](across-how-to-set-up-data-exchange-definitions.md) </span><span class="sxs-lookup"><span data-stu-id="c43f3-184">[How to: Set Up Data Exchange Definitions](across-how-to-set-up-data-exchange-definitions.md) </span></span>  
<span data-ttu-id="c43f3-185">[Procédure d'exportation de paiements vers un fichier bancaire](payables-how-export-payments-bank-file.md) </span><span class="sxs-lookup"><span data-stu-id="c43f3-185">[How to: Export Payments to a Bank File](payables-how-export-payments-bank-file.md) </span></span>  
<span data-ttu-id="c43f3-186">[Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md) </span><span class="sxs-lookup"><span data-stu-id="c43f3-186">[Collect Payments with SEPA Direct Debit](finance-collect-payments-with-sepa-direct-debit.md) </span></span>  
[<span data-ttu-id="c43f3-187">À propos de l'infrastructure d'échange de données</span><span class="sxs-lookup"><span data-stu-id="c43f3-187">About the Data Exchange Framework</span></span>](across-about-the-data-exchange-framework.md)
