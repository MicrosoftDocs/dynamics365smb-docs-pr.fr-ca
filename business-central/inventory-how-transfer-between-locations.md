---
title: Transfert d’articles entre des emplacements entrepôt
description: Découvrez comment déplacer un inventaire d’un lieu ou d’un entrepôt à un autre soit avec le journal reclassement soit à l’aide d'ordres de transfert.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 05/24/2024
ms.custom: bap-template
ms.search.keywords: 'move, warehouse'
ms.search.forms: '5746, 5745, 5759, 5753, 5743, 5758, 5752, 5744, 5749, 5740, 5741, 5742, 5757, 5748, 5747, 9285, 5756, 5755'
ms.service: dynamics-365-business-central
---
# Transférer l’inventaire entre des emplacements

Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert. Vous pouvez également utiliser le journal reclassement article.

> [!NOTE]
> Pour transférer des articles, vous devez configurer des emplacements et des acheminements transfert. Pour en savoir plus sur la configuration des emplacements, voir [Configurer des emplacements](inventory-how-setup-locations.md). Vous ne pouvez pas utiliser d’ordres de transfert pour des emplacements *vides*.

## Ordres de transfert

Vous pouvez livrer un transfert sortant à partir d’un emplacement et recevoir un transfert entrant à destination. Vous pouvez :

* Suivre une quantité en transit
* Définissez les calendriers, les itinéraires et les heures de traitement entrant et sortant pour le calcul et la planification des dates. Pour en savoir plus sur la planification, consultez [À propos de la fonctionnalité de planification](production-about-planning-functionality.md).
* Utilisez différentes fonctionnalités d’entrepôt pour les emplacements entrants et sortants.
* Utiliser des ordres de transfert pour les transferts directs, Avec certaines limitations.

## Journaux reclassement article

Vous pouvez utiliser la page **Journaux reclassement article** pour :

* Transfert direct d’articles entre emplacements.
* Déplacez les articles entre zones. Pour en savoir plus sur le transfert d’articles entre zones, consultez [Déplacer des articles non planifiés dans les configurations de stockage de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md)
* Remplacez un numéro de lot ou de série par un nouveau numéro de lot ou de série. Pour en savoir plus sur le reclassement des numéros de série et de lot, consultez [Reclasser les numéros de série ou de lot](inventory-how-work-item-tracking.md#to-reclassify-serial-or-lot-numbers).
* Remplacez la date d’expiration par une nouvelle date.
* Reclasser les articles d’un emplacement vide vers un emplacement réel.
* Créez des entrées d’entrepôt si vous ne gérez pas les activités d’entrepôt.

## Pour transférer des articles avec un ordre de transfert

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Ordres de transfert**, puis sélectionnez le lien associé.
2. Sur la page **Ordre de transfer**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   Si vous avez renseigné les champs **Code transit**, **Code agent de livraison** et **Prestation agent de livraison** sur la page **Spéc. acheminement transfert** lors de la configuration de l’acheminement transfert, les champs correspondants sur l’ordre de transfert sont renseignés automatiquement.

    Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.

3. Il existe plusieurs façons de remplir les lignes :

    |Option  |Désignation  |
    |---------|---------|
    |Manuellement     | Dans le raccourci **Lignes**, complétez une ligne pour un article, ou utilisez l’action **Sélectionner les articles** pour choisir plusieurs articles.        |
    |Automatiquement     | * Choisissez l’action **Extraire contenu zone** pour sélectionner des éléments existants dans une zone spécifique.<br><br>* Choisissez **Extraire lignes réception** pour sélectionner les éléments qui viennent d’arriver dans l'emplacement provenance transfert.        |

    Vous pouvez maintenant livrer les articles.
4. Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.

    Les articles sont à présent en transit entre les emplacements spécifiés, selon l’acheminement transfert.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles. Les lignes ordre de transfert sont les mêmes que lors de la livraison et ne peuvent pas être modifiées.
5. Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.

### Reporter plusieurs ordres transfert dans un lot

La procédure suivante explique comment reporter plusieurs ordres transfert dans un lot.

1. 1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Ordres de transfert**, puis sélectionnez le lien associé.  
2. Sur la page **Ordres transfert**, sélectionnez les commandes à reporter.
3. Dans le champ **N°**, ouvrez le menu contextuel et choisissez **Sélectionner plus**.
4. Cochez la case pour les lignes pour chaque commande que vous souhaitez reporter.
5. Choisissez l’action **Report**, puis sélectionnez l’action **Reporter par lot**.
6. Sur la page **Reporter en lot les ordres de transfert**, renseignez les champs comme nécessaire.

   > [!TIP]
    > Pour les ordres transfert qui utilisent un lieu de transit, vous pouvez choisir soit **Livrer** ou **Recevoir**. Répétez cette étape si vous devez faire les deux. Pour les commandes où l’option **Report direct** est activée, les deux options fonctionnent de la même manière et reportent intégralement la commande.

7. Sélectionnez **OK**.
8. Pour afficher les problèmes potentiels, ouvrez la page **Registre des messages d’erreur**.

    > [!NOTE]
    > Le report de plusieurs documents peut prendre un certain temps et bloquer d’autres utilisateurs. Envisagez d’activer le report en arrière-plan. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](/dynamics365/business-central/admin-job-queues-schedule-tasks).

### Programmer une entrée dans la file d’attente des travaux pour reporter plusieurs documents dans un lot

Vous pouvez également utiliser la file d’attente des travaux pour programmer le report à un moment qui convient à votre organisation. Par exemple, il peut sembler raisonnable dans votre activité d’exécuter certaines routines lorsque la plupart de la saisie de données de la journée est achevée.

La procédure suivante décrit comment configurer le rapport **Reporter en lot les ordres de transfert** pour un report automatique des ordres transfert directs lancés à 16 h 00 les jours de semaine. Cette heure n’est qu’un exemple. Les étapes sont similaires pour les autres documents.  

1. Recherchez la page **Écritures file d’attente des travaux**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Type objet à exécuter**, sélectionnez **Rapport**.  
4. Dans le champ **Code objet à exécuter**, sélectionnez **5707, Reporter en lot les ordres de transfert**.
5. Activez la case à cocher **Page requête rapport**.
6. Sur la page de demande **Reporter en lot les ordres de transfert**, choisissez l’option **Livrer**, filtrez sur **Transfert direct**, puis sélectionnez **OK**.

   > [!IMPORTANT]
   > Il est important de définir des filtres. Sinon, [!INCLUDE [prod_short](includes/prod_short.md)] reportera tous les documents, même s’ils ne sont pas prêts. Pensez à définir un filtre sur le champ **État** pour la valeur **Libéré**, et un filtre sur le champ **Date de report** pour la valeur **..aujourd’hui**. Pour en savoir plus sur les filtres, accédez à [Trier, rechercher et filtrer](/dynamics365/business-central/ui-enter-criteria-filters).

7. Activez toutes les cases à cocher de **Exécuter le lundi** à **Exécuter le vendredi**.
8. Dans le champ **Heure début**, entrez **16 h 00**.
9. Choisissez l'action **Attribuer l'état Prêt**.

## Pour transférer des articles avec le journal reclassement article

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux reclassement article**, puis choisissez le lien associé.
2. Sur la page **Journal reclassement article**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.

    > [!NOTE]  
    > Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.
4. Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.
5. Sélectionnez l'action **Reporter**.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## Annuler une livraison transfert

Si vous trouvez une erreur dans une quantité sur un ordre transfert reporté, tant que la livraison n’est pas reçue, vous pouvez facilement corriger la quantité. Sur la page **Livraison de transfert validée**, l’action **Annuler la livraison** crée des lignes correctives, comme suit :

* La valeur du champ **Quantité livrée** est diminuée de la quantité annulée.
* La valeur du champ **Quantité à livrer** est augmentée de la quantité annulée.
* La case **Correction** est cochée pour les lignes.

Si la quantité a été livrée dans une livraison entrepôt, une ligne de correction est créée dans la livraison entrepôt reportée.

Pour terminer la correction, rouvrez l’ordre transfert, entrez la quantité correcte, puis reportez l’ordre. Si la commande doit être expédiée à l’aide d’une livraison entrepôt, créez et reportez une livraison entrepôt.

## Voir aussi .

[Gestion du stock](inventory-manage-inventory.md)  
[Configurer des emplacements](inventory-how-setup-locations.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modification des fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
