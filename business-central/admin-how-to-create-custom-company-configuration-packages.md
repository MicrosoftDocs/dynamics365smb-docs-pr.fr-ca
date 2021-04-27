---
title: Procédure de création de packages de configuration de compagnie personnalisés | Microsoft Docs
description: À mesure que vous développez votre entreprise, vous êtes susceptible d'utiliser un ensemble de types de compagnie pour la plupart de vos clients. Vous pouvez rationaliser votre processus d’implémentation en transformant ces types en packages de configuration de compagnie que vous pouvez réutiliser.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: e6781b01a80acfd3431fc000069dd2c8b96dffc5
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5779917"
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

Pour visualiser la liste complète des tables de configuration, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration manuelle**, puis sélectionnez le lien associé.  

> [!IMPORTANT]
> Soyez prudent si vous choisissez des tables ou des champs qui portent le même nom temporel mais sont différenciés par des caractères spéciaux, tels que %, &, <, >, (, et ). Par exemple, la table « XYZ » peut contenir les champs « Champ 1 » et « Champ 1 % ».
>
> Le processeur XML n'accepte que certains caractères spéciaux et supprime ceux qu'il n'accepte pas. Si la suppression d'un caractère spécial, tel que le signe % dans « Champ 1 % », génère deux ou plusieurs tables ou champs avec le même nom, une erreur se produit lorsque vous exportez ou importez un package de configuration.

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


[!INCLUDE[footer-include](includes/footer-banner.md)]