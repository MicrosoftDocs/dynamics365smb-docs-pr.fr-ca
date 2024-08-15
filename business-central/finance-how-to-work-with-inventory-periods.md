---
title: Utiliser les périodes d'inventaire
description: Vous pouvez contrôler le délai de report des modifications de l'inventaire en définissant des périodes d'inventaire.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'inventory, periods'
ms.search.form: 5828
ms.date: 04/01/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="work-with-inventory-periods"></a>Utiliser les périodes d'inventaire

Les périodes d'inventaire sont des périodes au cours desquelles vous pouvez reporter des modifications d'inventaire. Une période d'inventaire est définie par la date à laquelle elle se termine (date fin). Lorsque vous fermez une période d'inventaire, vous ne pouvez pas reporter de modifications d'inventaire, qu'elles soient prévues ou facturées, avant cette date fin. Vous ne pouvez pas reporter de nouvelles valeurs dans l'inventaire avant la date de fin. Si vous avez des écritures du grand livre d'articles ouvertes dans la période fermée, ce qui signifie des quantités positives qui n'ont pas encore été affectées sur des transactions sortantes, vous pouvez encore affecter des quantités sortantes sur ces écritures, même si la période est fermée.  

Les sections suivantes décrivent comment :

* Créer des périodes inventaire.  
* Fermer des périodes d'inventaire.  
* Rouvrir des périodes inventaire.  

## <a name="to-create-an-inventory-period"></a>Pour créer une période d'inventaire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Périodes d’inventaire**, puis choisissez le lien associé.  
2. Créez une ligne.  
3. Dans le champ **Date fin**, entrez la dernière date que vous voulez définir pour la période inventaire. Une fois la période fermée, vous ne pouvez plus reporter de modifications d'inventaire antérieures à cette date.  
4. Saisissez un nom descriptif dans le champ **Nom**. Cliquez sur le bouton **OK**.  

## <a name="to-close-inventory-periods"></a>Fermeture de périodes d'inventaire

Le champ **Clôturé** indique si la période inventaire est clôturée ou non sur des modifications de valeur de stock. Vous ne pouvez pas modifier ce champ.  

Vous pouvez fermer toute période d'inventaire, pour autant que les conditions suivantes soient vraies :  

* Il n'y a pas d'écritures du grand livre d'articles sortantes ouvertes (inventaire négatif) dans cette période.  
* Le coût de tous les articles a été ajusté à l'aide du traitement par lots **Ajuster coût écritures article**.  

Cela signifie que toutes les quantités de transaction sortante, telles que celles des documents de vente, transferts sortants, factures vente, retours achat ou notes de crédit achat doivent être affectées à la quantité en inventaire.  

### <a name="to-close-an-inventory-period"></a>Pour fermer une période d'inventaire

1. Avant de fermer une période d'inventaire, choisissez l'action **Ajuster coût écritures article** pour vous assurer que tous les ajustements des coûts sont reportés.

    Exécutez l'état **Clôturer période inventaire – Test** pour déterminer s'il y a des écritures article sortant ouvertes dans la période inventaire ou des articles dont le coût n'a pas encore été ajusté.  
2. Choisissez l'action **Fermer la période d'inventaire - Test**.  

    Exécutez le traitement en lot **Reporter le coût de l'inventaire au grand livre** pour vous assurer que tous les coûts sont reportés dans le grand livre.  
3. Cliquez sur l'action **Reporter inventaire en grand livre**.  
4. Ouvrez la page **Périodes d'inventaire** et sélectionnez la période d'inventaire que vous voulez fermer.  
5. Choisissez l'action **Fermer la période**. Une fois la période d'inventaire fermée, vous ne pouvez pas reporter de modifications d'inventaire avant la date de fin. Le coût de tous les articles doit être ajusté avec le traitement par lots **Ajuster coût écritures article** avant la clôture de la période inventaire.  
6. Choisissez le bouton **Oui** pour confirmer la clôture de la période, ou choisissez **Non** pour annuler la clôture.  
7. La période d'inventaire est fermée et un message de confirmation est affiché une fois l'opération terminée.  

## <a name="reopening-inventory-periods"></a>Réouverture de périodes inventaire
Une fois la période d'inventaire fermée, vous ne pouvez plus la supprimer. En revanche, vous pouvez la rouvrir si vous voulez autoriser son report avant la date fin. La réouverture d'une période rouvre également toutes les périodes inventaire dont la date fin est postérieure à la fin de la période que vous rouvrez.  

### <a name="to-reopen-an-inventory-period"></a>Pour rouvrir une période d'inventaire
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Périodes d’inventaire**, puis choisissez le lien associé.  
2. Sélectionnez la période d'inventaire que vous voulez rouvrir.  
3. Sélectionnez l'action de la période **Rouvrir période**. Confirmez que vous voulez réouvrir la période.  
4. Toutes les périodes inventaire dont la date fin est postérieure à la fin de la période sélectionnée sont réouvertes.  

## <a name="see-also"></a>Voir aussi
[Détails de conception : périodes inventaire](design-details-inventory-periods.md)  
[Finance](finance.md)  
[Inventaire](inventory-manage-inventory.md)  
[Utiliser Financials](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
