---
title: Gestion des variantes de produits
description: 'Découvrez comment vous pouvez enregistrer des produits presque identiques, mais dont la couleur, la taille ou le matériau varient en tant que variantes d’articles.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'item, variant, finished good, component, raw material, assembly item, item substitution'
ms.search.form: '30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719'
ms.date: 06/13/2024
ms.service: dynamics-365-business-central
---
# Gestion des variantes de produits

Les variantes d’articles sont un excellent moyen de garder votre liste de produits sous contrôle. Par exemple, vous avez un grand nombre d’articles quasiment identiques et dont seule la couleur varie. Vous pouvez définir chaque variante comme un article séparé. Mais vous choisissez aussi de configurer un article et de spécifier les différentes couleurs comme variantes de l’article.  

> [!TIP]
> Pour une introduction pratique à l’utilisation des variantes en production, voir [Procédure pas à pas : variantes](contoso-coffee/manufacturing/variants.md) pour les données de démonstration de Contoso Coffee.  

## Ajouter des variantes à un article

Il est assez simple de définir des variantes pour un article.  

### Pour ajouter des variantes

1. Ouvrez [la page **Fiche article**](https://businesscentral.dynamics.com/?page=31), puis ouvrez l’article approprié.  
2. Sur la page **Fiche article**, sélectionnez l’action **Variations**.  
3. Dans la page **Variantes article**, répertoriez les variantes.  

Ensuite, lorsque vous créez un document de vente et ajoutez l’article, vous pouvez spécifier la variante de l’article dans le champs **Code variante**. La même chose s’applique aux documents achat.  

## Dispo. article par variante

[!INCLUDE [inventory_variant-availability](includes/inventory_variant-availability.md)]

## Exiger l’utilisation de variantes

À compter de la 2e vague de lancement 2022, les administrateurs peuvent exiger des utilisateurs qu’ils précisent la variante dans les documents et les journaux pour les articles avec des variantes. Pour activer la fonctionnalité, sur la page **Configuration inventaire**, sélectionnez le champ **Variante obligatoire si elle existe**. Vous pouvez remplacer ce paramètre global pour des éléments spécifiques.  

Sur les fiches article, le champ **Variante obligatoire si elle existe** a les options suivantes :

|Valeur de champ |Désignation|
|---------|----|
|Par défaut (Non)| La définition de **Configuration inventaire** s’applique à cet article.|
|N°| Les utilisateurs ne sont pas tenus de spécifier une variante pour cet article.|
|Oui| Si l’article a une ou plusieurs variantes, les utilisateurs doivent spécifier la variante appropriée. S’ils ne le font pas, ils ne pourront pas reporter la transaction.|

> [!NOTE]
> Ces paramètres n’affectent pas les articles qui n’ont pas de variantes.

Si la fonctionnalité est activée, vous ne pouvez pas reporter une écriture si la variante n’est pas spécifiée.

## Catégories, attributs et variantes

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

## Voir aussi .

[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Configurer des informations générales relatives à l'inventaire](inventory-how-setup-general.md)  
[Procédure pas à pas : variantes](contoso-coffee/manufacturing/variants.md)  
