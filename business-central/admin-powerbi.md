---
title: Activation de vos données commerciales pour Power BI| Microsoft Docs
description: Il est facile d'obtenir des informations exploitables, de la veille économique et des KPI de vos applications Business Central pour Power BI.
author: bmeier90
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.reviewer: edupont
ms.date: 04/01/2020
ms.author: bmeier
ms.openlocfilehash: 0625197f9feb0c12daa45b183973316df52b0672
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3186901"
---
# <a name="enabling-your-business-data-for-power-bi"></a>Activation de vos données commerciales pour Power BI

Il est facile d'obtenir des informations exploitables de vos données [!INCLUDE[prodshort](includes/prodshort.md)] grâce à [!INCLUDE[prodshort](includes/prodshort.md)] et aux applications pour Power BI. Power BI extrait vos données, puis génère un tableau de bord prêt à l'emploi et des rapports basés sur ces données.  

Vous devez disposer d'un compte valide avec [!INCLUDE[prodshort](includes/prodshort.md)] et avec Power BI. En outre, vous devez télécharger [Power BI Desktop](https://powerbi.microsoft.com/desktop/) si vous souhaitez créer vos propres rapports Power BI. Les applications Power BI nécessitent des autorisations vers les tables d'où sont extraites les données. Vous trouverez plus d'informations sur les besoins ci-dessous.  

> [!IMPORTANT]
> Les applications Power BI décrites dans cet article sont conçues pour utiliser Azure Active Directory comme mécanisme d'authentification sauf indication contraire. De plus, vous devez disposer d'une [Licence Power BI Pro](/power-bi/service-features-license-type) pour partager votre contenu, tout comme les personnes avec qui vous le partagez, ou le contenu doit être dans un espace de travail dans une [Capacité Premium](/power-bi/service-premium-what-is). Pour en savoir plus, consultez [Moyens de partager votre travail dans Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).

[!INCLUDE [prodlong](includes/prodlong.md)] a publié les applications suivantes pour Power BI:

- [!INCLUDE [prodlong](includes/prodlong.md)] - CRM  
- [!INCLUDE [prodlong](includes/prodlong.md)] - Finance  
- [!INCLUDE [prodlong](includes/prodlong.md)] - Sales  

## <a name="using-the-prodshort-dashboards-in-power-bi"></a>Utilisation des tableaux de bord [!INCLUDE [prodshort](includes/prodshort.md)] dans Power BI

Chaque application contient des rapports que vous pouvez afficher :

- Sélectionnez un visuel du tableau de bord pour afficher l'un des rapports sous-jacents.  
- Filtrez le rapport ou ajoutez les champs que vous souhaitez contrôler.  
- Épinglez cette vue personnalisée au tableau de bord pour continuer à effectuer le suivi.  
  Vous pouvez actualiser les données manuellement, et vous pouvez configurer un calendrier d'actualisation. Pour plus d'informations, voir [Configuration d'une actualisation programmée](/power-bi/refresh-scheduled-refresh).  

Les applications sont conçues pour fonctionner avec les données de toute compagnie de votre [!INCLUDE[prodshort](includes/prodshort.md)]. Lorsque vous installez l'application Power BI, spécifiez un ou plusieurs paramètres à connecter à votre [!INCLUDE [prodshort](includes/prodshort.md)].  

> [!NOTE]
> Vous pouvez également générer vos propres rapports et tableaux de bord dans Power BI selon vos données [!INCLUDE[d365fin](includes/d365fin_md.md)]. Pour plus d'informations, voir [Connexion de vos données métier à Power BI](across-how-use-financials-data-source-powerbi.md).  

### <a name="to-connect-your-data-in-power-bi"></a>Pour connecter vos données dans Power BI

1. Ouvrez votre navigateur, accédez à https://powerbi.microsoft.com et connectez-vous à votre compte.
2. Sélectionnez **Extraire les données** en bas du volet de navigation gauche.  

    ![Naviguer pour obtenir des données](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-get-data.png)

    Vous pouvez également démarrer depuis [!INCLUDE [prodshort](includes/prodshort.md)]. Depuis votre page d'accueil, accédez à **Sélection de rapport** dans la section Power BI. Sélectionnez **Service** ou **Mon organisation** dans le ruban. Lorsque l'une de ces actions est sélectionnée, vous arrivez dans la galerie Organisation de Power BI ou dans Microsoft AppSource, qui sera également filtrée pour afficher uniquement les applications associées à [!INCLUDE[prodshort](includes/prodshort.md)].

3. Dans la zone **Services**, sélectionnez **Extraire**. Une page s'ouvre et affiche **AppSource** et **Applications pour Power BI**.  

<!--    ![Choose apps from online services that you use.](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-online-services-get.png)-->
4. Sélectionnez **Applications** dans l'onglet **Applications pour Power BI** et choisissez l'application **Microsoft Dynamics 365 Business Central** à utiliser, puis cliquez sur **Obtenir maintenant**.  
<!--    ![Select Dynamics 365 Business Central and select Get it now](./media/across-how-to-connect-powerbi-d365-content-packspowerbi-dynamics365-for-financials-get-it-now.png)/-->
5. Lorsque vous y êtes invité(e), entrez le nom de l'environnement et de la compagnie dans votre application [!INCLUDE[prodshort](includes/prodshort.md)] à laquelle vous souhaitez vous connecter. Si vous n'avez pas créé plusieurs environnements, entrez **Production**. Pour le paramètre Compagnie, assurez-vous d'entrer le nom et non le nom d'affichage. Vous pourrez trouver le nom de la compagnie dans la page **Compagnies** de votre instance [!INCLUDE[prodshort](includes/prodshort.md)].  

    > [!NOTE]
    > Si vous vous connectez à [!INCLUDE [prodshort](includes/prodshort.md)] sur site, vous devez spécifier le paramètre *URL du service Web*. Trouvez ceci sur la page **Services Web** dans [!INCLUDE [prodshort](includes/prodshort.md)]. Votre instance [!INCLUDE [server](includes/server.md)] doit être configurée pour l'authentification de base et vous devez spécifier un utilisateur et la clé d'accès Web de cet utilisateur comme mot de passe. Dans l'exemple suivant, remplacez *myserver :7048* par votre nom [!INCLUDE [server](includes/server.md)] et *CRONUS%20US* par le nom de votre compagnie.  
    > ```https://myserver:7048/BC140/ODataV4/Company('CRONUS%20US')/```

6. Une fois connecté(e), un tableau de bord et des rapports sont ajoutés à votre espace de travail Power BI. Une fois terminé, les mosaïques affichent les données de votre compagnie [!INCLUDE[prodshort](includes/prodshort.md)].

    ![Sélectionnez Dynamics 365 Business Central, puis Obtenir maintenant.](./media/across-how-to-connect-powerbi-d365-content-packs/powerbi-workspace-dashboard-report-dataset.png)

### <a name="what-now"></a>Et ensuite ?

- Cliquez sur [poser une question dans la zone Q&R](/power-bi/service-q-and-a-tips) en haut du tableau de bord.
- [Modifiez les mosaïques](/power-bi/service-dashboard-edit-tile) du tableau de bord.  
- [Sélectionnez une mosaïque](/power-bi/service-dashboard-tiles) pour ouvrir le rapport sous-jacent.  
- Par défaut, votre ensemble de données n'est pas programmé pour être actualisé. Vous pouvez modifier le calendrier d'actualisation ou essayer de l'actualiser à la demande à l'aide de **Actualiser maintenant**. Pour plus d'informations, voir [Configuration d'une actualisation programmée](/power-bi/refresh-scheduled-refresh).

## <a name="power-bi-in-prodshort"></a>Power BI dans [!INCLUDE [prodshort](includes/prodshort.md)]

Votre page d'accueil dans [!INCLUDE [prodshort](includes/prodshort.md)] peut inclure un élément de contrôle Power BI pouvant être configuré pour afficher les rapports Power BI sur votre page d'accueil.

> [!IMPORTANT]
> Vous devez disposer d'un compte valide avec [!INCLUDE [prodshort](includes/prodshort.md)] et avec Power BI. De plus, si vous souhaitez modifier des rapports, vous devez télécharger Power BI Desktop. Pour plus d'informations, voir [Utilisation de Business Central en tant que source de données Power BI](across-how-use-financials-data-source-powerbi.md).  

### <a name="on-first-login"></a>À la première ouverture de session

Quand vous vous connectez pour la première fois à [!INCLUDE [prodshort](includes/prodshort.md)], vous remarquerez une partie Power BI vide sur votre page d'accueil. Pour voir les rapports, vous devez d’abord vous connecter à Power BI en sélectionnant le lien *Mise en route avec Power BI*.

[!INCLUDE [prodshort](includes/prodshort.md)], puis communique avec le service Power BI pour déterminer si vous avez un compte Power BI valide. Une fois votre licence vérifiée, les rapports Power BI par défaut s'affichent sur votre page d'accueil.

### <a name="selecting-power-bi-reports"></a>Sélections de rapports Power BI

Le contrôle Power BI sur votre page d'accueil peut afficher tout rapport Power BI. Pour afficher un rapport existant, choisissez l'action **Sélectionner un rapport** dans la liste déroulante des commandes Power BI.  

La page de sélection des rapports affiche une liste de tous les rapports Power BI auxquels vous avez accès. Cette liste est extraite de votre espace de travail Power BI. Activez chaque rapport que vous souhaitez afficher sur la page d'accueil, puis choisissez OK. Vous serez redirigé(e) vers votre page d'accueil et le dernier rapport que vous avez activé apparaîtra. A l'aide de la liste déroulante des commandes, utilisez les commandes Précédent et Suivant pour naviguer entre les rapports.  

### <a name="get-reports"></a>Obtenir des rapports

Si vous ne voyez aucun rapport sur la page Sélectionner des rapports, ou vous ne voyez pas le rapport souhaité. Vous pouvez choisir d’obtenir des rapports à partir de *Mon organisation* ou de *Services*.
Choisissez *Mon organisation* pour accéder aux services Power BI où vous pouvez afficher les rapports au sein de votre organisation pour lesquels vous avez le droit de les visualiser et de les ajouter à votre espace de travail. Choisissez *Services* pour accéder à Microsoft AppSource où vous pouvez installer les applications Power BI.  

Vous pouvez également choisir de créer de nouveaux rapports Power BI. Une fois ces rapports publiés dans votre espace de travail Power BI, ils apparaîtront sur cette page.  

### <a name="managing-reports"></a>Gestion des rapports

Dans la section Power BI de votre page d’accueil, vous pouvez choisir l'action **Gérer le rapport** dans la liste déroulante des commandes afin que vous puissiez modifier le rapport sélectionné dans le tableau de bord.  

Des modifications peuvent être apportées au rapport, puis sauvegardées.  Toute modification apportée au rapport sera modifiée pour tout utilisateur avec lequel ce rapport est partagé puisque vous modifiez le rapport enregistré dans le service Power BI.  

Une fois vos modifications terminées, sélectionnez Enregistrer. S'il s'agit d'un rapport partagé, vous pouvez sélectionner Enregistrer sous pour éviter d'apporter cette modification à tous les utilisateurs.
Revenez au tableau de bord et le rapport mis à jour apparaîtra. Si vous avez effectué une commande Enregistrer sous, vous devez ouvrir la page de sélection des rapports et activer le nouveau rapport.

### <a name="uploading-reports"></a>Téléchargement des rapports

Vous pouvez télécharger de nouveaux rapports Power BI et les partager avec tous les utilisateurs de votre [!INCLUDE [prodshort](includes/prodshort.md)]. Les rapports sont partagés au sein de chaque compagnie dans [!INCLUDE [prodshort](includes/prodshort.md)].  

Pour télécharger un rapport, sélectionnez l'action **Télécharger le rapport** dans la liste déroulante des commandes. Vous pouvez ensuite télécharger un fichier .pbix qui définit les rapports que vous souhaitez partager. Vous pouvez modifier le nom par défaut du fichier.  

Une fois le rapport téléchargé dans votre espace de travail Power BI, il est automatiquement chargé dans les espaces de travail Power BI de tous les autres utilisateurs de cette compagnie lors de leur prochaine connexion à [!INCLUDE [prodshort](includes/prodshort.md)].

## <a name="system-requirements"></a>Configuration système requise

Pour importer les données [!INCLUDE[prodshort](includes/prodshort.md)] dans Power BI, vous devez disposer des autorisations sur les services Web utilisés pour récupérer les données. Les services Web obligatoires pour chaque application Power BI incluent :

### <a name="microsoft-dynamics-365-business-central--crm"></a>Microsoft Dynamics 365 Business Central – CRM

- Opportunités ventes
- Informations sur le modèle Excel Afficher Compagnie
- Étiquettes de rapport Power BI

### <a name="microsoft-dynamics-365-business-central--finance"></a>Microsoft Dynamics 365 Business Central – Finance

- PowerBIFinance
- Informations sur le modèle Excel Afficher Compagnie
- Étiquettes de rapport Power BI

### <a name="microsoft-dynamics-365-business-central---sales"></a>Microsoft Dynamics 365 Business Central - Sales

- Ventes d'articles par client
- Tableau de bord ventes
- Modèle Excel Afficher Compagnie
- Étiquettes de rapport Power BI

> [!NOTE]
> [!INCLUDE [prodshort](includes/prodshort.md)] sur site utilise les mêmes points de terminaison de service Web que [!INCLUDE [prodshort](includes/prodshort.md)] en ligne.

## <a name="web-services"></a>Services web

Pour trouver facilement les services Web, il suffit de rechercher *services web* dans [!INCLUDE[prodshort](includes/prodshort.md)]. Sur la page **Services Web**, assurez-vous que le champ **Publier** est sélectionné pour les services Web répertoriés ci-dessus.

## <a name="troubleshooting"></a>Dépannage

Le tableau de bord Power BI s'appuie sur les services Web publiés qui sont répertoriés ci-dessus. Il affichera les données de la compagnie de démonstration ou de votre propre compagnie si vous importez les données de votre solution financière actuelle. Toutefois, si une erreur se produit, cette section fournit une solution de rechange pour les problèmes les plus courants.  

### <a name="you-do-not-have-a-power-bi-account"></a>Vous n'avez pas de compte Power BI

Aucun compte Power BI n'a été créé. Afin d'avoir un compte Power BI valide, vous devez avoir une licence et vous devez avoir déjà ouvert une session dans Power BI, pour pouvoir créer votre espace de travail Power BI.  

### <a name="message-there-are-no-enabled-reports-choose-select-report-to-see-a-list-of-reports-that-you-can-display"></a>Message : Aucun rapport n'est activé. Choisissez Sélectionner un rapport pour afficher la liste des rapports disponibles.

Ce message apparaîtra si le rapport par défaut n’a pas été déployé sur votre espace de travail Power BI ou s'il a été déployé mais que l’actualisation n’a pas réussi. Si cela se produit, accédez au rapport dans votre espace de travail Power BI, sélectionnez **Ensemble de données**, **Paramètres**, puis mettez à jour les informations d'identification manuellement. Une fois le jeu de données actualisé, revenez dans Business Central et sélectionnez manuellement le rapport dans la page **Sélectionner des rapports**.

### <a name="you-need-a-power-bi-pro-license-to-install-the-prodshort-app-in-power-bi"></a>Vous devez disposer d'une licence Power BI Pro pour installer l'application [!INCLUDE [prodshort](includes/prodshort.md)] dans Power BI

Vous devez disposer d'une [Licence Power BI Pro](/power-bi/service-features-license-type) pour partager votre contenu, tout comme les personnes avec qui vous le partagez, ou le contenu doit être dans un espace de travail dans une [Capacité Premium](/power-bi/service-premium-what-is). Pour en savoir plus, consultez [Moyens de partager votre travail dans Power BI](/power-bi/service-how-to-collaborate-distribute-dashboards-reports).  

### <a name="parameter-validation-failed-please-make-sure-all-parameters-are-valid"></a>« Échec de la validation des paramètres, assurez-vous que tous les paramètres sont valides »

Cette erreur indique qu'un ou plusieurs paramètres ne sont pas valides.

- Le paramètre d'environnement spécifié ne correspond à aucun environnement de production ou sandbox [!INCLUDE [prodshort](includes/prodshort.md)] existant.
- Le paramètre de compagnie spécifié ne correspond à aucune compagnie [!INCLUDE [prodshort](includes/prodshort.md)] existante. Vérifiez le nom de la compagnie dans la page **Compagnies** dans [!INCLUDE [prodshort](includes/prodshort.md)].
- Si vous vous connectez à [!INCLUDE [prodshort](includes/prodshort.md)] sur site. vous avez entré une URL non valide. Vous pouvez vérifier l’URL sur la page **Services Web** dans [!INCLUDE [prodshort](includes/prodshort.md)]  
- Un port n'est pas ouvert pour permettre à la demande de passer par votre pare-feu.

### <a name="cannot-sign-in"></a>Connexion impossible

Si vous obtenez un message d'erreur de type échec d'ouverture de session après avoir utilisé vos informations d'identification utilisateur [!INCLUDE [prodshort](includes/prodshort.md)] pour vous connecter, vous rencontrez peut-être l'un des problèmes suivants :

- Le compte que vous utilisez n'est pas doté des autorisations nécessaires pour récupérer les données [!INCLUDE [prodshort](includes/prodshort.md)] de votre compte. Vérifiez que vous disposez des autorisations pour les données requises dans [!INCLUDE [prodshort](includes/prodshort.md)]et essayez à nouveau.
- Vous avez sélectionné un type d'authentification autre que Basique si vous vous connectez à [!INCLUDE [prodshort](includes/prodshort.md)] sur site.
- Vous n'avez pas entré de nom d'utilisateur ni de mot de passe valide.

### <a name="incorrect-company-name"></a>Nom de compagnie incorrect

Une erreur courante consiste à entrer le nom d'affichage de la compagnie au lieu de son nom. Pour trouver le nom de la compagnie, cherchez dans **Compagnies**. Utilisez ensuite le champ **Nom** au moment de saisir le nom de votre compagnie.

### <a name="the-key-didnt-match-any-rows-in-the-table"></a>La clé ne correspond à aucune ligne de la table

Si vous entrez un nom de compagnie non valide pendant le processus de connexion, le message d'erreur suivant « La clé ne correspond à aucune ligne de la table » peut s'afficher. Indiquez le nom de compagnie correct, puis reconnectez-vous.

### <a name="historical-data-appears-to-be-missing"></a>Les données historiques semblent manquer

Une fois que l'application Power BI est installée et que vos données apparaissent dans Power BI, vous remarquerez peut-être que toutes vos données ne s'affichent pas. Les ensembles de données sont filtrés pour ne renvoyer que les 365 derniers jours de données. Cette option par défaut est en place pour accélérer les rapports.  

### <a name="i-only-see-data-for-a-single-company"></a>Je ne vois que des données pour une seule compagnie

L'application Power BI affichera uniquement les données de la compagnie [!INCLUDE [prodshort](includes/prodshort.md)] qui a été définie lorsque l'application Power BI a été installée. Les données provenant d'autres compagnies peuvent être ajoutées aux rapports en ajoutant de nouvelles requêtes utilisant différentes compagnies en tant que source de données.  

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

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
