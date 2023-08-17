---
title: Utiliser la planification des commandes pour créer et réserver un approvisionnement
description: Procédure pas à pas pour apprendre à utiliser la planification des commandes pour créer le bon de production requis pour l’approvisionnement dans Business Central.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics365-business-central
author: edupont04
ms.author: andreipa
---

# <a name="walkthrough-use-order-planning-to-create-and-reserve-supply"></a>Procédure pas-à-pas : Utiliser la planification des commandes pour créer et réserver un approvisionnement

Dans cet article, nous vous expliquons comment utiliser les données de démonstration de Contoso Coffee dans la planification des commandes.

## <a name="scenario"></a>Scénario

Vous êtes planificateur de production chez Contoso Coffee. Vous avez créé un bon de production pour 100 unités de l’article **SP-SCM1009, Airpot**, et vous souhaitez planifier des produits semi-finis pour cette commande. Vous utilisez la planification des commandes pour créer le bon de production requis pour l’approvisionnement. Étant donné que vous créez le bon de production pour répondre aux exigences d’une commande spécifique, vous décidez de réserver la production du bon de production.  

## <a name="steps"></a>Étapes

1. Créez le nouveau bon de production libéré pour 100 unités de l’article **SP-SCM1009, Airpot**.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bon de production libéré**, puis sélectionnez le lien associé.  

    2. Cliquez sur l’action **Nouveau**, puis renseignez les champs comme indiqué dans le tableau suivant.  

        |Champ  |Valeur  |
        |---------|---------|
        |**Type origine** |Article ;|
        |**N° origine** |SP-SCM1009|
        |**Quantité** |100|
    3. Choisissez l’action **Actualiser Bon de production**.  

    Notez le numéro du bon de production libéré.

2. Ouvrez la page **Planification commande** et calculez un nouveau plan.

    1. Sélectionnez l'action **Planification**.  

    2. Sur la page **Planification commande**, choisissez l'action **Calculer planification**.  

    3. Faites défiler jusqu’à la ligne de demande qui représente le bon de production libéré que vous avez créé précédemment.  

    4. Développez les lignes pour afficher les détails de la ligne demande. Confirmez qu’il s’agit d’une suggestion pour un bon de production de 100 unités de l’article 1001.  

3. Créez un nouveau bon de production pour 100 unités d’article **SP-BOM2000, Ensemble réservoir**, et réservez la sortie de ce bon de production pour le compte de l’ordre parent associé.  

    1. Cochez la case du champ **Réserver** sur la ligne de demande pour les 100 unités de l’article SP-BOM2000.

    2. Sélectionnez l'action **Créer commandes**.  

    3. Définissez le champ **Créer commandes pour** sur *La ligne active*.  

    4. Définissez le champ **Créer un Bon de production** sur *Planifié ferme*.

    5. Cliquez sur le bouton **OK** pour créer le bon de production.

    6. Sur la page **Planification commande**, confirmez que la ligne de demande pour les 100 unités de l’article 1001 est supprimée.

C’est tout pour la planification des commandes dans [!INCLUDE [prod_short](../../includes/prod_short.md)].  

## <a name="see-also"></a>Voir aussi

[Introduction aux données de démonstration Contoso Coffee](../contoso-coffee-intro.md)  
[À propos des bons de production](../../production-about-production-orders.md)  
