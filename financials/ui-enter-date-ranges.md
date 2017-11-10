---
title: "Définition des plages de dates dans Dynamics 365 for Financials | Microsoft Docs"
description: "En savoir plus pour obtenir un rapport affichant les données de périodes spécifiques à l'aide de plages de dates dans Dynamics 365 for Financials."
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: dates, reporting, filter
ms.date: 05/29/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: dc7cd392843ce7c39200bb2331c09cc44c7a394a
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="entering-date-ranges-in-dynamics-365-for-financials"></a><span data-ttu-id="32fa5-103">Saisie de plages de dates dans Dynamics 365 for Financials</span><span class="sxs-lookup"><span data-stu-id="32fa5-103">Entering Date Ranges in Dynamics 365 for Financials</span></span>
<span data-ttu-id="32fa5-104">Vous pouvez définir des filtres contenant une date de début et une date de fin pour afficher uniquement les données contenues dans cette plage de données ou cet intervalle de temps.</span><span class="sxs-lookup"><span data-stu-id="32fa5-104">You can set filters containing a start date and an end date to display only the data contained in that date range or time interval.</span></span> <span data-ttu-id="32fa5-105">Des règles spéciales s'appliquent à la définition des plages de dates.</span><span class="sxs-lookup"><span data-stu-id="32fa5-105">Special rules apply to the way you set date ranges.</span></span> <span data-ttu-id="32fa5-106">Prenons par exemple **Palmarès des clients** :</span><span class="sxs-lookup"><span data-stu-id="32fa5-106">Let's take the **Customer Top 10** as an example:</span></span>

![Définition d'une plage de dates dans la page de demande de la liste du palmarès des clients](./media/ui-enter-date-ranges/customer-top10-list.png)

<span data-ttu-id="32fa5-108">Vous pouvez limiter ici le rapport à une plage de dates telles que les 2 dernières semaines, ou un total de 6 semaines, ou toute plage de votre choix.</span><span class="sxs-lookup"><span data-stu-id="32fa5-108">Here you can limit the report to a date range such as the past 2 weeks, or a total of 6 weeks, or whatever range you want.</span></span> <span data-ttu-id="32fa5-109">Pour définir les plages de dates, vous entrez des dates puis utilisez **..**</span><span class="sxs-lookup"><span data-stu-id="32fa5-109">To set date ranges, you enter dates and then use either **..**</span></span> <span data-ttu-id="32fa5-110">ou **|** pour définir la plage.</span><span class="sxs-lookup"><span data-stu-id="32fa5-110">or **|** to set the range.</span></span> <span data-ttu-id="32fa5-111">Dans notre exemple, pour afficher les 10 clients principaux des deux premières semaines de mai, vous devez définir le filtre de date sur *05 01 17..05 14 17*.</span><span class="sxs-lookup"><span data-stu-id="32fa5-111">In our example, to show the top 10 customers for the first two weeks of May, you would set the date filter to *05 01 17..05 14 17*.</span></span>
<span data-ttu-id="32fa5-112">Voici d'autres exemples :</span><span class="sxs-lookup"><span data-stu-id="32fa5-112">Here are a couple of other examples:</span></span>

| <span data-ttu-id="32fa5-113">Signification</span><span class="sxs-lookup"><span data-stu-id="32fa5-113">Meaning</span></span> | <span data-ttu-id="32fa5-114">Exemple :</span><span class="sxs-lookup"><span data-stu-id="32fa5-114">Example</span></span> | <span data-ttu-id="32fa5-115">Ecritures incluses</span><span class="sxs-lookup"><span data-stu-id="32fa5-115">Entries included</span></span> |
|---|---|---|
|<span data-ttu-id="32fa5-116">Egal à</span><span class="sxs-lookup"><span data-stu-id="32fa5-116">Equal to</span></span>| <span data-ttu-id="32fa5-117">15 12 16</span><span class="sxs-lookup"><span data-stu-id="32fa5-117">12 15 16</span></span> |<span data-ttu-id="32fa5-118">Uniquement les écritures reportées le 15 décembre 2016.</span><span class="sxs-lookup"><span data-stu-id="32fa5-118">Only those posted on December 15 2016.</span></span>|
|<span data-ttu-id="32fa5-119">Intervalle</span><span class="sxs-lookup"><span data-stu-id="32fa5-119">Interval</span></span>| <span data-ttu-id="32fa5-120">15 12 16..15 17 17</span><span class="sxs-lookup"><span data-stu-id="32fa5-120">12 15 16..01 15 17</span></span><br /><br /><span data-ttu-id="32fa5-121">..12 15 16</span><span class="sxs-lookup"><span data-stu-id="32fa5-121">..12 15 16</span></span>|<span data-ttu-id="32fa5-122">Écritures reportées du 15 décembre 2016 au 15 janvier 2017 inclus.</span><span class="sxs-lookup"><span data-stu-id="32fa5-122">Those posted on dates between and including December 15 2016 and January 15 2017.</span></span><br /><br /><span data-ttu-id="32fa5-123">Écritures reportées le 15 décembre 2016 ou à une date antérieure.</span><span class="sxs-lookup"><span data-stu-id="32fa5-123">Those posted on December 15 2016 or earlier.</span></span>|
|<span data-ttu-id="32fa5-124">Et/ou</span><span class="sxs-lookup"><span data-stu-id="32fa5-124">Either/or</span></span>|<span data-ttu-id="32fa5-125">12 15 16&#124;12 16 16</span><span class="sxs-lookup"><span data-stu-id="32fa5-125">12 15 16&#124;12 16 16</span></span>|<span data-ttu-id="32fa5-126">Écritures reportées le 15 ou le 16 décembre 2016.</span><span class="sxs-lookup"><span data-stu-id="32fa5-126">Those posted on either December 15 or December 16 2016.</span></span> <span data-ttu-id="32fa5-127">Les écritures reportées aux deux dates sont également affichées.</span><span class="sxs-lookup"><span data-stu-id="32fa5-127">If there are entries posted on both days, they will all be displayed.</span></span>|

<span data-ttu-id="32fa5-128">Vous pouvez aussi combiner les divers types de format.</span><span class="sxs-lookup"><span data-stu-id="32fa5-128">You can also combine the various format types.</span></span>

| <span data-ttu-id="32fa5-129">Exemple :</span><span class="sxs-lookup"><span data-stu-id="32fa5-129">Example</span></span> | <span data-ttu-id="32fa5-130">Ecritures incluses</span><span class="sxs-lookup"><span data-stu-id="32fa5-130">Entries included</span></span> |
|---|---|
|<span data-ttu-id="32fa5-131">12 15 16&#124;12 01 16..05 31 17</span><span class="sxs-lookup"><span data-stu-id="32fa5-131">12 15 16&#124;12 01 16..05 31 17</span></span> | <span data-ttu-id="32fa5-132">Écritures reportées le 15 décembre 2016 ou à des dates situées entre le 1er décembre 2016 et le 31 mai 2017 inclus.</span><span class="sxs-lookup"><span data-stu-id="32fa5-132">Entries posted either on December 15 2016 or on dates between and including December 01 2016 and May 31 2017.</span></span> |
|<span data-ttu-id="32fa5-133">..12 14 16&#124;12 30 16..</span><span class="sxs-lookup"><span data-stu-id="32fa5-133">..12 14 16&#124;12 30 16..</span></span> | <span data-ttu-id="32fa5-134">Les écritures reportées le 14 décembre ou avant, ou écritures reportées le 30 décembre ou après, c.-à-d. toutes les écritures à l'exception de celles reportées à des dates situées entre le 15 et le 29 décembre.</span><span class="sxs-lookup"><span data-stu-id="32fa5-134">Entries posted on December 14 or earlier, or entries posted on December 30 or later - that is, all entries except those posted on dates between and including December 15 and 29.</span></span> |

<span data-ttu-id="32fa5-135">Remarquez que nous avons utilisé le format de date américaine MMJJAA.</span><span class="sxs-lookup"><span data-stu-id="32fa5-135">Note that we have used the US date format MMDDYY here.</span></span> <span data-ttu-id="32fa5-136">A mesure que [!INCLUDE[d365fin](includes/d365fin_md.md)] deviendra disponible sur d'autres marché, vous pourrez utiliser les formats auxquels vous êtes habitué.</span><span class="sxs-lookup"><span data-stu-id="32fa5-136">As [!INCLUDE[d365fin](includes/d365fin_md.md)] becomes available in other markets, you'll be able to use the formats that you are used to.</span></span>

## <a name="see-also"></a><span data-ttu-id="32fa5-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32fa5-137">See Also</span></span>
<span data-ttu-id="32fa5-138">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="32fa5-138">[Working with [!INCLUDE[d365fin](includes/d365fin_long_md.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="32fa5-139">Saisir les critères pour les filtres</span><span class="sxs-lookup"><span data-stu-id="32fa5-139">Entering Criteria in Filters </span></span>](ui-enter-criteria-filters.md)  
[<span data-ttu-id="32fa5-140">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="32fa5-140">General Business Functionality</span></span>](ui-across-business-areas.md)
