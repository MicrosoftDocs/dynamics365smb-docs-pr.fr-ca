---
title: Acquérir des immobilisations
description: 'Vous pouvez configurer une immobilisation, attribuer un registre amortissement et enregistrer le coût d''acquisition de l''immobilisation.'
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: purchase fixed asset
ms.search.form: '5605, 5551, 5600, 5628, 5629, 5633'
ms.date: 12/03/2021
ms.author: edupont
---
# <a name="acquire-fixed-assets"></a>Acquérir des immobilisations

Pour chaque immobilisation, vous devez créer une fiche contenant des informations la concernant. Vous pouvez configurer des bâtiments ou un équipement de production en tant qu'immobilisation principale avec une liste de composantes et vous pouvez les regrouper de différentes façons, comme par catégorie, département ou emplacement. Un registre amortissement doit être configuré et assigné à chaque immobilisation avant que vous puissiez l'acquérir.

Lorsqu'une immobilisation est configurée et qu'un registre amortissement est attribué, vous devez acquérir l'immobilisation. Pour acquérir une immobilisation, vous enregistrez son coût d'acquisition dans le compte du grand livre, le compte bancaire ou le fournisseur pertinent en reportant une transaction d'acquisition à partir de la page **Journal GL immobilisation**. Vous pouvez utiliser la page **Acquisition d'immobilisation assistée** pour créer et reporter automatiquement les lignes journal général requises.

La valeur résiduelle est la valeur restante d'une immobilisation qui est devenue inutilisable. Vous pouvez reporter la valeur résiduelle lors du report du coût d'acquisition. Pour en savoir plus, voir [Amortir des immobilisations](fa-how-depreciate-amortize.md).

L'actualisation permet d'ajuster des valeurs en fonction de modifications générales de niveau de prix. Le traitement par lots **Réévaluer immobilisations** permet de calculer les coûts d'acquisition à des coûts de remplacement.

## <a name="to-create-a-fixed-asset-and-acquire-it-automatically"></a>Pour créer une immobilisation et l'acquérir automatiquement

La procédure suivante décrit comment créer une immobilisation, puis l'acquérir via la page **Acquisition d'immobilisation assistée** pour créer et reporter les lignes journal GL immobilisation requises. Vous pouvez également créer et reporter les lignes journal manuellement. Pour en savoir plus, voir [Pour reporter manuellement une acquisition immobilisation avec le journal GL immobilisation](fa-how-acquire.md#to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**, puis renseignez les champs du raccourci **Général**, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Sur le raccourci **Loi d'amortissement**, renseignez les champs, le cas échéant. Cette étape attribue un registre amortissement à l'immobilisation.  
4. Si vous devez assigner plusieurs registres amortissement à l'immobilisation, sélectionnez l'action **Ajouter d'autres registres amortissement**. Pour en savoir plus, voir [Pour attribuer une loi d'amortissement à une immobilisation](fa-how-setup-depreciation.md#to-assign-a-depreciation-book-to-a-fixed-asset).

    Lorsque tous les champs obligatoires pour acquérir une immobilisation sont complétés, la notification **Vous êtes sur le point d'acquérir l'immobilisation. Acquérir** s'affiche en haut de la page.
5. Sélectionnez l'action **Acquérir** dans la notification.
6. Suivez les étapes sur la page **Acquisition d'immobilisation assistée** pour terminer l'acquisition automatique de l'immobilisation.

> [!NOTE]  
>   Vous pouvez également reporter le coût d'acquisition en tant que crédit. Dans ce cas, n'oubliez pas que la valeur du champ **Coût d'acquisition TVA incluse** doit comporter un signe moins pour indiquer un avoir.

Lorsque vous sélectionnez **Terminer**, le champ **Valeur comptable** de la page **Fiche immobilisation** est renseigné, indiquant que l'immobilisation a été acquise au coût d'acquisition spécifié.  

## <a name="to-set-up-a-component-list-for-a-main-asset"></a>Pour configurer une liste de composantes pour une immobilisation principale

Vous pouvez regrouper les immobilisations en immobilisations principales divisées en composants. Par exemple, si vous disposez d'une machine de production composée de différentes pièces, vous pouvez regrouper ces pièces de cette manière.  

Vous devez définir à la fois l'immobilisation principale et ses composants en tant que fiches immobilisation individuelles. Une fois la liste de composants créée, [!INCLUDE[prod_short](includes/prod_short.md)] renseigne automatiquement les champs **Immo. principale/Composant** et **Composant immo. principale** sur les fiches immobilisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation principale, puis l'action **Composants immo. principale**.
3. Sur la page **Composantes immo. principale**, choisissez **N° immo.**., puis sélectionnez l'immobilisation que vous souhaitez ajouter comme composante de l'immobilisation principale.
4. Fermez la page.
5. Répétez les étapes 3 et 4 pour chaque composante de l'immobilisation que vous souhaitez ajouter.
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration immobilisations**, puis choisissez le lien associé.
7. Cochez la case **Compta. immo. princip.**.

## <a name="to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal"></a>Pour reporter manuellement une acquisition immobilisation avec le journal GL immobilisation

La procédure suivante décrit comment acquérir manuellement une immobilisation en créant et en reportant des lignes sur la page **Journal GL immobilisation**. Vous pouvez également acquérir automatiquement une immobilisation via la page **Acquisition d'immobilisation assistée**. Pour en savoir plus, voir l'étape 5 de [Pour créer une immobilisation et l'acquérir automatiquement](fa-how-acquire.md#to-create-a-fixed-asset-and-acquire-it-automatically).

> [!NOTE]  
>   Vous pouvez également reporter le coût d'acquisition en tant que crédit. Dans ce cas, n'oubliez pas que la valeur du champ **Montant** doit comporter un signe moins pour indiquer un avoir.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.
2. Sur la page **Journal GL immobilisation**, dans le champ **Type report immo.**, sélectionnez **Coût acquisition**.
3. Renseignez les champs restants selon vos besoins.
4. Sélectionnez l'action **Valider**.  

> [!TIP]  
>   Si vous renseignez le champ **N° assurance** dans le journal GL immobilisation lorsque vous reportez un coût d'acquisition, [!INCLUDE[prod_short](includes/prod_short.md)] valide également le coût d'acquisition de l'immobilisation dans le livre couverture d'assurance. Pour en savoir plus, voir [Assurer des immobilisations](fa-how-insure.md).

## <a name="to-cancel-an-acquisition-cost-posting-for-one-fixed-asset"></a>Pour annuler le report du coût d'une acquisition pour une immobilisation

Si vous faites une erreur lors de la validation d'un coût d'acquisition, vous pouvez supprimer l'écriture à l'aide du traitement par lots **Annuler écritures immo**, puis valider l'écriture d'acquisition correcte. Les écritures erronées sont transférées vers la page **Erreur écritures immo.**.

Par exemple, si vous reportez une acquisition avec une date erronée, vous devez la corriger dès que possible, car la date de report de l’immobilisation est utilisée pour de nombreux calculs.

> [!IMPORTANT]  
> Vous ne pouvez pas utiliser la fonction **Transaction contrepassée** pour les écritures comptables immobilisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures immobilisation**, puis sélectionnez le lien associé.  
2. Sur la page **Écritures immobilisation**, sélectionnez la ou les écritures à annuler.  
3. Choisissez le menu **Actions**, puis choisissez l’action **Annuler les entrées**.
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Pour lancer le traitement en lot, cliquez sur le bouton **OK**.
6. Lorsqu'une écriture incorrecte ou lorsque plusieurs écritures incorrectes sont annulées, continuez à reporter le coût d'acquisition exact.

## <a name="to-post-the-salvage-value-together-with-the-acquisition-cost"></a>Pour reporter la valeur résiduelle ainsi que le coût d'acquisition

Vous pouvez reporter la valeur résiduelle avec le coût d'acquisition à partir d'un journal immobilisation.

> [!NOTE]
> Ce processus peut nécessiter que vous personnalisiez la page journaux immobilisations en ajoutant le champ Valeur résiduelle. Par défaut, le champ À ne s’affiche pas sur la page. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux immobilisation**, puis choisissez le lien associé.
2. Sur la page **Journaux immobilisation**, créez la ligne d'acquisition. Pour en savoir plus, voir [Pour reporter manuellement une acquisition immobilisation avec le journal GL immobilisation](fa-how-acquire.md#to-post-a-fixed-asset-acquisition-manually-with-the-fixed-asset-gl-journal).
3. Dans le champ **Valeur résiduelle** de la ligne journal, saisissez le montant de la valeur résiduelle comme crédit (préfixe du montant avec un signe moins, par exemple, **-** 100).
4. Sélectionnez l'action **Reporter**.

> [!NOTE]
> S'il existe une valeur résiduelle pour une immobilisation, celle-ci est utilisée dans le report de l'amortissement au lieu de la valeur dans le champ **Valeur comptable finale** de la page **Registres amortissement immo**. Pour plus d'informations, voir [Pour gérer la valeur comptable finale](fa-how-depreciate-amortize.md#to-manage-the-ending-book-value).

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/purchase-fixed-assets/) associée

## <a name="see-also"></a>Voir aussi .

[Immobilisations](fa-manage.md) 

[Paramétrage d'immobilisations](fa-setup.md)

[Détails de la conception concernant l’impact de la TVA non déductible sur les immobilisations](design-details-nondeductible-vat.md)

[Finance](finance.md)  

[Préparation aux activités commerciales](ui-get-ready-business.md)  

[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
