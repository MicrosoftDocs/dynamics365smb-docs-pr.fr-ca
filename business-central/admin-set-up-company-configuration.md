---
title: Définir une configuration de compagnie | Microsoft Docs
description: Le processus d'implémentation commence avec les éléments requis par la solution Business Central. Vous regroupez toutes ces informations dans des colis de configuration.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 571261190274fc74535e7b18b2c949d7f7714c1b
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3917736"
---
# <a name="set-up-company-configuration"></a>Configurer une compagnie
Le processus d’implémentation commence avec le partenaire Microsoft. Le partenaire est responsable des réflexions sur les détails de la configuration et de la création d’un package qu’un client peut facilement appliquer. Avant de créer une nouvelle compagnie, vous devez en planifier la méthode de configuration. Vous devez prendre en compte les données de configuration de base et les types de données requis par la solution [!INCLUDE[d365fin](includes/d365fin_md.md)]. Vous regroupez toutes ces informations dans des packages configuration.

RapidStart Services fournit également les outils que vous utiliserez pour migrer vos données héritées, telles que les clients et les fournisseurs.  

Il est recommandé de créer des colis de configuration dont la plupart des tables de configuration sont déjà renseignées pour permettre aux clients de ne modifier que quelques paramètres après l'affectation du colis. Par exemple, lorsque vous créez une compagnie, les tables **Séries de n°** et **Ligne séries de n°** sont renseignées à l'aide d'un ensemble de séries de numéros et les numéros de début. Les champs **Souches de n°** correspondants des tables de configuration sont également renseignés automatiquement. Il n'est pas nécessaire d'entrer des séries de numéros et d'autres informations de configuration de base. Vous pouvez également modifier manuellement toutes les données par défaut utilisées avec RapidStart Services à l’aide de la feuille de configuration.  

Les packages configuration sont constitués sur la base d’une compagnie préconfigurée. Après avoir configuré une compagnie qui répond à vos besoins, vous pouvez créer un package de configuration qui contient les données pertinentes de cette compagnie. Vous pouvez ensuite les utiliser lorsque vous créez une compagnie que vous voulez configurer de la même manière.  

Pour faciliter l’importation des données principales, par exemple les informations sur le fournisseur et le client, vous pouvez utiliser des modèles de configuration. Les modèles de configuration contiennent un ensemble de paramètres par défaut, qui sont automatiquement affectés aux enregistrements importés dans [!INCLUDE[d365fin](includes/d365fin_md.md)].

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Planifier une configuration de la compagnie en renseignant la feuille de configuration.|[Gérer la configuration de la compagnie dans une feuille](admin-how-to-manage-company-configuration-in-a-worksheet.md)|  
|Créer un package de configuration, personnaliser un package, affecter des tables à un package, vérifier ou modifier les données client existantes, créer la compagnie et déplacer les données de test vers l'environnement de production.|[Préparer un package configuration](admin-how-to-prepare-a-configuration-package.md)| 

## <a name="see-also"></a>Voir aussi  
[Configuration d'une compagnie avec RapidStart Services](admin-set-up-a-company-with-rapidstart.md)  
[Administration](admin-setup-and-administration.md)
