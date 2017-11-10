---
title: "Créer et modifier des présentations personnalisées pour les rapports et les documents| Microsoft Docs"
description: "Découvrez comment créer vos propres présentations personnalisées qui vous permettent de personnaliser l'apparence d'un rapport lorsqu'il est consulté, imprimé ou enregistré."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 03/29/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: dbe130ef829c6c4efd97fa3f223312c193a078f5
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-create-and-modify-a-custom-report-or-document-layout"></a><span data-ttu-id="b81ed-103">Procédure : créer et modifier une présentation de rapport ou de document personnalisée</span><span class="sxs-lookup"><span data-stu-id="b81ed-103">How to: Create and Modify a Custom Report or Document Layout</span></span>
<span data-ttu-id="b81ed-104">Par défaut, un rapport aura une présentation de rapport intégrée, qui peut être soit une présentation de rapport RDLC ou une présentation de rapport Word, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="b81ed-104">By default, a report will have a built-in report layout, which can be either an RDLC report layout or Word report layout, or both.</span></span> <span data-ttu-id="b81ed-105">Vous ne pouvez pas modifier les présentations intégrées.</span><span class="sxs-lookup"><span data-stu-id="b81ed-105">You cannot modify built-in layouts.</span></span> <span data-ttu-id="b81ed-106">Cependant, vous pouvez créer vos propres présentations personnalisées qui vous permettent de modifier l'apparence d'un rapport lorsqu'il est consulté, imprimé ou enregistré.</span><span class="sxs-lookup"><span data-stu-id="b81ed-106">However, you can create your own custom layouts that enable you to change the appearance of report when it is viewed, printed or saved.</span></span> <span data-ttu-id="b81ed-107">Vous pouvez créer plusieurs présentations de rapport personnalisées pour le même rapport, puis faire basculer la présentation utilisée par un rapport selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b81ed-107">You can create multiple custom report layouts for the same report, and then switch the layout that is used by a report as needed.</span></span>

> [!NOTE]  
>   <span data-ttu-id="b81ed-108">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], le terme « état » couvre également les documents externes, tels que les factures vente et les confirmations de commande que vous envoyez à des clients comme fichiers PDF.</span><span class="sxs-lookup"><span data-stu-id="b81ed-108">In [!INCLUDE[d365fin](includes/d365fin_md.md)], the term "report" also covers externally-facing documents, such as sales invoices and order confirmations that you send to customers as PDF files.</span></span>

<span data-ttu-id="b81ed-109">Pour créer une présentation personnalisée, vous pouvez effectuer une copie d'une présentation personnalisée existante ou ajouter une nouvelle présentation personnalisée, qui est le plus souvent basée sur une présentation intégrée.</span><span class="sxs-lookup"><span data-stu-id="b81ed-109">To create a custom layout, you can either make a copy of an existing custom layout or add a new custom layout, which in most cases is based on a built-in layout.</span></span> <span data-ttu-id="b81ed-110">Lorsque vous ajoutez une nouvelle présentation personnalisée, vous pouvez choisir d'ajouter un type de présentation de rapport RDLC, un type de présentation de rapport Word, ou les deux.</span><span class="sxs-lookup"><span data-stu-id="b81ed-110">When you add a new custom layout, you can choose to add an RDLC report layout type, Word report layout type, or both.</span></span> <span data-ttu-id="b81ed-111">La nouvelle présentation personnalisée est automatiquement basée sur la présentation intégrée pour le rapport s'il y en a une disponible.</span><span class="sxs-lookup"><span data-stu-id="b81ed-111">The new custom layout will automatically be based on the built-in layout for the report if one is available.</span></span> <span data-ttu-id="b81ed-112">S'il n'y a pas de présentation intégrée pour le type, alors une nouvelle présentation vide est créée, que vous devrez modifier et concevoir entièrement.</span><span class="sxs-lookup"><span data-stu-id="b81ed-112">If there is no built-in layout for the type, then a new blank layout is a created, which you will have to modify and design from scratch.</span></span> <span data-ttu-id="b81ed-113">Pour plus d'informations sur les présentations de rapport RDLC et Word, les présentations intégrées et personnalisées, et plus encore, reportez-vous à [Gérer la présentation des états](ui-manage-report-layouts.md).</span><span class="sxs-lookup"><span data-stu-id="b81ed-113">For more information about RDLC and Word report layouts, built-in and custom layouts, and more, see [Manage Report Layouts](ui-manage-report-layouts.md).</span></span>  

## <a name="to-create-a-custom-layout"></a><span data-ttu-id="b81ed-114">Pour créer une présentation personnalisée</span><span class="sxs-lookup"><span data-stu-id="b81ed-114">To create a custom layout</span></span>
1. <span data-ttu-id="b81ed-115">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Sélection présentation rapport**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="b81ed-115">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Report Layout Selection**, and then choose the related link.</span></span>  
   <span data-ttu-id="b81ed-116">La fenêtre **Sélection présentation rapport** répertorie tous les rapports disponibles dans la compagnie spécifiée dans le champ Compagnie en haut de la fenêtre.</span><span class="sxs-lookup"><span data-stu-id="b81ed-116">The** Report Layout Selection** window lists all the reports that are available in the company that is specified in the Company field at the top of the window.</span></span>
2. <span data-ttu-id="b81ed-117">Définissez le champ **Société** sur la société pour laquelle vous souhaitez créer la présentation de rapport.</span><span class="sxs-lookup"><span data-stu-id="b81ed-117">Set the **Company** field to the company in which you want to create the report layout.</span></span>
3. <span data-ttu-id="b81ed-118">Sélectionnez la ligne du rapport pour lequel vous souhaitez créer la présentation, puis sélectionnez l'action **Présentations personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-118">Select the row for the report that you want to create the layout for, and then choose the **Custom Layouts** action.</span></span>  
   <span data-ttu-id="b81ed-119">La fenêtre **Présentations état personnalisées** s'affiche et répertorie toutes les présentations personnalisées disponibles pour l'état sélectionné.</span><span class="sxs-lookup"><span data-stu-id="b81ed-119">The **Custom Report Layouts** window appears and lists all the custom layouts that are available for the selected report.</span></span>
4. <span data-ttu-id="b81ed-120">Si vous souhaitez créer une copie d'une présentation personnalisée existante, sélectionnez cette dernière, puis sélectionnez l'action **Copier**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-120">If you want to create a copy of an existing custom layout, select the existing custom layout in the list, and then choose the **Copy** action.</span></span>  
   <span data-ttu-id="b81ed-121">La copie de la présentation personnalisée s'affiche dans la fenêtre **Présentations rapport personnalisées**. Le terme *Copie* figure dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-121">The copy of the custom layout appears in the **Custom Report Layouts** window and has the words *Copy of* in the **Description** field.</span></span>
5. <span data-ttu-id="b81ed-122">Si vous voulez ajouter une nouvelle présentation personnalisée basée sur une présentation intégrée, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="b81ed-122">If you want to add a new custom layout that is based on a built-in layout, do the following:</span></span>  
   1. <span data-ttu-id="b81ed-123">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-123">Choose the **New** action.</span></span> <span data-ttu-id="b81ed-124">La fenêtre **Insérer présentation intégrée pour un état** s'affiche.</span><span class="sxs-lookup"><span data-stu-id="b81ed-124">The **Insert Built-in Layout for a Report** window appears.</span></span> <span data-ttu-id="b81ed-125">Les champs **ID** et **Nom** sont automatiquement renseignés.</span><span class="sxs-lookup"><span data-stu-id="b81ed-125">The **ID** and **Name** fields are automatically filled in.</span></span>
   2. <span data-ttu-id="b81ed-126">Pour ajouter un type de présentation de rapport Word, cochez la case **Insérer présentation Word**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-126">To add a custom Word report layout type, then select the **Insert Word Layout** check box.</span></span>
   3. <span data-ttu-id="b81ed-127">Pour ajouter un type de présentation de rapport RDLC, cochez la case **Insérer présentation RDLC**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-127">To add a custom RDLC report layout type, then select the **Insert RDLC Layout** check box.</span></span>
   4. <span data-ttu-id="b81ed-128">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-128">Choose the **OK** button.</span></span>  
      <span data-ttu-id="b81ed-129">Les nouvelles présentations personnalisées s'affichent dans la fenêtre **Présentations état personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-129">The new custom layouts appear in the **Custom Report Layouts** window.</span></span> <span data-ttu-id="b81ed-130">Si une nouvelle présentation est basée sur une présentation intégrée, les termes **Copie d'une présentation intégrée** figurent dans le champ **Description**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-130">If a new layout is based on a built-in layout, then it has the words **Copy of a Built-in Layout** in the **Description** field.</span></span> <span data-ttu-id="b81ed-131">S'il n'y avait aucune présentation intégrée pour l'état, les termes **Nouvelle présentation** figurent dans le champ **Description** de la nouvelle présentation, ce qui indique que la présentation personnalisée est vide.</span><span class="sxs-lookup"><span data-stu-id="b81ed-131">If there was no built-in layout for the report, then the new layout has the words **New Layout** in the **Description** field, which indicates that custom layout is blank.</span></span>
6. <span data-ttu-id="b81ed-132">Par défaut, le champ **Nom de la société** est vide, ce qui signifie que la présentation personnalisée est disponible pour l'état dans toutes les sociétés.</span><span class="sxs-lookup"><span data-stu-id="b81ed-132">By default, the **Company Name** field is blank, which means that the custom layout will be available for the report in all companies.</span></span> <span data-ttu-id="b81ed-133">Afin que la présentation personnalisée soit disponible pour une société spécifique uniquement, sélectionnez **Modifier**, puis définissez le champ **Nom de la société** sur la société que vous souhaitez.</span><span class="sxs-lookup"><span data-stu-id="b81ed-133">To make the custom layout available in a specific company only, choose **Edit**, and then set the **Company Name** field to the company that you want.</span></span>

<span data-ttu-id="b81ed-134">La présentation personnalisée a été créée.</span><span class="sxs-lookup"><span data-stu-id="b81ed-134">The custom layout has been created.</span></span> <span data-ttu-id="b81ed-135">Vous pouvez à présent modifier la présentation personnalisée selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b81ed-135">You can now modify the custom layout as needed.</span></span>

## <span data-ttu-id="b81ed-136"><a name="ModifyCustomLayout"></a>Modification d'une présentation personnalisée</span><span class="sxs-lookup"><span data-stu-id="b81ed-136"><a name="ModifyCustomLayout"></a>Modifying a custom layout</span></span>
<span data-ttu-id="b81ed-137">Pour modifier une présentation de rapport, vous devez d'abord exporter la présentation de rapport sous forme de fichier dans un emplacement sur votre ordinateur ou le réseau, puis ouvrir le document exporté et effectuer les modifications.</span><span class="sxs-lookup"><span data-stu-id="b81ed-137">To modify a report layout, you must first export the report layout as a file to a location on your computer or network, and then open the exported document and make the changes.</span></span> <span data-ttu-id="b81ed-138">Lorsque vous avez terminé d'apporter les modifications, vous importez la présentation de rapport.</span><span class="sxs-lookup"><span data-stu-id="b81ed-138">When you are finished making the changes, you import the report layout.</span></span>

### <a name="to-modify-a-custom-layout"></a><span data-ttu-id="b81ed-139">Pour modifier une présentation personnalisée</span><span class="sxs-lookup"><span data-stu-id="b81ed-139">To modify a custom layout</span></span>
1.  <span data-ttu-id="b81ed-140">Vous exportez une présentation personnalisée à partir de la fenêtre **Présentations rapport personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-140">You export a custom layout from the **Custom Report Layouts** window.</span></span> <span data-ttu-id="b81ed-141">Si cette fenêtre n'est pas déjà ouverte, recherchez et ouvrez la fenêtre **Sélection présentation rapport**, sélectionnez le rapport dont vous souhaitez modifier la présentation, puis choisissez l'action **Présentations personnalisées**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-141">If this window is not already open, search for and open the **Report Layout Selection** window, select the report that has the layout that you want to modify, and then choose the **Custom Layouts** action.</span></span>  
2.  <span data-ttu-id="b81ed-142">Dans la fenêtre **Présentations rapport personnalisées**, sélectionnez la présentation à modifier, choisissez l'action **Exporter présentation**, puis choisissez **Enregistrer** ou **Enregistrer sous** pour enregistrer le document de présentation de rapport dans un emplacement sur votre ordinateur ou réseau.</span><span class="sxs-lookup"><span data-stu-id="b81ed-142">In the **Custom Report Layouts** window, select the layout that you want to modify, choose the **Export Layout** action, and then choose **Save** or **Save As** to save the report layout document to a location on your computer or network.</span></span>  
  
3.  <span data-ttu-id="b81ed-143">Ouvrez le document de présentation de rapport que vous avez enregistré, puis apportez les modifications.</span><span class="sxs-lookup"><span data-stu-id="b81ed-143">Open the report layout document that you just saved, and then make changes.</span></span>

      <span data-ttu-id="b81ed-144">Si vous modifiez une présentation Word, ouvrez le document de présentation dans Word.</span><span class="sxs-lookup"><span data-stu-id="b81ed-144">If you are changing a Word layout, open the layout document in Word.</span></span> <span data-ttu-id="b81ed-145">Pour modifier les détails, reportez-vous à la section suivante [Apporter des modifications à la présentation de rapport](ui-how-create-custom-report-layout.md#MakeChangesToLayout).</span><span class="sxs-lookup"><span data-stu-id="b81ed-145">For editing details, see the next section [Making Changes to the Report Layout](ui-how-create-custom-report-layout.md#MakeChangesToLayout).</span></span> 

      <span data-ttu-id="b81ed-146">Les présentations de rapport RDLC sont plus avancées que les présentations de rapport Word.</span><span class="sxs-lookup"><span data-stu-id="b81ed-146">RDLC report layouts are more advanced than Word report layouts.</span></span> <span data-ttu-id="b81ed-147">Pour plus d'informations sur la modification d'une présentation de rapport RDLC, voir [Création de présentations de rapport RDLC](https://msdn.microsoft.com/en-us/dynamics-nav/designing-rdlc-report-layouts).</span><span class="sxs-lookup"><span data-stu-id="b81ed-147">For more information about modifying an RDLC report layout, see [Designing RDLC Report Layouts](https://msdn.microsoft.com/en-us/dynamics-nav/designing-rdlc-report-layouts).</span></span>

      <span data-ttu-id="b81ed-148">Pensez à enregistrer vos modifications une fois effectuées.</span><span class="sxs-lookup"><span data-stu-id="b81ed-148">Remember to save you changes when done.</span></span>
  
4.  <span data-ttu-id="b81ed-149">Retournez à la fenêtre **Présentations rapport personnalisées**, sélectionnez la présentation de rapport que vous avez exportée et modifiée, puis choisissez l'action **Importer présentation**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-149">Return to the **Custom Report Layouts** window, select the report layout that you exported and modified, and then choose the **Import Layout** action.</span></span>  
  
5. <span data-ttu-id="b81ed-150">Dans la boîte de dialogue **Importer**, sélectionnez **Choisir** pour rechercher et sélectionner le document de présentation de rapport, puis choisissez **Ouvrir**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-150">In the **Import** dialog box, select **Choose** to find and select the report layout document, and then choose **Open**.</span></span>

##  <span data-ttu-id="b81ed-151"><a name="MakeChangesToLayout"></a> Apporter des modifications à une présentation de rapport Word</span><span class="sxs-lookup"><span data-stu-id="b81ed-151"><a name="MakeChangesToLayout"></a> Making changes to a Word report layout</span></span>  
<span data-ttu-id="b81ed-152">Pour apporter des modifications générales de mise en forme et de disposition (par exemple modifier la police texte, ajouter et modifier un tableau ou supprimer un champ de données), utilisez les fonctions de base d'édition de Word, tout comme vous le faites avec n'importe quel document Word.</span><span class="sxs-lookup"><span data-stu-id="b81ed-152">To can make general formatting and layout changes, such as changing text font, adding and modifying a table, or removing a data field, just use the basic editing features of Word, like you do with any Word document.</span></span>

<span data-ttu-id="b81ed-153">Si vous créez une présentation de rapport Word de A à Z ou en ajoutant de nouveaux champs de données, commencez par ajouter un tableau comprenant des lignes et colonnes qui finiront par contenir les champs de données.</span><span class="sxs-lookup"><span data-stu-id="b81ed-153">If you are designing a Word report layout from scratch or adding new data fields, then start by adding a table that includes rows and columns that will eventually hold the data fields.</span></span> 
  
> [!TIP]  
>  <span data-ttu-id="b81ed-154">Affiche les quadrillages de façon à visualiser les contours des cellules de la table.</span><span class="sxs-lookup"><span data-stu-id="b81ed-154">Show the table gridlines so that you see the boundaries of table cells.</span></span> <span data-ttu-id="b81ed-155">Pensez à masquer les quadrillages lorsque vous avez terminé l'édition.</span><span class="sxs-lookup"><span data-stu-id="b81ed-155">Remember to hide the gridlines when you are done editing.</span></span> <span data-ttu-id="b81ed-156">Pour masquer ou afficher des quadrillages dans la table, sélectionnez la table, puis sous **Mise en page** sous l'onglet **Table**, sélectionnez **Afficher les quadrillages**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-156">To show or hide table gridlines, select the table, and then under **Layout** on the **Table** tab, choose **View Gridlines**.</span></span>  
  
###  <span data-ttu-id="b81ed-157"><a name="RemoveField"></a> Suppression des champs d'étiquette et de données dans les présentations Word</span><span class="sxs-lookup"><span data-stu-id="b81ed-157"><a name="RemoveField"></a> Removing Label and Data Fields in Word Layouts</span></span>  
 <span data-ttu-id="b81ed-158">L'étiquette et les champs de données d'un rapport sont contenus dans des contrôles de contenu dans Word.</span><span class="sxs-lookup"><span data-stu-id="b81ed-158">Label and data fields of a report are contained in content controls in Word.</span></span> <span data-ttu-id="b81ed-159">La figure ci-après illustre un contrôle de contenu lorsqu'il est sélectionné dans le document Word.</span><span class="sxs-lookup"><span data-stu-id="b81ed-159">The following figure illustrates a content control when it is selected in the Word document.</span></span>  
  
 <span data-ttu-id="b81ed-160">![Contrôle de contenu d'un champ dans une présentation de rapport Word](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")</span><span class="sxs-lookup"><span data-stu-id="b81ed-160">![Content control for field in Word report layout](media/nav_wordreportlayouts_contentcontrol.png "NAV_WordReportLayouts_ContentControl")</span></span>  
  
 <span data-ttu-id="b81ed-161">Le nom de l'étiquette ou le nom du champ de données s'affiche dans le contrôle de contenu.</span><span class="sxs-lookup"><span data-stu-id="b81ed-161">The name of the label or data field name displays in the content control.</span></span> <span data-ttu-id="b81ed-162">Dans l'exemple, le nom du champ est CompanyAddr1.</span><span class="sxs-lookup"><span data-stu-id="b81ed-162">In the example, the field name is CompanyAddr1.</span></span>  
  
### <a name="to-remove-a-label-or-data-field"></a><span data-ttu-id="b81ed-163">Pour supprimer un champ étiquette ou données</span><span class="sxs-lookup"><span data-stu-id="b81ed-163">To remove a label or data field</span></span>  
  
1.  <span data-ttu-id="b81ed-164">Cliquez avec le bouton droit sur le champ que vous voulez supprimer, puis choisissez **Supprimer le contrôle de contenu**.</span><span class="sxs-lookup"><span data-stu-id="b81ed-164">Right-click the field that you want to delete, and then choose **Remove Content Control**.</span></span>  
  
     <span data-ttu-id="b81ed-165">Le contrôle de contenu est supprimé, mais le nom du champ reste sous forme de texte.</span><span class="sxs-lookup"><span data-stu-id="b81ed-165">The content control is removed, but the field name remains as text.</span></span>  
  
2.  <span data-ttu-id="b81ed-166">Supprimez le texte restant selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="b81ed-166">Delete the remaining text as needed.</span></span>  

### <a name="adding-data-fields"></a><span data-ttu-id="b81ed-167">Ajout de champs de données</span><span class="sxs-lookup"><span data-stu-id="b81ed-167">Adding data fields</span></span>
<span data-ttu-id="b81ed-168">L'ajout de champs de données à partir d'un ensemble de données de rapport est une fonction plus avancée qui exige des connaissances sur l'ensemble de données de rapport.</span><span class="sxs-lookup"><span data-stu-id="b81ed-168">Adding data fields from a report dataset is a more advanced and requires some knowledge of the report dataset.</span></span> <span data-ttu-id="b81ed-169">Pour plus d'informations sur l'ajout de champs pour les données, étiquettes et images, voir [Procédure : ajouter des champs à une présentation de rapport Word](ui-how-add-fields-word-report-layout.md).</span><span class="sxs-lookup"><span data-stu-id="b81ed-169">For information about adding fields for data, labels, data, and images, see [How to: Add Fields to a Word Report Layout](ui-how-add-fields-word-report-layout.md).</span></span>  
  

## <a name="see-also"></a><span data-ttu-id="b81ed-170">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b81ed-170">See Also</span></span>
[<span data-ttu-id="b81ed-171">Gestion des présentations de rapport</span><span class="sxs-lookup"><span data-stu-id="b81ed-171">Managing Report Layouts</span></span>](ui-manage-report-layouts.md)  
[<span data-ttu-id="b81ed-172">Procédure : Modification de la présentation actuellement utilisée sur un rapport</span><span class="sxs-lookup"><span data-stu-id="b81ed-172">How to: Change Which Layout is Currently Used on a Report</span></span>](ui-how-change-layout-currently-used-report.md)  
[<span data-ttu-id="b81ed-173">Procédure : importer et exporter une présentation de rapport ou de document personnalisée</span><span class="sxs-lookup"><span data-stu-id="b81ed-173">How to: Import and Export a Custom Report or Document Layout</span></span>](ui-how-import-and-export-report-layout.md)  
[<span data-ttu-id="b81ed-174">Utilisation des rapports</span><span class="sxs-lookup"><span data-stu-id="b81ed-174">Working with Reports</span></span>](ui-work-report.md)  
<span data-ttu-id="b81ed-175">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="b81ed-175">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
