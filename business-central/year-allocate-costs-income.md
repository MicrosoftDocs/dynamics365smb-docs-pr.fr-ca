---
title: Aperçu des tâches de ventilation des coûts et des revenus
description: Décrit les tâches pour affecter une écriture d’un journal général récurrent dans plusieurs comptes différents lorsque vous reportez le journal.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: overview
ms.devlang: al
ms.search.form: '283, 5629'
ms.date: 02/05/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# <a name="allocate-recurring-costs-and-income"></a>Ventilation des coûts et des bénéfices récurrents

Vous pouvez affecter une écriture d’un journal général récurrent dans différents comptes lorsque vous reportez le journal. Pour en savoir plus sur les journaux généraux récurrents, consultez [Utiliser des journaux récurrents](ui-work-general-journals.md#work-with-recurring-journals). 

L'affectation peut être effectuée de trois manières différentes :

* Quantité
* Pourcentage (%)
* Montant

Les fonctions d'affectation fonctionnent avec les journaux généraux récurrents et dans les journaux immobilisation.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

Les procédures suivantes décrivent comment se préparer à affecter des coûts dans un journal général récurrent en définissant des clés d'affectation. Lorsque des clés d'affectation sont définies, vous renseignez et reportez le journal comme tout autre journal général récurrent. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

## <a name="to-set-up-allocation-keys"></a>Pour définir des clés de ventilation

Vous pouvez affecter une écriture dans un journal général récurrent dans différents comptes lorsque vous reportez le journal. L'affectation peut être effectuée par quantité, pourcentage ou montant.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général récurrent**, puis sélectionnez le lien associé.
2. Sélectionnez le champ **Nom du lot** pour ouvrir la page **Lots journal général**.
3. Vous pouvez soit modifier les ventilations sur un lot existant dans la liste ou créer un lot avec des ventilations.
   * Pour créer un lot, sélectionnez l'action **Nouveau**, et passez à l'étape suivante.
   * Pour modifier les affectations à partir d'un journal existant, sélectionnez le journal et passez à l'étape 7.    
4. Dans le champ **Nom**, saisissez le nom du lot, par exemple NETTOYAGE. Dans le champ **Description**, saisissez une description, par exemple Feuille frais de nettoyage.
5. Fermez la page lorsque vous avez terminé. Un nouveau journal récurrent vide s'ouvre.
6. Renseignez les champs de la ligne.
7. Sélectionnez l'action **Ventilations**.
8. Ajoutez une ligne pour chaque affectation. Vous devez renseigner le champ **% ventilation**, **Quantité imputée** ou **Montant**. Vous devez également renseigner le champ **N° compte** et, si vous affectez la transaction à des dimensions principales, les champs de ces dimensions principales.
9. Si vous saisissez un pourcentage dans une ligne, le montant du champ **Montant** est calculé automatiquement. Ces montants sont dotés du signe opposé à celui du montant total figurant dans le champ **Montant** de la feuille récurrente.
10. Après avoir saisi les lignes d'affectations, cliquez sur **OK** pour revenir à la page **Journal général récurrent**. Le champ **Montant imputé DS** est renseigné et correspond au champ **Montant**.
11. Reportez le journal.

## <a name="to-change-an-allocation-key-that-has-already-been-set-up"></a>Pour modifier une clé d'affectation déjà configurée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal général récurrent**, puis sélectionnez le lien associé.
2. Sur la page **Journal général récurrent**, sélectionnez le journal contenant l'affectation.
3. Sélectionnez la ligne de l'affectation, puis choisissez l’action **Affectations**.
4. Modifiez les champs appropriés, puis choisissez **OK**.

## <a name="see-also"></a>Voir aussi .

[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)    
[Validation des documents et des feuilles](ui-post-documents-journals.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
