---
title: Cession ou annulation d’immobilisations
description: 'Lorsque vous commercialisez ou cédez une immobilisation, la valeur de cession doit être reportée pour calculer et enregistrer le gain ou la perte.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: scrap
ms.search.form: '5628, 5610, 5611, 5629, 5633'
ms.date: 06/10/2024
ms.service: dynamics-365-business-central
---
# <a name="dispose-of-or-retire-fixed-assets"></a>Cession ou annulation des immobilisations

Lorsque vous commercialisez ou cédez une immobilisation, vous devez reporter la valeur de cession pour calculer et enregistrer le gain ou la perte. Une écriture cession doit être la dernière écriture reportée pour une immobilisation. Pour les immobilisations partiellement cédées, vous pouvez reporter plusieurs écritures cession. Le total de tous les montants de cession reportés doit être un montant crédit.  

> [!NOTE]  
> Si vous négociez une immobilisation en échange d'une autre, vous devez enregistrer à la fois la vente de l'ancienne immobilisation (cession) et l'achat de la nouvelle (acquisition). Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).  

Les étapes suivantes supposent que vos groupes de report sont configurés sur la page **Groupes de report immo**. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  

## <a name="to-post-a-disposal-from-the-fixed-asset-gl-journal"></a>Pour reporter une cession à partir du journal GL immobilisation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux GL immobilisation**, puis choisissez le lien associé.  
2. Créez une ligne journal initiale et complétez les champs, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Dans le champ **Type compta. immo**, sélectionnez **Cession**.  
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de la cession.  

    > [!NOTE]  
    >  L'étape 4 ne fonctionne que si vous avez configuré ce qui suit : sur la page **Fiche groupe de report immo.** pour le groupe de report de l'immobilisation, le champ **Compte cession** contient le compte débit du grand livre et le champ **Compte contrepartie cession** contient le compte GL dans lequel vous souhaitez reporter les écritures contrepartie pour appréciation. Pour plus d'informations, voir [Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  
5. Sélectionnez l'action **Reporter**.  

Si vous vendez une immobilisation ou en cédez une partie, vous devez d'abord diviser l'immobilisation avant de pouvoir enregistrer la transaction cession. Pour en savoir plus, voir [Transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md).  

## <a name="to-view-disposal-ledger-entries"></a>Pour visualiser des écritures cession

Lorsque vous vendez ou cédez une immobilisation, la valeur de cession est reportée dans le grand livre où vous pouvez afficher le résultat.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Lois d'amortissement**.  
3. Sélectionnez la loi d'amortissement pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Écritures comptables**.  
4. Sélectionnez une ligne avec **Cession** dans le champ **Catégorie report immo.**, puis sélectionnez l’action **Rechercher des écritures**.  
5. Sur la page **Rechercher des écritures**, sélectionnez la ligne écriture, puis l’action **Afficher les écritures associées**.  

La page **Écritures** s'ouvre. Vous pouvez y voir les écritures résultant du report de la cession.  

## <a name="see-also"></a>Voir aussi .

[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Pour configurer des groupes de report immobilisation](fa-how-setup-general.md#to-set-up-fixed-asset-posting-groups).  
[Finance](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Rechercher des écritures](ui-find-entries.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
