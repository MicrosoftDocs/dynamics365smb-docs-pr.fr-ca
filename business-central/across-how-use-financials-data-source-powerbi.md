---
title: Création de rapports Power BI Desktop pour afficher des données Business Central | Microsoft Docs
description: Vous pouvez rendre vos données disponibles sous forme de source de données dans Power BI et créer des rapports puissants sur l'état de votre activité.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: business intelligence, KPI, Odata, Power App, SOAP, analysis
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: ee7e6a132f463f35206dd9ac4fe75ce1a41fd40d
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5780092"
---
# <a name="building-power-bi-reports-to-display-prod_long-data"></a>Création de rapports Power BI pour afficher des données [!INCLUDE [prod_long](includes/prod_long.md)]

Vous pouvez rendre vos données [!INCLUDE[prod_long](includes/prod_long.md)] disponibles sous forme de source de données dans Power BI Desktop et créer des rapports puissants sur l'état de votre activité.

Cet article aborde la prise en main de Power BI Desktop pour créer des rapports qui affichent des données [!INCLUDE[prod_long](includes/prod_long.md)].  Après avoir créé des rapports, vous pouvez les publier dans votre service Power BI ou les partager avec tous les utilisateurs de votre organisation. Une fois que ces rapports figurent dans le service Power BI, les utilisateurs configurés pour ce dernier peuvent alors afficher les rapports dans [!INCLUDE[prod_long](includes/prod_long.md)].

## <a name="get-ready"></a>Mise en route

- Inscrivez-vous au service Power BI.

    Si vous ne vous êtes pas encore inscrit, accédez à [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Au moment de votre inscription, utilisez votre adresse de courriel professionnelle et votre mot de passe.

- Téléchargez [Power BI Desktop](https://powerbi.microsoft.com/desktop/).

   Power BI Desktop est une application gratuite que vous installez sur votre ordinateur local. Pour plus d'informations, voir [Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data).

- Assurez-vous que les données souhaitées dans le rapport sont publiées en tant que service Web.
    
    Il existe de nombreux services Web publiés par défaut. Pour trouver facilement les services Web, il suffit de rechercher *services web* dans [!INCLUDE[prod_short](includes/prod_short.md)]. Sur la page **Services Web**, assurez-vous que le champ **Publier** est sélectionné. Cette tâche est généralement administrative.
    
    Pour plus d’informations sur la publication des services Web, voir [Publier un service Web](across-how-publish-web-service.md).

- Pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site, obtenez les informations suivantes :

    - L’URL OData pour [!INCLUDE[prod_short](includes/prod_short.md)]. En règle générale, cette URL a le format `http[s]://[computer]:[port]/[serverinstance]/ODataV4`, par exemple, `https://localhost:7048/BC160/ODataV4`. Si vous disposez d’un déploiement à plusieurs abonnés, incluez le client dans l’URL, par exemple, `https://localhost:7048/BC160/ODataV4?tenant=tenant1`.
    - Un nom d’utilisateur et une clé d’accès au service Web d’un compte [!INCLUDE[prod_short](includes/prod_short.md)].

      Pour obtenir des données depuis [!INCLUDE[prod_short](includes/prod_short.md)], Power BI utilise l’authentification de base. Vous aurez donc besoin d’un nom d’utilisateur et d’une clé d’accès au service Web pour vous connecter. Le compte peut être votre propre compte utilisateur ou votre organisation peut avoir un compte spécifique à cette fin.

- Téléchargez le thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)] (facultatif).

    Pour plus d’informations, consultez [Utilisation du thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)]](#theme) dans cet article.

## <a name="add-prod_short-as-a-data-source-in-power-bi-desktop"></a><a name="getdata"></a>Ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop

La première tâche dans le cadre de la création de rapports consiste à ajouter [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données dans Power BI Desktop. Une fois connecté, vous pouvez commencer à créer le rapport.

1. Lancez Power BI Desktop.
2. Sélectionnez **Extraire les données**.

    Si vous ne voyez pas **Extraire les données**, sélectionnez le menu **Fichier**, puis **Extraire les données**.
2. Sur la page **Extraire les données**, sélectionnez **Services en ligne**.
3. Dans le volet **Services en ligne**, effectuez l’une des étapes suivantes :

    1. Si vous vous connectez à [!INCLUDE [prod_short](includes/prod_short.md)] en ligne, choisissez **Dynamics 365 Business Central**, puis **Connecter**.
    2. Si vous vous connectez à [!INCLUDE [prod_short](includes/prod_short.md)] sur site, choisissez **Dynamics 365 Business Central (sur site)**, puis **Connecter**.

4. Power BI affiche un assistant qui va vous guider tout au long du processus de connexion, notamment à [!INCLUDE [prod_short](includes/prod_short.md)].

    Pour la version en ligne, choisissez **Se connecter**, puis le compte approprié. Utilisez le même compte que celui avec lequel vous vous êtes connecté(e) à [!INCLUDE [prod_short](includes/prod_short.md)].
    
    Pour la version sur site, entrez l’URL OData pour [!INCLUDE[prod_short](includes/prod_short.md)] et éventuellement le nom de la compagnie. Ensuite, à l’invite, entrez le nom d’utilisateur et le mot de passe du compte à utiliser pour vous connecter à [!INCLUDE[prod_short](includes/prod_short.md)]. Dans la zone **Mot de passe**, entrez la clé d’accès au service Web.

    > [!NOTE]  
    > Une fois que vous êtes connecté(e) à [!INCLUDE[prod_short](includes/prod_short.md)], vous n’êtes plus invité(e) à vous connecter.
    
5. Choisissez **Connecter** pour continuer.

    L'assistant Power BI affiche la liste des compagnies, des environnements et des sources de données Microsoft [!INCLUDE[prod_short](includes/prod_short.md)]. Ces sources de données représentent tous les services web que vous avez publiés à partir de [!INCLUDE [prod_short](includes/prod_short.md)].
6. Spécifiez les données à ajouter à votre modèle de données, puis sélectionnez le bouton **Charge**.
7. Répétez les étapes précédentes pour ajouter des informations [!INCLUDE [prod_short](includes/prod_short.md)] supplémentaires, ou d'autres données, à votre modèle de données Power BI.

Une fois les données chargées, elles s'affichent dans le volet de navigation à droite dans la page. À ce stade, vous êtes connecté(e) à vos données [!INCLUDE[prod_short](includes/prod_short.md)] et vous êtes prêt(e) à générer votre rapport Power BI.  

> [!TIP]
> Pour plus d’informations sur l’utilisation de Power BI Desktop, reportez-vous à [Mise en route avec Power BI Desktop](/power-bi/fundamentals/desktop-getting-started).

## <a name="creating-reports-to-display-data-associated-with-a-list"></a>Création de rapports pour afficher des données associées à une liste

Vous pouvez créer des rapports qui s’affichent dans un Récapitulatif d’une page de liste [!INCLUDE [prod_short](includes/prod_short.md)]. Les rapports peuvent contenir des données sur l’enregistrement sélectionné dans la liste. La création de ces rapports est similaire à celle d’autres rapports, à la différence près que vous devez effectuer quelques actions pour vous assurer que les rapports s’affichent comme prévu. Pour plus d’informations, consultez [Création de rapports Power BI pour afficher les données de la liste dans [!INCLUDE[prod_short](includes/prod_short.md)]](across-how-use-powerbi-reports-factbox.md).

## <a name="using-the-prod_short-report-theme-optional"></a><a name="theme"></a>Utilisation du thème du rapport [!INCLUDE [prod_short](includes/prod_short.md)] (facultatif)

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

Après avoir créé ou modifié un rapport, vous pouvez le publier dans votre service Power BI et le partager avec d’autres membres de votre organisation. Une fois publié, le rapport apparaît dans Power BI. Le rapport est également disponible pour sélection dans [!INCLUDE[prod_short](includes/prod_short.md)].

Pour publier un rapport, sélectionnez **Publier** sur l’onglet **Accueil** du ruban ou du menu **Fichier**. Si vous êtes connecté au service Power BI, le rapport est publié sur ce service. Sinon, vous êtes invité à vous connecter. 

## <a name="distribute-or-share-a-report"></a>Distribuer ou partager un rapport

Il existe plusieurs façons de transmettre des rapports à vos collègues et à d’autres personnes :

- Distribuez les rapports sous forme de fichiers .pbix.

    Les rapports sont stockés sur votre ordinateur sous forme de fichiers .pbix. Vous pouvez distribuer le fichier .pbix du rapport aux utilisateurs, comme n’importe quel autre fichier. Ensuite, les utilisateurs peuvent télécharger le fichier sur leur service Power BI. Voir [Télécharger des rapports à partir de fichiers](across-working-with-business-central-in-powerbi.md#upload).

    > [!NOTE]
    > Distribuer les rapports de cette manière signifie que l’actualisation des données des rapports sera effectuée individuellement par chaque utilisateur. Cette situation pourrait avoir un impact sur la performance [!INCLUDE[prod_short](includes/prod_short.md)].

- Partager un rapport à partir de votre service Power BI

    Si vous avez une licence Power BI Pro, vous pouvez partager le rapport avec d’autres, directement depuis votre service Power BI. Pour plus d’informations, consultez [Power BI - Partager un tableau de bord ou un rapport](/power-bi/collaborate-share/service-share-dashboards#share-a-dashboard-or-report).

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/configure-powerbi-excel-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Activation de vos données commerciales pour Power BI](admin-powerbi.md)  
[Veille économique](bi.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Finances](finance.md)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  


[!INCLUDE[footer-include](includes/footer-banner.md)]