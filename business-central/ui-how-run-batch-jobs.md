---
title: Créer et exécuter un traitement en lot | Microsoft Docs
description: Vous exécutez des traitements en lot pour traiter les données et mettre à jour les informations, par exemple, pour élaborer des activités de comptabilité périodiques ou effectuer des calculs.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process
ms.date: 10/01/2019
ms.author: solsen
ms.openlocfilehash: 2387356fd3e80e5020b4d2e4857280dd4b99788a
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2315214"
---
# <a name="run-batch-jobs-and-xmlports"></a>Exécuter des traitements en lot et des objets XMLport
Un traitement par lots est une routine qui traite les données par lots, par exemple le traitement par lots **Ajuster taux de change**. Il existe des traitements en lot qui exécutent des activités de comptabilité périodiques, comme la fermeture de l'état des résultats à la fin d'un exercice financier. De nombreux traitements en lot exécutent des calculs, tels que le calcul des frais financiers, l'ajustement du taux de change et le calcul des prix unitaires.

Un traitement en lot est similaire à un rapport, sauf qu'il utilise les résultats obtenus pour mettre à jour les informations directement plutôt que d'imprimer les résultats.

Vous pouvez programmer l'exécution d'un traitement en lot. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## <a name="to-run-a-batch-job"></a>Pour exécuter un traitement en lot
1. Pour ouvrir la page de demande du traitement en lot approprié, choisissez l'icone ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez le nom du traitement en lot, puis sélectionnez le lien associé.
2. Si un raccourci **Options** est disponible pour le traitement par lots, renseignez-en les champs pour déterminer les tâches effectuées par le traitement par lots.
3. La page peut inclure un ou plusieurs raccourcis avec des filtres que vous pouvez utiliser pour limiter les données incluses dans le traitement en lot. Pour cela, entrez des critères dans les filtres suggérés ou ajoutez des filtres supplémentaires.
4. Pour démarrer le traitement en lot, cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi
[Tri, recherche et filtrage de listes](ui-enter-criteria-filters.md)  
[Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
