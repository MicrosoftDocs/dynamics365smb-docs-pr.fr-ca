---
title: Utilisation des rapports Power BI dans Business Central| Microsoft Docs
description: Il est facile d'obtenir des informations exploitables, de la veille économique et des KPI de vos applications Business Central pour Power BI.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: get-started-article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: account schedule, analysis, reporting, financial report, business intelligence, KPI
ms.date: 10/01/2020
ms.author: jswymer
ms.openlocfilehash: 8cf8946d8b9792c7fb557969257380d0b48d0d83
ms.sourcegitcommit: a9d48272ce61e5d512a30417412b5363e56abf30
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/04/2021
ms.locfileid: "5492958"
---
# <a name="working-with-power-bi-reports-in-prod_short"></a>Utilisation des rapports Power BI dans [!INCLUDE [prod_short](includes/prod_short.md)]

Dans cet article, vous découvrirez quelques notions de base sur l’affichage des rapports Power BI dans [!INCLUDE [prod_short](includes/prod_short.md)].

## <a name="overview"></a>Aperçu

Les rapports Power BI vous donnent un aperçu de votre [!INCLUDE[prod_short](includes/prod_short.md)]. Diverses pages dans [!INCLUDE [prod_short](includes/prod_short.md)] incluent une partie rapports Power BI qui peut afficher des rapports Power BI. Le tableau de bord est une page type où vous verrez une partie de rapports Power BI. Certaines pages de liste, comme **Articles**, comprennent également une partie Power BI.

[!INCLUDE [prod_short](includes/prod_short.md)] utilise le service Power BI. Les rapports à afficher dans [!INCLUDE [prod_short](includes/prod_short.md)] sont stockés dans un service Power BI. Dans [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez changer le rapport affiché dans la partie Power BI par tout rapport Power BI disponible dans votre service Power BI. La première fois que vous vous connectez à [!INCLUDE [prod_short](includes/prod_short.md)], et jusqu’à ce que vous vous connectiez à un service Power BI, les pièces restent vides, comme indiqué ici :

![Partie Power BI dans Business Central](./media/power-bi-part.png)

## <a name="prerequisites"></a>Conditions préalables

Si vous utilisez [!INCLUDE[prod_short](includes/prod_short.md)] sur site, il doit être activé pour l’intégration de Power BI. Cette tâche est généralement effectuée par un administrateur. Pour plus d’informations, consultez [Configurer [!INCLUDE[prod_short](includes/prod_short.md)] sur site pour l’intégration Power BI](admin-powerbi-setup.md#setup).

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] en ligne est déjà configuré pour s’intégrer à Power BI.

## <a name="get-ready"></a>Mise en route

Inscrivez-vous au service Power BI. Si vous ne vous êtes pas encore inscrit, accédez à [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Au moment de votre inscription, utilisez votre adresse de courriel professionnelle et votre mot de passe.

## <a name="connect-to-power-bi---one-time-only"></a><a name="connect"></a>Se connecter à Power BI - une fois seulement

Lorsque vous vous connectez pour la première fois [!INCLUDE [prod_short](includes/prod_short.md)], vous pourriez voir une partie Power BI vide sur une page, comme indiqué dans la figure précédente. La première chose à faire est de vous connecter à votre compte Power BI. Une fois connecté, vous pouvez voir les rapports. Vous ne devez effectuer cette étape qu’une seule fois.

Pour vous connecter à Power BI, sélectionnez le lien **Prise en main de Power BI** dans la partie **Rapports Power BI**. 

Pendant le processus de connexion, [!INCLUDE [prod_short](includes/prod_short.md)] communique avec le service Power BI pour déterminer si vous avez un compte et une licence Power BI valides. Une fois votre licence vérifiée, le rapport Power BI par défaut s’affiche sur la page. Si aucun rapport n’est affiché, vous pouvez sélectionner un rapport dans la partie.

> [!TIP]
> Avec [!INCLUDE [prod_short](includes/prod_short.md)] en ligne, cette étape téléchargera automatiquement les rapports Power BI par défaut utilisés dans [!INCLUDE [prod_short](includes/prod_short.md)] vers votre espace de travail Power BI.

##### <a name="from-prod_short-on-premises"></a>Depuis [!INCLUDE [prod_short](includes/prod_short.md)] sur site

Se connecter à Power BI depuis [!INCLUDE [prod_short](includes/prod_short.md)] est identique à la version en ligne. Cependant, vous pouvez être invité sur la page **AUTORISATIONS DE SERVICE AZURE ACTIVE DIRECTORY** pour accorder l’accès aux services Power BI. Pour accorder l’accès, sélectionnez **Autoriser les services Azure**, puis **Accepter**.

Une fois connecté, vous pouvez sélectionner un rapport dans la partie Power BI sur les pages.

## <a name="show-power-bi-reports-on-list-pages"></a>Afficher les rapports Power BI sur les pages de liste

[!INCLUDE[prod_long](includes/prod_long.md)] comprend un Récapitulatif Power BI sur plusieurs pages de liste clé. Ce Récapitulatif fournit des informations supplémentaires sur les données de la liste. Lorsque vous vous déplacez entre les lignes de la liste, le rapport est mis à jour et filtré pour l'écriture sélectionnée. Si vous ne voyez pas cette partie, dans la barre d’action, sélectionnez **Actions** > **Afficher** > **Afficher/Masquer les rapports Power BI**. Pour plus d’informations, consultez [Création de rapports Power BI pour afficher les données de la liste dans [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="select-power-bi-reports"></a>Sélectionner les rapports Power BI

Une partie Power BI sur une page peut afficher n’importe quel rapport Power BI à votre disposition. Pour basculer vers un autre rapport, choisissez l’action **Sélectionner un rapport** depuis la liste déroulante des commandes en haut de la partie.  

La page **Sélection de rapports Power BI** affiche une liste de tous les rapports Power BI auxquels vous avez accès. Cette liste est extraite de votre espace de travail Power BI. Sélectionnez la zone **Activer** pour chaque rapport que vous souhaitez afficher sur la page d’accueil, puis choisissez **OK**. Vous serez redirigé(e) vers la page et le dernier rapport que vous avez activé apparaîtra. A l’aide de la liste déroulante des commandes, utilisez les commandes **Précédent** et **Suivant** pour naviguer entre les rapports.  

## <a name="get-reports"></a>Obtenir des rapports

Si vous ne voyez aucun rapport sur la page **Sélection de rapports Power BI**, ou si vous ne voyez pas le rapport souhaité, choisissez **Obtenir des rapports**. Cette action vous permet de rechercher des rapports à partir de deux emplacements : *Mon organisation* ou *Prestations de service*.

- Choisissez **Mon organisation** pour accéder aux services Power BI. À partir de là, vous pouvez afficher les rapports au sein de votre organisation que vous avez le droit de consulter. Vous pouvez ensuite les ajouter à votre espace de travail.
- Choisissez **Services** pour accéder à Microsoft AppSource où vous pouvez installer les applications Power BI.  

> [!TIP]
> Si vous avez Power BI Desktop, vous pouvez également créer des rapports Power BI. Puis, une fois ces rapports publiés dans votre espace de travail Power BI, ils apparaîtront sur la page **Sélection de rapports Power BI**.  

## <a name="manage-and-modify-reports"></a>Gérer et modifier les rapports

Vous pouvez apporter des modifications à un rapport dans la partie Power BI. Les modifications que vous apportez seront ensuite publiées dans le service Power BI. Si le rapport est partagé avec d’autres utilisateurs, ils verront également les modifications, sauf si vous enregistrez les modifications dans un nouveau rapport.

Pour modifier un rapport, choisissez l’action **Gérer un rapport** dans la liste déroulante des commandes dans la partie Power BI. Ensuite, commencez à apporter des modifications. Une fois les modifications terminées, sélectionnez **Fichier** > **Enregistrer**. S’il s’agit d’un rapport partagé et si vous ne souhaitez pas effectuer la modification pour tous les utilisateurs, sélectionnez **Enregistrer sous** pour éviter de faire ce changement pour tous les utilisateurs.

Lorsque vous revenez au tableau de bord, le rapport mis à jour apparaîtra. Si vous avez utilisé **Enregistrer sous**, vous devrez choisir **Sélectionner un rapport**, puis activez le nouveau rapport pour l’afficher.

> [!NOTE]
> Cette fonctionnalité n’est pas disponible avec [!INCLUDE [prod_short](includes/prod_short.md)] sur site.

## <a name="upload-reports"></a><a name="upload"></a>Télécharger des rapports

Les rapports Power BI peuvent être distribués entre les utilisateurs sous forme de fichiers .pbix. Si vous avez des fichiers .pbix, vous pouvez les télécharger et les partager avec tous les utilisateurs de [!INCLUDE [prod_short](includes/prod_short.md)]. Les rapports sont partagés au sein de chaque compagnie dans [!INCLUDE [prod_short](includes/prod_short.md)].  

Pour télécharger un rapport, sélectionnez l’action **Télécharger le rapport** dans la liste déroulante des commandes sur la partie **Rapports Power BI**. Puis localisez le fichier .pbix qui définit les rapports que vous souhaitez partager. Vous pouvez modifier le nom par défaut du fichier.  

Une fois le rapport téléchargé sur votre espace de travail Power BI, il se télécharge automatiquement sur les espaces de travail Power BI des autres utilisateurs.

> [!NOTE]
> Le téléchargement d’un rapport nécessite que vous disposiez d’autorisations de SUPER utilisateur dans [!INCLUDE[prod_short](includes/prod_short.md)]. De plus, vous ne pouvez pas télécharger de rapports avec [!INCLUDE [prod_short](includes/prod_short.md)] sur site. Avec la version sur site, vous téléchargez des rapports directement sur votre espace de travail Power BI. Pour plus d’informations, reportez-vous à [Utilisation des données[!INCLUDE [prod_short](includes/prod_short.md)] dans Power BI](across-working-with-business-central-in-powerbi.md).

## <a name="fixing-problems"></a>Résolution des problèmes

Toutefois, si une erreur se produit, cette section fournit une solution de rechange pour les problèmes les plus courants.  

### <a name="you-dont-have-a-power-bi-account"></a>Vous n’avez pas de compte Power BI

Aucun compte Power BI n’a été créé. Pour obtenir un compte Power BI valide, vous devez avoir une licence et vous devez avoir déjà ouvert une session dans Power BI, pour créer votre espace de travail Power BI.   

### <a name="message-there-are-no-enabled-reports-choose-select-report-to-see-a-list-of-reports-that-you-can-display"></a>Message : Aucun rapport n'est activé. Choisissez Sélectionner un rapport pour afficher la liste des rapports disponibles.

Ce message apparaît si le rapport par défaut n’a pas pu être déployé sur votre espace de travail Power BI. Ou l’état a été déployé, mais n’a pas été actualisé avec succès. Accédez au rapport dans votre espace de travail Power BI, sélectionnez **Ensemble de données**, **Paramètres**, puis mettez à jour les informations d’identification manuellement. Une fois le jeu de données actualisé, revenez dans [!INCLUDE[prod_short](includes/prod_short.md)] et sélectionnez manuellement le rapport dans la page **Sélectionner des rapports**.


## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Business Central et Power BI](admin-powerbi.md)  
[Création de rapports Power BI pour afficher les données [!INCLUDE [prod_long](includes/prod_long.md)]](across-how-use-financials-data-source-powerbi.md)  
[Vue d’ensemble Architecture et composante d’intégration Power BI pour [!INCLUDE[prod_short](includes/prod_short.md)]](admin-powerbi-overview.md)  
[Utilisation avec les données [!INCLUDE [prod_short](includes/prod_short.md)] dans Power BI](across-working-with-business-central-in-powerbi.md)  
[Power BI pour les consommateurs](/power-bi/consumer/end-user-consumer)  
[Le « nouveau look » du service Power BI](/power-bi/service-new-look)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Documentation Power BI](/power-bi/)  
[Veille économique](bi.md)  
[Mise en route](product-get-started.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]