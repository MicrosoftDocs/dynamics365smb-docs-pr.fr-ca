---
title: Mettre à jour des immobilisations
description: Vous conservez un registre d’entretien de toutes les réparations et services sur une immobilisation pour préserver la valeur de cette immobilisation.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'repair, service'
ms.search.form: '5642, 5625'
ms.date: 06/15/2021
ms.author: bholtorf
---
# <a name="maintain-fixed-assets"></a>Mettre à jour des immobilisations

Les frais d'entretien sont des coûts périodiques de routine engagés pour préserver la valeur des immobilisations. Contrairement aux améliorations de capital, ils n'augmentent pas les valeurs.

Vous pouvez enregistrer et mettre à jour un fichier sur l'entretien et le service des immobilisations afin d'accéder facilement aux enregistrements d'entretien complets des immobilisations. Chaque fois qu'une immobilisation est envoyée en réparation, vous enregistrez toutes les informations importantes, par exemple la date de réparation, le numéro du fournisseur et le numéro de téléphone de l'intervenant. La saisie de l'entretien est effectuée pour chaque immobilisation à partir de la fiche immobilisation.

L'actualisation permet d'ajuster des valeurs en fonction de modifications générales de niveau de prix. Le traitement par lots **Réévaluer immobilisations** permet de recalculer les coûts de maintenance.

## <a name="to-record-maintenance-work-on-a-fixed-asset"></a>Pour enregistrer les travaux d'entretien sur une immobilisation

Vous pouvez enregistrer chaque tâche entretien, telle qu'une visite de service, effectuée pour une immobilisation donnée. Pour cela, utilisez la page **Enregistrements entretien**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez enregistrer la maintenance, puis sélectionnez l'action **Saisie de la maintenance**.
3. Sur la page **Enregistrement entretien**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-post-maintenance-costs-from-a-fixed-asset-gl-journal"></a>Pour reporter les coûts d'entretien à partir d'un journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Liste registres amortissement**, puis choisissez le lien associé.  
2. Sélectionnez la loi d'amortissement qui est attribuée à une immobilisation, puis sélectionnez l'action **Modifier**.
3. Sur la page **Fiche registre amortissement**, veillez à ce que la case **Entretien** ne soit pas cochée. Cela garantit que les coûts d'entretien ne sont pas reportés dans le grand livre.
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  
5. Créez une ligne journal initiale et complétez les champs, le cas échéant.
6. Dans le champ **Type compta. immo**, sélectionnez **Maintenance**.
7. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de l'entretien.

    > [!NOTE]  
    >   L'étape 7 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** du groupe de report de l'immobilisation, le champ **Compte entretien** contient le compte débit GL et le champ **Compte contrepartie entretien** contient le compte GL dans lequel vous souhaitez reporter les écritures contrepartie pour appréciation. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
8. Sélectionnez l'action **Reporter**.

## <a name="to-follow-up-on-fixed-assets-service-visits"></a>Pour effectuer le suivi des visites d'entretien des immobilisations

Vous pouvez imprimer l'état **Maintenance - Service suivant** afin de connaître les immobilisations pour lesquelles vous avez programmé une visite de service. Vous pouvez également utiliser cet état lorsque vous mettez à jour le champ **Date prochain service** des fiches immobilisation.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Entretien - Service suivant**, puis choisissez le lien associé.  
2. Renseignez les champs **Date début** et **Date fin**.  
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## <a name="to-monitor-maintenance-costs"></a>Pour surveiller les coûts d'entretien

Vous pouvez visualiser les coûts d'entretien lorsque vous consultez les statistiques d'une immobilisation.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les coûts de maintenance, puis sélectionnez l'action **Lois d'amortissement**.
3. Sur la page **Registres amortissement immo.**, sélectionnez le registre amortissement immobilisation pertinent, puis sélectionnez l'action **Statistiques**.
4. Sur la page **Statistiques immobilisation**, sélectionnez le champ **Entretien**.

La page **Écritures entretien** s'ouvre, affichant les écritures qui constituent le montant dans le champ **Entretien**.

## <a name="to-view-or-print-maintenance-costs-for-multiple-fixed-assets"></a>Pour afficher ou imprimer les coûts d'entretien pour plusieurs immobilisations

Dans l'état **Maintenance - Analyse**, vous pouvez choisir de visualiser la maintenance sur un, deux ou trois codes maintenance pour une date ou une période donnée. Vous pouvez également visualiser soit le total de toutes les immobilisations sélectionnées, soit celui de chaque immobilisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Entretien - Analyse**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## <a name="to-view-maintenance-ledger-entries"></a>Pour visualiser des écritures entretien

Vous pouvez également étudier les coûts d'entretien en visualisant les écritures.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures comptables, puis sélectionnez l'action **Lois d'amortissement**.
3. Sur la page **Registres amortissement immo.**, sélectionnez le registre amortissement immobilisation pertinent, puis l'action **Écritures du registre d'entretien**.

## <a name="to-view-or-print-maintenance-ledger-entries-for-multiple-fixed-assets"></a>Pour afficher ou imprimer les écritures d'entretien pour plusieurs immobilisations

Dans l'état **Maintenance - Détails**, vous pouvez afficher ou imprimer les écritures comptables de maintenance pour un ou plusieurs actifs.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Entretien - Détails**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## <a name="see-also"></a>Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
