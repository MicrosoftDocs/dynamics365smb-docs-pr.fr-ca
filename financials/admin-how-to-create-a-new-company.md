---
title: "Procédure de création d'une compagnie | Microsoft Docs"
description: "Lorsque vous utilisez RapidStart Services, des tables et des pages sont créées, mais elles ne contiennent pas de données."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/06/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 8c07b7c4e6b1c82004295a187184a6f3ccb4c7c7
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-a-new-company"></a>Créer une compagnie
Pour utiliser RapidStart Services pour [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez d'abord créer une compagnie pour laquelle vous souhaitez effectuer une implémentation client. Lorsque vous créez une société, les tables et les pages standard de [!INCLUDE[d365fin](includes/d365fin_md.md)] sont créées, mais elles ne contiennent pas de données.

Vous pouvez également appliquer des données de configuration spécifiques à votre compagnie après l’avoir initialisée. Les informations sont fournies dans un package de configuration, un fichier .rapidstart, qui fournit le contenu sous un format compressé.  

Des exemples de packages de configuration, qui comprennent des fichiers spécifiques à un pays/une région, sont inclus avec la compagnie de démonstration CRONUS. Suivez la procédure suivante pour utiliser l'exemple de package de configuration avec une nouvelle compagnie.  

## <a name="to-use-the-sample-basicconfig-configuration-package"></a>Pour utiliser l'exemple de package de configuration BASICCONFIG  
1. Ouvrez la compagnie CRONUS International Ltd. Pour plus d'informations, voir [Modification des paramètres de base](ui-change-basic-settings.md).
2. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Packages configuration**, puis sélectionnez le lien associé.  
3. Sélectionnez le package BASICCONFIG dans la liste, puis sélectionnez l'action **Exporter package**.  

Suivez la procédure suivante pour créer une compagnie, puis utilisez le package BASICCONFIG dans le cadre du processus.  

## <a name="to-create-a-new-company"></a>Création d'une nouvelle compagnie  
1. Créer une nouvelle compagnie. Pour plus d'informations, voir [Création de compagnies dans [!INCLUDE[d365fin](includes/d365fin_md.md)]](about-new-company.md).
2. Dans le tableau de bord Responsable de l'implémentation de RapidStart Services, vous pouvez maintenant importer le package de configuration que vous avez exporté de la compagnie CRONUS International Ltd.

Une fois que vous avez créé une compagnie, certaines tables se renseignent automatiquement, même si aucun modèle de compagnie n'est affecté. Par exemple, vous pouvez consulter les codes standard pour les transactions par lots et la validation dans la fenêtre **Code origine**. Si vous disposez d'une version locale de [!INCLUDE[d365fin](includes/d365fin_md.md)], consultez cette table en tenant compte d'éventuels problèmes de langue locale.

## <a name="about-data-tables"></a>À propos des tables de données
[!INCLUDE[d365fin](includes/d365fin_md.md)], les tables de données existent en deux types de base : Principale et Configuration. Lorsque vous paramétrez une configuration de compagnie, vous pouvez utiliser ces types afin de cibler votre stratégie de configuration.  

### <a name="master-data-tables"></a>Tables de données principales  
Le tableau suivant répertorie certaines tables de données principales. Lorsque vous lancez une nouvelle compagnie, ces tables sont vides.  

|N° table|Nom de table|  
|-------------------|--------------------|  
|15|Compte général|  
|18|Client|  
|23|Fournisseur|  
|27|Article|  
|5050|Contact|  

### <a name="setup-data-tables"></a>Tables de données de configuration  
Le tableau suivant répertorie certaines tables de données de configuration à partir desquelles vous capturez les informations de configuration dans le questionnaire de configuration. Ces tables contiennent des informations de base lors de la création de la compagnie.  

|Numéro table|Nom de table|  
|-------------------|--------------------|  
|98|Configuration du grand livre|  
|311|Configuration ventes & à recevoir|  
|312|Configuration achats et à payer|  
|313|Configuration de l'inventaire|  

Outre des tables de données de configuration, [!INCLUDE[d365fin](includes/d365fin_md.md)] dispose également de tables de données de type configuration qui spécifient des informations de base sur la compagnie et ses processus entreprise. Le tableau suivant répertorie certaines d'entre elles.  

|N° table|Nom de table|  
|-------------------|--------------------|  
|3|Modalités de paiement|  
|4|Devise|  
|6|Groupes prix client|  
|5700|Unité de stock|

  

## <a name="see-also"></a>Voir aussi  
[Appliquer des configurations à de nouvelles compagnies](admin-apply-configuration-to-new-companies.md)  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)

