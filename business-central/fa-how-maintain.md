---
title: Mise à jour des immobilisations
description: Enregistrez les réparations et l’entretien d’une immobilisation pour en préserver la valeur.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'repair, service'
ms.search.form: '5642, 5625'
ms.date: 05/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="maintain-fixed-assets"></a>Mise à jour des immobilisations

Les frais d’entretien sont des dépenses d’exploitation liées aux choses que vous faites pour préserver l’état de vos immobilisations. Contrairement aux améliorations des immobilisations, l’entretien n’augmente pas la valeur de vos actifs.

Chaque fois une immobilisation envoyée en réparation, vous enregistrez les informations, par exemple la date de réparation, le fournisseur et le numéro de téléphone de l'intervenant. Vous saisissez les informations d'entretien sur plusieurs pages :

* Fiche immobilisation
* Commande achat
* Facture achat
* Journal GL immobilisation

L'actualisation permet d'ajuster des valeurs en fonction de modifications générales de niveau de prix. Utilisez l'action **Réévaluer immobilisations** pour recalculer les coûts d'entretien.

## <a name="record-a-maintenance-cost-directly-on-a-fixed-asset"></a>Enregistrer un coût d'entretien directement sur une immobilisation

Vous pouvez enregistrer chaque tâche d'entretien d’un actif, telle qu’une visite de service sur la page **Enregistrements entretien**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez enregistrer la maintenance, puis sélectionnez l'action **Saisie de la maintenance**.
3. Sur la page **Enregistrement entretien**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="post-maintenance-costs-from-a-fixed-asset-gl-journal"></a>Reporter les coûts d'entretien à partir d’un journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Liste registres amortissement**, puis choisissez le lien associé.  
2. Sélectionnez la loi d'amortissement qui est attribuée à une immobilisation, puis sélectionnez l'action **Modifier**.
3. Sur la page **Fiche du registre amortissement**, assurez-vous que la case **Entretien** n’est pas cochée afin de ne pas reporter les coûts d'entretien dans le grand livre.
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL immobilisation**, puis choisissez le lien associé.  
5. Créez une ligne journal initiale et complétez les champs, le cas échéant.
6. Dans le champ **Type compta. immo**, sélectionnez **Maintenance**.
7. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de l'entretien.

    > [!NOTE]  
    > L'étape 7 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** du groupe de report de l'immobilisation, le champ **Compte entretien** contient le compte débit GL et le champ **Compte contrepartie entretien** contient le compte GL dans lequel vous souhaitez reporter les écritures contrepartie pour appréciation. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).
8. Sélectionnez l'action **Valider**.

## <a name="record-maintenance-cost-from-a-purchase-invoice"></a>Enregistrer le coût d'entretien à partir d’une facture achat

Les étapes suivantes décrivent comment enregistrer les coûts d'entretien d’une immobilisation à partir d’une facture d’achat. La procédure est identique pour les bons de commande.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Facture achat**, puis sélectionnez le lien associé.
2. Sur le raccourci **Général**, complétez les champs, comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans le champ **Type** du raccourci **Lignes**, sélectionnez **Immobilisations**.
4. Dans le champ **N°**, choisissez l’actif, puis spécifiez la quantité et le coût.
5. Dans le champ **Type report immo**, sélectionnez **Entretien**.
6. Reportez la facture achat.

## <a name="follow-up-on-service-visits"></a>Suivre visites d’entretien

Vous pouvez imprimer le rapport **Entretien - Service suivant** afin de lister les immobilisations programmées pour un service. Vous pouvez également utiliser ce rapport si vous souhaitez mettre à jour le champ **Date prochain service** sur les fiches immobilisation.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Entretien - Service suivant**, puis choisissez le lien associé.  
2. Renseignez les champs **Date début** et **Date fin**.  
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## <a name="monitor-maintenance-costs"></a>Surveiller les coûts d’entretien

Vous pouvez afficher des statistiques pour surveiller les coûts d'entretien.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les coûts de maintenance, puis sélectionnez l'action **Lois d'amortissement**.
3. Sur la page **Registres amortissement immo.**, sélectionnez le registre amortissement immobilisation pertinent, puis sélectionnez l'action **Statistiques**.
4. Sur la page **Statistiques immobilisation**, sélectionnez le champ **Entretien**.

Utilisez la page **Écritures entretien** pour afficher les écritures qui constituent le montant dans le champ **Entretien**.

## <a name="view-or-print-maintenance-costs-for-multiple-fixed-assets"></a>Afficher ou imprimer les coûts d'entretien pour plusieurs immobilisations

Dans le rapport **Entretien - Analyse**, vous pouvez choisir d'examiner l'entretien sur la base d'un, de deux ou de trois codes entretien pour une date ou une période spécifique. Le rapport peut visualiser le total de toutes les immobilisations sélectionnées, soit celui de chaque immobilisation.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Entretien - Analyse**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins.
3. Cliquez sur le bouton **Imprimer** ou **Aperçu**.

## <a name="view-maintenance-ledger-entries"></a>Visualiser des écritures entretien

Vous pouvez également explorer les coûts d'entretien en visualisant les écritures entretien.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures comptables, puis sélectionnez l'action **Lois d'amortissement**.
3. Sur la page **Registres amortissement immo.**, sélectionnez le registre amortissement immobilisation pertinent, puis l'action **Écritures du registre d'entretien**.

## <a name="view-or-print-maintenance-ledger-entries-for-multiple-fixed-assets"></a>Afficher ou imprimer des écritures entretien pour plusieurs immobilisations

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
