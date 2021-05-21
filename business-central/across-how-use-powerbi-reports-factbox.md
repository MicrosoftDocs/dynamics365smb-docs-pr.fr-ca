---
title: Afficher les rapports Power BI personnalisés pour les données Business Central | Microsoft Docs
description: Vous pouvez utiliser des rapports Power BI pour obtenir des informations supplémentaires sur les données dans les listes.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 04/26/2021
ms.author: jswymer
ms.openlocfilehash: c74593a429c520730efbd503a1884065ca6cd7e4
ms.sourcegitcommit: 57e8ab70d70849752567eecf29529efe2dcdf3af
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/26/2021
ms.locfileid: "5941623"
---
# <a name="creating-power-bi-reports-for-displaying-list-data-in-prod_short"></a><span data-ttu-id="3ff88-103">Création de rapports Power BI pour afficher les données de liste dans [!INCLUDE[prod_short](includes/prod_short.md)]</span><span class="sxs-lookup"><span data-stu-id="3ff88-103">Creating Power BI Reports for Displaying List Data in [!INCLUDE[prod_short](includes/prod_short.md)]</span></span>

[!INCLUDE[prod_long](includes/prod_long.md)] <span data-ttu-id="3ff88-104">comprend un élément de contrôle Récapitulatif Power BI sur plusieurs pages de liste clé.</span><span class="sxs-lookup"><span data-stu-id="3ff88-104">includes a Power BI FactBox control element on many key list pages.</span></span> <span data-ttu-id="3ff88-105">Le but de ce Récapitulatif est d'afficher des rapports Power BI liés aux enregistrements dans les listes, fournissant des informations supplémentaires sur les données.</span><span class="sxs-lookup"><span data-stu-id="3ff88-105">The purpose of this FactBox is to display Power BI reports that are related to records in the lists, providing extra insight into the data.</span></span> <span data-ttu-id="3ff88-106">L′idée est que lorsque vous vous déplacez entre les lignes de la liste, le rapport se met à jour pour l’écriture sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="3ff88-106">The idea is that as you move between rows in the list, the report updates for the selected entry.</span></span>

[!INCLUDE[prod_long](includes/prod_long.md)] <span data-ttu-id="3ff88-107">est livré avec certains de ces rapports.</span><span class="sxs-lookup"><span data-stu-id="3ff88-107">comes ready with some of these reports.</span></span> <span data-ttu-id="3ff88-108">Vous pouvez également créer vos propres rapports personnalisés qui s'affichent dans ce Récapitulatif.</span><span class="sxs-lookup"><span data-stu-id="3ff88-108">You can also create your own custom reports that display in this FactBox.</span></span> <span data-ttu-id="3ff88-109">La création de ces rapports est similaire à d'autres rapports.</span><span class="sxs-lookup"><span data-stu-id="3ff88-109">Creating these reports is similar to other reports.</span></span> <span data-ttu-id="3ff88-110">Mais il y a quelques règles de conception que vous devrez suivre pour vous assurer que les rapports s'affichent comme prévu.</span><span class="sxs-lookup"><span data-stu-id="3ff88-110">But there are a few design rules you'll have to follow to make sure the reports display as expected.</span></span> <span data-ttu-id="3ff88-111">Ces règles sont expliquées dans cet article.</span><span class="sxs-lookup"><span data-stu-id="3ff88-111">These rules are explained in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="3ff88-112">Pour des informations générales sur la création et la publication des rapports Power BI pour Business Central, voir [Création de rapports Power BI pour afficher des données [!INCLUDE [prod_long](includes/prod_long.md)]](across-how-use-financials-data-source-powerbi.md).</span><span class="sxs-lookup"><span data-stu-id="3ff88-112">For general information about creating and publishing Power BI reports for Business Central, see [Building Power BI Reports to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="3ff88-113">Conditions préalables</span><span class="sxs-lookup"><span data-stu-id="3ff88-113">Prerequisites</span></span>

- <span data-ttu-id="3ff88-114">Un compte Power BI.</span><span class="sxs-lookup"><span data-stu-id="3ff88-114">A Power BI account.</span></span>
- <span data-ttu-id="3ff88-115">Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="3ff88-115">Power BI Desktop.</span></span>

<!-- 
For more information about getting started, see [Using [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md).-->

## <a name="create-a-report-for-a-list-page"></a><span data-ttu-id="3ff88-116">Créer un rapport pour une page de liste</span><span class="sxs-lookup"><span data-stu-id="3ff88-116">Create a report for a list page</span></span>

1. <span data-ttu-id="3ff88-117">Lancez Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="3ff88-117">Start Power BI Desktop.</span></span>
2. <span data-ttu-id="3ff88-118">Sélectionnez **Obtenir des données** et commencez à choisir la source de données pour le rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-118">Select **Get Data**, and start choosing the data source for the report.</span></span>

    <span data-ttu-id="3ff88-119">Spécifiez les pages de liste Business Central qui contiennent les données souhaitées dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-119">Specify the Business Central list pages that contain the data that you want in the report.</span></span> <span data-ttu-id="3ff88-120">Par exemple, pour créer un rapport pour la liste **Factures vente**, incluez les pages liées aux ventes.</span><span class="sxs-lookup"><span data-stu-id="3ff88-120">For example, to create a report for the **Sales Invoices** list, include pages related to sales.</span></span>

    <span data-ttu-id="3ff88-121">Pour plus d'informations, suivez les instructions [Ajouter[!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop](across-how-use-financials-data-source-powerbi.md#getdata).</span><span class="sxs-lookup"><span data-stu-id="3ff88-121">For more information, follow the instructions [Add [!INCLUDE[prod_short](includes/prod_short.md)] as a data source in Power BI Desktop](across-how-use-financials-data-source-powerbi.md#getdata).</span></span>

3. <span data-ttu-id="3ff88-122">Définissez le filtre de rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-122">Set the report filter.</span></span>

    <span data-ttu-id="3ff88-123">Pour mettre à jour les données de l’enregistrement sélectionné dans la liste, vous ajoutez un filtre au rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-123">To make the data update to the selected record in the list, you add a filter to the report.</span></span> <span data-ttu-id="3ff88-124">Le filtre doit inclure un champ de la source de données utilisé pour identifier de manière unique chaque enregistrement de la liste.</span><span class="sxs-lookup"><span data-stu-id="3ff88-124">The filter must include a field of the data source that's used to uniquely identify each record in the list.</span></span> <span data-ttu-id="3ff88-125">En termes de développeur, ce champ est la *clé primaire*.</span><span class="sxs-lookup"><span data-stu-id="3ff88-125">In developer terms, this field is the *primary key*.</span></span> <span data-ttu-id="3ff88-126">Dans la plupart des cas, la clé primaire de la liste est **N°**</span><span class="sxs-lookup"><span data-stu-id="3ff88-126">In most cases, the primary key for a list is the **No.**</span></span> <span data-ttu-id="3ff88-127">.</span><span class="sxs-lookup"><span data-stu-id="3ff88-127">field.</span></span>

    <span data-ttu-id="3ff88-128">Pour définir le filtre, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="3ff88-128">To set the filter, do the following steps:</span></span>

    1. <span data-ttu-id="3ff88-129">Dans les **Filtres**, sélectionnez le champ de clé primaire dans la liste des champs disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ff88-129">In the **Filters**, select the primary key field from the list of available fields.</span></span>
    2. <span data-ttu-id="3ff88-130">Faites glisser le champ vers le volet **Filtres** et déposez-le dans le zone **Filtres sur toutes les pages**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-130">Drag the field to **Filters** pane and drop it in the **Filters on all pages** box.</span></span>
    3. <span data-ttu-id="3ff88-131">Définissez le **Type de filtre** sur **Filtrage de base**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-131">Set the **Filter type** to **Basic filtering**.</span></span> <span data-ttu-id="3ff88-132">Il ne peut pas s’agir d’un filtre de page, visuel ou avancé.</span><span class="sxs-lookup"><span data-stu-id="3ff88-132">It can't be page, visual, or advanced filter.</span></span>

    ![Définition du filtre de rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-filter-v3.png)
4. <span data-ttu-id="3ff88-134">Concevez la disposition du rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-134">Design the report layout.</span></span>

    <span data-ttu-id="3ff88-135">Créez la disposition en faisant glisser des champs et en ajoutant des visualisations.</span><span class="sxs-lookup"><span data-stu-id="3ff88-135">Create the layout by dragging fields and adding visualizations.</span></span> <span data-ttu-id="3ff88-136">Pour plus d'informations, voir [Utiliser la vue Rapport dans Power BI Desktop](/power-bi/create-reports/desktop-report-view) dans la documentation Power BI.</span><span class="sxs-lookup"><span data-stu-id="3ff88-136">For more information, see, [Work with Report view in Power BI Desktop](/power-bi/create-reports/desktop-report-view) in the Power BI documentation.</span></span>

5. <span data-ttu-id="3ff88-137">Consultez les sections suivantes sur le dimensionnement du rapport et l'utilisation de plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="3ff88-137">See the next sections about sizing the report and using multiple pages.</span></span>

6. <span data-ttu-id="3ff88-138">Enregistrez et nommez le rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-138">Save and name the report.</span></span>

    <span data-ttu-id="3ff88-139">Attribuez au rapport un nom qui contient le nom de la page de liste associée au rapport, comme dans le client.</span><span class="sxs-lookup"><span data-stu-id="3ff88-139">Give the report a name that contains the name of the list page associated with the report, as it is in the client.</span></span> <span data-ttu-id="3ff88-140">Le nom n′est cependant pas sensible à la casse.</span><span class="sxs-lookup"><span data-stu-id="3ff88-140">The name isn't case-sensitive though.</span></span> <span data-ttu-id="3ff88-141">Supposons que le rapport concerne la page de liste **Factures vente**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-141">Suppose the report is for the **Sales Invoices** list page.</span></span> <span data-ttu-id="3ff88-142">Dans ce cas, incluez les mots **factures vente** dans le nom, comme **mes factures vente.pbix** ou **Ma_liste_factures_vente.pbix**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-142">In this case, include the words *sales invoices*\* somewhere in the name, like **my sales invoices.pbix** or **my_Sales Invoices_list.pbix**.</span></span>

    <span data-ttu-id="3ff88-143">Cette convention de désignation de nom n’est pas obligatoire.</span><span class="sxs-lookup"><span data-stu-id="3ff88-143">This naming convention isn't a requirement.</span></span> <span data-ttu-id="3ff88-144">Cependant, il permet de sélectionner plus rapidement des rapports dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff88-144">However, it makes selecting reports in [!INCLUDE[prod_short](includes/prod_short.md)] quicker.</span></span> <span data-ttu-id="3ff88-145">Lorsque la page de sélection des rapports s’ouvre depuis une page de liste, elle est automatiquement filtrée en fonction du nom de la page.</span><span class="sxs-lookup"><span data-stu-id="3ff88-145">When the report selection page opens from a list page, it's automatically applied a filter based on the page name.</span></span> <span data-ttu-id="3ff88-146">Le filtre a la syntaxe suivante : `@*<caption>*` comme `@*Sales Invoices*`.</span><span class="sxs-lookup"><span data-stu-id="3ff88-146">The filter has the syntax: `@*<caption>*`,  like `@*Sales Invoices*`.</span></span> <span data-ttu-id="3ff88-147">Ce filtrage est effectué pour limiter les rapports affichés.</span><span class="sxs-lookup"><span data-stu-id="3ff88-147">This filtering is done to limit the reports that are displayed.</span></span> <span data-ttu-id="3ff88-148">Vous pouvez aussi effacer le filtre pour obtenir la liste complète des rapports disponibles dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="3ff88-148">Users can clear the filter to get a full list of reports available in Power BI.</span></span>

7. <span data-ttu-id="3ff88-149">Lorsque vous avez terminé, publiez le rapport comme d'habitude.</span><span class="sxs-lookup"><span data-stu-id="3ff88-149">When you're done, publish the report as usual.</span></span>

    <span data-ttu-id="3ff88-150">Pour en savoir plus, consultez [Publication d’un rapport](across-how-use-financials-data-source-powerbi.md#publish-reports).</span><span class="sxs-lookup"><span data-stu-id="3ff88-150">For more information, see [Publishing a Report](across-how-use-financials-data-source-powerbi.md#publish-reports).</span></span>

8. <span data-ttu-id="3ff88-151">Testez le rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-151">Test the report.</span></span>

    <span data-ttu-id="3ff88-152">Une fois les rapports publiés dans votre espace de travail, ils doivent être disponibles à partir du Récapitulatif Power BI sur la page de liste dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff88-152">Once the report's been published to your workspace, it should be available from the Power BI FactBox on the list page in [!INCLUDE[prod_short](includes/prod_short.md)].</span></span>

    <span data-ttu-id="3ff88-153">Pour le tester, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="3ff88-153">To test it, do the following steps.</span></span>

    1. <span data-ttu-id="3ff88-154">Ouvrez [!INCLUDE[prod_short](includes/prod_short.md)] et allez à la page de liste.</span><span class="sxs-lookup"><span data-stu-id="3ff88-154">Open [!INCLUDE[prod_short](includes/prod_short.md)] and go to the list page.</span></span>
    2. <span data-ttu-id="3ff88-155">Si vous ne voyez pas le Récapitulatif Power BI, dans la barre d’action, sélectionnez **Actions** > **Afficher** > **Afficher/Masquer les rapports Power BI**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-155">If you don't see the Power BI FactBox, go the action bar, then select **Actions** > **Display** > **Show/Hide Power BI Reports**.</span></span>
    3. <span data-ttu-id="3ff88-156">Dans le Récapitulatif Power BI, sélectionnez **Sélectionner des rapports**, cochez la case **Activer** pour le rapport, puis sélectionnez **OK**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-156">In the Power BI FactBox, select **Select Reports**, select the **Enable** box for the report, then select **OK**.</span></span>

    <span data-ttu-id="3ff88-157">S'il est correctement conçu, le rapport s'affiche.</span><span class="sxs-lookup"><span data-stu-id="3ff88-157">If designed correctly, the report displays.</span></span>  

## <a name="set-the-report-size-and-color"></a><span data-ttu-id="3ff88-158">Définissez la taille et la couleur du rapport</span><span class="sxs-lookup"><span data-stu-id="3ff88-158">Set the report size and color</span></span>

<span data-ttu-id="3ff88-159">La taille du rapport doit être configurée sur 325 pixels par 310 pixels.</span><span class="sxs-lookup"><span data-stu-id="3ff88-159">The size of the report must be set to 325 pixels by 310 pixels.</span></span> <span data-ttu-id="3ff88-160">Cette taille offre une mise à l’échelle appropriée du rapport dans l’espace disponible du contrôle Récapitulatif Power BI dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff88-160">This size provides the proper scaling of the report in the available space of the Power BI FactBox control in [!INCLUDE[prod_short](includes/prod_short.md)].</span></span> <span data-ttu-id="3ff88-161">Pour définir la taille du rapport, placez le focus en dehors de la zone de présentation de rapport, puis choisissez l'icône en forme de rouleau de peinture.</span><span class="sxs-lookup"><span data-stu-id="3ff88-161">To define the size of the report, place focus outside of the report layout area, and then choose the paint roller icon.</span></span>

![Définition de la largeur et de la hauteur du rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-sizing-v3.png)

<span data-ttu-id="3ff88-163">Vous pouvez modifier la largeur et la hauteur de l'état en choisissant **Personnalisé** dans le champ **Type**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-163">You can change the width and height of the report by choosing **Custom** in the **Type** field.</span></span>

<span data-ttu-id="3ff88-164">Si vous souhaitez que l’arrière-plan du rapport se fonde avec la couleur de l’arrière-plan du contrôle Récapitulatif Power BI, définissez la couleur d’arrière-plan de rapport sur *#FFFFFF* (blanc).</span><span class="sxs-lookup"><span data-stu-id="3ff88-164">If you want the background of the report to blend with the background color of the Power BI FactBox control, set report background color to *#FFFFFF* (white).</span></span> 

> [!TIP]
> <span data-ttu-id="3ff88-165">Utilisez le fichier de thème [!INCLUDE [prod_short](includes/prod_short.md)] pour créer des rapports avec le même style de couleur que les applications [!INCLUDE [prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff88-165">Use the [!INCLUDE [prod_short](includes/prod_short.md)] theme file to build reports with the same color styling as the [!INCLUDE [prod_short](includes/prod_short.md)] apps.</span></span> <span data-ttu-id="3ff88-166">Pour plus d’informations, consultez [Utilisation du thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)]](across-how-use-financials-data-source-powerbi.md#theme).</span><span class="sxs-lookup"><span data-stu-id="3ff88-166">For more information, see [Using the [!INCLUDE [prod_short](includes/prod_short.md)] report theme](across-how-use-financials-data-source-powerbi.md#theme).</span></span>

## <a name="reports-with-multiple-pages"></a><span data-ttu-id="3ff88-167">Rapports avec plusieurs pages</span><span class="sxs-lookup"><span data-stu-id="3ff88-167">Reports with multiple pages</span></span>

<span data-ttu-id="3ff88-168">Avec Power BI, vous pouvez créer un seul rapport avec plusieurs pages.</span><span class="sxs-lookup"><span data-stu-id="3ff88-168">With Power BI, you can create a single report with multiple pages.</span></span> <span data-ttu-id="3ff88-169">Cependant, pour les rapports qui s’affichent avec des pages de liste, nous ne recommandons pas plus d′une seule page.</span><span class="sxs-lookup"><span data-stu-id="3ff88-169">However, for reports that will display with list pages, we recommend that they don't have more than one page.</span></span> <span data-ttu-id="3ff88-170">Le Récapitulatif Power BI n’affiche que la première page de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-170">The Power BI FactBox will only show the first page of your report.</span></span>

## <a name="fixing-problems"></a><span data-ttu-id="3ff88-171">Résolution des problèmes</span><span class="sxs-lookup"><span data-stu-id="3ff88-171">Fixing problems</span></span>

<span data-ttu-id="3ff88-172">Cette section explique comment résoudre les problèmes que vous pourriez rencontrer en essayant d′afficher un rapport Power BI pour une page de liste dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="3ff88-172">This section explains how to fix problems that you might run into when you try to view a Power BI report for a list page in [!INCLUDE[prod_short](includes/prod_short.md)].</span></span>  

### <a name="you-cant-see-the-power-bi-factbox-on-a-list-page"></a><span data-ttu-id="3ff88-173">Vous ne pouvez pas voir le Récapitulatif Power BI sur une page de liste</span><span class="sxs-lookup"><span data-stu-id="3ff88-173">You can't see the Power BI FactBox on a list page</span></span>

<span data-ttu-id="3ff88-174">Par défaut, le Récapitulatif Power BI est caché de la vue.</span><span class="sxs-lookup"><span data-stu-id="3ff88-174">By default, the Power BI FactBox is hidden from view.</span></span> <span data-ttu-id="3ff88-175">Pour afficher le Récapitulatif sur une page, dans la barre d’action, sélectionnez **Actions** > **Afficher** > **Afficher/Masquer les rapports Power BI**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-175">To show the FactBox on a page, from the action bar, select **Actions** > **Display** > **Show/Hide Power BI Reports**.</span></span>

### <a name="you-cant-see-the-report-in-the-select-report-pane"></a><span data-ttu-id="3ff88-176">Vous ne pouvez pas voir le rapport dans le volet Sélectionner un rapport</span><span class="sxs-lookup"><span data-stu-id="3ff88-176">You can't see the report in the Select Report pane</span></span>

<span data-ttu-id="3ff88-177">Le nom du rapport ne contient pas le nom de la page de liste affichée.</span><span class="sxs-lookup"><span data-stu-id="3ff88-177">The report's name doesn't contain the name of the list page that's being shown.</span></span> <span data-ttu-id="3ff88-178">Effacez le filtre pour obtenir la liste complète des rapports disponibles dans Power BI.</span><span class="sxs-lookup"><span data-stu-id="3ff88-178">Clear the filter to get a full list of Power BI reports available.</span></span>  

### <a name="report-is-loaded-but-blank-not-filtered-or-filtered-incorrectly"></a><span data-ttu-id="3ff88-179">Le rapport est chargé, mais vide, non filtré ou filtré incorrectement</span><span class="sxs-lookup"><span data-stu-id="3ff88-179">Report is loaded but blank, not filtered, or filtered incorrectly</span></span>

<span data-ttu-id="3ff88-180">Vérifiez que le filtre du rapport contient la bonne clé primaire.</span><span class="sxs-lookup"><span data-stu-id="3ff88-180">Verify the report filter contains the right primary key.</span></span> <span data-ttu-id="3ff88-181">Dans la plupart des cas, il s’agit du champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="3ff88-181">In most cases, this field is the **No.**</span></span> <span data-ttu-id="3ff88-182">mais dans la table **Écriture**, vous devez utiliser le champ **N° écriture**.</span><span class="sxs-lookup"><span data-stu-id="3ff88-182">field, but in the **G/L Entry** table, for example, you must use the **Entry No.** field.</span></span>

### <a name="report-is-loaded-but-it-shows-a-page-you-didnt-expect"></a><span data-ttu-id="3ff88-183">Le rapport est chargé, mais il affiche une page à laquelle vous ne vous attendiez pas.</span><span class="sxs-lookup"><span data-stu-id="3ff88-183">Report is loaded, but it shows a page you didn't expect</span></span>

<span data-ttu-id="3ff88-184">Vérifiez que la page que vous souhaitez afficher est la première page de votre rapport.</span><span class="sxs-lookup"><span data-stu-id="3ff88-184">Verify that the page you want displayed is the first page in your report.</span></span>  

### <a name="report-appears-with-an-unwanted-gray-boarder-or-its-too-small-or-too-large"></a><span data-ttu-id="3ff88-185">L rapport apparaît avec des bordures grises non désirées, il est trop petit ou trop grand.</span><span class="sxs-lookup"><span data-stu-id="3ff88-185">Report appears with an unwanted gray boarder, or it's too small or too large</span></span>

<span data-ttu-id="3ff88-186">Vérifiez que la taille du rapport est configurée sur 325 pixels x 310 pixels.</span><span class="sxs-lookup"><span data-stu-id="3ff88-186">Verify that the report size is set to 325 pixels x 310 pixels.</span></span> <span data-ttu-id="3ff88-187">Enregistrez le rapport, puis actualisez la page de liste.</span><span class="sxs-lookup"><span data-stu-id="3ff88-187">Save the report, and then refresh the list page.</span></span>  

## <a name="see-related-training-at-microsoft-learn"></a><span data-ttu-id="3ff88-188">Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)</span><span class="sxs-lookup"><span data-stu-id="3ff88-188">See Related Training at [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)</span></span>

## <a name="see-also"></a><span data-ttu-id="3ff88-189">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3ff88-189">See Also</span></span>

[<span data-ttu-id="3ff88-190">Activation de vos données commerciales pour Power BI</span><span class="sxs-lookup"><span data-stu-id="3ff88-190">Enabling Your Business Data for Power BI</span></span>](admin-powerbi.md)  
<span data-ttu-id="3ff88-191">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)</span><span class="sxs-lookup"><span data-stu-id="3ff88-191">[Using [!INCLUDE[prod_short](includes/prod_short.md)] as a Power BI Data Source](across-how-use-financials-data-source-powerbi.md)</span></span>  
[<span data-ttu-id="3ff88-192">Préparation aux activités commerciales</span><span class="sxs-lookup"><span data-stu-id="3ff88-192">Getting Ready for Doing Business</span></span>](ui-get-ready-business.md)  
<span data-ttu-id="3ff88-193">[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)</span><span class="sxs-lookup"><span data-stu-id="3ff88-193">[Setting Up [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)</span></span>  
[<span data-ttu-id="3ff88-194">Finance</span><span class="sxs-lookup"><span data-stu-id="3ff88-194">Finance</span></span>](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]