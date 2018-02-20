---
title: "Créer et exécuter un traitement en lot | Microsoft Docs"
description: "Vous exécutez des traitements en lot pour traiter les données et mettre à jour les informations, par exemple, pour élaborer des activités de comptabilité périodiques ou effectuer des calculs."
services: project-madeira
documentationcenter: 
author: SusanneWindfeldPedersen
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process
ms.date: 03/29/2017
ms.author: solsen
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 8478a983da5020a4a7a49f6212c45a7a4c4d21a3
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="run-batch-jobs"></a><span data-ttu-id="3c9fe-103">Exécuter des traitements en lot</span><span class="sxs-lookup"><span data-stu-id="3c9fe-103">Run Batch Jobs</span></span>
<span data-ttu-id="3c9fe-104">Un traitement par lots est une routine qui traite les données par lots, par exemple le traitement par lots **Ajuster taux de change**.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-104">A batch job is a routine that processes data in batches, for example the **Adjust Exchange Rates** batch job.</span></span> <span data-ttu-id="3c9fe-105">Il existe des traitements en lot qui exécutent des activités de comptabilité périodiques, comme la fermeture de l'état des résultats à la fin d'un exercice financier.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-105">There are batch jobs that perform periodic accounting activities, such as closing the income statement at the end of a fiscal year.</span></span> <span data-ttu-id="3c9fe-106">De nombreux traitements en lot exécutent des calculs, tels que le calcul des frais financiers, l'ajustement du taux de change et le calcul des prix unitaires.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-106">Many batch jobs do calculation work, such as calculation of finance charges, exchange rate adjustment, and calculation of unit prices.</span></span>

<span data-ttu-id="3c9fe-107">Un traitement en lot est similaire à un rapport, sauf qu'il utilise les résultats obtenus pour mettre à jour les informations directement plutôt que d'imprimer les résultats.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-107">A batch job is like a report, except the batch job uses the result of its work to update information directly, instead of printing the results.</span></span>

## <a name="to-run-a-batch-job"></a><span data-ttu-id="3c9fe-108">Pour exécuter un traitement en lot</span><span class="sxs-lookup"><span data-stu-id="3c9fe-108">To run a batch job</span></span>
1. <span data-ttu-id="3c9fe-109">Pour ouvrir le formulaire de sélection du traitement par lots concerné, sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez le nom du traitement par lots, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-109">To open the request window for the relevant batch job, choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter the name of the batch job, and then choose the related link.</span></span>
2. <span data-ttu-id="3c9fe-110">Si un raccourci **Options** est disponible pour le traitement par lots, renseignez-en les champs pour déterminer les tâches effectuées par le traitement par lots.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-110">If there is an **Options** FastTab for the batch job, fill in the fields to determine what the batch job will do.</span></span>
3. <span data-ttu-id="3c9fe-111">La fenêtre peut inclure un ou plusieurs raccourcis avec des filtres que vous pouvez utiliser pour limiter les données incluses dans le traitement en lot.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-111">The window may contain one or more FastTab with filters, which you can use to limit the data included in the batch job.</span></span> <span data-ttu-id="3c9fe-112">Pour cela, entrez des critères dans les filtres suggérés ou ajoutez des filtres supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-112">You can enter criteria in the suggested filters or add more filters.</span></span>
4. <span data-ttu-id="3c9fe-113">Pour démarrer le traitement par lots, cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="3c9fe-113">Choose the **OK** button to start the batch job.</span></span>

## <a name="see-also"></a><span data-ttu-id="3c9fe-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="3c9fe-114">See Also</span></span>
[<span data-ttu-id="3c9fe-115">Saisir les critères pour les filtres</span><span class="sxs-lookup"><span data-stu-id="3c9fe-115">Entering Criteria in Filters</span></span>](ui-enter-criteria-filters.md)  
<span data-ttu-id="3c9fe-116">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="3c9fe-116">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>

