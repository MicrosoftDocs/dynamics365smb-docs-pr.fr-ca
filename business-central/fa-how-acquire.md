---
title: Acquisition des immobilisations
description: 'Vous pouvez configurer une immobilisation, attribuer un registre amortissement et enregistrer le coût d''acquisition de l''immobilisation.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: purchase fixed asset
ms.search.form: '5605, 5551, 5600, 5628, 5629, 5633'
ms.date: 05/15/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="acquire-fixed-assets"></a>Acquisition des immobilisations

Utilisez la page **Fiche d’immobilisation** pour saisir des informations sur un actif. Vous pouvez configurer des bâtiments ou un équipement de production en tant qu'immobilisation principale avec une liste de composantes et vous pouvez les regrouper de différentes façons, comme par catégorie, département ou emplacement. Vous devez constituer et affecter un registre d’amortissement à chaque immobilisation avant de pouvoir l’acquérir.

Après avoir configuré une immobilisation et affecté un registre d’amortissement, vous devez acquérir l’immobilisation. Pour acquérir une immobilisation, vous enregistrez son coût d'acquisition dans le compte du grand livre, le compte bancaire ou le fournisseur pertinent en reportant une transaction d'acquisition à partir de la page **Journal GL immobilisation**. Vous pouvez utiliser la page **Acquisition d'immobilisation assistée** pour créer et reporter automatiquement les lignes journal général requises.

Utilisez l’indexation pour ajuster les valeurs en fonction des changements généraux du niveau des prix. Utilisez la tâche par lots **Indexer les immobilisations** pour calculer les coûts d’acquisition et les coûts de remplacement.

## <a name="add-a-fixed-asset-to-your-list-of-fixed-assets"></a>Ajouter une immobilisation à votre liste d’immobilisations

Avant de pouvoir acquérir une immobilisation, vous devez l’ajouter à votre liste d’actifs. Il existe plusieurs façons d’ajouter des immobilisations à votre liste :

* Saisissez les informations sur les actifs sur la page **Fixe Asset Card** .
* Utilisez l’action **Modifier dans Excel** pour télécharger votre liste d’éléments dans une feuille de calcul, ajouter de nouveaux éléments à la liste, puis publier la mise à jour [!INCLUDE [prod_short](includes/prod_short.md)].
* Utilisez un bon de commande pour ajouter des actifs.
* Utilisez l’action **Copier l’immobilisation** .

Après avoir ajouté des immobilisations à votre liste, l’étape suivante consiste à les acquérir afin de pouvoir les utiliser dans des transactions. Pour en savoir plus, consultez [Acquérir une immobilisation](#acquire-fixed-assets).

### <a name="add-a-fixed-asset-on-the-fixed-asset-card-page"></a>Ajouter une immobilisation sur la page Fiche immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**, puis renseignez les champs du raccourci **Général**, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Sur le raccourci **Loi d'amortissement**, renseignez les champs, le cas échéant. Cette étape attribue un registre amortissement à l'immobilisation.  
4. Si vous devez assigner plus d'une loi d'amortissement à l'immobilisation, sélectionnez l'action **Ajouter davantage de lois d'amortissement**. Pour en savoir plus, accédez à [Pour affecter une loi d’amortissement à une immobilisation](fa-how-setup-depreciation.md#to-assign-a-depreciation-book-to-a-fixed-asset).

    Après avoir rempli les champs obligatoires, **Vous êtes prêt à acquérir l’immobilisation.** La notification apparaît en haut de la page. Si vous êtes prêt à acquérir l’actif maintenant, choisissez l’action **Acquérir** . Suivez les étapes de la page **Acquisition assistée d’immobilisations** pour finaliser l’acquisition. Si vous n’êtes pas prêt, vous pourrez toujours acquérir l’actif plus tard.

### <a name="use-edit-in-excel-to-add-assets"></a>Utilisez Modifier dans Excel pour ajouter des actifs

Si vous souhaitez ajouter de nombreuses immobilisations, Modifier dans Excel est un excellent outil à utiliser. L’outil télécharge votre liste actuelle d’actifs dans une feuille de calcul qui comprend la plupart des champs disponibles sur la page Fiche des immobilisations. Vous pouvez remplir tout ou partie des champs d’une ligne pour chaque élément et publier vos modifications pour les ajouter à votre liste dans [!INCLUDE [prod_short](includes/prod_short.md)]. Si vous ne pouvez pas remplir tous les champs obligatoires, ce n’est pas grave. Vous pourrez les mettre à jour dans [!INCLUDE [prod_short](includes/prod_short.md)] lorsque vous serez prêt.

> [!NOTE]
> Pour utiliser l’action Modifier dans Excel, vous devez avoir installé le Microsoft Dynamics complément Office. Le complément crée la connexion entre Excel et [!INCLUDE [prod_short](includes/prod_short.md)]. Pour en savoir plus, accédez à [Obtenir le complément Business Central pour Excel](admin-deploy-excel-addin.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Choisissez l’icône :::image type="content" source="media/share-icon.png" alt-text="Partager cette page avec d’autres utilisateurs ou applications."::: Puis choisissez **Modifier dans Excel**.
3. Ouvrez le fichier téléchargé et saisissez les informations sur les nouvelles immobilisations.

   > [!TIP]
   > Vous n’avez pas besoin de saisir d’identifiant dans le champ **N°.** . Lorsque vous publiez votre mise à jour, [!INCLUDE [prod_short](includes/prod_short.md)] attribue un identifiant basé sur la série de numéros que vous utilisez pour les immobilisations.

4. Pour mettre à jour [!INCLUDE [prod_short](includes/prod_short.md)], dans le **Microsoft Dynamics** volet, choisissez **Publier**.

### <a name="add-a-fixed-asset-from-a-purchase-order-or-invoice"></a>Ajouter une immobilisation à partir d’un bon de commande ou d’une facture

Les étapes suivantes décrivent comment ajouter une immobilisation à partir d’un bon de commande. Les étapes sont similaires pour une facture d’achat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.
2. Choisissez **Nouveau** pour créer un nouveau bon de commande.
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire. [!INCLUDE [tooltip-inline-tip_md](../archive/SetupAndAdministration/includes/tooltip-inline-tip_md.md)]
4. Sur l’onglet **Lignes** Rapide, dans le champ **Type**, choisissez **Immobilisation**.
5. Dans le champ **N°**, , soit choisissez une immobilisation existante pour ajouter une dépense, soit choisissez **Nouveau** pour ajouter une nouvelle immobilisation.
6. Après avoir saisi les informations du nouvel actif et du bon de commande, choisissez **Publier**.

## <a name="acquire-a-fixed-asset-by-using-a-fixed-asset-gl-journal"></a>Acquérir une immobilisation à l’aide d’un journal G/L d’immobilisation

La procédure suivante décrit comment acquérir en créant et en reportant les lignes journal du grand livre des immobilisations requises. Vous pouvez également créer et reporter les lignes journal manuellement. Pour en savoir plus, accédez à [Acquérir une immobilisation à l’aide d’un journal du grand livre des immobilisations](#acquire-a-fixed-asset-by-using-a-fixed-asset-gl-journal).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
1. Choisissez l’actif que vous souhaitez acquérir, puis choisissez l’action **Acquérir** .
1. Suivez les étapes de la page **Acquisition assistée d’immobilisations** pour finaliser l’acquisition.

> [!NOTE]  
> Vous pouvez également reporter le coût d'acquisition en tant que crédit. Dans ce cas, n'oubliez pas que la valeur du champ **Coût d'acquisition TVA incluse** doit comporter un signe moins pour indiquer un avoir.

Lorsque vous choisissez **Terminer**, le champ **Valeur comptable** de la **Fiche des immobilisations** page est remplie, ce qui indique que l’immobilisation a été acquise au coût d’acquisition spécifié.  

## <a name="to-post-a-fixed-asset-acquisition-manually-with-a-fixed-asset-gl-journal"></a>Pour valider manuellement une acquisition d’immobilisation avec un journal général d’immobilisation

La procédure suivante décrit comment acquérir manuellement une immobilisation en créant et en reportant des lignes sur la page **Journal GL immobilisation**. Vous pouvez également acquérir une immobilisation automatiquement sur la page **Fiche immobilisation** en choisissant l’action **Acquérir une immobilisation** . Pour en savoir plus, rendez-vous sur [Acquérir une immobilisation](#acquire-fixed-assets).

> [!NOTE]  
> Vous pouvez également reporter le coût d'acquisition en tant que crédit. Dans ce cas, n'oubliez pas que la valeur du champ **Montant** doit comporter un signe moins pour indiquer un avoir.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux GL immobilisation**, puis choisissez le lien associé.
2. Sur la page **Journal GL immobilisation**, dans le champ **Type report immo.**, sélectionnez **Coût acquisition**.
3. Renseignez les champs restants selon vos besoins.
4. Sélectionnez l'action **Valider**.  

> [!TIP]  
> Si vous renseignez le champ **N° d’assurance**, [!INCLUDE[prod_short](includes/prod_short.md)] comptabilise également le coût d’acquisition de l’immobilisation dans le grand livre de couverture d’assurance. Pour en savoir plus, consultez [Assurer les immobilisations](fa-how-insure.md).

## <a name="to-set-up-a-component-list-for-a-main-asset"></a>Pour configurer une liste de composantes pour une immobilisation principale

Vous pouvez regrouper les immobilisations en immobilisations principales divisées en composants. Par exemple, vous pouvez avoir une machine de production composée de plusieurs pièces que vous souhaitez regrouper de cette manière.  

Vous devez paramétrer l’immobilisation principale et tous ses composants en tant qu’immobilisation individuelle. Après avoir configuré une liste de composants, [!INCLUDE[prod_short](includes/prod_short.md)] remplit automatiquement les **Actifs principaux/Composant** et **Composants de l’actif principal** champs sur les immobilisations.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation principale, puis l'action **Composants immo. principale**.
3. Sur la page **Composantes immo. principale**, choisissez **N° immo.**., puis sélectionnez l'immobilisation que vous souhaitez ajouter comme composante de l'immobilisation principale.
4. Fermez la page.
5. Répétez les étapes 3 et 4 pour chaque composante de l'immobilisation que vous souhaitez ajouter.
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration immobilisations**, puis choisissez le lien associé.
7. Activez le bouton **Autoriser la publication sur les éléments principaux** .

## <a name="to-cancel-an-acquisition-cost-posting-for-one-fixed-asset"></a>Pour annuler le report du coût d'une acquisition pour une immobilisation

Si vous faites une erreur lors de la validation d'un coût d'acquisition, vous pouvez supprimer l'écriture à l'aide du traitement par lots **Annuler écritures immo**, puis valider l'écriture d'acquisition correcte. Les écritures erronées sont transférées vers la page **Erreur écritures immo.**.

Par exemple, si vous reportez une acquisition avec une date erronée, vous devez la corriger dès que possible, car la date de report de l’immobilisation est utilisée pour de nombreux calculs.

> [!IMPORTANT]  
> Vous ne pouvez pas utiliser l’action **Annuler les transactions** pour les saisies d’immobilisations.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures immobilisation**, puis sélectionnez le lien associé.  
2. Sur la page **Écritures immobilisation**, sélectionnez la ou les écritures à annuler.  
3. Choisissez le menu **Actions**, puis choisissez l’action **Annuler les entrées**.
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
5. Pour lancer le traitement en lot, cliquez sur le bouton **OK**.
6. Lorsqu'une écriture incorrecte ou lorsque plusieurs écritures incorrectes sont annulées, continuez à reporter le coût d'acquisition exact.

## <a name="to-post-the-salvage-value-together-with-the-acquisition-cost"></a>Pour reporter la valeur résiduelle ainsi que le coût d'acquisition

La valeur résiduelle est la valeur restante d'une immobilisation qui est devenue inutilisable. Vous pouvez reporter la valeur résiduelle lors du report du coût d'acquisition. Pour en savoir plus, consultez [Déprécier ou amortir les immobilisations](fa-how-depreciate-amortize.md).

Vous pouvez reporter la valeur résiduelle avec le coût d'acquisition à partir d'un journal immobilisation.

> [!NOTE]
> Ce processus peut nécessiter que vous personnalisiez la page journaux immobilisations en ajoutant le champ Valeur résiduelle. Par défaut, le champ À ne s’affiche pas sur la page. Pour en savoir plus, accédez à [Personnalisez votre espace de travail](ui-personalization-user.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux immobilisation**, puis choisissez le lien associé.
2. Sur la page **Journaux immobilisation**, créez la ligne d'acquisition. Pour en savoir plus, accédez à [Pour valider manuellement une acquisition d’immobilisation avec un journal général d’immobilisation](#to-post-a-fixed-asset-acquisition-manually-with-a-fixed-asset-gl-journal).
3. Dans le champ **Valeur résiduelle** de la ligne journal, saisissez le montant de la valeur résiduelle comme crédit (préfixe du montant avec un signe moins, par exemple, **-** 100).
4. Sélectionnez l'action **Valider**.

> [!NOTE]
> Si une valeur de récupération existe pour une immobilisation, cette valeur est utilisée dans la comptabilisation de l’amortissement au lieu de la valeur dans le champ  **Valeur comptable de fin**  du **Page des registres d’amortissement FA** . Pour en savoir plus, accédez à [Pour gérer la valeur comptable de clôture](fa-how-depreciate-amortize.md#to-manage-the-ending-book-value).

## <a name="see-also"></a>Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Détails de conception sur l’impact de la TVA non déductible sur les immobilisations](design-details-nondeductible-vat.md)  
[Finance](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
