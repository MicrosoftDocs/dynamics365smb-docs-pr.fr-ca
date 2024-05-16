---
title: Synchroniser et exécuter les documents de vente
description: Configurez et exécutez l’importation et le traitement des documents de vente à partir de Shopify.
ms.date: 03/25/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: '30110, 30111, 30112, 30113, 30114, 30115, 30121, 30122, 30123, 30128, 30129, 30150, 30151, 30145, 30147'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
---

# Synchroniser et exécuter les documents de vente

Cet article décrit les paramètres et les étapes à effectuer pour synchroniser et exécuter les documents de vente avec Shopify dans [!INCLUDE[prod_short](../includes/prod_short.md)].

## Définir l’importation des commandes sur la Fiche magasin Shopify

Saisissez un **Code devise** si la boutique en ligne utilise une devise différente de la devise locale ($). La devise spécifiée doit avoir des taux de change configurés. Si votre boutique en ligne utilise la même devise que [!INCLUDE[prod_short](../includes/prod_short.md)], laissez le champ vide. 

Vous pouvez accéder à la devise du magasin dans les paramètres [Détails du magasin](https://www.shopify.com/admin/settings/general) dans votre administrateur Shopify. Shopify peut être configuré pour accepter différentes devises. Toutefois, les commandes importées dans [!INCLUDE[prod_short](../includes/prod_short.md)] utilisent la devise du magasin.

Une commande Shopify classique peut inclure des coûts en plus du sous-total, comme les frais d’expédition ou, s’ils sont activés, les pourboires. Ces montants sont reportés directement dans le compte du grand livre à utiliser pour des types de transactions spécifiques :

* **Compte frais d’expédition**
* **Compte carte cadeau vendu** ; en savoir plus dans la rubrique [Carte cadeau](synchronize-orders.md#gift-cards)
* **Compte de pourboires**  

Activez **Créer automatiquement des commandes** pour créer automatiquement des documents vente dans [!INCLUDE[prod_short](../includes/prod_short.md)] après l’importation de la commande Shopify.

Si vous souhaitez libérer automatiquement un document de vente, activez le bouton bascule **Libérer automatiquement les documents de vente**.

Si vous ne souhaitez pas envoyer de confirmations d’expédition automatiques aux clients, désactivez l’option **Envoyer une confirmation d’expédition** . Désactiver la bascule peut être utile si vous vendez des biens numériques ou si vous souhaitez utiliser un autre mécanisme de notification.

Si vous sélectionnez le champ **N° commande Shopify sur n° ligne doc.**, [!INCLUDE [prod_short](../includes/prod_short.md)] insère les ligne vente de type **Commentaire** avec le numéro de commande Shopify.

> [!NOTE]
> Le document de vente dans [!INCLUDE[prod_short](../includes/prod_short.md)] est lié à la commande Shopify, et vous pouvez ajouter le **N° de commande Shopify** vers les pages de liste ou de fiche pour les documents de vente, les factures et les livraisons. Pour en savoir plus sur l’ajout d’un champ, accédez à [Commencer à personnaliser en utilisant le mode de personnalisation](../ui-personalization-user.md#start-personalizing-by-using-the-personalization-mode). 

Dans le champ **Priorité région fiscale**, vous pouvez définir la priorité en matière de sélection d'un code région fiscale pour les adresses sur les commandes. La commande Shopify importée contient des informations sur les taxes. Les taxes sont recalculées lorsque vous créez les documents de vente, il est donc important que les paramètres de TVA/taxe soient corrects dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Pour plus d’informations sur les taxes, accédez à [Configurer les taxes pour la connexion Shopify](setup-taxes.md).

Précisez comment vous traiterez les retours et les remboursements :

* **Vide** spécifie que vous n’importez pas et ne traitez pas les retours et les remboursements.
* **Importer uniquement** indique que vous importez des informations, mais vous créerez manuellement la note de crédit correspondante.
* **Créer automatiquement une note de crédit** spécifie que vous importez des informations et [!INCLUDE[prod_short](../includes/prod_short.md)] crée automatiquement les notes de crédit. Cette option nécessite que vous activiez le bouton à bascule **Créer automatiquement un document de vente**.

Spécifiez un emplacement pour les retours et des comptes du grand livre pour les remboursements de marchandises et autres remboursements.

* **Articles non réapprovisionnés du compte de remboursement** spécifie un n° compte du grand livre pour les articles pour lesquels vous ne souhaitez pas avoir de correction d'inventaire.
* **Compte de remboursement** spécifie un compte du grand livre pour la différence entre le montant total remboursé et le montant total des articles.

En savoir plus sur [Retours et remboursements](synchronize-orders.md#returns-and-refunds)

### Mappage des méthodes de livraison

Le **Code méthode de livraison** pour les documents vente importés de Shopify peut être renseigné automatiquement. Vous devez configurer le **Mappage méthodes de livraison**.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez définir le mappage pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Mappage méthodes de livraison**. Cela crée automatiquement les enregistrements des conditions de livraison définis dans les paramètres [**Expédition**](https://www.shopify.com/admin/settings/payments) dans l’**administration Shopify**.
4. Dans le champ **Nom**, vous affichez le nom de la condition de livraison de Shopify.
5. Saisissez le **Code méthode de livraison** avec la méthode de livraison correspondante dans [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> Si plusieurs frais d’expédition sont associés à un document de vente, un seul est sélectionné comme la méthode de livraison et affecté au document vente.

### Cartographie des emplacements

Le mappage de l’emplacement est nécessaire pour compléter le **Code d’emplacement** pour les lignes document vente importées depuis Shopify. C’est important lorsque le bouton à bascule **Emplacement Obligatoire** est activé dans la fiche **Configuration inventaire**, sinon vous ne pourrez pas créer de documents vente.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez configurer le mappage des emplacements pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Emplacements** pour ouvrir les **Emplacements des magasins Shopify**.
4. Sélectionnez l’action **Obtenir les emplacements Shopify** pour importer tous les emplacements définis dans Shopify. Ils se trouvent dans les paramètres [**Emplacements**](https://www.shopify.com/admin/settings/locations) du volet **Administration Shopify**. 
5. Entrez le **Code d’emplacement par défaut** avec l’emplacement correspondant dans [!INCLUDE[prod_short](../includes/prod_short.md)].

> [!NOTE]  
> Le mappage de l’emplacement est également utilisé pour synchroniser l’inventaire. Pour en savoir plus, accédez à [Synchroniser l’inventaire dans Shopify](synchronize-items.md#sync-inventory-to-shopify).
  
## Exécuter la synchronisation des commandes

La procédure suivante décrit comment importer et mettre à jour les documents de vente.

> [!NOTE]  
> Les commandes archivées dans Shopify ne peuvent pas être importées. Si vous devez vérifier l’état de la commande, ouvrez la commande à partir de la page [commandes](https://www.shopify.com/admin/orders) du panneau **Shopify d’administration** et examinez-la. détails de la commande.
> 
> Désactivez l’option **Archiver automatiquement la commande** dans la section **Traitement des commandes** des paramètres **Validation** dans le volet **Administration Shopify** pour vérifier que toutes les commandes sont importées dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Pour importer des commandes archivées, utilisez l’action **Désarchiver les commandes** dans la page [Commandes](https://www.shopify.com/admin/orders) du volet  **Administration Shopify**. 

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez importer des commandes pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Commandes**.
4. Sélectionnez l’action **Synchroniser les commandes à partir de Shopify**.
5. Définissez des filtres sur les commandes si nécessaire. Par exemple, vous pouvez importer les commandes entièrement payées ou celles présentant un faible niveau de risque.

   > [!NOTE]  
   > Lors du filtrage par balise, vous devez utiliser les jetons de filtre `@` et `*`. Par exemple, si vous souhaitez importer des commandes contenant *tag1*, utilisez `@*tag1*`. `@` s’assurera que le résultat ne respecte pas la casse, tandis que `*` recherche des commandes avec plusieurs balises.

6. Cliquez sur le bouton **OK**.

Sinon, vous pouvez rechercher le traitement en lot **Synchroniser les commandes à partir de Shopify**.

Vous pouvez programmer la tâche pour qu’elle soit exécutée automatiquement. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

### Informations détaillées

Le connecteur Shopify importe les commandes en deux étapes :

1. Il importe les en-têtes de commande dans la table **Commandes Shopify à importer** lorsqu’ils remplissent certaines conditions :

   * Ils ne sont pas archivés. Cela signifie que vous pouvez inclure ou exclure des commandes de la synchronisation en les archivant ou en les désarchivant dans l’administrateur Shopify.
   * Ils ont été créés ou modifiés après la dernière synchronisation. Cela signifie que vous pouvez forcer la réimportation d’une commande spécifique si vous la modifiez, par exemple, en ajoutant les **Notes** ou la **Balise**.

2. Il importe les commandes Shopify et des informations supplémentaires.

   * Le connecteur Shopify traite tous les enregistrements de la table **Commandes Shopify à importer** qui correspondent aux critères de filtre que vous avez définis dans la page de demande **Synchroniser les commandes à partir de Shopify**. Par exemple, les balises, le canal ou l'état d’exécution. Si vous n’avez spécifié aucun filtre, il traite tous les enregistrements.
   * Lors de l’importation d’une commande Shopify, le connecteur Shopify demande des informations supplémentaires à Shopify :

     * En-tête de commande
     * Lignes de commande
     * Informations d’expédition et d’exécution
     * Transactions
     * Retours et remboursements, s’ils sont configurés

La page **Commande Shopify à importer** est utile pour dépanner l’importation de commandes. Vous pouvez évaluer les commandes disponibles et effectuer les étapes suivantes :

* Vérifiez si une erreur a bloqué l’importation d’une commande spécifique et explorez les détails de l’erreur. Vérifiez le champ **Contient une erreur**.
* Traitez uniquement des commandes spécifiques. Vous devrez remplir le champ **Code magasin**, sélectionner une ou plusieurs commandes, puis choisir l’action **Importer les commandes sélectionnées**.
* Supprimez des commandes de la page **Commande Shopify à importer** pour les exclure de la synchronisation.

## Passer en revue les commandes importées

Une fois l’importation terminée, vous pouvez explorer la commande Shopify et trouver toutes les informations associées comme les transactions de paiement, les frais d’expédition, le niveau de risque, les attributs et balises de commande ou les exécutions, si la commande a déjà été exécutée dans Shopify. Vous pouvez également voir les confirmations de commande envoyées au client en sélectionnant l’action **Page d'état Shopify**.

> [!NOTE]  
> Vous pouvez accéder directement à la fenêtre **Commandes Shopify** pour afficher les commandes dont l'état est défini sur *Ouvert* dans tous les magasins. Pour consulter les commandes terminées, vous devez ouvrir la page **Commandes Shopify** à partir de la page **Fiche magasin Shopify** spécifique.

Avant que les documents de vente ne soient créés dans [!INCLUDE[prod_short](../includes/prod_short.md)], vous pouvez utiliser l’action **Synchroniser la commande à partir de Shopify** dans la **Shopify Commande** page pour réimporter des commandes spécifiques.

Vous pouvez également marquer une commande comme payée, ce qui est utile dans un scénario B2B où les paiements sont traités en dehors du Shopify paiement. Sélectionnez l’action **Marquer comme payé** sur la page **Shopify Commande**. Vous pouvez également marquer une commande comme annulée pour lancer le flux de remboursement dans Shopify. Choisir la **annuler la commande** action sur le **Shopify Commande** page, remplissez les champs nécessaires sur la page **Shopify annuler la commande** page et appuyez sur **OK**. Vous devrez exécuter la synchronisation des commandes pour importer les mises à jour dans [!INCLUDE[prod_short](../includes/prod_short.md)].

## Créer des documents vente dans Business Central

Si le bouton à bascule **Créer automatiquement des commandes** est activée sur la **Fiche magasin Shopify**, [!INCLUDE[prod_short](../includes/prod_short.md)] tente de créer un document vente après l’importation de la commande. Si des problèmes tels qu’un client ou un produit manquant surviennent, vous devrez les résoudre, puis créer à nouveau le document de vente.

### Pour créer des documents vente

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser les commandes pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Commandes**.
4. Sélectionnez la commande pour laquelle vous voulez créer un document vente et sélectionnez l’action **Créer documents vente**.
5. Choisissez **Oui**.

Si la commande Shopify exige une exécution, un **document de vente** est créé. Pour les commandes Shopify exécutées, telles que les commandes qui ne contiennent qu’une carte-cadeau ou qui sont déjà traitées dans Shopify, une **Facture vente** est créée.

Un document vente est créé et peut être géré en utilisant les fonctionnalités standard de [!INCLUDE[prod_short](../includes/prod_short.md)].

Si vous souhaitez recréer un document de vente, vous pouvez utiliser le **Dissocier les documents traités** action dans le **Shopify Commande** page. Notez que cette action ne supprime pas le document de vente déjà créé. Vous devez le traiter manuellement.

### Gérer les clients manquants

Si vos paramètres empêchent la création automatique d’un client et qu’une correspondance client est introuvable, vous devez attribuer un client à la commande Shopify manuellement. Il existe plusieurs façons d’attribuer des clients à des commandes :

* Affecter **N° débiteur** et **N° client facturé** directement dans la page **Commandes Shopify** en choisissant un client dans la liste des clients existants.
* Sélectionner un modèle client, puis créer et affecter le client par l’action **Créer un client** dans la page **Commandes Shopify**. Le client Shopify doit avoir au moins une adresse. Les commandes créées via le canal de vente du PDV Shopify manquent souvent de détails d’adresse.
* Vous pouvez mapper un client existant avec le **Client Shopify** existant dans la page **Clients Shopify**, puis sélectionner l’action **Trouver le mappage** dans la page **Commandes Shopify**.

### Comment le connecteur choisit le client à utiliser

La fonction *Importer la commande à partir de Shopify* tente de sélectionner le client dans l’ordre suivant :

1. Si le **N° client par défaut** est défini dans **Modèle client Shopify** pour le **Code pays/région destinataire**, puis le **N° client par défaut** est utilisé quels que soient les paramètres dans les champs **Importation client à partir de Shopify** et **Type de mappage client**. En savoir plus sur [Modèle client par pays](synchronize-customers.md#customer-template-per-countryregion).
2. Si le champ **Importation client à partir de Shopify** est défini sur *Aucun* et le champ **N° client par défaut** est défini sur la page **Fiche magasin Shopify**, alors le **N° client par défaut** est utilisé.

Les étapes suivantes dépendent du champ **Type de mappage client**.

* **Toujours prendre le client par défaut**, puis le connecteur utilise le client défini dans le champ **N° client par défaut** dans la page **Fiche magasin Shopify**.
* **Par courriel/téléphone**, le connecteur tente d’abord de trouver le client existant par code, puis par courriel, puis par téléphone. Si le client est introuvable, le connecteur crée un client.
* **Par informations de facturation**, le connecteur tente d’abord de trouver le client existant par code, puis par adresse facturation. Si le client est introuvable, le connecteur crée un client.

> [!NOTE]  
> Le connecteur utilise les informations de l’adresse facturation et crée le client facturé dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Le débiteur correspond au client facturé.

Pour les commandes B2B, le flux est similaire, bien que le connecteur utilise les champs **Numéro compagnie par défaut**, **Importation de la compagnie depuis Shopify** et **Type de mappage compagnie** sur la page **ShopifyFiche magasin**. Notez qu’il n’y a pas **Numéro de compagnie par défaut** Dans le **Shopify Modèle client** car au B2B, il est censé avoir des clients nommés.

### Différentes règles de traitement des commandes

Vous souhaiterez peut-être traiter les commandes différemment en fonction d’une règle. Par exemple, les commandes provenant d’un canal de vente spécifique, comme le point de vente, doivent utiliser le client par défaut, mais vous souhaitez que votre boutique en ligne ait de vraies informations sur le client.

Une façon de répondre à cette exigence consiste à créer une fiche Shopify Shop supplémentaire et à utiliser des filtres dans la page de demande **Synchroniser des commandes à partir de Shopify** .

Exemple : vous avez une boutique en ligne ainsi qu’un PDV Shopify. Pour votre PDV, vous souhaitez utiliser un client fixe, mais pour votre boutique en ligne, vous souhaitez créer des clients dans [!INCLUDE[prod_short](../includes/prod_short.md)]. La procédure suivante répertorie les étapes de haut niveau. Pour en savoir plus, consultez les articles d’aide correspondants.

1. Créez une boutique Shopify appelée *MAGASIN* et associez-la à votre compte Shopify.
1. Configurez la synchronisation article/produit pour que ce magasin gère les informations produit.
1. Spécifiez que les clients sont importés avec les commandes. Le connecteur doit trouver des clients en recherchant leur adresse de courriel. S’il ne trouve pas d’adresse, il utilise le modèle de client pour créer un client.
1. Créez une boutique Shopify appelée *PDV* et associez-la au même compte Shopify.
1. Assurez-vous que la synchronisation article/produit est désactivée.
1. Sélectionnez le connecteur qui utilise le client par défaut.
1. Créez une entrée de file d’attente de tâches récurrentes pour le rapport 30104 **Synchroniser les commandes à partir de Shopify**. Sélectionnez **MAGASIN** dans le champ **Code magasin Shopify** et utilisez des filtres pour saisir toutes les commandes sauf celles qui passent par le canal de vente PDV crée. Par exemple, **<>Point de vente**
1. Créez une entrée de file d’attente de tâches récurrentes pour le rapport 30104 **Synchroniser les commandes à partir de Shopify**. Sélectionnez **PDV** dans le champ **Code magasin Shopify** et utilisez des filtres pour saisir les commandes générées par le canal de vente PDV. Par exemple, **Point de vente**.

Chaque file d’attente importe et traite les commandes dans les filtres définis et utilise les règles de la fiche magasin Shopify correspondante. Par exemple, elles créent des commandes de point de vente pour le client par défaut.

> [!Important]
> Pour éviter les conflits lors du traitement des commandes, utilisez la même catégorie de file d’attente des projets pour les deux entrées file d’attente des projets.

### Impact des modifications des commandes

Dans Shopify :

|Modifier|Impact sur Shopify Commandes non encore traitées dans [!INCLUDE[prod_short](../includes/prod_short.md)] | Impact sur Shopify Commandes déjà traitées dans [!INCLUDE[prod_short](../includes/prod_short.md)] |
|------|-----------|-----------|
|Modifier l’emplacement d’exécution | L’emplacement d’exécution est synchronisé avec [!INCLUDE[prod_short](../includes/prod_short.md)]. | L’emplacement d’exécution est synchronisé avec [!INCLUDE[prod_short](../includes/prod_short.md)].|
|Modifier une commande et accroître sa quantité|La commande importée utilise la nouvelle quantité.| Le connecteur détectera les modifications et marquera les commandes. |
|Modifier une commande et réduire sa quantité|La commande importée utilise la nouvelle quantité. Un remboursement Shopify d’un montant nul sera importé et ne pourra pas être converti en note de crédit.| Le connecteur détectera les modifications et marquera les commandes. |
|Modifier une commande et supprimer un article existant |L’élément supprimé ne sera pas importé. Un remboursement Shopify d’un montant nul sera importé et ne pourra pas être converti en note de crédit.| Le connecteur détectera les modifications et marquera les commandes. |
|Modifier une commande et ajouter un nouvel article | Les articles originaux et ajoutés sont importés. | Le connecteur détectera les modifications et marquera les commandes. |
|Traiter la commande : remplir, mettre à jour les informations de paiement | L’en-tête de la commande sera mis à jour. |L’en-tête de la commande sera mis à jour. Le traitement ne sera pas synchronisé avec Shopify.|
|Annuler une commande payée | L’en-tête de la commande sera mis à jour et sera traité séparément |Le connecteur détectera les modifications et marquera les commandes. |
|Annuler une commande non payée | L’élément supprimé ne sera pas importé. Shopify un remboursement d’un montant nul sera importé et ne pourra pas être converti en note de crédit. |Le connecteur détectera les modifications et marquera les commandes. |

Si une commande a déjà été traitée dans [!INCLUDE[prod_short](../includes/prod_short.md)] le connecteur affiche le message d'erreur suivant : *la commande a déjà été traitée dans Business Central, mais une édition a été reçue de Shopify. Les modifications n’ont pas été propagées à la commande traitée dans Business Central. Mettez à jour les documents traités pour qu’ils correspondent aux données reçues de Shopify. Si vous souhaitez forcer la synchronisation, utilisez l’action « Synchroniser la commande de Shopify » dans la page carte de commande Shopify.*

En fonction de l’état du document de vente créé, vous pouvez effectuer les actions suivantes :

1. Supprimer un document vente créé
2. Choisir la **Dissocier les documents traités** action pour réinitialiser le **Traité** indicateur.
3. Choisir la **Synchroniser la commande à partir de Shopify** action pour mettre à jour la commande individuelle avec les données récentes de Shopify.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)] :

|Modifier|Impact|
|------|-----------|
|Changez l’emplacement vers un autre emplacement. Reportez la livraison. | La commande est marquée comme exécutée. Lieu de traitement à partir de Shopify sera utilisé. |
|Réduisez la quantité. Reportez la livraison. | La commande Shopify est marquée comme partiellement exécutée. |
|Augmentez la quantité. Reportez la livraison. | Le traitement ne sera pas synchronisé avec Shopify. Idem si l’exécution a été divisée en Shopify mais traité comme une seule ligne dans [!INCLUDE[prod_short](../includes/prod_short.md)]. |
|Ajoutez un nouvel article. Reportez la livraison. | La commande Shopify est marquée comme exécutée. Les nouvelles lignes ne seront pas ajoutées. |

## Synchroniser les livraisons avec Shopify

Lorsqu’un document de vente créé à partir d’une commande Shopify est livré, vous pouvez synchroniser les livraisons avec Shopify.

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Synchroniser livraisons avec Shopify**, puis sélectionnez le lien associé.
2. Définissez les filtres sur les livraisons si nécessaire. Par exemple, vous pouvez mettre à jour une livraison reportée à une date donnée.
3. Cliquez sur **OK**.

La commande dans Shopify est marquée comme exécutée. Le client reçoit automatiquement un courriel ou un SMS d’avis de livraison. Si un agent de livraison et un code de suivi sont spécifiés sur la livraison, les informations de suivi sont indiquées dans le courriel.

Sinon, utilisez l’action **Synchroniser les livraisons** sur les pages Documents de vente Shopify ou Magasin Shopify.

Vous pouvez programmer la tâche pour qu’elle soit exécutée de manière automatisée. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

> [!Important]
> L’emplacement, y compris l’emplacement vide, défini dans la ligne de livraison reportée doit avoir un enregistrement correspondant dans l’emplacement Shopify. Sinon, cette ligne ne sera pas renvoyée à Shopify. En savoir plus sur le [Mappage d’emplacement](synchronize-orders.md#location-mapping).

N’oubliez pas d’exécuter **Synchroniser les commandes à partir de Shopify** pour mettre à jour l'état d’exécution d'une commande dans [!INCLUDE[prod_short](../includes/prod_short.md)]. La fonctionnalité du connecteur archive également les commandes entièrement payées et exécutées à la fois dans Shopify et dans [!INCLUDE[prod_short](../includes/prod_short.md)] si les conditions sont remplies. 

### Agents de livraison et URL de suivi

Si le document **Livraison vente reportée** contient le **Code agent de livraison** et/ou le **N° de suivi du colis**, ces informations seront envoyées à Shopify et au client dans le courriel de confirmation de livraison.

La compagnie de suivi est renseignée dans l'ordre suivant (du plus élevé au plus faible), en fonction de l’enregistrement de l'agent de livraison :

1. **Compagnie de suivi Shopify**
1. **Nom**
1. **Code**

Si le champ **URL de suivi des colis** est renseigné pour l’enregistrement de l'agent de livraison, la confirmation de livraison contiendra aussi une URL de suivi.

## Retours et remboursements

Dans une intégration entre Shopify et [!INCLUDE[prod_short](../includes/prod_short.md)], il est important de pouvoir synchroniser autant de données métier que possible. Cela facilite la mise à jour de vos niveaux de financement et d’inventaire dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Les données que vous pouvez synchroniser incluent les retours et les remboursements qui ont été enregistrés dans Administrateur Shopify ou PDV Shopify.

Les retours et les remboursements sont importés avec leurs commandes associées si vous avez activé le type de traitement sur la fiche magasin Shopify.

Les retours sont importés à des fins d’information uniquement. Aucune logique de traitement ne est associée.

Les transactions financières et, si nécessaire, les transactions d’inventaire sont traitées via des remboursements. Les remboursements peuvent inclure des produits ou simplement des montants, par exemple, si un marchand décide de compenser les frais d’expédition ou un autre montant.

Vous pouvez créer des notes de crédit vente pour les remboursements. Les avoirs peuvent avoir les types de lignes suivants :

|Type|N°|Commentaire|
|-|-|-|
|Compte du grand livre|Compte carte cadeau vendu| À utiliser pour les remboursements liés aux cartes-cadeaux.|
|Compte du grand livre|Articles non-stockés du compte de remboursement | Utilisez pour les remboursements associés à des produits qui n’ont pas été réapprovisionnés. |
|Article |Nombre d'articles| Utilisez pour les remboursements associés à des produits qui ont été réapprovisionnés. Valable pour les remboursements directs ou les remboursements liés aux remboursements. Le code d’emplacement sur la ligne de crédit plus est défini en fonction de la valeur sélectionnée pour l’emplacement de retour.|
|Compte du grand livre| Compte de remboursement | Utilisez pour d’autres montants remboursés qui ne sont pas associés à des produits ou à des cartes-cadeaux. Par exemple, des pourboires, ou si vous avez indiqué manuellement un montant à rembourser dans Shopify. |

> [!Note]
> Les emplacements de retour, y compris les emplacements vides, définis dans la **Fiche magasin Shopify** sont utilisés sur la note de crédit créée. Le système ignore les emplacements d’origine des commandes ou des expéditions.

## Cartes cadeaux

Dans le magasin Shopify, vous pouvez vendre des cartes cadeaux, qui peuvent être utilisées pour acheter des produits.

En matière de cartes cadeaux, il est important de saisir une valeur dans le champ **Compte carte cadeau vendu** dans la fenêtre **Fiche magasin Shopify**. La carte cadeau vendue est synchronisée avec les commandes en cours. Une carte cadeau appliquée est également importée avec la commande, mais en tant que transaction. Notez que la carte cadeau ne diminue pas le montant à facturer.

Pour examiner les cartes cadeaux appliquées et émises, sélectionnez l’icône ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Cartes cadeaux**, puis choisissez le lien associé.

## Voir aussi .

[Mise en route avec le connecteur Shopify](get-started.md)  
