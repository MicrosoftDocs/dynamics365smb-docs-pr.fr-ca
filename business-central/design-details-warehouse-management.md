---
title: Gérer les activités entrepôt
description: 'Outre les réceptions et les livraisons, Business Central prend en charge une série d’activités d’entrepôt internes.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/05/2022
ms.custom: bap-template
---

# <a name="warehouse-management-overview"></a>Vue d’ensemble de la gestion des entrepôts

Deux choses sont importantes pour toutes les entreprises qui transportent physiquement des marchandises dans et hors de leur entrepôt :

* Elles ont une vue d’ensemble des niveaux d'inventaire et du placement des articles dans l’entrepôt.
* Elles peuvent recevoir, prélever et livrer des articles rapidement et avec précision.

Pour aider les entreprises à atteindre ces objectifs, les fonctionnalités d’entrepôt dans [!INCLUDE[prod_short](includes/prod_short.md)] ajoutent les fonctionnalités suivantes à la gestion de l'inventaire :

* Zones
* Livraisons entrepôt
* Prélèvements inventaire
* Feuille mouvement

Implémentez ces fonctionnalités dans différentes combinaisons pour adapter vos processus d’entrepôt à votre entreprise. Prévoyez une complexité croissante à mesure que votre compagnie se développe et que vos processus évoluent.

## <a name="overview-of-different-configuration-options"></a>Aperçu des différentes options de configuration

Vous pouvez configurer les fonctionnalités d’entrepôt de différentes manières. Il est important de choisir les options qui améliorent vos processus sans entraîner de surcharge. Le tableau suivant donne un aperçu des configurations typiques lorsqu’il s’agit de biens physiques.

|Niveau de complexité|Désignation|Paramètres|Code de zone|Exemple de flux entrant|Exemple de flux sortant|Exemple de flux interne|  
|---|----------------|----------|---------|------------------|------------------|------------------|
|Aucune activité entrepôt dédiée.|Report à partir de commandes et de journaux.||Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Bon de commande|Document de vente| Bon de production -> Journal consommation|  
|Basique|Envoi/réception regroupés pour plusieurs commandes.|**Réception requise**<br>**Livraison requise**.|Facultatif. Contrôlé par le bouton à bascule Code de zone obligatoire|Bon(s) de commande -> Réception entrepôt|Document de vente -> Livraison entrepôt|Comme ci-dessus.|
|Basique|Commande par commande.|Rangement requis ou Prélèvement requis. </br><br/> **REMARQUE** : bien que les paramètres soient appelés **Prélèvement requis** et **Rangement requis**, vous pouvez quand même reporter les réceptions et les livraisons directement à partir des documents source dans les emplacements où vous cochez ces cases.|Facultatif. Contrôlé par le bouton à bascule **Code de zone obligatoire**.|Bon de commande -> Rangement inventaire|Document de vente -> Prélèvement inventaire|Bon de production -> Prélèvement inventaire|
|Avancé|Envoi/réception regroupés pour plusieurs commandes.<br /><br />Activités de prélèvement/rangement regroupées pour plusieurs documents origine.|Réception requise + Rangement requis,</br> Livraison requise + Prélèvement requis|Facultatif. Contrôlé par le bouton à bascule Code de zone obligatoire|Bon(s) de commande -> Réception entrepôt -> Rangement entrepôt|Document(s) de vente -> Livraison(s) entrepôt -> Feuille prélèvement -> Prélèvement(s) entrepôt| Bon de production -> Journal prélèvement -> Prélèvement(s) entrepôt -> Journal consommation|
|Avancé|Comme ci-dessus + activités de prélèvement/rangement dirigées|Prélèvement et rangement dirigés (les boutons à bascule dépendants seront activés automatiquement)|Obligatoire|Comme ci-dessus.|Comme ci-dessus.| Bon de production -> Journal prélèvement -> Prélèvement(s) entrepôt -> Journal consommation|

La complexité augmente avec la taille de votre organisation et le nombre de départements et de personnes impliqués. Un processus peut être simple, par exemple, lorsque la même personne crée et publie un document de vente. Les processus peuvent également être plus complexes et impliquer plusieurs étapes et personnes. Les étapes suivantes sont un exemple de processus plus complexe :

1. Un préparateur de commandes crée une document de vente.
1. Un responsable d’entrepôt crée des instructions de prélèvement.
1. Un employé d'entrepôt termine le flux en reportant la livraison entrepôt.

Le niveau de complexité est également affecté par les types de documents que vous utilisez dans vos activités d’entrepôt. Par exemple, vous pouvez utiliser des documents de réception entrepôt et de rangement entrepôt pour votre flux entrant, mais utiliser des documents de prélèvement inventaire pour votre flux sortant.

Un autre facteur qui influe sur la complexité est la façon dont votre entrepôt physique est représenté dans [!INCLUDE[prod_short](includes/prod_short.md)]. Learn more at [Modélisation de l’entrepôt physique](#modeling-the-physical-warehouse).

## <a name="modeling-the-physical-warehouse"></a>Modélisation de l’entrepôt physique

Vous disposez de plusieurs options pour représenter la configuration réelle de votre entrepôt dans [!INCLUDE[prod_short](includes/prod_short.md)]. Vos choix déterminent la manière dont vous utiliserez les fonctionnalités de l’entrepôt.

Les articles peuvent être placés sur des tablettes, des emplacements ou des zones, et chaque option présente des avantages et des inconvénients.

### <a name="locations-and-bins"></a>Emplacements et zones

Pour manipuler des biens physiques, vous devez avoir au moins un emplacement. Vous pouvez utiliser plusieurs emplacements ou utiliser des zones pour modéliser votre entrepôt et votre structure organisationnelle.

En règle générale, les emplacements sont le moyen privilégié pour organiser des opérations réparties sur plusieurs zones géographiques. Dans certains cas, cependant, vous souhaiterez peut-être créer plusieurs emplacements situés au même endroit. L’utilisation des emplacements présente les avantages suivants :

* Accordez l’accès en utilisant les pages **Employé d'entrepôt** et **Centres de gestion**.
* Définissez les calendriers, les itinéraires et les heures de traitement entrant et sortant pour le calcul et la planification des dates. Pour plus d’informations, voir [À propos de la fonctionnalité Planification](production-about-planning-functionality.md).
* Spécifiez les dimensions par défaut et utilisez différentes configurations de report d'inventaire.
* Configurez les paramètres de planification. Learn more at [Paramètres de planification](production-about-planning-functionality.md#planning-parameters).  
* Utilisez différentes fonctionnalités d’entrepôt pour chaque emplacement.

### <a name="shelves-and-bins"></a>Tablettes et zones

Si vous stockez toujours un article au même endroit, vous pouvez utiliser le champ **N° tablette** sur les pages **Fiche article** ou **Fiche point de stock**. Ce champ peut être utilisé comme système de stockage manuel de base dans des environnements sans zone. La valeur du champ est copiée à partir de la fiche article vers les lignes document et les rapports, mais à titre informatif uniquement. La valeur n’est pas utilisée dans les activités d’entrepôt ou dans les calculs de disponibilité.

Les zones représentent la structure d’entrepôt de base et sont utilisées pour faire des propositions relatives à l’emplacement des articles :

* Une ou plusieurs zones fixes pour un article.
* Les zones pour des opérations spécifiques, comme une zone d’expédition ou une zone de sortie de production.
* Des restrictions de capacité et de poids des zones (uniquement pour le rangement et le prélèvement dirigés).
* Classement des zones (pour le rangement et le prélèvement dirigés uniquement).

## <a name="typical-warehouse-workflow"></a>Flux de travail typique d’un entrepôt

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Dans un flux de base, selon le principe de commande par commande, utilisez un rangement inventaire pour enregistrer la réception des articles dans les emplacements, y compris toute réception excédentaire. Ou, si vous regroupez plusieurs commandes dans la réception, utilisez une réception entrepôt.|[Flux entrant](design-details-inbound-warehouse-flow.md)|
|Enregistrez la livraison des articles à partir des emplacements d’entrepôt. Sur le principe de commande par commande, utilisez un prélèvement inventaire. Ou, si vous regroupez plusieurs commandes dans la livraison, utilisez une livraison entrepôt.|[Flux sortant](design-details-outbound-warehouse-flow.md)|
|Manipulez les articles dans l’emplacement d’entrepôt. Par exemple, lorsque vous déplacez des composantes vers la production ou effectuez un inventaire physique.|[Flux interne](design-details-internal-warehouse-flows.md)|

Configurez les processus d’entrepôt qui conviennent à votre entreprise. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

## <a name="terminology-related-to-warehouse-management"></a>Terminologie liée à la gestion d’entrepôt

### <a name="complexity-levels"></a>Niveaux de complexité

Nous utilisons les termes « de base » et « avancé » pour différencier les niveaux de complexité. Cette différenciation simple couvre plusieurs niveaux de complexité dans les configurations d’emplacement, chacune prise en charge par différents documents d’entrepôt. Le niveau d’entreposage le plus avancé est appelé « Rangement et prélèvement dirigés ׃. Pour utiliser le rangement et le prélèvement dirigés pour un emplacement, activez le bouton à bascule **Rangement et prélèvement dirigés** sur la page **Fiche emplacement**.

### <a name="warehouse-flows"></a>Flux d’entrepôt

* Flux entrant : déplace les articles vers l’emplacement d’entrepôt et les rend disponibles, par exemple pour les achats et les transferts entrants.
* Flux sortant : prélève et livre les articles aux clients ou à d’autres emplacements.
* Flux interne : gère les articles au sein d’un emplacement. Par exemple, vous déplacez des composantes vers la production ou effectuez un inventaire physique.

### <a name="basic-documents"></a>Documents de base

Les documents suivants sont utilisés dans les flux d’entrepôt de base.

* Article dans l'inventaire à classer
* Article en inventaire à prélever
* Mouvement d'inventaire
* Journal article
* Journal de reclassements d'articles

### <a name="advanced-documents"></a>Documents avancés

Les documents suivants sont utilisés dans les flux d’entrepôt avancés.

* Réception de l'entrepôt
* Feuille rangement
* Rangement magasin
* Feuille prélèvement
* Prélèvement magasin
* Feuille mouvement
* Mouvement d'entrepôt
* Prélèvement entrepôt interne
* Rangement entrepôt interne
* Feuille de création de zone
* Feuille de création du contenu de la zone
* journal article entrepôt
* Journal reclassement article entrepôt

### <a name="pages-and-settings"></a>Pages et paramètres

Cette section décrit les concepts sous-jacents aux pages et paramètres clés pour l’entreposage.

#### <a name="bins-and-bin-content"></a>Zones et contenu zone

Une zone est un dispositif de stockage conçu pour contenir des éléments distincts. Il s’agit de la plus petite unité de conteneur dans [!INCLUDE[prod_short](includes/prod_short.md)]. Les quantités d’articles dans les zones sont appelées *contenu de la zone*. Une recherche à partir du champ **Article** ou du champ **Code de zone** dans n'importe quelle ligne de document entrepôt affiche la disponibilité calculée de l'article dans la zone.  

Le contenu de la zone peut être **Fixe**, **Dédié** ou **Par défaut** pour définir comment utiliser le contenu de la zone. Les zones sans aucune de ces propriétés sont appelées zones *dynamiques*.  

Une zone statique contient les articles affectés au code de zone concerné. La propriété de zone statique garantit que même si la zone est vidée, le contenu de la zone ne disparaît pas. Vous pouvez sélectionner à nouveau la zone dès que son contenu est réapprovisionné.  

Une zone dédiée contient le contenu de la zone qui peut uniquement être prélevé pour la ressource dédiée qui utilise la zone. Par exemple, une unité de production. Un autre contenu non-prélèvement, tel que les quantités sortantes sur un report de livraison, peut être consommé à partir d’une zone dédiée. Seul le contenu de la zone pris en compte par l'algorithme **Créer prélèvement** est protégé dans une zone réservée.  

[!INCLUDE [prod_short](includes/prod_short.md)] utilise la propriété de zone **Par défaut** pour proposer des zones pour les activités de l’entrepôt. Dans les emplacements qui utilisent le rangement et le prélèvement dirigés, la propriété de zone par défaut n’est pas utilisée. Dans les emplacements où des zones sont requises, la propriété indique où placer les articles dans les flux entrants. Dans les flux sortants, la propriété indique l’endroit où prendre des articles.  

> [!NOTE]  
> Si les articles sortants sont stockés dans plusieurs zones, les articles sont d’abord pris dans les zones non définies par défaut, pour vider le contenu de ces zones, puis les articles restants sont pris dans la zone par défaut.  

Il ne peut y avoir qu’une zone par défaut par article et par emplacement.  

#### <a name="bin-type"></a>Type zone

Les emplacements qui utilisent le rangement et le prélèvement dirigés peuvent utiliser des types de zone. Les types de zone contrôlent les activités que vous autorisez pour une zone. Les types d’emplacement disponibles sont les suivants :  

|Type zone|Désignation|  
|------------------|---------------------------------------|  
|RECEPT.|Articles reçus mais non rangés.|  
|LIVR.|Articles prélevés pour des lignes livraison entrepôt, mais pas encore reportés comme livrés.|  
|RANG.|Généralement, les articles devant être stockés dans de grandes unités de mesure, mais auxquels vous ne souhaitez pas accéder à des fins de prélèvement. Ces zones ne sont pas utilisées pour le prélèvement, que ce soit pour les bons de production ou les livraisons ; leur utilisation peut donc être limitée. Ce type de zone est utile lorsque vous achetez une grande quantité d’articles. Les zones doivent toujours avoir un rang de zone bas, de sorte que les articles avec des zones PUTPICK de rang supérieur soient rangés en premier. Réapprovisionnez régulièrement ce type de zone afin que leurs articles soient disponibles dans des zones de type PUTPICK ou PICK.|  
|PRELEV.|Articles à utiliser uniquement pour prélever. Vous ne pouvez utiliser les mouvements que pour le réapprovisionnement de ces zones, pas pour le rangement.|  
|RGMT/PRLVT|Articles dans des zones qui sont proposés à la fois pour le rangement et le prélèvement. Les emplacements de ce type ont vraisemblablement un classement différent. Configurez vos zones de stockage en vrac avec des classements de zone inférieurs à ceux des zones de prélèvement ordinaires ou des zones dans votre zone de prélèvement en aval.|  
|CQ|Cet emplacement est utilisé pour des ajustements stock, si vous le spécifiez sur la fiche magasin dans le champ **Code empl. ajustement**. Vous pouvez également configurer des emplacements de ce type pour des articles défectueux ou en cours de contrôle. Vous pouvez déplacer des articles vers ce type de zone afin que le flux habituel des articles ne puisse pas y accéder. **Remarque :** contrairement à tous les autres types de zone, les cases à cocher pour le traitement des articles sont toutes désactivées par défaut pour le type **CQ**. Le contenu que vous placez dans une zone CQ est exclu des flux d’article.|  

À l’exception des types de zones PICK, PUTPICK et PUTAWAY, le type de zone définit l’activité autorisée pour une zone. Par exemple, vous ne pouvez utiliser qu’un type de zone RECEIVE pour recevoir des articles ou pour en prélever des articles.  

> [!NOTE]  
> Vous devez utiliser des mouvements pour déplacer les articles vers les zones RECEIVE et CQ. Utilisez des mouvements pour déplacer des articles des zones SHIP et CQ.  

#### <a name="bin-ranking"></a>Classement de zone

Dans l’entreposage avancé, vous pouvez automatiser et optimiser la collecte des articles dans les feuilles rangement et prélèvement en classant les zones. Les articles sont suggérés pour les prélèvements et les rangements en fonction du rang des zones.

Les procédés de rangement sont optimisés en fonction du classement de zone en suggérant des zones de priorité plus élevée avant les zones de priorité faible. Les procédés de prélèvement suggèrent en premier les articles ayant le classement de zone le plus élevé dans le contenu de zone. Le réapprovisionnement des zones suggère les zones de rang inférieur avant les zones de rang supérieur.  

Le classement et le contenu des zones sont les propriétés de base qui guident les employés dans l’entrepôt.  

#### <a name="bin-setup"></a>Configuration zone

Dans l’entreposage avancé, vous pouvez spécifier les valeurs de capacité suivantes pour contrôler comment et dans quelles zones vous stockez les articles :

* Quantité
* Cubage total
* Poids  

Vous pouvez attribuer une unité de mesure de base aux articles. Une unité de mesure de base peut être constituée de pièces, de palettes, de litres, de grammes ou de boîtes. Vous pouvez également créer des unités de mesure plus grandes en fonction de votre unité de mesure de base. Par exemple, si les pièces sont votre unité de mesure de base, une palette peut être égale à 16 pièces.  

Si un article a plusieurs unités de mesure, définissez la quantité maximale pour chaque unité de mesure sur la fiche article. Si vous manipulez un article sous forme de pièces et de palettes, le champ **Qté max.** de la page **Contenu zone** pour cet article doit également être défini en pièces et en palettes. Sinon, la quantité autorisée pour cette zone n'est pas calculée correctement.  

Avant de paramétrer des restrictions de capacité pour le contenu de zone dans une zone, assurez-vous que les unités de mesure et les dimensions de l’article ont été définies dans la fiche article.  

> [!NOTE]  
> Vous ne pouvez utiliser plusieurs unités de mesure que dans les emplacements qui utilisent le rangement et le prélèvement dirigés. Dans toutes les autres configurations, les contenus zone ne peuvent être que dans l’unité de mesure de base. Dans les transactions avec une unité de mesure supérieure à l’unité de mesure de base de l’article, la quantité est transformée en unité de mesure base.  

#### <a name="zone"></a>Zone

Dans l’entreposage avancé, des zones peuvent être groupées en zones pour gérer la manière dont le flux de travail des activités entrepôt est suggéré pour les emplacements.  

Une zone peut être une zone de réception ou une zone de stockage, et chaque zone peut comporter une ou plusieurs zones.  

La plupart des propriétés affectées à une zone sont affectées aux zones créées pour la zone.  

#### <a name="warehouse-class"></a>Classe magasin

Dans l’entreposage avancé, vous pouvez affecter des codes de classe d’entrepôt aux entités suivantes : 

* Articles
* Zones
* Zones

Les classes d’entrepôt contrôlent où stocker les articles. Vous pouvez diviser une zone en plusieurs classes d'entrepôt. Par exemple, vous pouvez stocker des articles dans la zone de réception dans la classe gelé, dangereux ou autre.

Lorsque vous travaillez sur des classes d’entrepôt avec une zone de réception/livraison par défaut, vous devez choisir manuellement les zones appropriées dans la réception entrepôt et les lignes livraison.  

Dans les flux entrants, le code classe est uniquement sélectionné sur les lignes entrantes lorsque le code classe article ne correspond pas à la zone de réception par défaut. Si les zones par défaut ne sont pas correctement affectées, la quantité ne peut pas être reçue.  

#### <a name="location"></a>Magasin

Un emplacement est une structure physique ou un lieu où l'inventaire est reçu, stocké et livré. Un emplacement peut être un entrepôt, une voiture de service, une salle d’exposition, une usine ou une zone d’une usine. L’inventaire est souvent organisé en zones.

#### <a name="first-expired-first-out"></a>FEFO (First-Expired-First-Out, premier expiré, premier sorti)

Si vous activez la case à cocher **Prélèvement selon FEFO** sur le raccourci **Config. zone** de la page **Fiche emplacement**, les articles suivis sont prélevés dans l’emplacement en fonction de leur date d’expiration. Les articles dont les dates de péremption sont les plus proches sont prélevés en premier.  

Les activités d’entrepôt dans tous les document de prélèvement et de mouvement sont triées selon FEFO, à moins que les articles en question n’aient des numéros de série ou de lot affectés. Si une partie seulement de la quantité de la ligne a des numéros de série ou de lot affectés, la quantité restante est triée selon FEFO.  

Lors du prélèvement selon FEFO, les articles qui expirent en premier sont rassemblés dans une liste temporaire de traçabilité en fonction de la date de péremption. Si deux articles ont la même date d'expiration, l’article avec le plus petit numéro de lot ou de série est prélevé en premier. Si les numéros de lot ou de série sont identiques, l’article enregistré en premier est sélectionné en premier. Les critères standard de sélection des articles dans les zones prélèvement, par exemple Classement de zone et Déconditionnement, sont appliqués à la liste de traçabilité FEFO temporaire.  

#### <a name="put-away-template"></a>Modèle rangement

Les modèles de rangement spécifient un ensemble de règles de priorité qui s’appliquent lorsque vous créez des rangements. Par exemple, un modèle de rangement peut vous obliger à placer des articles dans une zone dont le contenu a la même unité de mesure. S’il est impossible de trouver une zone similaire d’une capacité suffisante, l’article doit être placé dans une zone vide. Vous affectez un modèle de rangement à un article et à un emplacement.  

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/get-started-warehouse-management/) associée

## <a name="see-also"></a>Voir aussi

[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
