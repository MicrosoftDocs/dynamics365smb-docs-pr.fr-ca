---
title: Détails de conception - Configuration d'entrepôt | Microsoft Docs
description: La fonctionnalité d'entrepôt dans Business Central contient différents niveaux de complexité, tels que définis par les autorisations de licence dans les granules proposés. Le niveau de complexité dans une solution entrepôt est en grande partie défini par la configuration des zones sur les fiches emplacement, qui est lui-même contrôlé par licence afin que l'accès aux champs de configuration des zones soit défini par la licence.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 32c3fedfbeea37a1be315d737ac9fe41b5c7c20a
ms.sourcegitcommit: adf1a87a677b8197c68bb28c44b7a58250d6fc51
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/21/2021
ms.locfileid: "5035441"
---
# <a name="design-details-warehouse-setup"></a>Détails de conception : paramètres entrepôt

La fonctionnalité d'entrepôt dans [!INCLUDE[prod_short](includes/prod_short.md)] contient différents niveaux de complexité, tels que définis par les autorisations de licence dans les granules proposés. Le niveau de complexité dans une solution entrepôt est en grande partie défini par la configuration des zones sur les fiches emplacement, qui est lui-même contrôlé par licence afin que l'accès aux champs de configuration des zones soit défini par la licence. En outre, les objets d'application de la licence déterminent le document d'interface utilisateur à utiliser pour les activités entrepôt prises en charge.  
<!--
The following warehouse-related granules exist:  

- Basic Inventory (4010)  
- Bin (4170)  
- Put Away (4180)  
- Warehouse Receipt (4190)  
- Pick (4200)  
- Warehouse Shipment (4210)  
- Warehouse Management Systems (4620)  
- Internal Picks and Put-aways (4630)  
- Automated Data Capture System (4640)
- Bin Setup (4660)  

For more information about each granule, see [[!INCLUDE[prod_short](includes/prod_short.md)] Price Sheets](https://go.microsoft.com/fwlink/?LinkId=238341) (requires PartnerSource account). -->

Le tableau suivant indique les granules requis pour définir les différents niveaux de complexité entrepôt, les documents de l'interface utilisateur qui prennent en charge chaque niveau et les codes d'emplacement qui reflètent ces niveaux dans la base de données de démonstration [!INCLUDE[prod_short](includes/prod_short.md)].  

[!INCLUDE [locations-cronus](includes/locations-cronus.md)]

|Niveau de complexité|Description|Document d'interface utilisateur|Exemple d’emplacement|Granule minimum requis|  
|----------------|-----------|-----------|---------------|---------------------------|  
|1|Aucune activité entrepôt dédiée.<br /><br /> Report recevoir/livrer à partir des commandes.|Ordre|BLEU|Inventaire de base|  
|2|Aucune activité entrepôt dédiée.<br /><br /> Report recevoir/livrer à partir des commandes.<br /><br /> Le code de zone est requis.|Commande, avec un code de zone|ARGENTE|Inventaire de base/Zone|  
|3 <br /><br /> **REMARQUE** : bien que les paramètres soient appelés **Prélèvement requis** et **Rangement requis**, vous pouvez quand même reporter les réceptions et les livraisons directement à partir des documents commerciaux sources dans les emplacements où vous cochez ces cases.|Activité entrepôt de base, par commande.<br /><br /> Report de réception/livraison à partir des documents rangement/prélèvement inventaire. <br /><br /> Le code de zone est requis.|Article dans l'inventaire à classer/Mouvement d'inventaire/Article dans l'inventaire à prélever, avec code de zone|(ARGENT + Rangement requis ou Rangement requis)|Inventaire de base/Zone/Rangement/Prélèvement|  
|4|Activité entrepôt avancée pour plusieurs ordres/commandes.<br /><br /> Report recevoir/livrer consolidé en fonction des enregistrements de rangement/prélèvement dans l'entrepôt.|Réception entrepôt/Rangement entrepôt/Prélèvement entrepôt/Livraison entrepôt/Feuille prélèvement|VERT|Inventaire de base/Réception entrepôt/Rangement/Prélèvement/Livraison entrepôt|  
|5|Activité entrepôt avancée pour plusieurs ordres/commandes.<br /><br /> Report recevoir/livrer consolidé en fonction des enregistrements de rangement/prélèvement dans l'entrepôt.<br /><br /> Le code de zone est requis.|Réception entrepôt/Rangement en entrepôt/Prélèvement entrepôt/Livraison entrepôt/Feuille prélèvement/Feuille rangement, avec code de zone|(VERT + Zone obligatoire)|Inventaire de base/Zone/Réception entrepôt/Rangement/Prélèvement/Livraison entrepôt|  
|6 <br /><br /> **Remarque** : ce niveau est appelé « WMS », car il requiert le granule le plus avancé, Warehouse Management Systems.|Activité entrepôt avancée pour plusieurs ordres/commandes<br /><br /> Report recevoir/livrer consolidé en fonction des enregistrements de rangement/prélèvement dans l'entrepôt<br /><br /> Le code de zone est requis.<br /><br /> Le code zone/classe est facultatif.<br /><br /> Magasiniers dirigés par flux de travail<br /><br /> Planification de réapprovisionnement des zones<br /><br /> Classement de zone<br /><br /> Configuration de la zone par capacité<br /><br /> Insertion  <!-- Hand-held device integration -->|Réception entrepôt/Rangement entrepôt/Prélèvement entrepôt/Livraison entrepôt/Mouvement entrepôt/Feuille prélèvement/Feuille rangement/Entrepôt interne. Prélèvement/Rangement entrepôt interne, avec code de zone/classe<br /><br /> Différentes feuilles pour la gestion de la zone<br /><br /> Écrans ADCS|BLANC|Inventaire de base/Zone/Rangement/Réception entrepôt/Prélèvement/Livraison entrepôt/Systèmes de gestion d'entrepôt/Prélèvements internes et rangements/Configuration zone<!-- Automated Data Capture System/ -->Configuration zone|  

Pour des exemples d'utilisation des documents de l'interface utilisateur par niveau de complexité entrepôt, voir [Détails de conception : flux d'enlogement](design-details-inbound-warehouse-flow.md).  

## <a name="bin-and-bin-content"></a>Zone et contenu de la zone

Une zone est un dispositif de stockage conçu pour contenir des éléments distincts. Il s'agit de la plus petite unité de conteneur dans [!INCLUDE[prod_short](includes/prod_short.md)]. Les quantités d'articles dans des zones sont appelées contenu de la zone. Une recherche à partir du champ **Article** ou du champ **Code de zone** dans n'importe quelle ligne de document entrepôt affiche la disponibilité calculée de l'article dans la zone.  

Le contenu de la zone peut se voir affecter une propriété fixe, dédiée ou par défaut, pour définir la manière dont le contenu de la zone peut être utilisé. Les zones sans aucune de ces propriétés sont appelées zones dynamiques.  

Une zone fixe contient les articles affectés au code de zone concerné. La propriété de zone fixe garantit que même si le contenu de la zone est momentanément vidé, le contenu de la zone ne disparaît pas et la zone est donc de nouveau sélectionnée dès qu'elle a été réapprovisionnée.  

Une zone réservée contient le contenu de la zone qui peut être prélevé pour la ressource réservée, par exemple une unité de production, qui utilise la zone en question. Un autre contenu non-prélèvement, tel que les quantités sortantes sur un report de livraison, peut encore être consommé à partir d'une zone réservée. Seul le contenu de la zone pris en compte par l'algorithme **Créer prélèvement** est protégé dans une zone réservée.  

La propriété de la zone par défaut est utilisée par le système pour proposer des zones pour les activités entrepôt. Dans des emplacements WMS, la propriété de la zone par défaut n'est pas utilisée. Dans les emplacements où des zones sont requises, la propriété est utilisée dans des flux entrants pour indiquer l'endroit où placer les articles. Dans les flux de désenlogement, la propriété est utilisée pour indiquer l'endroit où prendre des articles.  

> [!NOTE]  
>  Si les articles sortants sont stockés dans plusieurs zones, les articles sont d'abord prélevés dans les zones non définies par défaut, pour vider le contenu de ces zones, puis les articles restants sont pris dans la zone par défaut.  

Il ne peut y avoir qu'une zone par défaut par article par emplacement.  

## <a name="bin-type"></a>Type zone

Dans des installations WMS, vous pouvez définir les activités entrepôt qui sont autorisées pour une zone en lui affectant un type de zone. Les types de zone suivants existent :  

|Type zone|Description|  
|------------------|---------------------------------------|  
|RECEPT.|Articles reportés comme étant reçus, mais pas encore rangés.|  
|LIVR.|Les articles prélevés pour des lignes livraison entrepôt, mais pas encore reportés en tant qu'articles livrés.|  
|RANG.|Généralement, les articles devant être stockés dans de grandes unités de mesure, mais auxquels vous ne souhaitez pas accéder à des fins de prélèvement. Étant donné que ces zones ne sont pas utilisées pour le prélèvement, que ce soit pour des bons de production ou des livraisons, l'utilisation d'une zone de type Rangement risque d'être limitée, mais ce type de zone peut se révéler utile si vous avez acheté une grande quantité d'articles. La priorité des zones de ce type doit toujours être peu élevée. Ainsi, lors du rangement des articles reçus, ce sont les zones RANGPRÉLÈV. de priorité plus élevée associés à l'article concerné qui sont rangées en premier lieu. Lorsque vous utilisez ce type de zone, vous devez régulièrement procéder au réapprovisionnement des zones, afin que les articles stockés dans ces zones puissent également être disponibles dans les zones de type RANGPRÉLÈV. ou PRÉLÈV.|  
|PRELEV.|Articles à utiliser uniquement pour prélever. Le réapprovisionnement de ces zones peut uniquement être effectué par mouvement, non par rangement.|  
|RGMT/PRLVT|Articles dans des zones qui sont proposés à la fois pour les fonctions de rangement et de prélèvement. Les emplacements de ce type ont vraisemblablement un classement différent. Vous pouvez configurer vos zones de stockage en vrac comme ce type de zone avec un classement peu élevé par rapport à vos zones prélèvement ordinaires ou vos zones prélèvement en aval.|  
|CQ|Cet emplacement est utilisé pour des ajustements stock, si vous le spécifiez sur la fiche magasin dans le champ **Code empl. ajustement**. Vous pouvez également configurer des emplacements de ce type pour des articles défectueux ou en cours de contrôle. Vous pouvez déplacer des articles vers ce type de zone afin que le flux habituel des articles ne puisse pas y accéder. **Remarque :** contrairement à tous les autres types de zone, les cases à cocher pour le traitement des articles sont toutes désactivées par défaut pour le type de zone **CQ**. Cela signifie que tout contenu que vous placez dans une zone de type CQ est exclu des flux d'articles.|  

Pour tous les types de zone, à l'exception de PRÉLÈV, RANGPRÉLÈV et RANGEMENT, aucune autre activité n'est autorisée pour la zone que celle définie par son type de zone. Par exemple, une zone de type **Réception** peut être utilisée uniquement pour recevoir des articles ou pour en prélever.  

> [!NOTE]  
> Un mouvement ne peut être effectué que vers des zones de type RÉCEPTIONNER et CQ. De même, seuls des mouvements peuvent être effectués à partir des zones de type LIVR. et CQ.  

## <a name="bin-ranking"></a>Priorité zone

Dans l'entreposage avancé, vous pouvez automatiser et optimiser la façon de collecter les articles dans des feuilles de rangement et de prélèvement en classant les zones par ordre de priorité, de sorte que le programme propose de prendre ou de placer ces articles en fonction des critères de priorité pour optimiser l'utilisation de l'espace de l'entrepôt.  

Les procédés de rangement sont optimisés en fonction du classement de zone en suggérant des zones de priorité plus élevée avant les zones de priorité faible. De même, des procédés de prélèvement sont optimisés en proposant d'abord les articles du contenu des zones à priorité élevée. De plus, des réapprovisionnements de zone sont suggérés à partir des zones de faible priorité vers celles ayant un niveau plus élevé.  

Le classement de zone ainsi que les informations relatives au contenu de la zone sont les propriétés de base permettant aux utilisateurs d'insérer des articles dans l'entrepôt.  

## <a name="bin-setup"></a>Configuration zone  
Dans l'entreposage avancé, des zones peuvent être configurées à l'aide des valeurs de capacité, telles que la quantité, le volume total, ainsi que le poids pour contrôler quels articles sont enregistrés dans la zone et comment.  

Sur chaque fiche article, vous pouvez affecter une unité de mesure pour l'article, par exemple des pièces, palettes, litres, grammes ou boîtes. Vous pouvez également avoir une base UOM pour un article et spécifier de plus grands UOM basés dessus. Par exemple, vous pouvez définir une palette égale à 16 pièces, ce qui est l'unité de base.  

Si vous souhaitez définir une quantité maximum pour un article spécifique à enregistrer dans une zone en particulier et que l'article a plusieurs unités de mesure, vous devez définir la quantité maximum de chaque unité de mesure qui existe dans la fiche article. Par conséquent, si un article a été configuré pour être traité en tant que pièces et palettes, le champ **Qté max.** de la page **Contenu de la zone** pour cet article doit également être considéré en tant que pièces et palettes. Sinon, la quantité autorisée pour cette zone n'est pas calculée correctement.  

Avant de paramétrer des restrictions de capacité pour le contenu de la zone dans une zone, vous devez d'abord vous assurer que les unités de mesure et les dimensions de l'article ont été définies dans la fiche article.  

> [!NOTE]  
> Il est possible d'utiliser plusieurs unités dans les installations WMS. Dans toutes les autres configurations, les contenus de la zone ne peuvent être que dans l'unité de mesure de base. Dans toutes les transactions avec une unité supérieure à l’unité de base de l’article, la quantité est transformée en unité de base.  

## <a name="zone"></a>Zone

Dans l'entreposage avancé, des zones peuvent être groupées en zones pour gérer la manière dont le flux de travail des activités entrepôt est suggéré.  

Une zone peut être une zone de réception ou une zone de stockage, et chaque zone peut comporter une ou plusieurs zones.  

La plupart des propriétés affectées à une zone sont par défaut affectées à la zone qui est créée à partir de cette zone.  

## <a name="class"></a>Catégorie  
Dans l'entreposage avancé, vous pouvez affecter des codes classe entrepôt aux articles et aux zones pour contrôler l'endroit où les différentes classes d'article sont stockées, telles que les produits gelés. Vous pouvez diviser une zone en plusieurs classes d'entrepôt. Par exemple, des articles figurant dans la zone de réception peuvent être enregistrés comme gelés, dangereux ou autre classe.  

Lorsque vous travaillez sur des classes d'entrepôt et une zone de réception/livraison par défaut, vous devez renseigner manuellement les zones appropriées dans la réception entrepôt et les lignes livraison.  

Dans les flux entrants, le code classe est uniquement sélectionné sur les lignes entrantes lorsque le code classe article ne correspond pas à la zone de réception par défaut. Si les zones par défaut ne sont pas correctement affectées, la quantité ne peut pas être reçue.  

## <a name="location"></a>Magasin

Un emplacement est une structure ou un lieu physique de réception de l'inventaire, conservé et livré. Il est éventuellement organisé sous forme de zones. Un emplacement peut être un entrepôt, une voiture de service, une salle d'exposition, une usine ou une zone dans une usine.  

## <a name="first-expired-first-out"></a>FEFO (First-Expired-First-Out, premier expiré, premier sorti)

Si vous activez la case à cocher **Prélèvement selon FEFO** sur le raccourci **Politiques de zones** de la fiche emplacement, les articles suivis sont prélevés en fonction de leur date d'expiration. Les articles dont les dates de péremption sont les plus proches sont prélevés en premier.  

Les activités d'entrepôt dans tous les document de prélèvement et de mouvement sont triées selon FEFO, à moins que les articles en question n'aient déjà des numéros de série/lot affectés. Si une partie seulement de la quantité de la ligne a déjà des numéros de série/lot affectés, la quantité restante à prélever est triée selon FEFO.  

Lors du prélèvement selon FEFO, les articles disponibles qui expirent en premier sont rassemblés dans une liste temporaire de traçabilité en fonction de la date d'expiration. Si deux articles ont la même date d'expiration, l'article ayant le plus petit numéro de série ou de lot est prélevé en premier. Si les numéros de lot ou de série sont identiques, l'article enregistré en premier est sélectionné en premier. Les critères standard de sélection des articles dans les zones prélèvement, par exemple Classement de zone et Déconditionnement, sont affectés à cette liste de traçabilité FEFO temporaire.  

## <a name="put-away-template"></a>Modèle rangement

Le modèle rangement peut être affecté à un article et à un emplacement. Le modèle rangement spécifie un ensemble de règles classées par priorité qui doivent être respectées lors de la création de rangements. Par exemple, un modèle de rangement peut exiger que l'article soit situé dans une zone dont le contenu correspond à l'unité de mesure, et si une zone similaire comportant suffisamment de capacité est introuvable, alors l'article doit être placé dans une zone vide.  

## <a name="see-also"></a>Voir aussi

[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)   
[Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md)
