---
title: Tableau des entrées de réservation - Fonctionnalités qui mettent à jour le tableau des entrées de réservation | Microsoft Docs
description: Ceci fournit des conseils pour vous aider à comprendre et à résoudre les problèmes d’incohérence des données dans la table d’entrée de réservation.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 06/26/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="reservation-entry-table---introduction"></a>Tableau d’entrée de réservation - Introduction

Ce livre blanc technique fournit des conseils pour vous aider à comprendre et à résoudre les problèmes d’incohérence des données dans la table  *Entrée de réservation* (Tableau 337) dans Microsoft Dynamics NAV. La première partie est une introduction aux fonctionnalités qui génèrent ou modifient les données dans cette table. Il couvre également plusieurs champs de la table  *Entrée de réservation* qui méritent d’être soulignés par rapport à ces fonctionnalités. La deuxième partie montre, à l’aide d’exemples, comment les entrées de la table  *Entrée de réservation* sont générées, supprimées ou modifiées lorsque les ordres de transfert sont traités ou que les fonctionnalités de planification sont exécutées.

La table *Entrée de réservation* est utilisée pour gérer et stocker les informations concernant la réservation, le suivi des articles et le suivi des commandes.

Lors du traitement du suivi des articles avec une comptabilisation partielle, le tableau fonctionne en conjonction avec le tableau  *Spécification de suivi* (tableau 336). Les données saisies dans la page  **Lignes de suivi des articles** par l’utilisateur sont créées dans une version temporaire de la table 336 et sont validées dans la table 337 et la table de spécifications de suivi lorsque la page est fermée.

En termes généraux, les données générées dans la table  *Entrée de réservation* dépendent des fonctionnalités que vous utilisez et des paramètres que vous avez sélectionnés sur l’élément carte. Ceux-ci inclus :

- Politique de suivi des commandes
- Politique de réservation
- Fonctionnalités de planification exécutées
- Politique de réapprovisionnement et de fabrication
- Paramètres de planification sur l’article ou l’unité de gestion des stocks carte
- Code traçabilité article

## <a name="features-that-update-the-reservation-entry-table"></a>Fonctionnalités qui mettent à jour la table des entrées de réservation

### <a name="order-tracking-policy"></a>Politique de suivi des commandes

Si le champ  **Politique de suivi des commandes** d’un article est défini sur Aucun, Microsoft Dynamics NAV ne créera jamais d’entrées de réservation dans la table *Entrée de réservation*, sauf si le plan de changement net ou le plan de régénération, la réservation ou le suivi des articles est exécuté. De plus, sans suivi des commandes activé, vous pouvez avoir des entrées de réservation lorsque vous utilisez les politiques de fabrication sur commande ou d’assemblage sur commande.

Vous pouvez envisager de définir la  **Politique de suivi des commandes** sur Aucun si vous n’avez pas besoin de suivre à la volée une demande par rapport à une offre ou vice versa. Le suivi de l’offre par rapport à la demande est géré par la fonctionnalité de suivi des commandes ou par le moteur de planification. Nous vous déconseillons d’utiliser le suivi des commandes avec la fonctionnalité de planification.

Lorsque vous définissez le champ  **Politique de suivi des commandes** sur Suivi uniquement, Microsoft Dynamics NAV des entrées seront toujours créées dans la table 337 chaque fois qu’une commande est créée pour l’article, mais le **Statut de réservation** dans la table 337 n’est pas toujours strictement défini sur Suivi. Considérez le scénario suivant :

> [!NOTE]  
> La date de travail est fixée au 23/01/2014 (MM/JJ/AAAA) pour tous les exemples. 
  
1. Créez un article avec le champ  **Politique de suivi des commandes** défini sur Suivi uniquement.  
1. Créez un bon de commande. Microsoft Dynamics NAV créera une entrée de réservation avec le **Statut de réservation** Surplus, puisque la commande d’achat n’est pas encore attribuée à une demande.
1. Créez un document de vente. Microsoft Dynamics NAV va maintenant créer une autre entrée de réservation avec un **statut de réservation** de Suivi.

Le **statut de réservation** créé dans étape 2 sera mis à jour en Suivi ; ceci est géré automatiquement. Microsoft Dynamics NAV  Ce concept est appelé suivi dynamique.
En définissant le champ  **Politique de suivi des commandes** de l’article sur Suivi uniquement, un utilisateur final peut utiliser la fonction de suivi des commandes pour obtenir un aperçu de l’offre à laquelle la demande est allouée et vice versa.

> [!NOTE]  
> La fonctionnalité de suivi ne remplace pas la fonctionnalité de planification, qui prend en compte tous les articles, demandes et fournitures ensemble pour fournir des propositions de planification optimales afin d’optimiser les niveaux de service client et d’équilibrer les niveaux de stock.

### <a name="reservation-policy"></a>Politique de réservation

Une réservation se compose d’une paire d’enregistrements dans la table *Entrée de réservation* avec un **Statut de réservation** de Réservation, qui partage le même numéro d’entrée. Un enregistrement a le champ Positif activé et pointe vers l’approvisionnement. L’autre enregistrement a le champ  **Positif** non activé et pointe vers la demande. Les champs **Type de source**, **N° de référence de la source** et **ID de la source** mettent en évidence le lien de réservation entre la demande et l’offre.

Les informations dans le champ  **Type de source** correspondent à la table à laquelle le champ  **Numéro d’entrée** de réservation est lié. Par exemple, s’il s’agit d’une entrée de demande (négative), il peut s’agir de la table  *Commande client* (Tableau 37) ou du  *Composant de planification* (Tableau 99000829).

Le champ  **ID source** contient l’ID du document dans la table référencée par le type de source.

La **référence source. N°** Le champ contient un numéro de référence pour la ligne, dont la réservation **Numéro d’entrée**  est liée à. Si l’entrée est liée à une ligne de vente ou d’achat, à une ligne de journal ou à une ligne de demande, les informations de ce champ sont copiées à partir de la ligne de commande. **Numéro de ligne** . S’il s’agit d’une entrée dans la table *Écriture comptable d’article*  (tableau 32), les informations de ce champ sont copiées à partir du champ **Numéro d’entrée** de la table *Écriture comptable d’article* .

Lorsque vous utilisez l’option de politique de réservation Toujours en combinaison avec le suivi des commandes, les deux sont normalement synchronisés. Cependant, lorsque la réservation est supprimée ou que la date de réception de l’approvisionnement est avancée au-delà de la date d’échéance de la demande, le suivi des commandes sera supprimé. Vous pouvez également rencontrer un message d’erreur, dans lequel Microsoft Dynamics NAV vous demande quoi faire avec les réservations existantes. Ce scénario est illustré dans l’exemple suivant :

1. Créez un nouvel élément appelé COMP. Définissez les champs suivants :
  - **Système de réapprovisionnement** : achat
  - **Politique de suivi des commandes** : Suivi uniquement
  - **Réserve** : Toujours
2. Créez un deuxième élément appelé FG. Définissez les champs suivants :
  - **Système de réapprovisionnement** : Commande de produit
  - **Politique de suivi des commandes** : Suivi uniquement
  - **Réserve** : Toujours
3. Créez un deuxième élément appelé FG. Définissez les champs suivants :
  - **Article** : COMP
  - **Quantité par** : 1
4. Certifier le numéro de nomenclature de production BOM FG et l’attribuer à l’article FG.
5. Créez un bon de commande. Définissez les champs suivants :
  - **Article** : COMP
  - **Quantité** : 10
  - **Code de localisation** : BLEU
  - **Date de réception prévue** : 24/01/2014
6. Créez un document de vente. Définissez les champs suivants :
  - **Date d’expédition** : 14/02/2014
  - **Code de localisation** : BLEU
  - **Article** : COMP
  - **Quantité** : 10

> [!NOTE]  
> Une réservation automatique a été exécutée entre la commande d’achat et la commande de vente. De plus, un suivi des commandes a été créé entre les commandes d’achat et de vente.

7. Créez un ordre de fabrication lancé manuellement. Définissez les champs suivants :
  - **Article** : 14/02/2014
  - **Quantité** : 10
  - **Localisation** : BLEU
  - **Date d’échéance** : 01/02/2014
8. Dans l’onglet **Accueil**, dans le groupe Processus, choisissez **Actualiser l’ordre de fabrication**.
9. Ouvrez la liste des composants et recherchez l’élément COMP.

> [!NOTE]  
> Aucune réservation ni suivi de commande n’est créé par Microsoft Dynamics NAV. La raison est qu’une réservation existe déjà sur la commande client créée dans étape 6.

Supposons que, pour des raisons commerciales, l’article soit nécessaire de manière plus urgente sur l’ordre de fabrication lancé créé dans étape 7. Ensuite, dans les étapes suivantes, nous Terminé la réservation de la commande client qui a été créée dans étape 6 et remarquons comment le suivi des commandes est géré.

10. Recherchez la commande client pour l’article COMP de étape 6 et Annuler la réservation.
11. Ouvrez le bon de commande à partir de étape 5 et remarquez que le suivi de commande est désormais créé entre le bon de commande et le composant nécessaire à partir de l’ordre de fabrication lancé.
12. Recréez la réservation entre le composant nécessaire à partir de l’ordre de fabrication lancé et l’approvisionnement à partir de la commande d’achat dans étape 5.

> [!NOTE]  
> La réservation n’est pas recréée, ce qui doit être fait manuellement.

13. Modifiez le champ  **Date de réception prévue** sur l’en-tête du bon de commande au numéro étape 5 du 24/01/2014 au 05/02/2014.

Microsoft Dynamics NAV affichera le message d’avertissement suivant :

   Des réservations existent pour cette commande. Ces réservations seront annulées si un conflit de données est causé par ce changement. Souhaitez-vous continuer?

14. Choisissez Oui. Recherchez les entrées de réservation et de suivi de commande à partir du bon de commande.

> [!NOTE]  
> La réservation existante est annulée et devra être recréée manuellement. La commande est cependant dynamique et a été recréée par Microsoft Dynamics NAV pour exister entre le bon de commande et le bon de commande. La raison est que la demande de l’ordre de production lancé (02/01/2014) est antérieure à la date de réception prévue de la fourniture.

Ceci conclut la démonstration de l’interaction entre l’utilisation des réservations automatiques et le suivi des commandes. Les exemples montrent également ce qui se passe lorsque vous modifiez les dates d’échéance et le message d’erreur qui est déclenché en cas de conflit de réservation.

### <a name="planning-calculated"></a>Planification calculée

La planification Terminé à l’aide de la planification des commandes, de la feuille de calcul de demande ou de la feuille de calcul de planification générera des entrées dans la table *Entrée de réservation* avec le champ **Statut de réservation** défini sur Suivi, Réservation ou Surplus. Il doit toujours y avoir une paire correspondante avec le même numéro d’entrée de valeur positive et négative dans le champ  **Quantité (base)** lorsque le statut est Suivi ou Réservation. Le champ  **Type de source** sera le type de demande, c’est-à-dire la table 37 pour la quantité négative et une table de planification, par exemple la table 246, pour la quantité positive. Le champ  **ID source** sera PLANNING.

En cas d’offre ou de demande non allouée, Microsoft Dynamics NAV définira le champ **Statut de réservation** sur Surplus. Par exemple, vous pouvez avoir un statut de réservation Surplus lorsque l’inventaire existant est inférieur à la quantité du stock de sécurité ou que la demande est liée aux prévisions.

La table *Élément de planification non suivi* (Table 99000855) contient des informations sur les quantités non suivies affichées lorsque l’utilisateur effectue une recherche à partir de la page de suivi des commandes pour voir les quantités non suivies ou choisit une icône d’avertissement dans la feuille de calcul de planification. Le tableau contient des entrées qui représentent une quantité excédentaire non suivie dans le réseau de suivi des commandes.

Ces écritures sont générées au cours de l'exécution de la planification et expliquent la provenance de la quantité excédentaire non chaînée des lignes chaînage. Cet excédent non chaîné peut provenir des lignes suivantes :

- Prévisions production ;
- Commandes permanentes
- Stock de sécurité ;
- Point de commande ;
- Inventaire maximum
- Quantité de réappro. ;
- Qté maximum commande ;
- Qté minimum commande ;
- Commandé par ;
- Seuil (% taille lot).

Dans la table *Entrée de réservation*, comme dans les ordres d’achat, de transfert et de production, il existe un champ **Flexibilité de planification** . Ce champ d’option définit si l’approvisionnement représenté par ces commandes d’approvisionnement est pris en compte par le système de planification lors du calcul des messages d’action. Si le champ contient l’option Illimité, le système de planification inclut la ligne lors du calcul des messages d’action. Si le champ contient l’option Aucun, la ligne est ferme et immuable, et le système de planification n’inclut pas la ligne lors du calcul des messages d’action. La fonctionnalité est gérée dans la table *Entrée de réservation* par le champ portant le même nom.

### <a name="reordering-and-manufacturing-policy"></a>Politique de réapprovisionnement et de fabrication

Si une fonctionnalité de planification est exécutée pour un ensemble d’articles avec la politique de réapprovisionnement définie sur Commande, Microsoft Dynamics NAV créera des entrées dans la table *Entrée de réservation* avec le statut de réservation de type Réservation au lieu de Suivi.

Les champs  **Type de source** et **ID de la source** auront le traitement équivalent des autres politiques de réorganisation. Cependant, dans le champ **Liaison** de la table *Entrée de réservation*, Microsoft Dynamics NAV saisira Ordre à Ordre.

Le champ  **Liaison** est renseigné pour contrôler les commandes d’approvisionnement liées à une demande spécifique, par exemple, les ordres de fabrication créés directement à partir d’une commande client. Le champ affiche Commande à commande lorsque l’entrée est liée spécifiquement à une demande ou à une offre (réservation automatique). La demande peut être liée aux ventes ou aux besoins en composants.

### <a name="item-tracking-and-prospect-reservation-entry"></a>Suivi des articles et saisie des réservations de prospects

Le statut de réservation Prospect peut être créé dans la table  Microsoft Dynamics NAV Entrée de réservation *lorsque vous n’utilisez aucune entité de réseau de commande, c’est-à-dire le suivi des commandes.*  Par exemple, sur une ligne de journal de consommation, vous affectez le suivi des articles au composant. Cependant, si l’article fait déjà l’objet d’un suivi de commande, cela peut créer davantage d’entrées de réservation de prospects. Microsoft Dynamics NAV  Ceci est démontré dans l’EXEMPLE 2 relatif aux ordres de transfert dans la deuxième partie de ce document.

Lorsque vous affichez ou modifiez la page **Lignes de suivi d’article**, le contenu collectif de la table *Spécification de suivi* (tableau 336) et de la table *Entrée de réservation* est présenté dans une version temporaire du tableau 336. Ceci garantit que les données de suivi article historiques et actives sont accessibles en même temps.

Les réservations se répartissent en deux catégories : les réservations non spécifiques, où les numéros de lot et de série ne sont pas spécifiés au moment de la réservation, et les réservations spécifiques, où vous réservez des numéros de lot ou de série spécifiques à partir de l’inventaire.

Lors d’une réservation non spécifique, le champ  **Numéro de lot** ou **Numéro de série** est vide dans le **Numéro d’entrée** de la table 337 pointant vers la demande (par exemple, la vente). En raison de la structure de la logique de réservation dans Microsoft Dynamics NAV, lorsque vous placez une réservation non spécifique sur un article suivi dans l’inventaire, Microsoft Dynamics NAV vous devez néanmoins créer des entrées de grand livre d’articles spécifiques pour effectuer une réservation.

Étant donné que les écritures du grand livre des articles contiennent les informations de suivi des articles, la réservation réserve indirectement des numéros de lot ou de série spécifiques, même si l’utilisateur ne l’avait pas prévu. Cependant, avec la reliure tardive, des réserves sont toujours émises contre des entrées spécifiques, mais un mécanisme de remaniement est ensuite utilisé lors de la publication. Microsoft Dynamics NAV  Microsoft Dynamics NAV 

Pour plus d’informations, consultez les Microsoft Dynamics NAV livres blancs techniques répertoriés dans les ressources supplémentaires à la fin de ce document.

### <a name="source-subtype-suppressed-action-msg-action-message-adjustment-and-disallow-cancellation-fields"></a>Champs Sous-type de source, Message d’action supprimé, Ajustement du message d’action et Interdire l’annulation

Les champs  **Sous-type de source**, **Message d’action supprimé**, **Ajustement du message d’action** et **Interdire l’annulation** dans la table *Entrée de réservation* sont décrits dans cette section. Des scénarios sont fournis pour démontrer l’utilisation des champs **Message d’action supprimé**, **Ajustement du message d’action** et **Interdire l’annulation** . Le champ  **Ajustement du message d’action** est utilisé pour la fonctionnalité de politique de suivi des commandes Suivi et message d’action. Le champ  **Interdire l’annulation** est utilisé pour la fonctionnalité Assemblage sur commande dans Microsoft Dynamics NAV 2013.

#### <a name="source-subtype"></a>Sous-type origine

Le champ  **Sous-type de source** indique à quel sous-type de source l’entrée de réservation est liée. Si l’entrée est liée à une ligne d’achat ou de vente, le champ est copié à partir du champ  **Type de document** sur la ligne. S’il est lié à une ligne de journal, le champ est copié à partir du champ  **Type d’entrée** sur la ligne de journal.

#### <a name="suppressed-action-msg"></a>Message d'action supprimé

Le champ  **Message d’action supprimé** enregistre lorsqu’un approvisionnement existant a déjà été partiellement traité, par exemple lorsqu’une commande d’achat a déjà été partiellement reçue ou lorsqu’un ordre de fabrication a des consommations enregistrées.

Lorsque la planification est exécutée, Microsoft Dynamics NAV marque ce champ et définit le champ **Statut de l’entrée de réservation** sur *Surplus8. L’exemple suivant sert d’illustration :

1. Ouvrir l’article 80001. Définissez les champs suivants :
  - **Politique de réapprovisionnement** : lot par lot
  - **Réserve** : Facultatif
  - **Politique de suivi des commandes** : Aucune
2. Créez un document de vente. Définissez les champs suivants :
  - **Article** : 80001
  - **Emplacement** : Vide/Aucun
  - **Quantité** : 10
  - **Date d’expédition** : 15/02/2014
3. Ouvrez les **Feuilles de travail de demande** et exécutez la tâche par lots **Calculer le plan** pour l’article 80001.
  - **Date de début** : 23/01/2014
  - **Date de fin** : 01/03/2014
4. Une suggestion de planification est donnée pour réapprovisionner une quantité de 10 avec un nouveau bon de commande et une **date d’échéance** 02/15/2014.
5. Dans l’onglet **Actions**, dans le groupe Fonctions, choisissez **Exécuter l’action** Message pour créer un bon de commande avec **Date de réception prévue** 02/15/2014.
6. Ouvrez le bon de commande de étape 5 et définissez **Qté à recevoir** sur 2 et enregistrez uniquement la réception.
7. Ouvrez la commande client de étape 2 et modifiez la **date d’expédition** en 02/10/2014.
8. Ouvrez les **feuilles de travail de demande** et exécutez **Calculer le plan** pour l’article 80001
  - **Date de début** : 23/01/2014
  - **Date de fin** : 01/03/2014
9. Une suggestion de planification est donnée pour réapprovisionner une quantité de 8 avec un nouveau bon de commande et une **date d’échéance** 02/10/2014.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

L’entrée n° 28 dans le tableau 337 a un statut de réservation Suivi pour correspondre à l’inventaire existant enregistré dans l’entrée du grand livre des articles 318 pour 2 unités et à la demande en cours dans le tableau des commandes clients 37. L’entrée suivante n° 29 a également le statut de réservation Suivi et relie la quantité restante de 8 unités entre la demande dans la table Commande client 37 et l’approvisionnement suggéré dans la table Ligne de demande 246.

L’entrée n° 30 est la commande d’achat existante qui a été partiellement reçue avec la quantité 2. Par conséquent, le champ  **Statut de réservation** est Surplus, et Microsoft Dynamics NAV définit le champ  **Quantité (base)** sur *8* (solde restant) et le champ  **Message d’action supprimé** est activé.

#### <a name="action-message-adjustment"></a>Réglage de message de tâche

Le champ  **Ajustement du message d’action** affiche la modification du côté de l’approvisionnement du suivi de commande qui résulte de l’acceptation des messages d’action associés. Une valeur apparaît ici uniquement lorsque les fonctionnalités de suivi des commandes et de messages d’action sont actives (politique de suivi des commandes définie sur Suivi et message d’action). La valeur est calculée en fonction des données de la table *Entrée de message d’action* (tableau 99000849). L’exemple suivant sert d’illustration :
1. Ouvrir l’article 80002. Définissez le champ suivant :
 - **Politique de suivi des commandes** : Suivi et message d’action.
2. Créez un document de vente. Définissez les champs suivants :
  - **Article** : 80002
  - **Localisation** : BLEU
  - **Quantité** : 100
3. Ouvrez la page  **Planification des commandes** et exécutez la tâche par lots  **Calculer le plan** .
4. Sélectionner la commande client de étape 2 et exécutez le travail par lots  **Créer des commandes** .
5. Sur la commande client de étape 2, modifiez le champ  **Quantité** de 100 à 105.
Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.
6. L’entrée n° 34 a le champ **Ajustement du message d’action** dans la table 337 activé pour 5 unités avec le statut de réservation Surplus. Comme la commande client a été augmentée à étape 5, Microsoft Dynamics NAV cette réservation a été créée car un approvisionnement supplémentaire est nécessaire.
7. Ouvrez la page **Feuilles de travail de planification** et dans l’onglet **Accueil**, dans le groupe **Processus**, choisissez **Obtenir des messages d’action**. Microsoft Dynamics NAV suggérera d’augmenter la quantité du bon de commande de 100 à 105.

#### <a name="disallow-cancellation"></a>Interdire l'annulation

Le champ  **Interdire l’annulation** indique que l’entrée de réservation représente le lien entre une ligne de commande client et un ordre d’assemblage. Vous ne pouvez pas supprimer cette réservation car elle est nécessaire pour maintenir la synchronisation qui se produit lorsqu’un article est assemblé sur commande. L’exemple suivant sert d’illustration :

1. Créez un bon de commande. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : Assemblage
  - **Politique d’assemblage** : assemblage sur commande
  - **Politique de suivi des commandes** : Suivi uniquement
2. Créez un nouvel élément appelé Assemble COMP. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : achat
  - **Politique de suivi des commandes** : Suivi uniquement
3. Ouvrez l’élément Assembler FG, et dans l’onglet **Naviguer**, dans le groupe **Assemblage/Production**, choisissez **Assemblage**, puis choisissez **Nomenclature d’assemblage**. Dans la nomenclature d’assemblage, définissez les champs suivants :
  - **Type** : Élément
  - **Non.**  : Assembler COMP
  - **Quantité par** : 1 Choisissez le bouton **OK** .
4. Ouvrez un journal d’articles et augmentez l’inventaire d’Assemble COMP à la quantité 10 par rapport à l’emplacement BLEU et enregistrez la ligne de journal.
5. Créez un document de vente. Définissez les champs suivants :
  - **Article** : Assembler FG
  - **Localisation** : BLEU
  - **Quantité** : 1 Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

L’entrée n° 82 a un statut de réservation excédentaire avec 9 unités de l’Assemble Comp en stock et n’a aucune demande. L’entrée n° 84 suit les entrées de réservation entre la demande sur la table 901 de la  *chaîne de montage* et son approvisionnement sur l’entrée 346 du grand livre des articles.

L’entrée n° 86 a un statut de réservation de commande à commande contraignante. De plus, le champ  **Interdire l’annulation** est activé car la politique d’assemblage est définie sur Assembler sur commande pour l’article Assemblage FG. Enfin, le champ  **Flexibilité de planification** est défini sur Aucun, car Microsoft Dynamics NAV cela ne permet pas à la logique de planification de supprimer la réservation.

#### <a name="quantity-available-to-pick-and-reservations"></a>Quantité disponible à cueillir et réservations

Le champ  **Quantité réservée à prélever et à expédier** de la table 337 qui existe dans les versions antérieures à Microsoft Dynamics NAV 2013 contrôle la disponibilité des articles dans un entrepôt géré. Dans toute installation de gestion d’entrepôt, les quantités d’articles existent à la fois sous forme d’entrées d’entrepôt et d’entrées de grand livre d’articles. Microsoft Dynamics NAV  Ces deux types d’entrée contiennent des informations différentes sur l’emplacement des éléments et leur disponibilité. Les écritures d'entrepôt définissent la disponibilité d'un article par zone et type de zone, qui est appelée contenu de la zone. Les écritures du grand livre d'articles définissent la disponibilité d'un article par sa réservation aux documents sortants. Une fonctionnalité spéciale existe dans l’algorithme de prélèvement pour calculer la quantité disponible pour le prélèvement lorsque le contenu du bac est associé aux réservations. L’algorithme de prélèvement soustrait les quantités réservées à d’autres documents sortants, les quantités figurant sur les documents de prélèvement existants et les quantités prélevées mais pas encore expédiées ou consommées. Le résultat s’affiche dans le champ  **Quantité disponible à prélever** de la page **Feuille de travail de sélection**, où le champ est calculé de manière dynamique. La valeur est également calculée lorsqu’un utilisateur crée des prélèvements d’entrepôt directement à partir de documents sortants tels que des commandes client, une consommation de production ou des transferts sortants.

*Quantité disponible à prélever = quantité dans les bacs de prélèvement - quantité sur prélèvements et mouvements – (quantité réservée dans les bacs de prélèvement + quantité réservée sur prélèvements et mouvements).*

L’exemple suivant illustre la manière dont la valeur de la quantité disponible à prélever est calculée dans Microsoft Dynamics NAV :

1. Créez un nouvel élément appelé Article d’entrepôt. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : achat
  - **Politique de réserve** : Toujours
  - **Politique de suivi des commandes** : Suivi uniquement
2. Créer un bon de commande auprès du fournisseur 60000. Définissez les champs suivants :
  - **Article** : Article d’entrepôt
  - **Localisation** : BLANC
  - **Quantité** : 100
3. Libérez la commande d’achat et créez le reçu d’entrepôt.
4. Enregistrez le reçu d’entrepôt et le rangement en entrepôt pour la quantité 100.
5. Créez un deuxième bon de commande auprès du fournisseur 60000. Définissez les champs suivants :
  - **Article** : Article d’entrepôt
  - **Localisation** : BLANC
  - **Quantité** : 10
6. Libérez la commande d’achat et créez le reçu d’entrepôt.
7. Postez UNIQUEMENT le récépissé d’entrepôt. N’enregistrez pas le rangement en entrepôt.
8. Créez un document de vente. Définissez les champs suivants :
  - **Article** : Article d’entrepôt
  - **Localisation** : BLANC
  - **Quantité** : 10 La quantité réservée est automatiquement définie sur 10 en raison de la politique de réserve définie sur Toujours.
9. Créez un document de vente. Définissez les champs suivants :
  - **Article** : Article d’entrepôt
  - **Localisation** : BLANC
  - **Quantité** : 100 La quantité réservée est automatiquement définie sur 100 en raison de la politique de réserve définie sur Toujours.
10. Lancez la première commande client de étape 8 et créez une expédition en entrepôt.
11. Libérez l’expédition de l’entrepôt et dans l’onglet **Actions**, choisissez **Créer une sélection**.
Le message d’erreur suivant s’affiche : *Rien à gérer.*
  La raison est que la quantité disponible à choisir est nulle. Cela se calcule comme suit : Quantité en stock = 110 Quantité disponible à la cueillette = 100

> [!NOTE]  
> La quantité rangée ou dans le bac de réception n’est pas disponible pour le prélèvement.
   
   Le total réservé aux commandes client est de 110. Quantité disponible pour prélèvement = 100 – 110 = zéro.

Lorsque le rangement en entrepôt est enregistré dans étape 7, cela permet la création du prélèvement en entrepôt dans étape 11. Dans les versions antérieures à Microsoft Dynamics NAV 2013, le champ Quantité réservée **à prélever et à expédier** dans la table 337 est renseigné par rapport à la réservation pour la quantité 10.

L’illustration suivante est tirée de Microsoft Dynamics NAV 2009 R2.

## <a name="illustrations-using-transfer-orders-and-planning"></a>Illustrations utilisant les ordres de virement et la planification

### <a name="transfer-orders"></a>Ordres de transfert

Lorsque vous utilisez des ordres de transfert et que l’article est expédié mais pas entièrement reçu, dans le tableau *Entrée de réservation*, vous obtenez un statut de réservation Surplus. Le code d’emplacement sera l’emplacement de transfert.

La **référence source. N°** Le champ est calculé par le dernier numéro d’entrée de ligne + le numéro d’entrée de ligne de l’article sur l’expédition de transfert enregistrée.

Lorsque le suivi des commandes est activé et qu’il n’y a pas de demande (commande client ou consommation), Microsoft Dynamics NAV crée deux entrées dans la table 337 avec le statut de réservation Surplus. L’une concerne la table  *Ligne de transfert* 5741 et l’autre la table Écriture du grand livre des articles 32.

Ceci est démontré dans le premier exemple.

#### <a name="example-1"></a>Exemple 1

1. Ouvrez les éléments 80003 et 80004 et définissez le champ  **Politique de suivi** sur *Suivi uniquement*. Laissez les autres champs par défaut.
2. Ouvrez un journal d’articles et augmentez l’inventaire de ces articles à une quantité de 10 chacun par rapport à l’emplacement ROUGE et enregistrez les lignes du journal.
3. Créez un ordre de transfert de l’emplacement ROUGE vers BLEU pour ces deux articles : article 80003 sur la ligne 10000 de l’ordre de transfert et article 80004 sur la deuxième ligne 20000, tous deux pour 10 unités.
4. Postez uniquement la partie expédition de l’ordre de transfert sans aucune fonctionnalité d’entrepôt.
L’expédition de transfert affichée est présentée dans l’illustration suivante.
Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.
5. Comparez les résultats de l’expédition de transfert enregistrée avec les entrées du tableau 337.

Le tableau suivant décrit ce qui se passe dans certains champs par rapport à l’entrée de réservation 40.

|Champ|Désignation|  
|---------------------------------|---------------------------------------|  
|**Statut de réservation**|L’excédent car l’article 80003 est configuré avec un suivi de commande mais aucune demande n’existe.|  
|**Code d'emplacement**|Code de transfert vers l’emplacement BLEU.|  
|**Type origine**|Tableau de ligne de transfert 5741.|  
|**ID de la source**|Document n° de l’ordre de virement 1011.|
|**Référence de la source**|Nombre total de lignes 20000 + Numéro de ligne 10000 contre l’article 80003 = 30000.|

L’explication des champs suivants pour l’entrée de réservation 43 est la suivante.

|Champ|Désignation|  
|---------------------------------|---------------------------------------|  
|**Statut de réservation**|L’excédent car l’article 80003 est configuré avec un suivi de commande mais aucune demande n’existe.|  
|**Code d'emplacement**|Emplacement de transit OWN LOG est l’emplacement où l’article existe.|  
|**Type origine**|Tableau des écritures comptables des articles 32.|  
|**Référence de la source**|L’écriture comptable ouverte numéro 322.|

#### <a name="example-2"></a>Exemple 2

L’exemple suivant illustre ce qui se passe lorsqu’un composant est transféré entre des emplacements, mais qu’il est en même temps suivi entre un besoin de demande et une offre disponible. Les composants seront transférés de l’emplacement ROUGE vers l’emplacement BLEU, qui doit être consommé sur un ordre de production lancé. Le composant utilise le suivi des commandes, la planification des commandes et le suivi des articles.

L’exemple met en évidence le flux détecté dans le tableau 337 par rapport aux champs **Statut de réservation**, **Code d’emplacement**, **Type de source**, **ID de source**, **N° de référence de la source** et type de **Liaison**.

1. Dans la page **Configuration de fabrication**, définissez le champ **Composants à l’emplacement** sur ROUGE.
2. Créer un nouveau composant d’élément. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : achat
  - **Politique de fabrication** : fabrication sur stock
  - **Politique de suivi des commandes** : Suivi uniquement
  - **Code de suivi de l’article** : LOTALL
3. À l’aide du journal des articles, augmentez l’inventaire du composant d’article par rapport à l’emplacement ROUGE à 100 unités. Définissez les numéros de lot suivants :
  - Numéro de lot Lot A, Quantité 30
  - Numéro de lot Lot B, Quantité 70
4. Créer un nouvel élément Produit. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : Production
  - **Politique de fabrication** : fabrication sur stock
  - **Politique de suivi des commandes** : Suivi uniquement
5. Créez une **nomenclature de production** avec 1 quantité par composant d’article.
6. Affecter la nomenclature de production à l’article produit.
7. Créez un document de vente. Définissez les champs suivants :
  - **Article** : Produit
  - **Localisation** : BLEU
  - **Quantité** : 100
8. Dans l’onglet **Actions** de la commande client, dans le groupe **Plan**, choisissez **Planification** pour créer un ordre de fabrication lancé lié à la commande client.
9. Ouvrez l’ordre de production publié / le composant nécessaire et remarquez que l’emplacement est défini comme ROUGE.
La raison est que les **Composants à l’emplacement** sont ROUGES dans la **Configuration de fabrication** carte.
L’élément produit obtiendra la sortie par rapport à l’emplacement BLEU.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

##### <a name="reservation-entries-with-numbers-55-and-56"></a>Réservations avec les numéros 55 et 56

Pour les besoins en composants des lots A et B, respectivement, des liens de suivi de commande sont créés à partir de la demande dans la table 5407, Composant de commande de production, vers l’approvisionnement dans la table 32, Écriture comptable des articles. Le **Statut de réservation**  le champ contient le suivi des quatre entrées pour indiquer que ces liens de suivi de commande dynamiques entre offre et demande.

La demande dans la table 5407, Composant de l’ordre de production, est liée à l’ID source de l’ordre de production lancé 101006. L’approvisionnement dans le tableau 32, Écriture du grand livre des articles, est lié au numéro de référence de la source. étant les numéros d’écriture du grand livre des articles 325 et 326 auxquels les unités existent.

> [!NOTE]  
> Le champ **N° lot** est vide sur les lignes demande, parce que les numéros de lot ne sont pas spécifiés sur les lignes composante du bon de production libéré.

##### <a name="reservation-entry-with-number-57"></a>Réservation Entrée avec numéro 57

À partir de la demande de vente dans la table 37, Ligne de vente, un lien de suivi de commande est créé vers l’approvisionnement dans la table 5406, Ligne de commande de production. Le champ  **Statut de réservation** contient Réservation et le champ  **Liaison** contient Commande à commande. Cela est dû au fait que l’ordre de fabrication publié a été généré spécifiquement pour la commande client et doit rester lié contrairement aux liens de suivi de commande avec le statut de réservation de Suivi, qui sont créés et modifiés de manière dynamique.

> [!NOTE]  
> Le champ **Liaison** peut également contenir *Commande à commande* lorsque vous utilisez Fabrication à la commande comme politique de fabrication et/ou Commande comme politique de réapprovisionnement.

10. Dans ce pointer du scénario, les 100 unités du composant sont transférées de l’emplacement ROUGE vers l’emplacement BLEU à l’aide d’un ordre de transfert.

Sélectionner Lot A et Lot B pour l’expédition.

Affichez la quantité totale en attente comme expédiée UNIQUEMENT.

> [!NOTE]  
> Les composants peuvent être consommés à l’emplacement ROUGE, mais pour l’exemple illustrant le flux des entrées de réservation, les unités sont transférées manuellement à l’emplacement BLEU.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

##### <a name="reservation-entries-with-number-55-and-56"></a>Réservations avec les numéros 55 et 56

Les entrées de suivi de commande pour les deux lots du composant reflétant la demande dans la table 5407 sont modifiées d’un statut de réservation de Suivi à Surplus. La raison est que les approvisionnements qui ont été liés précédemment, dans la table 32, ont été utilisés par la livraison de l'ordre de transfert. Un excédent véritable, comme dans ce cas, reflète un excédent d'approvisionnement ou de demande qui reste non chaîné. Il s’agit d’une indication de déséquilibre dans le réseau de commandes, qui générera un message d’action par le système de planification à moins qu’il ne soit résolu de manière dynamique.

##### <a name="reservation-entry-numbers-59-to-63"></a>Numéros d’entrée de réservation 59 à 63

Étant donné que les deux lots du composant sont enregistrés sur l’ordre de transfert comme expédiés mais non reçus, toutes les entrées de suivi de commande positives associées sont de type de réservation Surplus, indiquant qu’elles ne sont affectées à aucune demande. Pour chaque numéro de lot, une entrée se rapporte à la table 5741, Ligne de transfert, et une entrée se rapporte à l’écriture comptable des articles à l’emplacement de transit où les articles existent désormais.

Le tableau 5741, **Ligne de transfert**, correspond au type de source. **L’ID source** est le numéro de document d’ordre de transfert 1012 et **le numéro de référence de la source.** Est 20000 = 10000 + 10000 comme détaillé dans l’exemple 1. L’emplacement est défini comme BLEU pour le code d’emplacement de transfert.

Les deux entrées restantes avec **Statut de réservation** Surplus ont la table 32, **Écriture de grand livre d’articles**, comme Type de source et **N° de référence de la source.** 328 et 330, y compris leurs numéros de lot situés actuellement dans le journal de sortie de l’emplacement en transit.

11. Enregistrez l’ordre de transfert en attente comme reçu.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

Les entrées de suivi de commande sont désormais similaires au premier pointer du scénario, avant que l’ordre de transfert ne soit publié comme expédié uniquement, sauf que les entrées pour le composant ont désormais le statut de réservation Surplus au lieu de Suivi. Cela est dû au fait que le composant nécessaire se trouve toujours à l’emplacement ROUGE, ce qui indique que le champ  **Code d’emplacement** sur la ligne du composant de l’ordre de fabrication contient ROUGE comme défini dans le champ de configuration  **Composants à l’emplacement** .

L’approvisionnement qui avait été alloué à cette demande auparavant avait été transféré vers l’emplacement BLEU et ne peut désormais plus être entièrement suivi, à moins que le besoin en composants sur la ligne de commande de production ne soit modifié vers l’emplacement BLEU. Ceci est enregistré dans les deux dernières entrées de réservation avec les numéros de lot renseignés, le champ  **Type de source** étant le tableau 32 et **N° de référence de la source.** Le champ étant les écritures comptables 333 et 334.

12. Dans la liste des composants affectée à l’ordre de fabrication lancé, modifiez l’emplacement sur BLEU pour le composant.

12. Ouvrez le **journal de consommation** et exécutez la tâche par lots **Calc. Consommation** .
Attribuer au lot A une quantité de 30 et au lot B une quantité de 70.

Fermer le formulaire de suivi des articles.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

##### <a name="reservation-entries-with-numbers-68-and-69"></a>Réservations avec les numéros 68 et 69

Étant donné que le besoin en composants a été modifié vers l’emplacement BLEU et que l’approvisionnement est disponible sous forme d’entrées de grand livre d’articles à l’emplacement BLEU, toutes les entrées de suivi de commande pour les deux numéros de lot sont désormais entièrement suivies, comme l’indique le statut de réservation du suivi. Les numéros de lot ne sont pas renseignés dans le champ  **N° de lot** par rapport à la demande dans la table 5406, **Ligne de commande de production**, car nous n’avons pas spécifié de numéros de lot pour le composant sur l’ordre de fabrication lancé.

##### <a name="reservation-entries-with-numbers-70-and-71"></a>Réservations avec les numéros 70 et 71

Les entrées avec le statut de réservation Prospect sont générées dans la table 337. La raison est que les deux numéros de lot sont attribués au composant dans le journal de consommation, mais le journal n’a pas été enregistré.

Ceci termine la section sur la manière dont les entrées de suivi de commande dans la table  **Entrée de réservation**  sont générées, modifiées et supprimées lors de l’utilisation de plusieurs fonctionnalités en combinaison avec des ordres de transfert.

### <a name="planning-calculated-1"></a>Planification calculée

Lorsque vous utilisez les fonctionnalités de planification, c’est-à-dire la **Feuille de travail de demande**, la **Feuille de travail de planification** ou la **Planification de commande**, les entrées de réservation dans la **Entrée de réservation** table 337 peuvent être modifiées ou ajoutées en fonction de la suggestion de planification donnée par la logique dans Microsoft Dynamics NAV. L’exemple 3 utilisera **Politique de réapprovisionnement**  Commander avec **Politique de fabrication**  Fabrication sur commande pour un article produit. Le composant utilisera **Politique de réapprovisionnement**  Quantité de réapprovisionnement fixe.

#### <a name="example-3"></a>Exemple 3

1. Dans le **Configuration de fabrication**  carte, **Composant à l’emplacement**  est ROUGE par rapport à l’exemple précédent.
2. Créer un nouvel élément élément parent 70061. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : Commande de produit
  - **Politique de fabrication** :Fabriqué sur commande
  - **Politique de réapprovisionnement** : Commande
  - **Politique de réserve** : Facultatif
  - **Suivi de commande** : Aucun
3. Créer un nouvel élément de composant 70062. Définissez les champs suivants :
  - **Unité de mesure de base** : PCS
  - Tous les groupes de publication par défaut
  - **Système de réapprovisionnement** : Achat
  - **Politique de réapprovisionnement** : Quantité fixe de réapprovisionnement
  - **Politique de réserve** : Facultatif
  - **Politique de suivi des commandes** : Aucune
  - **Quantité de stock de sécurité** : 10
  - **Réorganiser pointer** : 25
  - **Quantité de commande** : 50
4. Créez une nouvelle nomenclature de production et spécifiez l’article de composant 70062 avec la quantité par 1.
Affectez la nomenclature de production à l’article élément parent 70061.
5. Créez un document de vente. Définissez les champs suivants :
  - **Article** : Quantité fixe à commander
  - **Localisation** : ROUGE
  - **Quantité** : 40
  - **Date d’expédition** : 15/02/2014
6. Ouvrez la page  **Feuilles de travail de planification** et exécutez la tâche par lots  **Calculer le plan de régénération** .
  - **MPS/MRP** : activé
  - **Date de début** : 23/01/2014
  - **Date de fin** : 01/03/2014
  - Filtrer sur les articles 70061 et 70062
  - Aucune prévision

Les suggestions de planification suivantes sont données.

La première suggestion de planification est de créer un nouvel ordre de production planifié pour répondre à la demande en suspens de la commande client pour la quantité 40 de l’article élément parent 70061. Vérifiez le suivi des commandes et Microsoft Dynamics NAV affichera la commande en cours. Le suivi des commandes est activé au fur et à mesure qu’il est généré par le moteur de planification.

La deuxième ligne sert à amener l’inventaire au-dessus de Réorganiser pointer (25). Ainsi, en prenant en compte la quantité de réapprovisionnement (50), une quantité de 50 unités est suggérée par la logique de planification. La troisième ligne consiste à amener l’inventaire au niveau du stock de sécurité (10).

La quatrième ligne sert à réapprovisionner l’inventaire lorsque la commande client est expédiée. À ce moment-là, l’inventaire est de 20 et donc inférieur à Réorganiser pointer. En conséquence, le moteur de planification propose d’acheter 50 composants supplémentaires en tenant compte de la quantité de réapprovisionnement. Il s’agit d’une quantité non suivie, donc dans la table  *Entrée de réservation* 337, elle sera marquée avec le statut de réservation Surplus.

Les informations d’état du tableau 337 sont présentées dans l’illustration suivante.

Le champ  **Statut de réservation** est Réservation et une liaison de commande à commande est créée. La raison est que la politique de fabrication des articles est "Fabriqué sur commande" et la politique de réapprovisionnement est définie sur "Commande". Si l’un des deux est défini sur Commande, le statut de réservation sera Réservation au lieu de Suivi et la liaison sera définie sur Commande à commande.

La demande de 40 unités par rapport au champ  **ID source** est le numéro de commande client 1005 et le type de source est  *Ligne de vente* table 37. L’entrée de réservation est alignée sur la suggestion de planification, référence source n°. 10000, l’ID source est PLANIFICATION et le type de source est *Ligne de demande* table 246. Il y a donc un équilibre entre la demande de la commande client et l’offre suggérée par le moteur de planification.

##### <a name="reservation-entry-numbers-73-and-74"></a>Réservation Entrées numéros 73 et 74

En exécutant le travail par lots Calculer le plan, les quatre entrées suivantes sont générées avec un statut de réservation Suivi en raison du paramètre de politique de réapprovisionnement Quantité de réapprovisionnement fixe pour le composant. L’approvisionnement nécessaire pour le composant article 70062 est réapprovisionné selon les suggestions de planification données, référence source n°. 20 000 et 30 000, avec l’ID source défini sur PLANIFICATION et le type de source de la table 246 de la  *Ligne de demande* . Le composant nécessaire est créé pour répondre à la demande concernant l’article élément parent 70061 pour une quantité totale (base) de 40. En raison de cette demande, le champ  **Source Prod. Order Line** est 10 000, avec le type de source de la table  *Component Need* 99000829.

Le statut de réservation n’est pas Surplus, car le suivi des commandes existe entre la demande de l’article élément parent 70061 et l’approvisionnement de l’article composant 70062.

##### <a name="reservation-entry-numbers-75-and-76"></a>Réservation Entrées numéros 75 et 76

Les deux dernières entrées ont un statut de réservation Surplus, car il s’agit de quantités non suivies générées sur la feuille de planification liée aux paramètres de réapprovisionnement Reorder pointer et Reorder Quantity.

## <a name="see-also"></a>Voir aussi .
[Détails de conception : conception de la traçabilité](design-details-item-tracking-design.md)  
[Détails de conception : équilibrage de la demande et de l’approvisionnement](design-details-balancing-demand-and-supply.md)  
[Détails de conception : réservation, chaînage et message d'action](design-details-reservation-order-tracking-and-action-messaging.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
