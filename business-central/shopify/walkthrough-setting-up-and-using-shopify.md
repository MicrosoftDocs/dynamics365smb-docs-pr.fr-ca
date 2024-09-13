---
title: Configurer et utiliser le connecteur Shopify
description: Divers scénarios d’intégration pour démontrer le workflow entre Shopify et Business Central
ms.date: 08/30/2024
ms.topic: article
ms.service: dynamics-365-business-central
ms.search.form: '30101, 30102, 30106, 30107, 30113, 30115, 30126, 30156, 30157'
ms.reviewer: bholtorf
author: brentholtorf
ms.author: bholtorf
---

# <a name="walkthrough-set-up-and-use-the-shopify-connector"></a>Procédure pas à pas : configurer et utiliser le connecteur Shopify

Cette section illustre certains scénarios typiques et vous guide à travers les étapes pour tester ou former les utilisateurs sur le workflow du magasin intégré [!INCLUDE[prod_short](../includes/prod_short.md)] et du magasin Shopify.

## <a name="prerequisites"></a>Conditions préalables

### <a name="shopify"></a>Shopify

Vous devez disposer :

- D’un compte Shopify
- D’une boutique en ligne Shopify

En savoir plus sur la création de versions d’essai Shopify et les paramètres recommandés dans [Créer et configurer un compte Shopify](shopify-account.md).

### <a name="business-central"></a>Business Central

Vous devez disposer d’un compte [!INCLUDE[prod_short](../includes/prod_short.md)].

Par exemple, vous pouvez créer un compte démo ou démarrer un essai. Pour en savoir plus, rendez-vous sur [Préparer les environnements de démonstrations de Dynamics 365 Business Central](/dynamics365/business-central/dev-itpro/administration/demo-environment) et [S’inscrire à l’essai](../trial-signup.md). 

## <a name="connect-business-central-to-the-shopify-shop"></a>Connexion de Business Central à la boutique Shopify

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez l’action **Nouveau**.
3. Dans le champ **Code**, saisissez **DEMO1**.
4. Dans le champ **URL Shopify**, saisissez l’URL de la boutique en ligne à laquelle vous souhaitez vous connecter.
5. Activez le bouton à bascule **Activé**, lisez et acceptez les conditions générales.

Pour configurer le magasin Shopify, procédez comme suit :

1. Désactivez **Autoriser les synchronisations en arrière-plan**.
2. Sélectionnez *Vers Shopify* dans le champ **Synchroniser l’article**.
3. Sélectionnez *Vers Shopify* dans le champ **Synchroniser les images de l’article**.
4. Activez le bouton à bascule **Synchroniser les attributs d’un article**.
5. Activez le bouton bascule **Inventaire suivi**.
6. Sélectionnez *Refuser* dans le champ **Stratégie d’inventaire par défaut** .
7. Activez le bouton de basculement **Créer automatiquement des clients inconnus**.
8. Remplissez le champ **Code modèle client/compagnie** avec le modèle approprié.
9. Remplissez le **Compte de frais d’expédition**, le **Compte de pourboires** avec le compte de revenus. Par exemple, aux États-Unis, utilisez **40210**.
10. Activez le bouton de basculement **Créer automatiquement des commandes**.
11. Désactivez le bouton à bascule **Libérer automatiquement les documents de vente**.

Configurer le mappage de l’emplacement :

1. Sélectionnez l’action **Emplacements** pour ouvrir **Emplacements des magasins Shopify**.
2. Sélectionnez l’action **Obtenir les emplacements Shopify** pour importer tous les emplacements définis dans Shopify. Sélectionnez l’entrée avec la bascule **Est principal** est sélectionnée.
3. Dans le **Filtre d’emplacement**, entrez **’’|EAST|MAIN**.
4. Pour activer une synchronisation d’inventaire pour un emplacement sélectionné, dans le champ  Shopify Calcul du stock **, Sélectionner** Solde disponible projeté aujourd’hui **.**

## <a name="walkthrough-start-selling-products-online"></a>Procédure pas à pas : commencer à vendre des produits en ligne

### <a name="scenario"></a>Scénario

Disons que vous voulez essayer Shopify en tant que boutique en ligne sans consacrer beaucoup de temps à la configuration, surtout parce que vous entretenez déjà vos articles dans [!INCLUDE[prod_short](../includes/prod_short.md)] correctement. Après avoir lancé votre boutique en ligne Shopify, vous obtenez immédiatement de nouveaux clients qui sont satisfaits de votre boutique et de leur expérience d’achat. Alors, ils décident de laisser des pourboires à la caisse.

### <a name="steps"></a>Étapes

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Sélectionnez **Ajouter des articles**.
3. Dans le champ **Code boutique**, saisissez **DEMO1**.
4. Dans le champ **Code de catégorie d’article**, définissez le filtre **CHAIR**.
5. Activez le bouton à bascule **Synchroniser les images de produit**.
6. Activez le bouton à bascule **Synchroniser l'inventaire**.
7. Sélectionner **OK** et attendez que la synchronisation initiale des articles, des prix, des images et de l’inventaire soit terminée.

Dans la **boutique en ligne Shopify** :
> [!Tip]  
> Ouvrez **Admin Shopify** en accédant à l’URL spécifiée dans le champ **URL** de la page **Carte de la boutique Shopify**. Sélectionnez l’icône en forme d’œil à côté du canal de vente de la **boutique en ligne**, située dans la barre latérale **Admin Shopify**. 

Ouvrez le catalogue de produits. Avis :

* Titres, images et prix des produits.
* Indicateur de disponibilité (épuisé pour les produits en rupture de stock).

Choisissez n’importe quel produit qui peut être vendu. Par exemple, la chaise pivotante BERLIN, jaune. **·** Notez que la description contient des attributs d’élément.

Sélectionnez **Acheter maintenant** et passez à la caisse.

1. Dans le champ  **E-mail ou numéro de téléphone portable**, saisissez **cl@contoso.com** (ou une adresse e-mail à laquelle vous souhaitez recevoir les confirmations de commande et d’expédition).
2. Dans les champs **Prénom** et **Nom de famille**, saisissez **Claudia** et **Lawson**.
3. Entrez l’adresse locale.
4. Cochez la case **Enregistrer ces informations pour la prochaine fois** .
6. Conservez *Standard* comme mode d’expédition.
8. Dans le champ  **Numéro de crédit carte**, saisissez **1** si vous utilisez **(pour tester) Bogus Gateway**, ou saisissez **5555 5555 5555 4444** si vous utilisez **Shopify les paiements** en mode test.
9. Renseignez le champ **Nom sur la fiche**.
10. Dans le champ **Date d’expiration**, saisissez le mois/l’année en cours.
11. Dans le **Code de sécurité**, entrez **111**.
12. Facultatif : Sélectionner **10 %** pourboire.
13. Sélectionnez **Payer maintenant**.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des prochaines étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Commandes Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez l’action **Synchroniser les commandes à partir de Shopify**.
3. Sélectionnez **OK**.

La commande importée est prête à être traitée.

1. Sélectionnez la commande importée pour ouvrir la fenêtre **Commande Shopify**.
2. Notez que le client et les documents de vente sont créés.
3. Explorez les actions liées aux **risques** et aux **frais d’expédition** .
4. Sélectionnez **Document de vente** pour ouvrir la fenêtre **Document de vente**. Le document de vente est une demande qui, si nécessaire, peut être couverte par l’assembly, la production ou l’achat à l’aide du moteur de planification. Il prend également en charge divers processus de manutention en entrepôt avec une séparation complète des tâches.
6. Dans le champ **Agent**, saisissez **DHL**. Rouvrez la commande si nécessaire en choisissant l’action **Réouvrir** .
7. Dans le **Numéro de suivi du colis**, saisissez **123456789**.
8. Sélectionnez **Reporter**, conservez l’option **Livrer et facturer**, puis sélectionnez **OK**.

Désormais, les données physiques et financières sont enregistrées dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Il est temps d’informer Shopify des changements.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Synchroniser les livraisons avec Shopify** et sélectionnez le lien associé.
2. Sélectionnez **OK**.

Dans **Admin Shopify** notez que la commande est maintenant marquée comme *Exécuté*. Vous pouvez également consulter les détails de la livraison et y voir l’URL de suivi. Si vous exécutez à nouveau **Synchroniser les commandes à partir de Shopify**, la commande sera archivée dans les deux systèmes.

## <a name="walkthrough-add-your-customers-to-your-new-online-store"></a>Procédure pas à pas : ajouter vos clients dans votre nouvelle boutique en ligne

### <a name="scenario-1"></a>Scénario

Après un lancement rapide et réussi de votre nouvelle boutique en ligne, vous souhaitez que vos clients actuels la visitent et commencent à passer des commandes. En fonction de votre Shopify plan et processus, vous pouvez essayer les flux B2B et DTC

### <a name="dtc-steps"></a>Étapes DTC

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Clients Shopify** et sélectionnez le lien associé.
2. Sélectionnez **Ajouter des clients**.
3. Dans le champ **Code boutique**, saisissez **DEMO1**.
4. Dans le champ **N°**, Champ, définissez le filtre **20000**.
5. Sélectionnez **OK** et attendez que la synchronisation initiale des clients soit terminée.

Dans **Admin Shopify** notez que le client a été importés. Ouvrez les clients et remarquez que le prénom et le nom du client proviennent du champ **Nom du contact** de la **Fiche client**. Le nom de la compagnie se trouve dans l’adresse par défaut, liée au client. Si vous utilisez des **comptes clients classiques**, vous pouvez alors Sélectionner **envoyer une invitation de compte** pour inviter le client. Avec les **nouveaux comptes clients**, aucun mot de passe n’est requis pour que les clients se connectent. Au lieu de cela, Shopify permet à vos clients de se connecter à l’aide d’un code de vérification unique à 6 chiffres envoyé par e-mail. 

### <a name="b2b-steps"></a>Étapes B2B

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Compagnies Shopify** et sélectionnez le lien associé.
2. Sélectionnez **Ajouter une compagnie**.
3. Dans le champ Code de la boutique, saisissez  **DEMO1** . **·**
4. Réglez le filtre **30000** sur le **N°.** .
5. Sélectionnez **OK** et attendez que la synchronisation initiale des clients soit terminée.

Dans **Shopify Admin**, notez que la société et le client ont été importés. Ouvrez les clients et remarquez que la boîte de faits de l’entreprise contient des liens vers l’entreprise, l’emplacement et les autorisations attribuées.
Pour inviter le client, Sélectionner **[...]** dans la FactBox **Entreprise**, puis Sélectionner **Envoyer un e-mail d’accès B2B**.

## <a name="walkthrough-fine-tuning-of-item-management"></a>Procédure pas à pas : ajustement de la gestion des articles

### <a name="scenario-2"></a>Scénario

Vous aimerez ajouter plus de flexibilité et de contrôle à vos processus de gestion des articles. Vous souhaitez améliorer les descriptions de produits et souhaitez ajouter plus d’étapes de révision avant que les produits ne soient disponibles pour tous les clients.

### <a name="steps-1"></a>Étapes

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

Préparez les données.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Groupe prix client** et sélectionnez le lien associé.
2. Ajoutez un nouveau groupe de tarifs. Dans le champ **Code**, saisissez **SHOPIFY**.
3. Fermez fenêtre **Groupe prix client**.
4. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Articles** et sélectionnez le lien associé.
5. Sélectionner item **1896-S, Athens Desk**, puis suivre ces étapes :

6. Sélectionner l’action **Variantes** puis ajoutez deux variantes : **PREMIUM, Athens Desk, édition Premium** et **ESSENTIAL, Athens Desk, édition Essential**.
7. Sélectionnez l’action **Texte marketing** et utilisez le **Brouillon avec Copilot** pour obtenir un texte créatif et engageant. Si la suggestion de texte marketing n’est pas activée, entrez simplement : « **Design simple et élégant** se marie avec n’importe quel ensemble. *Disponible en deux éditions.*.
8. Sélectionnez l’action **Prix de vente** et ajoutez de nouveaux prix comme indiqué dans le tableau suivant :

   |Ligne|Type vente|Code vente|Type|Code|Code de variante<br>(ajoutez le champ via la personnalisation)|Prix unit|
   |------|------------|------------|------------|----------------|------------|------------|
   |1|Groupe prix client|SHOPIFY|Article|1896-S|ESSENTIAL|700|
   |2|Groupe prix client|SHOPIFY|Article|1896-S|PREMIUM|1 000|

9. Sélectionnez l’action **Escomptes sur les ventes** et ajoutez un nouvel escompte :

   * **Type de vente** *Groupe escompte client*
   * **Code vente** *VENTE AU DÉTAIL*
   * **Type** *Article*
   * **Code** *1896-S*
   * **Code unité de mesure** *PCS*
   * **% escompte ligne** *10*

10. Sélectionner l’action **Références d’élément** et ajoutez les lignes suivantes :

   |Ligne|Type référence|N° référence|Code de variante|
   |------|------------|------------|------------|
   |1|Code-barres|77777777|ESSENTIAL|
   |2|Code-barres|11111111|PREMIUM|

11. Sélectionnez l’élément **1920-S, Table de conférence ANVERS**, puis procédez comme suit :
12. Sélectionner **Ajuster Inventaire** et dans le champ **Nouvel inventaire**, saisissez **100** pour les emplacements **EST** et **OUEST**.
13. Sélectionnez **OK**.

Ajustez les paramètres de synchronisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify** et sélectionnez le lien associé.
2. Sélectionner la **DEMO1** boutique pour laquelle vous souhaitez synchroniser les articles pour ouvrir la **Shopify page Boutique carte** .
3. Activez le champ **Synchronisation du texte Marketing**.
4. Dans le **SKU mappage** field, Sélectionner **Numéro d’article + code de variante**.
5. Dans le champ **Stratégie d’inventaire par défaut**, Sélectionner **Continuer**.
6. Dans le champ **Statut des produits créés**, Sélectionner **Brouillon**.
7. Dans le champ **Action pour le produit supprimé**, Sélectionner **Statut sur Archivé**.
8. Dans le champ **Groupe de prix client**, Sélectionner **SHOPIFY**.
9. Dans le champ **Groupe de remise client**, Sélectionner **VENTE AU DÉTAIL**.

Exécuter la synchronisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify** et sélectionnez le lien associé.
2. Sélectionner la **DEMO1** boutique pour laquelle vous souhaitez synchroniser les articles pour ouvrir la **Shopify page Boutique carte** .
3. Sélectionner **Produits** pour ouvrir la page **Shopify Produits** .
4. Sélectionnez l’action **Ajouter des articles**.
5. Définissez le filtre **TABLE|BUREAU** sur le champ **Code de catégorie d’article** .
6. Activez le bouton à bascule **Synchroniser les images de produit**.
7. Activez le bouton à bascule **Synchroniser l'inventaire**.
8. Sélectionner **OK** et attendez que la synchronisation initiale des articles, des prix, des images et de l’inventaire soit terminée.

Les produits sont ajoutés. Notez que le statut est défini sur **Brouillon** et que par conséquent les articles ne sont pas visibles dans la Shopify boutique en ligne.

1. Sélectionner la ligne avec l’article **1920-S, Table de conférence ANTWERP**. Dans le **Titre SEO**, saisissez **Table de réunion rectangulaire Anvers, 10 places, noire**.
2. Dans le champ **Statut**, Sélectionner **Actif**.
3. Sélectionner la ligne avec l’article **1906-S, ATHÈNES, Piédestal mobile** puis Sélectionner **Supprimer**.

Dans **Admin Shopify**, notez que tous les produits ont des états différents.

* *La table de conférence ANTWERP* est *active* car nous avons changé son statut sur la page **Shopify Produit** .
* *Bureau ATHÈNES* est un *Brouillon*, car nous avons configuré l'état par défaut pour tous les produits ajoutés sur *Brouillon*.
* Le *piédestal mobile ATHÈNES* est *Archivé* parce que nous avons configuré la boutique pour attribuer automatiquement l'état *Archivé* aux produits supprimés.

Notez que l’inventaire de la table de conférence ANTWERP est de 100, car nous avons configuré le système pour utiliser l’inventaire uniquement de deux emplacements, MAIN et EAST. L'inventaire à un autre emplacement (WEST) est ignoré.

* Ouvrez *Table de conférence ANTWERP*, notez les champs **Type personnalisé**, **Fournisseur**, **Poids** et **Coût par article**, puis la section **Aperçu de la liste du moteur de recherche**.
* Ouvrez *Bureau Athens*, faites défiler jusqu’à la section **Variantes** et notez comment le champ **Unité de stock** est rempli.
* Pour consulter le code-barres et les prix, Sélectionner **Modifier**.
* Modifiez le statut de **Athens Desk** en **Actif** et Sélectionner **version préliminaire**.

Dans la boutique en ligne, ouvrez le catalogue de produits et recherchez le produit  Shopify ATHENS Desk **.**  Notez que différentes options sont disponibles. Pour différentes options, les prix sont différents. Faites attention aux informations d'escompte.

### <a name="additional-steps-for-b2b"></a>Étapes supplémentaires pour le B2B

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

Vous pouvez configurer le connecteur pour créer et attribuer automatiquement un catalogue aux compagnies exportées. Les étapes ci-dessous sont utiles si vous souhaitez un contrôle plus précis de ce qui est disponible pour les clients B2B.

Dans **Shopify Admin**, créez et attribuez un catalogue.

1. Sélectionnez **Produits** puis **Catalogues** dans la barre latérale de **Shopify admin**.
2. Créer un catalogue pour des produits spécifiques. Donnez-lui le titre "B2B". 
3. Choisissez **Gérer**, puis **Gérer les produits et les prix**.
4. Sélectionner le filtre **Exclus**, recherchez **ATHENS Desk** et choisissez **Inclure dans le catalogue**.
5. Sélectionner **Clients**, puis **Entreprises** dans la barre latérale de **Shopify admin**.
6. Sélectionner **École des Beaux-Arts**, choisissez **[...]**, puis **Ajouter des catalogues** et ajoutez le **catalogue B2B** créé précédemment.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], procédez comme suit :

Préparez les données.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Articles** et sélectionnez le lien associé.
2. Sélectionner item **1896-S, Athens Desk**, puis suivre ces étapes :
3. Sélectionnez l’action **Escomptes sur les ventes** et ajoutez un nouvel escompte :

   * **Type de vente** *Groupe escompte client*
   * **Code vente** *GRAND CPTE*
   * **Type** *Article*
   * **Code** *1896-S*
   * **Code unité de mesure** *PCS*
   * **% escompte ligne** *25*

4. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Catalogues Shopify** et choisissez le lien associé.
5. Sélectionner **Obtenir les catalogues**.
6. Dans le champ **Code boutique**, saisissez **DEMO1**.
7. Sélectionner l’entrée avec le catalogue *B2B* pour lequel vous souhaitez synchroniser les prix.
8. Activez le bouton **Synchroniser les prix** .
9. Dans le champ **Groupe de prix client**, Sélectionner **SHOPIFY**.
10. Dans le champ **Groupe de remise client**, Sélectionner **GRAND COMPTE**.
11. Sélectionnez **Sync prix** et attendez que la synchronisation des prix soit terminée.

Dans **Shopify Admin**, explorez les prix du catalogue **B2B** .

Dans la **boutique en ligne Shopify**, ouvrez le catalogue de produits et recherchez le produit *Bureau ATHENS*. Notez les informations sur les prix et les remises.

## <a name="walkthrough-check-out-and-order-synchronization-for-individual-buyer-and-company-representative"></a>Procédure pas à pas : vérification et synchronisation des commandes pour l’acheteur individuel et le représentant de la compagnie

Ceci est la suite de la [Procédure pas à pas : Commencez à vendre des produits en ligne](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online). Vous pouvez également essayer avec vos propres données, par exemple en utilisant votre Shopify magasin ou votre sandbox.

Acheteur individuel

1. Dans la **boutique en ligne Shopify**. Choisissez icône **compte**. Entrer le courriel auquel vous avez accès.
2. connectez-vous en utilisant un code de vérification à 6 chiffres à usage unique envoyé par e-mail que vous avez saisi.
3. Explorez le catalogue de produits, vous devriez pouvoir voir tous les produits avec leurs prix de détail.
4. Sélectionnez la variante Essential, puis sélectionnez **Acheter maintenant** et procédez au paiement.
5. Remplir **Prénom** et **Nom**.
6. Entrez l’adresse locale.
7. Conservez *Standard* comme mode d’expédition.
8. Dans le champ  **Numéro de crédit carte**, saisissez **1** si vous utilisez **(pour tester) une passerelle fictive**, ou saisissez **5555 5555 5555 4444** si vous utilisez **Shopify des paiements** en mode test.
9. Dans le champ **Date d’expiration**, saisissez le mois/l’année en cours.
10. Dans le **Code de sécurité**, entrez **111**.
11. Renseignez le champ **Nom sur la fiche**.
12. Sélectionnez **Payer maintenant**.

Représentant de la compagnie

[!INCLUDE [shopify-preview](../includes/shopify-preview.md)]

1. Dans **Shopify Admin**.
2. Sélectionnez **Clients**, puis **Compagnies** dans la barre latérale de **Admin Shopify**.
3. Ouvrir *l’entrée à l’École des Beaux-Arts* .
4. Choisissez **[...]** dans la case d’informations **École des beaux-arts**, puis **Modifier les conditions de paiement**, puis Sélectionner **Dû le exécution**.
5. Choisissez **[...]** dans la zone d’informations **Clients**, puis **Ajouter un client**, puis ajoutez celui avec l’e-mail que vous avez utilisé pour vous connecter au magasin plus tôt.
6. Dans la **boutique en ligne Shopify**. Choisissez icône **compte**. Entrer le courriel auquel vous avez accès.
7. connectez-vous en utilisant un code de vérification à 6 chiffres à usage unique envoyé par e-mail que vous avez saisi.
8. Explorez le catalogue de produits, vous devriez pouvoir voir uniquement les produits ajoutés au catalogue B2B avec des prix de détail spéciaux.
9. Sélectionner la variante essentielle, Sélectionner **Achetez-la maintenant**, et passez à la caisse.
10. Notez que le compte, le destinataire et le mode de paiement sont renseignés.
11. Remplissez le champ  **Numéro de bon de commande** avec **PO-12345**.
12. Sélectionner **Soumettre la commande**.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], exécutez l’une des prochaines étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Commandes Shopify**, puis sélectionnez le lien associé.
2. Sélectionnez l’action **Synchroniser les commandes à partir de Shopify**.
3. Sélectionnez **OK**.

La commande importée est prête à être traitée.

1. Sélectionner la commande importée pour ouvrir la page **Shopify Commande** .
2. Notez que les deux commandes ont été soumises par la même personne, elles sont liées à deux clients différents.
3. Dans la commande soumise au nom de l’entreprise, vous pouvez voir une valeur dans le champ  **Numéro de bon de commande**, qui est également transférée dans le champ  **Numéro de document externe** du document de vente créé.
4. Étant donné que nous avons configuré l’entreprise B2B pour gérer les paiements en dehors de Shopify, le **statut financier** est défini sur **En attente**. Après avoir reçu le paiement, Sélectionner l’action **Marquer comme payé** . Les mises à jour du statut financier dans Shopify.

## <a name="walkthrough-import-items-customers-companies-from-shopify"></a>Procédure pas à pas : importer des articles, des clients, des compagnies depuis Shopify

### <a name="scenario-3"></a>Scénario

Vous avez déjà une boutique en ligne performante et souhaitez commencer à l’utiliser [!INCLUDE[prod_short](../includes/prod_short.md)] comme logiciel de gestion d’entreprise. Vous souhaitez importer autant de données de Shopify que possible.

### <a name="steps-2"></a>Étapes

Ceci est la suite de [Procédure pas à pas : Commencez à vendre des produits en ligne](walkthrough-setting-up-and-using-shopify.md#walkthrough-start-selling-products-online) et [Procédure pas à pas : Ajoutez vos clients à votre nouvelle boutique en ligne](walkthrough-setting-up-and-using-shopify.md#walkthrough-add-your-customers-to-your-new-online-store). Vous pouvez également essayer avec vos propres données, par exemple en utilisant votre Shopify magasin ou votre sandbox.

Dans [!INCLUDE[prod_short](../includes/prod_short.md)], suivez les étapes indiquées ci-dessous.

#### <a name="prepare-data"></a>Préparer les données

1. Passez à un essai gratuit de 30 jours sans exemples de données. Pour plus d’informations, voir [Ajouter vos propres données à une société test vide](/dynamics365/business-central/dev-itpro/administration/trials-subscriptions#add-your-own-data-to-an-empty-trial-company).
2. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify**, puis sélectionnez le lien associé.
3. Sélectionnez **Nouveau**.
4. Dans le champ **Code**, saisissez **DEMO2**.
5. Dans le champ **URL Shopify**, saisissez l’URL de la boutique en ligne à laquelle vous souhaitez vous connecter.
6. Activez le bouton à bascule **Activé**, lisez et acceptez les conditions générales.

Configurez le magasin Shopify comme décrit ici :

1. Désactivez **Autoriser les synchronisations en arrière-plan**.
2. Dans le champ  **Élément de synchronisation**, Sélectionner **De Shopify**.
3. Activez le bouton bascule  **Créer automatiquement des éléments inconnus** .
4. Remplissez le champ **Code modèle article** avec le modèle approprié.
5. Dans le champ **Synchroniser les images des éléments**, Sélectionner **De Shopify**.
6. Dans le **SKU mappage** field, Sélectionner **Numéro d’article + code de variante**.
7. Dans le champ **Importation client depuis Shopify**, Sélectionner **Tous les clients**.
8. Activez le bouton de basculement **Créer automatiquement des clients inconnus**.
9. Remplissez le champ **Code modèle client/compagnie** avec le modèle approprié.
10. Dans le champ **Importer la société depuis Shopify**, Sélectionner **Tous les clients**.
11. Activez le bouton bascule  **Créer automatiquement une société inconnue** .

#### <a name="run-the-synchronization"></a>Exécuter la synchronisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify** et sélectionnez le lien associé.
2. Sélectionnez le magasin *DÉMO2* pour lequel vous voulez synchroniser les données pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez **Synchroniser les produits**.
4. Sélectionnez **Synchroniser les images produit**.
5. Sélectionnez **Synchroniser les clients**.
6. Sélectionner **Synchroniser les compagnies**

### <a name="results"></a>Résultats

* Les produits Shopify sont importés. Pour vérifier, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
* Des articles avec des images sont créés. Pour vérifier, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Article** et sélectionnez le lien associé.
* Shopify les clients sont importés. Pour vérifier, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Clients Shopify** et sélectionnez le lien associé.
* Shopify les entreprises sont importées. Pour vérifier, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Compagnies Shopify** et sélectionnez le lien associé.
* Les clients sont créés. Pour vérifier, sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Clients** et sélectionnez le lien associé.

## <a name="see-also"></a>Voir aussi .

[Mise en route avec le connecteur Shopify](get-started.md)  
