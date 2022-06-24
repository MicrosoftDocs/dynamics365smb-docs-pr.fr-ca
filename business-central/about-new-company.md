---
title: Créer des compagnies en utilisant le guide de configuration assistée
description: Il est facile de créer une nouvelle compagnie vide dans Business Central. Un guide de configuration assistée vous aide à l'aide de procédures, et vous pouvez importer les données métier existantes.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: company, setup wizard
ms.search.form: 1803, 9020, 9022, 9026, 9027, 9030, 9000, 9009, 9004, 9005, 9024, 9006, 9007, 9010, 9016, 9017
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 843de26d836e8cf16f1f4f79d4ec697c481eebc0
ms.sourcegitcommit: 0bb9473a2563211bc0c02ebfd837bba1b2e9ad3f
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/25/2022
ms.locfileid: "8805240"
---
# <a name="create-new-companies-in-prod_short"></a>Créer des compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)]

Dans [!INCLUDE[prod_short](includes/prod_short.md)], le conteneur pour les données métier appartenant à une unité fonctionnelle ou une entité juridique sont désignés en tant que *compagnie*. Lorsque vous vous connectez à [!INCLUDE[prod_short](includes/prod_short.md)], une compagnie de démonstration et une compagnie vide, *Ma compagnie*, vous sont attribuées. Le basculement entre compagnies est facile : accédez simplement à **Mes paramètres** et passez à l'autre compagnie. Vous pouvez également créer de nouvelles compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)], selon les besoins de votre activité.  

Lorsque vous créez une compagnie, un guide de configuration assistée vous permet de mettre en place les fondements. Ensuite, vous pouvez importer des données appropriées à partir de votre système hérité ou d'une autre compagnie dans [!INCLUDE[prod_short](includes/prod_short.md)].  

[!INCLUDE [about-ui-learn](includes/about-ui-learn.md)]

## <a name="choose-the-right-template"></a>Choisir le bon modèle

Si vous décidez d'ajouter une compagnie à votre [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez utiliser le guide de configuration assistée **Créer une nouvelle compagnie** pour démarrer. L'assistant de configuration est disponible à partir de la page **Compagnies** et depuis la zone de recherche dans le champ **Compagnie** sur la page **Mes paramètres**.  

L’assistant de configuration propose deux modèles et une option vierge :

- **Évaluation - Exemples de données**  
    Cela crée une compagnie qui est similaire à la compagnie de démonstration avec des exemples de données et des données de configuration. Ce type de compagnie est à votre disposition sans passer à une période d’essai de 30 jours, ce qui est le cas des autres types.  
- **Production - Données de configuration uniquement**  
    Cela crée une compagnie qui est similaire à **Ma compagnie** avec des données de configuration, mais sans exemples de données. Vous pourrez utiliser cette compagnie pendant une période d’évaluation de 30 jours.  
- **Créer nouveau - Aucune donnée**  
    Cela crée une compagnie vide sans données de configuration. Vous pourrez utiliser cette compagnie pendant une période d’évaluation de 30 jours.  

Si vous souhaitez démarrer facilement avec une nouvelle compagnie, sélectionnez **Production - Données de configuration uniquement**, puis importez vos propres données métier, telles que les clients, les articles et les fournisseurs. Choisissez le modèle **Nouveau** si vous souhaitez tout redéfinir à zéro. Dans ce cas, vous pouvez utiliser le guide de configuration assistée **Configuration de la compagnie** qui vous aidera à commencer par des données de configuration essentielles.  

> [!NOTE]  
> Lorsque vous créez une compagnie, cela prend quelques minutes avant de pouvoir y accéder dans [!INCLUDE[prod_short](includes/prod_short.md)]. L'état de configuration sur la page **Compagnies** s'affiche lorsque la nouvelle compagnie est prête pour vous. Ensuite, vous pouvez basculer vers la nouvelle compagnie en utilisant **Mes paramètres**.  

Au cours de votre période d’évaluation de 30 jours, vous pouvez créer autant de compagnies que vous voulez, mais elles ne seront disponibles que durant cette période d’évaluation. Pour plus d'informations, contactez votre partenaire [!INCLUDE[prod_short](includes/prod_short.md)]. Voir aussi l’article [FAQ sur la version d’essai Dynamics 365 Business Central](trial-faq.md).  

Votre administrateur peut en savoir plus sur les essais et les abonnements [ici](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions).  

## <a name="copy-a-company"></a>Copier une compagnie

Sur la page **Compagnies**, vous pouvez utiliser l'action **Copier** pour créer une deuxième compagnie sur la base du contenu d’une compagnie existante. Ceci est utile, par exemple, lorsque vous souhaitez tester une compagnie sans perturber les données de production.

> [!Important]
> Cette fonction ne peut pas être utilisée pour sauvegarder une compagnie. La sauvegarde d'une compagnie commence par l'exportation de la base de données sous la forme d'un fichier .bacpac. Pour plus d'informations, voir [Exportation de bases de données](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-database-export) dans Aide dédiée au développement et à l'administration.

## <a name="set-up-the-company"></a>Configurer la compagnie

Lorsque vous vous connectez à une nouvelle compagnie, l'Assistant **Configuration de la compagnie** s'exécute automatiquement et vous permet de démarrer. Il vous sera demandé des informations sur votre activité, telles que l’adresse, les coordonnées bancaires et le mode d’évaluation du coût de l'inventaire. Ces informations sont nécessaires parce qu’elles servent de base dans plusieurs zones de [!INCLUDE[prod_short](includes/prod_short.md)], ce qui vous évitera de les configurer manuellement plus tard.  

Par exemple, [!INCLUDE [prod_short](includes/prod_short.md)] inclut l’adresse de votre compagnie dans les factures et autres documents et vos coordonnées bancaires dans les paiements. Le mode d’évaluation du coût est utilisé pour calculer les prix, ainsi que pour l’évaluation de l'inventaire.  

Une fois les bases en place, vous pouvez configurer les zones de base restantes. Maintenant, vous êtes prêt à ajouter des données métier, telles que les clients et les fournisseurs. Pour plus d’informations, consultez [Configurer [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md).  

## <a name="companies-and-environments"></a>Compagnies et environnements

[!INCLUDE [company_environment](includes/company_environment.md)]

Pour plus d'informations, voir [Passer à une autre compagnie ou un autre environnement](ui-organization-switch.md). Pour plus d’informations sur les environnements, voir [Comprendre l’infrastructure de Business Central Online](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology) (en anglais uniquement).  

## <a name="changing-a-companys-name"></a>Changer le nom d’une compagnie

Une fois qu’une compagnie a été créée, vous ne pouvez pas changer son nom. Mais vous pouvez changer son **Nom complet**, qui est le texte qui sera affiché pour la compagnie dans toute l’application.  

> [!TIP]
> Vous pouvez renommer une compagnie si vous utilisez [!INCLUDE[prod_short](includes/prod_short.md)] sur site.

## <a name="add-contoso-coffee"></a>Ajouter Contoso Coffee

L’application Contoso Coffee fournit des données de démonstration pour vous aider à explorer les fonctionnalités avancées de [!INCLUDE [prod_short](includes/prod_short.md)]. Trouvez l’application dans AppSource et installez-la dans une compagnie vide, par exemple une compagnie dans un environnement sandbox. Pour plus d’informations, voir [Présentation des données de démonstration Contoso Coffee](contoso-coffee/contoso-coffee-intro.md).  

## <a name="see-also"></a>Voir aussi

[Personnalisation de Business Central](ui-customizing-overview.md)  
[Configuration de [!INCLUDE[prod_short](includes/prod_short.md)]](setup.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Comprendre l’infrastructure de Business Central Online (en anglais uniquement)](/dynamics365/business-central/dev-itpro/administration/tenant-environment-topology)  

[!INCLUDE[footer-include](includes/footer-banner.md)]