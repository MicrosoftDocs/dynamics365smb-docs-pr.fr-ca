---
title: Affecter les revenus et les coûts à plusieurs comptes GL
description: Découvrez comment affecter des coûts à un ou plusieurs comptes dans votre grand livre.
author: brentholtorf
ms.author: bholtorf
ms.date: 09/04/2023
ms.topic: conceptual
ms.search.keywords: 'allocate, allocation, accounts'
ms.search.form: '39, 2673, 2670, 2674,'
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="allocate-revenue-and-costs-to-multiple-general-ledger-accounts"></a>Affecter les revenus et les coûts à plusieurs comptes GL

Cet article décrit comment utiliser les comptes d'affectation pour répartir les montants des documents vente et achat et des lignes journal général entre différents comptes du grand livre. Vous pouvez ventiler les montants via une répartition fixe ou variable.  

L'affectation divise une ligne journal général en lignes définies sur la page **Compte d'affectation**. Par exemple, si vous divisez une dépense de loyer de trois manières à l’aide de dimensions, vous disposez de trois lignes à reporter pour l'affectation. Par conséquent, vous disposez de six lignes GL (ou éventuellement plus si vous utilisez la TVA ou la taxe de vente). Bien que cela reporte plus d’écritures GL que ce dont vous pourriez avoir besoin, cela vous permet d'inverser des lignes individuelles au lieu d'inverser toute l'affectation.

Les comptes d'affectation fonctionnent également avec les échelonnements. Pour en savoir plus sur les échelonnements, consultez [Échelonner les revenus et les dépenses](finance-how-defer-revenue-expenses.md).

Le tableau suivant présente les méthodes d'affectation que vous pouvez utiliser.

|Mode de répartition  |Désignation  |
|---------|---------|
|Corrigé     | Lorsque vous souhaitez diviser les dépenses de manière répétée sur une période plus longue, vous pouvez utiliser une affectation fixe. Une affectation fixe vous permet de définir la division de l'affectation. Cette répartition ne change que lorsque vous modifiez la configuration sur la page **Compte d'affectation**.        |
|Variable     | Pour répartir les revenus ou les dépenses en fonction de valeurs qui changent dans le temps, utilisez la méthode d'affectation variable. Les affectations variables vous permettent de spécifier les sources à utiliser pour calculer les pourcentages d'affectation. Cette méthode est utile, par exemple, pour répartir les coûts du personnel en fonction des effectifs variables dans un département ou une division. Un autre exemple est la répartition du coût du loyer en fonction de la superficie de l’atelier de production, qui peut varier selon la ligne de production au fil du temps. Les affectations variables utilisent une combinaison de dimensions et de comptes statistiques pour déterminer la manière dont les montants sont répartis sur une période donnée. Pour en savoir plus sur les comptes statistiques, consultez [Analyser les données avec les comptes statistiques](bi-use-statistical-accounts.md). Pour en savoir plus sur les dimensions, consultez [Utiliser les dimensions](finance-dimensions.md).        |

## <a name="use-a-fixed-share-or-percentage-method-to-allocate-amounts"></a>Utiliser une méthode de partage ou de pourcentage fixe pour ventiler les montants

1. Choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Compte d'affectation**, puis choisissez le lien associé.  
1. Sur la page **Comptes d'affectation**, choisissez **Nouveau**.
1. Renseignez le champ **N°** et **Nom**.
1. Dans le champ **Type compte**, choisissez **Fixe**.
1. Dans le champ **Type du compte de destination**, choisissez **Compte du grand livre** ou **Compte bancaire**.
1. Dans le champ **Numéro du compte de destination**, choisissez le compte sur lequel reporter la valeur.
1. Facultatif : choisissez l’action **Dimensions**, puis spécifiez les dimensions à reporter pour la ligne.
1. Dans les champs **Partager** et **Pourcentage**, spécifiez comment répartir les montants sur le compte de destination.
  
   > [!TIP]
   > Si vous saisissez le montant réel à affecter pour une affectation fixe dans le champ **Partager**, le champ **Pourcentage** affiche le pourcentage du montant total.
1. Répétez ce processus pour chaque compte à inclure dans l'affectation.

## <a name="use-a-variable-method-to-allocate-amounts"></a>Utiliser une méthode variable pour ventiler les montants

1. Choisissez l’icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Compte d'affectation**, puis choisissez le lien associé.  
1. Sur la page **Comptes d'affectation**, choisissez **Nouveau**.
1. Renseignez le champ **N°** et **Nom**.
1. Dans le champ **Type compte**, choisissez **Variable**.
1. Dans le champ **Type du compte de destination**, choisissez **Compte du grand livre**.
1. Dans le champ **Numéro du compte de destination**, choisissez le compte sur lequel reporter la valeur.
1. Dans le champ **Type du compte de ventilation**, choisissez **Compte statistique**.
1. Dans le champ **Période de calcul**, choisissez la période pour laquelle répartir les montants.
1. Facultatif : pour filtrer des valeurs de dimension globales spécifiques, choisissez l’action **Filtres du solde du compte de ventilation**, puis spécifiez les valeurs de filtre.
1. Facultatif : choisissez l’action **Dimensions**, puis spécifiez les dimensions à reporter pour la ligne.

## <a name="allocate-amounts-on-the-fly"></a>Ventiler les montants à la volée

Vous créez des comptes d'affectation pour répartir les revenus et les coûts pour les comptes du grand livre et les comptes bancaires. L’automatisation de l'affectation peut vous faire gagner du temps. Toutefois, si vous souhaitez utiliser des comptes d'affectation, mais ne souhaitez pas les créer pour chaque compte du grand livre, vous pouvez gagner encore plus de temps.

L’option Copier à partir du parent vous permet d’utiliser le compte d'affectation pour répartir les montants de tout compte du grand livre sur une ligne d’un document ou d’un journal. Dans le champ **Type de compte** d’une ligne document ou journal, vous choisissez un compte du grand livre, puis choisissez le compte d'affectation dans le champ **N° du compte d'affectation**. Le montant de la ligne est réparti pour le compte du grand livre selon la configuration dans votre compte d'affectation. Il s’agit d’une méthode d'affectation moins transparente, mais il n’est pas nécessaire de créer un compte d'affectation spécifiquement pour le compte du grand livre.

Les affectations ad hoc sont faciles à configurer. Au lieu de spécifier un compte bancaire ou général dans le champ **Type du compte de destination** de la page **Compte d'affectation**, choisissez l’option **Copier à partir du parent**. Laissez le champ **Numéro du compte de destination** vide. Lorsque vous choisissez le compte du grand livre sur la ligne document ou journal, ce compte est utilisé pour ventiler les montants.

## <a name="verify-that-amounts-distribute-correctly-before-you-post-them"></a>Vérifier que les montants sont correctement répartis avant de les reporter

Il existe plusieurs façons de vérifier que les montants sont correctement répartis :

* Sur la page **Compte d'affectation**, choisissez l’action **Tester l'affectation**. Utilisez le champ **Montant à ventiler** pour tester différents montants.
* Sur la page **Journaux grand livre**, choisissez le journal et utilisez l’action **Aperçu report**.

## <a name="adjust-the-distribution"></a>Ajuster la répartition

Si vous trouvez quelque chose dans une affectation que vous souhaitez modifier, vous pouvez ajuster l'affectation avant de la reporter.  

1. Ouvrez le document ou le journal contenant l'affectation que vous souhaitez modifier.
1. Choisissez la ligne, puis choisissez l’action **Répartir à nouveau les affectations du compte**.
1. Sur la page **Modifier les affectations**, effectuez votre ajustement.

## <a name="post-an-allocation-transaction"></a>Reporter une transaction d'affectation

Les étapes suivantes décrivent comment reporter une transaction d'affectation à partir d’un journal général. Les étapes sont les mêmes pour les documents vente et achat.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.  
1. Créez une ligne. Remplissez les champs de la même manière que vous le feriez pour tout autre type de journal général.
1. Si vous utilisez une affectation fixe ou variable, remplissez les champs suivants :
    1. Dans le champ **Type compte**, choisissez **Compte d'affectation**.
    1. Dans le champ **N° compte**, choisissez le compte d'affectation.
1. Si vous utilisez une affectation qui utilise l’option Copier à partir du parent, procédez comme suit :
    1. Dans le champ **Type de compte**, choisissez **Compte du grand livre**.
    1. Dans le champ **N° compte**, choisissez le compte du grand livre.
    1. Dans le champ **N° du compte d'affectation**, choisissez le compte d'affectation configuré pour utiliser l’option Copier à partir du parent. 
1. Choisissez **Reporter**.

## <a name="see-also"></a>Voir aussi

[Utiliser des journaux généraux](ui-work-general-journals.md)  
