---
title: Configurer l’intégration de OneDrive avec Business Central local
description: Découvrez comment configurer Business Central sur site pour l’intégrer à OneDrive pour le travail ou l’école (anciennement connu sous le nom de OneDrive Entreprise).
author: jswymer
ms.topic: conceptual
ms.search.keywords: 'OneDrive, share, browser'
ms.date: 09/01/2024
ms.author: jswymer
ms.service: dynamics-365-op
ms.reviewer: jswymer
---
# <a name="configuring-onedrive-integration-with-business-central-on-premises"></a>Configurer l’intégration de OneDrive avec Business Central local

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Article explique comment configurer OneDrive pour le travail ou l’école (anciennement connu sous le nom de OneDrive Entreprise) intégration Business Central local. Contrairement à [!INCLUDE[prod_short](includes/prod_short.md)] Online, la connexion entre Business Central et OneDrive n’est pas configurée automatiquement. Si la connexion n’est pas configurée, les utilisateurs ne peuvent pas utiliser les fonctionnalités pour OneDrive.

Deux tâches doivent être effectuées pour configurer l’intégration de OneDrive.

- La première tâche consiste à enregistrer une application (app) sur votre client Microsoft Entra de votre plan Microsoft 365. L’application enregistrée est utilisée à des fins d’authentification. Cette tâche est généralement effectuée dans le portail Azure et dans le client web Business Central.
- La deuxième tâche consiste à établir la connexion à l’URL OneDrive et à activer les fonctionnalités OneDrive dans Business Central. Cette tâche est effectuée dans le client web Business Central. Ces tâches s’effectuent différemment pour la version 21 par rapport aux versions 19 et 20. La version 21 introduit une nouvelle **Configuration de OneDrive** qui remplace la **Configuration des connexions SharePoint**.  

> [!IMPORTANT]
> [!INCLUDE[prod_short](includes/prod_short.md)] en local ne peut être connecté qu’à un OneDrive hébergé par Microsoft dans le nuage. La connexion de [!INCLUDE[prod_short](includes/prod_short.md)] sur site au référentiel Mes sites du serveur SharePoint n’est pas prise en charge.

## <a name="register-an-app-in-microsoft-entra-id-for-onedrive-integration"></a><a name="registerapp"></a>Enregistrer une application dans Microsoft Entra ID pour l’intégration de OneDrive

Dans cette tâche, vous ajoutez une application enregistrée pour Business Central dans le locataire Microsoft Entra de votre plan Microsoft 365. Comme d′autres services Azure qui fonctionnent avec Business Central, OneDrive nécessite une application enregistrée dans Microsoft Entra ID. L’application enregistrée fournit des services d’authentification et d’autorisation entre Business Central et SharePoint, qui sont utilisés par OneDrive.

Pour connaître les étapes détaillées de réalisation de cette étape, consultez [Enregistrer une application dans Microsoft Entra ID](/dynamics365/business-central/dev-itpro/administration/register-app-azure#register-an-application-in-azure-active-directory) dans l’aide pour les développeurs et les professionnels de l’informatique.

Lorsque vous enregistrez l’application, tenez compte des points suivants :

- Si vous avez déjà enregistré une application dans le cadre d’une intégration avec un autre produit Microsoft, tel que Power BI, vous pouvez réutiliser cette application enregistrée. Dans ce cas, vous n’aurez qu’à définir les autorisations SharePoint pour l’application enregistrée existante.

- Assurez-vous de configurer l’application enregistrée avec les autorisations suivantes déléguées à l’API SharePoint :

    - AllSites.FullControl
    - User.ReadWrite.All
    
    Pour la 2e vague de lancement 2021 de Business Central (version 19), définissez plutôt les autorisations suivantes :
    
    - AllSites.Write
    - MyFiles.Write
    - User.Read.All 

- Si vous utilisez Business Central version 19 ou 20, copiez le **Code d’application (client)** et le **secret client** utilisé par l’application enregistrée. Vous aurez besoin de ces informations dans la tâche suivante.

## <a name="get-your-onedrive-url"></a><a name="url"></a>Obtenir votre URL OneDrive

[!INCLUDE[onedrive-url](includes/onedrive-url.md)]

## <a name="set-up-the-onedrive-connection-in-version-21-and-later"></a>Configurer la connexion OneDrive dans les versions 21 et supérieures

Utilisez cette procédure si vous utilisez la version Business Central de la 2e vague de lancement 2022 (version 21) ou une version ultérieure.

### <a name="prerequisites"></a>Conditions préalables

- Autorisation indirecte de modification et de suppression (imd) sur la table **Scénario de service de documents** au minimum

### <a name="run-onedrive-setup"></a>Exécuter la configuration de OneDrive

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configurer OneDrive**, puis choisissez le lien associé.
2. La première fois que vous exécutez la configuration assistée, vous verrez **Votre vie privée**. Lisez les informations de la page et, si vous êtes d’accord avec les conditions générales, sélectionnez **Accepter** pour continuer.
3. Sur la page **Configurer la gestion des fichiers**, vous avez le choix entre les options suivantes :

   [!INCLUDE[onedrive-feature-options](includes/onedrive-feature-options.md)]

4. Sur la page **Configurer Business Central**, entrez l’URl de OneDrive dans le champ **URL OneDrive**.

   [Comment rechercher mon URL OneDrive ?](#url)
5. Choisissez **Tester la connexion** et attendez les résultats.
   - Si le test réussit, sélectionnez **Terminé**, et vous êtes prêt.
   - Si le test échoue, vous recevez un message décrivant le problème. Généralement, le problème est lié à l’URL que vous avez fournie. Sélectionnez **OK** pour revenir à la page **Configurer Business Central** page, vérifiez l’URL et réessayez.
   - Si vous n’avez pas encore configuré l’application enregistrée Microsoft Entra ID, le guide **Configurer Microsoft Entra ID** s’ouvre.
6. Cela fait, l’avis de confidentialité pour l’intégration de OneDrive est accepté pour tous les utilisateurs. Si vous souhaitez le modifier afin que les utilisateurs soient obligés d'accepter ou de refuser pour eux-mêmes, accédez à la page **État des avis de confidentialité** et sélectionnez **Laisser l’utilisateur décider** pour l’intégration de OneDrive. Les utilisateurs seront alors invités à accepter ou non l’avis de confidentialité la première fois qu’ils utiliseront les fonctionnalités de OneDrive. Pour plus d’informations, consultez [Avis de confidentialité](privacy-notices-status.md).

## <a name="set-up-the-connection-in--version-19-and-20"></a>Configurer la connexion dans les versions 19 et 20 de [!INCLUDE[prod_short](includes/prod_short.md)]

Suivez cette procédure si vous utilisez la version Business Central de la 1re vague de lancement 2022 (version 20) ou celle de la 2e vague de lancement 2021 (version 19).
> [!IMPORTANT]
> En configurant cette fonctionnalité, vous activez également les fonctionnalités héritées qui envoient des fichiers à OneDrive.  
>
>* La fonction Ouvrir dans Excel copiera automatiquement le fichier Excel dans OneDrive, puis l’ouvrira dans Excel Online. 
>* L’exportation de tout rapport vers un fichier copiera automatiquement le fichier dans OneDrive, puis l’ouvrira dans Excel Online, Word Online ou OneDrive. 
>* D’autres fonctionnalités peuvent également s’ouvrir automatiquement dans OneDrive.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration de la connexion à Microsoft SharePoint**, puis choisissez le lien associé.
2. Dans le champ **Description**, saisissez une description de la connexion, telle que **OneDrive**.
3. Dans le champ **Dossier**, entrez **Business Central**.
4. Dans le champ **Emplacement**, entrez l’URL de votre OneDrive.

   [Comment rechercher mon URL OneDrive ?](#url)
5. Dans le champ **Code client**, entrez le code client de votre application enregistrée.
6. Dans le champ **Secret client**, entrez le secret client de votre application enregistrée. 

> [!IMPORTANT]
> La page **Configuration de la connexion SharePoint** est utilisée pour configurer plusieurs fonctionnalités héritées. La section **Général** configure la connexion à OneDrive, et la section **Documents partagés** redirige les fichiers vers SharePoint. La **Configuration de la connexion SharePoint** est obsolète et sera supprimée dans une prochaine version. Nous vous recommandons de ne pas configurer la section **Documents partagés**. Pour plus d’informations, consultez [Fonctionnalités obsolètes dans l’application de base](/dynamics365/business-central/dev-itpro/upgrade/deprecated-features-w1#microsoft-sharepoint-connection-setup).

## <a name="after-upgrade-to-version-21"></a>Après mise à niveau à la version 21

Lorsque vous effectuez une mise à niveau vers la version 21 ou ultérieure, la connexion existante à OneDrive qui est configurée sur la page **Configuration de la connexion SharePoint** fonctionne toujours. Mais comme la page **Configuration de la connexion SharePoint** sera supprimée dans la version 23, nous vous conseillons de passer à la nouvelle intégration de OneDrive, comme décrit dans la section suivante. Faire ce changement maintenant facilitera la tâche lorsque la **Configuration de la connexion SharePoint** sera finalement supprimé. De plus, cela vous permet d’utiliser le guide de configuration assistée **Configuration de OneDrive** pour gérer les fonctionnalités OneDrive accessibles aux utilisateurs.

## <a name="switching-from-legacy-sharepoint-to-new-onedrive-integration"></a>Passer de l’ancien SharePoint à la nouvelle intégration de OneDrive

Pour passer à la nouvelle intégration de OneDrive, vous exécutez le guide de configuration assistée **Configuration de OneDrive**, que vous pouvez ouvrir directement ou à partir de l’ancienne page **Configuration de la connexion SharePoint**. La configuration assistée **Configuration de OneDrive** vous guide tout au long de la transition, en vous fournissant des informations sur les modifications apportées en cours de route.

Avant de commencer le basculement, ou pendant, reportez-vous à la section suivante pour en savoir plus sur certains aspects et considérations sur le processus. 

### <a name="about-switching-to-the-new-onedrive-integration"></a><a name="onedrivesetupmigration"></a>À propos du passage à la nouvelle intégration de OneDrive

En plus de l’intégration de OneDrive, Business Central peut également s’intégrer à d’autres services, tels que Power BI et l’impression universelle. L’intégration avec ces autres services nécessite également une application enregistrée Microsoft Entra pour l’authentification. L’application Microsoft Entra utilisée par ces autres services est configurée dans la configuration assistée **Configurer vos comptes Microsoft Entra**. Lorsque vous abandonnez l’ancienne configuration de connexion SharePoint, la nouvelle configuration assistée **Configuration OneDrive** change votre intégration OneDrive pour utiliser également la configuration assistée **Configurer vos comptes Microsoft Entra**, ainsi, toutes les intégrations utilisent la même application Microsoft Entra.

Ce changement a des implications lors du passage à la nouvelle intégration OneDrive, selon qu’il existe déjà ou non une application Microsoft configurée dans la configuration assistée **Configurer vos comptes Microsoft Entra**. 

> [!IMPORTANT]
> Après être passé à la nouvelle configuration de OneDrive, vous ne pouvez plus utiliser la page **Configuration de la connexion SharePoint** pour configurer l’intégration de OneDrive.

#### <a name="how-the-changes-affect-the-integration"></a>Impact des modifications sur l’intégration

La configuration assistée **Configuration de OneDrive** utilisera toujours l’application configurée dans la configuration assistée **Configurer vos comptes Microsoft Entra**, s’il en existe une. Lorsque vous exécutez la configuration assistée **Configuration de OneDrive**, cela compare l’application configurée dans **Configurer vos comptes Microsoft Entra** avec votre application actuellement configurée dans **Configuration de la connexion SharePoint**.

> [!TIP]
> Sur la page **Configuration de la connexion SharePoint** et dans la configuration assistée **Configurer vos comptes Microsoft Entra**, l’application Microsoft Entra est identifiée par le **Code client**.

- Si l’application dans **Configurer vos comptes Microsoft Entra** est différente de l’application dans **Configuration de la connexion SharePoint**, l’intégration de OneDrive change pour utiliser l’application dans **Configurer vos comptes Microsoft Entra**.

   Dans **Configuration de OneDrive**, lors du changement, vous recevez un message semblable au texte suivant : 

  `The Microsoft Entra application used for authentication will be configured for all Business Central integrations. This means the client id will change to NNNNNNNNN-NNNN-NNNN-NNNN-NNNNNNNNNNNN, you may want to test it has the correct permissions.`

  `NNNNNNNNN-NNNN-NNNN-NNNN-NNNNNNNNNNNN` représente le code client de l’application dans **Configurer vos comptes Microsoft Entra** vers lequel l’intégration de OneDrive a été basculée. 

  > [!IMPORTANT]
  > Pour que la nouvelle intégration de OneDrive fonctionne après avoir effectué le changement, vous devez accorder l’autorisation de l’application à l’API SharePoint dans le portail Azure. Vous pouvez effectuer cette étape avant ou après avoir basculé vers la nouvelle configuration de OneDrive. Pour plus d’informations, consultez la section [Enregistrer une application dans Microsoft Entra ID pour l’intégration de OneDrive](#registerapp).

- Si l’application dans **Configurer vos comptes Microsoft Entra** est la même que l’application dans **Configuration de la connexion SharePoint**, l’intégration de OneDrive utilise la même application qu’auparavant, à l’exception de la configuration dans la configuration **Configurer vos comptes Microsoft Entra**.

   Dans **Configuration de OneDrive**, lors du changement, vous recevez un message semblable au texte suivant :

    `The Microsoft Entra application used for authentication will be configured for all Business Central integrations. This has already been configured with the same client id (aaaabbbb-0000-cccc-1111-dddd2222eeee).`

- Si aucune application n’est configurée dans la configuration **Configurer vos comptes Microsoft Entra**, l’intégration de OneDrive utilise la même application qu’auparavant.

   La configuration assistée **Configuration de OneDrive** copie la configuration de l’application dans la configuration **Configurer vos comptes Microsoft Entra** ; elle est donc utilisée pour d’autres intégrations qui pourraient être configurées ultérieurement.

   Dans **Configuration de OneDrive**, lors du changement, vous recevez un message semblable au texte suivant :

   `The Microsoft Entra application used for authentication will be configured for all Business Central integrations`.

### <a name="run-onedrive-setup-to-switch-to-the-new-onedrive-integration"></a>Exécuter la configuration de OneDrive pour passer à la nouvelle intégration de OneDrive

1. Ouvrez soit la page **Configuration de OneDrive**, soit la page **Configuration de la connexion SharePoint**.
2. Si vous utilisez la page **Configuration de la connexion SharePoint**, choisissez **Accéder à la nouvelle configuration de OneDrive** dans la notification en haut de la page.
3. Suivez le guide de configuration assistée **Configuration de OneDrive**.
4. Lorsque vous arrivez à la page **Configurer la gestion des fichiers**, choisissez l’une des options suivantes pour activer les fonctionnalités :

   [!INCLUDE[onedrive-feature-options](includes/onedrive-feature-options.md)]

5. La page **Configurer Business Central** affiche la même URL que celle utilisée par l’intégration OneDrive existante. Vous pouvez modifier l’URL si nécessaire.
6. Sélectionnez **Tester la connexion** et suivez les instructions.

   Si le test réussit, sélectionnez **Terminé**, et vous êtes prêt. Sinon, utilisez les messages de la page pour vous aider à résoudre le problème.

## <a name="see-also"></a>Voir aussi .
[Intégration de Business Central et OneDrive](across-onedrive-overview.md)  
[Ouverture des fichiers Business Central dans OneDrive](across-share-onedrive.md)  
[FAQ OneDrive](admin-onedrive-faq.md)

