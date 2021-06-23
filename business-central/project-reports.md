---
title: Rapports et analyses de projet
description: Découvrez les rapports et analyses de projet disponibles dans la version standard de Business Central afin que vous puissiez suivre votre activité.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 06/01/2021
ms.author: andreipa
ms.openlocfilehash: ff5294df5cdbeaf0054249f017906bfd60ee4bf7
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6216435"
---
# <a name="project-reports-and-analytics-in-business-central"></a>Rapports et analyses de projet dans Business Central

Les rapports de projet dans [!INCLUDE [prod_short](includes/prod_short.md)] permettent aux professionnels des projets et des affaires d’obtenir des informations et des statistiques sur les activités de projet actuelles et passées.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports de projet.

|Rapport |Code objet|Description  |
|---------|---------|---------|
|**Analyse de projet**|1008|Analyse votre projet à l’aide des paramètres que vous spécifiez. Par exemple, vous pouvez créer un rapport avec les prix budgétés, les prix utilisation et les prix facturables, et comparer ainsi les trois types de prix.<br>Permet d’utiliser une combinaison des champs **Montant** disponibles pour créer une analyse personnalisée. Pour chaque champ, sélectionnez l’un des prix, coûts ou profit suivants : Calendrier, Utilisation, Contrat et Facturé. <br>Permet de choisir l’affichage de la devise : devise locale ou devise étrangère. |
|**Lignes planification projet**|1006|Ce rapport affiche les différentes lignes planification projet et tâche projet, y compris le type de ligne, les quantités, l’unité de mesure, les coûts totaux, etc.|
|**Projet Comp. réal./Budget**|1009|Compare les montants d’utilisation et programmés des projets sélectionnés. Toutes les lignes du projet sélectionné indiquent la quantité, le coût total et le montant ligne. <br>Ce rapport est prévu pour les projets terminés, mais vous pouvez l’utiliser à tout moment.<br>Ce rapport n’est pas disponible aux États-Unis, au Canada et au Mexique. Utilisez plutôt les rapports **Comparaison Coût réel projet/Coût budgété** (10210) ou **Comparaison Prix réel projet/Prix budgété** (10211).|
|**Prop. de facturation projet**|1011|Affiche la liste de tous les projets groupés par client, en indiquant le montant déjà facturé au client et le montant restant à facturer, c’est-à-dire la proposition de facturation. <br>Ce rapport n’est pas disponible aux États-Unis, au Canada et au Mexique. Utilisez plutôt le rapport **Prop. de facturation coût projet** (10219).|
|**Projets par client**|1012|Affiche la liste de tous les projets groupés par client. Il permet de comparer le prix programmé, le pourcentage d’achèvement, le prix facturé et le pourcentage de facturation pour chaque **Client facturé**.|
|**Articles par projet** ou **Projets par article**|1013 ou 1014|Aperçu des articles utilisés dans un projet. En fonction du rapport que vous souhaitez utiliser pour obtenir un aperçu des articles planifiés pour un projet, vous pouvez définir un filtre supplémentaire. Le rapport affiche les articles pertinents et une valeur cumulée des coûts.|
|**Détail transactions projet**|1007|Ce rapport vous donnera un aperçu des tâches de projets reportées, telles que les ressources et les articles. Comprend des informations détaillées sur les coûts totaux et les prix totaux ainsi qu’une information concernant les escomptes ligne, etc. Le rapport affiche les données des écritures projet.|
|**Projet TEC au GL**|1010|Affiche la valeur des travaux en cours des projets sélectionnés comparée au montant reporté dans le grand livre.|




## <a name="tasks"></a>Tâches

Les articles suivants décrivent certaines des tâches clés pour analyser l’état de votre entreprise :

* [Surveiller la progression et les performances](projects-how-monitor-progress-performance.md)  


## <a name="see-also"></a>Voir aussi

[Configuration de la gestion de projet](projects-setup-projects.md)  
[Gestion de projets](projects-manage-projects.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
