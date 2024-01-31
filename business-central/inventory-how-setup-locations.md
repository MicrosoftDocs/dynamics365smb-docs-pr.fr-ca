---
title: Configurer une fiche emplacement et définir des acheminements de transfert (contient une vidéo)
description: 'Si vous achetez, stockez ou commercialisez des articles à plusieurs endroits, vous pouvez configurer chaque lieu en tant qu’emplacement.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'warehouse, distribution center'
ms.search.forms: '5703, 15'
ms.date: 03/25/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Configurer des emplacements

Les emplacements sont des endroits tels que des entrepôts où vous achetez, stockez ou vendez des articles. [!INCLUDE [prod_short](includes/prod_short.md)] utilise des emplacements pour aider à suivre l'inventaire dans les processus d’entrepôt à la fois simples et complexes.

Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements. Pour en savoir plus, voir [Gérer l’inventaire](inventory-manage-inventory.md).
<br><br>  
  
> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## Fiches emplacement

Vous spécifiez des informations sur un emplacement, par exemple un entrepôt ou un centre de distribution sur la page **Fiche emplacement**. Affectez un nom et un code représentatifs à chaque emplacement. Il vous suffit ensuite de saisir le code d'emplacement dans d’autres parties du programme lorsque vous souhaitez enregistrer les transactions d’un emplacement en particulier.  

Vous pouvez entrer des informations sur les zones et les règles entrepôt pour chaque emplacement. En fonction de vos stratégies d’entrepôt, vous pouvez utiliser les options sur le raccourci **Zones** pour spécifier lesquelles utiliser par défaut pour les transactions. Si vous utilisez les prélèvements et rangements suggérés, vous pouvez utiliser la plupart des options du raccourci **Politiques de zones** pour définir la façon dont vous souhaitez utiliser les différentes fonctions d’entrepôt avancées.  

Certains champs d’option dépendent des paramètres dans la page **Fiche emplacement** pour limiter les combinaisons de configuration non prises en charge.  

Choisissez les actions **Zone** ou **Zones** pour visualiser des informations sur les zones qui sont définies pour l'emplacement.

### Pour configurer un emplacement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.

> [!NOTE]  
> De nombreux champs de la page Fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement. Ces champs ne sont pas pertinents pour les compagnies qui n’ont pas besoin des fonctionnalités d’entrepôt complexes. Pour en savoir plus, accédez à [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Vous pouvez modifier la configuration d’un emplacement tant qu’il n’a pas d’écritures article.  

Si vous avez plusieurs emplacements, vous pouvez définir des acheminements transfert entre les emplacements. Pour en savoir plus sur les itinéraires de transfert, accédez à [Pour créer un itinéraire de transfert](inventory-how-setup-locations.md#to-create-a-transfer-route).

### Pour créer un acheminement transfert

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Acheminements de transfert**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
4. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez à présent transférer des articles en inventaire entre deux emplacements. Pour en savoir plus sur les transferts, accédez à [Transférer l’inventaire entre les emplacements](inventory-how-transfer-between-locations.md).

## Zones

Les zones représentent la structure de base de l’entrepôt et peuvent suggérer où placer les articles. Vos zones peuvent avoir du contenu ou être flottantes sans contenu spécifique.

Pour utiliser la fonctionnalité de zone liée à l’emplacement, vous devez d’abord activer la fonctionnalité sur la page **Fiche emplacement** sur le raccourci **Entrepôt** en activant le bouton à bascule **Zone obligatoire**. Vous pouvez concevoir le flux d’articles à l’emplacement en spécifiant des codes de zone dans les champs des processus d’entrepôt sur les raccourcis **Zones** et **Stratégies de zone**.

> [!NOTE]
> Avant de pouvoir spécifier les codes zone sur un emplacement, vous devez les créer. Pour en savoir plus sur les zones, accédez à [Créer des zones](warehouse-how-to-create-individual-bins.md) et [Configurer les types de zones](warehouse-how-to-set-up-bin-types.md).  

## Zones

Si vous souhaitez structurer vos zones en zones, vous pouvez le faire dans la page **Zones**. Lorsque vous affectez une zone à des zones, [!INCLUDE [prod_short](includes/prod_short.md)] copie les informations de la zone vers les zones. Vous pouvez également choisir de configurer une zone et d’utiliser des zones seules pour organiser votre entrepôt. Pour en savoir plus sur les zones, accédez à [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

## Dimensions par défaut pour les emplacements

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser avec différents outils de création de rapports. Par exemple, les dimensions peuvent indiquer le service ou le projet dont est issue une écriture. Le fait d’avoir des dimensions par défaut aide les gens à éviter de faire des erreurs et d’avoir à saisir manuellement les dimensions au niveau de la transaction si toutes les marchandises proviennent d’un seul emplacement et d’un même service.

Pour définir les dimensions par défaut pour un emplacement, allez sur la page **Fiche emplacement** et choisissez **Dimensions**. Par la suite, les dimensions par défaut de l’emplacement sont attribuées aux documents suivants lorsque vous choisissez l’emplacement sur une ligne.

* Ordres de transfert
* Commandes d’inventaire
* Livraisons inventaire
* Réceptions inventaire
* Journaux article

Au besoin, vous pouvez supprimer ou modifier les dimensions sur les lignes. Dans le champ **Contrôle report**, pouvez exiger que les personnes spécifient des dimensions pour des emplacements spécifiques avant de pouvoir reporter une écriture. Si vous souhaitez que les utilisateurs puissent choisir uniquement certaines valeurs de dimension, vous pouvez spécifier celles-ci dans le champ **Filtre valeurs autorisées**. Vous pouvez également inclure des valeurs de dimension d’emplacement sur la page **Affect. analytique prioritaire** et **Croisements analytiques** pour les combinaisons de règles de priorité et de dimension.

Puisque les documents d’ordre transfert et les journaux de reclassement traitent de plusieurs emplacements, l’ordre dans lequel vous saisissez les données est important. Les dimensions par défaut sont copiées à partir du dernier champ d’emplacement (l’emplacement en transit est ignoré).

### Exemple des dimensions par défaut sur les emplacements

Les exemples suivants illustrent comment la dimension par défaut est utilisée.

Vous avez les paramètres de dimension suivants :

* Emplacement EST. La dimension du service est ADM
* Emplacement OUEST. La dimension du service est PROD

Vous spécifiez l’emplacement sur un ordre transfert comme suit :

1. Emplacement de provenance = EST
2. Emplacement de destination = OUEST

La dimension PROD est copiée à partir de l’emplacement OUEST.

Vous remplissez les champs dans l’ordre inverse, comme suit :

1. Emplacement de destination = OUEST
2. Emplacement de provenance = EST

La dimension ADM est copiée à partir de l’emplacement EST.

## Voir aussi .

[Gestion du stock](inventory-manage-inventory.md)  
[Transférer l’inventaire entre des emplacements](inventory-how-transfer-between-locations.md)  
[Créer zones](warehouse-how-to-create-individual-bins.md)  
[Configurer des types de zone](warehouse-how-to-set-up-bin-types.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
