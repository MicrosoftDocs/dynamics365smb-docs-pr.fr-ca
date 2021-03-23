---
title: Utiliser des états financiers et des aperçus dans Excel
description: En savoir plus sur la manière dont vous pouvez ouvrir des états financiers dans Microsoft Excel à partir de Business Central pour une meilleure analyse.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: accountant, accounting, financial report
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 54d4bed11f79aef8e5d4c123dceb479e263e5ec7
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5391159"
---
# <a name="analyzing-financial-statements-in-microsoft-excel"></a>Analyse des états financiers dans Microsoft Excel

Dans [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez visualiser les KPI et obtenir des aperçus de l'état financier de la compagnie. Vous pouvez également ouvrir des listes dans Excel et analyser les données afférentes. De plus, vous pouvez exporter des relevés financiers volumineux, tels que le bilan ou l'état des résultats vers Excel, analyser les données et imprimer les rapports.  

Dans les tableaux de bord Gestionnaire d'utilisation et Comptable, vous pouvez choisir les états financiers à afficher dans Excel à partir d'un menu déroulant dans la section Rapports pour personnaliser le ruban. Lorsque vous sélectionnez un état, il est ouvert dans Excel ou Excel Online. Un complément connecte les données à [!INCLUDE [prod_short](includes/prod_short.md)]. Cependant, vous devez vous connecter avec le même compte que celui utilisé avec [!INCLUDE [prod_short](includes/prod_short.md)].  

## <a name="getting-the-overview-and-the-details-in-excel"></a>Affichage de l'aperçu et des détails dans Excel

Dans le ruban, sélectionnez le rapport Excel approprié, et laissez-le ouvert afin d'accéder à l'aperçu que vous recherchiez. Dans cette version de [!INCLUDE [prod_short](includes/prod_short.md)], nous proposons les rapports Excel suivants :

- Bilan  
- État des résultats  
- Déclaration de trésorerie  
- Déclaration de réserves  
- Comptes fournisseurs classés chronologiquement  
- Comptabilité client classée chronologiquement  

Supposons que vous souhaitiez analyser en profondeur votre trésorerie. Depuis les tableaux de bord Gestionnaire d’activité et Comptable, vous pouvez ouvrir le rapport **Déclaration de trésorerie** dans Excel, mais en réalité, nous exportons les données appropriées pour vous et créons un classeur Excel sur la base d’un modèle prédéfini. Selon votre navigateur, vous pouvez être invité à ouvrir ou enregistrer le classeur.  

Dans Excel, vous pouvez voir un onglet où les données sont présentées sur la première feuille. Toutes les données qui ont été exportées sont également présentes dans d'autres feuilles en cas de besoin. Vous pouvez imprimer le rapport tel qu'il est, ou vous pouvez le modifier jusqu'à ce que vous ayez l'aperçu et les détails que vous souhaitez. Utilisez le complément [!INCLUDE [prod_short](includes/prod_short.md)] pour Excel afin de mieux filtrer et analyser les données.  

### <a name="understanding-the-excel-templates"></a>Comprendre les modèles Excel

Les rapports Excel prédéfinis sont basés sur les données de la compagnie actuelle. Par exemple, la compagnie de démonstration a mis en place le plan comptable pour répertorier trois comptes règlement sous *Actifs actuels* : 10100 **Compte chèque**, 10200 **Compte épargne** et 10300 **Fonds de caisse**. Les comptes ont le champ **Sous-catégorie de compte** défini sur *Espèces*, et c’est leur montant combiné qui apparaît comme *Espèces* dans le rapport Excel **Bilan**.  

Des feuilles supplémentaires dans le classeur Excel affichent les données derrière le rapport. Mais pour savoir ce qui se cache derrière les regroupements dans les rapports Excel, vous devrez peut-être revenir à [!INCLUDE [prod_short](includes/prod_short.md)] et appliquer des filtres aux listes, par exemple.  

## <a name="the-prod_short-excel-add-in"></a>Module complémentaire [!INCLUDE [prod_short](includes/prod_short.md)] pour Excel

Votre expérience [!INCLUDE [prod_short](includes/prod_short.md)] inclut un complément pour Excel. Selon votre abonnement, vous êtes connecté automatiquement, ou vous devez spécifier les mêmes détails d'ouverture de session utilisés pour [!INCLUDE [prod_short](includes/prod_short.md)]. Pour plus d’informations, voir [Affichage et édition dans Excel depuis Business Central](across-work-with-excel.md).  

Le complément vous permet d'obtenir des données actualisées à partir de [!INCLUDE [prod_short](includes/prod_short.md)] et d'appliquer les modifications à [!INCLUDE [prod_short](includes/prod_short.md)]. Toutefois, la possibilité de transférer les données vers la base de données est désactivée pour les rapports financiers Excel dans la liste ci-dessus.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Affichage et édition dans Excel depuis Business Central](across-work-with-excel.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Le grand livre et le plan comptable](finance-general-ledger.md)  
[Utilisation de Business Central](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]