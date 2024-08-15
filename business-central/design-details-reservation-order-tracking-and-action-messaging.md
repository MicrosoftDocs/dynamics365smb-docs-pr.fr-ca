---
title: 'Détails de conception - réservation, suivi des commandes et messagerie d’action | Microsoft Docs'
description: Le système de réservation est complet et inclut les fonctionnalités étroitement liées et parallèles du Chaînage et des Messages d'action.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'design, replenishment, reordering'
ms.date: 07/23/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="design-details-reservation-order-tracking-and-action-messaging"></a>Détails de conception : réservation, chaînage et message d’action

Le système de réservation est complet et inclut les fonctionnalités étroitement liées et parallèles du Chaînage et des Messages d'action.  

Au cœur du système de réservation se trouve la liaison d’une entrée de demande et d’une entrée d’offre correspondante, soit via la réservation, soit via le suivi des commandes. Une réservation est un lien généré par l'utilisateur, alors qu'un enregistrement de chaînage est un lien généré par le système. Une quantité d'articles entrée dans le système de réservation est réservée ou chaînée, mais pas les deux à la fois. La manière dont les systèmes gèrent un élément dépend de la manière dont l’élément est configuré.  

Le système de réservation interagit avec le système de planification en créant des messages d'action sur les lignes planification pendant les exécutions de planification. Un message d'action peut être considéré comme un ajout à un enregistrement de chaînage. Les messages d'action, s'ils sont créés dynamiquement dans le chaînage ou lors de l'exécution de la planification, offrent un outil de choix pour une planification efficace de l'approvisionnement.  

> [!NOTE]  
> Les quantités réservées sont ignorées par le système de planification., c.-à-d., le lien fixe qui est effectué entre la demande et l'approvisionnement ne peut pas être modifié par le biais de la planification.  

 Le système de réservation forme également la base structurelle du système de traçabilité. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-tracking.md).  

 <!--For more detailed information about how the reservation system works, see the _Reservation Entry Table_ white paper on [PartnerSource](https://go.microsoft.com/fwlink/?LinkId=258348).  -->
<!--
> [!NOTE]
> [!INCLUDE [locations-cronus](includes/locations-cronus.md)]
-->

## <a name="reservation"></a>Réservation

 Une réservation est un lien ferme qui connecte une demande spécifique à un approvisionnement spécifique. Ce lien affecte directement la transaction d'inventaire ultérieure et garantit l'affectation correcte des écritures article à des fins d'évaluation des coûts. Une réservation remplace le mode d'évaluation du stock par défaut d'un article. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-tracking.md).  

 La page **Réservation** est accessible à partir de toutes les lignes d'ordre à la fois des types demande et approvisionnement. Sur la page, l'utilisateur peut spécifier avec quelle écriture demande ou approvisionnement créer un lien réservation. La réservation comporte deux enregistrements qui partagent le même numéro de séquence. Un enregistrement contient un signe négatif et pointe vers la demande. L'autre enregistrement a un signe positif et pointe vers l'approvisionnement. Ces enregistrements sont stockés dans la table *Entrée de réservation* avec la valeur de statut *Réservation*. L'utilisateur peut afficher toutes les réservations sur la page **Écritures réservation**.  

### <a name="offsetting-in-reservations"></a>Compensation dans les réservations

 Les réservations sont effectuées par rapport aux quantités disponibles article. La disponibilité article est calculée en termes de base comme suit :  

 `available quantity = inventory + scheduled receipts - gross requirements`

 Le tableau suivant montre les détails des entités réseau d'ordres qui font partie du calcul de disponibilité.  

||Champ dans l’élément T27|Table source|Filtre table|Champ origine|  
|-|------------------|------------------|------------------|------------------|  
|**Inventaire**|Stock|Écriture article|N/A|Quantité|  
|**Réceptions programmées**|FR bon réception (qté)|Ligne bon de prod.|=Planifié ferme|Quantité restante (base)|  
|**Réceptions programmées**|Bon de réception assorti (qté)|Ligne bon de prod.|=Libéré|Quantité restante (base)|  
|**Réceptions programmées**|Qté sur ordre d'assemblage|En-tête d'assemblage|=Ordre|Quantité restante (base)|  
|**Réceptions programmées**|Quantité sur bon de commande|Ligne achat|=Ordre|Quantité en suspens (base)|  
|**Réceptions programmées**|Réception transfert (qté)|Ligne transfert|N/A|Quantité restante|  
|**Besoins brut**|Qté sur document de vente|Ligne de paiement|=Ordre|Quantité en suspens (base)|  
|**Besoins brut**|Besoin prévu (quantité)|Composante bon de prod.|<>Simulé|Quantité restante (base)|  
|**Besoins brut**|Qté sur composante d'assemblage|Ligne assemblage|=Ordre|Quantité restante (base)|  
|**Besoins brut**|Livraison transfert (qté)|Ligne transfert|N/A|Quantité restante|  

 Pour plus d'informations, voir [Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md).  

### <a name="manual-reservation"></a>Réservation manuelle

Lorsqu'un utilisateur crée une réservation intentionnellement, l'utilisateur gagne la propriété complète et la responsabilité et de ces articles. Cela signifie que l'utilisateur doit également modifier manuellement ou annuler une réservation. De telles modifications manuelles peuvent entraîner une modification automatique des réservations concernées.  

Le tableau suivant indique quand et quelles modifications peuvent survenir :  

|Action de l'utilisateur|Réaction du système|  
|-----------------|---------------------|  
|Diminution de la quantité réservée|Les champs de quantité associés sont mis à jour.|  
|Modification des champs date|Les champs de date associés sont mis à jour.<br /><br /> **Remarque :** si la date d'échéance sur une demande est modifiée pour précéder la date de livraison ou la date d'échéance de l'approvisionnement, la réservation est annulée.|  
|Suppression de la commande.|La réservation est annulée.|  
|Modification de l'emplacement, de la zone, de la variante, du numéro de série ou du numéro de lot|La réservation est annulée.|  

> [!NOTE]  
> La fonctionnalité Lien tardif peut également modifier des réservations sans informer l'utilisateur, en remaniant des réservations non spécifiques de numéros de série ou de lot. Pour plus d’informations, reportez-vous à [Détails de conception : traçabilité et réservations](design-details-item-tracking-and-reservations.md).  

### <a name="automatic-reservations"></a>Réservations automatiques

 La fiche article peut être configurée pour être toujours réservée automatiquement à partir de la demande, par exemple, des documents de vente. Dans ce cas, la réservation est effectuée par rapport à l'inventaire, aux bons de commande, aux ordres d'assemblage et aux bons de production. Un avertissement est émis si l'approvisionnement est insuffisant.  

 De plus, les articles sont réservés automatiquement par diverses fonctions de planification afin de suivre une demande liée à un approvisionnement spécifique. Les entrées de suivi de commande pour ces liens de planification contiennent **Réservation** dans le champ **Statut de réservation** de la table *Entrée de réservation* . Les réservations automatiques sont créées dans les cas suivants :  

- Ordre de fabrication multi-niveaux où le champ **Mode de lancement** des articles enfants et parents associés est défini sur **Fabrication à la commande**. Le système de planification crée des réservations entre l’ordre de production élément parent et les ordres de production sous-jacents pour garantir qu’ils sont traités ensemble. Un tel lien de réservation remplace la méthode par défaut d’évaluation du coût et d'affectation de l’article.  

- Un bon de production, un assemblage ou un bon de commande dont le champ **Politique réapprovisionnement** de l'article concerné est défini sur **Commande**. Le système de planification crée des réservations entre la demande et l'approvisionnement planifié pour s'assurer que l'approvisionnement spécifique est créé. Pour plus d'informations, reportez-vous à [Commande](design-details-handling-reordering-policies.md#order).  

- Un bon de production créé à partir d'un document de vente avec la fonction **Planification document de vente** est lié au document de vente avec une réservation automatique.  

- Un ordre d’assemblage créé automatiquement pour une ligne de commande client afin de respecter la quantité indiquée dans le champ  **Qté à assembler pour commander** . Cette réservation automatique lie la demande de vente et l'approvisionnement d'assemblage afin que les préparateurs de documents de vente puissent personnaliser et assurer l'élément d'assemblage directement au client. En outre, la réservation lie le résultat d'assemblage à la ligne document de vente via l'activité d'expédition qui répond à la commande client.  

Dans le cas d’une offre ou d’une demande non allouée, le système de planification attribue automatiquement un statut de réservation de type **Surplus**. Cela peut être le résultat de la demande qui est due aux quantités prévues ou des paramètres de planification saisis par l'utilisateur. Il s’agit d’un excédent légitime, que le système reconnaît, et qui ne donne pas lieu à des messages d’action. Un excédent peut également être véritable, un excédent d'approvisionnement ou une demande qui reste non chaînée. Il s'agit d'une mention d'un déséquilibre dans le réseau d'ordres, qui conduit le système à émettre des messages d'action. Notez qu'un message d'action qui propose une modification de quantité fait toujours référence au type **Excédent**. Pour plus d’informations, consultez la section [Exemple : suivi des commandes dans les ventes, la production et les transferts](#example-order-tracking-in-sales-production-and-transfers) de cet article.  

Les réservations automatiques qui sont créées lors de l'exécution de la planification sont traitées comme suit :  

- Ils sont appliqués aux quantités d’articles qui font partie du calcul de disponibilité, tout comme les réservations manuelles. Pour plus d’informations, consultez la section "Compensation dans les réservations" de cet article.  

- Ils sont inclus et potentiellement modifiés dans les exécutions de planification ultérieures, contrairement aux éléments réservés manuellement.  

## <a name="order-tracking"></a>Suivi de commande

Le chaînage aide le gestionnaire à conserver un programme d'approvisionnement valide en fournissant un aperçu du décalage entre la demande et l'approvisionnement dans le réseau d'ordres. L'enregistrement du suivi de commande sert de base pour créer les messages d'action dynamiques et les propositions ligne planification lors de l'exécution de la planification.  

> [!NOTE]  
> Le système de chaînage compense le stock disponible à mesure que les commandes sont saisies dans le réseau d'ordres. Cela implique que le système ne priorise pas les commandes qui peuvent être plus urgentes en termes de date d'échéance. C'est à la logique du système de planification ou à la sagesse du gestionnaire de réorganiser les priorités d'une manière explicite.  

> [!NOTE]  
> La politique de suivi des commandes et la fonction Obtenir des messages d’action ne sont pas intégrées aux projets. Cela signifie qu’une demande liée à un projet n’est pas automatiquement suivie. Étant donné qu’il n’est pas suivi, il peut entraîner l’utilisation d’un réapprovisionnement existant avec suivi des informations de projet sur une autre demande, par exemple, un document de vente. Par conséquent, vous pouvez rencontrer la situation dans laquelle les informations sur l'inventaire disponible ne sont pas synchronisées.  

### <a name="the-order-network"></a>Le Réseau d’ordres

Le système de suivi de commande est basé sur le principe que le réseau d'ordres doit toujours être dans un état d'équilibre, dans lequel chaque demande qui entre dans le système est compensée par un approvisionnement correspondant et vice versa. Le système fournit ceci en identifiant les liens logiques entre toutes les écritures de de mande et d'approvisionnement dans le réseau de commandes.  

Ce principe implique qu’un changement dans une demande entraîne un déséquilibre correspondant du côté de l’approvisionnement du réseau d’ordres. Inversement, une modification d'approvisionnement entraîne un déséquilibre correspondant du côté de la demande du réseau d'ordres. En réalité, le réseau d'ordres se trouve dans un état de flux constant tant que les utilisateurs saisissent, modifient et suppriment des commandes. Le chaînage traite les commandes dynamiquement, en réagissant à chaque modification au moment où elle entre dans le système et devient une partie du réseau d'ordres. Dès que de nouveaux enregistrements de chaînage sont créés, le réseau d'ordres est équilibré, mais uniquement jusqu'à la prochaine modification.  

Pour augmenter la transparence des calculs dans le système de planification, la page **Éléments planification non suivis** affiche les quantités non suivies, qui représentent la différence de quantité entre la demande connue et l’approvisionnement proposé. Chaque ligne de la page fait référence à la cause de l'excédent, par exemple, **Commande permanente**, **Niveau de stock de sécurité**, **Quantité de réapprovisionnement fixe**, **Qté minimum commande**, **Arrondissement** ou **Seuil**.  

### <a name="offsetting-in-order-tracking"></a>Compensation dans le chaînage

Contrairement aux réservations, qui ne peuvent être exécutées que pour des quantités d'article disponibles, le chaînage est possible sur toutes les entités réseau de commande qui sont incluses dans le calcul des besoins nets du système de planification. Les besoins nets sont calculés comme suit :  

`net requirements = gross requirements + reorder point - scheduled receipts - planned receipts - projected available balance`  

> [!NOTE]  
> Une demande liée aux paramètres de prévisions ou de planification n'est pas chaînée.  

### <a name="example-order-tracking-in-sales-production-and-transfers"></a>Exemple : suici de commande dans les ventes, production et transferts

Le scénario suivant montre quelles entrées de suivi de commande sont créées dans la table *Entrée de réservation* à la suite de diverses modifications du réseau de commande.  

Prenez l'exemple des données suivantes pour deux articles configurés pour le chaînage.  

|Article|Paramètre|Détails|
|-|-|-|
|Article 1|Nom|Composante|
||Disponibilité|100 unités dans l'emplacement EAST<br /><br />- 30 unités de LOTA<br />- 70 unités de LOTB|  
|Article 2|Nom|Article produit|
||Nomenclature de production|1 qté par composant|  
||Demande|Vente de 100 unités à l'emplacement WEST|  
||Approvisionnement|Ordre de fabrication lancé (généré avec la fonction *Planification des commandes client* pour la vente de 100 unités)|  

Sur la page **Configuration de fabrication**, le champ **Composants à l’emplacement** est défini sur *EST*.

Les entrées de suivi de commande suivantes existent dans la table *Entrée de réservation* en fonction des données de la table.  

<!--![First example of order tracking entries in Reservation Entry table.](media/supply_planning_RTAM_1.png "supply_planning_RTAM_1")  -->
**Entrées de réservation**

|N° d’écriture|Positif|Nombre d'articles|Code d’emplacement|Quantité|État de réservation|Désignation|N° lot|Type source|Code source|Consolidation|  
|--------|--------|--------|-------------|--------|------------------|-----------|-------|-----------|---------|-------| 
|8|-|COMPOSANT|EST|-70|Suivi|Composante|-|5407|101004|-|
|8|Oui|COMPOSANT|EST|70|Suivi|Composante|Lot B|32|-|-| 
|9|-|COMPOSANT|EST|-30|Suivi|Composante|-|5407|1001004|-| 
|9|Oui|COMPOSANT|EST|30|Suivi|Composante|LOTA|32|-|-| 
|10|-|ARTICLE PRODUIT|OUEST|-100|Réservation|Article produit|-|37|1001|Ordre pour ordre|
|10|Oui|ARTICLE PRODUIT|OUEST|100|Réservation|Article produit|-|5406|101004|Ordre pour ordre|


#### <a name="entry-numbers-8-and-9"></a>Numéros d’écriture 8 et 9

Pour les besoins en composants LOTA et LOTB respectivement, des liens de suivi de commande sont créés à partir de la demande dans la table 5407, *Composant de commande de production*, vers l’approvisionnement dans la table 32, *Écriture de grand livre d’articles*. Le champ  **Statut de réservation** contient *Suivi* pour indiquer que ces entrées sont des liens de suivi de commande dynamiques entre offre et demande.  

> [!NOTE]  
> Le champ **N° lot** est vide sur les lignes demande, parce que les numéros de lot ne sont pas spécifiés sur les lignes composante du bon de production libéré.  

#### <a name="entry-number-10"></a>Numéro écriture 10

À partir de la demande de vente dans la table 37, *Lignes de vente*, un lien de suivi de commande est créé vers l’approvisionnement dans la table 5406, *Ligne de commande de production*. Le champ  **Statut de réservation** contient *Réservation*, et le champ  **Liaison** contient *Ordre à ordre*. Cela est dû au fait que l’ordre de fabrication publié a été généré spécifiquement pour la commande client et doit rester lié, contrairement aux liens de suivi de commande avec un statut de réservation de Suivi, qui est créé et modifié de manière dynamique. Pour plus d’informations, consultez la section  [Réservations automatiques](#automatic-reservations) de cet article.  

 À ce stade dans ce scénario, les 100 unités de LOTA et LOTB sont transférées à l'emplacement WEST par un ordre de transfert.  

> [!NOTE]  
> Seule la livraison de l'ordre de transfert est reportée à ce stade, mais pas la réception.  

 Les entrées de suivi de commande suivantes existent désormais dans la table *Entrée de réservation* .  

<!-- ![Second example of order tracking entries in Reservation Entry table.](media/supply_planning_RTAM_2.png "supply_planning_RTAM_2")  -->
**Entrées de réservation**

|N° d’écriture|Positif|Nombre d'articles|Code d’emplacement|Quantité|État de réservation|Désignation|N° lot|Type source|Code source|Consolidation|  
|---------|--------|--------|-------------|--------|------------------|-----------|-------|-----------|---------|-------| 
|9|-|COMPOSANT|EST|-30|Excédent|Composante|-|5407|1001004|-| 
|10|-|ARTICLE PRODUIT|OUEST|-100|Réservation|Article produit|-|37|1001|Ordre pour ordre|
|10|Oui|ARTICLE PRODUIT|OUEST|100|Réservation|Article produit|-|5406|101004|Ordre pour ordre|
|12|Oui|COMPOSANT|OUEST|70|Excédent|Composante|Lot B|5741|1011|-| 
|14|Oui|COMPOSANT|OUEST|30|Excédent|Composante|LOTA|5741|1011|-| 
|15|Oui|COMPOSANT|OUT.JOURNAL.|70|Excédent|Composante|Lot B|32|-|-| 
|16|Oui|COMPOSANT|OUT.JOURNAL.|30|Excédent|Composante|LOTA|32|-|-| 

#### <a name="entry-numbers-8-and-9-1"></a>Numéros d’écriture 8 et 9

Les entrées de suivi de commande pour les deux lots du composant reflétant la demande dans la table 5407 sont modifiées d’un statut de réservation de *Suivi* à *Surplus*. La raison est que les approvisionnements qui ont été liés précédemment, dans la table 32, ont été utilisés par la livraison de l'ordre de transfert.  

Un excédent véritable, comme dans ce cas, reflète un excédent d'approvisionnement ou de demande qui reste non chaîné. Il s’agit d’une indication de déséquilibre dans le réseau de commandes, qui générera un message d’action par le système de planification à moins qu’il ne soit résolu de manière dynamique.  

#### <a name="entry-numbers-12-to-16"></a>Numéros d’écriture 12 à 16

Étant donné que les deux lots du composant sont enregistrés sur l’ordre de transfert comme expédiés mais non reçus, toutes les entrées de suivi de commande positives associées sont de type de réservation *Surplus*, indiquant qu’elles ne sont affectées à aucune demande. Pour chaque numéro de lot, une entrée se rapporte à la table 5741, *Ligne de transfert*, et une entrée se rapporte à l’écriture comptable des articles à l’emplacement de transit où les articles existent désormais.  

À ce pointer du scénario, l’ordre de transfert des composants de l’emplacement *EST* à *OUEST* est affiché comme reçu.  

Les entrées de suivi de commande suivantes existent désormais dans la table *Entrée de réservation* .  

<!-- ![Third example of order tracking entries in Reservation Entry table.](media/supply_planning_RTAM_3.png "supply_planning_RTAM_3") -->
 **Entrées de réservation**

|N° d’écriture|Positif|Nombre d'articles|Code d’emplacement|Quantité|État de réservation|Désignation|N° lot|Type source|Code source|Consolidation|  
|---------|--------|--------|-------------|--------|------------------|-----------|-------|-----------|---------|-------| 
|8|-|COMPOSANT|EST|-70|Excédent|Composante|-|5407|101004|-| 
|9|-|COMPOSANT|EST|-30|Excédent|Composante|-|5407|1001004|-|
|10|-|ARTICLE PRODUIT|OUEST|-100|Réservation|Article produit|-|37|1001|Ordre pour ordre|
|10|Oui|ARTICLE PRODUIT|OUEST|100|Réservation|Article produit|-|5406|101004|Ordre pour ordre|
|17|Oui|COMPOSANT|OUEST|70|Excédent|Composante|Lot B|32|-|-| 
|18|Oui|COMPOSANT|OUEST|30|Excédent|Composante|LOTA|32|-|-| 

Les entrées de suivi de commande sont désormais similaires au premier pointer du scénario, avant que l’ordre de transfert ne soit enregistré comme expédié uniquement, sauf que les entrées pour le composant ont désormais le statut de réservation *Surplus*. Cela est dû au fait que le composant nécessaire est toujours à l’emplacement *EST*, ce qui indique que le champ **Code d’emplacement** sur la ligne du composant de l’ordre de fabrication contient *EST* comme configuré dans le champ **Composants à l’emplacement** . L’approvisionnement qui a été alloué à cette demande auparavant a été transféré vers l’emplacement *OUEST*  et ne peut désormais plus être entièrement suivi, sauf si le besoin en composants sur la ligne de commande de production est modifié vers l’emplacement *OUEST* .  

Dans ce pointer du scénario, le **code d’emplacement** sur la ligne du composant de l’ordre de fabrication est défini sur *OUEST*. De plus, sur la page **Lignes de suivi des articles**, les 30 unités de LOTA et les 70 unités de LOTB sont affectées à la ligne de composant de l’ordre de fabrication.  

Les entrées de suivi de commande suivantes existent désormais dans la table *Entrée de réservation* .  

<!-- ![Fourth example of order tracking entries in Reservation Entry table.](media/supply_planning_RTAM_4.png "supply_planning_RTAM_4")   -->
 **Entrées de réservation**

|N° d’écriture|Positif|Nombre d'articles|Code d’emplacement|Quantité|État de réservation|Désignation|N° lot|Type source|Code source|Consolidation|  
|---------|--------|--------|-------------|--------|------------------|-----------|-------|-----------|---------|-------| 
|10|-|ARTICLE PRODUIT|OUEST|-100|Réservation|Article produit|-|37|1001|Ordre pour ordre|
|10|Oui|ARTICLE PRODUIT|OUEST|100|Réservation|Article produit|-|5406|101004|Ordre pour ordre|
|21|-|COMPOSANT|OUEST|-70|Suivi|Composante|Lot B|5407|101004|-| 
|21|Oui|COMPOSANT|OUEST|70|Suivi|Composante|Lot B|32|-|-| 
|22|-|COMPOSANT|OUEST|-30|Suivi|Composante|LOTA|5407|1001004|-| 
|22|Oui|COMPOSANT|OUEST|30|Suivi|Composante|LOTA|32|-|-| 

#### <a name="entry-numbers-21-and-22"></a>Numéros d’écriture 21 et 22

Étant donné que le besoin en composants a été modifié vers l’emplacement *OUEST* et que l’approvisionnement est disponible sous forme d’entrées de grand livre d’articles à l’emplacement *OUEST*, toutes les entrées de suivi de commande pour les deux numéros de lot sont désormais entièrement suivies, comme l’indique le statut de réservation de *Suivi*.  

Le champ **N° lot** est désormais renseigné dans l'écriture suivi de commande de la table 5407, car les numéros de lot ont été affectés aux lignes composante bon de production.  

## <a name="action-messaging"></a>Messagerie d’action

Lorsque le système de suivi d'ordre détecte un déséquilibre dans le réseau d'ordres, il crée automatiquement un message d'action pour en informer l'utilisateur. Les messages d'action sont des appels générés par le système en vue d'une action de l'utilisateur. Ils indiquent les détails du déséquilibre et suggèrent des propositions sur la façon de restaurer l'équilibre dans le réseau d'ordres. Elles s’affichent sous forme de lignes de planification sur la page  **Feuilles de travail de planification** lorsque vous choisissez l’action  **Obtenir des messages d’action** . En outre, des messages d’action s’affichent sur les lignes planification qui sont générés par l’exécution de la planification pour tenir compte des propositions du système de planification sur la façon de rétablir l’équilibre du réseau d’ordres. Dans les deux cas, les suggestions sont exécutées sur le réseau de commandes, lorsque vous choisissez l’action  **Exécuter le message d’action** .  

Un message d'action traite un seul niveau de nomenclature à la fois. Si l'utilisateur accepte le message d'action, cela peut produire des messages d'action supplémentaire au niveau de nomenclature suivant.  

Le tableau suivant montre les messages d'action existants.  

|Message d'action|Description|  
|--------------------|---------------------------------------|  
|**Changer qté**|Modifie la quantité d'une commande d'approvisionnement existante pour couvrir une demande modifiée ou nouvelle.|  
|**Replanifier**|Replanifie la date d'échéance sur un ordre de fabrication existant.|  
|**Replanifier & Changer qté**|Replanifie la date d'échéance et modifie la quantité de la commande existante.|  
|**Créer**|Crée une nouvelle commande si la demande ne peut être satisfaite par aucun des messages d’action précédents.|  
|**Annuler**|Annule un ordre de fabrication existant.|  

Le système de chaînage essaie toujours de résoudre un déséquilibre dans le réseau d'ordres existant. Si cela n’est pas possible, il émet un message d’action pour créer une nouvelle commande. Voici la liste par ordre de priorité que le système de chaînage utilise lorsqu'il détermine la manière de restaurer le solde. Si une demande supplémentaire est entrée dans le réseau d'ordres, le système cherche à faire un chaînage par les vérifications suivantes :  

1. Vérifier un approvisionnement excédentaire dans l'enregistrement existant de chaînage de cette demande.  
2. Vérifier les réceptions prévues et programmées par ordre de date de réception. La dernière date possible est sélectionnée.  
3. Vérifier le stock disponible.  
4. Vérifier si une commande d'approvisionnement apparaît dans l'enregistrement actuel du suivi de commande. Si tel est le cas, le système émet un message d’action de type *Modifier* pour augmenter la commande.  
5. Vérifier qu'aucune commande d'approvisionnement n'apparaît dans l'enregistrement actuel du suivi de commande. Si tel est le cas, le système émet un message d’action de type *Nouveau* pour créer une nouvelle commande.  

Une demande ouverte traverse la liste et compense l'approvisionnement disponible à chaque point. La demande restante est toujours couverte par la vérification 4 ou la vérification 5.  

Si une sortie dans la quantité demandée se produit, le système de suivi de commande tente de résoudre le déséquilibre en effectuant les vérifications précédentes dans l'ordre inverse. Cela signifie que les messages d'action existants peuvent être modifiés ou même supprimés, si nécessaire. Le système de chaînage présente toujours le résultat net de ses calculs à l'utilisateur.  

## <a name="order-tracking-and-planning"></a>Suivi de commande et planification

Lorsque le système de planification est exécuté, il supprime tous les enregistrements de suivi de commande et écritures de message d'action existants et les recrée en tant que suggestions de ligne de planification en fonction des paires approvisionnement/demande et priorités. Lorsque l'exécution de la planification a terminé, le réseau d'ordres est en équilibre.  

### <a name="planning-system-versus-order-tracking-and-action-messaging"></a>Comparaison entre système planification et suivi de commande et message d’action

 La comparaison suivante montre les différences entre les méthodes utilisées par le système de planification pour créer des propositions de ligne planification et les méthodes utilisées par le système de suivi de commande pour créer les enregistrements de suivi de commande et les messages d'action.  

- Le système de planification traite l'ensemble de la configuration de demande et d'approvisionnement d'un article particulier, alors que le chaînage traite la commande qui l'a activé.  

- Le système de planification traite tous les niveaux de hiérarchie de la nomenclature, alors que le chaînage traite un niveau de nomenclature à la fois.  

- Le système de planification crée des liens entre la demande et l'approvisionnement en fonction de la date d'échéance prioritaire. Le chaînage crée des liens entre la demande et l'approvisionnement en fonction de la séquence de saisie des commandes.  

- Le système de planification prend en compte les paramètres de planification, contrairement au suivi des commandes.  

- Le système de planification crée des liens dans un mode de lots activé par l'utilisateur lorsqu'il équilibre la demande et l'approvisionnement, alors que le chaînage crée des liens automatiquement et de façon dynamique lorsque l'utilisateur saisit les commandes.  

## <a name="see-also"></a>Voir aussi .

[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
