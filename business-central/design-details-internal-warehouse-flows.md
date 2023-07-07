---
title: 'Détails de conception - Flux pour la production, l’assemblage et les tâches'
description: 'Découvrez le flux entre les zones d’entrepôt pour le prélèvement des composantes et le rangement des articles finis pour l’assemblage, la production ou les ordres de travail.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/16/2022
ms.custom: bap-template
---
# <a name="flows-for-production-assembly-and-jobs"></a>Flux pour la production, l’assemblage et les tâches

Les flux internes, tels que le prélèvement de composantes et le rangement des articles finis pour l’assemblage, les tâches et les bons de production, sont similaires aux flux entrants ou sortants. Ainsi, de nombreux processus peuvent sembler familiers. Cet article fournit des informations sur l’utilisation des flux d’entrepôt internes avec différents niveaux de complexité.

## <a name="overview-of-different-configuration-options"></a>Aperçu des différentes options de configuration

Vous pouvez configurer les fonctionnalités d’entrepôt de différentes manières. Il est important que les options que vous choisissez améliorent vos processus sans entraîner de surcharge. Les tableaux suivants décrivent les configurations typiques de traitement des biens physiques pour la production, les tâches et les ordres d’assemblage.

### <a name="inbound-flow-put-away"></a>Flux entrant (rangement)

|Niveau de complexité|Désignation|Paramètres|Code de zone|Flux entrant du bon de production|Flux entrant de l’ordre d’assemblage|Flux entrant de tâches|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|Aucune activité entrepôt dédiée.|Report à partir de commandes et de journaux.||Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Journal de production -> Journal de sortie</br><br/> **REMARQUE** : Vous pouvez reporter la sortie à l’aide du **Journal production**.|Ordre d’assemblage|Le rangement ne s’applique pas aux tâches|  
|Basique|Commande par commande.|Rangement requis. </br><br/> **REMARQUE** : bien que le paramètre soit appelé **Rangement requis**, vous pouvez toujours publier la sortie des documents source aux emplacements où vous cochez cette case. |Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Bon de production -> Rangement inventaire|Ordre d’assemblage|Le rangement ne s’applique pas aux tâches|
|Avancé|Activités de rangement regroupées pour plusieurs documents origines.|Réception requise + Rangement requis|Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Bon(s) de production -> Journal de sortie|Ordre(s) d’assemblage -> mouvements internes | Le rangement ne s’applique pas aux tâches|
|Avancé|Comme ci-dessus + activités de prélèvement/rangement dirigées|Prélèvement et rangement dirigés (les boutons à bascule dépendants seront activés automatiquement)|Obligatoire|Comme ci-dessus.|Comme ci-dessus.| Le rangement ne s’applique pas aux tâches|

Certaines configurations ne vous permettent pas d’utiliser des documents d’entrepôt dédiés pour enregistrer les rangements. Toutefois, si votre emplacement utilise des zones, vous pouvez utiliser des documents de mouvement génériques pour déplacer les articles produits ou assemblés vers l’entrepôt. Learn more at [Déplacement des articles en interne dans les configurations entrepôt de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).

### <a name="outbound-flow-pick"></a>Flux sortant (prélèvement)

|Niveau de complexité|Désignation|Paramètres|Code de zone|Flux sortant du bon de production|Flux sortant de l’ordre d’assemblage|Flux sortant de tâches|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|Aucune activité entrepôt dédiée.|Report à partir de commandes et de journaux.||Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Journal production -> Journal consommation </br><br/> **REMARQUE** : Vous pouvez reporter la consommation à l’aide du **Journal production**.|Ordre d’assemblage|Tâche -> Journal projet|  
|Basique|Commande par commande.|Prélèvement requis. </br><br/> **REMARQUE** : bien que le paramètre soit appelé **Prélèvement requis**, vous pouvez toujours publier la sortie des documents source aux emplacements où vous cochez cette case. <!-- ToDo Test prod output-->|Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Bon de production -> Prélèvement inventaire|Ordre de fabrication -> Mouvement d’inventaire</br><br/>Le **mouvement d’inventaire** ne peut être utilisé qu’avec des zones.|Tâche -> Prélèvement inventaire|
|Avancé|Activités de prélèvement regroupées pour plusieurs documents origines.|Livraison requise + Prélèvement requis|Facultatif. Contrôlé par le bouton à bascule Code de zone obligatoire|Bon(s) de production ->Prélèvement entrepôt -> Journal consommation |Ordre(s) d’assemblage -> Prélèvement entrepôt| Tâche(s) -> Prélèvement entrepôt -> Journal projet |
|Avancé|Comme ci-dessus + activités de prélèvement/rangement dirigées|Prélèvement et rangement dirigés (les boutons à bascule dépendants seront activés automatiquement)|Obligatoire|Comme ci-dessus.|Comme ci-dessus.| Le prélèvement et le rangement dirigés ne sont pas pris en charge pour les tâches|

Comme pour le flux entrant, certaines configurations ne vous permettent pas d’utiliser des documents d’entrepôt dédiés pour enregistrer les rangements. Si votre emplacement utilise des zones, vous pouvez utiliser des documents de mouvement génériques pour déplacer les articles produits ou assemblés. Learn more at [Déplacement d’articles](warehouse-move-items.md).

## <a name="warehouses-without-dedicated-warehouse-activity"></a>Entrepôts sans activité d’entrepôt dédiée

Même si vous n’avez pas d’activités d’entrepôt dédiées, vous souhaiterez probablement toujours suivre des éléments tels que la consommation et la production. Les articles suivants fournissent des informations sur le traitement des réceptions pour les documents origine.

* [Enregistrer la consommation et la production pour une ligne bon de production libéré](production-how-to-register-consumption-and-output.md)
* [Assembler des articles](assembly-how-to-assemble-items.md)
* [Enregistrer la consommation ou l′utilisation pour les projets](projects-how-record-job-usage.md)

## <a name="basic-warehouse-configuration"></a>Configuration d’entrepôt de base

Les flux entrants et sortants dans une configuration d’entrepôt de base impliquent les paramètres suivants sur la page **Fiche emplacement** pour l’emplacement :

* Pour le flux entrant (rangement), activez le bouton à bascule **Rangement requis** , mais désactivez le bouton à bascule **Réception requise**.
* Pour le flux sortant (prélèvement), activez le bouton à bascule **Prélèvement requis**, mais désactivez le bouton à bascule **Livraison requise**.

### <a name="flows-to-and-from-production-in-a-basic-warehouse-configuration"></a>Flux vers et depuis la production dans une configuration d’entrepôt de base

Utilisez les documents **Prélèvement inventaire** pour prélever des composantes de production dans le flux vers la production. Pour ranger les produits que vous fabriquez, utilisez les documents **Rangement inventaire**.

Pour les emplacements qui utilisent des zones, les documents de mouvement d’inventaire sont particulièrement utiles pour la consommation des composantes. Pour en savoir plus sur la façon dont la consommation de composantes passe des zones avant production aux zones d'atelier ouvert, voir [Consommation des composantes de production dans l’entrepôt](warehouse-how-to-pick-for-production.md#flushing-production-components-in-a-basic-warehouse-configuration).

   > [!NOTE]
   > Les mouvements d’inventaire sont des documents importants si vous utilisez les méthodes de consommation **Prélèvement + Aval** ou **Prélèvement + Amont**. Learn more at [Méthodes de consommation](production-how-to-flush-components-according-to-operation-output.md#flushing-methods).

* Les champs **Code de zone avant production**, **Code de zone post-production** et **Code de zone d'atelier ouvert** de l'emplacement ou de l'unité de production/atelier définissent les flux par défaut à destination et en provenance des zones de production.
* Gérez le mouvement des articles produits sur la page **Mouvement interne** sans rapport avec un bon de production.

### <a name="flows-to-and-from-assembly-in-a-basic-warehouse-configuration"></a>Flux vers et depuis l’assemblage dans une configuration d’entrepôt de base

Reportez le résultat d’assemblage et la consommation directement à partir d’un ordre d’assemblage.

> [!NOTE]
> Les documents **Prélèvement inventaire** et **Rangement inventaire** ne sont pas pris en charge pour les ordres d’assemblage.

Pour les emplacements qui utilisent des zones :

* Utilisez les documents **Mouvement d’inventaire** pour déplacer les composantes d’assemblage vers la zone d’assemblage.
* Les champs **Code de zone avant assemblage**, **Code de zone post-assemblage** de la fiche emplacement définissent les flux par défaut depuis et vers les zones d’assemblage.
* Gérez le mouvement des articles assemblés sur la page **Mouvement interne**, sans rapport avec un ordre d’assemblage.

[!INCLUDE [prod_short](includes/prod_short.md)] prend en charge les flux d’assemblage Assembler pour stock et Assembler pour commande. Pour en savoir plus, voir [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). En ce qui concerne la gestion des entrepôts, l’assemblage pour stock fait partie du flux interne de l’entrepôt et l’assemblage pour commande se trouve dans le flux sortant de l’entrepôt. Pour en savoir plus, voir [Traitement des articles à assembler pour commande dans les prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

### <a name="flows-for-project-management-in-a-basic-warehouse-configuration"></a>Flux pour la gestion de projet dans une configuration d’entrepôt de base

Utilisez les documents **Prélèvement inventaire** pour sélectionner les composantes de la tâche dans le flux vers la gestion de projet.

Pour un emplacement qui utilise des zones, le champ **Code de zone avant projet** dans l'emplacement définit les flux par défaut vers la gestion de projet.

## <a name="advanced-warehouse-configurations"></a>Configurations d'entrepôt avancées

Les flux entrants et sortants dans une configuration d’entrepôt avancée impliquent les paramètres suivants sur la page **Fiche emplacement** pour l’emplacement :

* Pour le flux entrant (rangement), activez les boutons à bascule **Réception requise** et **Rangement requis**.
* Pour le flux sortant (prélèvement), activez les boutons à bascule **Livraison requise** et **Réception requise**.

### <a name="flows-to-and-from-production-in-advanced-warehouse-configurations"></a>Flux vers et depuis la production dans une configuration d’entrepôt avancée

Utilisez les documents **Prélèvement entrepôt** et la page **Feuille prélèvement** pour prélever des composantes pour la production.

Pour les emplacements qui utilisent des zones :

* Les documents **Mouvement entrepôt** et la page **Feuille mouvement** sont particulièrement utiles pour la consommation des composantes. Pour en savoir plus, voir [Consommation des composantes de production dans l’entrepôt](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md#flushing-production-components-in-a-advanced-warehouse-configuration).
* Les champs **Code de zone avant production**, **Code de zone post-production** et **Code de zone d'atelier ouvert** de l'emplacement ou de l'unité de production/atelier définissent les flux par défaut à destination et en provenance des zones de production. 
* Gérez le mouvement des articles produits sur les pages **Feuille mouvement** ou **Rangement interne entrepôt** sans rapport avec un bon de production.

### <a name="flows-to-and-from-assembly-in-advanced-warehouse-configurations"></a>Flux vers et depuis l’assemblage dans une configuration d’entrepôt avancée

Utilisez les documents **Prélèvement entrepôt** et la page **Feuille prélèvement** pour prélever des composantes pour l’assemblage.

Pour les emplacements qui utilisent des zones :

* Les champs **Code de zone avant assemblage** et **Code de zone post-assemblage** de l’emplacement définissent le flux par défaut depuis et vers les champs d’assemblage.
* Gérez le mouvement des éléments d’assemblage sur les pages **Feuille mouvement** ou **Rangement interne entrepôt** sans rapport avec un ordre d’assemblage.

[!INCLUDE [prod_short](includes/prod_short.md)] prend en charge les flux d’assemblage Assembler pour stock et Assembler pour commande. Pour en savoir plus, voir [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md#understanding-assemble-to-order-and-assemble-to-stock). 

L’assemblage pour stock fait partie du flux interne de l’entrepôt et l’assemblage pour commande se trouve dans le flux sortant de l’entrepôt. Pour en savoir plus, voir [Traitement des articles à assembler pour commande dans les livraisons entrepôt](warehouse-how-ship-items.md#handling-assemble-to-order-items-in-warehouse-shipments).

### <a name="flows-to-project-management-in-advanced-warehouse-configurations"></a>Flux pour la gestion de projet dans une configuration d’entrepôt avancée

Utilisez les documents **Prélèvement entrepôt** et la page **Feuille prélèvement** pour prélever des composantes dans le flux pour la gestion de projet.

Pour les emplacements qui utilisent des zones, le champ **Code de zone avant projet** dans l'emplacement définit les flux par défaut vers la zone du projet.

## <a name="see-also"></a>Voir aussi

[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
