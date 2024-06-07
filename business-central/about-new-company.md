---
title: Créer des compagnies en utilisant le guide de configuration assistée
description: 'Il est facile de créer une nouvelle compagnie vide dans Business Central. Un guide de configuration assistée vous aide à l’aide de procédures, et vous pouvez importer vos données métier.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 03/08/2024
ms.custom: bap-template
ms.search.keywords: 'company, setup wizard'
ms.search.form: '1803, 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017'
ms.service: dynamics-365-business-central
---
# Créer des compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)]

Dans [!INCLUDE[prod_short](includes/prod_short.md)], le conteneur pour les données métier appartenant à une unité fonctionnelle ou une entité juridique sont désignés en tant que *compagnie*. Lorsque vous vous connectez à [!INCLUDE[prod_short](includes/prod_short.md)], une compagnie de démonstration et une compagnie vide, *Ma compagnie*, vous sont attribuées. Le basculement entre compagnies est facile : accédez simplement à **Mes paramètres** et passez à l'autre compagnie. Vous pouvez également créer de nouvelles compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)], selon les besoins de votre activité.  

> [!NOTE]
> Pour créer une compagnie, vous devez être affecté à l’ensemble d’autorisations **Super**.

Lorsque vous créez une compagnie, un guide de configuration assistée vous permet de mettre en place les fondements. Ensuite, vous pouvez importer des données à partir de votre système hérité ou d’une autre compagnie dans [!INCLUDE[prod_short](includes/prod_short.md)].  

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## Choisir le bon modèle

Si vous décidez d’ajouter une compagnie à votre [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez utiliser le guide de configuration assistée **Créer une nouvelle compagnie** pour démarrer. Le guide de configuration est disponible à partir de la page **Compagnies** et depuis la zone de recherche dans le champ **Compagnie** de la page **Mes configurations**.  

Le guide de configuration propose trois modèles et une option vierge :

- **Évaluation — Exemples de données**  
    Créez une compagnie qui est similaire à la compagnie de démonstration avec des exemples de données et des données de configuration. Ce type de compagnie est à votre disposition sans passer à une période d’essai de 30 jours, ce qui est le cas des autres types.  
- **Évaluation avancée – Exemples de données complets** Créez une compagnie avec la portée des fonctionnalités avancées, qui dispose de tout ce dont vous avez besoin pour évaluer le produit pour les compagnies dotées de processus avancés. Ce type de compagnie est à votre disposition sans passer à une période d’essai de 30 jours, ce qui est le cas des autres types.
- **Production — Données de configuration uniquement**  
    Créez une compagnie similaire à **Ma Compagnie**, avec des données de configuration telles qu’un plan comptable, des modes de paiement et des définitions de rapports financiers, mais sans exemples de données. Vous pouvez utiliser cette compagnie pour une version d’évaluation de 30 jours.
- **Créer — Pas de données**  
    Créez une compagnie vide sans données de configuration. Vous pouvez utiliser cette compagnie pour une version d’évaluation de 30 jours.  

Si vous souhaitez démarrer facilement avec une nouvelle compagnie, sélectionnez **Production - Données de configuration uniquement**, puis importez vos propres données métier, telles que les clients, les articles et les fournisseurs. Choisissez le modèle **Nouveau** si vous souhaitez tout redéfinir à zéro. Dans ce cas, vous pouvez utiliser le guide de configuration assistée **Configuration de la compagnie** qui vous aidera à commencer par des données de configuration essentielles.  

> [!NOTE]  
> Lorsque vous créez une compagnie, cela prend quelques minutes avant de pouvoir y accéder dans [!INCLUDE[prod_short](includes/prod_short.md)]. L'état de configuration sur la page **Compagnies** s'affiche lorsque la nouvelle compagnie est prête pour vous. Ensuite, vous pouvez basculer vers la nouvelle compagnie en utilisant **Mes paramètres**.  

Au cours de votre période d’évaluation de 30 jours, vous pouvez créer autant de compagnies que vous voulez, mais elles ne sont disponibles que durant cette période d’évaluation. Pour plus d'informations, contactez votre partenaire [!INCLUDE[prod_short](includes/prod_short.md)]. Voir aussi l’article [FAQ sur la version d’essai Dynamics 365 Business Central](trial-faq.md).  

Votre administrateur peut en savoir plus sur les essais et les abonnements [ici](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions).  

## Copier une compagnie

Sur la page **Compagnies**, vous pouvez utiliser l'action **Copier** pour créer une deuxième compagnie sur la base du contenu d’une compagnie existante. La copie d’une compagnie est utile, par exemple, lorsque vous souhaitez tester une compagnie sans perturber les données de production.

> [!Important]
> N’utilisez pas l’action Copier pour effectuer une sauvegarde d’une compagnie. Pour effectuer une sauvegarde, commencez par exporter la base de données sous forme de fichier .bacpac. Pour plus d'informations, voir [Exportation de bases de données](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-database-export) dans Aide dédiée au développement et à l'administration.

[!INCLUDE [email-copy-company](includes/email-copy-company.md)]

[!INCLUDE [dataverse-copy-company](includes/dataverse-copy-company.md)]

## Configurer la compagnie

Lorsque vous vous connectez à une nouvelle compagnie, le guide de configuration assistée **Configuration de la compagnie** vous permet de démarrer. Le guide demande des informations sur votre activité, telles que l’adresse, les coordonnées bancaires et le mode d’évaluation du coût de l’inventaire. Ces informations constituent la base de nombreuses zones de [!INCLUDE[prod_short](includes/prod_short.md)] vous n’aurez donc pas à les configurer manuellement.  

Par exemple, [!INCLUDE [prod_short](includes/prod_short.md)] inclut l’adresse de votre compagnie dans les factures et autres documents et vos coordonnées bancaires dans les paiements. Le mode d’évaluation du coût est utilisé pour calculer les prix, ainsi que pour l’évaluation de l'inventaire.  

Une fois les bases en place, vous pouvez configurer les zones de base restantes. Maintenant, vous êtes prêt à ajouter des données métier, telles que les clients et les fournisseurs. Pour plus d’informations, consultez [Configurer [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md).  

## Compagnies et environnements

[!INCLUDE [company_environment](includes/company_environment.md)]

Pour plus d'informations, voir [Passer à une autre compagnie ou un autre environnement](ui-organization-switch.md). Pour plus d’informations sur les environnements, voir [Comprendre l’infrastructure de Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology) (en anglais uniquement).  

## Changer le nom d’une compagnie

Une fois une compagnie créée, vous ne pouvez pas changer son nom. Mais vous pouvez changer son **Nom d’affichage**, qui est le texte qui s’affiche pour la compagnie dans toute l’application.  

> [!TIP]
> Vous pouvez renommer une compagnie si vous utilisez [!INCLUDE[prod_short](includes/prod_short.md)] sur site.

## Ajouter Contoso Coffee

L’application Contoso Coffee fournit des données de démonstration pour vous aider à explorer les fonctionnalités avancées de [!INCLUDE [prod_short](includes/prod_short.md)]. Trouvez l’application dans AppSource et installez-la dans une compagnie vide, par exemple une compagnie dans un environnement sandbox. Pour plus d’informations, voir [Présentation des données de démonstration Contoso Coffee](contoso-coffee/contoso-coffee-intro.md).  

## Voir aussi .

[Personnalisation de Business Central](ui-customizing-overview.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Comprendre l’infrastructure de Business Central Online (en anglais uniquement)](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
