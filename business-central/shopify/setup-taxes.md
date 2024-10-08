---
title: Configurer les taxes pour la connexion Shopify
description: Comment configurer les taxes dans Shopify et dans Business Central.
ms.date: 05/29/2024
ms.topic: article
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.custom: bap-template
---

# <a name="set-up-taxes-for-the-shopify-connection"></a>Configuration des taxes pour la connexion Shopify

Dans cet article, nous allons étudier de quelle manière divers paramètres de Shopify ont un impact sur les taxes et les prix en magasin qui sont affichés aux clients. Nous allons également couvrir comment configurer [!INCLUDE[prod_short](../includes/prod_short.md)] pour prendre en charge les paramètres dans Shopify. Cet article n’est pas conçu comme un guide complet sur les taxes. Pour en savoir plus, contactez votre administration fiscale locale ou un expert en fiscalité.  

L’article suppose que vous êtes assujettis à des taxes lorsque vous vendez des biens au niveau local ou international.

## <a name="if-you-sell-domestically"></a>Si vous vendez sur le marché intérieur

Une fois que vous avez configuré votre Shopify pour recouvrer les taxes dans votre pays ou région, vous pouvez décider de la manière dont vous souhaitez afficher les prix en magasin.

Vous spécifiez si vous souhaitez inclure la taxe dans les prix en activant ou en désactivant le bouton **Tous les prix sont taxe comprise** dans les paramètres [**Taxes et droits de douane**](https://www.shopify.com/admin/settings/taxes) dans votre **Administrateur Shopify**.

Le bouton à bascule est généralement activé pour les pays/régions suivants :

* Australie
* Autriche
* Belgique
* République tchèque
* Danemark
* Finlande
* France
* Allemagne
* Islande
* Italie
* Pays-Bas
* Nouvelle-Zélande
* Norvège
* Espagne
* Suède
* Suisse
* Royaume-Uni

Dans de tels marchés, un prix de 100 EUR défini sur la fiche produit contient déjà la taxe sur la valeur ajoutée (TVA). Le prix, TTC, est affiché au client en vitrine et au moment du passage en caisse.  

Aux États-Unis et au Canada, les clients ne s’attendent pas à voir les prix avec les taxes, car la taxe finale dépend du lieu d’expédition des produits. La taxe est ajoutée au moment du paiement, donc l’option **Tous les prix incluent les taxes** est généralement désactivée. Dans ce cas, un prix de $100 défini sur le produit carte est le prix hors taxes. Au moment du paiement, les taxes sont ajoutées au prix.

Pour prendre en charge le scénario dans lequel **Tous les prix sont taxes comprises** est sélectionné, dans [!INCLUDE[prod_short](../includes/prod_short.md)], remplissez les champs suivants sur la page **Fiche magasin Shopify** :  

1. Activez le bouton à bascule **Prix TTC**.  
2. Dans le champ **Groupe de report marché TVA**, spécifiez le groupe de report que vous utilisez pour les clients nationaux.  

Définissez maintenant les prix article dans le champ **Fiche article** ou dans le champ **Liste tarifs**, avec ou sans taxe. Lors de l’exportation des prix vers Shopify, [!INCLUDE [prod_short](../includes/prod_short.md)] inclut les taxes nationales dans le prix calculé, puis affiche ce prix dans la fiche produit dans Shopify.

> [!NOTE]
> Ces paramètres affectent l’exportation des prix. Lorsque vous importez des commandes depuis Shopify, le paramètre du champ **Prix TTC** provient du **Modèle client** sur la fiche magasin Shopify, ou le modèle de client par pays/région. Même si vous utilisez le client par défaut pour les commandes importées, vous devez remplir le **Code de modèle client**.

## <a name="if-you-sell-internationally"></a>Si vous vendez à l'international

Cette section explore les paramètres des scénarios dans lesquels vous devez recouvrer des taxes lors de la vente dans un autre pays/région, par exemple d’autres pays/régions de l’UE.

Actuellement, le connecteur Shopify ne vous permet que d’exporter un seul prix. Shopify applique automatiquement les taxes locales, les devises et les arrondissements. Le bouton bascule **Tous les prix sont taxes comprises** entraîne les actions décrites dans les sous-sections suivantes.

### <a name="all-prices-include-tax-is-selected"></a>Tous les prix sont taxes comprises est sélectionné

|-|Ventes nationales|Pays étranger/région étrangère où vous ne recouvrez pas de taxes|Pays étranger/région étrangère où vous ne recouvrez pas de taxes|
|------------------------|--------|--------|--------|
|Prix affiché en magasin|1200|1200|1200|
|Pourcentage de taux de taxe|2.0|25|0|
|Prix à la caisse|1200|1200|1200|

Le prix pour le client reste inchangé, quel que soit son emplacement, mais cela affecte votre marge, car les taux de taxe sont différents selon les pays/régions.

### <a name="all-prices-include-tax-is-not-selected"></a>Tous les prix sont taxes comprises n'est pas sélectionné

|-|Ventes nationales|Pays étranger où vous recouvrez des taxes|Pays étranger où vous ne recouvrez pas de taxes|
|------------------------|--------|--------|--------|
|Prix affiché en magasin|1 000|1 000|1 000|
|Pourcentage de taux de taxe|2.0|25|0|
|Prix à la caisse|1200|1250|1 000|

Shopify ajoute les taxes locales en plus du prix défini sur la fiche produit en fonction de l’endroit où les marchandises sont livrées.

## <a name="dynamic-tax-inclusive-pricing"></a>Tarification TTC dynamique

Les pays/régions ont des exigences différentes pour inclure la taxe dans les prix. Si vous souhaitez que les prix incluent automatiquement la taxe, vous pouvez activer la [tarification dynamique TTC](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing) dans Shopify.

Dans votre **Administrateur Shopify**, sélectionnez **Inclure ou exclure les taxes en fonction du pays de votre client** dans la section **Autres marchés – Préférences** des paramètres [**Marchés**](https://www.shopify.com/admin/settings/markets).  

> [!NOTE]
> Ce paramètre n’affecte pas la représentation des prix sur les marchés nationaux, qui est contrôlée par le bouton bascule **Tous les prix sont taxes comprises**.

### <a name="all-prices-include-tax-is-selected-1"></a>Tous les prix sont taxes comprises est sélectionné

|-|Ventes nationales|Pays étranger/région étrangère où la taxe est incluse dans le prix|Pays étranger/région étrangère où la taxe n’est pas incluse|
|------------------------|---------------|---------------|--------|
|Prix affiché en magasin|1200|1250|1 000|
|Pourcentage de taux de taxe|2.0|25|10|
|Prix à la caisse|1200|1250|1100|

Le prix pour chaque client varie en fonction de l’emplacement du client.

### <a name="all-prices-include-tax-is-not-selected-1"></a>Tous les prix sont taxes comprises n'est pas sélectionné

|-|Ventes nationales|Pays étranger/région étrangère où la taxe est incluse dans le prix|Pays étranger/région étrangère où la taxe n’est pas incluse|
|------------------------|--------|--------|--------|
|Prix affiché en magasin|1 000|1250|1 000|
|Pourcentage de taux de taxe|2.0|25|10|
|Prix à la caisse|1200|1250|1100|

> [!NOTE]
> Le bouton bascule **Tous les prix sont taxes comprises** ne modifie pas la façon dont les prix sont affichés pour les clients internationaux.

## <a name="if-you-sell-to-eu-customers"></a>Si vous vendez à des clients de l’UE

Différents pays/régions de l’UE ont des taux de taxes locales différents. Toutefois, si vous êtes situé dans l’UE et que vous vendez dans d’autres pays/régions de l’UE, vous pouvez, dans certains cas, utiliser votre taux de taxe local.  

Dans votre **Administrateur Shopify**, cochez la case **Recouvrer la TVA** dans la section **Union européenne** des paramètres [**Taxes et droits de douane**](https://www.shopify.com/admin/settings/taxes).

|Recouvrer la TVA|Taux de TVA|
|-|-|
|Exonération des micro-entreprises|Utiliser votre taux de taxe national pour toutes les ventes à l’intérieur de l’UE|
|Guichet unique ou identification spécifique au pays/à la région|Utiliser le taux de TVA du pays/de la région de votre client|

### <a name="collect-vat-set-to-one-stop-shop-registration"></a>Recouvrer la TVA définie sur l'identification à guichet unique

Dans l’exemple suivant, le bouton bascule **Tous les prix sont taxes comprises** est activé. Le prix sur la fiche produit est fixé à *1 200*.

|-|Ventes nationales|Pays étranger/région étrangère|
|------------------------|--------|--------|
|Prix affiché en magasin|1200|1250|
|Pourcentage de taux de taxe|2.0|25|
|Prix à la caisse|1200|1250|

Shopify utilise le taux de taxe du pays/de la région étrangère lors du calcul des prix finaux.

### <a name="collect-vat-set-to-micro-business-exemption"></a>Recouvrer la TVA fixée définie sur l’exonération des micro-entreprises

Dans l’exemple suivant, le bouton bascule **Tous les prix sont taxes comprises** est activé. Le prix sur la fiche produit est fixé à *1 200*.

|-|Ventes nationales|Pays étranger/région étrangère avec un taux de taxe local de 25 %.|
|------------------------|--------|--------|
|Prix affiché en magasin|1200|1200|
|Pourcentage de taux de taxe|2.0|2.0|
|Prix à la caisse|1200|1200|

Shopify utilise le taux de taxe national et ignore le taux de taxe dans le pays étranger/la région étrangère lors du calcul des prix finaux.

## <a name="importing-shopify-orders-sold-to-international-customers"></a>Importation des commandes Shopify vendues à des clients internationaux

Si vous recouvrez des taxes dans plusieurs pays/régions, vous devez définir un paramètre spécifique au pays/à la région dans [!INCLUDE[prod_short](../includes/prod_short.md)]. Il y a une raison pour laquelle ce paramètre est requis. Lorsqu’un document de vente est créé dans [!INCLUDE[prod_short](../includes/prod_short.md)], [!INCLUDE [prod_short](../includes/prod_short.md)] calcule les taxes plutôt que de réutiliser les taxes importées depuis Shopify.

Vous spécifiez les paramètres spécifiques au pays/région sur la page **Modèle client Shopify**. Vous pouvez définir le **N° client par défaut** ou **N° modèle client**. Dans les deux cas, assurez-vous que les champs suivants sont définis pour le client ou le modèle sélectionné :

1. **Groupe de report marché** (utilisé pour les clients étrangers).
2. **Groupe de report marché TVA** (utilisé pour les clients étrangers).
3. **Prix TTC** (aligné avec le réglage sur le côté Shopify) :

* Choisissez **Oui** si **Tous les prix sont taxes comprises** est activé et **Inclure ou exclure les taxes en fonction du pays de votre client** est désactivé.
* Choisissez **Non** si **Tous les prix sont taxes comprises** est désactivé et **Inclure ou exclure les taxes en fonction du pays de votre client** est désactivé.
* Choisissez **Oui** si **Inclure ou exclure les taxes en fonction du pays de votre client** est activé, et le pays ou la région est répertorié dans [Pays/régions TTC](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).
* Choisissez **Non** si **Inclure ou exclure les taxes en fonction du pays de votre client** est activé, et le pays ou la région n’est pas répertorié dans [Pays/régions TTC](https://help.shopify.com/en/manual/markets/pricing/dynamic-tax-inclusive-pricing#tax-inclusive-versus-tax-exclusive-countries-and-regions).

> [!NOTE]
> Le paramètre du champ **Prix TTC** provient du modèle, pas du client spécifique. C’est pourquoi il est important que le modèle client soit défini.

## <a name="other-tax-remarks"></a>Autres remarques sur les taxes

Même si la commande Shopify importée contient des informations sur les taxes, les taxes sont recalculées lorsque vous créez le document vente. Ce nouveau calcul indique qu’il est important que les paramètres TVA/Taxe soient corrects dans [!INCLUDE[prod_short](../includes/prod_short.md)].

* Plusieurs taux de taxe ou de TVA sur les produits. Par exemple, certaines catégories de produits peuvent bénéficier de taux de taxe réduits. Vous pouvez utiliser la fonctionnalité de [remplacement des taxes](https://help.shopify.com/en/manual/taxes/tax-overrides#create-a-manual-collection-for-products-that-need-a-tax-override) dans Shopify. Lorsque vous importez des articles et les créez dans [!INCLUDE[prod_short](../includes/prod_short.md)], ils utilisent le paramètre de taxe tel qu’il est renseigné sur le code modèle article dans le magasin Shopify. Avant d’importer des commandes avec ces articles, vous devez mettre à jour le groupe de report des produits TVA.  
* Taux de taxe dépendant de l’adresse. Utilisez le champ **Priorité région fiscale** avec le tableau **Modèles client** pour remplacer la logique standard qui renseigne le **Code région fiscale** dans le document vente. Le champ **Priorité région fiscale** spécifie la priorité qui indique à la fonction où prendre des informations sur le pays ou la région, et sur l’état ou la province. L’enregistrement correspondant dans les modèles client Shopify est ensuite identifié, et les champs **Code région fiscale**, **Imposable** et **Groupe de report marché TVA** sont utilisés lors de la création d’un document vente.  

## <a name="see-also"></a>Voir aussi

[Mise en route du connecteur pour Shopify](get-started.md)  
