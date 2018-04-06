---
title: "Procédure de création de packages de configuration de compagnie personnalisés | Microsoft Docs"
description: "À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 03/05/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 7feaa0e41cf5800ffd51d5807a90f6929492804e
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-custom-company-configuration-packages"></a>Créer des packages de configuration de compagnie personnalisés
À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.  

En général, créez un colis configuration par domaine fonctionnel, par exemple, créez un colis pour la fonctionnalité de fabrication. Cela vous permet d’appliquer et de configurer de nouveaux domaines au sein d’une compagnie en fonction de vos besoins.  

Autrement, vous pouvez créer un colis qui inclut les tables qui définissent la configuration, par exemple :  

-   Configuration des immobilisations  
-   Configuration du grand livre  
-   Configuration de l'inventaire  
-   Configuration de la fabrication  
-   Configuration achats et à payer  
-   Configuration du marketing  
-   Configuration de service  
-   Config. ventes et à recevoir  
-   Configuration d'entrepôt  
-   Config. paramètres report  
-   Configuration report de taxe  
-   Configuration du report d'inventaire  

Pour afficher une liste complète des tables de configuration, choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration**, puis sélectionnez le lien associé.  

## <a name="to-create-a-custom-company-configuration-package"></a>Pour créer un package de configuration de compagnie personnalisé  
1.  Créez une [!INCLUDE[d365fin](includes/d365fin_md.md)]. ***Lien NON POSSIBLE pour aider à la « création d'un abonné »***.   
2.  Créez une compagnie pour le modèle solution ou secteur d'utilisation. Pour plus d’informations, voir [Créer une compagnie](admin-how-to-create-a-new-company.md).  
3.  Configurer la nouvelle compagnie en tenant compte de vos besoins. Renseignez toutes les tables de configuration nécessaires.  
4.  Ouvrir la nouvelle compagnie.
5. Ouvrez la fenêtre **Feuille configuration**.  
6.  Ajoutez les tables que vous souhaitez transférer vers une autre compagnie à la feuille. Affecter des lignes feuille au colis.  
7.  Créez un questionnaire pour les tables de configuration les plus souvent utilisées.  
8.  Créez des modèles de configuration pour faciliter la création de données de base, telles que les clients ou les articles.  
9.  Exportez votre package comme fichier .rapidstart.  

## <a name="see-also"></a>Voir aussi  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)

