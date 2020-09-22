---
title: Vue d’ensemble Architecture et composante d’intégration Power BI pour Business Central| Microsoft Docs
description: Il est facile d'obtenir des informations exploitables, de la veille économique et des KPI de vos applications Business Central pour Power BI.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.reviewer: edupont
ms.date: 04/01/2020
ms.author: jswymer
ms.openlocfilehash: 9514f0355932c1b1cbd30acfdb9f6dab46db8a0a
ms.sourcegitcommit: aeaa0dc64e54432a70c4b0e1faf325cd17d01389
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 08/17/2020
ms.locfileid: "3697812"
---
# <a name="power-bi-integration-component-and-architecture-overview-for-prodshort"></a>Vue d’ensemble Architecture et composante d’intégration Power BI pour [!INCLUDE[prodshort](includes/prodshort.md)]

Dans cet article, vous découvrirez les différents aspects de l’intégration de Power BI à [!INCLUDE[prodshort](includes/prodshort.md)] pour vous aider à comprendre sa mise en œuvre et son utilisation.

## <a name="components"></a>Composantes

Le tableau suivant décrit les principales composantes impliquées dans l’intégration Power BI.

|Composante|Description|
|---------|-----------|
|Power BI|Un service d’hébergement et de gestion des rapports basé sur le nuage.|
|Power BI Desktop|Outil de création permettant de créer des rapports et des tableaux de bord, et vous permettant d’exécuter des rapports. Il est disponible en téléchargement gratuit sur Microsoft Store et est installé localement.|
|[!INCLUDE[prodshort](includes/prodshort.md)]|Solution en ligne ou sur site avec des connecteurs exposés à Power BI et possibilité d’intégrer une partie de Power BI.|

## <a name="whats-available-from-the-start"></a>Ce qui est disponible dès le départ

Le tableau suivant décrit les fonctionnalités disponibles.

|Fonctionnalité|Support [!INCLUDE[prodshort](includes/prodshort.md)] en ligne ou sur site|
|-------|---------------------|
|Connecteurs Power BI|Les deux. Différents connecteurs pour la solution ligne et la solution sur site. Connecteur identique utilisé pour le service Power BI Desktop et Power BI |
|Expérience intégrée pour afficher un rapport donné dans un Récapitulatif dans [!INCLUDE[prodshort](includes/prodshort.md)]|Les deux. Nécessite une configuration pour afficher les rapports sur site.|
|Gestion des rapports Power BI depuis [!INCLUDE[prodshort](includes/prodshort.md)]|En ligne|
|Rapports Power BI par défaut sur les tableaux de bord déployés vers Power BI|En ligne|
|Applications Power BI sur Microsoft AppSource|En ligne.|

## <a name="architecture"></a>Architecture

[!INCLUDE[prodshort](includes/prodshort.md)] s’intègre à Power BI via un connecteur utilisant OData. La source de données pour les rapports Power BI est exposée comme services Web OData.

![Architecture Power BI pour l’intégration avec Business Central](./media/power-bi-architecture.png)

## <a name="general-flow"></a>Flux général

Le diagramme suivant illustre le flux de travail de base pour les utilisateurs lors de la connexion de [!INCLUDE[prodshort](includes/prodshort.md)] à Power BI.

![Flux de travai Power BI pour l’intégration avec Business Central](./media/power-bi-flow.png)

1. L’utilisateur s’inscrit à un compte Power BI.
2. L’utilisateur se connecte à Power BI depuis [!INCLUDE[prodshort](includes/prodshort.md)].
3. [!INCLUDE[prodshort](includes/prodshort.md)] vérifie la licence.
4. [!INCLUDE[prodshort](includes/prodshort.md)] déploie les rapports par défaut sur le service Power BI. Cette étape ne se produit que pour [!INCLUDE[prodshort](includes/prodshort.md)] en ligne.
5. [!INCLUDE[prodshort](includes/prodshort.md)] rend les rapports dans Power BI disponibles pour la sélection dans [!INCLUDE[prodshort](includes/prodshort.md)]. Les rapports par défaut sont automatiquement affichés dans des parties de Power BI.
6. L’utilisateur crée un rapport dans Power BI Desktop.
7. L’utilisateur publie le rapport vers le service Power BI. Les rapports sont ensuite disponibles pour la sélection dans [!INCLUDE[prodshort](includes/prodshort.md)].

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Business Central et Power BI](admin-powerbi.md)  
[Power BI pour les consommateurs](/power-bi/consumer/end-user-consumer)  
[Le « nouveau look » du service Power BI](/power-bi/service-new-look)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Documentation Power BI](/power-bi/)  
[Veille économique](bi.md)  
[Mise en route](product-get-started.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  