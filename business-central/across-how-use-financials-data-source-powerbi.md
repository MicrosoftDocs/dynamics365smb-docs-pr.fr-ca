---
title: "Création de rapports dans Power BI Desktop pour afficher des données Business\_Central"
description: Vous pouvez rendre vos données disponibles sous forme de source de données dans Power BI et créer des rapports puissants sur l'état de votre activité.
author: jswymer
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'business intelligence, KPI, Odata, Power App, SOAP, analysis'
ms.date: 06/12/2024
ms.author: jswymer
ms.service: dynamics-365-business-central
ms.reviewer: jswymer
---

# <a name="building-power-bi-reports-to-display--data"></a>Création de rapports Power BI pour afficher des données [!INCLUDE [prod_long](includes/prod_long.md)]

Vous pouvez rendre vos données [!INCLUDE[prod_long](includes/prod_long.md)] disponibles sous forme de source de données dans Power BI Desktop et créer des rapports puissants sur l’état de votre activité.

Cet article décrit la prise en main de Power BI Desktop pour créer des rapports qui affichent des données [!INCLUDE[prod_long](includes/prod_long.md)]. Après avoir créé des rapports, vous pouvez les publier dans votre service Power BI ou les partager avec tous les utilisateurs de votre organisation. Lorsque les rapports figurent dans le service Power BI, les utilisateurs configurés pour ce dernier peuvent afficher les rapports dans [!INCLUDE[prod_long](includes/prod_long.md)].

## <a name="get-ready"></a>Mise en route

- Inscrivez-vous au service Power BI.

  Si vous ne vous êtes pas inscrit, accédez à [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Au moment de votre inscription, utilisez votre adresse de courriel professionnelle et votre mot de passe.

- Téléchargez [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

  Power BI Desktop est une application gratuite que vous installez sur votre ordinateur local. Pour plus d'informations, voir [Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Veillez à ce que les données que vous souhaitez dans le rapport soit disponible en tant que page API ou publiées en tant que service Web. Pour plus d’informations, consultez [Exposer les données via des pages API ou des services Web OData](admin-powerbi-setup.md#exposedata).

<!--- For [!INCLUDE[prod_short](includes/prod_short.md)] on-premises, get the following information:

  - The OData URL for [!INCLUDE[prod_short](includes/prod_short.md)].
  
    Typically, this URL has the format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, for example, `https://localhost:7048/BC190/ODataV4`. If you have a multi-tenant deployment, include the tenant in the URL, for example, `https://localhost:7048/BC190/ODataV4?tenant=tenant1`.
  - A user name and web service access key of a [!INCLUDE[prod_short](includes/prod_short.md)] account.

    To get data from [!INCLUDE[prod_short](includes/prod_short.md)], Power BI uses basic authentication. So, you'll need a user name and web service access key to connect. The account might be your own user account, or your organization may have specific account for this purpose.-->

- Téléchargez le thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)] (facultatif).

  Pour plus d’informations, consultez [Utiliser le thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)]](#theme) dans cet article.

[!INCLUDE[note-multicompany-reports](includes/note-multicompany-reports.md)]

## <a name="add--as-a-data-source-in-power-bi-desktop"></a><a name="getdata"></a>Ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop

La première tâche dans le cadre de la création de rapports consiste à ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop. Une fois connecté, vous pouvez commencer à créer le rapport.

1. Lancez Power BI Desktop.
2. Sélectionnez **Extraire les données**.

    Si vous ne voyez pas **Extraire les données**, sélectionnez le menu **Fichier**, puis **Extraire les données**.
3. Sur la page **Extraire les données**, sélectionnez **Services en ligne**.
4. Dans le volet **Services en ligne**, effectuez l’une des étapes suivantes :

    - Pour se connecter à [!INCLUDE [prod_short](includes/prod_short.md)] en ligne, sélectionnez **Dynamics 365 Business Central**, puis **Connecter**.
    <!--- To connect to  [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, select **Dynamics 365 Business Central (on-premises)**, then **Connect**.-->

5. Connectez-vous à [!INCLUDE [prod_short](includes/prod_short.md)] (une fois seulement).

    Si vous ne vous êtes jamais connecté à [!INCLUDE [prod_short](includes/prod_short.md)] depuis Power BI Desktop, vous êtes invité à vous connecter.

    - Pour [!INCLUDE [prod_short](includes/prod_short.md)] en ligne, sélectionnez **Se connecter**, puis choisissez le compte pertinent. Utilisez le même compte que celui avec lequel vous vous êtes connecté(e) à [!INCLUDE [prod_short](includes/prod_short.md)]. Lorsque vous avez terminé, sélectionnez **Connecter**.

    <!--- For [!INCLUDE [prod_short](includes/prod_short.md)] on-premises, first enter the OData URL for [!INCLUDE[prod_short](includes/prod_short.md)], then select **OK**. When prompted, enter the user name and password of the account to use for connecting to [!INCLUDE[prod_short](includes/prod_short.md)]. In the **Password** box, enter the web service access key. When done, select **Connect**.-->

    > [!NOTE]  
    > Une fois connecté(e) à [!INCLUDE[prod_short](includes/prod_short.md)], vous n’êtes plus invité(e) à vous connecter. [Comment modifier ou effacer le compte que j’utilise actuellement pour me connecter à Business Central depuis Power BI Desktop ?](/dynamics365/business-central/power-bi-faq?tabs=designer#perms)

6. Une fois connecté, Power BI contacte le [!INCLUDE [prod_short](includes/prod_short.md)] service. Le **Navigateur** affiche les sources de données disponibles pour les rapports de construction. Sélectionnez un dossier pour le développer et afficher les sources de données disponibles.

   Ces sources de données représentent tous les services web et les pages API qui sont publiés pour [!INCLUDE [prod_short](includes/prod_short.md)], regroupés par environnements et compagnies. Avec [!INCLUDE [prod_short](includes/prod_short.md)] Online, **Navigateur** a la structure suivante :

    - **Nom de l’environnement**
      - **Nom de la compagnie**
        - **API avancées**

          Ce dossier répertorie les pages API avancées publiées par Microsoft, comme les [API d’automatisation de Business Central](/dynamics365/business-central/dev-itpro/administration/itpro-introduction-to-automation-apis) et [pages d’API personnalisées pour Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-develop-custom-api). Les pages d’API personnalisées sont en outre regroupées dans des dossiers selon propriétés [APIPublisher](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apipublisher-property)/[APIGroup](/dynamics365/business-central/dev-itpro/developer/properties/devenv-apigroup-property) du code source de la page API.

        - **API standards v2.0**

          Ce dossier répertorie les pages API exposées par l’[API Business Central V2.0](/dynamics365/business-central/dev-itpro/api-reference/v2.0/).

        - **Services Web \(hérités)**

          Ce dossier répertorie les pages, les unités de code et les requêtes publiées en tant que services Web dans Business Central.

    <!--
    > [!NOTE]
    > The structure for Business Central on-premises is different because it doesn't support API pages.-->

7. Sélectionnez la source ou les sources de données que vous souhaitez ajouter à votre modèle de données, puis sélectionnez le bouton **Charge**.
8. Si vous souhaitez ajouter ultérieurement d’autres données Business Central, vous pouvez répéter les étapes précédentes.

Une fois les données chargées, elles s'affichent dans le volet de navigation à droite dans la page. À ce stade, vous êtes connecté à vos données [!INCLUDE[prod_short](includes/prod_short.md)] et vous pouvez commencer à générer votre rapport Power BI.  

> [!TIP]
> Pour plus d’informations sur l’utilisation de Power BI Desktop, reportez-vous à [Mise en route avec Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## <a name="creating-accessible-reports"></a>Créer des rapports accessibles

Il est important de rendre vos rapports utilisables par autant de personnes que possible. Essayez de concevoir des rapports qui ne nécessitent aucune adaptation particulière pour répondre aux besoins spécifiques des différents utilisateurs. Assurez-vous que la conception permet aux utilisateurs de tirer parti des technologies d′assistance standard, comme les lecteurs d′écran. Power BI comprend diverses fonctionnalités d′accessibilité, des outils et des consignes pour vous aider à atteindre cet objectif. Pour plus d′informations, [Conception de rapports Power BI pour l′accessibilité](/power-bi/create-reports/desktop-accessibility-creating-reports) dans la documentation Power BI.

## <a name="creating-reports-to-display-data-associated-with-a-list"></a>Création de rapports pour afficher des données associées à une liste

Vous pouvez créer des rapports qui s’affichent dans un Récapitulatif d’une page de liste [!INCLUDE [prod_short](includes/prod_short.md)]. Les rapports peuvent contenir des données sur l’enregistrement sélectionné dans la liste. La création de ces rapports est similaire à celle d’autres rapports, à la différence près que vous devez effectuer quelques actions pour vous assurer que les rapports s’affichent comme prévu. Pour plus d’informations, consultez [Création de rapports Power BI pour afficher les données de la liste dans [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="using-the--report-theme-optional"></a><a name="theme"></a>Utilisation du thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)] (facultatif)

Avant de générer votre rapport, il est préférable de télécharger et d’importer le fichier de thème [!INCLUDE [prod_short](includes/prod_short.md)]. Le fichier de thème crée une palette de couleurs afin de pouvoir établir des rapports avec le même style de couleur que les applications [!INCLUDE [prod_short](includes/prod_short.md)] sans avoir à définir des couleurs personnalisées pour chaque visuel.

> [!NOTE]
> Cette tâche est facultative. Vous pouvez toujours créer vos rapports, puis télécharger et appliquer le modèle de style ultérieurement.

### <a name="download-the-theme"></a>Télécharger le thème

Le fichier de thème est disponible sous forme de fichier json sur la galerie de thèmes de la communauté Microsoft Power BI. Pour télécharger le fichier de thème, procédez comme suit :

1. Accédez à la [galerie de thèmes de la communauté Microsoft Microsoft Power BI pour Microsoft Dynamics 365 Business Central](https://community.powerbi.com/t5/Themes-Gallery/Microsoft-Dynamics-365-Business-Central/m-p/385875).
2. Sélectionnez la pièce jointe de téléchargement **Microsoft Dynamics Business Central.json**.

### <a name="import-the-theme-on-a-report"></a>Importer le thème dans un rapport

Après avoir téléchargé le thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez l’importer dans vos rapports. Pour importer le thème, sélectionnez **Afficher** > **Thèmes** > **Parcourir les thèmes**. Pour plus d’informations, consultez [Power BI Desktop - Importer des thèmes de rapport personnalisés](/power-bi/create-reports/desktop-report-themes#import-custom-report-theme-files).

## <a name="publish-reports"></a>Publier des rapports

Après avoir créé ou modifié un rapport, vous pouvez le publier dans votre service Power BI et le partager avec d’autres membres de votre organisation. Après avoir publié un rapport, il est disponible dans Power BI. Le rapport est également disponible pour sélection dans [!INCLUDE[prod_short](includes/prod_short.md)].

Pour publier un rapport, sélectionnez **Publier** sur l’onglet **Accueil** du ruban ou du menu **Fichier**. Si vous êtes connecté au service Power BI, le rapport est publié sur ce service. Sinon, vous êtes invité à vous connecter. 

## <a name="distribute-or-share-a-report"></a>Distribuer ou partager un rapport

Il existe plusieurs façons de transmettre des rapports à vos collègues et à d’autres personnes :

- Distribuez les rapports sous forme de fichiers .pbix.

    Les rapports sont stockés sur votre ordinateur sous forme de fichiers .pbix. Vous pouvez distribuer le fichier .pbix du rapport aux utilisateurs, comme n’importe quel autre fichier. Ensuite, les utilisateurs peuvent télécharger le fichier sur leur service Power BI. Voir [Télécharger des rapports à partir de fichiers](across-working-with-powerbi.md#upload).

    > [!NOTE]
    > Distribuer les rapports de cette manière signifie que l’actualisation des données des rapports sera effectuée individuellement par chaque utilisateur. Cette situation pourrait avoir un impact sur la performance [!INCLUDE[prod_short](includes/prod_short.md)].

- Partager un rapport à partir de votre service Power BI

    Si vous avez une licence Power BI Pro, vous pouvez partager le rapport avec d’autres, directement depuis votre service Power BI. Pour plus d’informations, consultez [Power BI - Partager un tableau de bord ou un rapport](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

## <a name="how-to-develop-cross-company-or-cross-environment-power-bi-reports"></a>Comment développer des rapports Power BI intercompagnies ou interenvironnements

Le [!INCLUDE[prod_short](includes/prod_short.md)] points de terminaison de l’API portent tous le préfixe `https://api.businesscentral.dynamics.com/v2.0/<environment_name>/api/v2.0` suivi de `/companies({company_id})/accounts({id})` (ici nous utilisons le `accounts` API à titre d’illustration). Vous pouvez utiliser cette structure pour créer des requêtes PowerQuery qui chargent des données pour plusieurs compagnies ou plusieurs environnements si l’utilisateur qui lit les données peut y accéder.

Pour configurer une requête afin de charger des données pour plusieurs compagnies, procédez comme suit :

1. Prenez la requête PowerQuery qui charge les données d’une seule compagnie. Convertissez-le en fonction Power Query personnalisée qui prend le code de la compagnie (ou peut-être le nom de l’environnement) comme paramètres. Pour en savoir plus, rendez-vous sur [Utiliser la personnalisation Power Query les fonctions](/power-query/custom-function).
1. Utilisez désormais la nouvelle fonction personnalisée dans une requête PowerQuery, où vous mappez la fonction sur une liste de compagnies, puis fusionnez les ensembles de données à l’aide de la fonction [Table.Combine](/powerquery-m/table-combine) Power Query.

## <a name="fixing-problems"></a>Résolution des problèmes

### <a name="cant-insert-a-record-current-connection-intent-is-read-only-error-connecting-to-custom-api-page"></a>« Impossible d’insérer un enregistrement. L’intention de connexion actuelle est en lecture seule. » erreur de connexion à la page API personnalisée

> **S’APPLIQUE À :** Business Central Online

À compter de février 2022, les nouveaux rapports qui utilisent les données [!INCLUDE [prod_short](includes/prod_short.md)] se connecteront par défaut à une réplique en lecture seule de la base de données [!INCLUDE [prod_short](includes/prod_short.md)]. Dans de rares cas, selon la conception de la page, vous obtenez une erreur lorsque vous essayez de vous connecter et d’obtenir des données à partir de la page.

1. Lancez Power BI Desktop.
2. Sur le ruban, cliquez sur **Obtenir les données** > **Services en ligne**.
3. Dans le volet **Services en ligne**, sélectionnez **Dynamics 365 Business Central**, puis **Connecter**.
4. Dans la fenêtre **Navigateur**, sélectionnez le point de terminaison d’API à partir duquel vous souhaitez charger les données.
5. Le volet d’aperçu affiche l’erreur suivante :

   *Dynamics365BusinessCentral : Échec de la requête : le serveur distant a renvoyé une erreur : (400) Requête incorrecte. (Impossible d’insérer un enregistrement. L’intention de connexion actuelle est en lecture seule. CorrelationId : [...]) ».*

6. Sélectionner **Transformer les données** à la place de **Charger** comme vous le feriez normalement.
7. Dans **l’éditeur Power Query**, sélectionnez **Éditeur avancé** du ruban.
8. Dans la ligne qui commence par **Source =**, remplacez le texte suivant :

   ```
   Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, null)
   ```

   par :

   ```
   Dynamics365BusinessCentral.ApiContentsWithOptions(null, null, null, [UseReadOnlyReplica = false])
   ```

9. Cliquez sur **Terminé**.
10. Sélectionnez **Fermer et appliquer** à partir du ruban pour enregistrer les modifications et fermer l’éditeur Power Query.

## <a name="see-also"></a>Voir aussi

[Activation de vos données commerciales pour Power BI](admin-powerbi-setup.md)  
[Veille économique](bi.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finances](finance.md)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
