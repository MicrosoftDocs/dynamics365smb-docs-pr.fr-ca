---
title: "Créer une fiche projet pour un projet et spécifier des tâches| Microsoft Docs"
description: "Pour un nouveau projet, vous créez une fiche projet qui contient les tâches projet et les lignes planification, pour vous aider à gérer la progression et les budgets."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, task
ms.date: 01/25/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: ece0a95f83868ac2657fdf41330e7d0a9cce37d6
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-jobs"></a>Créer des projets
Lorsque vous démarrez un nouveau projet, vous devez créer une fiche projet avec des tâches intégrées et des lignes planification structurées en deux couches.  

La première couche inclut les tâches du projet. Vous devez créer au moins une tâche par projet car tous les reports font référence à une tâche de projet. Cela permet de configurer les lignes planification projet et de reporter la consommation dans le projet.

La seconde couche inclut les lignes planification projet, qui spécifient l'utilisation détaillée des ressources, articles et diverses dépenses du grand livre.

La structure de couche permet de séparer le projet en tâches plus petites et ainsi d'utiliser des détails plus spécifiques dans l'établissement du budget, les devis et l'enregistrement. En outre, elle vous donne un aperçu de la progression d'un projet. Par exemple, vous pouvez rechercher si vous respectez les étapes importantes fixées ou si vous êtes en passe de satisfaire les attentes budgétaires.

> [!NOTE]  
>   L'action **Nouveau projet** du tableau de bord **Chef de projet** lance une configuration assistée qui vous guide dans les étapes de création d'un projet avec des tâches intégrées et des lignes planning. La procédure suivante décrit comment exécuter les étapes manuellement.

## <a name="to-create-a-job-card"></a>Pour créer une fiche projet
Vous devez créer une fiche projet, puis créer des Lignes tâche projet et des lignes planification projet pour ce projet.

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Projets**, puis choisissez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour spécifier le projet avec les informations d'autres projets, cliquez sur **Copier projet**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

> [!NOTE]  
>   Si vous utilisez des feuilles de temps dans le projet, vous devez également indiquer une personne responsable. Cette personne peut approuver les feuilles de temps pour les tâches des employés associées à ce projet. Pour plus d'informations, voir [Paramétrer des feuilles de temps](projects-how-setup-time-sheets.md).

## <a name="to-create-tasks-for-a-job"></a>Pour créer une tâche pour un projet
L'une des clés de la création d'un projet consiste à spécifier les différentes tâches impliquées dans le projet. Pour ce faire, ajoutez de nouvelles lignes dans le raccourci **Tâches** de la fenêtre **Fiche projet**, une tâche par ligne. Chaque projet doit avoir au minimum une tâche.

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Projets**, puis choisissez le lien associé.
2. Ouvrez la fiche projet pour un projet concerné.
3. Sur le raccourci **Tâches**, renseignez les champs, le cas échéant sur une ligne.
4. Pour indenter des tâches et créer une hiérarchie, cliquez sur **Tâches**, puis sur **Indenter tâches projet**.
5. Répétez les étapes 3 et 4 pour toutes les tâches dont vous avez besoin pour le projet.
6. Pour spécifier les tâches du projet avec les informations d'autres tâches de projet, cliquez sur **Copier les tâches projet de**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

## <a name="to-create-planning-lines-for-a-job"></a>Pour créer des lignes planification pour un projet
Vous pouvez redéfinir vos nouvelles tâches projet sur les lignes planification projet. Une ligne planification peut être utilisée pour extraire toute information que vous souhaitez suivre pour un projet. Vous pouvez utiliser des lignes planification pour ajouter des informations telles que les ressources nécessaires ou pour capturer les articles nécessaires pour exécuter le projet. Par exemple, si vous avez une tâche pour obtenir l'accord d'un client sur un projet, vous pouvez associer cette tâche à des lignes planification article, comme un rendez-vous avec le client ou l'affectation d'une ressource.  

Une ligne planification projet peut avoir l'un des types suivants :  

| Type | Description |
| --- | --- |
| **Budget** |Permet d'obtenir les utilisations et coûts prévus pour le projet, généralement dans le cadre d'un projet de régie. Les lignes planification de ce type ne peuvent pas être facturées. |
| **Facturable** |Permet de fournir un devis au client, généralement utilisé dans le cadre d'un projet à prix fixe. |
| **Budget et Facturable** |Permet de faire correspondre l'utilisation budgétée au montant que vous souhaitez facturer. |

**Remarque**. Au fur et à mesure de l'ajout d'informations sur les lignes planification projet, le coût est automatiquement mis à jour. Par exemple, le coût, le prix et l'escompte relatifs aux ressources et aux articles sont initialement calculés sur la base des informations définies dans les fiches ressource et article.

1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Projets**, puis choisissez le lien associé.
2. Ouvrez la fiche projet appropriée.
3. Sélectionnez une tâche projet pour laquelle le champ **Type tâche projet** contient **Validation** puis, cliquez sur **Lignes planning projet**.  
4. Dans la fenêtre **Lignes planning projet**, renseignez les champs, le cas échéant sur une nouvelle ligne.
5. Répétez les phases 3 et 4 pour toutes les lignes planification dont vous avez besoin pour la tâche projet.

## <a name="see-also"></a>Voir aussi
[Gestion de projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Achats](purchasing-manage-purchasing.md)         
[Ventes](sales-manage-sales.md)      
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

