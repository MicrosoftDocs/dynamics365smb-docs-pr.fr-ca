---
title: Connexion de Power BI à Business Central sur site | Microsoft Docs
description: "Obtenir des informations, des informations décisionnelles et des indicateurs de performance clés à partir de vos données Business\_Central à l’aide de Power BI."
author: jswymer
ms.topic: get-started
ms.devlang: al
ms.search.keywords: 'account schedule, analysis, reporting, financial report, business intelligence, KPI'
ms.date: 01/22/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---
# Connecter à Power BI à partir de Business Central en local

<!--In this article, you learn some of the basics about working with reports and dashboards in Power BI that use [!INCLUDE [prod_short](includes/prod_short.md)] as a data source. The article discusses some aspects that will help you get started as a [!INCLUDE[prod_short](includes/prod_short.md)] user. For general guidelines and instructions about using Power BI, see [Power BI documentation for consumers](/power-bi/consumer).

## Get ready

Sign up for the Power BI service. If you haven't already signed up, go to [https://powerbi.microsoft.com](https://powerbi.microsoft.com). When you sign up, use a work email address and password.-->

## Mise en route

Pour utilisez [!INCLUDE [prod_short](includes/prod_short.md)] sur site, il doit être activé pour l’intégration de Power BI. Cette tâche est généralement effectuée par un administrateur. Pour plus d’informations sur l’activation de l’ Power BI intégration avec Business Central Online, voir [Configurer Business Central sur site pour Power BI l’intégration](admin-powerbi-setup.md).

Certaines fonctionnalités ne sont disponibles qu’avec Business Central Online, pas sur site. Pour plus d’informations, voir [Introduction Business Central et Power BI](admin-powerbi.md#what-you-can-do-with-power-bi-and-business-central)

## <a name="setup"></a>Configurer [!INCLUDE[prod_short](includes/prod_short.md)] sur site pour l’intégration Power BI

Cette section explique les conditions requises pour un déploiement [!INCLUDE[prod_short](includes/prod_short.md)] sur site à intégrer à Power BI.

1. Configurez [NavUserPassword](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-navuserpassword) ou [Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/authenticating-users-with-azure-ad-overview) comme méthode d’authentification pour le déploiement.  
    
    > [!NOTE]
    > L’intégration Power BI ne prend pas en charge l’authentification Windows et n’est pas prise en charge sur le client Windows.

2. Activez les services Web OData et le point de terminaison ODataV4.

    Le service Web OData doit être activé sur le [!INCLUDE[server](includes/server.md)] et le port OData ouvert dans le pare-feu. Pour plus d’informations, reportez-vous à la rubrique [Configuration de Business Central Server - Services Web OData](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#ODataServices).

    Le serveur local doit être accessible depuis Internet.

3. Accordez aux comptes d’utilisateur [!INCLUDE[prod_short](includes/prod_short.md)] une clé d’accès au service Web.

    Une clé d’accès au service Web est nécessaire uniquement pour afficher les données [!INCLUDE[prod_short](includes/prod_short.md)] dans Power BI. Vous pouvez attribuer une clé d’accès au service Web à chaque compte d’utilisateur. Ou plutôt, créez un compte spécifique avec une clé d’accès au service Web à l’usage de tous les utilisateurs. Pour plus d’informations, reportez-vous à la rubrique [Authentification des services Web](/dynamics365/business-central/dev-itpro/webservices/web-services-authentication#generate-a-web-service-access-key).

4. Créez un enregistrement d’application pour [!INCLUDE[prod_short](includes/prod_short.md)] dans Microsoft Azure.

    Pour voir les rapports Power BI intégrés dans les pages [!INCLUDE[prod_short](includes/prod_short.md)], une application doit être enregistrée pour [!INCLUDE[prod_short](includes/prod_short.md)] dans Microsoft Azure. L’application enregistrée a besoin d’une autorisation pour les services Power BI. Au minimum, l’application nécessite l’autorisation **User.ReadWrite.All**. Pour que les utilisateurs puissent afficher les rapports des espaces de travail Power BI partagés, l’application nécessite l’autorisation **Workspace.Read.All**. Pour plus d’informations, voir [Enregistrement de [!INCLUDE[prod_short](includes/prod_short.md)] en local dans Microsoft Entra ID pour l’intégration avec d’autres services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

    > [!NOTE]
    > Si votre déploiement utilise l’authentification NavUserPassword, [!INCLUDE[prod_short](includes/prod_short.md)] se connecte au même service Power BI pour tous les utilisateurs. Vous spécifierez ce compte de service dans le cadre de l’enregistrement de l’application. Avec l’authentification Microsoft Entra, [!INCLUDE[prod_short](includes/prod_short.md)] se connecte au service Power BI associé aux comptes utilisateurs individuels.

    <!-- Windows authentication can also be used but you can't get data from BC in Power BI -->
5. Établissez la connexion initiale de Business Central vers Power BI.

    Avant que les utilisateurs finaux puissent utiliser Power BI dans [!INCLUDE[prod_short](includes/prod_short.md)], un administrateur de l’application Azure devra donner son accord au service Power BI.

    Pour établir la connexion initiale, ouvrez [!INCLUDE[prod_short](includes/prod_short.md)], et exécutez **Mise en route avec Power BI** à partir de la page d'accueil. Cette action vous guidera tout au long du processus de consentement et vérifiera votre licence Power BI. Lorsque vous y êtes invité, connectez-vous à l’aide d’un compte d’administrateur Microsoft Entra. Pour en savoir plus, consultez [Se connecter à Power BI – une fois seulement](across-working-with-powerbi.md#connect).

## Créer des rapports Power BI pour afficher des données [!INCLUDE [prod_long](includes/prod_long.md)]

Vous pouvez rendre vos données Dynamics 365 Business Central disponibles sous forme de source de données dans Power BI Desktop et créer des rapports puissants sur l'état de votre activité.

Utilisez Power BI Desktop pour créer des rapports qui affichent des données Dynamics 365 Business Central. Après avoir créé des rapports, vous pouvez les publier dans votre service Power BI ou les partager avec tous les utilisateurs de votre organisation. Une fois que ces rapports figurent dans le service Power BI, les utilisateurs configurés pour ce dernier peuvent alors afficher les rapports dans Dynamics 365 Business Central.

- Pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site, obtenez les informations suivantes :

  - L’URL OData pour [!INCLUDE[prod_short](includes/prod_short.md)].
  
    En règle générale, cette URL a le format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, par exemple `https://localhost:7048/BC190/ODataV4`. Si vous disposez d’un déploiement à plusieurs abonnés, incluez le client dans l’URL, par exemple `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - Un nom d’utilisateur et une clé d’accès au service Web d’un compte [!INCLUDE[prod_short](includes/prod_short.md)].

    Pour obtenir des données depuis [!INCLUDE[prod_short](includes/prod_short.md)], Power BI utilise l’authentification de base. Vous aurez donc besoin d’un nom d’utilisateur et d’une clé d’accès au service Web pour vous connecter. Le compte peut être votre propre compte utilisateur ou votre organisation peut avoir un compte spécifique à cette fin.

## <a name="getdata"></a>Ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop

La première tâche dans le cadre de la création de rapports consiste à ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop. Une fois connecté, vous pouvez commencer à créer le rapport.

1. Lancez Power BI Desktop.
2. Sélectionnez **Extraire les données**.

    Si vous ne voyez pas **Extraire les données**, sélectionnez le menu **Fichier**, puis **Extraire les données**.
3. Sur la page **Extraire les données**, sélectionnez **Services en ligne**.
4. Dans volet **Services enligne** se connecter à [!INCLUDE [prod_short](includes/prod_short.md)] local, sélectionnez **Dynamics 365 Business Central (local)**, puis **Connecter**.
5. Connectez-vous à [!INCLUDE [prod_short](includes/prod_short.md)] (une fois seulement).

    Si vous ne vous êtes jamais connecté à [!INCLUDE [prod_short](includes/prod_short.md)] depuis Power BI Desktop auparavant, vous êtes invité à vous connecter.

   - Pour [!INCLUDE [prod_short](includes/prod_short.md)] local, saisissez d’abord l’URL OData pour [!INCLUDE[prod_short](includes/prod_short.md)], puis sélectionnez **OK**. Puis, à l’invite, entrez le nom d’utilisateur et le mot de passe du compte à utiliser pour vous connecter à [!INCLUDE[prod_short](includes/prod_short.md)]. Dans la zone **Mot de passe**, entrez la clé d’accès au service Web. Lorsque vous avez terminé, sélectionnez **Connecter**.
   
    > [!NOTE]  
    > Une fois que vous êtes connecté(e) à [!INCLUDE[prod_short](includes/prod_short.md)], vous n’êtes plus invité(e) à vous connecter. [Comment modifier ou effacer le compte que j’utilise actuellement pour me connecter à Business Central depuis Power BI Desktop ?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

6. Une fois connecté, Power BI se met en contact avec le service Business Central. La fenêtre **Navigateur** apparaît et affiche les sources de données disponibles pour les rapports de construction. Sélectionnez un dossier pour le développer et voir les sources de données disponibles. 

   Ces sources de données représentent tous les services web et les pages API que vous avez publiés à partir de [!INCLUDE [prod_short](includes/prod_short.md)]. Les sources de données sont regroupées par environnements et compagnies Business Central.

   > [!NOTE]
    > La structure de Business Central en local est différente, car elle ne prend pas en charge les pages API.

7. Sélectionnez la source ou les sources de données que vous souhaitez ajouter à votre modèle de données, puis sélectionnez le bouton **Charge**.
8. Si vous souhaitez ajouter ultérieurement d’autres données Business Central, vous pouvez répéter les étapes précédentes.

Une fois les données chargées, elles s'affichent dans le volet de navigation à droite dans la page. À ce stade, vous êtes connecté(e) à vos données [!INCLUDE[prod_short](includes/prod_short.md)] et vous êtes prêt(e) à générer votre rapport Power BI.  

> [!TIP]
> Pour plus d’informations sur l’utilisation de Power BI Desktop, reportez-vous à [Mise en route avec Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## Gérer et modifier les rapports

> [!NOTE]
> Vous ne pouvez pas gérer ni modifier de rapports. 

## Télécharger des rapports

Pour [!INCLUDE [prod_short](includes/prod_short.md)] sur site, aucun rapport de démonstration n’est disponible. Vous devrez donc repartir de zéro en utilisant Power BI Desktop. Sinon, les rapports Power BI peuvent être distribués sous forme de fichiers que vous pouvez télécharger directement à partir du service Power BI en ligne. Pour plus d’informations, consultez [Télécharger le rapport vers le service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

<!--
> [!NOTE]
> Uploading a report requires that you have SUPER user permissions in [!INCLUDE[prod_short](includes/prod_short.md)]. Also, you can't upload reports with [!INCLUDE [prod_short](includes/prod_short.md)] on-premises. With on-premises, you upload reports directly to your Power BI workspace. For more information, see [Connect to Power BI from [!INCLUDE [prod_short](includes/prod_short.md)] on-premises](across-working-with-business-central-in-powerbi.md).

<!--Once you have a Power BI account, you can sign in at [https://powerbi.microsoft.com/](https://powerbi.microsoft.com/).

The Power BI service hosts all the reports available to you. To see the report, select **My Workspace** > **Reports**. Then just select the report that you want to view.

With [!INCLUDE[prod_short](includes/prod_short.md)] online, you'll automatically have a set of default reports on your workspace. If you want to create your own reports, you can use Power BI Desktop to create reports, and then publish them to your workspace. For more information, see [Getting Started Building Reports in Power BI Desktop to Display [!INCLUDE [prod_long](includes/prod_long.md)] Data](across-how-use-financials-data-source-powerbi.md).

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

If you're using [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, you'll have to start from scratch by using Power BI Desktop. Optionally, Power BI reports can be distributed as files, that you can upload.

<!--## Get the latest data

Each Power BI report is based on a dataset that gets data from the [!INCLUDE[prod_short](includes/prod_short.md)] sources. You want to make sure that the data in your Power BI reports is up to date with the data in [!INCLUDE[prod_short](includes/prod_short.md)]. This concept is referred to as *refreshing*.  Depending on how your organization has set up Power BI, refreshing might not happen automatically. There are two ways to refresh data: manually or by scheduling a refresh. Manual refreshing is done on-demand, as needed. Scheduled refreshing lets you refresh automatically at defined time intervals.

### Refresh manually

In the navigation pane, under **Datasets**, select **More options (...)** next to the dataset, then select **Refresh now**.

### Schedule a refresh

In the navigation pane, under Datasets, select More options (...) next to the dataset, then select **Schedule refresh**. Fill in the information under the **Schedule refresh** section, and select **Apply**.

For more information, see [Configure scheduled refresh](/power-bi/connect-data/refresh-scheduled-refresh)-->

<!--## <a name="upload"></a>Upload reports from files

Power BI Reports can be distributed among users as .pbix files. If you have a .pbix file, you can upload the file to a workspace. To upload a report, do the following steps:

1. In your new workspace, select **Get Data**.

2. In the Files box, select **Get**.

3. Select **Local File**, navigate to where you saved the file, and select **Open**.

For more information, see [Upload the report to the service](/power-bi/paginated-reports/paginated-reports-quickstart-aw#upload-the-report-to-the-service).

> [!NOTE]
> Uploading a report requires that you have a [Premium capacity](/power-bi/service-premium-what-is) work space. For more information, see [Managing Premium capacities](/power-bi/admin/service-premium-capacity-manage). 

> [!TIP]
> If you're using [!INCLUDE[prod_short](includes/prod_short.md)] online, you can also upload a report from within [!INCLUDE[prod_short](includes/prod_short.md)]. For more information, see [Work with Power BI Reports in [!INCLUDE [prod_short](includes/prod_short.md)] - Upload Reports](across-working-with-powerbi.md#upload).

## <a name="share"></a>Share reports with others

Once a report is in your workspace, you can share it with others in your organization.

To share a report, in a list reports, or in an open report, select **Share**. In the **Share report** pane, enter the full email addresses for individuals or distribution groups you want to share with. Follow the instructions on screen to complete the sharing. For more information, see [Share a dashboard or report](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

> [!NOTE]
> You must have  [Power BI Pro license](/power-bi/service-features-license-type), and the people you share with do too. The content must be in a workspace in a [Premium capacity](/power-bi/service-premium-what-is). For more information, see [Ways to share your work in Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).-->

## Voir aussi .

[Business Central et Power BI](admin-powerbi.md)  
[Télécharger des rapports](across-working-with-business-central-in-powerbi.md#upload-reports)
 
[!INCLUDE[footer-include](includes/footer-banner.md)]
