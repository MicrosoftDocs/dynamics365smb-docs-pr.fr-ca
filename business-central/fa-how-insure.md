---
title: Assurance des immobilisations
description: Vous pouvez attribuer une ou plusieurs immobilisations à une police d’assurance lors du report sur les livres couverture d’assurance à partir de la page **Journal assurance**.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'policy, coverage'
ms.search.form: '5647, 5644, 5653, 5651, 5655, 5652, 5645, 5656, 5646, 5648, 9275'
ms.date: 05/15/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="insure-fixed-assets"></a>Assurance des immobilisations

Utilisez la page **Carte d’assurance** pour configurer une police d’assurance couvrant une ou plusieurs immobilisations. Vous pouvez affecter une immobilisation à une police d’assurance ou plusieurs immobilisations à une police d’assurance.

Vous attribuez une immobilisation à une police d'assurance lors du report sur le livre couverture d'assurance à partir de la page **Journal assurance**.

En outre, vous pouvez attribuer une immobilisation à une police d'assurance et créer des écritures de couverture lorsque vous reportez son coût d'acquisition. Vous validez un coût d’acquisition du journal des immobilisations avec le champ **N° d’assurance** rempli. Vous devez activer l’option **Publication automatique d’assurance** sur la page **Configuration des immobilisations** . Pour plus d’informations, voir [Acquérir une immobilisation à l’aide d’un journal général d’immobilisation](fa-how-acquire.md#acquire-a-fixed-asset-by-using-a-fixed-asset-gl-journal).

Si l’option **Publication automatique d’assurance** de la page **Configuration des immobilisations** n’est pas activée, la validation des acquisitions à partir du Le journal des immobilisations crée des lignes sur la page **Journal d’assurance** . Vous devez publier ces lignes manuellement.

> [!WARNING]  
> Si vous n’activez pas l’option **Publication automatique d’assurance** sur la page **Configuration des immobilisations**, votre journal d’assurance doit être basé sur un modèle de journal sans série de numéros. En effet, les numéros de document insérés à partir de la ligne journal immobilisation entreront sinon en conflit avec les séries de numéros du journal assurance. Pour en savoir plus concernant les modèles journal et les lots, voir [Configurer les informations générales relatives aux immobilisations](fa-how-setup-general.md).

Après avoir affecté une immobilisation à une police d’assurance, le champ **Assuré** de la fiche de l’immobilisation contient **Oui**. Lorsque vous vendez l’immobilisation, la bascule est automatiquement désactivée.

## <a name="to-create-or-modify-an-insurance-card"></a>Pour créer ou modifier une fiche assurance

Lorsque vous recevez des informations concernant les modifications du montant de la couverture, vous devez saisir les nouvelles informations sur la page **Fiche assurance** pour vous assurer que vous avez analysé correctement la couverture de la police d'assurance.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Assurance**, puis choisissez le lien associé.
2. Choisissez l'action **Nouveau** pour créer une fiche pour une police d'assurance. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Sinon, sélectionnez la police d'assurance que vous souhaitez modifier, puis sélectionnez l'action **Modifier**.

## <a name="to-assign-a-fixed-asset-to-an-insurance-policy-by-posting-from-the-insurance-journal"></a>Pour affecter une immobilisation à une police d'assurance en effectuant un report à partir du journal assurance

Vous affectez une immobilisation à une police d'assurance en reportant sur les écritures couverture d'assurance.  

La procédure suivante explique comment créer une ligne journal assurance manuellement. Si le bouton **Publication automatique d’assurance** est activé sur la page **Configuration des immobilisations**, les lignes du journal d’assurance sont automatiquement créées lorsque vous comptabilisez les frais d’acquisition. Dans ce cas, tout ce que vous avez à faire consiste à reporter le journal.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux assurance**, puis choisissez le lien associé.  
2. Ouvrez le journal pertinent, puis complétez les lignes journal, le cas échéant.  
3. Pour affecter plusieurs immobilisations à une police d'assurance, créez des lignes journal avec la même valeur dans le champ **N° assurance** et d'autres valeurs dans le champ **N° immo.**.  
4. Sélectionnez l'action **Valider**.  

    > [!NOTE]  
    > Les écritures d'un journal assurance sont uniquement reportées dans le livre couverture d'assurance.  

## <a name="to-update-the-insurance-value-of-a-fixed-asset"></a>Pour mettre à jour la valeur assurance d'une immobilisation

Vous pouvez utiliser le traitement par lots **Réévaluer assurance** pour mettre à jour la valeur des immobilisations couvertes.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réévaluer assurance**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins.

    > [!NOTE]  
    >   Dans le champ **Taux de réévaluation**, vous saisissez une baisse de 5 %, par exemple, soit 95, tout en saisissant une hausse de 2 %, soit 102.  
3. Cliquez sur le bouton **OK**.  

   Le traitement en lot calcule le nouveau montant en tant que pourcentage de la valeur totale assurée à partir de la page **Statistiques assurance**, puis crée une ligne dans le journal assurance.  
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux assurance**, puis choisissez le lien associé.  
5. Ouvrez le journal assurance pertinent, examinez les valeurs créées, puis reportez-les sur les écritures couverture d'assurance.  

## <a name="to-monitor-insurance-coverage"></a>Pour surveiller la couverture assurance

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des rapports dédiés et des pages de statistiques à utiliser pour analyser les polices d'assurance et si vos immobilisations sont sur- ou sous-assurées.  

### <a name="overview-of-insurance-policies"></a>Aperçu des polices d’assurance

Pour obtenir un aperçu de vos polices d'assurance, afficher un aperçu ou imprimer l'état **Assurances - Liste**. Le rapport indique toutes les polices et les champs les plus importants des fiches assurance.  

### <a name="insurance-coverage"></a>Couverture d’assurance

Pour visualiser les immobilisations couvertes par une assurance et à quelle hauteur, vous pouvez afficher l'aperçu ou imprimer l'état **Assurances - Valeur totale**.  

#### <a name="overunder-coverage"></a>Sur/sous-couverture

Vous pouvez vérifier si les immobilisations sont sur ou sous-assurées des manières suivantes :  

* La page **Statistiques assurance**. Un montant positif dans le champ **Sur/Sous-assuré** signifie que l'immobilisation est sur-assurée. Un montant négatif signifie que le bien est sous-assuré.  
* La page **Statistiques immobilisation**. Choisissez le champ **Valeur totale assurée** pour afficher la page **Écritures couverture assurance.**.  
* L'état **Sur-assurance et sous-assurance**.  
* L'état **Assurance - Analyse**.  

### <a name="uninsured-fixed-assets"></a>Immobilisations non assurées

Pour vérifier si vous avez oublié d’affecter une immobilisation à un contrat d’assurance, vous pouvez imprimer ou prévisualiser le rapport **Assurance - FA non assurés** . Ce rapport affiche les immobilisations pour lesquelles les montants ne sont pas comptabilisés dans le grand livre de couverture d’assurance.  

## <a name="to-view-insurance-coverage-ledger-entries"></a>Pour visualiser des écritures couverture d'assurance

Vous pouvez consulter les écritures que vous avez effectuées dans le grand livre de la couverture d’assurance.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Assurance**, puis choisissez le lien associé.  
2. Sélectionnez la police d'assurance appropriée, puis sélectionnez l'action **Écritures comptables couverture**.  

## <a name="to-view-the-total-insurance-value-of-fixed-assets"></a>Pour afficher la valeur d'assurance totale des immobilisations

Une page matricielle affiche les valeurs d’assurance enregistrées pour chaque police d’assurance pour chaque immobilisation résultant des montants liés à l’assurance comptabilisés.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Assurance**, puis choisissez le lien associé.  
2. Sélectionnez la police d'assurance appropriée, puis sélectionnez l'action **Valeur totale assurée par immo.**.  
3. Renseignez les champs selon vos besoins.  
4. Choisissez l'action **Afficher matrice**.  
5. Pour visualiser les écritures couverture d'assurance, sélectionnez une valeur dans la matrice.  

## <a name="to-correct-insurance-coverage-entries"></a>Pour corriger des écritures couverture assurance

Si une immobilisation a été affectée à la mauvaise police d’assurance, vous pouvez la corriger en créant deux écritures de reclassement à partir du journal d’assurance.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux assurance**, puis choisissez le lien associé.  
2. Créez une ligne feuille pour l'immobilisation et la police d'assurance appropriée lorsque la valeur du champ **Montant** est positive.  
3. Créez une autre ligne feuille pour l'immobilisation et la police d'assurance incorrecte lorsque la valeur du champ **Montant** est négative.  
4. Sélectionnez l'action **Valider**.  

L’immobilisation est supprimée de la police d’assurance incorrecte sur la deuxième ligne. L’actif est affecté à la police d’assurance appropriée sur la première ligne du journal.  

## <a name="see-also"></a>Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
