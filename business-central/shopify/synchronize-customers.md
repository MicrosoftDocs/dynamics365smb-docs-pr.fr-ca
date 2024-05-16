---
title: Synchronisation des clients et des compagnies
description: Importer les clients de ou les exporter dans Shopify.
ms.date: 03/25/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: '30105, 30106, 30107, 30108, 30109,'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
---

# Synchronisation des clients et des compagnies

Lorsque vous importez une commande à partir de Shopify, les informations sur le client sont essentielles pour le traitement ultérieur du document dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Il existe deux options principales et plusieurs combinaisons :

* Utiliser un client spécial pour toutes les commandes.
* Importez les informations client à partir de Shopify. Cette option est également disponible lorsque vous exportez des clients dans Shopify à partir de [!INCLUDE[prod_short](../includes/prod_short.md)].

Shopify vous permet de gérer votre entreprise B2B et DTC (direct client) à partir d’un seul endroit avec la puissance et la facilité de Shopify La plateforme tout-en-un. Le connecteur Shopify fonctionne également avec différentes versions de l’e-Commerce.

Alors que Shopify possède deux entités, client et compagnie, [!INCLUDE[prod_short](../includes/prod_short.md)] ne possède que l’entité client, ce qui affecte le fonctionnement de la synchronisation.

Lorsque vous exécutez DTC, l’acheteur est créé dans Shopify en tant que client. Le client est ensuite importé vers [!INCLUDE[prod_short](../includes/prod_short.md)] comme un Shopify client, et lié ou converti en client.

Si vous faites du B2B, l’acheteur est créé dans Shopify en tant que client lié à une compagnie. Le client est importé vers [!INCLUDE[prod_short](../includes/prod_short.md)] comme un client Shopify, et l’entreprise est importée vers [!INCLUDE[prod_short](../includes/prod_short.md)] comme une compagnie Shopify et liée ou convertie en client.

Pour exporter un client depuis [!INCLUDE[prod_short](../includes/prod_short.md)] à Shopify, les étapes sont différentes selon ce que vous souhaitez faire :

* Exporter un client en tant que Shopify client pour DTC.
* Exportez un client sous forme de couple compagnie-client pour le flux B2B.

## Paramètres importants lors de l’importation de clients DTC à partir de Shopify

Que vous importiez des clients à partir de Shopify en bloc ou lors de l’importation de commandes, les paramètres suivants permettent de gérer le processus :

|Champ|Désignation|
|------|-----------|
|**Importation client à partir de Shopify**|Sélectionnez **Tous les clients** si vous prévoyez d’importer des clients à partir de Shopify en bloc, soit manuellement en utilisant l’action **Synchroniser les clients**, soit via la file d’attente des travaux pour les mises à jour récurrentes. Quelle que soit la sélection, les informations client sont toujours importées avec la commande. Cependant, l’utilisation de ces informations dépend du champ **Modèles client Shopify** et des paramètres du champ **Type de mappage client**.|
|**Type de mappage client**|Définissez comment le connecteur effectue le mappage.</br></br>- **Par courriel/téléphone**, pour que le connecteur utilise le compte de courriel et les informations de téléphone pour mapper le client Shopify importé à un client existant dans Business Central.</br></br>- **Par informations de facturation**, pour que le connecteur utilise l’adresse du destinataire de la facture pour mapper le client Shopify importé sur un client existant dans Business Central en utilisant les informations d’adresse de la partie qui réceptionne la facture.</br></br>- **Toujours prendre le client par défaut** pour que le système utilise un client du champ **N° client par défaut.** . |
|**Shopify peut mettre à jour les clients**| Sélectionnez ce champ pour que le connecteur mette à jour les clients trouvés si les options **Par courriel/téléphone** ou **Par informations de facturation** sont sélectionnées dans le champ **Type de mappage client**.|
|**Créer automatiquement des clients inconnus**| Sélectionnez ce champ pour que le connecteur crée les clients manquants si les options **Par courriel/téléphone** ou **Par informations de facturation** sont sélectionnées dans le champ **Type de mappage client**. Un client est créé en utilisant les données importées et **Code modèle client** défini dans les pages **Fiche magasin Shopify** ou **Modèle client Shopify**. Remarquez que le client Shopify doit avoir au moins une adresse. Les commandes créées via le canal de vente du PDV Shopify manquent souvent de détails d’adresse. Si cette option n’est pas activée, vous devez créer un client manuellement et le lier au client Shopify.|
|**Code modèle client/compagnie**|Utilisez ce champ avec **Créer automatiquement des clients inconnus**.</br></br>Choisissez le modèle par défaut à utiliser pour les clients créés automatiquement. Assurez-vous que le modèle sélectionné contient les champs obligatoires tels que les champs **Groupe de report marché**, **Groupe de report client**, et les champs qui concernent la taxe sur la valeur ajoutée (TVA) ou d’autres taxes.</br></br>Vous pouvez définir des modèles par pays/région dans la page **Modèles client Shopify**, ce qui est utile pour calculer correctement les taxes.</br></br>En savoir plus sur [Configurer les taxes](setup-taxes.md).|

### Modèle client par pays/région

Certains paramètres peuvent être définis au niveau du pays/de la région ou au niveau de l’État/de la province. Les paramètres peuvent être configurés dans [Expédition et livraison](https://www.shopify.com/admin/settings/shipping) sur Shopify.

Vous pouvez procéder comme suit pour chaque client avec le **Modèle client Shopify** :

1. Indiquer le **N° client par défaut**, qui a priorité sur la sélection présente dans les champs **Importation client à partir de Shopify** et **Type de mappage client**. Il est utilisé dans le document de vente importé.
2. Définir le **Code modèle client**, qui est utilisé pour créer des clients manquants, si l’option **Créer automatiquement des clients inconnus** est activée. Si le **Code modèle client** est vide, la fonction utilise le **Code modèle client** défini dans la page **Fiche magasin Shopify**. Le système essaie d’abord de trouver un modèle pour le **Code pays/région** pour l’adresse par défaut. S’il ne trouve pas de modèle, il utilise la première adresse.
3. Dans certains cas, le **Code modèle client** défini pour un pays/région n’est pas suffisant pour assurer le calcul correct des taxes (par exemple, pour les pays/régions avec taxe de vente). Dans ce cas, la **région fiscale** peut constituer un complément utile.
4. Le champ **Région fiscale** contient également une paire **Code pays** et **Nom du comté**. Cette paire est utile lorsque le connecteur doit convertir un code en un nom, ou vice versa.

> [!NOTE]  
> Les codes pays sont les codes pays ISO 3166-1 alpha-2. En savoir plus sur le [Code postal](https://help.shopify.com/en/api/custom-storefronts/storefront-api/reference/enum/countrycode).

## Paramètres importants lors de l’exportation de clients DTC vers Shopify

Vous pouvez exporter les clients existants dans Shopify en bloc. Dans chaque cas, un client et une adresse par défaut sont créés. Vous pouvez gérer le processus avec les paramètres suivants :

|Champ|Désignation|
|------|-----------|
|**Peut mettre à jour les clients Shopify**| Activez-le pour générer des mises à jour ultérieurement à partir de Business Central pour les clients qui existent déjà dans Shopify.|

Voici les conditions requises pour exporter un client :

* Le client doit avoir une adresse de courriel valide.
* Lorsque vous exportez des clients avec des provinces, assurez-vous que **Code ISO** est rempli pour les pays/régions.|
* Si le pays/la région est sélectionné sur la fiche client, assurez-vous que **Code ISO** est spécifié. Pour les clients locaux, avec un pays/une région vide, le connecteur Shopify utilise le pays/la région spécifié(e) sur la page **Informations sur la compagnie**.
* Si le client a un numéro de téléphone, ce numéro doit être unique, car Shopify n’acceptera pas un deuxième client avec le même numéro de téléphone.
* Si le client a un numéro de téléphone, celui-ci doit être au format E.164. Différents formats sont pris en charge s’ils représentent un numéro qui peut être composé de n’importe où dans le monde. Les formats suivants sont valides :

  * xxxxxxxxxx
  * +xxxxxxxxxxx
  * (xxx)xxx-xxxx
  * +x xxx-xxx-xxxx

Une fois que vous créez les clients dans Shopify, vous pouvez leur envoyer des invitations directes les incitant à activer leurs comptes.

### Remplir les informations client dans Shopify

Un client dans Shopify a un prénom, un nom de famille, une adresse de courriel et/ou un numéro de téléphone. Vous pouvez renseigner le prénom et le nom de famille à partir de la fiche client dans [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priorité|Champ de la fiche client|Désignation|
|------|------|-----------|
|1|**Nom du contact**|Priorité la plus élevée, si le champ **Nom du contact** est rempli et si le champ **Source du contact** dans la page **Fiche magasin Shopify** contient les options *Prénom et nom* ou *Nom et prénom*, ce qui définit comment diviser les valeurs.|
|2|**Nom 2**|Si le champ **Nom 2** est rempli et si le champ **Source nom 2** dans la page **Fiche magasin Shopify** contient les options *Prénom et nom* ou *Nom et prénom*, ce qui définit comment diviser les valeurs.|
|3|**Nom**|Priorité la moins élevée, si le champ **Nom** est rempli et si le champ **Origine nom** dans la page **Fiche magasin Shopify** contient les options *Prénom et nom* ou *Nom et prénom*, ce qui définit comment diviser les valeurs.|

Un client dans Shopify a également une adresse par défaut. L’adresse pourrait contenir, en plus du prénom, du nom, du courriel et/ou du numéro de téléphone, la compagnie et l’adresse. Vous pouvez remplir le champ **Compagnie** en fonction des données présentes dans la fiche client dans [!INCLUDE[prod_short](../includes/prod_short.md)].

|Priorité|Champ de la fiche client|Désignation|
|------|------|-----------|
|1|**Nom**|Priorité la plus élevée, si le champ **Origine nom** dans la page **Fiche magasin Shopify** contient *Nom de la compagnie*.|
|2|**Nom 2**|Priorité la moins élevée, si le champ **Source nom 2** dans la page **Fiche magasin Shopify** contient *Nom de la compagnie*.|

Pour les adresses où le comté/la province est utilisé(e), sélectionnez **Code** ou **Nom** dans le champ **Source comté** sur la page **Fiche magasin Shopify**. Ceci spécifie le type de données stockées dans [!INCLUDE[prod_short](../includes/prod_short.md)] dans le champ **Comté**. N’oubliez pas d’initialiser les modèles de clients par pays/région afin que le mappage code/nom du comté soit prêt. 

## Exporter les clients DTC dans Shopify

### Synchronisation initiale des clients de Business Central vers Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients Shopify**, puis choisissez le lien associé.
2. Choisissez l’action **Ajouter un client**.
3. Dans le champ **Code magasin**, saisissez le code. Si vous ouvrez la fenêtre **Shopify clients** dans la page **Fiche magasin**, le code magasin est rempli automatiquement.
4. Définissez des filtres sur les clients selon vos besoins. Par exemple, vous pouvez filtrer par code pays/région.
5. Cliquez sur **OK**.

Les clients résultants sont automatiquement créés dans Shopify avec l'adresses.

> [!NOTE]  
> Synchronisation initiale des clients de [!INCLUDE[prod_short](../includes/prod_short.md)] à Shopify ne considère pas **Peut mettre à jour Shopify clients** les paramètres.

### Synchroniser les clients

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasin Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin spécifique pour lequel vous voulez synchroniser les clients.
3. Sélectionnez l’action **Synchroniser les clients**.

Sinon, vous pouvez utiliser l’action **Lancer la synchronisation des clients** dans la fenêtre **Clients Shopify** ou rechercher le traitement en lot **Synchroniser les clients**.

Vous pouvez programmer la tâche pour qu’elle soit exécutée de manière automatisée. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

## Compagnies B2B

Si vous utilisez B2B dans Shopify, vous pouvez créer des compagnies en plus des clients. Vous pouvez lier un ou plusieurs clients individuels à une compagnie. Vous pouvez également définir des modalités de paiement, des emplacements et des catalogues.

## Paramètres importants lors de l’importation de compagnies B2B à partir de Shopify

Que vous importiez des compagnies à partir de Shopify en bloc ou lors de l’importation de commandes, les paramètres suivants dans la table permettent de gérer le processus.

|Champ|Désignation|
|------|-----------|
|**Importation de compagnie à partir de Shopify**|Sélectionnez **Toutes les compagnies** si vous prévoyez d’importer des clients à partir de Shopify en bloc, soit manuellement en utilisant l’action **Compagnies sync.**, soit via la file d’attente des tâches pour les mises à jour récurrentes. Quelle que soit la sélection, les informations client sont toujours importées avec la commande. Cependant, l’utilisation de ces informations dépend du champ **Modèles compagnie Shopify** et des paramètres du champ **Type de mappage compagnie**.|
|**Type de mappage de compagnie**|Définissez comment le connecteur effectue le mappage.</br></br>- **Par courriel/téléphone**, pour que le connecteur mappe les compagnies Shopify importées à un client existant dans Business Central en utilisant le courriel et le téléphone du contact principal.</br></br>- Sélectionnez **Toujours prendre la compagnie par défaut** pour que le système utilise une compagnie du champ **N° compagnie par défaut** . |
|**Shopify peut mettre à jour la compagnie**| Sélectionnez ce champ pour que le connecteur mette à jour les clients trouvés si l’option **Par courriel/téléphone** est sélectionnées dans le champ **Type de mappage compagnies**.|
|**Créer automatiquement des compagnies inconnues**| Sélectionnez ce champ pour que le connecteur crée les clients si l’option **Par courriel/téléphone** est sélectionnée dans le champ **Type de mappage compagnies**. Un client est créé en utilisant les données importées et le **Code modèle client/compagnie** défini dans les pages **Fiche magasin Shopify** ou **Modèle client Shopify**.|
|**Code modèle client/compagnie**|Utilisez ce champ avec **Créer automatiquement des compagnies inconnues**.</br></br>- Choisissez le modèle par défaut à utiliser pour les clients créés automatiquement. Assurez-vous que les champs obligatoires sont renseignés sur le modèle, comme les champs **Groupe de report marché**, **Groupe de report client**, **Taxe sur la valeur ajoutée (TVA)** ou d’autres champs qui concernent les taxes.</br></br>- Vous pouvez définir des modèles par pays/région dans la page **Modèles client Shopify**, ce qui est utile pour calculer correctement les taxes.</br></br>En savoir plus sur [Configurer les taxes](setup-taxes.md).|

> [!NOTE]  
> La compagnie doit avoir un interlocuteur principal. Sinon, le connecteur passe à la compagnie.
> Un seul emplacement le plus ancien est importé.
> Seul le contact principal est importé.

## Paramètres importants lors de l’exportation de compagnies B2B vers Shopify

Vous pouvez exporter les clients existants dans Shopify en bloc comme compagnie. Dans chaque cas, une compagnie et un emplacement par défaut sont créés ainsi qu’un contact principal. Il est également possible de créer un catalogue.

|Champ|Désignation|
|------|-----------|
|**Possibilité de mettre à jour les compagnies Shopify**| Activez cette option pour générer des mises à jour ultérieurement à partir de Business Central pour les compagnies qui existent déjà dans Shopify.|
|**Autorisations contact par défaut**| Spécifiez les autorisations qui doivent être attribuées au contact principal. Vous pouvez choisir entre **Aucune**, **Commandes uniquement** et **Administrateur de l’emplacement**.|
|**Créer automatiquement catalogue**| Activez cette option si vous souhaitez créer un catalogue incluant tous les produits. Un catalogue est créé pour chaque compagnie exportée.|

## Exporter une compagnie B2B vers Shopify

### Synchronisation initiale des compagnies B2B de Business Central vers Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Compagnie Shopify** et choisissez le lien associé.
2. Choisissez l’action **Ajouter une compagnie**.
3. Dans le champ **Code magasin**, saisissez le code. Si vous ouvrez la fenêtre **Compagnie Shopify** dans la page **Fiche magasin**, le code magasin est rempli automatiquement.
4. Définissez des filtres sur les clients selon vos besoins. Par exemple, vous pouvez filtrer par code pays/région.
5. Cliquez sur **OK**.

Les compagnies résultantes sont automatiquement créées dans Shopify.

> [!NOTE]  
> La synchronisation initiale des compagnies de [!INCLUDE[prod_short](../includes/prod_short.md)] vers Shopify ne tient pas compte des paramètres **Possibilité de mettre à jour les compagnies Shopify**.

### Synchronisation compagnies B2B

1. Sélectionnez l’icône en forme ![d’Ampoule qui ouvre la fenêtre de recherche 1.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasin Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez le magasin spécifique pour lequel vous voulez synchroniser les clients.
3. Sélectionnez l’action **Synchroniser la compagnie**.

Sinon, utilisez l’action **Commencer synchroniser compagnies** dans la page **Compagnie Shopify** ou recherchez le traitement en lot **Synchroniser la compagnie**.

Vous pouvez programmer la tâche pour exécuter de manière automatisée. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

## Voir aussi .

[Mise en route du connecteur pour Shopify](get-started.md)  
