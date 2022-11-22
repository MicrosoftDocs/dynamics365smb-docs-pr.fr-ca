---
title: Exécuter des tâches en arrière-plan et de manière récurrente
description: Configurer la synchronisation des données entre Business Central et Shopify en arrière-plan.
ms.date: 05/11/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.reviewer: solsen
author: edupont04
ms.author: andreipa
ms.openlocfilehash: 4a67f6fc58fb8b158563ce58baab55e7fda2ccb1
ms.sourcegitcommit: 5bb13966e9ba8d7a3c2f00dd32f167acccf90b82
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/28/2022
ms.locfileid: "9728610"
---
# <a name="run-tasks-in-the-background"></a>Exécuter des tâches en arrière-plan

Il est efficace d’exécuter certaines tâches simultanément et de manière automatisée. Vous pouvez effectuer ces tâches en arrière-plan et également définir un calendrier pour les exécuter automatiquement. Pour exécuter des tâches en arrière-plan, deux modes sont pris en charge :

- Les tâches déclenchées manuellement sont programmées immédiatement via **Écritures file d’attente des travaux**.
- Les tâches récurrentes sont programmées dans **Écritures file d’attente des travaux**.

## <a name="run-tasks-in-the-background-for-a-specific-shop"></a>Exécuter des tâches en arrière-plan pour un magasin spécifique

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez le nom du **Magasin Shopify**, puis choisissez le nom du magasin dans la liste.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser les articles pour ouvrir la page **Fiche magasin Shopify**.
3. Activez **Autoriser les synchronisations en arrière-plan**.

Désormais, lorsque l’action de synchronisation est déclenchée, au lieu d’exécuter une tâche au premier plan, vous serez invité à attendre. Une fois la synchronisation terminée, vous pouvez passer à l’action suivante. La tâche est créée comme **Écriture file d’attente des travaux** et démarre instantanément de manière non bloquante.

## <a name="to-schedule-recurring-tasks"></a>Pour programmer des tâches récurrentes

Vous pouvez programmer les activités récurrentes suivantes pour qu’elles soient exécutées de manière automatisée. Pour plus d’informations sur la planification des tâches, voir [File d’attente des travaux](../admin-job-queues-schedule-tasks.md).

|Tâche|Objet|
|------|------------|
|**Synchroniser les commandes à partir de Shopify**|Rapport 30104 Synchroniser les commandes à partir de Shopify|
|**Traiter les commandes Shopify**|Rapport 30103 Créer des documents de vente Shopify|
|**Synchroniser livraisons avec Shopify**|Rapport 30109 Synchroniser livraison avec Shopify|
|**Synchroniser les produits et/ou les prix**|Rapport 30108 Synchroniser les produits Shopify|
|**Synchroniser l'inventaire**|Rapport 30102 Synchroniser le stock avec Shopify|
|**Synchroniser les images**|Rapport 30107 Synchroniser les images Shopify|
|**Synchroniser les clients**|Rapport 30100 Synchroniser les clients Shopify|
|**Synchroniser les paiements**|Rapport 30105 Synchroniser les paiements Shopify|

> [!NOTE]
> Certains éléments peuvent être mis à jour par plusieurs tâches, par exemple lorsque vous importez des commandes, selon le paramétrage dans la **fiche magasin Shopify**, le système peut également importer et mettre à jour des données client et/ou produit. N’oubliez pas d’utiliser la même catégorie de file d’attente des travaux pour éviter les conflits.

## <a name="see-also"></a>Voir aussi .

[Mise en route du connecteur pour Shopify](get-started.md)  