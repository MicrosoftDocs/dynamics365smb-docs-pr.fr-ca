---
title: Vente d'articles à assembler pour commande
description: Découvrez comment vendre un article qui est assemblé pour commande.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 11/23/2022
ms.search.keywords: 'kit, kitting, substitute items'
ms.search.form: '900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905'
ms.custom: bap-template
---
# <a name="sell-items-assembled-to-order" />Vente d'articles à assembler pour commande

Les articles paramétrés pour assembler pour commande ne devraient pas être en inventaire, et seront assemblés une fois inclus dans un document de vente. Un article est configuré pour assembler sur commande quand le champ **Politique d’assemblage** sur la fiche article contient **Assembler pour commande**. Quand vous entrez l’article sur une ligne document de vente, un ordre d’assemblage est automatiquement créé et lié au document de vente.  

> [!NOTE]  
> Si des articles à assembler pour commande sont déjà en inventaire, vous pouvez déduire cette quantité de l’ordre d’assemblage et la réserver dans l'inventaire. Pour en savoir plus, voir [Vente d’articles en inventaire dans des flux à assembler pour commande](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

Dans cette procédure, vous effectuez la vente d'un article que vous assemblez selon les spécifications qui sont demandées par le client. Les mesures incluent : 

* Création d’une ligne document de vente.
* Personnalisation de l’élément d’assemblage en modifiant ses composantes et ses ressources.
* Vérification de la disponibilité pour établir une date de livraison.
* Libération du document de vente à assembler et à livrer immédiatement.  

> [!NOTE]  
> La procédure suivante n’inclut pas les étapes de création d’un document de vente standard ayant lieu avant l’étape où vous entrez l’article à assembler pour commande dans une ligne document de vente. Pour en savoir plus sur la création de documents de vente, voir [Vendre des produits avec un document de vente client](sales-how-sell-products.md).  

## <a name="to-sell-an-item-that-is-assembled-to-order" />Vendre un article qui est assemblé pour commande

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Créez un document de vente. 
3. Dans le champ **N°**, , entrez un article qui est configuré pour l'assemblage pour commande.  
4. Dans le champ **Code magasin**, définissez le magasin à partir duquel l'article sera vendu. Le processus d'assemblage a lieu à cet emplacement.  
5. Dans le champ **Quantité**, entrez le nombre d'unités à vendre.  

    > [!NOTE]  
    >  Si une ou plusieurs composantes de la quantité d’éléments d’assemblage demandée ne sont pas disponibles, une page d’avertissement de disponibilité s’ouvre. <!-- Check whether the field help would be useful. For more information, see Assembly Availability.  -->

    Un ordre d’assemblage est créé et est lié à la ligne document de vente. La date d’échéance de l’ordre d’assemblage est la date de livraison de la ligne document de vente.  

    La quantité à vendre est copiée dans le champ **Quantité à assembler pour commande**, ce qui indique que d’après la configuration vous assemblerez la quantité totale de la ligne vente. Vous pouvez réduire la quantité à assembler, par exemple si vous savez que certains articles sont déjà disponibles. Pour en savoir plus, voir [Vente d’articles en inventaire dans des flux à assembler pour commande](assembly-how-to-sell-inventory-items-in-assemble-to-order-flows.md).  

6. Si le client souhaite un article supplémentaire dans un kit, sur le raccourci **Lignes**, sélectionnez l’action **Ligne**, sélectionnez l’action **Assembler pour commande**, puis sélectionnez l’action **Lignes d’assemblage pour commande** pour visualiser et modifier les composantes d’assemblage standard. Sinon, choisissez le champ **Quantité à assembler pour commande**.  
7. Sur la page **Lignes d’assemblage pour commande**, créez une nouvelle ligne de type **Article** pour la composante d’assemblage supplémentaire.  

    Vous pouvez également personnaliser la commande en augmentant la quantité d’un article standard dans le kit. Vous pouvez effectuer cette opération en augmentant la valeur du champ **Quantité par** de la ligne d'ordre d'assemblage spécifique.  

    > [!NOTE]  
    >  La page **Lignes d’assemblage pour commande** contient seulement les champs de base pour personnaliser la liste des composantes, ajouter des numéros de traçabilité ou résoudre des problèmes de disponibilité des composantes. Pour ajouter plus d’informations en matière d’ordre d’assemblage, telles que la date de début de l’ordre d’assemblage, choisissez l’action **Afficher documents**. Ceci ouvre l'affichage complet de l'ordre d'assemblage lié à la ligne document de vente. Vous ne pouvez pas modifier le contenu de la plupart des champs de l’en-tête de l’ordre d’assemblage et vous ne pouvez pas en reporter le résultat d’assemblage. Vous devez reporter la livraison de la ligne document de vente.  
    >
    >  Sur les ordres d’assemblage liés, seul le champ **Date début** peut être modifié. La modification de la date début permet aux ouvriers de l’assemblage de spécifier qu’ils commencent l’assemblage avant la date d’échéance. Tous les champs des lignes de l'ordre d'assemblage associé peuvent être modifiés afin que les magasiniers puissent entrer les chiffres de consommation pendant le processus.  

8. Examinez les problèmes de disponibilité des composantes ou réagissez face à eux. Par exemple, sélectionnez un article de substitution.  
9. Fermez la page **Lignes d'assemblage pour commande**. L’ordre d’assemblage lié est prêt à commencer et les collaborateurs peuvent commencer à assembler les articles personnalisés.  
10. Sur le document de vente, choisissez l'action **Libérer** pour informer le département d’assemblage que le processus d’assemblage peut démarrer. En savoir plus sur [Assembler les articles](assembly-how-to-assemble-items.md).  

> [!NOTE]  
> Les substitutions d’articles n’entraînent pas automatiquement le remplacement d’un article par un autre, par exemple pendant la création d’un document de vente ou dans une nomenclature. Au lieu de cela, vous serez alerté du fait qu’un substitut est disponible.

## <a name="see-related-microsoft-trainingtrainingmodulesassemble-to-order-dynamics--business-central" />Voir la [formation Microsoft](/training/modules/assemble-to-order-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Gestion d'assemblage](assembly-assemble-items.md)  
[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
