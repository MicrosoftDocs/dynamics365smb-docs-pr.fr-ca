---
title: Combiner la consommation automatique et la consommation manuelle
description: Procédure pas à pas pour un gestionnaire de production chez Contoso Coffee qui souhaite combiner la consommation automatique et et la consommation manuelle.
ms.date: 04/01/2022
ms.topic: article
ms.service: dynamics-365-business-central
author: brentholtorf
ms.author: bholtorf
---

# <a name="walkthrough-combine-automatic-and-manual-flushing"></a>Procédure pas à pas : Combiner la consommation automatique et la consommation manuelle

Dans cet article, nous vous expliquons comment utiliser les données de démonstration Contoso Coffee dans la consommation.  

## <a name="scenario"></a>Scénario

Vous êtes planificateur de production chez Contoso Coffee. Vous devez créer un nouveau bon de production pour 10 unités de l’article SP-SCM1004, AutoDrip. Certaines composantes et opérations seront consommées en aval et d’autres en amont en fonction de différentes conditions.

## <a name="steps"></a>Étapes

> [Remarque !] N’oubliez pas d’ajuster l'inventaire en reportant le journal article avec les soldes d’ouverture.

1. Créez un bon de production planifié ferme pour cinq unités de l’article **SP-SCM1004, AutoDrip** à l’emplacement *PRINCIPAL*. Pour obtenir des conseils, voir [Procédure pas à pas : Créer un bon de production planifié ferme et le modifier](create-firm-planned-production-order-change.md).  

2. Libérez le bon de production.

    1. Choisissez l’action **Modifier état**.  

    2. Dans la page qui s’affiche, définissez le champ **Nouvel état** sur *Libéré*, puis choisissez le bouton **Oui**.  

        Un message avec une barre d’état s’affiche et fait référence à la consommation automatique. Il est suivi d’un message de confirmation indiquant que l’ordre est modifié pour avoir l'état *Libéré*.  

    3. Cliquez sur le bouton **OK** pour fermer le message de confirmation.

3. Vérifiez les écritures article et capacité pour le bon de production.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bon de production libéré**, puis sélectionnez le lien associé.  

    2. Ouvrez le bon de production avec les 5 unités de la machine à café AutoDrip.  

    3. Sélectionnez l’action **Écritures article**.  

        L’article **SP-BOM1305 Vis hex m3, zinc** est immédiatement consommé avec la quantité prévue totale. Fermez la page **Écritures article**.  

    4. Choisissez l’action **Écritures capacité**.  Notez qu’une écriture d’opérations d’assemblage du corps a également été effectuée au moment du lancement de la commande. Fermez la fenêtre **Écritures capacité**.

    Vous pouvez consommer manuellement les composantes à l’aide du journal consommation ou du journal production. La consommation manuelle vous permet d’ajuster la quantité avant de reporter. Par exemple, si une quantité supplémentaire est nécessaire pour couvrir des matières premières de faible qualité.
4. Consommez les composantes manuellement.  
    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal consommation**, puis choisissez le lien associé.  

    2. Choisissez l’action **Calculer consommation**.  

    3. Dans la page de demande **Calculer consommation**, dans le raccourci **Bon de production**, définissez un filtre pour l’ordre spécifique dans le champ **N° commande** puis choisissez le bouton **OK**. Après la fermeture de la page de demande de traitement en lot, notez que la page **Journal consommation** se remplit avec les composantes qui nécessitent une consommation manuelle.

    4. Choisissez l’action **Reporter**. Fermez le journal consommation.

5. Enregistrez manuellement la production pour le câblage électrique.  

    Vous devez renseigner manuellement les champs **Temps de préparation** et **Temps d’exécution**. Vous pouvez également spécifier la quantité réellement produite et le rebut. Entrez *3* comme quantité de production et reportez la production.

    1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me.](../../media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal de sortie**, puis choisissez le lien associé.  

    2. Sur la page **Journal production**, créez une ligne journal.  

    3. Dans le champ **N° d’ordre**, spécifiez l’ordre.  

    4. Choisissez l’action **Éclater itinéraire**.  

        La page **Journal production** se remplit avec la ligne d’opération uniquement pour le câblage électrique.

    5. Définissez le champ **Temps d’exécution** sur *10*.  

    6. Remplacez la valeur du champ **Quantité** *5* par *3*.

    7. Choisissez **Reporter**.  
    8. Fermez le journal production.

6. Vérifiez les écritures article pour le bon de production.

    1. Dans la page du bon de production, choisissez l’action **Écritures article**.  

    L’article **SP-BOM1302, Affich. panneau conf.** est reporté avec une quantité de *3*, sur la base de la production réelle, tandis que l’article **SP-BOM1303, Bouton** est reporté avec la quantité prévue totale. Fermez la page **Écritures article**.

7. Terminez le bon de production.  

    1. Choisissez l’action **Modifier état**.
    2. Dans la page qui s’affiche, définissez le champ **Nouvel état** sur *Terminé*, puis choisissez le bouton **Oui**.  

        Un message s’affiche avec une barre d’état qui reflète la consommation automatique. Il est suivi d’un message de confirmation indiquant que l’ordre est transformé en ordre avec l'état *Terminé*. Le bon de production terminé a le même numéro que celui qu’il avait avec l'état *Libéré*.
    3. Cliquez sur le bouton **OK** pour fermer le message de confirmation.

8. Vérifiez à nouveau les écritures article et capacité pour le bon de production.

    1. Choisissez l’action **Écritures capacité**.  

        L’écriture des opérations de livraison a été réalisée au moment du lancement de la commande. La quantité produite (production) est *5*, quelle que soit la production de l’étape précédente. Fermez la page **Écritures capacité**.

    2. Sélectionnez l’action **Écritures article**.  

        La quantité de l’écriture article du type *Production* est égale à la quantité produite dans l’écriture capacité. La quantité consommée des articles **SP-BOM1301, AutoDrip logement** et **SP-BOM1304, Carafe therm. acier inox** est 5, car la production prévue et la production réelle sont les mêmes. 

    3. Fermez la page **Écritures article**.  

C’est tout pour la consommation manuelle et automatique des composantes.

## <a name="see-also"></a>Voir aussi

[Consommer des composantes en fonction de la production réalisée](../../production-how-to-flush-components-according-to-operation-output.md)  
[Introduction aux données de démonstration Contoso Coffee](contoso-coffee-manufacturing-intro.md)  
