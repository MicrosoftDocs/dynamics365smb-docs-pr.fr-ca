---
title: Réévaluer les immobilisations
description: 'Apprenez comment ajuster la valeur des immobilisations, en enregistrant de nouveaux montants comme dépréciation ou appréciation, et reporter les autres coûts d’acquisition.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: conceptual
ms.search.form: '5628, 5629, 5633'
ms.date: 02/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# Réévaluation des immobilisations

La réévaluation des immobilisations peut consister en réévaluations, dépréciations ou corrections de valeurs générales.

Lorsque la valeur d’une immobilisation augmente, vous reportez une ligne journal avec une appréciation, dans le registre amortissement. Le nouveau montant est enregistré comme appréciation selon la configuration du report immobilisation.

Lorsque la valeur d’une immobilisation diminue, vous reportez une ligne journal avec un montant inférieur, une dépréciation, dans le registre amortissement. Le nouveau montant est enregistré comme dépréciation selon la configuration du report immobilisation.

L'actualisation permet d'ajuster plusieurs valeurs immobilisation, par exemple, en fonction de modifications générales de niveau de prix. Le traitement par lots **Réévaluer immobilisations** permet de modifier divers montants, tels que les montants de dépréciation et de réévaluation.

## Pour reporter une appréciation à partir du journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  
2. Créez une ligne journal initiale et complétez les champs, le cas échéant.
3. Dans le champ **Type compta. immo**, sélectionnez **Réévaluation**.
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de l'appréciation.

    > [!NOTE]  
    >   L'étape 4 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** du groupe de report de l'immobilisation, le champ **Compte appréciation** contient le compte débit GL et le champ **Compte contrepartie appréciation** contient le compte GL dans lequel vous souhaitez reporter les écritures contrepartie pour appréciation. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  
5. Sélectionnez l'action **Reporter**.

## Pour reporter une dépréciation à partir du journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  
2. Créez une ligne journal initiale et complétez les champs, le cas échéant.
3. Dans le champ **Type compta. immo**, sélectionnez **Dépréciation**.
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de la dépréciation.

    > [!NOTE]  
    >   L'étape 4 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** pour le groupe de report de l'immobilisation, le champ **Compte dépréciation** contient le compte crédit du grand livre et le champ **Compte dépense dépréciation** contient le compte débit du grand livre dans lequel vous souhaitez reporter les écritures contrepartie pour dépréciation. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
5. Sélectionnez l'action **Reporter**.

## Pour exécuter une réévaluation générale des immobilisations

L'actualisation permet d'ajuster plusieurs valeurs immobilisation, par exemple, en fonction de modifications générales de niveau de prix. Le traitement par lots **Réévaluer immobilisations** permet de modifier divers montants, tels que les montants de dépréciation et de réévaluation. La case **Autoriser indexation** sur la page **Registre amortissement** doit être cochée.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Actualiser immobilisations**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **OK**.

    Les lignes de réévaluation sont créées conformément à vos paramètres à l'étape 2. Les lignes sont créées dans le journal immobilisation ou le journal GL immobilisation., selon votre modèle et la configuration par lot sur la page **Configuration journal immo.**. Pour en savoir plus, voir [Configurer des informations générales sur les immobilisations](fa-how-setup-general.md).
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  
5. Sélectionnez la feuille avec les immobilisations que vous souhaitez réévaluer, puis sélectionnez l'action **Écritures comptables**.  
6. Vérifiez les écritures créées, puis sélectionnez l'action **Valider** pour valider la feuille.

    > [!TIP]  
    >   Si les taux de réévaluation sont définis uniquement pour une simulation, vous pouvez créer un registre amortissement spécifique pour les stocker. Ainsi, ces écritures n'affectent aucune autre loi d'amortissement.

## Pour reporter les autres coûts d’acquisition

Vous pouvez reporter d’autres coûts d’acquisition d’une immobilisation à partir d’une facture achat ou d’un journal immobilisation de la même manière que vous reportez le coût d’acquisition d’origine. Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).  

Si l’amortissement de l’immobilisation est calculé, cochez la case **Amortir coût acquisition** pour que le résultat du autre coût d’acquisition moins la valeur résiduelle soit amorti proportionnellement au montant de l’amortissement de l’immobilisation précédemment acquise. Cette méthode garantit l’invariabilité de la période d’amortissement.  

Le pourcentage d'amortissement est calculé comme suit :  

*P = (amortissement total x 100)/base amortissement*

*Montant de l'amortissement = (P/100) x (coût d'acquisition supplémentaire - valeur résiduelle)*  

Pensez à cocher la case **Amort. jusqu’à date de report** sur les lignes de la facture, du journal GL immobilisation ou du journal immobilisation pour que le programme calcule l’amortissement à partir de la date report de l’immobilisation jusqu’à la date report de l’autre coût d’acquisition.

### Exemple - Report des autres coûts d’acquisition

Vous achetez une machine le 1er août 2000. Son coût d'acquisition est de 4 800. La méthode d'amortissement est linéaire sur quatre années.

Le 31 août 2000, le traitement par lots **Calculer amortissement** est exécuté. L'amortissement est calculé comme suit :

*valeur comptable x nombre jours d'amortissement / nombre total de jours d'amortissement = 4 800 x 30 / 1 440 = 100*  

Le 15 septembre 2000, une facture de peinture est reportée pour la machine. Le montant de cette facture est de 480.

Si vous avez coché la case **Amort. jusqu’à date de report** sur la facture avant le report, le calcul suivant est effectué :  

15 jours d'amortissement (du 01/09/00 au 15/09/00) calculés comme suit :

*valeur comptable x nombre jours d'amortissement / nombre restant de jours d'amortissement = (4 800 - 100) x 15 / 1 410 = 50*

Si vous avez coché la case **Amortir coût acquisition** sur la facture avant que cette dernière soit reportée, le calcul suivant est effectué :  

*Le autre coût d’acquisition est amorti de ((150 x 100) / 4 800) / 100 x 480 = 15*

La base d'amortissement est maintenant égale à *5 280 = (4 800 + 480)* et l'amortissement cumulé équivaut à *165 = (100 + 50 + 15)*, soit 45 jours d'amortissement du coût d'acquisition total. Ce calcul signifie que l'immobilisation sera totalement amortie au cours de sa durée de vie estimée à quatre ans.  

Lorsque le traitement par lots **Calculer amortissement** est exécuté le 30/09/00, le calcul suivant est utilisé :  

*Durée d’amortissement restante : 3 ans, 10 mois et 15 jours = 1 395 jours*  

*Valeur comptable : (5 280 - 165) = 5 115*  

*Montant de l'amortissement pour septembre 2 000 : 5 115 x 15 / 1 395 = 55,00*  

*Amortissement total = 165 + 55 = 220*  

Si vous n’avez pas coché la case **Amort. jusqu’à date de report**, l’actif perdrait 15 jours d’amortissement, car le traitement en lot **Calculer amortissement** exécuté le 30/09/00 calculerait l’amortissement du 15/09/00 au 30/09/00. , l'immobilisation perd 15 jours d'amortissement car le traitement par lots **Calculer amortissement** exécuté le 30/09/00 calcule l'amortissement du 15/09/00 au 30/09/00 comme suit :  

*Durée de vie restante : 3 ans, 10 mois et 15 jours = 1 395 jours*  

*Valeur comptable : (4 800 + 480 - 100 - 15) = 5 165*

*Montant de l'amortissement pour septembre 2 000 : 5 165 * 15 / 1 395 = 55,54*  

*Amortissement total = 100 + 15 + 55,54 = 170,54*

## Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
