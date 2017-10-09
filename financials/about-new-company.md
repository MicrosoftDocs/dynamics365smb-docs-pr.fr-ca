---
title: "Créer des compagnies en utilisant un guide de configuration assistée | Microsoft Docs"
description: "Il est facile de créer une nouvelle compagnie vide dans Dynamics 365 for Financials. Un guide de configuration assistée vous aide à l'aide de procédures, et vous pouvez importer les données métier existantes."
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: company, setup wizard
ms.date: 07/14/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: eea34afbee429d14ab150894729cb4ea3843bb2b
ms.openlocfilehash: 3ff3c7af87033595d64e583b62b0e0242b22d2f1
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="creating-new-companies-in-included365finlongincludesd365finlongmdmd"></a>Création de compagnies dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], les conteneurs pour les données métier appartenant à une unité fonctionnelle ou une entité juridique sont désignés en tant que *compagnie*. Lorsque vous vous connectez à [!INCLUDE[d365fin](includes/d365fin_md.md)], une compagnie de démonstration et une compagnie vide vous sont attribuées, *Ma compagnie*. Le basculement entre compagnies est facile - accédez simplement à **Mes paramètres** et passez à l'autre compagnie. Vous pouvez également créer de nouvelles compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)], selon les besoins de votre compagnie. Lorsque vous créez une compagnie, un guide de configuration assistée vous permet de mettre en place les fondements. Ensuite, vous pouvez importer des données appropriées à partir de votre système hérité ou d'une autre compagnie dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="create-new-company"></a>Créer une nouvelle compagnie
Si vous décidez d'ajouter une compagnie à votre [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez utiliser l'assistant de configuration assistée **Créer une nouvelle compagnie** pour démarrer. L'assistant de configuration est disponible à partir de la fenêtre **Compagnies** et depuis la zone de recherche dans le champ **Compagnie** sous **Mes paramètres**.  

L'assistant de configuration offre trois modèles :

-   **Évaluation Suite**  
    Cela crée une compagnie qui est similaire à la compagnie de démonstration avec des exemples de données et des données de configuration.  
-   **Production Suite**  
    Cela crée une compagnie qui est similaire à **Ma compagnie** avec des données de configuration, mais sans exemples de données.  
-   **Créer**  
    Cela crée une compagnie vide sans données de configuration.  

Si vous souhaitez démarrer facilement avec une nouvelle compagnie, sélectionnez **Production Suite**, puis importez vos propres données commerciales, telles que les clients, les articles et les fournisseurs. Choisissez le modèle **Nouveau** si vous souhaitez tout redéfinir à zéro. Dans ce cas, vous pouvez utiliser l'assistant de configuration assistée **Configuration de la compagnie** pour commencer par des données de configuration essentielles.  

> [!NOTE]  
>   Lorsque vous créez une compagnie, cela prend quelques minutes avant de pouvoir y accéder dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. L'état de configuration dans la fenêtre **Compagnies** s'affiche lorsque la nouvelle compagnie est prête pour vous. Ensuite, vous pouvez basculer vers la nouvelle compagnie en utilisant **Mes paramètres**.  

Au cours de votre période d'évaluation de 30 jours, vous pouvez créer autant de compagnies que vous voulez, mais elles ne seront disponibles que durant cette période d'évaluation. Pour plus d'informations, contactez votre partenaire [!INCLUDE[d365fin](includes/d365fin_md.md)].  

## <a name="company-setup"></a>Configuration de la compagnie
Lorsque vous vous connectez à une nouvelle compagnie, l'Assistant **Configuration de la compagnie** s'exécute automatiquement et vous permet de démarrer. Il vous sera demandé des informations sur votre activité, telles que l'adresse, les coordonnées bancaires et le mode d'évaluation du stock. Ces informations sont nécessaires parce qu'elles servent de base dans plusieurs zones de [!INCLUDE[d365fin](includes/d365fin_md.md)], ce qui vous évitera de les configurer manuellement plus tard.  

Par exemple, l'adresse de votre compagnie est incluse dans les factures et autres documents, vos coordonnées bancaires sont utilisées pour les paiements, et la méthode d'évaluation du coût est utilisée pour calculer les prix, ainsi que pour l'évaluation de l'inventaire.  

Une fois les bases en place, vous pouvez configurer les zones de base restantes. Maintenant, vous êtes prêt à ajouter des données métier, telles que les clients et les fournisseurs. Pour plus d'informations, voir [Configuration de Dynamics 365 for Financials](setup.md).  

## <a name="see-also"></a>Voir aussi
[Configuration de Dynamics 365 for Financials](setup.md)  
[Importation des données métier à partir d'autres systèmes financiers](upload-data.md)  
[Modification des paramètres de base](ui-change-basic-settings.md)  
[Bienvenue dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  

