---
title: Créer des compagnies en utilisant un guide de configuration assistée | Microsoft Docs
description: Il est facile de créer une nouvelle compagnie vide dans Business Central. Un guide de configuration assistée vous aide à l'aide de procédures, et vous pouvez importer les données métier existantes.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: company, setup wizard
ms.date: 11/01/2019
ms.author: edupont
ms.openlocfilehash: 70bd78244c4d8570a5e9b8fbe2d1e8a4c74d7530
ms.sourcegitcommit: 49309bdff9b680a35032b355fe97c565845dba15
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 11/01/2019
ms.locfileid: "2695129"
---
# <a name="creating-new-companies-in-included365finincludesd365fin_mdmd"></a>Création de compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)]
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les conteneurs pour les données métier appartenant à une unité fonctionnelle ou une entité juridique sont désignés en tant que *compagnie*. Lorsque vous vous connectez à [!INCLUDE[d365fin](includes/d365fin_md.md)], une compagnie de démonstration et une compagnie vide vous sont attribuées, *Ma compagnie*. Le basculement entre compagnies est facile : accédez simplement à **Mes paramètres** et passez à l'autre compagnie. Vous pouvez également créer de nouvelles compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)], selon les besoins de votre activité. Lorsque vous créez une compagnie, un guide de configuration assistée vous permet de mettre en place les fondements. Ensuite, vous pouvez importer des données appropriées à partir de votre système hérité ou d'une autre compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="creating-a-new-company"></a>Création d'une compagnie
Si vous décidez d'ajouter une compagnie à votre [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez utiliser le guide de configuration assistée **Créer une nouvelle compagnie** pour démarrer. L'assistant de configuration est disponible à partir de la page **Compagnies** et depuis la zone de recherche dans le champ **Compagnie** sur la page **Mes paramètres**.  

L'assistant de configuration offre trois modèles :

-   **Évaluation - Exemples de données**  
    Cela crée une compagnie qui est similaire à la compagnie de démonstration avec des exemples de données et des données de configuration.  
-   **Production - Données de configuration uniquement**  
    Cela crée une compagnie qui est similaire à **Ma compagnie** avec des données de configuration, mais sans exemples de données.
-   **Évaluation avancée - Exemple de données complètes** Permet de créer une compagnie avec des données de configuration et des exemples de données complètes pour toutes les fonctions, y compris la production et la gestion des services.
-   **Créer nouveau - Aucune donnée**  
    Cela crée une compagnie vide sans données de configuration.  

Si vous souhaitez démarrer facilement avec une nouvelle compagnie, sélectionnez **Production - Données de configuration uniquement**, puis importez vos propres données métier, telles que les clients, les articles et les fournisseurs. Choisissez le modèle **Nouveau** si vous souhaitez tout redéfinir à zéro. Dans ce cas, vous pouvez utiliser le guide de configuration assistée **Configuration de la compagnie** qui vous aidera à commencer par des données de configuration essentielles.  

> [!NOTE]  
>   Lorsque vous créez une compagnie, cela prend quelques minutes avant de pouvoir y accéder dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. L'état de configuration sur la page **Compagnies** s'affiche lorsque la nouvelle compagnie est prête pour vous. Ensuite, vous pouvez basculer vers la nouvelle compagnie en utilisant **Mes paramètres**.  

Au cours de votre période d'évaluation de 30 jours, vous pouvez créer autant de compagnies que vous voulez, mais elles ne seront disponibles que durant cette période d'évaluation. Pour plus d'informations, contactez votre partenaire [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="copying-a-company"></a>Copie d'une compagnie
Sur la page **Compagnies**, vous pouvez utiliser l'action **Copier** pour créer une deuxième compagnie sur la base du contenu d’une compagnie existante. Ceci est utile, par exemple, lorsque vous souhaitez tester une compagnie sans perturber les données de production.

> [!Important]
> Cette fonction ne peut pas être utilisée pour sauvegarder une compagnie. La sauvegarde d'une compagnie commence par l'exportation de la base de données sous la forme d'un fichier .bacpac. Pour plus d'informations, voir [Exportation de bases de données](/dynamics365/business-central/dev-itpro/administration/tenant-admin-center-database-export) dans Aide dédiée à l'équipe IT et aux développeurs.

## <a name="company-setup"></a>Configuration de la compagnie
Lorsque vous vous connectez à une nouvelle compagnie, l'Assistant **Configuration de la compagnie** s'exécute automatiquement et vous permet de démarrer. Il vous sera demandé des informations sur votre activité, telles que l'adresse, les coordonnées bancaires et le mode d'évaluation du stock. Ces informations sont nécessaires parce qu'elles servent de base dans plusieurs zones de [!INCLUDE[d365fin](includes/d365fin_md.md)], ce qui vous évitera de les configurer manuellement plus tard.  

Par exemple, l'adresse de votre compagnie est incluse dans les factures et autres documents, vos coordonnées bancaires sont utilisées pour les paiements, et la méthode d'évaluation du coût est utilisée pour calculer les prix, ainsi que pour l'évaluation de l'inventaire.  

Une fois les bases en place, vous pouvez configurer les zones de base restantes. Maintenant, vous êtes prêt à ajouter des données métier, telles que les clients et les fournisseurs. Pour plus d'informations, reportez-vous à [Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md).  

## <a name="see-also"></a>Voir aussi
[Personnalisation de Business Central](ui-customizing-overview.md)  
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Mise en route](product-get-started.md)  
