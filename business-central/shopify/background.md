---
title: Exécuter des tâches en arrière-plan et de manière récurrente
description: Configurer la synchronisation des données entre Business Central et Shopify en arrière-plan.
ms.date: 05/26/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
author: brentholtorf
ms.author: bholtorf
ms.custom: bap-template
---

# <a name="run-tasks-in-the-background"></a>Exécution des tâches en arrière-plan

Il est efficace d’exécuter certaines tâches simultanément et de manière automatisée. Vous pouvez effectuer ces tâches en arrière-plan et également définir un calendrier pour les exécuter automatiquement. Pour exécuter des tâches en arrière-plan, deux modes sont pris en charge :

- Les tâches déclenchées manuellement sont programmées immédiatement via **Écritures file d’attente des travaux**.
- Les tâches récurrentes sont programmées dans **Écritures file d’attente des travaux**.

## <a name="run-tasks-in-the-background-for-a-specific-shop"></a>Exécuter des tâches en arrière-plan pour un magasin spécifique

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasin Shopify**, puis choisissez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez exécuter la synchronisation à l’arrière-plan pour ouvrir la page **Fiche magasin Shopify**.
3. Activez **Autoriser les synchronisations en arrière-plan**.

Désormais, lorsque l’action de synchronisation démarre, au lieu d’exécuter une tâche au premier plan, vous serez invité à attendre. Une fois la synchronisation terminée, vous pouvez passer à l’action suivante. La tâche est créée comme **Écriture file d’attente des travaux** et démarre immédiatement.

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
|**Compagnies sync.**|Rapport 30114 Synchroniser les compagnies (B2B) Shopify|
|**Synchroniser les paiements**|Rapport 30105 Synchroniser les paiements Shopify|
|**Sync. catalogues**|Rapport 30115 Shopify - Sync. catalogues (B2B)|
|**Sync. prix catalogue**|Rapport 30116 Shopify - Sync. prix catalogue (B2B)|

> [!NOTE]
> Certains éléments peuvent être mis à jour par plusieurs tâches. Par exemple lorsque vous importez des commandes, selon le paramétrage dans la page **fiche magasin Shopify**, le système peut également importer et mettre à jour des données client et/ou produit. Pour éviter les conflits, n’oubliez pas d’utiliser la même catégorie de file d’attente des projets.
>
> Utilisez le **Page de demande de rapport** action pour définir des filtres. Par exemple, vous pouvez spécifier que vous importez les commandes uniquement lorsque leur état est **Entièrement payé**.

Autres tâches pouvant être utiles pour automatiser le traitement ultérieur des documents de vente :

- Rapport 297 Reporter en lot des factures vente
- Rapport 296 Reporter en lot des documents de vente

Vous pouvez utiliser le champ **N° de commande Shopify** pour identifier les documents commerciaux importés depuis Shopify.

Pour en savoir plus sur le report de commandes client par lot, accédez à [Pour créer une entrée de file d’attente de tâches pour le report par lot de documents de vente](../ui-batch-posting.md#to-create-a-job-queue-entry-for-batch-posting-of-sales-orders).

## <a name="to-check-the-status-of-synchronization"></a>Pour examiner l’état de la synchronisation

Sur le **Chef d’entreprise** Centre de rôle, le **Shopify Activités** La pièce propose plusieurs indices qui peuvent vous aider à identifier rapidement s’il y a des problèmes avec Shopify Connecteur.

- **Clients non mappés** : Shopify le client est importé, mais n’est pas lié à une entrée client correspondante dans [!INCLUDE [prod_short](../includes/prod_short.md)].
- **Produits non mappés** – Shopify le produit est importé, mais n’est pas lié à une entrée article correspondante dans [!INCLUDE [prod_short](../includes/prod_short.md)].
- **Commandes non traitées** : Shopify les commandes sont importées, mais les documents de vente [!INCLUDE [prod_short](../includes/prod_short.md)] n’ont pas été créés, souvent à cause de produits ou de clients non cartographiés.
- **Expéditions non traitées** : les expéditions de vente reportées provenant des commandes Shopify ne sont pas synchronisées avec Shopify.
- **Erreurs d’expédition** : Shopify le connecteur n’a pas pu synchroniser les expéditions de vente reportées avec Shopify.
- **Erreurs de synchronisation** : des écritures file d’attente des projets ayant échoué sont liées à la synchronisation avec Shopify.

## <a name="see-also"></a>Voir aussi .

[Mise en route avec le connecteur Shopify](get-started.md)  
