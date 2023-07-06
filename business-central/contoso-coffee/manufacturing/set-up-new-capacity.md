---
title: Configurer une nouvelle capacité
description: Procédure pas à pas pour apprendre à configurer un nouvel atelier avec un calendrier de capacité pour un seul quart de travail dans Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# <a name="walkthrough-set-up-new-capacity"></a><a name="walkthrough-set-up-new-capacity"></a><a name="walkthrough-set-up-new-capacity"></a>Procédure pas-à-pas : Configurer une nouvelle capacité

Dans cet article, nous vous expliquons comment utiliser les données de démonstration de Contoso Coffee pour gérer les capacités.  

## <a name="scenario"></a><a name="scenario"></a><a name="scenario"></a>Scénario

Vous êtes planificateur de production chez Contoso Coffee. En réponse à des changements dans l’atelier, vous devez créer un nouveau atelier, un département de test. Le nouveau atelier dispose d’une unité de production pour effectuer des tests. Le nouveau poste doit avoir un calendrier de capacité pour un seul quart de travail de 8 h 00 à 16 h 00, du lundi au vendredi.  

## <a name="steps"></a><a name="steps"></a><a name="steps"></a>Étapes

1. Configurez l'atelier.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **ateliers**, puis choisissez le lien associé.  

    2. Cliquez sur l’action **Nouveau**, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**N°** |700|
        |**Nom** |Département de test|
        |**Code groupe ateliers** |1, Département production|
        |**Coût unitaire direct**|3,25|
        |**Calcul du coût unitaire**|Heure|
        |**Méthode consommation**|Manuel|
        |**Groupe de report produit**|SANS TVA</br></br>Notez que cette sélection dépend de la configuration de la comptabilité et de votre pays.|
        |**Code d’unité de mesure** |MINUTES|
        |**Capacité** |1|
        |**Rendement** |90|
        |**Code calendrier usine** |1|

        Dans le champ **Code calendrier usine**, 1 désigne une équipe du lundi au vendredi.

    3. Fermez la fiche de l'atelier.

2. Configurez l'unité de production.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **unités de production**, puis choisissez le lien associé.  

    2. Cliquez sur l’action **Nouveau**, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**N°** |760|
        |**Nom** |Test|
        |**N° atelier** |700, département des tests|
        |**Coût unitaire direct**|3,25|
        |**Méthode consommation**|Manuel|
        |**Groupe de report produit**|SANS TVA</br></br>Notez que cette sélection dépend de la configuration de la comptabilité et de votre pays.|
        |**Capacité** |1|
        |**Rendement** |90|
    3. Développez le raccourci **Configuration itinéraire**, puis, dans le champ **Temps de préparation**, entrez *10*.  

3. Calculez le calendrier de capacité de l'unité de production.  

    1. Sélectionnez l'action **Calendrier**.  

    2. Dans la page **Calendrier unité de production**, sur le raccourci **Options matrice**, définissez le champ **Afficher par** sur *Mois*.  

    3. Choisissez l'action **Afficher matrice**.  

    4. Sur la page **Matrice Calendrier unité de production**, choisissez l’action **Calculer**.  

    5. Dans la page **Calculer calendrier unité de production**, sur le raccourci **Options**, définissez le champ **Date début** sur *1er janvier*.  

    6. Définissez le champ **Date de fin** sur 31 décembre.  

    7. Sur le raccourci **Unité de production**, dans le champ à filtrer **N°**. sélectionnez *760, Tests*.  

    8. Choisissez le bouton **OK**. Une fois le traitement en lot terminé, vous revenez sur la page **Matrice Calendrier unité de production**.  

    9. Sélectionnez l'action **Actualiser**.  

    10. Sur la ligne de l'unité de production 760, Tests, accédez à la valeur de la colonne de janvier.  

Sur la page **Écritures calendrier**, les écritures de capacité journalière du champ **Capacité (totale)** sont de 480 minutes. Cela correspond à un quart de travail de huit heures pour chaque journée de travail. De plus , le champ **Capacité (réelle)** indique 432 minutes. Cela reflète le taux d’efficacité de 90 % que vous avez attribué à l'unité de production.  

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi

[Introduction aux données de démonstration Contoso Coffee](../contoso-coffee-intro.md)  
