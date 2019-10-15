---
title: Procédure de création de packages de configuration de compagnie personnalisés | Microsoft Docs
description: À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 6fd35133d16056b947db6680cc9a76cfccaa6a3c
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2308097"
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

Pour visualiser la liste complète des tables de configuration, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration manuelle**, puis sélectionnez le lien associé.  

## <a name="to-create-a-custom-company-configuration-package"></a>Pour créer un package de configuration de compagnie personnalisé  
1.  Créer une nouvelle compagnie. Pour plus d'informations, voir [Création de compagnies dans Business Central](about-new-company.md).  
3.  Configurez la nouvelle compagnie en tenant compte de vos besoins. Renseignez toutes les tables de configuration nécessaires.  
4.  Ouvrir la nouvelle compagnie.
5. Ouvrir la page **Feuille configuration**.  
6.  Ajoutez les tables que vous souhaitez transférer vers une autre compagnie à la feuille. Affecter des lignes feuille au colis.  
7.  Créez un questionnaire pour les tables de configuration les plus souvent utilisées.  
8.  Créez des modèles de configuration pour faciliter la création de données de base, telles que les clients ou les articles.  
9.  Exportez votre package comme fichier .rapidstart.  

## <a name="see-also"></a>Voir aussi  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
