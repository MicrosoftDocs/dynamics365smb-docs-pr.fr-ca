---
title: "Entrée des dates et des heures dans Business Central | Microsoft Docs"
description: "Apprendre comment entrer des dates et des heures avec diverses astuces de productivité telles que la sténographie, les expressions et les plages. Filtrez les listes ou les rapports à des dates ou périodes spécifiques."
documentationcenter: 
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: dates, reporting, filter, calendar, shorthand, range
ms.date: 10/01/2018
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 8717d60a8449ca300eaf9c1a5c4b137ea1a1a247
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---

# <a name="working-with-calendar-dates-and-times"></a><span data-ttu-id="69278-104">Utilisation de dates civiles et les heures</span><span class="sxs-lookup"><span data-stu-id="69278-104">Working with Calendar Dates and Times</span></span>
[!INCLUDE[d365fin](includes/d365fin_long_md.md)] <span data-ttu-id="69278-105">offre plusieurs méthodes principales de saisie des dates et des heures, y compris des fonctions puissantes qui accélèrent la saisie de données, ou vous permettent de saisir des expressions de calendrier complexes.</span><span class="sxs-lookup"><span data-stu-id="69278-105">offers multiple ways to enter dates and times, including powerful features that accelerate data entry, or help you write complex calendar expressions.</span></span> <span data-ttu-id="69278-106">Il existe différents emplacements dans toute l'application où vous pouvez entrer des dates et des heures dans les champs.</span><span class="sxs-lookup"><span data-stu-id="69278-106">There are various places throughout the application where you can enter dates and times in fields.</span></span> <span data-ttu-id="69278-107">Par exemple, sur un document de vente, vous pouvez définir la date de livraison.</span><span class="sxs-lookup"><span data-stu-id="69278-107">For example, on a sales order, you can set the shipment date.</span></span> <span data-ttu-id="69278-108">En filtrant des listes ou des données de rapports, vous pouvez entrer des dates et des heures pour désigner uniquement les données qui vous intéressent.</span><span class="sxs-lookup"><span data-stu-id="69278-108">When filtering lists or report data, you can enter dates and times to pinpoint only the data that you are interested in.</span></span>

## <a name="check-your-region-and-language-settings"></a><span data-ttu-id="69278-109">Vérifiez les paramètres de zone et de langue</span><span class="sxs-lookup"><span data-stu-id="69278-109">Check your region and language settings</span></span>
<span data-ttu-id="69278-110">La page [**Mes paramètres**](https://businesscentral.dynamics.com?page=9176 "Accéder directement à votre page de paramètres utilisateurs dans Business Central") spécifie **Région** et **Langue** que vous utilisez dans l'application.</span><span class="sxs-lookup"><span data-stu-id="69278-110">The [**My Settings**](https://businesscentral.dynamics.com?page=9176 "Go directly to your user settings page in Business Central") page specifies the **Region** and **Language** that you are using in the application.</span></span> <span data-ttu-id="69278-111">Ces paramètres ont une incidence sur la manière dont vous saisissez des dates et des heures.</span><span class="sxs-lookup"><span data-stu-id="69278-111">These settings influence how you enter dates and times.</span></span> 

-   <span data-ttu-id="69278-112">Le paramètre **Région** détermine la manière dont les dates, heures, nombres et devises sont affichés ou mis en forme.</span><span class="sxs-lookup"><span data-stu-id="69278-112">The **Region** setting determines how dates, times, numbers, and currencies are shown or formatted.</span></span>

-   <span data-ttu-id="69278-113">Pour des modèles de date qui impliquent des mots, la langue des mots utilisée doit correspondre au paramètre **Langue**.</span><span class="sxs-lookup"><span data-stu-id="69278-113">For date patterns that involve words, the language of the words that you use must correspond to the **Language** setting.</span></span>

> [!NOTE]
> [!INCLUDE[d365fin](includes/d365fin_long_md.md)] <span data-ttu-id="69278-114">utilise le système du calendrier grégorien.</span><span class="sxs-lookup"><span data-stu-id="69278-114">uses the Gregorian calendar system.</span></span>

<!-- 
The following sections describe how you can enter dates, times, datetimes, durations, date ranges, and how you use date formulas.
-->
## <a name="entering-dates"></a><span data-ttu-id="69278-115">Saisie de dates</span><span class="sxs-lookup"><span data-stu-id="69278-115">Entering Dates</span></span>
<span data-ttu-id="69278-116">Dans un champ de date, vous pouvez saisir une date à l'aide du format standard pour votre paramètre de zone.</span><span class="sxs-lookup"><span data-stu-id="69278-116">In a date field, you can enter a date using the standard format for your region setting.</span></span> <span data-ttu-id="69278-117">Les différentes régions peuvent utiliser différents séparateurs entre les jours, mois et années.</span><span class="sxs-lookup"><span data-stu-id="69278-117">Different regions can use different separators between the days, months and years.</span></span> <span data-ttu-id="69278-118">Par exemple, certaines régions utilisent les tirets (mm-jj-aaaa) et d'autres les barres obliques (mm/jj/aaaa).</span><span class="sxs-lookup"><span data-stu-id="69278-118">For example, some regions use dashes (mm-dd-yyyy) and others use forward slashes (mm/dd/yyyy).</span></span> <span data-ttu-id="69278-119">Cependant, vous pouvez utiliser tous les séparateurs, même un espace, et la date est modifiée automatiquement pour utiliser les séparateurs correspondant à votre région.</span><span class="sxs-lookup"><span data-stu-id="69278-119">However, you can use any separators, even a space, and the date will automatically be changed to use separators that match your region.</span></span>

<span data-ttu-id="69278-120">Notez que le format des dates affichées sur les rapports imprimés ou les documents envoyés par courriel n'est pas influencé par votre choix personnel au niveau du paramètre de région.</span><span class="sxs-lookup"><span data-stu-id="69278-120">Note that the format in which dates are displayed on printed reports or emailed documents is not influenced by your personal choice of region setting.</span></span>

<span data-ttu-id="69278-121">Pour travailler plus productivement avec des dates et des heures, vous pouvez utiliser les méthodes ou les formats décrits dans les sections suivantes.</span><span class="sxs-lookup"><span data-stu-id="69278-121">To work more productively with dates and times, you can use any of the methods or formats that are described in the following sections.</span></span> 

### <a name="picking-dates-from-the-calendar"></a><span data-ttu-id="69278-122">Choisir des dates dans le calendrier</span><span class="sxs-lookup"><span data-stu-id="69278-122">Picking dates from the calendar</span></span>
<span data-ttu-id="69278-123">Tout champ affichant une icône de calendrier peut être paramétré à l'aide du sélecteur de date civile.</span><span class="sxs-lookup"><span data-stu-id="69278-123">Any field displaying a calendar icon can be set using the calendar date picker.</span></span> <span data-ttu-id="69278-124">Pour afficher le sélecteur de date civile, activer l'icône de calendrier ou appuyer sur le raccourci clavier Ctrl+Début dans le champ.</span><span class="sxs-lookup"><span data-stu-id="69278-124">To display the calendar date picker, activate the calendar icon or press the Ctrl + Home keyboard shortcut in the field.</span></span>

<span data-ttu-id="69278-125">![Champs de date](media/ui-date-field.png "Exemple d'un champ de date")</span><span class="sxs-lookup"><span data-stu-id="69278-125">![Date fields](media/ui-date-field.png "Example of a date field")</span></span>

<span data-ttu-id="69278-126">Voir aussi [Raccourcis clavier du sélecteur de date civile](keyboard-shortcuts.md#calendarshortcuts)</span><span class="sxs-lookup"><span data-stu-id="69278-126">See also [Keyboard Shortcuts in the calendar date picker](keyboard-shortcuts.md#calendarshortcuts)</span></span>

### <a name="today"></a><span data-ttu-id="69278-127">Aujourd'hui</span><span class="sxs-lookup"><span data-stu-id="69278-127">Today</span></span>
<span data-ttu-id="69278-128">Entrez le mot pour `today`, dans la langue définie par le paramètre **Langue**, qui définit la date à la date actuelle.</span><span class="sxs-lookup"><span data-stu-id="69278-128">Enter the word for `today`, in the language set by **Language** setting, that will set the date to the current date.</span></span> <span data-ttu-id="69278-129">Au lieu de saisir le mot entier, vous pouvez saisir une partie du mot, en commençant par le début par exemple `tod` ou `t`, tant que ce n'est pas également le début d'un autre mot.</span><span class="sxs-lookup"><span data-stu-id="69278-129">Instead of entering the entire word, you can enter part of the word, starting from the beginning, such as `t` or `tod`, as long as it is not also the start of another word.</span></span>

### <a name="day-week-year-pattern"></a><span data-ttu-id="69278-130">Modèle jour\-semaine\-année</span><span class="sxs-lookup"><span data-stu-id="69278-130">Day\-week\-year pattern</span></span>
<span data-ttu-id="69278-131">Vous pouvez saisir une date comme un jour de la semaine suivi d'un numéro de semaine et, éventuellement, une année.</span><span class="sxs-lookup"><span data-stu-id="69278-131">You can enter a date as a weekday followed by a week number and, optionally, a year.</span></span> <span data-ttu-id="69278-132">Par exemple, `Mon25` ou `mon25` signifie le lundi de la semaine 25.</span><span class="sxs-lookup"><span data-stu-id="69278-132">For example, `Mon25` or `mon25` means Monday in week 25.</span></span> <span data-ttu-id="69278-133">Si vous ne saisissez pas une année, l'année de la date de travail est utilisée.</span><span class="sxs-lookup"><span data-stu-id="69278-133">If you do not enter a year, the year of the work date is used.</span></span>

<span data-ttu-id="69278-134">Au lieu de saisir le mot entier du jour de la semaine, vous pouvez saisir une partie du mot, en commençant du début.</span><span class="sxs-lookup"><span data-stu-id="69278-134">Instead of entering the entire word for the day of the week, you can enter part of the word, starting from the beginning.</span></span> <span data-ttu-id="69278-135">Dans le cas de conflits (par exemple avec `s` qui peut être samedi ou dimanche), les jours sont évalués en fonction de le paramètre d'une zone.</span><span class="sxs-lookup"><span data-stu-id="69278-135">In case of conflicts (such as with `s` which could be Saturday or Sunday), the days are evaluated according to the region setting.</span></span> <span data-ttu-id="69278-136">L'entrée est d'abord évaluée par rapport à la `workdate` et `today`, ne l'oubliez pas en abrégeant.</span><span class="sxs-lookup"><span data-stu-id="69278-136">The input is first evaluated against `workdate` and `today` as well, so keep this in mind when abbreviating.</span></span> <span data-ttu-id="69278-137">Par exemple, `t` signifie déjà aujourd'hui, ce qui ne peut pas être mardi ou jeudi.</span><span class="sxs-lookup"><span data-stu-id="69278-137">For example, `t` already means today, so it cannot mean Tuesday or Thursday.</span></span>

<span data-ttu-id="69278-138">Le schéma de numéros de semaine est toujours ISO 8601, où la semaine 1 est la semaine avec le 4 janvier dans celle-ci, ou la semaine avec le premier jeudi de l'exercice.</span><span class="sxs-lookup"><span data-stu-id="69278-138">The week number scheme is always ISO 8601, where week 1 is the week with 4 January in it, or the week with the first Thursday of the year.</span></span>

### <a name="digit-patterns"></a><span data-ttu-id="69278-139">Modèles de chiffres</span><span class="sxs-lookup"><span data-stu-id="69278-139">Digit patterns</span></span>
<span data-ttu-id="69278-140">Vous pouvez saisir deux, quatre, six ou huit chiffres dans un champ date :</span><span class="sxs-lookup"><span data-stu-id="69278-140">In a date field you can enter two, four, six, or eight digits:</span></span>

-   <span data-ttu-id="69278-141">Si vous ne saisissez que deux chiffres, ils sont interprétés comme le jour, et le mois et l'année de la date de travail sont ajoutés.</span><span class="sxs-lookup"><span data-stu-id="69278-141">If you enter only two digits, this is interpreted as the day, and it will add the month and the year of the work date.</span></span>

-   <span data-ttu-id="69278-142">Si vous saisissez quatre chiffres, ils sont interprétés comme le jour et le mois, et l'année de la date de travail est ajoutée.</span><span class="sxs-lookup"><span data-stu-id="69278-142">If you enter four digits, this is interpreted as the day and the month, and it will add the year of the work date.</span></span> <span data-ttu-id="69278-143">L'ordre du jour et du mois est déterminé par les paramètres de région.</span><span class="sxs-lookup"><span data-stu-id="69278-143">The order of the day and month is determined by your region settings.</span></span> <span data-ttu-id="69278-144">Même si vos paramètres de région ont l'année avant le jour et le mois, quatre chiffres sont interprétés en tant que jour et mois.</span><span class="sxs-lookup"><span data-stu-id="69278-144">Even if your region settings have the year before the day and month, four digits are interpreted as the day and month.</span></span>

-   <span data-ttu-id="69278-145">Si la date que vous souhaitez saisir est comprise entre le 01/01/1930 et le 31/12/2029, vous pouvez saisir les deux chiffres de l'année ; sinon saisissez les quatre chiffres.</span><span class="sxs-lookup"><span data-stu-id="69278-145">If the date you want to enter is in the range 01/01/1930 through 12/31/2029, you can enter the year with two digits; otherwise, enter the year with four digits.</span></span>

### <a name="current-work-date"></a><span data-ttu-id="69278-146">Date de travail actuelle</span><span class="sxs-lookup"><span data-stu-id="69278-146">Current work date</span></span>
<span data-ttu-id="69278-147">La fonction de date de travail vous permet d'enregistrer les transactions en utilisant une date qui est différente de la date du jour.</span><span class="sxs-lookup"><span data-stu-id="69278-147">The work date feature allows you to record transations using a date that is different from the current date.</span></span>

<span data-ttu-id="69278-148">Le mot « date de travail », dans la langue définie par le paramètre **Langue**, définit la date à laquelle la date de travail configurée actuellement est spécifiée sur la page [**Mes paramètres**](https://businesscentral.dynamics.com?page=9176 "Accéder directement à votre page de paramètres utilisateurs dans Business Central").</span><span class="sxs-lookup"><span data-stu-id="69278-148">The word for 'workdate', in the language set by **Language** setting, will set the date to the currently set work date that is specified on the [**My Settings**](https://businesscentral.dynamics.com?page=9176 "Go directly to your user settings page in Business Central") page.</span></span> <span data-ttu-id="69278-149">Au lieu de saisir le mot entier, vous pouvez saisir une partie du mot, en commençant du début, comme "t" pour travail.</span><span class="sxs-lookup"><span data-stu-id="69278-149">Instead of entering the entire word, you can enter part of the word, starting from the beginning, such as 'w' or 'work'.</span></span>

<span data-ttu-id="69278-150">Si vous ne définissez pas de date de travail, la date actuelle sera utilisée comme date de travail.</span><span class="sxs-lookup"><span data-stu-id="69278-150">If you have not defined a work date, the current date will be used as the work date.</span></span> <span data-ttu-id="69278-151">Vous souhaiterez peut-être utiliser une date de travail si vous avez beaucoup de transactions avec une date différente de la date d'aujourd'hui.</span><span class="sxs-lookup"><span data-stu-id="69278-151">You may want to use a work date if you have many transactions with a date other than today's date.</span></span>

<span data-ttu-id="69278-152">Voir aussi [Modification des paramètres de base, comme la date de travail](ui-change-basic-settings.md#work-date)</span><span class="sxs-lookup"><span data-stu-id="69278-152">See also [Changing Basic Settings, such as the Work Date](ui-change-basic-settings.md#work-date)</span></span>

### <a name="closing-date"></a><span data-ttu-id="69278-153">Date de fermeture</span><span class="sxs-lookup"><span data-stu-id="69278-153">Closing Date</span></span>
<span data-ttu-id="69278-154">Lorsque vous fermez un exercice financier, vous pouvez utiliser des dates de fermeture pour indiquer qu'une écriture est une écriture de fermeture.</span><span class="sxs-lookup"><span data-stu-id="69278-154">When you close a fiscal year, you can use closing dates to indicate that an entry is a closing entry.</span></span> <span data-ttu-id="69278-155">Techniquement, une date de fermeture se trouve entre deux dates, par exemple le 31 décembre et le 1er janvier.</span><span class="sxs-lookup"><span data-stu-id="69278-155">A closing date technically is between two dates, for example between Dec 31 and Jan 1.</span></span>

<span data-ttu-id="69278-156">Pour spécifier qu'une date est une date de fermeture, placez un `C` devant cette date, comme `C123101`.</span><span class="sxs-lookup"><span data-stu-id="69278-156">To specify that a date is a closing date, put `C` just before the date, such as `C123101`.</span></span> <span data-ttu-id="69278-157">Ceci peut être utilisé avec tous les modèles de date.</span><span class="sxs-lookup"><span data-stu-id="69278-157">This can be used in combination with all the date patterns.</span></span>

### <a name="examples"></a><span data-ttu-id="69278-158">Exemples</span><span class="sxs-lookup"><span data-stu-id="69278-158">Examples</span></span>
<span data-ttu-id="69278-159">Le tableau suivant affiche des exemples de dates à l'aide de tous les formats.</span><span class="sxs-lookup"><span data-stu-id="69278-159">The following table contains examples of dates using all the formats.</span></span> <span data-ttu-id="69278-160">Il considère les paramètres de région selon lesquels format les dates : **year.month.day.**, une semaine commençant lundi, et l'anglais.</span><span class="sxs-lookup"><span data-stu-id="69278-160">It assumes region settings that format dates according to: **year.month.day.**, a week starting on Monday, and the English language.</span></span>

|<span data-ttu-id="69278-161">**Écriture**</span><span class="sxs-lookup"><span data-stu-id="69278-161">**Entry**</span></span>      |<span data-ttu-id="69278-162">**Interprétation**</span><span class="sxs-lookup"><span data-stu-id="69278-162">**Interpretation**</span></span>      |
|---------------|------------------------|
|`2018.12.31.`|<span data-ttu-id="69278-163">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-163">2018.12.31.</span></span>|
|`181231`|<span data-ttu-id="69278-164">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-164">2018.12.31.</span></span>|
|`18.12.31.`|<span data-ttu-id="69278-165">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-165">2018.12.31.</span></span>|
|`18.12.31.`|<span data-ttu-id="69278-166">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-166">2018.12.31.</span></span>|
|`20181231`|<span data-ttu-id="69278-167">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-167">2018.12.31.</span></span>|
|`18/12,31`|<span data-ttu-id="69278-168">2018.12.31.</span><span class="sxs-lookup"><span data-stu-id="69278-168">2018.12.31.</span></span>|
|`11`|<span data-ttu-id="69278-169">année date travail.mois date travail.11.</span><span class="sxs-lookup"><span data-stu-id="69278-169">work date year.work date month.11.</span></span>|
|`1112`|<span data-ttu-id="69278-170">année date travail.11.12.</span><span class="sxs-lookup"><span data-stu-id="69278-170">work date year.11.12.</span></span>|
|<span data-ttu-id="69278-171">`t` ou `today`</span><span class="sxs-lookup"><span data-stu-id="69278-171">`t` or `today`</span></span>|<span data-ttu-id="69278-172">date du jour</span><span class="sxs-lookup"><span data-stu-id="69278-172">today's date</span></span>|
|<span data-ttu-id="69278-173">`w` ou `workdate`</span><span class="sxs-lookup"><span data-stu-id="69278-173">`w` or `workdate`</span></span>|<span data-ttu-id="69278-174">date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-174">the working date</span></span>|
|<span data-ttu-id="69278-175">`m` ou `Monday`</span><span class="sxs-lookup"><span data-stu-id="69278-175">`m` or `Monday`</span></span>|<span data-ttu-id="69278-176">Lundi de la semaine de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-176">Monday of the work date week</span></span>|
|<span data-ttu-id="69278-177">`tu` ou `Tuesday`</span><span class="sxs-lookup"><span data-stu-id="69278-177">`tu` or `Tuesday`</span></span>|<span data-ttu-id="69278-178">Mardi de la semaine de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-178">Tuesday of the work date week</span></span>|
|<span data-ttu-id="69278-179">`sa` ou `Saturday`</span><span class="sxs-lookup"><span data-stu-id="69278-179">`sa` or `Saturday`</span></span>|<span data-ttu-id="69278-180">Samedi de la semaine de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-180">Saturday of the work date week</span></span>|
|<span data-ttu-id="69278-181">`s` ou `Sunday`</span><span class="sxs-lookup"><span data-stu-id="69278-181">`s` or `Sunday`</span></span>|<span data-ttu-id="69278-182">Dimanche de la semaine de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-182">Sunday of the work date week</span></span>|
|`t23`|<span data-ttu-id="69278-183">Mardi de la semaine 23 de l'année de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-183">Tuesday of week 23 of the work date year</span></span>|
|`t 23`|<span data-ttu-id="69278-184">Mardi de la semaine 23 de l'année de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-184">Tuesday of week 23 of the work date year</span></span>|
|`t-1`|<span data-ttu-id="69278-185">Mardi de la semaine 1 de l'année de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-185">Tuesday of week 1 of the work date year</span></span>|

##  <a name="BKMK_SettingDateRanges"></a> <span data-ttu-id="69278-186">Définition des plages</span><span class="sxs-lookup"><span data-stu-id="69278-186">Setting Ranges</span></span>
<span data-ttu-id="69278-187">Sous Listes, totaux et rapports, vous pouvez définir des filtres sur les dates, heures et dates/heures contenant une valeur de début et éventuellement une valeur de fin pour afficher uniquement les données contenues dans cette plage.</span><span class="sxs-lookup"><span data-stu-id="69278-187">On lists, totals and reports, you can set filters on dates, times and datetimes containing a start value and optionally an end value to display only the data contained in that range.</span></span> <span data-ttu-id="69278-188">Les règles standard s'appliquent à la définition des plages de dates.</span><span class="sxs-lookup"><span data-stu-id="69278-188">The standard rules apply to the way you set date ranges.</span></span>

|<span data-ttu-id="69278-189">**Signification**</span><span class="sxs-lookup"><span data-stu-id="69278-189">**Meaning**</span></span>|<span data-ttu-id="69278-190">**Exemple d'expression (Date)**</span><span class="sxs-lookup"><span data-stu-id="69278-190">**Sample expression (Date)**</span></span>|<span data-ttu-id="69278-191">**Données incluses dans le filtre**</span><span class="sxs-lookup"><span data-stu-id="69278-191">**Data included in the filter**</span></span>|
|-----------|---------------------|--------------------|
|<span data-ttu-id="69278-192">Intervalle</span><span class="sxs-lookup"><span data-stu-id="69278-192">Interval</span></span>|<span data-ttu-id="69278-193">`12 15 00..01 15 01`  \n`..12 15 00`</span><span class="sxs-lookup"><span data-stu-id="69278-193">`12 15 00..01 15 01`  \n`..12 15 00`</span></span>|<span data-ttu-id="69278-194">Enregistrements dont les dates sont comprises entre le 15/12/00 et le 15/01/01 inclusivement.</span><span class="sxs-lookup"><span data-stu-id="69278-194">Records with dates between and including 12 15 00 and 01 15 01.</span></span>  <span data-ttu-id="69278-195">\nEnregistrements dont les dates sont le 12/15/00 ou avant.</span><span class="sxs-lookup"><span data-stu-id="69278-195">\nRecords with dates of 12 15 00 or earlier.</span></span>|
|<span data-ttu-id="69278-196">Et/ou</span><span class="sxs-lookup"><span data-stu-id="69278-196">Either/or</span></span>|<span data-ttu-id="69278-197">\`12 15 00</span><span class="sxs-lookup"><span data-stu-id="69278-197">\`12 15 00</span></span>|<span data-ttu-id="69278-198">12 16 00\`</span><span class="sxs-lookup"><span data-stu-id="69278-198">12 16 00\`</span></span>|<span data-ttu-id="69278-199">Enregistrement dont les dates sont le 12/15/00 ou 12/16/00.</span><span class="sxs-lookup"><span data-stu-id="69278-199">Records with dates of either 12 15 00 or 12 16 00.</span></span> <span data-ttu-id="69278-200">Si des enregistrements comportent des dates pendant ces deux jours, ils sont tous affichés.</span><span class="sxs-lookup"><span data-stu-id="69278-200">If there are records with dates on both days, they will all be displayed.</span></span>|
|<span data-ttu-id="69278-201">Combinaison</span><span class="sxs-lookup"><span data-stu-id="69278-201">Combination</span></span>|<span data-ttu-id="69278-202">\`12 15 00</span><span class="sxs-lookup"><span data-stu-id="69278-202">\`12 15 00</span></span>|<span data-ttu-id="69278-203">12 01 00..12 10 00`  \n`..12 14 00</span><span class="sxs-lookup"><span data-stu-id="69278-203">12 01 00..12 10 00`  \n`..12 14 00</span></span>|<span data-ttu-id="69278-204">12 30 00..\`</span><span class="sxs-lookup"><span data-stu-id="69278-204">12 30 00..\`</span></span>|<span data-ttu-id="69278-205">Enregistrements avec pour dates le 15/12/00 ou entre le 01/12/00 et le 10/12/00 inclus.</span><span class="sxs-lookup"><span data-stu-id="69278-205">Records with dates of 12 15 00 or on dates between and including 12 01 00 and 12 10 00.</span></span>  <span data-ttu-id="69278-206">\nEnregistrements avec dates le 14/12/00 ou avant, ou le 30/12/00 ou après, c'est-à-dire tous les enregistrements exceptés ceux avec des dates comprises entre le 15/12/00 et le 29/12/00 inclusivement.</span><span class="sxs-lookup"><span data-stu-id="69278-206">\nRecords with dates of 12 14 00 or earlier, or dates of 12 30 00 or later, that is, all records except those with dates between and including 12 15 00 and 12 29 00.</span></span>|

<span data-ttu-id="69278-207">Vous pouvez utiliser l'un des formats valides dans les filtres Plage de dates.</span><span class="sxs-lookup"><span data-stu-id="69278-207">You can use any of the valid formats in date range filters.</span></span> <span data-ttu-id="69278-208">Par exemple, `mon14 3..t 4p` appliqué pour un champ Date/heure engendre un filtre à partir de 3 h du matin le lundi de la semaine 14 de l'année de la date de travail en cours, incluse, jusqu'à aujourd'hui à 16 h, inclus.</span><span class="sxs-lookup"><span data-stu-id="69278-208">For example, `mon14 3..t 4p` applied on a datetime field results in a filter from 3 AM on Monday in week 14 of the current work date year, inclusive, until today at 4PM, inclusive.</span></span>


## <a name="using-date-formulas"></a><span data-ttu-id="69278-209">Utilisation de formules date</span><span class="sxs-lookup"><span data-stu-id="69278-209">Using Date Formulas</span></span>
<span data-ttu-id="69278-210">Une formule date est une combinaison abrégée de lettres et de nombres qui spécifie comment calculer les dates.</span><span class="sxs-lookup"><span data-stu-id="69278-210">A date formula is a short, abbreviated combination of letters and numbers that specifies how to calculate dates.</span></span> <span data-ttu-id="69278-211">Vous pouvez entrer des formules date dans différents champs ou filtres de calcul de date.</span><span class="sxs-lookup"><span data-stu-id="69278-211">You can enter date formulas in various date calculation fields or filters.</span></span>

> [!NOTE]
>  <span data-ttu-id="69278-212">Dans tous les champs formule de données, un jour est automatiquement inclus pour couvrir le jour de début de la période.</span><span class="sxs-lookup"><span data-stu-id="69278-212">In all data formula fields, one day is automatically included to cover today as the day when the period starts.</span></span> <span data-ttu-id="69278-213">Par conséquent, si vous saisissez `1W`, par exemple, la période est bien huit jours parce que aujourd'hui est inclus.</span><span class="sxs-lookup"><span data-stu-id="69278-213">Accordingly, for example, if you enter `1W`, then the period is actually eight days because today is included.</span></span> <span data-ttu-id="69278-214">Pour définir une période de sept jours \(une vraie semaine\) avec la date début de la période, vous devez saisir `6D` ou `1W-1D`.</span><span class="sxs-lookup"><span data-stu-id="69278-214">To specify a period of seven days \(one true week\) including the period starting date, then you must enter `6D` or `1W-1D`.</span></span>

<span data-ttu-id="69278-215">Voici quelques exemples d'utilisation de formules date :</span><span class="sxs-lookup"><span data-stu-id="69278-215">Here are some examples of how date formulas can be used:</span></span>

-   <span data-ttu-id="69278-216">La formule date du champ fréquence récurrente des journaux récurrents détermine la fréquence de report de l'écriture sur la ligne journal.</span><span class="sxs-lookup"><span data-stu-id="69278-216">The date formula in the recurring frequency field in recurring journals determines how often the entry on the journal line will be posted.</span></span>

-   <span data-ttu-id="69278-217">La formule date du champ **Période de carence** pour un niveau de rappel précis détermine la période qui doit s'écouler à partir de la date d'échéance \(ou de la date du rappel précédent\) avant la création d'un nouveau rappel.</span><span class="sxs-lookup"><span data-stu-id="69278-217">The date formula in the **Grace Period** field for a specified reminder level determines the period of time that must pass from the due date \(or from the date of the previous reminder\) before a reminder will be created.</span></span>

-   <span data-ttu-id="69278-218">La formule date du champ **Calcul date d'échéance** détermine la manière dont la date d'échéance du rappel est calculée.</span><span class="sxs-lookup"><span data-stu-id="69278-218">The date formula in the **Due Date Calculation** field determines how to calculate the due date on the reminder.</span></span>

<span data-ttu-id="69278-219">La formule de la date peut comprendre un maximum de 20 caractères, des chiffres et des lettres.</span><span class="sxs-lookup"><span data-stu-id="69278-219">The date formula can contain a maximum of 20 characters, both numbers and letters.</span></span> <span data-ttu-id="69278-220">Vous pouvez utiliser les lettres suivantes qui sont des abréviations d'unités de calendrier.</span><span class="sxs-lookup"><span data-stu-id="69278-220">You can use the following letters, which are abbreviations for calendar units.</span></span>

|  <span data-ttu-id="69278-221">Lettre</span><span class="sxs-lookup"><span data-stu-id="69278-221">Letter</span></span>  |  <span data-ttu-id="69278-222">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-222">Meaning</span></span>  |
|----------|----------------------|
|`C`|<span data-ttu-id="69278-223">Actuellement</span><span class="sxs-lookup"><span data-stu-id="69278-223">Current</span></span>|
|`D`|<span data-ttu-id="69278-224">Jour\(s\)</span><span class="sxs-lookup"><span data-stu-id="69278-224">Day\(s\)</span></span>|
|`W`|<span data-ttu-id="69278-225">Week\(s\) (Semaines)</span><span class="sxs-lookup"><span data-stu-id="69278-225">Week\(s\)</span></span>|
|`M`|<span data-ttu-id="69278-226">Mois</span><span class="sxs-lookup"><span data-stu-id="69278-226">Month\(s\)</span></span>|
|`Q`|<span data-ttu-id="69278-227">Trimestre\(s\)</span><span class="sxs-lookup"><span data-stu-id="69278-227">Quarter\(s\)</span></span>|
|`Y`|<span data-ttu-id="69278-228">Année\(s\)</span><span class="sxs-lookup"><span data-stu-id="69278-228">Year\(s\)</span></span>|

<span data-ttu-id="69278-229">Vous pouvez construire la formule date de trois manières.</span><span class="sxs-lookup"><span data-stu-id="69278-229">You can construct a date formula in three ways.</span></span>

<span data-ttu-id="69278-230">L'exemple suivant indique comment utiliser `C` pour en cours et une unité temporelle.</span><span class="sxs-lookup"><span data-stu-id="69278-230">The following example shows how to use `C`, for current, and a time unit.</span></span>

|  <span data-ttu-id="69278-231">Expression</span><span class="sxs-lookup"><span data-stu-id="69278-231">Expression</span></span>  |  <span data-ttu-id="69278-232">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-232">Meaning</span></span>  |
|--------------|-----------|
|`CW`|<span data-ttu-id="69278-233">Semaine en cours</span><span class="sxs-lookup"><span data-stu-id="69278-233">Current week</span></span>|
|`CM`|<span data-ttu-id="69278-234">Mois en cours</span><span class="sxs-lookup"><span data-stu-id="69278-234">Current month</span></span>|

<span data-ttu-id="69278-235">L'exemple suivant indique comment utiliser un chiffre et une unité de temps.</span><span class="sxs-lookup"><span data-stu-id="69278-235">The following example shows how to use a number and a time unit.</span></span> <span data-ttu-id="69278-236">Un chiffre ne peut pas être supérieur à 9999.</span><span class="sxs-lookup"><span data-stu-id="69278-236">A number cannot be larger than 9999.</span></span>

|  <span data-ttu-id="69278-237">Expression</span><span class="sxs-lookup"><span data-stu-id="69278-237">Expression</span></span>  |  <span data-ttu-id="69278-238">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-238">Meaning</span></span>  |
|--------------|-----------|
|`10D`|<span data-ttu-id="69278-239">10 jours à dater d'aujourd'hui</span><span class="sxs-lookup"><span data-stu-id="69278-239">10 days from today</span></span>|
|`2W`|<span data-ttu-id="69278-240">2 semaines à dater d'aujourd'hui</span><span class="sxs-lookup"><span data-stu-id="69278-240">2 weeks from today</span></span>|

<span data-ttu-id="69278-241">L'exemple suivant indique comment utiliser une unité de temps et un chiffre.</span><span class="sxs-lookup"><span data-stu-id="69278-241">The following example shows how to use a time unit and a number.</span></span>

|  <span data-ttu-id="69278-242">Expression</span><span class="sxs-lookup"><span data-stu-id="69278-242">Expression</span></span>  |  <span data-ttu-id="69278-243">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-243">Meaning</span></span>  |
|--------------|-----------|
|`D10`|<span data-ttu-id="69278-244">Le dixième jour du mois suivant</span><span class="sxs-lookup"><span data-stu-id="69278-244">The next 10th day of a month</span></span>|
|`WD4`|<span data-ttu-id="69278-245">Le quatrième jour de la semaine \(jeudi\)</span><span class="sxs-lookup"><span data-stu-id="69278-245">The next 4th day of a week \(Thursday\)</span></span>|

<span data-ttu-id="69278-246">L'exemple suivant indique comment combiner ces trois formules.</span><span class="sxs-lookup"><span data-stu-id="69278-246">The following example shows how you can combine these three forms as needed.</span></span>

|  <span data-ttu-id="69278-247">Expression</span><span class="sxs-lookup"><span data-stu-id="69278-247">Expression</span></span>  |  <span data-ttu-id="69278-248">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-248">Meaning</span></span>  |
|--------------|-----------|
|`CM+10D`|<span data-ttu-id="69278-249">Mois en cours \+ 10 jours</span><span class="sxs-lookup"><span data-stu-id="69278-249">Current month \+ 10 days</span></span>|

<span data-ttu-id="69278-250">L'exemple ci-dessous illustre comment vous pouvez utiliser le signe moins pour indiquer une date du passé.</span><span class="sxs-lookup"><span data-stu-id="69278-250">The following example shows how you can use a minus sign to indicate a date in the past.</span></span>

|  <span data-ttu-id="69278-251">Expression</span><span class="sxs-lookup"><span data-stu-id="69278-251">Expression</span></span>  |  <span data-ttu-id="69278-252">Signification</span><span class="sxs-lookup"><span data-stu-id="69278-252">Meaning</span></span>  |
|--------------|-----------|
|`-1Y`|<span data-ttu-id="69278-253">Il y a 1 an à dater d'aujourd'hui</span><span class="sxs-lookup"><span data-stu-id="69278-253">1 year ago from today</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="69278-254">Si l'emplacement utilise un calendrier principal, la formule de date que vous entrez, par exemple le champ **Délai de livraison**, est interprétée en fonction des jours ouvrés du calendrier.</span><span class="sxs-lookup"><span data-stu-id="69278-254">If the location uses a base calendar, then the date formula that you enter in, for example, the **Shipping Time** field is interpreted according to the calendar working days.</span></span> <span data-ttu-id="69278-255">Par exemple, `1W` un signifie sept jours ouvrés.</span><span class="sxs-lookup"><span data-stu-id="69278-255">For example, `1W`  means seven working days.</span></span>
<!--
# Entering Date Ranges
You can set filters containing a start date and an end date to display only the data contained in that date range or time interval. Special rules apply to the way you set date ranges. Let's take the **Customer Top 10** as an example:

![Setting a date range in the request page for the Customer Top 10 list](./media/ui-enter-date-ranges/customer-top10-list.png)

Here you can limit the report to a date range such as the past 2 weeks, or a total of 6 weeks, or whatever range you want. To set date ranges, you enter dates and then use either **..** or **|** to set the range. In our example, to show the top 10 customers for the first two weeks of May, you would set the date filter to *05 01 17..05 14 17*.
Here are a couple of other examples:

| Meaning | Example | Entries included |
|---|---|---|
|Equal to| 12 15 16 |Only those posted on December 15 2016.|
|Interval| 12 15 16..01 15 17<br /><br />..12 15 16|Those posted on dates between and including December 15 2016 and January 15 2017.<br /><br />Those posted on December 15 2016 or earlier.|
|Either/or|12 15 16&#124;12 16 16|Those posted on either December 15 or December 16 2016. If there are entries posted on both days, they will all be displayed.|

You can also combine the various format types.

| Example | Entries included |
|---|---|
|12 15 16&#124;12 01 16..05 31 17 | Entries posted either on December 15 2016 or on dates between and including December 01 2016 and May 31 2017. |
|..12 14 16&#124;12 30 16.. | Entries posted on December 14 or earlier, or entries posted on December 30 or later - that is, all entries except those posted on dates between and including December 15 and 29. |

Note that we have used the US date format MMDDYY here. As [!INCLUDE[d365fin](includes/d365fin_md.md)] becomes available in other markets, you'll be able to use the formats that you are used to.

## Using Date Formulas
A date formula is a short, abbreviated combination of letters and numbers that specifies how to calculate dates. You can enter date formulas in various date calculation fields and in recurring frequency fields in recurring journals.

> [!NOTE]
>  In all data formula fields, one day is automatically included to cover today as the day when the period starts. Accordingly, for example, if you enter **1W**, then the period is actually eight days because today is included. To specify a period of seven days (one true week) including the period starting date, then you must enter **6D** or **1W\-1D**.

Here are some examples of how date formulas can be used:

-   The date formula in the recurring frequency field in recurring journals determines how often the entry on the journal line will be posted.

-   The date formula in the **Grace Period** field for a specified reminder level determines the period of time that must pass from the due date (or from the due date of the previous reminder) before a reminder will be created.

-   The date formula in the **Due Date Calculation** field determines how to calculate the due date on the reminder.

The date calculation formula can contain a maximum of 20 characters, both numbers and letters. You can use the following letters, which are abbreviations for time specifications.

|  Letter  |  Time specification  |
|----------|----------------------|
|C|Current|
|D|Day\(s\)|
|W|Week\(s\)|
|M|Month\(s\)|
|Q|Quarter\(s\)|
|Y|Year\(s\)|

You can construct a date formula in three ways.

The following example shows how to use **C**, for current, and a time unit.

|  Expression  |  Meaning  |
|--------------|-----------|
|CW|Current week|
|CM|Current month|

The following example shows how to use a number and a time unit. A number cannot be larger than 9999.

|  Expression  |  Meaning  |
|--------------|-----------|
|10D|10 days from today|
|2W|2 weeks from today|

The following example shows how to use a time unit and a number.

|  Expression  |  Meaning  |
|--------------|-----------|
|D10|The next 10th day of a month|
|WD4|The next 4th day of a week \(Thursday\)|

The following example shows how you can combine these three forms as needed.

|  Expression  |  Meaning  |
|--------------|-----------|
|CM\+10D|Current month \+ 10 days|

The following example shows how you can use a minus sign to indicate a date in the past.

|  Expression  |  Meaning  |
|--------------|-----------|
|-1Y|1 year ago from today|

> [!IMPORTANT]
>  If the location uses a base calendar, then the date formula that you enter in, for example, the **Shipping Time** field is interpreted according to the calendar working days. For example, **1W**  means seven working days.

-->

## <a name="entering-times"></a><span data-ttu-id="69278-256">Saisie des heures</span><span class="sxs-lookup"><span data-stu-id="69278-256">Entering Times</span></span>
<span data-ttu-id="69278-257">Lorsque vous saisissez des heures, vous pouvez insérer n'importe quel type de séparateur entre les unités, mais si vous utilisez des chiffres doubles pour chaque unité jusqu'aux millisecondes, ce n'est pas requis.</span><span class="sxs-lookup"><span data-stu-id="69278-257">When you enter times, you can insert any non-space separators that you want between the units, but if you use double digits for each unit up to milliseconds, then it is not required.</span></span>

<span data-ttu-id="69278-258">Vous n'avez qu'à entrer les plus grandes unités souhaitées ; les autres sont remis à zéro.</span><span class="sxs-lookup"><span data-stu-id="69278-258">You only have to write the largest units that you require; the rest will be set to zero.</span></span> <span data-ttu-id="69278-259">Vous pouvez également omettre l'indicateur AM/PM.</span><span class="sxs-lookup"><span data-stu-id="69278-259">You can also leave out any AM/PM indicator.</span></span>

<span data-ttu-id="69278-260">Le tableau suivant répertorie les différents formats de saisie possibles pour les heures, ainsi que leur interprétation.</span><span class="sxs-lookup"><span data-stu-id="69278-260">The following table lists the various ways in which times can be entered and how they are interpreted.</span></span> <span data-ttu-id="69278-261">Il considère les paramètres de zone qui formatent les périodes : **Heures:Minutes:Secondes.Millisecondes.**</span><span class="sxs-lookup"><span data-stu-id="69278-261">It assumes region settings that format times according to: **Hours:Minutes:Seconds.Milliseconds.**</span></span> <span data-ttu-id="69278-262">et utilisent les indicateurs AM et PM « AM » et « PM », respectivement.</span><span class="sxs-lookup"><span data-stu-id="69278-262">and use the AM and PM indicators of 'AM' and 'PM', respectively.</span></span>

|<span data-ttu-id="69278-263">**Écriture**</span><span class="sxs-lookup"><span data-stu-id="69278-263">**Entry**</span></span>      |<span data-ttu-id="69278-264">**Interprétation**</span><span class="sxs-lookup"><span data-stu-id="69278-264">**Interpretation**</span></span>      |
|---------------|------------------------|
|`05:23:17`|<span data-ttu-id="69278-265">05:23:17</span><span class="sxs-lookup"><span data-stu-id="69278-265">05:23:17</span></span>|
|`5`|<span data-ttu-id="69278-266">05:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-266">05:00:00</span></span>|
|`5AM`|<span data-ttu-id="69278-267">05:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-267">05:00:00</span></span>|
|`5P`|<span data-ttu-id="69278-268">17:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-268">17:00:00</span></span>|
|`12`|<span data-ttu-id="69278-269">12:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-269">12:00:00</span></span>|
|`12A`|<span data-ttu-id="69278-270">00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-270">00:00:00</span></span>|
|`12P`|<span data-ttu-id="69278-271">12:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-271">12:00:00</span></span>|
|`17`|<span data-ttu-id="69278-272">17:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-272">17:00:00</span></span>|
|`5:30`|<span data-ttu-id="69278-273">05:30:00</span><span class="sxs-lookup"><span data-stu-id="69278-273">05:30:00</span></span>|
|`0530`|<span data-ttu-id="69278-274">05:30:00</span><span class="sxs-lookup"><span data-stu-id="69278-274">05:30:00</span></span>|
|`5:30:5`|<span data-ttu-id="69278-275">05:30:05</span><span class="sxs-lookup"><span data-stu-id="69278-275">05:30:05</span></span>|
|`053005`|<span data-ttu-id="69278-276">05:30:05</span><span class="sxs-lookup"><span data-stu-id="69278-276">05:30:05</span></span>|
|`5:30:5,50`|<span data-ttu-id="69278-277">05:30:05,5</span><span class="sxs-lookup"><span data-stu-id="69278-277">05:30:05.5</span></span>|
|`053005050`|<span data-ttu-id="69278-278">05:30:05,05</span><span class="sxs-lookup"><span data-stu-id="69278-278">05:30:05.05</span></span>|

<span data-ttu-id="69278-279">Tenez compte que les millisecondes sont interprétées comme des notation de décimales.</span><span class="sxs-lookup"><span data-stu-id="69278-279">You should be aware that milliseconds are interpreted as decimal notation.</span></span> <span data-ttu-id="69278-280">Ainsi, par exemple `3`, `30`, et `300` tous signifient 300 millisecondes, alors que `03` signifie `30` et `003` signifie 3 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="69278-280">So, for example, `3`, `30`, and `300` all mean 300 milliseconds, while `03` means `30` and `003` means 3 milliseconds.</span></span>

<span data-ttu-id="69278-281">Vous ne pouvez pas utiliser `24:00` pour dire minuit, ou utiliser une valeur supérieure à 24:00.</span><span class="sxs-lookup"><span data-stu-id="69278-281">You cannot use `24:00` to mean midnight, or use any value greater than 24:00.</span></span>

<span data-ttu-id="69278-282">Le mot pour « time » (heure) dans la langue utilisée par [!INCLUDE[d365fin](includes/d365fin_long_md.md)] est évalué sur l'heure actuelle sur votre ordinateur ou appareil mobile.</span><span class="sxs-lookup"><span data-stu-id="69278-282">The word for 'time' in the language used by [!INCLUDE[d365fin](includes/d365fin_long_md.md)] will be evaluated to the current time on your computer or mobile device.</span></span> <span data-ttu-id="69278-283">Vous pouvez saisir n'importe quel partie du mot, en commençant au début, par exemple `t` ou `TIM`.</span><span class="sxs-lookup"><span data-stu-id="69278-283">You can enter any part of the word, starting from the beginning, such as `t` or `TIM`.</span></span>

## <a name="entering-combined-dates-and-times"></a><span data-ttu-id="69278-284">Saisie de dates et d'heures combinées</span><span class="sxs-lookup"><span data-stu-id="69278-284">Entering combined Dates and Times</span></span>
<span data-ttu-id="69278-285">Lorsque vous saisissez les dates/heures, qui sont une date et heure combinées en un champ, vous devez saisir un espace entre la date et l'heure.</span><span class="sxs-lookup"><span data-stu-id="69278-285">When you enter datetimes, which are a date and time combined into one field, you must enter a space between the date and the time.</span></span> <span data-ttu-id="69278-286">La partie de la date ne peut contenir des espaces sous forme de séparateur de date officiel de vos paramètres de région.</span><span class="sxs-lookup"><span data-stu-id="69278-286">The date part can only contain spaces in the form of the official date separator of your region settings.</span></span> <span data-ttu-id="69278-287">L'heure peut contenir des espaces autour de l'indicateur AM/PM.</span><span class="sxs-lookup"><span data-stu-id="69278-287">The time can contain spaces around the AM/PM indicator.</span></span>

<span data-ttu-id="69278-288">Il est également possible de saisir qu'une date dans un champ Date/heure, mais il n'est pas possible d'entrer seulement une heure.</span><span class="sxs-lookup"><span data-stu-id="69278-288">It is also possible to enter only a date in a datetime field, but it is not possible to enter only a time.</span></span>

<span data-ttu-id="69278-289">Le tableau suivant répertorie quelques exemples de combinaisons Date/heure.</span><span class="sxs-lookup"><span data-stu-id="69278-289">The following table lists some examples of date/time combinations.</span></span> <span data-ttu-id="69278-290">Les paramètres de région dans les exemples affichent les dates au format jour\-mois\-année, en utilisant les indicateurs AM/PM, l'anglais, et le dimanche comme début de la semaine.</span><span class="sxs-lookup"><span data-stu-id="69278-290">The region settings in the examples displays dates in the day\-month\-year format, using AM/PM designators, English language, and Sunday as the start of the week.</span></span>

|<span data-ttu-id="69278-291">**Écriture**</span><span class="sxs-lookup"><span data-stu-id="69278-291">**Entry**</span></span>      |<span data-ttu-id="69278-292">**Interprétation**</span><span class="sxs-lookup"><span data-stu-id="69278-292">**Interpretation**</span></span>      |
|---------------|------------------------|
|`08-01-2016 05:48:12 PM`|<span data-ttu-id="69278-293">08\-01\-2016 05:48:12 PM</span><span class="sxs-lookup"><span data-stu-id="69278-293">08\-01\-2016 05:48:12 PM</span></span>|
|`131202 132455`|<span data-ttu-id="69278-294">13\-12\-2002 13:24:55</span><span class="sxs-lookup"><span data-stu-id="69278-294">13\-12\-2002 13:24:55</span></span>|
|`1-12-02 10`|<span data-ttu-id="69278-295">01\-12\-2002 10:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-295">01\-12\-2002 10:00:00</span></span>|
|`1.12.02 5`|<span data-ttu-id="69278-296">01\-12\-2002 05:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-296">01\-12\-2002 05:00:00</span></span>|
|`1.12.02`|<span data-ttu-id="69278-297">01\-12\-2002 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-297">01\-12\-2002 00:00:00</span></span>|
|`11 12`|<span data-ttu-id="69278-298">11\-mois date de travail\-année date de travail 12:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-298">11\-work date month\-work date year 12:00:00</span></span>|
|`1112 12`|<span data-ttu-id="69278-299">11\-12\-année date de travail 12:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-299">11\-12\-work date year 12:00:00</span></span>|
|<span data-ttu-id="69278-300">`t` ou `today`</span><span class="sxs-lookup"><span data-stu-id="69278-300">`t` or `today`</span></span>|<span data-ttu-id="69278-301">date du jour 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-301">today's date 00:00:00</span></span>|
|`t 10:30`|<span data-ttu-id="69278-302">date du jour 10:30:00</span><span class="sxs-lookup"><span data-stu-id="69278-302">today's date 10:30:00</span></span>|
|`t 3:3:3`|<span data-ttu-id="69278-303">date du jour 03:03:03</span><span class="sxs-lookup"><span data-stu-id="69278-303">today's date 03:03:03</span></span>|
|<span data-ttu-id="69278-304">`w` ou `workdate`</span><span class="sxs-lookup"><span data-stu-id="69278-304">`w` or `workdate`</span></span>|<span data-ttu-id="69278-305">date de travail 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-305">the working date 00:00:00</span></span>|
|<span data-ttu-id="69278-306">`m` ou `Monday`</span><span class="sxs-lookup"><span data-stu-id="69278-306">`m` or `Monday`</span></span>|<span data-ttu-id="69278-307">Lundi de la semaine de date de travail 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-307">Monday of the work date week 00:00:00</span></span>|
|<span data-ttu-id="69278-308">`tu` ou `Tuesday`</span><span class="sxs-lookup"><span data-stu-id="69278-308">`tu` or `Tuesday`</span></span>|<span data-ttu-id="69278-309">Mardi de la semaine de date de travail 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-309">Tuesday of the work date week 00:00:00</span></span>|
|<span data-ttu-id="69278-310">`sa` ou `Saturday`</span><span class="sxs-lookup"><span data-stu-id="69278-310">`sa` or `Saturday`</span></span>|<span data-ttu-id="69278-311">Samedi de la semaine de date de travail 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-311">Saturday of the work date week 00:00:00</span></span>|
|<span data-ttu-id="69278-312">`s` ou `Sunday`</span><span class="sxs-lookup"><span data-stu-id="69278-312">`s` or `Sunday`</span></span>|<span data-ttu-id="69278-313">Dimanche de la semaine de date de travail 00:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-313">Sunday of the work date week 00:00:00</span></span>|
|`tu 10:30`|<span data-ttu-id="69278-314">Mardi de la semaine de date de travail 10:30:00</span><span class="sxs-lookup"><span data-stu-id="69278-314">Tuesday of the work date week 10:30:00</span></span>|
|`tu 3:3:3`|<span data-ttu-id="69278-315">Mardi de la semaine de date de travail 03:03:03</span><span class="sxs-lookup"><span data-stu-id="69278-315">Tuesday of the work date week 03:03:03</span></span>|
|`t23 t`|<span data-ttu-id="69278-316">Mardi de la semaine 23 de l'année de date de travail, heure actuelle</span><span class="sxs-lookup"><span data-stu-id="69278-316">Tuesday of week 23 of the work date year, current time of day</span></span>|
|`t23`|<span data-ttu-id="69278-317">Mardi de la semaine 23 de l'année de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-317">Tuesday of week 23 of the work date year</span></span>|
|`t 23`|<span data-ttu-id="69278-318">Aujourd'hui 23:00:00</span><span class="sxs-lookup"><span data-stu-id="69278-318">Today 23:00:00</span></span>|
|`t-1`|<span data-ttu-id="69278-319">Mardi de la semaine 1 de l'année de date de travail</span><span class="sxs-lookup"><span data-stu-id="69278-319">Tuesday of week 1 of the work date year</span></span>|

## <a name="entering-duration"></a><span data-ttu-id="69278-320">Saisie des durées</span><span class="sxs-lookup"><span data-stu-id="69278-320">Entering Duration</span></span>
<span data-ttu-id="69278-321">Certains champs de l'application représentent une durée, ou la quantité de temps écoulé, au lieu d'une date ou d'une heure spécifique.</span><span class="sxs-lookup"><span data-stu-id="69278-321">Some fields in the application represent a duration, or amount of elapsed time, instead of a specific date or time.</span></span> <span data-ttu-id="69278-322">Vous entrez une durée sous la forme d'un nombre suivi d'une unité de mesure.</span><span class="sxs-lookup"><span data-stu-id="69278-322">You enter a duration as a number followed by its unit of measure.</span></span>

<span data-ttu-id="69278-323">Voilà quelques exemples.</span><span class="sxs-lookup"><span data-stu-id="69278-323">Here are some examples.</span></span>

|<span data-ttu-id="69278-324">**Durée**</span><span class="sxs-lookup"><span data-stu-id="69278-324">**Duration**</span></span>|<span data-ttu-id="69278-325">**Unité de mesure**</span><span class="sxs-lookup"><span data-stu-id="69278-325">**Unit of measure**</span></span>|
|------------|-------------------|
|`2h`|<span data-ttu-id="69278-326">2 heures</span><span class="sxs-lookup"><span data-stu-id="69278-326">2 hrs</span></span>|
|`6h 30 m`|<span data-ttu-id="69278-327">6 heures 30 minutes</span><span class="sxs-lookup"><span data-stu-id="69278-327">6 hrs 30 mins</span></span>|
|`6.5h`|<span data-ttu-id="69278-328">6 heures 30 minutes</span><span class="sxs-lookup"><span data-stu-id="69278-328">6 hrs 30 mins</span></span>|
|`90m`|<span data-ttu-id="69278-329">1 heure 30 minutes</span><span class="sxs-lookup"><span data-stu-id="69278-329">1 hr 30 mins</span></span>|
|`2d 6h 30m`|<span data-ttu-id="69278-330">2 jours 6 heures 30 minutes</span><span class="sxs-lookup"><span data-stu-id="69278-330">2 days 6 hrs 30 mins</span></span>|
|`2d 6h 30m 56s 600ms`|<span data-ttu-id="69278-331">2 jours 6 h 30 m 56 s 600 ms</span><span class="sxs-lookup"><span data-stu-id="69278-331">2 days 6 hrs 30 mins 56 secs 600 msecs</span></span>|

<span data-ttu-id="69278-332">Vous pouvez également saisir un nombre automatiquement converti en durée.</span><span class="sxs-lookup"><span data-stu-id="69278-332">You can also enter a number, which will be automatically converted to a duration.</span></span> <span data-ttu-id="69278-333">Le nombre saisi est converti en fonction de l'unité de mesure par défaut spécifiée pour le champ de durée.</span><span class="sxs-lookup"><span data-stu-id="69278-333">The number you enter is converted according to the default unit of measure that has been specified for the duration field.</span></span>

<span data-ttu-id="69278-334">Pour connaître l'unité de mesure utilisée pour un champ de durée, entrez un nombre et observez l'unité de mesure dans laquelle il est converti.</span><span class="sxs-lookup"><span data-stu-id="69278-334">To see what unit of measure is being used in a duration field, enter a number and see which unit of measure it is converted to.</span></span>

<span data-ttu-id="69278-335">Par exemple, si l'unité de mesure est « heures », le chiffre `5` est converti en 5 h.</span><span class="sxs-lookup"><span data-stu-id="69278-335">For example, if the unit of measure is hours, the number `5` is converted to 5 hrs.</span></span>


## <a name="see-also"></a><span data-ttu-id="69278-336">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="69278-336">See Also</span></span>
<span data-ttu-id="69278-337">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="69278-337">[Working with [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="69278-338">Calcul de la date des achats</span><span class="sxs-lookup"><span data-stu-id="69278-338">Date Calculation for Purchases</span></span>](purchasing-date-calculation-for-purchases.md)  
[<span data-ttu-id="69278-339">Saisir les critères pour les filtres</span><span class="sxs-lookup"><span data-stu-id="69278-339">Entering Criteria in Filters </span></span>](ui-enter-criteria-filters.md)  

