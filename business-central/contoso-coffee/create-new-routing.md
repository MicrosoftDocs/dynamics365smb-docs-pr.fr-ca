---
title: Créer un itinéraire
description: Procédure pas à pas pour apprendre à saisir manuellement toutes les informations relatives à un nouvel itinéraire dans Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# Procédure pas à pas : Créer un itinéraire

Dans cet article, nous vous expliquons comment utiliser les données de démonstration Contoso Coffee pour configurer manuellement un nouvel itinéraire de production dans [!INCLUDE [prod_short](../includes/prod_short.md)].  

## Scénario

Oscar, l’ingénieur de processus chez Contoso Coffee, décide de créer un itinéraire nommé *Nouveau chemin*. Étant donné que cet itinéraire ne ressemble à aucun autre chez Contoso Coffee, il doit saisir manuellement toutes les informations relatives à l'itinéraire.  

## Étapes

1. Créez l’en-tête de l'itinéraire.  

    1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **itinéraires**, puis sélectionnez le lien associé.  

    2. Cliquez sur l’action **Nouveau**, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**N°** |1099|
        |**Description** |Nouveau chemin|
2. Créer les lignes itinéraire.

    1. Dans le raccourci **Lignes**, ajoutez une nouvelle ligne, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**N° opération** |10|
        |**Type** |Atelier|
        |**N°** |100|
        |**Temps de préparation** |20|
        |**Temps d’exécution** |15|

    2. Ajoutez une nouvelle ligne, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**N° opération** |20|
        |**Type** |Atelier|
        |**N°** |200|
        |**Temps de préparation** |30|
        |**Temps d’exécution** |5|
3. Certifiez l'itinéraire.

    1.Dans le champ **État**, choisissez *Validé*.  

Le nouvel itinéraire est maintenant configuré.  

## Voir aussi

[Introduction aux données de démonstration Contoso Coffee](contoso-coffee-intro.md)  
