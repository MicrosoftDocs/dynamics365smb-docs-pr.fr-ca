---
title: Créer des itinéraires
description: 'Cet article donne une vue d’ensemble des différentes manières de créer des itinéraires, y compris les conditions préalables requises et comment créer des liens d''itinéraire.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.form: '99000764, 99000765, 99000766, 99000767, 99000794, 99000796, 99000798, 99000806, 99000808, 99000810, 99000817, 99000834, 99000835, 99000836, 99000837, 99000840, 99000841, 99000844, 99000845'
ms.date: 06/06/2024
ms.service: dynamics-365-business-central
---
# Créer des itinéraires

Les compagnies manufacturières utilisent des itinéraires pour visualiser et gérer le processus de fabrication.

L'itinéraire est la base de la programmation des processus et des capacités, de l'affectation programmée du matériel en fonction des besoins et des documents de production.  

En ce qui concerne les nomenclatures de production, les itinéraires sont affectés à l’article fini produit. Un itinéraire contient les données de base qui capturent les exigences du traitement correspondant à un article produit donné. Après la création d’un bon de production pour un article, son itinéraire régit le calendrier des opérations comme représenté sur la page **Itinéraire Bon de production** sous le bon de production.  

Pour pouvoir configurer un itinéraire, les paramètres suivants doivent être en place :  

- Des fiches article sont créées pour les articles parents qui participent à la production. Pour en savoir plus sur [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).
- Les ressources de production sont configurées. Pour plus d’informations, voir [Configurer des ateliers et des unités de production](production-how-to-set-up-work-and-machine-centers.md).

## Pour créer un itinéraire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Itinéraires**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Sélectionnez l'une des options du champ **Type tâche projet** :
   - **Série** pour calculer l'itinéraire de production en fonction de la valeur de **N° opération.** .  
   - Sélectionnez **Parallèle** pour calculer les opérations en fonction de la valeur de **Numéro de l'opération suivante**. .  
5. Pour modifier la gamme, définissez le champ **Statut** sur **Création en cours** ou sur **Modification en cours**.  

    Renseignez les lignes itinéraire.
6. Dans le champ **N° opération**, entrez le numéro de la première opération \(par exemple, **10**\).  
7. Dans le champ **Type**, sélectionnez le type de ressource utilisé, par exemple, **Centre de charge**.  
8. Dans le champ **N°**, sélectionnez la ressource à utiliser, ou entrez\-la.  
9. Dans le champ **Code lien itinéraire**, vous pouvez entrer un code permettant de lier la composante à une opération spécifique. Pour plus d'informations, voir [Pour créer des liens itinéraire](production-how-to-create-routings.md#to-create-routing-links).
10. Dans les champs **Temps d'exécution** et **Temps de préparation**, entrez les temps opératoires nécessaires pour exécuter l'opération.

     > [!NOTE]
     > Le temps de préparation est calculé par bon de production, tandis que le temps d'exécution est calculé par article produit.  

11. Dans le champ **Capacités simultanées** , indiquez combien d'unités de la ressource sélectionnée sont utilisées pour exécuter l'opération. Par exemple, deux personnes affectées à une opération de livraison divisent par deux le temps d’exécution.  
12. Poursuivez le remplissage des lignes pour toutes les opérations intervenant dans la production de l'article en question.  
13. Pour copier des lignes à partir d'un itinéraire existant, choisissez l'action **Copier itinéraire** pour sélectionner des lignes existantes.  
14. Pour activer l'itinéraire, dans le champ **État**, choisissez **Certifié**.  
15. Vous pouvez désormais lier le nouvel itinéraire à la fiche de l'article de production concerné en renseignant le champ **N° itinéraire**. Pour en savoir plus sur [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).  

> [!NOTE]  
> N'oubliez pas également de recalculer le coût standard de l'article dans la fiche **article**. Choisissez l’action **Fabrication**, action **Calculer coût standard**, puis choisissez l’action **Tous les niveaux**.  

## Pour créer des liens itinéraire

Vous pouvez créer des liens itinéraire pour lier des composantes à des opérations spécifiques et conserver leur relation, même si la nomenclature de production ou l'itinéraire sont modifiés. Les liens itinéraire simplifient également la consommation automatique juste-à-temps des composantes, à savoir lorsque l’opération liée spécifique commence, et non quand le bon de production complet est libéré. Pour en savoir plus, voir [Consommer des composantes en fonction de la production réalisée](production-how-to-flush-components-according-to-operation-output.md).  

Les composantes et opérations liées apparaissent dans une structure opératoire logique lorsque vous utilisez la page **Journal production** pour le report de la production et de la consommation, ce qui constitue un autre avantage majeur.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Itinéraires**, puis sélectionnez le lien associé.  
2. Ouvrez l'itinéraire contenant les opérations que vous voulez lier.  

    Vérifiez que le statut de la gamme est **Modification en cours**.  

3. Sur la ligne gamme appropriée, dans le champ **Code lien gamme** , sélectionnez un code.  
4. Ajoutez différents codes lien itinéraire à d’autres opérations de l'itinéraire, si nécessaire.  

    > [!NOTE]  
    > Vous ne devez pas utiliser le même code lien itinéraire dans plusieurs opérations d’un itinéraire, car vous risquez de lier de manière incorrecte une même composante à deux opérations différentes et, de ce fait, de la consommer deux fois.  
    >
    > Il peut être judicieux de nommer le code lien itinéraire en fonction de l’opération pour garantir que les liens itinéraire soient propres à chaque opération.

5. Définissez le statut de la gamme sur **Validé**.  

    Les codes lien itinéraire sont désormais affectés aux opérations. Ensuite, vous devez créer le lien réel en attribuant les mêmes codes à des composants spécifiques de la nomenclature de production appropriée.  

6. Ouvrez la **Nomenclature de production** qui contient les composantes à lier aux opérations ci-dessus. Pour en savoir plus, voir [Créer des nomenclatures de production](production-how-to-create-production-boms.md).
7. Vérifiez que le statut de la nomenclature est **Modification en cours**.  
8. Sur la ligne appropriée de nomenclature de production, dans le champ **Code lien itinéraire**, sélectionnez le code que vous avez affecté à l’opération.  
9. Ajoutez ensuite des codes lien itinéraire à d’autres composantes, selon les opérations uniques pour lesquelles ils sont utilisés.  
10. Définissez le statut de la nomenclature de production sur **Validé**.  

    > [!NOTE]  
    > Pour activer les liens itinéraire d'un bon de production existant, vous devez actualiser le bon de production. Pour en savoir plus, voir [Créer des bons de production](production-how-to-create-production-orders.md).  

Les composantes sélectionnées sont désormais liées aux opérations sélectionnées lorsque vous créez ou actualisez un bon de production à l’aide de la nomenclature de production et de l'itinéraire. Ce lien est visible sur la page **Composantes bon de production** sous le bon de production. Vous pouvez supprimer et ajouter les codes de lien de routage à tout moment.

## Pour affecter des qualifications, des outils et des contrôles qualité à des opérations itinéraire

Si vous avez besoin de personnes ayant des qualifications, un savoir-faire particulier, ou bénéficiant d'une autorisation spéciale pour une opération, vous pouvez affecter ces personnes à l'opération. En outre, vous pouvez affecter des outils et des exigences de qualité à l'opération. Cette procédure décrit l'affectation de qualifications. Les étapes sont similaires pour d'autres types d'informations sur l'opération.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Itinéraires**, puis sélectionnez le lien associé.  
2. Ouvrez l'itinéraire approprié.  
3. Sur le raccourci **Lignes**, sélectionnez la ligne à traiter, choisissez l'action **Opérations**, puis choisissez l'action **Qualifications**.  
4. Renseignez les champs de la page **Itinéraires personnels**.  
5. Cliquez sur le bouton **OK** pour quitter la page. Les valeurs saisies sont copiées et affectées à l'opération.  

## Pour créer une nouvelle version d’un itinéraire

Le principe de la version permet de gérer différentes versions d'un itinéraire. La structure d'une version d'itinéraire correspond à la structure de l'itinéraire composée d'un en-tête et de lignes version d'itinéraire. La différence de base est définie par la date début.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Itinéraires**, puis sélectionnez le lien associé.  
2. Sélectionnez l'itinéraire à copier, puis choisissez l’action **Versions**.  
3. Sur la page **Versions de l'itinéraire**, sélectionnez l'action **Nouveau**.
4. Dans le champ **Code version**, saisissez le numéro d'identification unique de la version. Vous pouvez utiliser n'importe quelle combinaison de chiffres et de lettres.  

    Le statut **Nouveau** est automatiquement affecté à la version que vous venez de créer.  
5. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]
6. Pour créer des lignes opération, sélectionnez la première ligne vide, puis renseignez le champ **N° opération** en fonction de la séquence des opérations.

    Les lignes opération sont par ordre croissant, en fonction du numéro des opérations. Afin de faciliter les modifications ultérieures, optez pour des incréments de taille adéquate. Le champ **N° opération suivante** se réfère à l'opération suivante de l'itinéraire.

7. Lorsque la configuration de la version d'itinéraire est terminée, dans le champ **État**, choisissez **Certifié**.

## Voir aussi .

[Création des nomenclatures de production](production-how-to-create-production-boms.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Fabrication](production-manage-manufacturing.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]