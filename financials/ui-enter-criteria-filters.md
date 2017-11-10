---
title: "Recherche de données et saisie de critères de filtre | Microsoft Docs"
description: "Décrit comment utiliser les filtres, par exemple le filtre rapide, pour préciser les résultats que vous obtenez lorsque vous recherchez des données."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: delimit, FlowFilter
ms.date: 03/29/2017
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 11d7ef56e980ba263dba6328b2f2f08b86410242
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="searching-filtering-and-sorting-data"></a><span data-ttu-id="6ea94-103">Recherche, filtrage et tri de données</span><span class="sxs-lookup"><span data-stu-id="6ea94-103">Searching, Filtering, and Sorting Data</span></span>
<span data-ttu-id="6ea94-104">Il existe quelques fonctions que vous pouvez utiliser pour vous aider à rechercher, identifier et analyser des enregistrements d'une liste.</span><span class="sxs-lookup"><span data-stu-id="6ea94-104">There are a few things that you can do that will help you find, pinpoint, and scan records in a list.</span></span> <span data-ttu-id="6ea94-105">Ce sont notamment le tri, la recherche et le filtrage.</span><span class="sxs-lookup"><span data-stu-id="6ea94-105">These include sorting, searching and filtering.</span></span>

<span data-ttu-id="6ea94-106">Lorsque vous souhaitez rechercher des données, telles que des noms de client, des adresses ou des groupes de produits, vous saisissez des critères.</span><span class="sxs-lookup"><span data-stu-id="6ea94-106">When you want to search for data, such as customer names, addresses, or product groups, you enter criteria.</span></span> <span data-ttu-id="6ea94-107">Dans vos critères de recherche, vous pouvez utiliser tous les chiffres et toutes les lettres que vous utilisez habituellement dans ce champ spécifique.</span><span class="sxs-lookup"><span data-stu-id="6ea94-107">In search criteria you can use all the numbers and letters that you normally use in the specific field.</span></span> <span data-ttu-id="6ea94-108">En plus, vous pouvez utiliser des symboles spéciaux pour filtrer davantage les résultats.</span><span class="sxs-lookup"><span data-stu-id="6ea94-108">In addition, you can use special symbols to further filter the results.</span></span> <span data-ttu-id="6ea94-109">Il existe deux façons d'effectuer des recherches : en utilisant le filtre rapide ou les filtres de colonne.</span><span class="sxs-lookup"><span data-stu-id="6ea94-109">There are two ways to search: using the Quick Filter or column filters.</span></span>

## <a name="sorting"></a><span data-ttu-id="6ea94-110">Tri</span><span class="sxs-lookup"><span data-stu-id="6ea94-110">Sorting</span></span>
<span data-ttu-id="6ea94-111">Le tri vous permet d'avoir facilement un aperçu de vos données.</span><span class="sxs-lookup"><span data-stu-id="6ea94-111">Sorting makes it easy for you to get a quick overview of your data.</span></span> <span data-ttu-id="6ea94-112">Si vous avez de nombreux clients, par exemple, vous pouvez choisir de les trier par **N° client**, **Groupe de report client**, **Code devise**, **Code pays/région** ou **N° d'enregistrement taxe de vente** pour obtenir l'aperçu dont vous avez besoin.</span><span class="sxs-lookup"><span data-stu-id="6ea94-112">If you have many customers, for example, you can choose to sort them by **Customer No.**, **Customer Posting Group**, **Currency Code**, **Country Region Code**, or **Sales Tax Registration No.** to get the overview you need.</span></span>

<span data-ttu-id="6ea94-113">Pour trier une liste, vous pouvez choisir un texte d'en-tête de colonne pour permuter entre l'ordre croissant et décroissant, ou cliquer sur la petite flèche vers le bas dans l'en-tête de colonne et choisir **Croissant** ou **Décroissant**.</span><span class="sxs-lookup"><span data-stu-id="6ea94-113">To sort a list, you can either choose a column heading text to toggle between ascending and descending order, or choose the small downs arrow in the column heading, and then choose **Ascending** or **Descending**.</span></span>  

> [!NOTE]  
>   <span data-ttu-id="6ea94-114">Le tri n'est pas pris en charge sur les images, les champs de type BLOB, les FlowFilters, et les champs n'appartenant pas à une table.</span><span class="sxs-lookup"><span data-stu-id="6ea94-114">Sorting is not supported images, BLOB fields, FlowFilters, and fields that do not belong to a table.</span></span>  

## <a name="searching-by-using-the-quick-filter"></a><span data-ttu-id="6ea94-115">Recherche à l'aide du filtre rapide</span><span class="sxs-lookup"><span data-stu-id="6ea94-115">Searching by using the Quick Filter</span></span>
<span data-ttu-id="6ea94-116">Vous pouvez ajouter des filtres pour l'ensemble des pages en utilisant le filtre rapide.</span><span class="sxs-lookup"><span data-stu-id="6ea94-116">You can add filters to all pages by using the Quick Filter.</span></span> <span data-ttu-id="6ea94-117">Vous activez le filtre rapide sélectionnant l'icône de loupe dans le coin supérieur droit d'une page.</span><span class="sxs-lookup"><span data-stu-id="6ea94-117">The Quick Filter is enabled by choosing the magnifier icon in the top right corner of a page.</span></span> <span data-ttu-id="6ea94-118">Ce type de filtre est utilisé pour une saisie rapide des critères.</span><span class="sxs-lookup"><span data-stu-id="6ea94-118">This filtering type is used for a fast entry of criteria.</span></span>

> [!IMPORTANT]  
>   <span data-ttu-id="6ea94-119">Le Filtre rapide facilite l'accès aux données de filtre par la saisie de texte simple, mais fournit également un grand nombre d'options de critères de recherche.</span><span class="sxs-lookup"><span data-stu-id="6ea94-119">The Quick Filter provides an easy access to filter data by entering plain text, but does also provide a lot of search criteria options.</span></span> <span data-ttu-id="6ea94-120">Selon que vous saisissez du texte simple ou du texte comprenant des symboles, le Filtre rapide se comporte de façon différente.</span><span class="sxs-lookup"><span data-stu-id="6ea94-120">Depending on whether you enter plain text or text including symbols, the Quick Filter behaves differently.</span></span>  

* <span data-ttu-id="6ea94-121">Si vous saisissez du texte simple dans les critères de recherche, le critère de recherche est interprété comme une recherche insensible à la casse qui contient un certain texte.</span><span class="sxs-lookup"><span data-stu-id="6ea94-121">If you enter plain text in the search criteria, the search criteria is interpreted as a case insensitive search that contains certain text.</span></span>  
* <span data-ttu-id="6ea94-122">Si vous saisissez du texte comprenant des symboles dans les critères de recherche, le critère de recherche est interprété exactement comme vous l'avez saisi, et la recherche distingue les majuscules et les minuscules.</span><span class="sxs-lookup"><span data-stu-id="6ea94-122">If you enter text including symbols in the search criteria, the search criteria is interpreted exactly as you entered it, and the search is case sensitive.</span></span>

### <a name="quick-filter-criteria"></a><span data-ttu-id="6ea94-123">Critères de filtre rapide</span><span class="sxs-lookup"><span data-stu-id="6ea94-123">Quick filter criteria</span></span>
<!-- html syntax because symbols conflict with MarkDown syntax -->
<TABLE>
  <TR>
    <TH><span data-ttu-id="6ea94-124">Critères de recherche</span><span class="sxs-lookup"><span data-stu-id="6ea94-124">Search Criteria</span></span></TH>
    <TH><span data-ttu-id="6ea94-125">Interprété comme...</span><span class="sxs-lookup"><span data-stu-id="6ea94-125">Interpreted as...</span></span></TH>
    <TH><span data-ttu-id="6ea94-126">Renvoie...</span><span class="sxs-lookup"><span data-stu-id="6ea94-126">Returns...</span></span></TH>
  </TR>
  <TR>
    <TD><span data-ttu-id="6ea94-127">man</span><span class="sxs-lookup"><span data-stu-id="6ea94-127">man</span></span></TD>
    <TD><span data-ttu-id="6ea94-128">@&#42;man&#42;</span><span class="sxs-lookup"><span data-stu-id="6ea94-128">@&#42;man&#42;</span></span></TD>
    <TD><span data-ttu-id="6ea94-129">Tous les enregistrements qui contiennent le texte <b>man</b> et ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-129">All records that contain the text <b>man</b> and case insensitive.</span></span></TD>
  </TR>
  <TR>
    <TD><span data-ttu-id="6ea94-130">se</span><span class="sxs-lookup"><span data-stu-id="6ea94-130">se</span></span></TD>
    <TD><span data-ttu-id="6ea94-131">@&#42;se&#42;</span><span class="sxs-lookup"><span data-stu-id="6ea94-131">@&#42;se&#42;</span></span></TD>
    <TD><span data-ttu-id="6ea94-132">Tous les enregistrements qui contiennent le texte <b>se</b> et ne respectent pas la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-132">All records that contain the text <b>se</b> and case insensitive.</span></span></TD>
  </TR>
  <TR>
    <TD><span data-ttu-id="6ea94-133">Man&#42;</span><span class="sxs-lookup"><span data-stu-id="6ea94-133">Man&#42;</span></span></TD>
    <TD><span data-ttu-id="6ea94-134">Commence par <b>Man</b> avec respect de la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-134">Starts with <b>Man</b> and case sensitive.</span></span></TD>
    <TD><span data-ttu-id="6ea94-135">Tous les enregistrements qui commencent par le texte <b>Man</b>.</span><span class="sxs-lookup"><span data-stu-id="6ea94-135">All records that start with the text <b>Man</b>.</span></span></TD>
  </TR>
  <TR>
    <TD><span data-ttu-id="6ea94-136">'man'</span><span class="sxs-lookup"><span data-stu-id="6ea94-136">'man'</span></span></TD>
    <TD><span data-ttu-id="6ea94-137">Texte exact avec respect de la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-137">An exact text and case sensitive.</span></span></TD>
    <TD><span data-ttu-id="6ea94-138">Tous les enregistrements qui correspondent exactement à <b>man</b>.</span><span class="sxs-lookup"><span data-stu-id="6ea94-138">All records that match <b>man</b> exactly.</span></span></TD>
  </TR>
  <TR>
    <TD><span data-ttu-id="6ea94-139">@man*</span><span class="sxs-lookup"><span data-stu-id="6ea94-139">@man*</span></span> </TD>
    <TD><span data-ttu-id="6ea94-140">Commence par et ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-140">Starts with and case insensitive.</span></span></TD>
    <TD><span data-ttu-id="6ea94-141">Tous les enregistrements qui commencent par <b>man</b>.</span><span class="sxs-lookup"><span data-stu-id="6ea94-141">All records that start with <b>man</b>.</span></span></TD>
  </TR>
    <TR>
    <TD><span data-ttu-id="6ea94-142">@&#42;man</span><span class="sxs-lookup"><span data-stu-id="6ea94-142">@&#42;man</span></span></TD>
    <TD><span data-ttu-id="6ea94-143">Se termine par et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-143">Ends with and case insensitive.</span></span></TD>
    <TD><span data-ttu-id="6ea94-144">Tous les enregistrements qui se terminent par <b>man</b>.</span><span class="sxs-lookup"><span data-stu-id="6ea94-144">All records that end with <b>man</b>.</span></span></TD>
  </TR>
</TABLE>

> [!NOTE]  
>   <span data-ttu-id="6ea94-145">Vous ne pouvez pas utiliser de caractères génériques lors du filtrage des champs d'énumération, tels que le champ **Statut** sur les commandes vente.</span><span class="sxs-lookup"><span data-stu-id="6ea94-145">You cannot use a wildcard when filtering on enumeration fields, such as the **Status** field on sales orders.</span></span> <span data-ttu-id="6ea94-146">Pour entrer un filtre pour ce type de champ, vous pouvez saisir la valeur numérique comme paramètre de filtre.</span><span class="sxs-lookup"><span data-stu-id="6ea94-146">To enter a filter for this type of field, you can enter the numeric value as a filtering parameter.</span></span> <span data-ttu-id="6ea94-147">Par exemple, dans le champ **Statut** sur une commande vente qui a les valeurs **Ouvert**, **Lancé**, **Approbation suspendue** et **Acompte suspendu**, utilisez les valeurs **0**, **1**, **2** et **3** pour filtrer ces options.</span><span class="sxs-lookup"><span data-stu-id="6ea94-147">For example, in the **Status** field on a sales order that has the values **Open**, **Released**, **Pending Approval**, and **Pending Prepayment**, use the values **0**, **1**, **2**, and **3** to filter for these options.</span></span> 

## <a name="searching-by-using-column-filters"></a><span data-ttu-id="6ea94-148">Recherche à l'aide des filtres de colonne</span><span class="sxs-lookup"><span data-stu-id="6ea94-148">Searching by using column Filters</span></span>
<span data-ttu-id="6ea94-149">Vous pouvez ajouter un filtre sur une ou plusieurs colonnes d'une liste.</span><span class="sxs-lookup"><span data-stu-id="6ea94-149">You can add a filter on one or more columns in a list.</span></span> <span data-ttu-id="6ea94-150">Le filtrage des colonnes est une fonction plus flexible et améliorée que le filtre rapide.</span><span class="sxs-lookup"><span data-stu-id="6ea94-150">Filtering on columns is more flexible and enhanced than the Quick Filter.</span></span> 

### <a name="to-add-a-filter-on-a-column"></a><span data-ttu-id="6ea94-151">Pour ajouter un filtre à une colonne</span><span class="sxs-lookup"><span data-stu-id="6ea94-151">To add a filter on a column</span></span>
1.  <span data-ttu-id="6ea94-152">Avant d'ajouter un filtre, choisissez l'icône ![Afficher sous forme de liste](media/ui_show_as_list_icon.png "Afficher sous forme de liste") pour passer à la vue de liste.</span><span class="sxs-lookup"><span data-stu-id="6ea94-152">Before you add a filter, choose ![Show as list](media/ui_show_as_list_icon.png "Show as list arrow left") icon to change to the list view.</span></span>
2. <span data-ttu-id="6ea94-153">Cliquez sur la flèche vers le bas dans l'en-tête de colonne, puis choisissez **Filtrer**.</span><span class="sxs-lookup"><span data-stu-id="6ea94-153">Choose the downwards arrow in the column heading, and then choose **Filter**.</span></span>
3. <span data-ttu-id="6ea94-154">Exécutez l'une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="6ea94-154">Do one of the following:</span></span> 
  -  <span data-ttu-id="6ea94-155">Choisissez *…* en regard de la zone pour sélectionner une valeur dans la liste.</span><span class="sxs-lookup"><span data-stu-id="6ea94-155">Choose *...* next to the box to select a value from a list.</span></span>
  -  <span data-ttu-id="6ea94-156">Entrez les critères de filtre dans la zone.</span><span class="sxs-lookup"><span data-stu-id="6ea94-156">Enter filter criteria in the box.</span></span> <span data-ttu-id="6ea94-157">Consultez la section suivante pour plus de détails.</span><span class="sxs-lookup"><span data-stu-id="6ea94-157">See the next section for details.</span></span>
4. <span data-ttu-id="6ea94-158">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="6ea94-158">Choose the **OK** button.</span></span>

## <a name="filter-criteria-and-symbols"></a><span data-ttu-id="6ea94-159">Critères et symboles de filtre</span><span class="sxs-lookup"><span data-stu-id="6ea94-159">Filter criteria and symbols</span></span>
<span data-ttu-id="6ea94-160">Lorsque vous saisissez des critères, vous pouvez utiliser tous les chiffres et toutes les lettres que vous utilisez habituellement dans ce champ.</span><span class="sxs-lookup"><span data-stu-id="6ea94-160">When you enter criteria, you can use all the numbers and letters that you can normally use in the field.</span></span> <span data-ttu-id="6ea94-161">En plus, vous pouvez utiliser des symboles spéciaux pour filtrer davantage les résultats.</span><span class="sxs-lookup"><span data-stu-id="6ea94-161">In addition, you can use special symbols to further filter the results.</span></span> <span data-ttu-id="6ea94-162">Les tables suivantes indiquent les symboles qui peuvent être utilisés dans les filtres.</span><span class="sxs-lookup"><span data-stu-id="6ea94-162">The following tables show the symbols which can be used in filters.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="6ea94-163">Il peut y avoir des instances où les valeurs de champ contiennent ces symboles et vous souhaitez les filtrer.</span><span class="sxs-lookup"><span data-stu-id="6ea94-163">There may be instances where field values contain these symbols and you want to filter on them.</span></span> <span data-ttu-id="6ea94-164">Pour ce faire, vous devez inclure l'expression de filtre qui contient le symbole entre guillemets (").</span><span class="sxs-lookup"><span data-stu-id="6ea94-164">To do this, you must include the filter expression that contains the symbol in quotation marks ('').</span></span> <span data-ttu-id="6ea94-165">Par exemple, si vous souhaitez filtrer les enregistrements commençant par le texte *S&R*, l'expression de filtre est **'S&R*'**.</span><span class="sxs-lookup"><span data-stu-id="6ea94-165">For example, if you want to filter on records that start with the text *S&R*, the filter expression is **'S&R*'**.</span></span>  
  
### <a name="-interval"></a><span data-ttu-id="6ea94-166">(..) Intervalle</span><span class="sxs-lookup"><span data-stu-id="6ea94-166">(..) Interval</span></span>  
  
|<span data-ttu-id="6ea94-167">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-167">Sample Expression</span></span>|<span data-ttu-id="6ea94-168">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-168">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-169">1100..2100</span><span class="sxs-lookup"><span data-stu-id="6ea94-169">1100..2100</span></span>|<span data-ttu-id="6ea94-170">Numéros de 1100 à 2100</span><span class="sxs-lookup"><span data-stu-id="6ea94-170">Numbers 1100 through 2100</span></span>|  
|<span data-ttu-id="6ea94-171">..2500</span><span class="sxs-lookup"><span data-stu-id="6ea94-171">..2500</span></span>|<span data-ttu-id="6ea94-172">Jusqu'à 2500 inclus</span><span class="sxs-lookup"><span data-stu-id="6ea94-172">Up to and including 2500</span></span>|  
|<span data-ttu-id="6ea94-173">..12 31 00</span><span class="sxs-lookup"><span data-stu-id="6ea94-173">..12 31 00</span></span>|<span data-ttu-id="6ea94-174">Dates jusqu'au 31/12/00 compris</span><span class="sxs-lookup"><span data-stu-id="6ea94-174">Dates up to and including 12 31 00</span></span>|  
|<span data-ttu-id="6ea94-175">P8..</span><span class="sxs-lookup"><span data-stu-id="6ea94-175">P8..</span></span>|<span data-ttu-id="6ea94-176">Informations sur la période comptable 8 et les suivantes</span><span class="sxs-lookup"><span data-stu-id="6ea94-176">Information for accounting period 8 and thereafter</span></span>|  
|<span data-ttu-id="6ea94-177">..23</span><span class="sxs-lookup"><span data-stu-id="6ea94-177">..23</span></span>|<span data-ttu-id="6ea94-178">Antérieur au 23/mois en cours/année en cours 23:59:59</span><span class="sxs-lookup"><span data-stu-id="6ea94-178">From the beginning date until 23-current month-current year 23:59:59</span></span>|  
|<span data-ttu-id="6ea94-179">23..</span><span class="sxs-lookup"><span data-stu-id="6ea94-179">23..</span></span>|<span data-ttu-id="6ea94-180">Postérieur au 23/mois en cours/année en cours 0:00:00</span><span class="sxs-lookup"><span data-stu-id="6ea94-180">From 23-current month-current year 0:00:00 until the end of time</span></span>|  
|<span data-ttu-id="6ea94-181">22..23</span><span class="sxs-lookup"><span data-stu-id="6ea94-181">22..23</span></span>|<span data-ttu-id="6ea94-182">Entre le 22/mois en cours/année en cours 0:00:00 et le 23/mois en cours/année en cours 23:59:59</span><span class="sxs-lookup"><span data-stu-id="6ea94-182">From 22-current month-current year 0:00:00 until 23-current month-current year 23:59:59</span></span>|  
  
### <a name="124-eitheror"></a><span data-ttu-id="6ea94-183">(&#124;) Et/ou</span><span class="sxs-lookup"><span data-stu-id="6ea94-183">(&#124;) Either/or</span></span>  
  
|<span data-ttu-id="6ea94-184">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-184">Sample Expression</span></span>|<span data-ttu-id="6ea94-185">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-185">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-186">1200&#124;1300</span><span class="sxs-lookup"><span data-stu-id="6ea94-186">1200&#124;1300</span></span>|<span data-ttu-id="6ea94-187">Numéros incluant 1200 ou 1300</span><span class="sxs-lookup"><span data-stu-id="6ea94-187">Numbers with 1200 or 1300</span></span>|  
  
### <a name="-not-equal-to"></a><span data-ttu-id="6ea94-188">(<>) Différent de</span><span class="sxs-lookup"><span data-stu-id="6ea94-188">(<>) Not equal to</span></span>  
  
|<span data-ttu-id="6ea94-189">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-189">Sample Expression</span></span>|<span data-ttu-id="6ea94-190">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-190">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-191"><>0</span><span class="sxs-lookup"><span data-stu-id="6ea94-191"><>0</span></span>|<span data-ttu-id="6ea94-192">Tous les numéros à l'exception de 0</span><span class="sxs-lookup"><span data-stu-id="6ea94-192">All numbers except 0</span></span><br /><br /> <span data-ttu-id="6ea94-193">La version SQL Server vous permet de combiner ce symbole avec une expression de caractères génériques.</span><span class="sxs-lookup"><span data-stu-id="6ea94-193">The SQL Server Option allows you to combine this symbol with a wild card expression.</span></span> <span data-ttu-id="6ea94-194">Par exemple, <>A* signifie différent de tout texte commençant par A.</span><span class="sxs-lookup"><span data-stu-id="6ea94-194">For example, <>A* meaning not equal to any text that starts with A.</span></span>|  
  
### <a name="-greater-than"></a><span data-ttu-id="6ea94-195">(>) Supérieur à</span><span class="sxs-lookup"><span data-stu-id="6ea94-195">(>) Greater than</span></span>  
  
|<span data-ttu-id="6ea94-196">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-196">Sample Expression</span></span>|<span data-ttu-id="6ea94-197">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-197">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-198">>1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-198">>1200</span></span>|<span data-ttu-id="6ea94-199">Numéros supérieurs à 1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-199">Numbers greater than 1200</span></span>|  
  
### <a name="-greater-than-or-equal-to"></a><span data-ttu-id="6ea94-200">(>=) Supérieur ou égal à</span><span class="sxs-lookup"><span data-stu-id="6ea94-200">(>=) Greater than or equal to</span></span>  
  
|<span data-ttu-id="6ea94-201">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-201">Sample Expression</span></span>|<span data-ttu-id="6ea94-202">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-202">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-203">>=1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-203">>=1200</span></span>|<span data-ttu-id="6ea94-204">Numéros supérieurs ou égaux à 1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-204">Numbers greater than or equal to 1200</span></span>|  
  
### <a name="-less-than"></a><span data-ttu-id="6ea94-205">(<) Inférieur à</span><span class="sxs-lookup"><span data-stu-id="6ea94-205">(<) Less than</span></span>  
  
|<span data-ttu-id="6ea94-206">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-206">Sample Expression</span></span>|<span data-ttu-id="6ea94-207">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-207">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-208"><1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-208"><1200</span></span>|<span data-ttu-id="6ea94-209">Numéros inférieurs à 1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-209">Numbers less than 1200</span></span>|  
  
### <a name="-less-than-or-equal-to"></a><span data-ttu-id="6ea94-210">(<=) Inférieur ou égal à</span><span class="sxs-lookup"><span data-stu-id="6ea94-210">(<=) Less than or equal to</span></span>  
  
|<span data-ttu-id="6ea94-211">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-211">Sample Expression</span></span>|<span data-ttu-id="6ea94-212">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-212">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-213"><=1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-213"><=1200</span></span>|<span data-ttu-id="6ea94-214">Numéros inférieurs ou égaux à 1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-214">Numbers less than or equal to 1200</span></span>|  
  
### <a name="-and"></a><span data-ttu-id="6ea94-215">(&) Et</span><span class="sxs-lookup"><span data-stu-id="6ea94-215">(&) And</span></span>  
  
|<span data-ttu-id="6ea94-216">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-216">Sample Expression</span></span>|<span data-ttu-id="6ea94-217">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-217">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-218">>200&<1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-218">>200&<1200</span></span>|<span data-ttu-id="6ea94-219">Nombres supérieurs à 200 et inférieurs à 1200</span><span class="sxs-lookup"><span data-stu-id="6ea94-219">Numbers greater than 200 and less than 1200</span></span>|  
  
### <a name="-an-exact-character-match"></a><span data-ttu-id="6ea94-220">(") Correspondance exacte de caractères</span><span class="sxs-lookup"><span data-stu-id="6ea94-220">('') An exact character match</span></span>  
  
|<span data-ttu-id="6ea94-221">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-221">Sample Expression</span></span>|<span data-ttu-id="6ea94-222">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-222">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-223">'man'</span><span class="sxs-lookup"><span data-stu-id="6ea94-223">'man'</span></span>|<span data-ttu-id="6ea94-224">Texte qui correspond exactement à man et qui respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-224">Text that matches man exactly and is case sensitive.</span></span>|  
  
### <a name="-case-insensitive"></a><span data-ttu-id="6ea94-225">(@) Non-respect de la casse</span><span class="sxs-lookup"><span data-stu-id="6ea94-225">(@) Case insensitive</span></span>  
  
|<span data-ttu-id="6ea94-226">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-226">Sample Expression</span></span>|<span data-ttu-id="6ea94-227">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-227">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-228">@man*</span><span class="sxs-lookup"><span data-stu-id="6ea94-228">@man*</span></span>|<span data-ttu-id="6ea94-229">Texte qui commence par man et qui ne respecte pas la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-229">Text that starts with man and is case insensitive.</span></span>|  
  
### <a name="-an-indefinite-number-of-unknown-characters"></a><span data-ttu-id="6ea94-230">(*) Un chiffre quelconque ou des caractères inconnus</span><span class="sxs-lookup"><span data-stu-id="6ea94-230">(*) An indefinite number of unknown characters</span></span>  
  
|<span data-ttu-id="6ea94-231">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-231">Sample Expression</span></span>|<span data-ttu-id="6ea94-232">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-232">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-233">*Co*</span><span class="sxs-lookup"><span data-stu-id="6ea94-233">*Co*</span></span>|<span data-ttu-id="6ea94-234">Texte qui contient « Co » et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-234">Text that contains "Co" and is case sensitive.</span></span>|  
|<span data-ttu-id="6ea94-235">*Co</span><span class="sxs-lookup"><span data-stu-id="6ea94-235">*Co</span></span>|<span data-ttu-id="6ea94-236">Texte qui se termine par « Co » et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-236">Text that ends with "Co" and is case sensitive.</span></span>|  
|<span data-ttu-id="6ea94-237">Co*</span><span class="sxs-lookup"><span data-stu-id="6ea94-237">Co*</span></span>|<span data-ttu-id="6ea94-238">Texte qui commence par « Co » et respecte la casse.</span><span class="sxs-lookup"><span data-stu-id="6ea94-238">Text that begins with "Co" and is case sensitive.</span></span>|  
  
### <a name="-one-unknown-character"></a><span data-ttu-id="6ea94-239">(?) Un caractère inconnu</span><span class="sxs-lookup"><span data-stu-id="6ea94-239">(?) One unknown character</span></span>  
  
|<span data-ttu-id="6ea94-240">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-240">Sample Expression</span></span>|<span data-ttu-id="6ea94-241">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-241">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-242">Hans?n</span><span class="sxs-lookup"><span data-stu-id="6ea94-242">Hans?n</span></span>|<span data-ttu-id="6ea94-243">Texte tel que Hansen ou Hanson</span><span class="sxs-lookup"><span data-stu-id="6ea94-243">Text such as Hansen or Hanson</span></span>|  
  
### <a name="combined-format-expressions"></a><span data-ttu-id="6ea94-244">Expressions de format combinées</span><span class="sxs-lookup"><span data-stu-id="6ea94-244">Combined format expressions</span></span>  
  
|<span data-ttu-id="6ea94-245">Expression</span><span class="sxs-lookup"><span data-stu-id="6ea94-245">Sample Expression</span></span>|<span data-ttu-id="6ea94-246">Enregistrements affichés</span><span class="sxs-lookup"><span data-stu-id="6ea94-246">Records Displayed</span></span>|  
|-----------------------|-----------------------|  
|<span data-ttu-id="6ea94-247">5999&#124;8100..8490</span><span class="sxs-lookup"><span data-stu-id="6ea94-247">5999&#124;8100..8490</span></span>|<span data-ttu-id="6ea94-248">Inclure tous les enregistrements ayant pour numéro 5999 ou un numéro de l'intervalle 8100 à 8490.</span><span class="sxs-lookup"><span data-stu-id="6ea94-248">Include any records with the number 5999 or a number from the interval 8100 through 8490.</span></span>|  
|<span data-ttu-id="6ea94-249">..1299&#124;1400..</span><span class="sxs-lookup"><span data-stu-id="6ea94-249">..1299&#124;1400..</span></span>|<span data-ttu-id="6ea94-250">Inclure tous les enregistrements qui portent un numéro inférieur ou égal à 1299 ou un numéro supérieur ou égal à 1400 (tous les numéros sauf ceux compris entre 1300 et 1399).</span><span class="sxs-lookup"><span data-stu-id="6ea94-250">Include records with a number less than or equal to 1299 or a number equal to 1400 or greater (all numbers except 1300 through 1399).</span></span>|  
|<span data-ttu-id="6ea94-251">>50&<100</span><span class="sxs-lookup"><span data-stu-id="6ea94-251">>50&<100</span></span>|<span data-ttu-id="6ea94-252">Inclure les enregistrements qui portent un numéro supérieur à 50 et inférieur à 100 (numéros 51 à 99).</span><span class="sxs-lookup"><span data-stu-id="6ea94-252">Include records with numbers that are greater than 50 and less than 100 (numbers 51 through 99).</span></span>|  
 
## <a name="see-also"></a><span data-ttu-id="6ea94-253">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="6ea94-253">See Also</span></span>
<span data-ttu-id="6ea94-254">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="6ea94-254">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
