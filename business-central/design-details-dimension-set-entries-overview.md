---
title: Aperçu des écritures de l'ensemble de dimensions | Microsoft Docs
description: Cette rubrique décrit comment les écritures de l'ensemble de dimensions sont stockées et reportées dans Dynamics 365.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: dimension
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 8ed544486af6949932814bf97d99293f1ef17ee2
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2303590"
---
# <a name="dimension-set-entries-overview"></a>Aperçu des écritures de l'ensemble de dimensions
Cette rubrique décrit comment les écritures de l'ensemble de dimensions sont stockées et validées dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="dimension-sets"></a>Ensembles de dimensions  
Un ensemble de dimensions est une combinaison unique de sections analytiques. Il est stocké comme des écritures de l'ensemble de dimensions dans la base de données. Chaque écriture de l'ensemble de dimensions représente une valeur de dimension unique. L'ensemble de dimensions est identifié par un code commun, qui est affecté à chaque écriture correspondante qui appartient à l'ensemble de dimensions.  

L'exemple suivant présente un ensemble de dimensions constitué de trois écritures. L'ensemble de dimensions est identifié par le code 108.  

|Code ensemble de dimensions|Code de dimension|Code de valeur de dimension|Nom de la valeur de dimension|  
|----------------------|--------------------|--------------------------|--------------------------|  
|108|REGION|70|Amérique du Nord|  
|108|GROUPE COMPTABILISATION MARCHÉ|DÉBUT|Accueil|  
|108|DEPARTEMENT|VENTES|Vente|  

## <a name="dimension-set-entries"></a>Écritures de l'ensemble de dimensions  
Les ensembles de dimensions sont stockés dans la table **Écriture de l'ensemble de dimensions** telles des écritures de l'ensemble de dimensions avec le même ID.  

![Flux d'écritures d'ensemble de dimensions](media/dimensionentrynav7.png "Flux d'écritures d'ensemble de dimensions")  

Lorsque vous créez une ligne de journal, un en-tête de document ou une ligne de document, vous pouvez spécifier une combinaison de valeurs de dimension. Au lieu d'enregistrer explicitement chaque valeur de dimension dans la base de données, un code d'ensemble de dimensions est affecté à la ligne de journal, à l'en-tête du document ou à la ligne du document pour spécifier l'ensemble de dimensions.  

Lorsque vous modifiez et fermez la page **Modifier les écritures de l'ensemble de dimensions**, une vérification est exécutée pour voir si la combinaison de valeurs de dimension existe comme un ensemble de dimensions dans la table. Si la combinaison se produit dans la table, le code d'ensemble de dimensions correspondant est affecté à la ligne journal, à l'en-tête document ou à la ligne document. Sinon, un nouvel ensemble de dimensions est ajouté à la table, et le nouveau code d'ensemble de dimensions est affecté à la ligne journal, à l'en-tête document ou à la ligne document.

## <a name="codeunit-408-dimension-management"></a>Codeunit 408 Gestion des dimensions
Codeunit 408 Gestion des dimensions est une bibliothèque de fonctions qui gère les tâches courantes qui sont liées aux dimensions, telles que copier d'une table à une autre ou d'un document à un autre.

## <a name="performance-improvement"></a>Amélioration des performances  
En enregistrant les ensembles de dimensions dans la base de données, l'espace de la base de données est conservé et les performances globales sont améliorées.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : recherche des combinaisons de dimensions](design-details-searching-for-dimension-combinations.md)   
[Détails de conception : structure de la table](design-details-table-structure.md)   
[Détails de conception : écritures d'ensemble de dimensions](design-details-dimension-set-entries.md)   
