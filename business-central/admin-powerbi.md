---
title: "Introduction à Business\_Central et Power BI"
description: "Obtenez une vue d’ensemble de l’utilisation de Power BI pour obtenir des informations, des informations décisionnelles et des indicateurs de performance clés à partir de vos données Business\_Central."
author: jswymer
ms.topic: overview
ms.search.keywords: 'account schedule, analysis, reporting, financial report, business intelligence, KPI'
ms.search.form: '6316, 6317'
ms.reviewer: jswymer
ms.date: 09/28/2023
ms.author: jswymer
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="introduction-to--and-power-bi"></a>Présentation de [!INCLUDE[prod_short](includes/prod_short.md)] et de Power BI

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Obtenir des informations sur vos données [!INCLUDE[prod_short](includes/prod_short.md)] est facile avec [Power BI](https://powerbi.microsoft.com), système de visualisation de données de Microsoft. Power BI récupère les données [!INCLUDE[prod_short](includes/prod_short.md)] vous permettant de créer des tableaux de bord et des rapports basés sur ces données. Power BI fournit une alternative flexible aux rapports intégrés dans [!INCLUDE[prod_short](includes/prod_short.md)], vous permettant d’explorer et de personnaliser la visualisation, et même de fusionner les données de différentes compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)]. Certains rapports Power BI peuvent également être intégrés à Business Central et affichés sans quitter le système. Les tableaux de bord plus complexes sont mieux expérimentés depuis le site Web Power BI.

![Power BI et Business Central.](media/power-bi-intro.png)

## <a name="what-you-can-do-with-power-bi-and-"></a>Ce que vous pouvez faire avec Power BI et [!INCLUDE[prod_short](includes/prod_short.md)]

Il existe différentes fonctionnalités pour utiliser [!INCLUDE[prod_short](includes/prod_short.md)] et Power BI. Vous pouvez faire certaines choses depuis Power BI, tandis que vous pouvez en faire d’autres depuis [!INCLUDE[prod_short](includes/prod_short.md)]. De plus, certaines fonctionnalités ne sont disponibles qu’avec [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, pas sur site. Le tableau suivant vous donne une vue d’ensemble.

|Fonctionnalité|Désignation|En ligne|On-premises|En savoir plus|
|-------|-----------|--------------|-----------|----------------|
|Afficher les données [!INCLUDE[prod_short](includes/prod_short.md)] dans Power BI|Vous pouvez consulter vos données depuis [!INCLUDE[prod_short](includes/prod_short.md)] dans les rapports dans Power BI. [!INCLUDE[prod_short](includes/prod_short.md)] en ligne comprend des rapports Power BI prédéfinis. Ou votre organisation a peut-être mis à votre disposition certains rapports personnalisés.|![Fonctionne en ligne.](media/check.png)|![Fonctionne en local](media/check.png)|[Ici...](across-working-with-business-central-in-powerbi.md)|
|Afficher les rapports Power BI dans le client [!INCLUDE[prod_short](includes/prod_short.md)].| Les rapports Power BI qui affichent les données [!INCLUDE[prod_short](includes/prod_short.md)] peuvent être intégrés directement dans les pages [!INCLUDE[prod_short](includes/prod_short.md)] des composants. Vous pouvez changer de partie pour afficher tout rapport mis à votre disposition. |![fonctionne en ligne.](media/check.png)|![Fonctionne en local](media/check.png)<sup>[*](#onprem)</sup>|[Ici...](across-working-with-powerbi.md).|
|Créez des rapports et des tableaux de bord dans Power BI qui affichent les données [!INCLUDE[prod_short](includes/prod_short.md)].|Utilisez Power BI Desktop pour créer vos propres rapports et tableaux de bord. Vous pouvez publier les rapports vers votre propre service Power BI ou les partager avec tous les utilisateurs de votre organisation.|![Fonctionne en ligne.](media/check.png)|![fonctionne en local](media/check.png)|[Ici...](across-how-use-financials-data-source-powerbi.md)|
|Applications [!INCLUDE[prod_short](includes/prod_short.md)] dans Power BI| [!INCLUDE[prod_short](includes/prod_short.md)] publie trois applications pour Power BI sur Microsoft AppSource. Ces applications créent des rapports et des tableaux de bord détaillés dans votre service Power BI pour visualiser les données [!INCLUDE[prod_short](includes/prod_short.md)]. Les applications disponibles incluent : <ul><li>[!INCLUDE [prod_long](includes/prod_long.md)] - CRM </li><li>[!INCLUDE [prod_long](includes/prod_long.md)] - Finance </li><li>[!INCLUDE [prod_long](includes/prod_long.md)] - Sales </li></ul>  |![Fonctionne en ligne.](media/check.png)||[Ici...](across-powerbi-business-central-apps.md)|
|Utiliser les données [!INCLUDE [prod_short](includes/prod_short.md)] dans les datamarts et les flux de données|Depuis juillet 2022, vous pouvez utiliser le connecteur [!INCLUDE [prod_short](includes/prod_short.md)] dans Power Query Online pour les flux de données que vous partagez dans différents rapports et tableaux de bord.|![fonctionne en ligne.](media/check.png)||[Ici...](across-powerbi-business-central-apps.md)|

<a name="onprem"><sup>*</sup></a>Cette fonctionnalité nécessite une application enregistrée pour Business Central dans Microsoft Azure. Pour plus d’informations, consultez [Enregistrer Business Central en local dans Microsoft Entra ID pour l’intégration à d’autres services](/dynamics365/business-central/dev-itpro/administration/register-app-azure).

## <a name="get-ready-to-use-power-bi"></a>Prise en main de Power BI

Il y a quelques tâches à effectuer avant de pouvoir commencer à utiliser Power BI avec [!INCLUDE[prod_short](includes/prod_short.md)]. <!-- Some of the tasks are typically only done by administrators or super users.--> Les tâches dépendront de votre rôle dans votre organisation et de ce que vous voulez faire avec Power BI :

- En tant qu’*utilisateur professionnel*, vous voulez voir les rapports Power BI dans Power BI Service ou dans Business Central.
- En tant qu’*administrateur*, vous êtes responsable de la gestion des paramètres à l’échelle de l’organisation qui contrôlent la façon dont Business Central et Power BI fonctionnent.
- En tant que *créateur de rapport*, vous voulez créer sur mesure des rapports Power BI que vous pouvez partager avec d’autres utilisateurs.

|Tâche|Utilisateur professionnel|Administrateur|Créateur de rapport|Plus d'informations|
|----|-------------|-------------|-----------------------|----------------|
|Obtenez un compte Power BI.|![encore une autre coche.](media/check.png)|![c’est une coche](media/check.png)|![encore une coche](media/check.png)|Accédez à [https://powerbi.microsoft.com](https://powerbi.microsoft.com). Pour vous inscrire à un compte, utilisez votre adresse de courriel professionnelle et votre mot de passe. <br /><br/>L’inscription nécessite que vous ayez une licence, mais dans la plupart des cas, vous devriez déjà avoir une licence gratuite. Pour en savoir plus, voir [Licences Power BI](admin-powerbi-setup.md#license).|
|Obtenir Power BI Desktop|||![encore une coche.](media/check.png)|Pour télécharger, accédez à [Power BI Desktop](https://powerbi.microsoft.com/desktop/). Pour plus d’informations, reportez-vous à la rubrique [Obtenir Power BI Desktop](/power-bi/fundamentals/desktop-get-the-desktop).
|Exposer les données Business Central à Power BI||![c’est une coche.](media/check.png)|![encore une coche](media/check.png)|[Exposer des données via des pages API ou des services Web OData](admin-powerbi-setup.md#exposedata)
|Activer l’intégration de Power BI<br />(en local uniquement)||![c’est une coche.](media/check.png)||[Configurer Business Central en local pour l’intégration Power BI](admin-powerbi-setup.md#setup)|

## <a name="track-your-business-kpis-with-power-bi-metrics"></a>Suivre vos KPI métier avec les mesures Power BI

Si vous utilisez Power BI sur les données [!INCLUDE[prod_short](includes/prod_short.md)], il est facile de suivre les KPI ou les mesures qui sont importants pour vous. 

Avec les mesures dans Power BI, vous pouvez organiser vos propres mesures et les suivre par rapport à des objectifs métier clés, dans un seul volet. Cette fonctionnalité améliore la culture des données en favorisant la responsabilité, l’alignement et la visibilité pour les équipes et les initiatives au sein des organisations. 

Suivez ce processus en quatre étapes pour configurer les mesures Power BI :

1. Créez un tableau de bord dans le service Power BI. En savoir plus sur [Créer des tableaux de bord dans Power BI](/power-bi/create-reports/service-goals-create).  
2. Ajoutez les _mesures_ que vous souhaitez suivre en vous connectant à votre rapport Power BI sur la télémétrie. En savoir plus sur [Créer des mesures connectées](/power-bi/create-reports/service-goals-create-connected).  
3. Pour ajouter des alertes, définissez des règles d’état pour vos mesures. Pour en savoir plus, voir [Créer des règles d'état automatisées pour les mesures](/power-bi/create-reports/service-metrics-status-rules).  

    Cette étape automatise les mises à jour d’état en fonction des règles qui régissent cette mesure. Les règles déclenchent des modifications en fonction de la valeur, du pourcentage de l’objectif atteint, des conditions de date ou d’une combinaison des trois, ce qui rend les règles aussi versatiles que possible. Pour les mesures connectées, ces règles d’état sont actualisées à chaque actualisation des données de votre tableau de bord.
4. Enfin, suivez les mesures pour recevoir des alertes dans Teams ou par courriel. Pour en savoir plus, rendez-vous sur [Suivre vos mesures](/power-bi/create-reports/service-metrics-follow).  

Pour plus d’informations sur les mesures Power BI, voir [Bien démarrer avec les mesures dans Power BI](/power-bi/create-reports/service-goals-introduction).

> [!NOTE]
> À partir de la 2e vague de lancement 2023 de Business Central, il est possible d’intégrer des tableaux de bord à partir de mesures Power BI dans [!INCLUDE[prod_short](includes/prod_short.md)].

## <a name="next-steps"></a>Étapes suivantes

- Si vous êtes un administrateur qui doit configurer Power BI dans [!INCLUDE[prod_short](includes/prod_short.md)], accédez à [Activation de l’intégration de Power BI](admin-powerbi-setup.md).
- Si Power BI est déjà configuré et vous souhaitez essayer les fonctionnalités, accédez à [Utiliser les rapports Power BI dans Business Central](across-working-with-powerbi.md).

## <a name="see-also"></a>Voir aussi .

[Veille économique](bi.md)  
[Configurer [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power BI](across-how-use-financials-data-source-powerbi.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] comme source de données Power Apps](across-how-use-financials-data-source-powerapps.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)] dans Power Automate](across-how-use-financials-data-source-flow.md)  
[Documentation Power BI](/power-bi/)  
[Qu’est-ce que Power BI ?](/power-bi/fundamentals/power-bi-overview)  
[Démarrage rapide : Se connecter aux données dans Power BI Desktop](/power-bi/desktop-quickstart-connect-to-data)  
[Présentation des datamarts](/power-bi/transform-model/datamarts/datamarts-overview)  
[Introduction aux flux de données et à la préparation des données en libre-service](/power-bi/transform-model/dataflows/dataflows-introduction-self-service)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
