---
title: Synchroniser les articles et l'inventaire
description: Configurer et exécuter des synchronisations d’articles entre Shopify et Business Central
ms.date: 04/28/2024
ms.topic: article
ms.search.form: '30116, 30117, 30126, 30127,'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.collection:
  - bap-ai-copilot
---

# Synchroniser les articles et l'inventaire

Les **Articles** dans [!INCLUDE[prod_short](../includes/prod_short.md)] correspondent aux *produits* dans Shopify, ce qui comprend les marchandises physiques, les téléchargements numériques, les services et les cartes cadeaux que vous vendez. Il existe deux raisons principales pour synchroniser les articles :

1. La gestion des données s’effectue principalement dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Vous devez exporter tout ou partie des données de là vers Shopify et le rendre visible. Vous pouvez exporter le nom, la description, l’image, les prix, la disponibilité, les variantes, les détails du fournisseur et le code à barres de l’article. Une fois exportés, vous pouvez revoir les éléments ou les rendre visibles immédiatement.
2. Lorsqu’une commande de Shopify est importée, les informations sur les articles sont essentielles pour le traitement ultérieur du document dans [!INCLUDE[prod_short](../includes/prod_short.md)].

Les deux scénarios précédents sont toujours activés.

Un troisième scénario consiste à gérer les données dans Shopify, mais à importer ces articles en vrac dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Ce scénario peut être utile pour les événements de migration de données, si vous souhaitez connecter une boutique en ligne existante à un nouvel environnement [!INCLUDE[prod_short](../includes/prod_short.md)].

## Définir les synchronisations des articles

1. Sélectionnez l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") et saisissez **Magasin Shopify**. Ouvrez la boutique pour laquelle vous souhaitez configurer la synchronisation des articles.
2. Dans le champ **Synchroniser l’article**, sélectionnez l’option requise.

   Le tableau suivant décrit les options.

   |Option|Désignation|
   |------|-----------|
   |**Vide**| Les produits sont importés avec l’importation des commandes. Les produits sont exportés vers Shopify si un utilisateur exécute l’action **Ajouter un article** dans la page **Produits Shopify**. Cette option est le processus par défaut.|
   |**À Shopify**| Sélectionnez cette option si, après la synchronisation initiale déclenchée par l’action **Ajouter un article**, vous prévoyez de mettre à jour les produits manuellement en utilisant l’action **Synchroniser le produit** ou via la file d’attente des travaux pour les mises à jour récurrentes. N’oubliez pas d’activer le champ **Peut mettre à jour le produit Shopify**. S’il n’est pas activé, il est égal à l’option **Vide** (processus par défaut). Pour plus d’informations, voir la section [Exporter les articles dans Shopify](synchronize-items.md#export-items-to-shopify)|
   |**De Shopify**| Choisissez cette option si vous prévoyez d’importer des produits de Shopify en bloc, soit manuellement en utilisant l’action **Synchroniser le produit**, soit via la file d’attente des travaux pour les mises à jour récurrentes. Pour plus d’informations, voir la section [Importer les articles dans Shopify](synchronize-items.md#import-items-from-shopify).|

   > [!NOTE]
   > Changer **Synchroniser l’élément** de **Depuis Shopify** vers **À Shopify** n’aura d’effet que si vous activez **Peut mettre à jour les produits Shopify**.

## Importer des articles de Shopify

Tout d’abord, importiez les articles de Shopify en bloc ou en même temps que l’importation des commandes, ces articles sont d’abord ajoutés aux tableaux **Produit Shopify** et **Variante Shopify**. Mappez ensuite les produits et variantes importés aux articles et variantes dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Gérez le processus avec les paramètres suivants :

|Champ|Désignation|
|------|-----------|
|**Créer automatiquement des articles inconnus**|Lorsque les produits et variantes Shopify sont importés dans [!INCLUDE[prod_short](../includes/prod_short.md)], la fonction [!INCLUDE[prod_short](../includes/prod_short.md)] tente toujours de trouver d’abord l’enregistrement correspondant dans la liste d’articles. L’option **Mappage unité de stock** a un impact sur la correspondance et crée un article et/ou une variante article. Activez cette option pour créer un article ou lorsqu’un enregistrement correspondant n’existe pas. Le nouvel article est créé en utilisant les données importées et le **Code modèle article**. Si cette option n’est pas activée, vous devez créer un élément manuellement et utiliser l’action **Mapper le produit** dans la page **Produits Shopify**.|
|**Code modèle article**|Utilisez cette option avec le bouton à bascule **Créer automatiquement des articles inconnus**.<br>Choisissez le modèle à utiliser pour les articles créés automatiquement.|
|**Mappage unité de stock**|Choisissez comment vous voulez utiliser la valeur **Unité de stock** importée de Shopify lors du mappage et de la création de l’article/de la variante. En savoir plus dans la section [Effet des points de stock et codes barres de produit Shopify sur le mappage et la création d’articles et de variants dans Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).|
|**Séparateur de champ d'unité de stock**|Utilisez-le avec **Mappage unité de stock** défini sur **[N° article + Code variante](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central)**.<br>Définissez un séparateur qui doit servir à diviser l'unité de stock.<br>Par exemple, si, dans Shopify, vous créez la variante avec l'unité de stock 1000/001, tapez « / » dans le champ **Séparateur de champ d'unité de stock** pour obtenir le numéro d’article dans [!INCLUDE[prod_short](../includes/prod_short.md)] comme 1000 et le code variante article comme 001. Notez que si vous créez la variante avec l’unité de stock « 1000/001/111 » dans Shopify, le numéro d’article dans [!INCLUDE[prod_short](../includes/prod_short.md)] sera « 1000 » et le code de variante d’article « 001 ». La partie "111" est ignorée. |
|**Préfixe variante**|Utilisez avec le paramètre **Mappage unité de stock** défini sur **Code variante** ou **N° article + Code variante** comme stratégie de secours lorsque l'unité de stock provenant de Shopify est vide.<br>Pour créer la variante article dans [!INCLUDE[prod_short](../includes/prod_short.md)] automatiquement, saisissez une valeur dans **Code**. Par défaut, la valeur définie dans le champ Unité de stock importé de Shopify est utilisée. Cependant, si l’unité de stock est vide, elle génère un code commençant par le préfixe de la variante défini et « 001 ».|
|**Shopify peut mettre à jour l’article**|Choisissez cette option pour mettre à jour les articles et/ou les variantes automatiquement.|
|**Unité en tant que variante**| Choisissez cette option si vous souhaitez que toutes les unités de mesure des articles soient exportées sous forme de variantes distinctes. Personnalisez la page pour ajouter le champ. Pour en savoir plus, consultez la section [Unité de mesure en tant que variante](synchronize-items.md#unit-of-measure-as-variant) .|
|**Nom d’option de variante pour l’unité**| Utilisez ce champ avec **UdM comme variante** pour spécifier sous quelle option ajouter des variantes qui représentent des unités de mesure. La valeur par défaut est *Unité de mesure*. Pour ajouter les champs vous devez personnaliser la page.|

## Exporter les articles dans Shopify

Il existe plusieurs façons d’exporter des éléments vers Shopify :

* Utilisez l’action **Ajouter un article à Shopify** directement à partir de la page **Fiche d’article** .
* Utilisez l’action **Ajouter un article** sur la page **Shopify Produits** .
* Exécutez la synchronisation des éléments une ou plusieurs fois avec l’automatisation.

Quelle que soit la manière dont vous exportez les articles, les informations spécifiques sur les articles sont transférées vers la Shopify liste de produits en fonction de votre choix de paramètres de synchronisation des articles.

> [!IMPORTANT]
> Le produit est ajouté uniquement au canal de vente de la **boutique en ligne**. Vous devez publier des produits sur d’autres canaux de vente, tels que PDV Shopify, à partir de Shopify.

Les paramètres suivants permettent de gérer l’exportation des articles :

|Champ|Désignation|
|------|-----------|
|**Synchroniser texte étendu article**|Sélectionnez ce champ pour synchroniser le texte étendu de l’article. Comme il sera ajouté au champ **Description**, il peut contenir du code HTML. |
|**Synchroniser les attributs d’articles**|Sélectionnez ce champ pour synchroniser les attributs d’articles. Les attributs sont présentés sous forme de tableau et inclus dans le champ **Description** dans Shopify.|
|**Synchroniser texte marketing article**|Sélectionnez ce champ pour synchroniser le texte marketing de l’article. Bien que le texte marketing soit une sorte de description, il est différent du champ **Description** d’un article. Le champ **Description** est généralement utilisé comme nom d’affichage concis pour identifier rapidement le produit. Le texte marketing, quant à lui, est un texte plus riche et descriptif. Son objectif est d’ajouter du contenu marketing et promotionnel. Ce texte peut ensuite être publié avec l’article dans Shopify. Il existe deux manières de créer du texte marketing. Utilisez Copilot, qui suggère le texte généré par l’IA pour vous, ou commencez à partir de zéro.|
|**Code langue**|Sélectionnez ce champ si vous souhaitez que les versions traduites soient utilisées pour le titre, les attributs et le texte étendu.|
|**Mappage unité de stock**|Choisissez comment vous voulez remplir le champ Unité de stock dans Shopify. Les options possibles sont les suivantes :<br> - **N° article** pour utiliser le numéro d’article pour les produits et les variantes.<br> - **N° article + Code variante** pour créer une unité de stock en concaténant les valeurs de deux champs. Pour les articles sans variantes, seul le numéro d’article est utilisé.<br>- **Référence fournisseur** pour utiliser la référence fournisseur définie dans **Fiche Article** pour les produits et les variantes.<br> - **Code à barres** pour utiliser le type de code à barres de **Référence article**. Cette option respecte les variantes.<br>Si **Peut mettre à jour les produits Shopify** est activé, les modifications dans le champ **Mappage unité de stock** sont propagées à Shopify après la prochaine synchronisation pour tous les produits et variantes répertoriés dans la page **Produits Shopify** pour le magasin sélectionné.|
|**Séparateur de champ d’unité de stock**|Définissez un séparateur pour l’option **N° article + Code variante**.|
|**Suivi inventaire**| Choisissez comment le système renseigne le champ **Suivi inventaire** pour les produits exportés dans Shopify. Vous pouvez mettre à jour les informations de disponibilité à partir de [!INCLUDE[prod_short](../includes/prod_short.md)] pour les produits dans Shopify pour lesquels le suivi inventaire est activé. Consultez la section [Inventaire](synchronize-items.md#sync-inventory-to-shopify).|
|**Stratégie d’inventaire par défaut**|Choisissez *Refuser* pour éviter tout stock négatif du côté de Shopify. <br>Si **Peut mettre à jour les produits Shopify** est activé, les modifications dans le champ **Stratégie d’inventaire par défaut** sont propagées à Shopify après la prochaine synchronisation pour tous les produits et variantes répertoriés dans la page **Produits Shopify** pour le magasin sélectionné.|
|**Possibilité de mettre à jour les produits Shopify**|Définissez ce champ si [!INCLUDE[prod_short](../includes/prod_short.md)] peut uniquement créer des articles ou peut également les mettre à jour. Sélectionnez cette option si, après la synchronisation initiale déclenchée par l’action **Ajouter un article**, vous prévoyez de mettre à jour les produits manuellement en utilisant l’action **Synchroniser le produit** ou via la file d’attente des travaux pour les mises à jour récurrentes. N’oubliez pas de sélectionner **À Shopify** dans le champ **Synchronisation article**.<br>**Peut mettre à jour les produits Shopify** n’a pas d’impact sur la synchronisation des prix, des images ou des niveaux d’inventaire, qui sont configurés par des contrôles indépendants.<br>Si la case **Peut mettre à jour les produits Shopify** est activée, les champs suivants du côté Shopify seront mis à jour au niveau du produit et, si nécessaire, au niveau de la variante : **Unité de stock**, **Code-barres**, **Poids**. Les champs **Titre**, **Type de produit**, **Fournisseur** et **Description** du produit seront également mis à jour si les valeurs exportées ne sont pas vides. Pour la description, cela signifie que vous devez activer l’un des boutons à bascule **Synchroniser texte étendu article**, **Synchroniser texte marketing article** et **Synchroniser les attributs d’articles** et les attributs, le texte étendu ou marketing doivent avoir des valeurs. Si le produit utilise des variantes, la variante est ajoutée ou supprimée si nécessaire. <br>Si le produit sur Shopify est configuré pour utiliser une matrice de variantes combinant deux options ou plus, le connecteur Shopify ne peut pas créer de variante pour ce produit. Dans [!INCLUDE[prod_short](../includes/prod_short.md)] il n’y a aucun moyen de définir une matrice d’options ; c’est pourquoi le connecteur utilise le **code variante** comme seule option. Cependant, Shopify attend plusieurs options et refuse de créer une variante si les informations sur la deuxième option et les autres options sont manquantes. |
|**Unité en tant que variante**| Choisissez cette option si vous souhaitez que certaines options soient exportées comme importées sous forme d’unités de mesure plutôt que de variantes. Personnalisez la page pour ajouter le champ. Pour en savoir plus, consultez la section [Unité de mesure en tant que variante](synchronize-items.md#unit-of-measure-as-variant) .|
|**Nom d’option de variante pour l’unité**| Utilisez ce champ avec **UdM comme variante** pour spécifier quelle option contient des variantes qui représentent des unités de mesure. La valeur par défaut est *Unité de mesure*. Personnalisez la page pour ajouter le champ.|

> [!NOTE]
> Lorsque vous souhaitez exporter de nombreux éléments et variantes, certains peuvent être bloqués. Vous ne pouvez pas inclure les articles et variantes bloqués dans les calculs de prix. Ils ne sont donc pas exportés. Le connecteur ignore ces éléments et variantes, vous n’avez donc pas besoin de les filtrer sur la page **Ajouter un élément à Shopify** de la demande.

## Détails avancés

### Effet des points de stock et codes à barres dans le produit Shopify sur le mappage et la création d’articles et de variantes dans Business Central

Lorsque les produits sont importés de Shopify vers les tableaux **Produits Shopify** et **Variantes Shopify**, [!INCLUDE[prod_short](../includes/prod_short.md)] tente de trouver les enregistrements existants.

Le tableau suivant présente les différentes options du champ **Mappage unité de stock**.

|Option|Effet sur le mappage|Effet sur la création|
|------|-----------------|------------------|
|**Vide**|Le champ Unité de stock n’est pas utilisé dans la routine de mappage des articles.|Aucun effet sur la création de l’article.<br>Cette option empêche la création de variantes. Lorsque, dans un document de vente, seul l’article principal est utilisé. Une variante peut toujours être mappée manuellement à partir de la page **Produit Shopify**.|
|**N° article**|Choisissez si le champ Unité de stock contient le numéro d’article.|Aucun effet sur la création de l’article sans les variantes. Pour un article avec des variantes, chaque variante est créée comme un article séparé.<br>Si Shopify a un produit avec deux variantes et que leurs points de stock sont 1000 et 2000, le système [!INCLUDE[prod_short](../includes/prod_short.md)] crée deux articles avec les numéros 1000 et 2000.|
|**Code de variante**|Le champ Unité de stock n’est pas utilisé dans la routine de mappage des articles.|Aucun effet sur la création de l’article. Si une variante article est créée, la valeur du champ Unité de stock est utilisée comme code. Si l'unité de stock est vide, un code est généré en utilisant le champ **Préfixe variante**.|
|**N° article + Code variante**|Sélectionnez cette option si le champ Unité de stock contient un numéro d’article et le code variante article séparés par la valeur définie dans le champ **Séparateur de champ d'unité de stock**.|Lorsqu’un article est créé, la première partie de la valeur du champ Unité de stock est utilisée comme **N°**. Si le champ Unité de stock est vide, un numéro d’article est généré en utilisant la série de numéros définie dans le champ **Code modèle article** ou **N° article** de la page **Configuration de l’inventaire**.<br>Lorsqu’un article est créé, la fonction variante utilise la seconde partie de la valeur du champ Unité de stock comme **Code**. Si le champ Unité de stock est vide, un code est généré en utilisant le champ **Préfixe variante**.|
|**Référence fournisseur**|Choisissez si le champ Unité de stock contient le numéro d’article du fournisseur. Dans ce cas, le **Numéro du fournisseur de l’article** n’est pas utilisé sur la page **Fiche article** ; le **Numéro d’article du fournisseur** du **Catalogue des fournisseurs d’articles** est plutôt utilisé. Si l’enregistrement *Catalogue fournisseur articles* trouvé contient un code variante, ce dernier est utilisé pour mapper la variante Shopify.|Si un fournisseur correspondant existe dans [!INCLUDE[prod_short](../includes/prod_short.md)], la valeur d'unité de stock sert de **Référence fournisseur** sur la page **Fiche Article** et comme **Référence article** de type *Fournisseur*. <br>Empêche la création de variantes. Utile pour utiliser l’article principal uniquement dans le document de vente. Vous pouvez toujours mapper une variante manuellement à partir de la page **Produit Shopify**.|
|**Code à barres**|Choisissez si le champ Unité de stock contient un code à barres. Une recherche est effectuée sur les **Références articles** de type *code-barres*. Si l’enregistrement Référence article trouvé contient un code variante, ce dernier est utilisé pour mapper la variante Shopify.|Aucun effet sur la création de l’article. <br>Empêche la création de variantes. Utile pour utiliser l’article principal uniquement dans le document de vente. Vous pouvez toujours mapper une variante manuellement à partir de la page **Produit Shopify**.|

Le tableau suivant donne les effets du champ **Code à barres**.

|Effet sur le mappage|Effet sur la création|
|-----------------|------------------|
|Une recherche est effectuée parmi les **Références articles** de type Code à barres sur la valeur définie dans le champ **Code à barres** dans Shopify. Si l’enregistrement Référence article trouvé contient un code variante, ce dernier est utilisé pour mapper la variante Shopify.|Le code à barres est enregistré comme **Référence article** pour l’article et la variante article.|

> [!NOTE]  
> Vous pouvez déclencher le mappage pour le produit/les variantes sélectionnés ou tous les produits non mappés importés en choisissant **Essayer de rechercher le mappage du produit** (pour le produit/les variantes sélectionnés) ou **Essayer de rechercher des mappages**.

### Aperçu du mappage des champs

|Shopify|Source lors de l’exportation à partir de [!INCLUDE[prod_short](../includes/prod_short.md)]|Cible lors de l’importation dans [!INCLUDE[prod_short](../includes/prod_short.md)]|
|------|-----------------|-----------------|
|état|En fonction du champ **État des produits créés** dans la page **Fiche magasin Shopify**. Pour plus d’informations, voir [Mises à jour ponctuelles des produits Shopify](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Aucun affichage.|
|Titre | **Description**. Si le code langue est défini et qu’il existe une traduction article correspondante, cette dernière remplace la description.|**Description**|
|Titre de la variante | **Code variante**.|**Description** de la variante|
|Désignation|Combine les textes étendus, le texte marketing et les attributs si vous activez les bascules correspondantes dans la fiche magasin Shopify. Respecte le code langue.|Aucun affichage.|
|Titre de la page du SEO|Valeur fixe : vide. Pour plus d’informations, voir [Mises à jour ponctuelles des produits Shopify](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Aucun affichage.|
|Description méta du SEO|Valeur fixe : vide. Pour plus d’informations, voir [Mises à jour ponctuelles des produits Shopify](synchronize-items.md#ad-hoc-updates-of-shopify-products).|Aucun affichage.|
|Support|**Image**. En savoir plus dans la section [Synchroniser les images des articles](synchronize-items.md#sync-item-images)|**Image**|
|Prix|Le calcul du prix du client final comprend le prix unitaire de l’article, le groupe de prix client, le groupe d’escomptes client et le code devise. En savoir plus dans la section [Synchroniser les prix](synchronize-items.md#sync-prices-with-shopify)|**Prix unitaire**. Le prix est uniquement importé dans les articles récemment créés, mais il ne sera pas mis à jour lors des synchronisations ultérieures.|
|Comparer au prix|Le calcul du prix sans escompte. Si la valeur est inférieure ou égale à **Prix**, le connecteur envoie 0 (null) au lieu de la valeur réelle.|Aucun affichage.|
|Coût par article|**Coût unitaire**|**Coût unitaire**. Le coût unitaire est uniquement importé dans les articles récemment créés et il ne sera pas mis à jour lors des synchronisations ultérieures.|
|Unité de stock|Pour plus de renseignements, consultez **Mappage unité de stock** dans la section [Exporter des articles vers Shopify](synchronize-items.md#export-items-to-shopify).|En savoir plus dans la section [Effet des points de stock et codes barres de produit Shopify sur le mappage et la création d’articles et de variants dans Business Central](synchronize-items.md#effect-of-shopify-product-skus-and-barcodes-on-mapping-and-creating-items-and-variants-in-business-central).|
|Code-barres|**Références articles** de type Code à barres.|**Références articles** de type Code à barres.|
|L’inventaire est stocké dans| Dépend des magasins Shopify. Si **Services d’exécution Business Central** a le champ **Emplacement de produit par défaut** activé, l’inventaire est stocké et expédié à partir de **Services d’exécution Business Central**. Sinon, le Shopify un emplacement principal ou plusieurs emplacements sont utilisés. Apprenez-en davantage dans les [Deux approches pour gérer les exécutions](synchronize-items.md#two-approaches-to-manage-fulfillments) section.| Aucun affichage.|
|Suivi quantité|En fonction du champ **Suivi inventaire** sur la page **Fiche magasin Shopify**. Consultez la section [Inventaire](synchronize-items.md#sync-inventory-to-shopify). Utilisé uniquement lorsque vous exportez un produit pour la première fois.|Aucun affichage.|
|Poursuivre la vente même en cas de rupture de stock|En fonction de la **Stratégie d'inventaire par défaut** dans la **Fiche magasin Shopify**.|Aucun affichage.|
|Type|**Description** de **Code catégorie article**. Si le type n’est pas spécifié dans Shopify, il est ajouté en tant que type personnalisé.|**Code catégorie article**. Mappage par description.|
|Fournisseur|**Nom** du fournisseur provenant de **N° fournisseur**|Mappage par nom de **N° fournisseur**.|
|Poids|**Poids brut**.|Aucun affichage.|
|Imposable|Valeur fixe : activée.|Aucun affichage.|
|Codes taxe|**Code groupe fiscal**. Uniquement pertinent pour les taxes de vente. En savoir plus sur [Configurer les taxes](setup-taxes.md).|Aucun affichage.|

### Balises

Examinez les balises importées dans le récapitulatif **Balises** de la page **Produit Shopify**. Sur la même page, pour modifier les balises, choisissez l’action **Balises**.

Si l’option **À Shopify** est sélectionnée dans le champ **Synchroniser l’article**, les balises attribuées sont exportées vers Shopify à la prochaine synchronisation.

### Unité de mesure comme variante

Shopify ne prend pas en charge plusieurs unités de mesure. Si vous souhaitez vendre le même produit, par exemple à la pièce et à l’ensemble, et utiliser des prix ou des escomptes différents, vous devez créer une unité de mesure en tant que variante de produit.
Le connecteur Shopify peut être configuré pour exporter des unités de mesure en tant que variantes ou importer des variantes en tant qu’unités de mesure.

Pour activer cette fonctionnalité, utilisez les champs **UoM comme variante** et **Nom de l’option de variante** dans les **Shopify Carte d’achat**. Les champs sont masqués par défaut, utilisez la personnalisation pour les ajouter à la page.

**Remarques concernant l’unité de mesure comme variante**

* Lorsque le produit est importé dans [!INCLUDE[prod_short](../includes/prod_short.md)], le connecteur crée des unités de mesure. Vous devrez mettre à jour **Qté. par unité de mesure**.
* Lorsque vous traitez une matrice de variantes, par exemple Couleur et UdM et que vous souhaitez importer des produits, vous devez définir le *Numéro d’article + Code de variante* dans le champ **Mappage SKU** et assurez-vous que le champ **SKU** dans Shopify a la même valeur pour toutes les unités de mesure et inclut le numéro d’article et le code de variante.
* Dans [!INCLUDE[prod_short](../includes/prod_short.md)] la disponibilité est calculée par article/variante d’article et non par unité de mesure. Cela signifie que la même disponibilité sera attribuée à chaque variante représentant l’unité de mesure (par rapport à **Qté par unité de mesure**), ce qui peut conduire à des cas où la quantité disponible dans Shopify n’est pas exacte. Exemple : article vendu en PCS et en boîte de 6. L’inventaire dans [!INCLUDE[prod_short](../includes/prod_short.md)] est de 6 PCS. Article exporté vers Shopify en tant que produit avec deux variantes. Une fois la synchronisation des inventaires exécutée, le niveau d’inventaire dans Shopify sera de 6 pour la variante PCS et de 1 pour la variante BOX. L’acheteur peut explorer uniquement le magasin et voir que le produit est disponible dans les deux options et passer une commande pour 1 BOÎTE. Le prochain acheteur verra que BOX n’est pas disponible, mais il reste encore 6 PCS. Ce problème sera corrigé lors de la prochaine synchronisation de l’inventaire.

### URL et URL d’aperçu

Un article ajouté à Shopify ou importé de Shopify peut avoir **URL** ou **URL d’aperçu** remplis. Le champ **URL** sera vide si le produit n’est pas publié sur la boutique en ligne, par exemple, parce que son état est brouillon. L’**URL** sera vide si le magasin est protégé par mot de passe, par exemple, parce qu’il s’agit d’un magasin de développement. Dans la plupart des cas, vous pouvez utiliser l’**URL d’aperçu** pour vérifier à quoi ressemblera le produit une fois publié.

## Exécuter la synchronisation des articles

La synchronisation complète ou partielle des articles peut être effectuée de différentes manières.

### Synchronisation initiale des articles de Business Central vers Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Choisissez l’action **Ajouter des articles**.
3. Dans le champ **Code magasin**, saisissez le code. Si vous ouvrez la fenêtre **Produit Shopify** dans la page **Fiche magasin**, le code magasin est rempli automatiquement.
4. Si vous avez configuré la synchronisation des images et de l’inventaire, vous pouvez les inclure dans le même processus. Les inclure dans le même processus est pratique pour les scénarios de démonstration ou lorsqu’il s’agit de traiter de plus petite quantités de données.
5. Définissez des filtres sur les articles selon vos besoins. Par exemple, vous pouvez filtrer par numéro d’article ou code catégorie article.
6. Cliquez sur **OK**.

Les articles résultants sont automatiquement créés dans Shopify avec les prix. Selon les choix que vous avez faits, des images et des niveaux d’inventaire peuvent être inclus. L’opération peut prendre un certain temps si un grand nombre d’articles est ajouté.

Alternativement, vous pouvez synchroniser un élément en choisissant l’option **Ajouter à Shopify** action dans le **Carte d’article** page.  

> [!NOTE]  
> Synchronisation initiale des éléments de [!INCLUDE[prod_short](../includes/prod_short.md)] à Shopify ne considère pas **Élément de synchronisation** et **Peut mettre à jour Shopify Des produits** paramètres. 

### Synchroniser les produits de Shopify vers Business Central

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasin Shopify**, puis choisissez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser les articles pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Synchroniser les produits**.

Sinon, utilisez l’action **Synchroniser les produits** sur la page **Produits Shopify** ou recherchez le traitement en lot **Synchroniser les produits**.

Vous pouvez programmer la tâche pour qu’elle soit exécutée de manière automatisée. En savoir plus dans la section [Programmer des tâches récurrentes](background.md#to-schedule-recurring-tasks).

### Mises à jour ponctuelles des produits Shopify

Si les enregistrements sont mis à jour dans le tableau **Produit Shopify**, les modifications suivantes sont synchronisées avec Shopify.

Mise à jour :

* **État** (vous avez le choix entre actif, archivé ou brouillon).
* **Titre du SEO**
* **Description du SEO**

Suppression :

En fonction de la valeur indiquée dans **Action pour produits supprimés** dans la page **Fiche magasin Shopify**, le produit est mis à jour dans Shopify lorsque l’enregistrement est supprimé de la page **Produits Shopify**.

* **Vide** : rien ne se passe. Si nécessaire, l’utilisateur doit effectuer l’action requise à partir de l’**administration Shopify**.
* **État sur Brouillon** : l’état du produit dans Shopify est défini sur *Brouillon*.
* **État sur Archivé** : le produit est archivé dans Shopify.

## Synchroniser les images d’articles

La synchronisation des images peut être configurée pour les articles synchronisés. Choisissez parmi les options suivantes :

* **Désactivé** : la synchronisation des images est désactivée.
* **À Shopify** : les images des articles sont exportées dans Shopify.
* **De Shopify** : les images de Shopify sont importés dans [!INCLUDE[prod_short](../includes/prod_short.md)].

La synchronisation des images peut être initialisée de deux manières décrites ci-dessous.

### Synchroniser les images des produits à partir de la page du magasin Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser les images pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Synchroniser les images des produits**.

### Synchroniser les images des produits à partir de la page des produits Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Sélectionnez l’action **Synchroniser les images des produits**.

### Remarques sur la synchronisation des images

* Lorsque vous exportez des images de [!INCLUDE[prod_short](../includes/prod_short.md)] vers Shopify, les images remplacent celles que vous avez exportées précédemment. Les images précédentes ne sont plus disponibles.
* Si vous supprimez une image dans [!INCLUDE[prod_short](../includes/prod_short.md)], l’image dans Shopify n’est pas supprimée. Vous devrez supprimer manuellement les anciennes images dans **Administrateur Shopify**.
* Les images que vous exportez dans Shopify doivent être conformes aux exigences de Shopify. Sinon, vous ne pouvez pas les importer. Pour en savoir plus sur les exigences multimédias, accédez à [Types de support du produit sur help.shopify.com](https://help.shopify.com/en/manual/products/product-media/product-media-types#images).

## Synchroniser les prix avec Shopify

Les paramètres suivants permettent d’exporter les prix avec ces paramètres :

|Champ|Désignation|
|------|-----------|
|**Groupe prix client**|Indique le prix d’un article dans Shopify. Le prix de vente de ce groupe prix client est pris en compte. Si aucun groupe n’est spécifié, le prix de la fiche Article est utilisé.|
|**Groupe escomptes client**|Indique l’escompte à utiliser pour calculer le prix d’un article dans Shopify. Les prix remisés sont stockés dans le champ **Prix** et le prix total est stocké dans le champ **Comparer au prix**.|
|**Autoriser escompte ligne**|Indique si l’escompte par ligne est autorisé lors du calcul des prix pour Shopify. Ce paramètre s’applique uniquement aux prix de l’article. Les prix pour le groupe de prix client ont leur propre bouton à bascule sur les lignes.|
|**Prix TTC**|Indique si les calculs de prix pour Shopify comprennent la TVA. En savoir plus sur [Configurer les taxes](setup-taxes.md).|
|**Groupe de report marché TVA**|Indique le groupe de report marché TVA utilisé pour calculer les prix dans Shopify. Cela devrait être le groupe que vous utilisez pour les clients nationaux. En savoir plus sur [Configurer les taxes](setup-taxes.md).|
|**Code devise**|Saisissez un code devise uniquement si la boutique en ligne utilise une devise différente de la devise locale ($). La devise spécifiée doit avoir des taux de change configurés. Si votre boutique en ligne utilise la même devise que [!INCLUDE[prod_short](../includes/prod_short.md)], laissez le champ vide.|

Vous pouvez exporter les prix pour les articles synchronisés de la manière décrite ci-dessous.

### Synchroniser les prix à partir de la page des produits Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Sélectionnez l’action **Synchroniser les prix avec Shopify**.

### Remarques sur le calcul des prix

* Lors de la détermination d’un prix, [!INCLUDE[prod_short](../includes/prod_short.md)] utilise le prix le plus bas. Cependant, la logique du prix le plus bas ignore le prix unitaire défini sur la fiche article si un prix est défini dans le groupe de prix. Cela est vrai même si le prix unitaire du prix de la fiche article est inférieur.
* Pour calculer les prix, le connecteur crée un devis temporaire pour l’article avec une quantité de 1 et utilise une logique de calcul de prix standard. Seuls les prix et escomptes applicables pour la quantité 1 sont utilisés. Vous ne pouvez pas exporter différents prix ou escomptes en fonction de la quantité.
* Le connecteur envoie une demande de mise à jour des prix dans Shopify si le prix est en [!INCLUDE[prod_short](../includes/prod_short.md)] a changé. Par exemple, si vous avez synchronisé des produits et des prix, puis modifié le prix dans Shopify, en choisissant le **Synchroniser les prix avec Shopify** l’action n’aura aucun impact sur le prix dans le Shopify car le nouveau prix calculé par le connecteur est le même que le prix stocké dans le Shopify Variante de la synchronisation précédente. Le **Comparer au prix** mis à jour uniquement si le prix principal a changé.

## Synchroniser l'inventaire sur Shopify

La synchronisation de l'inventaire peut être configurée pour les articles déjà synchronisés. Deux conditions doivent être remplies :

1. Le suivi de l'inventaire doit être activé pour un produit dans Shopify. Si les articles sont exportés dans Shopify, pensez à activer **Suivi inventaire** sur la page **Magasin Shopify**. Pour plus d’informations, voir la section [Exporter les articles dans Shopify](synchronize-items.md#export-items-to-shopify)
2. La synchronisation de l'inventaire doit être activée pour **Emplacements Shopify**.

### Pour activer la synchronisation de l'inventaire

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasin Shopify**, puis choisissez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser l'inventaire pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Emplacements** pour ouvrir **Emplacements des magasins Shopify**.
4. Sélectionnez l’action **Obtenir les emplacements Shopify** pour importer tous les emplacements définis dans Shopify. Ils se trouvent dans les paramètres [**Emplacements**](https://www.shopify.com/admin/settings/locations) sous **Administration Shopify**.
5. Dans le champ **Filtre emplacement**, ajoutez des emplacements si vous voulez inclure l'inventaire en provenance de certains emplacements uniquement. Par exemple, saisissez *EST|OUEST* pour que seul l'inventaire de ces deux emplacements soit disponible à la vente sur la boutique en ligne.
6. Sélectionnez la méthode de calcul des stocks à utiliser pour les emplacements Shopify sélectionnés.
7. Activez **Emplacement de produit par défaut** si vous souhaitez que l’emplacement soit utilisé pour la création d’enregistrements d’inventaire et participe à la synchronisation de l’inventaire.

La synchronisation de l'inventaire peut être initialisée des deux manières décrites ci-dessous.

### Synchroniser l'inventaire à partir de la page du magasin Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Magasins Shopify** et choisissez le lien associé.
2. Sélectionnez le magasin pour lequel vous voulez synchroniser l'inventaire pour ouvrir la page **Fiche magasin Shopify**.
3. Sélectionnez l’action **Synchroniser l'inventaire**.

### Synchroniser l'inventaire à partir de la page des produits Shopify

1. Accédez à l’icône de recherche ![Ampoule qui ouvre la fonction de recherche.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Produits Shopify** et choisissez le lien associé.
2. Sélectionnez l’action **Synchroniser l'inventaire**.

### Remarques sur l'inventaire

* Il existe deux méthodes standard de calcul des inventaires : **Solde disponible projeté à la date** et **Inventaire libre (non réservé)**. Avec l’extensibilité, vous pouvez ajouter plus d’options. Pour en savoir plus sur l’extensibilité, rendez-vous sur [ exemples](/dynamics365/business-central/dev-itpro/developer/devenv-extending-shopify#stock-calculation). 
* Vous pouvez consulter les informations d'inventaire en provenance de Shopify sur la page **Récapitulatif de l'inventaire Shopify**. Dans ce récapitulatif, un aperçu de l'inventaire Shopify et du dernier inventaire calculé s’affiche dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Il existe un enregistrement par emplacement.
* Si les informations de stock dans Shopify sont différentes de l’élément **Stock prévisionnel** dans [!INCLUDE[prod_short](../includes/prod_short.md)], le stock est mis à jour dans Shopify.
* Lorsque vous ajoutez un nouvel emplacement dans Shopify, vous devez également ajouter des enregistrements d’inventaire pour celui-ci. Shopify ne le fait pas automatiquement pour les produits et variantes existants et le connecteur ne synchronise pas les niveaux d’inventaire pour ces articles dans le nouvel emplacement. Pour en savoir plus, voir [Affecter un inventaire à des emplacements](https://help.shopify.com/manual/locations/assigning-inventory-to-locations).
* À la fois les **Services d’exécution Business Central** et les emplacements normaux sont pris en charge et peuvent être utilisés pour l’expédition et l’inventaire.

#### Exemple de calcul du solde disponible prévisionnel

Il y a 10 pièces de l’article A disponibles en stock et deux documents de vente en attente. Une pour lundi avec la quantité de *Un* et une pour jeudi avec une quantité de *Deux*. Selon le moment où vous synchronisez l’inventaire, le système mettra à jour le niveau de stock dans Shopify avec différentes quantités :

|Quand la synchronisation de l'inventaire est exécutée|Valeur utilisée pour mettre à jour le niveau de stock|Commentaire|
|------|-----------------|-----------------|
|Mardi|9|Inventaire 10 moins document de vente défini sur une livraison lundi|
|Vendredi|7|Inventaire 10 moins les deux documents de vente|

### Deux approches pour gérer les exécutions

Il existe deux manières de gérer l’exécution dans Shopify :

* Suivi de l’inventaire et exécution « intégrée » Shopify
* Exécution et suivi de l’inventaire tiers

L’inventaire de chaque produit Shopify peut être stocké soit par Shopify , soit par 3PL.

Si vous utilisez le Shopify exécution, vous pouvez également définir plusieurs emplacements dans Shopify. Une fois la commande créée, Shopify sélectionne l’emplacement en fonction de la disponibilité et de la priorité. Vous pouvez également spécifier les emplacements sur lesquels vous prévoyez de suivre un produit spécifique, par exemple ne jamais vendre à partir de l’emplacement *ShowRoom*.

Si vous utilisez 3PL, la manutention physique est prise en charge par le fournisseur 3PL, les emplacements ne sont donc pas nécessaires. Pour 3PL, le champ SKU devient obligatoire.

Lorsque vous décidez de l’emplacement auquel suivre l’article, Shopify crée des enregistrements dans le tableau **Niveaux d’inventaire** , qui peut être mis à jour manuellement en fonction de la disponibilité des inventaires.

Le connecteur prend en charge les deux modes. Il peut envoyer un inventaire à plusieurs emplacements Shopify ou fonctionner comme un service d’exécution.

Du point de vue [!INCLUDE[prod_short](../includes/prod_short.md)] lorsque vous créez un élément et que vous souhaitez l’envoyer à Shopify vous souhaitez également :

* Utilisez le bouton **Emplacement du produit par défaut** pour spécifier si cet article sera traité par Shopify exécution ou par 3PL. Il existe toujours un **service de traitement des commandes Business Central**, mais il peut y avoir davantage de services de traitement des commandes si davantage d’applications sont installées. Vous pouvez activer l’ **emplacement par défaut du produit** uniquement dans un seul enregistrement si vous souhaitez utiliser le service de traitement des commandes. 
* Utilisez le bouton **Emplacement du produit par défaut** pour spécifier les emplacements que vous souhaitez utiliser pour suivre l’inventaire. Vous pouvez activer l’ **emplacement par défaut du produit** pour plusieurs emplacements où **le service de traitement des commandes** est désactivé. Notez que l’inventaire sera toujours suivi pour l’emplacement principal.

#### Quelle est la différence ?

Shopify l’exécution est utile lors de l’utilisation Shopify PDV et il existe plusieurs magasins physiques. Vous voulez que les employés du magasin physique connaissent leur inventaire actuel. Dans ce cas, vous créez plusieurs emplacements dans Shopify, plusieurs emplacements dans [!INCLUDE[prod_short](../includes/prod_short.md)], et Activer **Emplacement du produit par défaut** pour tous ces endroits.  

Si la logistique est gérée dans [!INCLUDE[prod_short](../includes/prod_short.md)], où il peut y avoir autant d’emplacements que nécessaire représentant les centres de distribution, vous ne créez pas d’emplacements dans Shopify. Le connecteur crée automatiquement des services d’exécution Business Central et vous pouvez lier l’inventaire via des filtres d’emplacement de plusieurs emplacements vers un enregistrement de services d’exécution. Par conséquent, dans Shopify il n’y a aucune information sur l’endroit d’où les marchandises sont envoyées : il contient uniquement des informations de suivi, tandis que dans [!INCLUDE[prod_short](../includes/prod_short.md)], vous pouvez sélectionner en fonction de la disponibilité et de la proximité de la destination.

#### Exemple d’utilisation de la bascule Emplacement du produit par défaut

Après avoir choisi le **Obtenir Shopify Emplacements** action dans le **Shopify Emplacements** sur la page, vous voyez les emplacements suivants :

|Nom|Service d’exécution|Est principal|
|------|-----------------|-----------------|
|Principal| |**Oui**|
|Second| | |
|Service exécution Business Central|**Oui**| |

Examinons l’impact de l’activation de la bascule Emplacement du produit par défaut :

|Nom des emplacements pour lesquels le bouton Emplacement du produit par défaut est activé|Impact sur la façon dont le produit est créé dans Shopify|
|------|-----------------|
|Principal| L’inventaire sera stocké à : Plusieurs emplacements ; emplacements sélectionnés : principal (principal) |
|Principal et Deuxième| L’inventaire sera stocké à : Plusieurs emplacements ; emplacements sélectionnés : principal et second |
|Service exécution Business Central|L’inventaire sera stocké à : Business Central Fulfillment Service ; emplacements sélectionnés : (Application) Business Central Fulfillment Service|
|Service exécution Business Central et principal| Erreur : vous ne pouvez pas utiliser des emplacements Shopify standard avec des emplacements de service d’exécution|

## Voir aussi .

[Mise en route du connecteur pour Shopify](get-started.md)  
