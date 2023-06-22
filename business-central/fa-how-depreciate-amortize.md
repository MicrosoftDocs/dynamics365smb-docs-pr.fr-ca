---
title: Déprécier ou amortir des immobilisations
description: 'Vous devez définir comment vous allez déprécier ou amortir chacune de vos immobilisations, telles que les machines et l’équipement, tout au long de leur durée d’amortissement.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: write down
ms.search.form: '5610, 5611, 5629, 5633, 5659, 5660, 5663, 5619, 5666'
ms.date: 06/15/2021
ms.author: edupont
---
# <a name="depreciate-or-amortize-fixed-assets" />Amortir des immobilisations

L'amortissement permet de ventiler le coût des immobilisations, telles que les machines et le matériel, sur leur durée d'amortissement. Vous devez définir la méthode d'amortissement de chaque immobilisation.  

 Vous pouvez reporter l'amortissement de deux manières :  

* Automatiquement, via l'exécution du traitement par lots **Calculer amortissement**.  
* Manuellement, à l'aide du journal GL immobilisation.  

[!INCLUDE[prod_short](includes/prod_short.md)] peut calculer l'amortissement sur une base quotidienne, ce qui vous permet de calculer l'amortissement pour n'importe quelle période. Vous pouvez ainsi analyser les résultats d'exploitation en cours sur une période mensuelle, trimestrielle ou annuelle. Le calcul utilise une année standard de 360 jours et un mois standard de 30 jours. Pour en savoir plus, voir [Méthodes d'amortissement](fa-depreciation-methods.md).  

Lorsque plusieurs départements utilisent une immobilisation, vous pouvez affecter automatiquement un amortissement périodique à ces départements d'après une table d'affectation paramétrable.  

Vous pouvez annuler des écritures d'amortissement incorrectes à l'aide du traitement par lots **Annuler écriture comptable immo**. Ensuite, vous pouvez valider le montant correct en exécutant de nouveau le traitement par lots **Calculer amortissement**. Les erreurs que vous résolvez sont reportées en tant qu'écritures erreur immobilisation.  

L'actualisation permet d'ajuster des valeurs en fonction de modifications générales de niveau de prix. Vous pouvez utiliser le traitement par lots **Actualiser immobilisation** pour recalculer les montants des amortissements.  

## <a name="to-calculate-depreciation-automatically" />Pour calculer automatiquement des amortissements

Une fois par mois, ou à la fréquence de votre choix, vous pouvez lancer le traitement par lots **Calculer amortissement**. Le traitement en lot ignore les immobilisations qui ont été vendues, celles qui ont été bloquées ou qui sont inactives, et celles qui utilisent la méthode d'amortissement manuelle.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Calculer amortissement**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Cliquez sur le bouton **OK**.  

    Le traitement en lot calcule l'amortissement et crée des lignes dans le journal GL immobilisation.

4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  

    Sur la page **Journal GL immobilisation**, dans le champ **Nbre jours amort.**, vous pouvez voir le nombre de jours d'amortissement calculé.  
5. Sélectionnez l'action **Reporter**.  

> [!NOTE]
> Limitations connues : si vous définissez le champ **Utiliser Forcer nombre de jours** sur Oui, et que le champ **Forcer nombre de jours** est défini sur une valeur où la **Date de report** moins le **Nombre de jours** a pour résultat une date appartenant à l’année calendaire précédente, le système ne vous permettra pas de reporter l’amortissement.
> Vous pouvez éviter cela en réduisant le champ **Forcer nombre de jours** sur une valeur inférieure au nombre de jours calculés jusqu’à la date de report en utilisant 30 jours/mois OU en définissant l’indicateur **Exercice financier 365 jours** dans le registre amortissement.
> Nous recommandons la première option, car vous ne voudrez peut-être pas modifier l’utilisation de 30 jours/mois pour l’amortissement. Pour plus d’informations, consultez la section [Amortissement via le champ Exercice financier 365 jours](fa-how-setup-depreciation.md#fiscal-year-365-days-field-depreciation).


## <a name="to-post-depreciation-manually-from-the-fixed-asset-gl-journal" />Pour reporter un amortissement manuellement à partir du journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal GL immobilisation**, puis choisissez le lien associé.  
2. Créez une ligne journal initiale et complétez les champs, le cas échéant.  
3. Dans le champ **Type compta. immo**, sélectionnez **Amortissement**.  
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de l'amortissement. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
5. Choisissez l'action **Reporter** pour reporter le journal.  

Le champ **Valeur comptable** dans la page **Fiche immobilisation** est mis à jour en conséquence.

Si vous avez configuré des clés d'affectation immobilisation pour affecter des montants entre plusieurs départements ou plusieurs projets, les montants sont affectés lors du report. Pour en savoir plus, voir [Configurer des informations générales sur les immobilisations](fa-how-setup-general.md).  

## <a name="to-manage-the-ending-book-value" />Pour gérer la valeur comptable finale

Dans le champ **Valeur comptable finale** de la page **Registres amortissement immo.**, vous pouvez spécifier la valeur comptable de votre immobilisation dans le registre amortissement actuel une fois qu'elle a été entièrement amortie. Vous pouvez le faire manuellement ou vous pouvez renseigner le champ **Valeur comptable finale par défaut** dans la page **Registre amortissement**, qui est ensuite utilisée pour renseigner automatiquement le champ.

> [!NOTE]
> Si le dernier amortissement entraîne une valeur comptable inférieure à zéro dans le champ **Valeur comptable** de la page **Fiche immobilisation**, ce montant est automatiquement soustrait du dernier amortissement.<br /><br />
> Si la valeur du champ **Valeur comptable** est supérieure à zéro après le dernier amortissement, par exemple à cause d'un arrondissement ou d'une valeur résiduelle, la valeur du champ **Valeur comptable finale** dans la page **Registres amortissement immo.** est ignorée. Pour plus d'informations, voir [Pour reporter la valeur résiduelle avec le coût d'acquisition](fa-how-acquire.md#to-post-the-salvage-value-together-with-the-acquisition-cost).

## <a name="to-calculate-allocations-in-the-fixed-asset-gl-journal" />Pour calculer les affectations dans le journal GL immobilisation

Lorsqu'une immobilisation est utilisée par plusieurs départements, vous pouvez affecter automatiquement un amortissement périodique à ces départements d'après une table d'affectation paramétrable.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal GL immobilisation**, puis choisissez le lien associé.  
2. Créez une feuille initiale et complétez les champs, le cas échéant.
3. Dans le champ **Type compta. immo**, sélectionnez **Ventilation**.  
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de l'affectation.  
5. Choisissez l'action **Reporter** pour reporter le journal.  

## <a name="use-duplication-lists-to-prepare-to-post-to-multiple-depreciation-books" />Utilisez les listes de duplication pour préparer le report vers plusieurs registres amortissement

Lorsque vous renseignez les lignes journal à reporter dans un registre amortissement, vous pouvez dupliquer les lignes dans un autre journal afin de pouvoir reporter dans un autre registre amortissement. Pour en savoir plus, voir [Pour reporter des écritures vers différents registres amortissement](fa-how-depreciate-amortize.md#to-post-entries-to-different-depreciation-books).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Registres amortissement**, puis choisissez le lien associé.  
2. Ouvrez la loi d'amortissement, puis cochez la case **Inclure dans liste duplication**.  

> [!IMPORTANT]  
>   Si le champ **Utiliser liste duplication** est sélectionné, n'utilisez pas de souches de numéros sur la feuille. En effet, les séries de numéros pour le journal GL immobilisation ne correspondent pas aux séries pour le journal immobilisation.  

## <a name="to-post-entries-to-different-depreciation-books" />Pour reporter des écritures dans plusieurs registres amortissement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal GL immobilisation**, puis choisissez le lien associé.  
2. Dans la feuille avec laquelle vous souhaitez valider l'amortissement, sélectionnez la case **Utiliser liste duplication**.  
3. Renseignez les champs restants selon vos besoins.  
4. Sélectionnez l'action **Reporter**.  
5. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux immobilisation**, puis choisissez le lien associé.  

    > [!NOTE]  
    >   La page **Journal immobilisation** contient de nouvelles lignes pour différents registres amortissement selon la liste de duplication.  
6. Examinez ou modifiez les lignes, puis sélectionnez l'action **Valider**.  

    > [!NOTE]  
    >   Pour dupliquer une écriture dans une autre loi, vous pouvez également saisir un code loi d'amortissement dans le champ **Dupliquer dans journaux amort.** lorsque vous renseignez une ligne feuille.  

Vous pouvez copier des écritures d'une loi d'amortissement vers une autre à l'aide du traitement par lots **Copier lois d'amortissement**. Le traitement en lot crée des lignes journal dans le journal que vous avez spécifié sur la page **Configuration journal immo.** pour le registre amortissement vers lequel vous souhaitez réaliser la copie. Pour plus d'informations, voir la procédure suivante.  

## <a name="to-copy-fixed-asset-ledger-entries-between-depreciation-books" />Pour copier des écritures immobilisations entre les registres amortissement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Registres amortissement**, puis choisissez le lien associé.  
2. Ouvrez la fiche loi d'amortissement pertinente, puis sélectionnez l'action **Copier loi d'amortissement**.  
3. Sur la page **Copier loi d'amortissement**, renseignez les champs comme nécessaire.  
4. Cliquez sur le bouton **OK**.  

Les lignes copiées sont créées dans le journal GL immobilisation ou le journal immobilisation, selon que le registre amortissement que vous copiez a été intégrée dans le grand livre ou non.  

## <a name="see-related-microsoft-trainingtrainingmodulescalculate-post-depreciations" />Voir la [formation Microsoft](/training/modules/calculate-post-depreciations/) associée

## <a name="see-also" />Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
