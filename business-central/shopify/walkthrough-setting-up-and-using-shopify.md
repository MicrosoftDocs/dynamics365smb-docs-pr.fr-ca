---
title: Configurer et utiliser le connecteur Shopify
description: Divers scénarios d’intégration pour démontrer le workflow entre Shopify et Business Central
ms.date: 06/21/2022
ms.topic: article
ms.service: dynamics365-business-central
ms.search.form: '30101, 30102, 30106, 30107, 30113, 30115, 30126'
ms.reviewer: solsen
author: AndreiPanko
ms.author: andreipa
---

# Procédure pas à pas : configurer et utiliser le connecteur Shopify

Cette section illustre certains scénarios typiques et vous guide à travers les étapes pour tester ou former les utilisateurs sur le workflow du magasin intégré [!INCLUDE[prod_short](../includes/prod_short.md)] et du magasin Shopify.

## Conditions préalables 

### Shopify

Vous devez disposer :

- D’un compte Shopify
- D’une boutique en ligne Shopify

En savoir plus sur la création de versions d’essai Shopify et les paramètres recommandés sur [Création et configuration d’un compte Shopify](shopify-account.md).

### Business Central

Vous devez disposer d’un compte [!INCLUDE[prod_short](../includes/prod_short.md)]. 

Par exemple, vous pouvez créer un compte démo ou démarrer un essai. Pour en savoir plus, rendez-vous sur [Préparation des démonstrations de [!INCLUDE[prod_short](../includes/prod_short.md)]](/dynamics365/business-central/dev-itpro/administration/demo-environment.md) et [Inscrivez-vous à l’essai](../trial-signup.md). 

## Connexion de Business Central à la boutique Shopify

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des étapes suivantes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Dans le champ **Code**, entrez `DEMO1`.
4. Dans le champ **URL Shopify**, saisissez l’URL de la boutique en ligne à laquelle vous souhaitez vous connecter.
5. Activez la bascule **Activé**, lisez et acceptez les conditions générales.

Configurez le magasin Shopify comme indiqué dans les étapes suivantes :

1. Activez le bouton bascule **Journal activé**.
2. Désactivez **Autoriser les synchronisations en arrière-plan**.
3. Sélectionnez **Vers Shopify** dans le champ **Synchroniser l’article**.
4. Sélectionnez **Vers Shopify** dans le champ **Synchroniser les images de l’article**.
5. Activez le bouton à bascule **Synchroniser les attributs d’un article**.
6. Activez le bouton bascule **Inventaire suivi**.
7. Sélectionnez **Refuser** dans le champ **Stratégie d’inventaire par défaut** .
8. Activez le bouton de basculement **Créer automatiquement des clients inconnus**.
9. Remplissez le champ **Code modèle client** avec le modèle approprié.
10. Remplissez le **Compte de frais d’expédition**, le **Compte de pourboires** avec le compte de revenus. Par exemple, aux É.-U., utilisez `40100`.
11. Activez le bouton de basculement **Créer automatiquement des commandes**.

Configurer le mappage de l’emplacement :

1. Sélectionnez l’action **Emplacements** pour ouvrir **Emplacements des magasins Shopify**.
2. Sélectionnez l’action **Obtenir les emplacements Shopify** pour importer tous les emplacements définis dans le Shopify.
3. Dans **Filtre emplacement**, entrez `''|EAST|MAIN`.
4. Désactivez le bouton bascule **Désactivé** pour activer la synchronisation de l'inventaire pour l’emplacement Shopify sélectionné.

## Procédure pas à pas : commencer à vendre des produits en ligne

### Scénario

Disons que vous voulez essayer Shopify en tant que boutique en ligne sans passer beaucoup de temps à configurer les choses, surtout parce que vous entretenez déjà vos articles dans [!INCLUDE[prod_short](../includes/prod_short.md)] correctement. Après avoir lancé votre boutique en ligne Shopify, vous obtenez immédiatement de nouveaux clients qui sont satisfaits de votre boutique et de leur expérience d’achat. Alors, ils décident de laisser des pourboires à la caisse.

### Étapes

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], effectuez les étapes suivantes :

1. Sélectionnez ![l’icône en forme d’ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Choisissez l’action **Ajouter des articles**.
3. Dans le champ **Code magasin**, entrez *DÉMO1*.
4. Définissez le filtre `CHAIR` dans le champ **Code de catégorie d’article** (ajoutez un champ de filtre si nécessaire).
5. Sélectionnez **OK** et attendez que la synchronisation initiale des articles et des prix soit terminée.
6. Sélectionnez l’action **Synchroniser les images des produits**.
7. Sélectionnez l’action **Synchroniser l'inventaire**.

Dans la **boutique en ligne Shopify**
> [!Tip]  
> Ouvrez **Admin Shopify**, en accédant à l’URL spécifiée dans le champ **URL** de la page **Carte de la boutique Shopify**. Choisissez ensuite l’icône en forme d’œil à côté du canal de vente de la **boutique en ligne**, située dans la barre latérale **Admin Shopify**. 

Ouvrez le catalogue de produits. Avis :

* Titres, images et prix des produits.
* Indicateur de disponibilité (épuisé pour les produits en rupture de stock).

Choisissez n’importe quel produit qui peut être vendu, par exemple, le `BERLIN Swivel Chair, yellow`. Notez que la description contient des attributs d’élément.

Choisissez le bouton **Acheter maintenant** et passez à la caisse.

1. Dans le champ **Adresse de courriel ou numéro de téléphone portable**, saisissez `cl@contoso.com` (ou l’adresse de courriel à laquelle vous souhaitez recevoir les confirmations de commande et de livraison).
2. Dans **Prénom** et **Nom**, saisissez `Claudia Lawson`.
3. Entrez l’adresse locale.
4. Cochez la case **Enregistrer ces informations pour la prochaine fois** .
5. Cliquez sur le bouton **Continuer vers la livraison**.
6. Conservez `Standard` comme méthode de livraison, puis choisissez le bouton **Continuer vers le paiement** .
7. Sélectionnez un pourboire de `10%`.
8. Dans le champ **Carte de crédit**, saisissez `1` si vous utilisez *(pour tester) Bogus Gateway*, si vous utilisez les *Shopify Payments* en mode test, saisissez `5555 5555 5555 4444` dans le champ **Carte de crédit**.
9. Renseignez le champ **Nom sur la fiche**.
10. Dans le champ **Date d’expiration**, saisissez le mois/l’année en cours.
11. Dans le champ **Code de sécurité**, entrez `111`.
12. Cliquez sur le bouton **Payer maintenant**.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des prochaines étapes :

1. Sélectionnez ![l’icône en forme d’ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Commandes Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez l’action **Synchroniser les commandes à partir de Shopify**.
3. Cliquez sur **OK**.

La commande importée est prête à être traitée.

1. Sélectionnez la commande importée pour ouvrir la fenêtre **Commande Shopify**.
2. Notez que le client et le document de vente sont créés.
3. Explorez les actions **Risque** et **Coût d’expédition**.
4. Sélectionnez l’action **Document de vente** pour ouvrir la fenêtre **Document de vente**. Le document de vente est une demande qui, si nécessaire, peut être couverte par l’assembly, la production ou l’achat à l’aide du moteur de planification. Il prend également en charge divers processus de manutention en entrepôt avec une séparation complète des tâches.
5. Sélectionnez l’action **Rouvrir**.
6. Dans le champ **Agent**, saisissez `DHL`.
7. Dans **N° de suivi du colis**, entrez `123456789`.
8. Cliquez sur **Reporter**, conservez l’option **Livrer et facturer**, puis cliquez sur le bouton **OK**.

Désormais, les données physiques et financières sont enregistrées dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Il est temps d’informer Shopify des changements.

1. Sélectionnez ![l’icône en forme d’ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Synchroniser livraisons avec Shopify** et choisissez le lien associé.
2. Cliquez sur **OK**.

Dans **Administration Shopify** notez que la commande est maintenant marquée comme *Exécuté*. Vous pouvez également consulter les détails de la livraison et y voir l’URL de suivi. Si vous exécutez à nouveau **Synchroniser les commandes à partir de Shopify**, la commande sera archivée dans les deux systèmes.

## Procédure pas à pas : invitez vos clients dans votre nouvelle boutique en ligne

### Scénario

Après un lancement rapide et réussi de votre nouvelle boutique en ligne, vous souhaitez que vos clients actuels la visitent et commencent à passer des commandes.

### Étapes

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des étapes suivantes :

1. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin **DEMO1** pour lequel vous voulez synchroniser les clients pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Synchroniser les clients**.

Dans **Administration Shopify** notez que les clients ont été importés. Ouvrez l’un des clients et remarquez que le prénom et le nom du client proviennent du champ **Nom du contact** de la **Fiche client**. Le nom de la compagnie se trouve dans l’adresse par défaut, liée au client. Choisissez **Envoyer une invitation au compte** pour inviter le client.

## Procédure pas à pas : ajustement de la gestion des éléments

### Scénario 

Vous aimerez ajouter plus de flexibilité et de contrôle à vos processus de gestion des articles. Vous souhaitez améliorer la description du produit et souhaitez ajouter plus d’étapes de révision avant que les produits ne soient disponibles pour le client final.

### Étapes

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des étapes suivantes :

Préparez les données.

1. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  entrez **Groupe prix client**, puis sélectionnez le lien associé.
2. Ajoutez un nouveau groupe de tarifs. Dans le champ **Code**, entrez `SHOPIFY`.
3. Fermez fenêtre **Groupe prix client**.
4. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  entrez **Articles**, puis choisissez le lien associé.
5. Sélectionnez l’article **1896-S, bureau Athens**.
6. Choisissez l’action **Variantes**, puis ajoutez deux variantes et `PREMIUM, Athens Desk, Premium edition` et `ESSENTIAL, Athens Desk, Essential edition`.
7. Choisissez **Texte développé**, créez un texte développez valide pour tous les codes de langue. Dans le champ **Description**, entrez `Shopify`. 
8. Ajoutez la description suivante avec les balises HTML : `<b>Simple stylish design</b> blends with any ensemble. <i>Available in two editions.</i>`.
9. Choisissez **prix de vente** et ajoutez de nouveaux prix comme indiqué dans le tableau suivant :

  |Ligne|**Type vente**|**Code vente**|Type|Code|Code de variante<br>(ajoutez le champ via la personnalisation)|Prix unit|
  |------|------------|------------|------------|------------|------------|------------|
  |1|Groupe prix client|SHOPIFY|Article|1896-S|ESSENTIAL|700|
  |2|Groupe prix client|SHOPIFY|Article|1896-S|PREMIUM|1 000|

10. Choisissez **Escomptes sur les ventes** et ajoutez un nouvel escompte :

* **Type de vente** *Groupe escompte client*
* **Code vente** *VENTE AU DÉTAIL*
* **Type** *Article*
* **Code** *1896-S*
* **Code unité de mesure** *PCS*
* **% escompte ligne** *10*

11. Choisissez **références article** et ajoutez les lignes suivantes :

  |Ligne|**Type référence**|**N° référence**|Code de variante|
  |------|------------|------------|------------|
  |1|Code-barres|77777777|ESSENTIAL|
  |2|Code-barres|11111111|PREMIUM|

12. Fermez la **fiche article**.
13. Sélectionnez l’article **1920-S, Table de conférence ANTWERP**.
14. Choisissez **Ajuster l'inventaire** et dans le champ **Nouvel inventaire**, saisissez `100` pour les emplacements *EST* et *OUEST*. 
1. Cliquez sur **OK**.
1. Fermez la **fiche article**.

Ajustez les paramètres de synchronisation.

1. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin *DÉMO1* pour lequel vous voulez synchroniser les articles pour ouvrir la page Fiche magasin Shopify.
3. Sélectionnez *SHOPIFY* dans le champ **Groupe de prix client**.
4. Sélectionnez *VENTE AU DÉTAIL* dans le champ **Groupe escompte client**.
5. Activez le champ **Synchronisation du texte développé de l’article**.
6. Sélectionnez *N° d’article + code de variante* dans le champ **Mappage unité de stock**.
7. Sélectionnez *Brouillon* dans le champ **État des produits créés**.
8. Sélectionnez *État à archiver* dans le champ **Action pour le produit supprimé**.

Exécuter la synchronisation.

1. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin *DÉMO1* pour lequel vous voulez synchroniser les articles pour ouvrir la page **Fiche magasin Shopify**.
3. Choisissez l’action **Produits** pour ouvrir la fenêtre **Produits Shopify**.
4. Choisissez l’action **Ajouter des articles**.
5. Définissez le filtre *TABLE* sur le champ **Code de catégorie d’article**.
6. Sélectionnez l’action **Synchroniser les images des produits**.
7. Sélectionnez l’action **Synchroniser l'inventaire**.

Les produits sont ajoutés. Notez que l'état est défini sur *Brouillon*, par conséquent les articles ne sont pas visibles dans la boutique en ligne Shopify.

1. Sélectionnez la ligne avec l’article *1920-S, Table de conférence ANTWERP*. Dans le champ **Titre du SEO**, entrez le `Rectangular meeting table Antwerp, 10 seats, black`.
2. Dans le champ **État**, sélectionnez *Actif*.
3. Sélectionnez la ligne avec l’article *1906-S, ATHENS, Piédestal mobile*, puis choisissez l’action **Supprimer**.

Dans **Administration Shopify**, notez que tous les produits ont des états différents.

* *Table de conférence ANVERS* est *Active*, car nous avons modifié l'état dans la fenêtre **Produit Shopify**.
* *Bureau ATHÈNES* est un *Brouillon*, car nous avons configuré l'état par défaut pour tous les produits ajoutés sur *Brouillon*.
* Le *piédestal mobile ATHÈNES* est *Archivé* parce que nous avons configuré la boutique pour attribuer automatiquement l'état *Archivé* aux produits supprimés.

Notez que l'inventaire de la table de conférence ANVERS est de 100, car nous avons configuré le système pour utiliser l’inventaire uniquement à partir de deux emplacements PRINCIPAL et EST. L'inventaire à d’autres emplacements (OUEST) est ignoré.

* Ouvrez *Table de conférence ANTWERP*, notez les champs **Type personnalisé**, **Fournisseur**, **Poids**, **Coût par article**, puis la section **Aperçu de la liste du moteur de recherche**.
* Ouvrez *Bureau Athènes*, faites défiler jusqu’à la section **Variantes** et notez comment **Unité de stock** est renseigné.
* Choisissez **Modifier** pour revoir le code-barres et les prix.
* Modifiez l'état de *Bureau Athènes* sur *Actif* et choisissez l’action **Aperçu**.

Dans la **boutique en ligne Shopify**, ouvrez le catalogue de produits, recherchez le produit *Bureau ATHENS*. Notez que différentes options sont disponibles. Pour différentes options, les prix sont différents. Faites attention aux informations d'escompte.

## Procédure pas à pas : importer des articles de Shopify

### Scénario 

Vous avez déjà une boutique en ligne performante et souhaitez commencer à l’utiliser [!INCLUDE[prod_short](../includes/prod_short.md)] comme logiciel de gestion d’entreprise. Vous souhaitez importer autant de données de Shopify que possible. 

### Étapes

Ceci est la suite de la [Procédure pas à pas : Commencez à vendre des produits en ligne](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online). Vous pouvez également essayer avec vos propres données, par exemple votre boutique ou bac à sable Shopify.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des étapes suivantes :

#### Préparer les données

1. Passez à un essai gratuit de 30 jours sans exemples de données. Pour plus d’informations, voir [Ajouter vos propres données à une société test vide](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions#add-your-own-data-to-an-empty-trial-company).
2. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
3. Sélectionnez l'action **Nouveau**.
4. Dans le champ **Code**, entrez `DEMO2`.
5. Dans le champ **URL Shopify**, saisissez l’URL de la boutique en ligne à laquelle vous souhaitez vous connecter.
6. Activez la bascule **Activé**, lisez et acceptez les conditions générales.

Configurez le magasin Shopify comme indiqué ci-dessous dans les étapes suivantes :

7. Activez le bouton de basculement **Journal activé**.
8. Désactivez **Autoriser les synchronisations en arrière-plan**.
9. Sélectionnez **De Shopify** dans le champ **Synchroniser l’article**.
5. Activez le bouton à bascule **Créer automatiquement des articles inconnus**.
11. Remplissez le champ **Code modèle article** avec le modèle approprié.
12. Sélectionnez **De Shopify** dans le champ **Synchroniser les images de l’article**.
13. Sélectionnez **Tous les clients** dans **Importation de clients depuis Shopify**.
14. Activez le bouton à bascule **Créer automatiquement des clients inconnus**.
15. Remplissez le champ **Code modèle client** avec le modèle approprié.
16. Remplissez le **Compte de frais d’expédition**, le **Compte de pourboires** avec le compte de revenus. Par exemple, aux É.-U., utilisez `40100`.
17. Activez le bouton de bascule **Créer automatiquement des commandes**.

#### Exécuter la synchronisation

1. Sélectionnez l’![icône en forme d’Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin *DÉMO2* pour lequel vous voulez synchroniser les données pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Synchroniser les produits**.
4. Sélectionnez l’action **Synchroniser les images des produits**.
5. Sélectionnez l’action **Synchroniser les clients**.

### Résultats

* Les produits Shopify sont importés. Pour vérifier cela, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  , saisissez **Produits Shopify** et choisissez le lien associé.
* Des articles avec des images sont créés. Pour vérifier cela, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  entrez **Article**, puis choisissez le lien associé.
* Les clients Shopify sont importés. Pour vérifier cela, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  entrez **Clients Shopify**, puis choisissez le lien associé.
* Les clients sont créés. Pour vérifier cela, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"),  entrez **Clients**, puis choisissez le lien associé.


## Voir aussi

[Mise en route avec le connecteur Shopify](get-started.md)  