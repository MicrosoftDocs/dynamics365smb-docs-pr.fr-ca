---
title: Transfert d’articles entre des emplacements entrepôt
description: Découvrez comment déplacer un inventaire d’un lieu ou d’un entrepôt à un autre soit avec le journal reclassement soit à l’aide d'ordres de transfert.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 02/21/2023
ms.custom: bap-template
ms.search.keywords: 'move, warehouse'
ms.search.forms: '5746, 5745, 5759, 5753, 5743, 5758, 5752, 5744, 5749, 5740, 5741, 5742, 5757, 5748, 5747, 9285, 5756, 5755'
---
# Transfert d'inventaire entre des emplacements

Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert. Vous pouvez également utiliser le journal reclassement article.

> [!NOTE]
> Pour transférer des articles, vous devez configurer des emplacements et des acheminements transfert. Pour en savoir plus sur la configuration des emplacements, voir [Configurer des emplacements](inventory-how-setup-locations.md). Vous ne pouvez pas utiliser d’ordres de transfert pour des emplacements *vides*.

## Ordres de transfert

Vous pouvez livrer un transfert sortant à partir d’un emplacement et recevoir un transfert entrant à destination. Vous pouvez :

* Suivre une quantité en transit
* Définissez les calendriers, les itinéraires et les heures de traitement entrant et sortant pour le calcul et la planification des dates. Pour en savoir plus sur la planification, consultez [À propos de la fonctionnalité de planification](production-about-planning-functionality.md).
* Utilisez différentes fonctionnalités d’entrepôt pour les emplacements entrants et sortants.
* Avec certaines limitations, vous pouvez utiliser des ordres de transfert pour les transferts directs.

## Journaux reclassement article

* Transfert simple et direct d’articles entre emplacements.
* Déplacez les articles entre zones. Pour en savoir plus sur le transfert d’articles entre zones, consultez [Déplacer des articles non planifiés dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)
* Remplacez un numéro de lot ou de série par un nouveau numéro de lot ou de série. Pour en savoir plus sur le reclassement des numéros de série et de lot, consultez [Reclasser les numéros de série ou de lot](inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).
* Remplacez la date d’expiration par une nouvelle date.
* Reclasser les articles d’un emplacement *vide* vers un emplacement réel.
* Les activités d’entrepôt ne sont pas gérées. Des écritures entrepôt seront créées.

## Pour transférer des articles avec un ordre de transfert

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Ordres de transfert**, puis sélectionnez le lien associé.
2. Sur la page **Ordre de transfer**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   Si vous avez renseigné les champs **Code transit**, **Code agent de livraison** et **Prestation agent de livraison** sur la page **Spéc. acheminement transfert** lors de la configuration de l’acheminement transfert, les champs correspondants sur l’ordre de transfert sont renseignés automatiquement.

    Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.

3. Pour renseigner les lignes, saisissez manuellement les données ou choisissez l’une des options suivantes sous l'action **Fonctions** :

    * Choisissez l'action **Extraire contenu de la zone** pour sélectionner des éléments existants dans une zone spécifique de l'emplacement.
    * Choisissez l'action **Extraire lignes réception**pour sélectionner les articles qui viennent d'arriver dans l'emplacement provenance transfert.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à livrer les articles.
4. Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.

    Les articles sont à présent en transit entre les magasins spécifiés, selon l'acheminement transfert spécifié.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles. Les lignes Ordre transfert sont les mêmes que lors de la livraison et ne peuvent pas être modifiées.
5. Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.

## Pour transférer des articles avec le journal reclassement article

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux reclassement article**, puis choisissez le lien associé.
2. Sur la page **Journal reclassement article**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.

    > [!NOTE]  
    > Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.
4. Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.
5. Sélectionnez l'action **Valider**.

## Voir la [formation Microsoft](/training/modules/transfer-items/) associée

## Voir aussi .

[Gestion du stock](inventory-manage-inventory.md)  
[Configurer des emplacements](inventory-how-setup-locations.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
