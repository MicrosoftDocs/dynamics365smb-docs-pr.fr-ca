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
ms.date: 10/01/2020
ms.author: jswymer
ms.openlocfilehash: 6c818940357ed21a994e7553517989a0c16accec
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5379283"
---
# <a name="creating-power-bi-reports-for-displaying-list-data-in-prod_short"></a>Création de rapports Power BI pour afficher les données de liste dans [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[prod_long](includes/prod_long.md)] inclut un élément de contrôle Récapitulatif sur un certain nombre de pages Liste des clés fournissant des informations supplémentaires sur les données de la liste. Lorsque vous vous déplacez entre les lignes de la liste, le rapport est mis à jour et filtré pour l'écriture sélectionnée. Vous pouvez créer des rapports personnalisés à afficher dans ce contrôle. Cependant, il y a quelques règles à suivre pour s’assurer que les rapports fonctionnent comme prévu.  

## <a name="prerequisites"></a>Conditions préalables

- Un compte Power BI.
- Power BI Desktop.

Pour plus d’informations sur la mise en route, voir [Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md).

## <a name="defining-the-report-data-set"></a>Définition de l’ensemble de données de rapport

Spécifiez la source de données qui contient les données liées à la liste. Par exemple, pour créer un rapport pour la liste Ventes, assurez-vous que l’ensemble des données contient les informations liées aux ventes.  

## <a name="defining-the-report-filter"></a>Définition du filtre de rapport

Pour mettre à jour les données de l’enregistrement sélectionné dans la liste, vous ajoutez un filtre au rapport. Le filtre doit inclure un champ de la source de données utilisée comme *clé primaire*. Dans la plupart des cas, la clé primaire de la liste est **N°** .

Pour définir un filtre pour l'état, sélectionnez la clé primaire dans la liste des champs disponibles, puis faites glisser ce champ dans la section **Filtre d'état**. Le filtre doit être un filtre de rapport de base défini pour toutes les pages. Il ne peut pas s’agir d’un filtre de page, visuel ou avancé.

![Définition du filtre de rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-filter-v3.png)

## <a name="setting-the-report-size-and-color"></a>Définition de la taille et de la couleur du rapport

La taille du rapport doit être configurée sur 325 pixels par 310 pixels. Cette taille offre une mise à l’échelle appropriée du rapport dans l’espace disponible du contrôle Récapitulatif Power BI dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour définir la taille du rapport, placez le focus en dehors de la zone de présentation de rapport, puis choisissez l'icône en forme de rouleau de peinture.

![Définition de la largeur et de la hauteur du rapport pour le rapport Activités Facture vente](./media/across-how-use-powerbi-reports-factbox/financials-powerbi-report-sizing-v3.png)

Vous pouvez modifier la largeur et la hauteur de l'état en choisissant **Personnalisé** dans le champ **Type**.

Si vous souhaitez que l’arrière-plan du rapport se fonde avec la couleur de l’arrière-plan du contrôle Récapitulatif Power BI, définissez une couleur d’arrière-plan de rapport personnalisé de *#FFFFFF*. 

## <a name="using-reports-with-multiple-pages"></a>Utilisation des rapports avec plusieurs pages

Avec Power BI, vous pouvez créer un seul rapport avec plusieurs pages. Cependant, pour les rapports qui s’affichent avec des pages de liste, nous recommandons une seule page. Le Récapitulatif Power BI n’affiche que la première page de votre rapport.

## <a name="naming-the-report"></a>Définition du nom du rapport

Donnez au rapport un nom contenant le nom de la page de liste associée au rapport. Par exemple, si le rapport concerne la page de liste **Fournisseur**, incluez le mot *fournisseur* quelque part dans le nom.  

Cette convention de désignation de nom n’est pas obligatoire. Cependant, il permet de sélectionner plus rapidement des rapports dans [!INCLUDE[prod_short](includes/prod_short.md)]. Lorsque la page de sélection du rapport s’ouvre à partir d’une page de liste, elle est automatiquement filtrée en fonction du nom de la page. Ce filtrage est effectué pour limiter les rapports affichés. Vous pouvez aussi effacer le filtre pour obtenir la liste complète des rapports disponibles dans Power BI.  

## <a name="fixing-problems"></a>Résolution des problèmes

Cette section fournit une solution de rechange pour les problèmes les plus courants qui apparaissent lorsque vous créez le rapport Power BI.  

#### <a name="you-cant-see-a-report-on-the-select-report-page"></a>Vous ne pouvez pas voir de rapport sur la page Sélectionner un rapport.

C’est probablement parce que le nom du rapport ne contient pas le nom de la page de liste. Effacez le filtre pour obtenir la liste complète des rapports disponibles dans Power BI.  

#### <a name="report-is-loaded-but-blank-not-filtered-or-filtered-incorrectly"></a>Le rapport est chargé, mais vide, non filtré ou filtré incorrectement.

Vérifiez que le filtre du rapport contient la bonne clé primaire. Dans la plupart des cas, il s’agit du champ **N°**, mais dans la table **Écriture**, vous devez utiliser le champ **N° écriture**.

#### <a name="report-is-loaded-but-it-shows-a-page-you-didnt-expect"></a>Le rapport est chargé, mais il affiche une page à laquelle vous ne vous attendiez pas.

Vérifiez que la page que vous souhaitez afficher est la première page de votre rapport.  

#### <a name="report-appears-with-an-unwanted-gray-boarder-or-its-too-small-or-too-large"></a>L rapport apparaît avec des bordures grises non désirées, il est trop petit ou trop grand.

Vérifiez que la taille du rapport est configurée sur 325 pixels x 310 pixels. Enregistrez le rapport, puis actualisez la page de liste.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Activation de vos données commerciales pour Power BI](admin-powerbi.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Mise en route](product-get-started.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finances](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]