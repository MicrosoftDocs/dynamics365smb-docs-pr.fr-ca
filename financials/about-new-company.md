---
title: "Créer des compagnies en utilisant un guide de configuration assistée | Microsoft Docs"
description: "Il est facile de créer une nouvelle compagnie vide dans Finance and Operations, Business edition. Un guide de configuration assistée vous aide à l'aide de procédures, et vous pouvez importer les données métier existantes."
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: company, setup wizard
ms.date: 03/02/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 10fb70ded1407c95034db6fcf974c37c6e119099
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="creating-new-companies-in-included365finincludesd365finmdmd"></a>Création de compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)]
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les conteneurs pour les données métier appartenant à une unité fonctionnelle ou une entité juridique sont désignés en tant que *compagnie*. Lorsque vous vous connectez à [!INCLUDE[d365fin](includes/d365fin_md.md)], une compagnie de démonstration et une compagnie vide vous sont attribuées, *Ma compagnie*. Le basculement entre compagnies est facile - accédez simplement à **Mes paramètres** et passez à l'autre compagnie. Vous pouvez également créer de nouvelles compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)], selon les besoins de votre compagnie. Lorsque vous créez une compagnie, un guide de configuration assistée vous permet de mettre en place les fondements. Ensuite, vous pouvez importer des données appropriées à partir de votre système hérité ou d'une autre compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="create-new-company"></a>Créer une nouvelle compagnie
Si vous décidez d'ajouter une compagnie à votre [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez utiliser l'assistant de configuration assistée **Créer une nouvelle compagnie** pour démarrer. L'assistant de configuration est disponible à partir de la fenêtre **Compagnies** et depuis la zone de recherche dans le champ **Compagnie** sous **Mes paramètres**.  

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
>   Lorsque vous créez une compagnie, cela prend quelques minutes avant de pouvoir y accéder dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. L'état de configuration dans la fenêtre **Compagnies** s'affiche lorsque la nouvelle compagnie est prête pour vous. Ensuite, vous pouvez basculer vers la nouvelle compagnie en utilisant **Mes paramètres**.  

Au cours de votre période d'évaluation de 30 jours, vous pouvez créer autant de compagnies que vous voulez, mais elles ne seront disponibles que durant cette période d'évaluation. Pour plus d'informations, contactez votre partenaire [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="company-setup"></a>Configuration de la compagnie
Lorsque vous vous connectez à une nouvelle compagnie, l'Assistant **Configuration de la compagnie** s'exécute automatiquement et vous permet de démarrer. Il vous sera demandé des informations sur votre activité, telles que l'adresse, les coordonnées bancaires et le mode d'évaluation du stock. Ces informations sont nécessaires parce qu'elles servent de base dans plusieurs zones de [!INCLUDE[d365fin](includes/d365fin_md.md)], ce qui vous évitera de les configurer manuellement plus tard.  

Par exemple, l'adresse de votre compagnie est incluse dans les factures et autres documents, vos coordonnées bancaires sont utilisées pour les paiements, et la méthode d'évaluation du coût est utilisée pour calculer les prix, ainsi que pour l'évaluation de l'inventaire.  

Une fois les bases en place, vous pouvez configurer les zones de base restantes. Maintenant, vous êtes prêt à ajouter des données métier, telles que les clients et les fournisseurs. Pour plus d'informations, reportez-vous à [Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md).  

## <a name="see-also"></a>Voir aussi
[Personnalisation de Finance and Operations, Business edition](ui-customizing-overview.md)  
[Configuration de [!INCLUDE[d365fin](includes/d365fin_md.md)]](setup.md)  
[Importation des données métier à partir d'autres systèmes financiers](upload-data.md)  
[Modification des paramètres de base](ui-change-basic-settings.md)  
[Bienvenue dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  

