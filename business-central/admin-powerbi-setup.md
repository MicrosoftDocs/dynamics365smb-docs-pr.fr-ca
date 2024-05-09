---
title: Activation de l’intégration Power BI avec Business Central
description: "Découvrez comment configurer la connexion à Power BI. Avec les rapports Power BI, obtenez des informations, des informations décisionnelles et des indicateurs de performance clés à partir de vos données Business\_Central."
author: jswymer
ms.topic: get-started
ms.search.keywords: 'Power BI, setup, analysis, reporting, financial report, business intelligence, KPI'
ms.date: 01/28/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Activation de l’intégration de Power BI avec [!INCLUDE[prod_short](includes/prod_short.md)]

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Cet article décrit comment préparer [!INCLUDE[prod_short](includes/prod_short.md)] pour l’intégration avec Power BI. [!INCLUDE[prod_short](includes/prod_short.md)] en ligne est déjà activée pour intégration, bien que vous souhaitiez peut-être lire certaines informations sur les licences. Pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site, vous aurez configuré votre environnement pour vous connecter à Power BI avant que les utilisateurs puissent l’utiliser.

## <a name="license"></a>Gestion des licences Power BI

Avec [!INCLUDE[prod_short](includes/prod_short.md)], les utilisateurs bénéficient d’une licence Power BI qui donne accès aux fonctionnalités les plus courantes dans [!INCLUDE[prod_short](includes/prod_short.md)] et Power BI. Vous pouvez également acheter une licence Power BI Pro qui donne accès à des fonctionnalités supplémentaires. Le tableau suivant donne un aperçu des fonctionnalités disponibles avec chaque licence.

|Licence Power|Afficher les rapports|Créer des rapports|Partager des rapports|Actualiser les rapports| Applications [!INCLUDE[prod_short](includes/prod_short.md)]|
|-------------|--------||
|Power BI, version gratuite|![une coche.](media/check.png)|![une autre coche](media/check.png)|(limitée)|(limitée)||
|Power BI Pro|![encore une autre coche.](media/check.png)|![c’est une coche](media/check.png)|![encore une coche](media/check.png)|(étendue)|![dernière coche](media/check.png)|

Pour plus d’informations, consultez [Gestion des licences du service Power BI pour les utilisateurs de votre organisation](/power-bi/admin/service-admin-licensing-organization) ou [S’inscrire au service Power BI en tant que particulier](/power-bi/fundamentals/service-self-service-signup-for-power-bi).

## <a name="exposedata"></a>Exposer des données via des API ou des services Web OData

Business Central propose deux manières d’exposer les données qui peuvent être consommées par les rapports Power BI : des pages ou des requêtes API et des services Web Open Data Protocol (OData).

### Pages et requêtes API

> **S’APPLIQUE À :** Business Central Online uniquement

Les développeurs peuvent définir des objets de page et des objets de requête de type *API*. De cette façon, ils peuvent exposer les données des tables de base de données via un service REST pris en charge par le Webhook et compatible avec OData v4. Ce type de données ne peut pas être affiché dans l’interface utilisateur, mais est destiné à créer des services d’intégration fiables.

Business Central Online est disponible avec un ensemble d’API intégrées, que vous pouvez utiliser pour obtenir des données pour les entités commerciales les plus courantes, telles que les clients, les articles, les documents de vente, etc. Aucun travail ou configuration supplémentaire n’est requis pour utiliser ces API comme source de données pour les rapports Power BI. Pour plus d’informations sur ces API, consultez [API Business Central V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/).

Business Central Online prend également en charge les API personnalisées. Les développeurs d’applications des solutions Business Central peuvent créer leurs propres pages et requêtes API et les regrouper dans des applications. Vous pouvez ensuite installer les applications sur votre locataire. Une fois installé, vous utiliser les pages API pour vos rapports Power BI, comme vous le feriez avec les API intégrées (v2.0). Pour plus d’informations sur la création d'une API en exposant des pages ou des requêtes, consultez [Développement d’une API personnalisée](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api).

> [!IMPORTANT]
> À partir de février 2022, les rapports Power BI pour [!INCLUDE[prod_short](includes/prod_short.md)] Online proviennent d’une réplique de base de données secondaire en lecture seule pour des raisons de performances. Par conséquent, les développeurs AL doivent éviter de concevoir des pages d’API qui modifient la base de données pendant que les pages s’ouvrent ou chargent des enregistrements. En particulier, prenez en compte le code sur les déclencheurs AL : OnInit, OnOpenPage, OnFindRecord, OnNextRecord, OnAfterGetRecord et OnAfterGetCurrRecord. Ces modifications de la base de données, dans certains cas, peuvent entraîner des problèmes de performances et empêcher le rapport d’actualiser les données. Pour plus d’informations, voir [Articles sur les performances pour les développeurs](/dynamics365/business-central/dev-itpro/performance/performance-developer?branch=main#writing-efficient-web-services) dans le contenu de développement de Business Central.
>
> Dans de rares cas, le comportement entraînera une erreur lorsqu’un utilisateur essaiera d’obtenir des données à partir de l'API pour un rapport dans Power BI Desktop. Toutefois, si des modifications de la base de données sont nécessaires dans l'API personnalisée, les utilisateurs de Power BI Desktop peuvent forcer le comportement. Pour plus d’informations, consultez [Création de rapports Power BI pour afficher les données Business Central](across-how-use-financials-data-source-powerbi.md#fixing-problems).

### Services Web OData

Vous pouvez publier des objets d’application Business Central, tels que des unités de code, des pages et des requêtes, comme les [services Web OData](/dynamics365/business-central/dev-itpro/webservices/odata-web-services). Avec Business Central Online, de nombreux services Web sont publiés par défaut. Pour trouver facilement les services Web, il suffit de rechercher *services web* dans [!INCLUDE[prod_short](includes/prod_short.md)]. Sur la page **Services Web**, assurez-vous que le champ **Publier** est sélectionné pour les services Web répertoriés ci-dessus. Pour plus d’informations sur la publication des services Web, voir [Publier un service Web](across-how-publish-web-service.md).

Pour savoir ce que vous pouvez faire pour garantir les meilleures performances des services Web, comme observé depuis Business Central Server (point de terminaison) et le consommateur (client), consultez [Écrire des services Web efficaces](/dynamics365/business-central/dev-itpro/performance/performance-developer#writing-efficient-web-services).

### Choisir d’utiliser des pages API ou des services Web OData

Dans la mesure du possible, nous vous encourageons à utiliser des pages API au lieu du service Web OData. Les pages API sont plus rapides à charger les données dans les rapports Power BI que les services Web OData. De plus elles sont plus flexibles, car elles vous permettent d’obtenir des données à partir de champs de table qui ne sont pas définis dans un objet de page.

<!--## <a name="setup"></a>Set up [!INCLUDE[prod_short](includes/prod_short.md)] on-premises for Power BI integration

This section explains the requirements for a [!INCLUDE[prod_short](includes/prod_short.md)] on-premises deployment to integrate with Power BI.

1. Configure either [NavUserPassword](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-navuserpassword) or [Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-ad-overview) as the authentication method for the deployment.  
    
    > [!NOTE]
    > Power BI integration doesn't support Windows authentication and is not supported on Windows Client.

2. Enable OData web services and the ODataV4 endpoint.

    OData web service must be enabled on the [!INCLUDE[server](includes/server.md)], and OData port opened in firewall. For more information, see [Configuring Business Central Server - OData Web Services](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#ODataServices).

    The local server must be accessible from the Internet.

3. Give [!INCLUDE[prod_short](includes/prod_short.md)] user accounts a web service access key.

    A web service access key is only needed to view [!INCLUDE[prod_short](includes/prod_short.md)] data in Power BI. You can assign a web service access key to each user account. Or instead, create a specific account with a web service access key for use by all users. For more information, see [Web Services Authentication](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication#generate-a-web-service-access-key).

    <!--
    > [!IMPORTANT]
    > With [!INCLUDE[prod_short](../developer/includes/prod_short.md)] online, the use of access keys (Basic Auth) for web service authentication is [deprecated](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#accesskeys). We recommend that you use OAuth2 instead. For more information, see [Use OAuth to Authorize Business Central Web Services](/dynamics365/business-central/dev-itpro/webservices/authenticate-web-services-using-oauth).-->

<!--4. Create an application registration for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure.

    To view Power BI reports embedded in [!INCLUDE[prod_short](includes/prod_short.md)] pages, an application must be registered for [!INCLUDE[prod_short](includes/prod_short.md)] in Microsoft Azure. The registered application needs permission to Power BI services. At a minimum, the app requires  **User.ReadWrite.All** permission. For users to view reports from shared Power BI workspaces, the app requires **Workspace.Read.All** permission. For more information, see [Registering [!INCLUDE[prod_short](includes/prod_short.md)] On-Premises in Microsoft Entra ID for Integrating with Other Services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

    > [!NOTE]
    > If your deployment uses NavUserPassword authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the same Power BI service for all users. You'll specify this service account as part of registering the application. With Microsoft Entra authentication, [!INCLUDE[prod_short](includes/prod_short.md)] connects to the Power BI service associated with the individual user accounts.

    <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
<!--5. Make the initial connection from Business Central to Power BI.

    Before end-users can use Power BI in [!INCLUDE[prod_short](includes/prod_short.md)], an Azure application administrator will have to give consent to the Power BI service.

    To make the initial connection, open [!INCLUDE[prod_short](includes/prod_short.md)], and run **Get Started with Power BI** from the Home page. This action will lead you through the consent process, and check your Power BI license. When prompted sign in using an Microsoft Entra admin account. For more information, see [Connect to Power BI - one time only](across-working-with-powerbi.md#connect).-->

## Paramétrage des flux de données

Les flux de données vous permettent d’ingérer, de transformer et de charger des données dans un Power BI espace de travail, puis d’utiliser les données comme base pour vos rapports. Ces flux de données peuvent dans certains cas rencontrer des erreurs passagères lors d’une actualisation programmée. Le message d’erreur ressemble à ceci : `DataSource.Error: OData: Unable to read data from the transport connection: An existing connection was forcibly closed by the remote host.` 

À l’aide de PowerAutomate, vous pouvez configurer des tentatives dans le cas de cette situation. Pour plus d’informations, consultez [Réessayer automatiquement un flux de données en cas d’échec](/power-query/dataflows/automatically-retry-dataflow).

## Voir aussi .

[Business Central et Power BI](admin-powerbi.md)  
[Vue d’ensemble Architecture et composante d’intégration Power BI pour [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Power BI pour les consommateurs](/power-bi/consumer/end-user-consumer)  
[Le « nouveau look » du service Power BI](/power-bi/service-new-look)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Documentation Power BI](/power-bi/)  
[Veille économique](bi.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  




[!INCLUDE[footer-include](includes/footer-banner.md)]
