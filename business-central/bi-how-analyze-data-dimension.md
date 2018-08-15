---
title: "Analyse des données par axe analytique| Microsoft Docs"
description: "Décrit comment analyser les diverses données métier par axe analytique."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.date: 01/25/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 94d783a806b56e972f16ebe1e0d383582cd72126
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
#  <a name="analyze-data-by-dimensions"></a><span data-ttu-id="eba89-103">Analyse des données par axe analytique</span><span class="sxs-lookup"><span data-stu-id="eba89-103">Analyze Data by Dimensions</span></span>
<span data-ttu-id="eba89-104">En analyse financière, une dimension correspond à des données que vous pouvez ajouter à une écriture comme une sorte de marqueur.</span><span class="sxs-lookup"><span data-stu-id="eba89-104">In financial analysis, a dimension is data that you can add to an entry as a kind of marker.</span></span> <span data-ttu-id="eba89-105">Ces données permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les régions, les produits et les représentants, et de récupérer facilement ces groupes à des fins d'analyse.</span><span class="sxs-lookup"><span data-stu-id="eba89-105">This data is used to group entries with similar characteristics, such as customers, regions, products, and salesperson, and easily retrieve these groups for analysis.</span></span> <span data-ttu-id="eba89-106">Les axes peuvent être utilisés sur des écritures de feuilles, de documents et de budgets.</span><span class="sxs-lookup"><span data-stu-id="eba89-106">Dimensions can be used on entries in journals, documents, and budgets.</span></span> <span data-ttu-id="eba89-107">Le terme dimension décrit la manière dont l'analyse est effectuée.</span><span class="sxs-lookup"><span data-stu-id="eba89-107">The term dimension describes how analysis occurs.</span></span> <span data-ttu-id="eba89-108">Une analyse à deux axes, par exemple, est une analyse des ventes par zone.</span><span class="sxs-lookup"><span data-stu-id="eba89-108">A two-dimensional analysis, for example, would be sales per area.</span></span> <span data-ttu-id="eba89-109">Cependant, si vous utilisez plus de deux dimensions lors de la création d'une écriture, vous pouvez mener une analyse plus complexe, telle que des ventes par promotion de vente, par groupe client et par zone.</span><span class="sxs-lookup"><span data-stu-id="eba89-109">However, by using more than two dimensions when creating an entry, you can carry out a more complex analysis, such as sales per sales campaign per customer group per area.</span></span> <span data-ttu-id="eba89-110">Pour plus d'informations, reportez-vous à [Utilisation des axes](finance-dimensions.md).</span><span class="sxs-lookup"><span data-stu-id="eba89-110">For more information, see [Working with Dimensions](finance-dimensions.md).</span></span>

<span data-ttu-id="eba89-111">L'analyse de données par dimensions vous permet d'obtenir un meilleur aperçu de votre utilisation commerciale, ce qui vous permet d'évaluer les informations, telles que l'évaluation du bon fonctionnement de votre compagnie, les domaines dans lesquels elle prospère ou non, et ceux nécessitant l'affectation de ressources.</span><span class="sxs-lookup"><span data-stu-id="eba89-111">Analyzing data by dimensions gives you greater insight into your business, so you can evaluate information, such as how well your business is operating, where it is thriving and where it is not, and where more resources should be allocated.</span></span>

> [!TIP]
> <span data-ttu-id="eba89-112">Pour analyser rapidement les données transactionnelles par dimensions, vous pouvez filtrer les totaux du plan comptable et les entrées de toutes les fenêtres **Entrées** par dimensions.</span><span class="sxs-lookup"><span data-stu-id="eba89-112">As a quick way to analyze transactional data by dimensions, you can filter totals in the chart of accounts and entries in all **Entries** windows by dimensions.</span></span> <span data-ttu-id="eba89-113">Recherchez l'action **Définir le filtre dimension**.</span><span class="sxs-lookup"><span data-stu-id="eba89-113">Look for the **Set Dimension Filter** action.</span></span>

## <a name="to-set-up-an-analysis-view"></a><span data-ttu-id="eba89-114">Pour configurer une vue d'analyse :</span><span class="sxs-lookup"><span data-stu-id="eba89-114">To set up an analysis view</span></span>  
<span data-ttu-id="eba89-115">Une analyse par dimensions affiche une combinaison sélectionnée de dimensions.</span><span class="sxs-lookup"><span data-stu-id="eba89-115">An analysis by dimensions displays a selected combination of dimensions.</span></span> <span data-ttu-id="eba89-116">Vous pouvez stocker et récupérer chaque analyse que vous avez configurée.</span><span class="sxs-lookup"><span data-stu-id="eba89-116">You can store and retrieve each analysis you have set up.</span></span> <span data-ttu-id="eba89-117">Les informations de configuration des vues analytiques sont stockées sur des fiches **Vue d'analyse** afin de simplifier une éventuelle analyse ultérieure.</span><span class="sxs-lookup"><span data-stu-id="eba89-117">The information for setting up an analysis is stored on an **Analysis View** card to simplify future analysis.</span></span>  

1. <span data-ttu-id="eba89-118">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Vues d'analyse**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eba89-118">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis Views**, and then choose the related link.</span></span>  
2. <span data-ttu-id="eba89-119">Dans la fenêtre **Liste des vues d'analyse**, cliquez sur l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="eba89-119">In the **Analysis View List** window, choose the **New** action.</span></span>
3. <span data-ttu-id="eba89-120">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="eba89-120">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. <span data-ttu-id="eba89-121">Pour ajouter des codes axe aux quatre codes du raccourci **Axes analytiques**, cliquez sur **Filtre**, renseignez les champs et cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="eba89-121">To add other dimension codes in addition to the four on the **Dimensions** FastTab, choose the **Filter** action, fill in the fields, and then choose the **OK** button.</span></span>  
5. <span data-ttu-id="eba89-122">Pour mettre à jour la vue, choisissez l'action **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="eba89-122">To update the view, choose the **Update** action.</span></span>

## <a name="to-analyze-by-dimensions"></a><span data-ttu-id="eba89-123">Pour effectuer une analyse par axe analytique</span><span class="sxs-lookup"><span data-stu-id="eba89-123">To analyze by dimensions</span></span>
<span data-ttu-id="eba89-124">La matrice **Vues analytiques** peut vous permettre de consulter les montants de votre comptabilité à l'aide des vues d'analyse que vous avez déjà configurées.</span><span class="sxs-lookup"><span data-stu-id="eba89-124">You can use the **Analysis by Dimensions** matrix to view the amounts in your general ledger by using the analysis views that you have already set up.</span></span> <span data-ttu-id="eba89-125">Complétez la fenêtre **Vues analytiques** pour définir les éléments affichés dans la matrice, puis choisissez l'action **Afficher matrice** pour afficher la matrice.</span><span class="sxs-lookup"><span data-stu-id="eba89-125">You fill in the **Analysis by Dimensions** window to define what will be shown in the matrix, and then you choose the **Show Matrix** action to view the matrix.</span></span>  

- <span data-ttu-id="eba89-126">Les colonnes les plus à gauche contiennent des informations basées sur l'option sélectionnée dans le champ **Afficher lignes** de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="eba89-126">The leftmost columns contain information based on what you have selected in the **Show as Lines** field in the header.</span></span>  
- <span data-ttu-id="eba89-127">Les colonnes les plus à droite contiennent des informations basées sur l'option sélectionnée dans le champ **Afficher colonnes** de l'en-tête.</span><span class="sxs-lookup"><span data-stu-id="eba89-127">The rightmost columns contain information based on to what you have selected in the **Show as Columns** field in the header.</span></span>  

1. <span data-ttu-id="eba89-128">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Vues analytiques**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eba89-128">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis by Dimensions**, and then choose the related link.</span></span>  
2. <span data-ttu-id="eba89-129">Sélectionnez la vue d'analyse appropriée et choisissez l'action **Modifier vue d'analyse**.</span><span class="sxs-lookup"><span data-stu-id="eba89-129">Select the relevant analysis view,  and then choose the **Edit Analysis View** action.</span></span>
3. <span data-ttu-id="eba89-130">En haut de la fenêtre **Analyse vente par axe analytique**, renseignez les champs pour définir ce qui est affiché.</span><span class="sxs-lookup"><span data-stu-id="eba89-130">At the top of the **Analysis by Dimensions** window, fill in the fields to define what is shown.</span></span>
4. 5. <span data-ttu-id="eba89-131">Pour visualiser la spécification d'un montant affiché dans la fenêtre matricielle, sélectionnez le montant.</span><span class="sxs-lookup"><span data-stu-id="eba89-131">To see a specification of an amount shown in the matrix window, choose the amount.</span></span>  

> [!IMPORTANT]  
>   <span data-ttu-id="eba89-132">Vous ne pouvez pas sélectionner une période plus courte que celle indiquée en tant que compression date sur la fiche **Vue d'analyse**.</span><span class="sxs-lookup"><span data-stu-id="eba89-132">You cannot select a period length shorter than the period specified for the date compression on the **Analysis View** card.</span></span> <span data-ttu-id="eba89-133">Les commandes **Jeu suivant** et **Jeu précédent** ne sont pas actives si vous avez sélectionné **Période** dans le champ **Afficher lignes** ou **Afficher colonnes**.</span><span class="sxs-lookup"><span data-stu-id="eba89-133">The **Next Set** and **Previous Set** commands are inactive if you have selected **Period** in either the **Show as Lines** or the **Show as Columns** field.</span></span>  

> [!NOTE]  
>   <span data-ttu-id="eba89-134">Vous pouvez utiliser l'état **Axes analytiques - Détail** pour répertorier de manière détaillée les différentes utilisations des axes analytiques sur les écritures au cours d'une période.</span><span class="sxs-lookup"><span data-stu-id="eba89-134">You can use the **Dimensions - Detail** report to display a detailed classification of how dimensions have been used on entries over a selected period.</span></span> <span data-ttu-id="eba89-135">Vous pouvez utiliser le rapport **Dimensions - Total** pour afficher uniquement les montants totaux.</span><span class="sxs-lookup"><span data-stu-id="eba89-135">You can use the **Dimensions - Total** report to display only the total amounts.</span></span>  

> [!TIP]  
>   <span data-ttu-id="eba89-136">Vous pouvez également modifier la vue en changeant la valeur des champs **Afficher lignes** et **Afficher colonnes**.</span><span class="sxs-lookup"><span data-stu-id="eba89-136">You can also change the view by changing the contents of the **Show as Lines** field and **Show as Columns** field.</span></span> <span data-ttu-id="eba89-137">Pour contrepasser un paramètre de vue, choisissez l'action **Inverser lignes et colonnes**.</span><span class="sxs-lookup"><span data-stu-id="eba89-137">To reverse a view setting, choose the **Reverse Lines and Columns** action.</span></span>

## <a name="to-update-an-analysis-view"></a><span data-ttu-id="eba89-138">Pour mettre à jour une vue d'analyse</span><span class="sxs-lookup"><span data-stu-id="eba89-138">To update an analysis view</span></span>  
<span data-ttu-id="eba89-139">Les montants affichés dans la fenêtre **Vues analytiques** offrent une image de l'état de la société au moment de la dernière mise à jour.</span><span class="sxs-lookup"><span data-stu-id="eba89-139">The amounts that are displayed in the **Analysis by Dimensions** window give you a picture of the company’s state at the time of the last update.</span></span> <span data-ttu-id="eba89-140">Pour obtenir un aperçu de l'état actuel, vous devez actualiser la vue d'analyse en exécutant l'option de mise à jour.</span><span class="sxs-lookup"><span data-stu-id="eba89-140">To get a picture of the current state, you must update the analysis view by running the update function.</span></span>

<span data-ttu-id="eba89-141">La procédure suivante permet de mettre à jour une vue d'analyse à partir de la fenêtre **Vues analytiques**.</span><span class="sxs-lookup"><span data-stu-id="eba89-141">The following procedure is for updating an analysis view from the **Analysis by Dimensions** window.</span></span> <span data-ttu-id="eba89-142">Les étapes sont similaires entre les fenêtres **Fiche vue d'analyse** et des fenêtres **Liste des vues d'analyse**.</span><span class="sxs-lookup"><span data-stu-id="eba89-142">The steps are similar from the **Analysis View Card** and the **Analysis View List** windows.</span></span>  

1. <span data-ttu-id="eba89-143">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Vues analytiques**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="eba89-143">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Analysis by Dimensions**, and then choose the related link.</span></span>  
2. <span data-ttu-id="eba89-144">Dans la fenêtre **Vues analytiques**, sélectionnez le champ **Code vue analytique**.</span><span class="sxs-lookup"><span data-stu-id="eba89-144">In the **Analysis by Dimensions** window, choose the **Analysis View Code** field.</span></span>  
3. <span data-ttu-id="eba89-145">Sélectionnez la ligne contenant la vue d'analyse appropriée.</span><span class="sxs-lookup"><span data-stu-id="eba89-145">Select the line with the relevant analysis view.</span></span>  
4. <span data-ttu-id="eba89-146">Cliquez sur **Mettre à jour**.</span><span class="sxs-lookup"><span data-stu-id="eba89-146">Choose the **Update** action.</span></span>  

> [!TIP]  
>   <span data-ttu-id="eba89-147">Si vous activez la case à cocher **Mise à jour à la validation** sur la fiche vue d'analyse, la vue est automatiquement mise à jour lorsqu'une transaction concernée est validée.</span><span class="sxs-lookup"><span data-stu-id="eba89-147">If you select the **Update on Posting** check box on an analysis view card, the view is automatically updated when an involved transaction is posted.</span></span>

> [!NOTE]  
>   <span data-ttu-id="eba89-148">Pour mettre à jour tout ou partie des vues d'analyse en même temps, vous devez utiliser le traitement par lots **Mise à jour vues d'analyse**.</span><span class="sxs-lookup"><span data-stu-id="eba89-148">To update some or all analysis views at the same time, you must use the **Update Analysis Views** batch job.</span></span>  

## <a name="see-also"></a><span data-ttu-id="eba89-149">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eba89-149">See Also</span></span>
[<span data-ttu-id="eba89-150">Veille économique</span><span class="sxs-lookup"><span data-stu-id="eba89-150">Business Intelligence</span></span>](bi.md)  
[<span data-ttu-id="eba89-151">Finances</span><span class="sxs-lookup"><span data-stu-id="eba89-151">Finance</span></span>](finance.md)  
[<span data-ttu-id="eba89-152">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="eba89-152">Setting Up Finance</span></span>](finance-setup-finance.md)  
[<span data-ttu-id="eba89-153">Les écritures comptables et le plan comptable</span><span class="sxs-lookup"><span data-stu-id="eba89-153">The General Ledger and the Chart of Accounts</span></span>](finance-general-ledger.md)  
[<span data-ttu-id="eba89-154">Utilisation des axes analytiques</span><span class="sxs-lookup"><span data-stu-id="eba89-154">Working with Dimensions</span></span>](finance-dimensions.md)  
<span data-ttu-id="eba89-155">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="eba89-155">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
