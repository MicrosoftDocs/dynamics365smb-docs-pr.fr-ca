---
title: Vue d’ensemble Architecture et composante d’intégration Power BI pour Business Central| Microsoft Docs
description: En savoir plus sur les différents aspects de l′intégration Power BI avec Business Central.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.reviewer: edupont
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: a1d0d0403798f8cd2af6b29249f01f529fb789be
ms.sourcegitcommit: c11ad91a389ed72532f5513654fdc7909b20aed9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935246"
---
# <a name="power-bi-integration-component-and-architecture-overview-for-prod_short"></a>Vue d’ensemble Architecture et composante d’intégration Power BI pour [!INCLUDE[prod_short](includes/prod_short.md)]

Dans cet article, vous découvrirez les différents aspects de l’intégration de Power BI à [!INCLUDE[prod_short](includes/prod_short.md)] pour vous aider à comprendre sa mise en œuvre et son utilisation.

## <a name="components"></a>Composantes

Le tableau suivant décrit les principales composantes impliquées dans l’intégration Power BI.

|Composante|Description|
|---------|-----------|
|Power BI|Un service d’hébergement et de gestion des rapports basé sur le nuage.|
|Power BI Desktop|Outil de création permettant de créer des rapports et des tableaux de bord, et vous permettant d’exécuter des rapports. Il est disponible en téléchargement gratuit sur Microsoft Store et est installé localement.|
|[!INCLUDE[prod_short](includes/prod_short.md)]|Solution en ligne ou sur site avec des connecteurs exposés à Power BI et possibilité d’intégrer une partie de Power BI.|

## <a name="whats-available-from-the-start"></a>Ce qui est disponible dès le départ

Le tableau suivant décrit les fonctionnalités disponibles.

|Fonctionnalité|Support [!INCLUDE[prod_short](includes/prod_short.md)] en ligne ou sur site|
|-------|---------------------|
|Connecteurs Power BI|Les deux. Différents connecteurs pour la solution ligne et la solution sur site. Connecteur identique utilisé pour le service Power BI Desktop et Power BI |
|Expérience intégrée pour afficher un rapport donné dans un Récapitulatif dans [!INCLUDE[prod_short](includes/prod_short.md)]|Les deux. Nécessite une configuration pour afficher les rapports sur site.|
|Gestion des rapports Power BI depuis [!INCLUDE[prod_short](includes/prod_short.md)]|En ligne|
|Rapports Power BI par défaut sur les tableaux de bord déployés vers Power BI|En ligne|
|Applications Power BI sur Microsoft AppSource|En ligne.|

## <a name="architecture"></a>Architecture

[!INCLUDE[prod_short](includes/prod_short.md)] s’intègre à Power BI via un connecteur utilisant OData. La source de données pour les rapports Power BI est exposée comme services Web OData.

![Architecture Power BI pour l’intégration avec Business Central](./media/power-bi-architecture.png)

## <a name="general-flow"></a>Flux général

Le diagramme suivant illustre le flux de travail de base pour les utilisateurs lors de la connexion de [!INCLUDE[prod_short](includes/prod_short.md)] à Power BI.

![Flux de travai Power BI pour l’intégration avec Business Central](./media/power-bi-flow.png)

1. L’utilisateur s’inscrit à un compte Power BI.
2. L’utilisateur se connecte à Power BI depuis [!INCLUDE[prod_short](includes/prod_short.md)].
3. [!INCLUDE[prod_short](includes/prod_short.md)] vérifie la licence.
4. [!INCLUDE[prod_short](includes/prod_short.md)] déploie les rapports par défaut sur le service Power BI. Cette étape ne se produit que pour [!INCLUDE[prod_short](includes/prod_short.md)] en ligne.
5. [!INCLUDE[prod_short](includes/prod_short.md)] rend les rapports dans Power BI disponibles pour la sélection dans [!INCLUDE[prod_short](includes/prod_short.md)]. Les rapports par défaut sont automatiquement affichés dans des parties de Power BI.
6. L’utilisateur crée un rapport dans Power BI Desktop.
7. L’utilisateur publie le rapport vers le service Power BI. Les rapports sont ensuite disponibles pour la sélection dans [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Business Central et Power BI](admin-powerbi.md)  
[Power BI pour les consommateurs](/power-bi/consumer/end-user-consumer)  
[Le « nouveau look » du service Power BI](/power-bi/service-new-look)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Documentation Power BI](/power-bi/)  
[Veille économique](bi.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]