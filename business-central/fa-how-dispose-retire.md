---
title: Cession ou annulation d'immobilisations| Microsoft Docs
description: Vous devez reporter une valeur de cession lorsque vous mettez au rebut, vendez ou annulez une immobilisation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: scrap
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 550ae80bb03fb053547713fc71a8708fae100e5f
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="dispose-of-or-retire-fixed-assets"></a>Céder ou annuler des immobilisations
Lorsque vous commercialisez ou cédez une immobilisation, la valeur de cession doit être reportée pour calculer et enregistrer le gain ou la perte. Une écriture cession doit être la dernière écriture reportée pour une immobilisation. Pour les immobilisations partiellement cédées, vous pouvez reporter plusieurs écritures cession. Le total de tous les montants de cession reportés doit être un montant crédit.  

> [!NOTE]  
>   Si vous négociez une immobilisation en échange d'une autre, vous devez enregistrer à la fois la vente de l'ancienne immobilisation (cession) et l'achat de la nouvelle (acquisition). Pour en savoir plus, voir [Acquérir des immobilisations](fa-how-acquire.md).  

## <a name="to-post-a-disposal-from-the-fixed-asset-gl-journal"></a>Pour reporter une cession à partir du journal GL immobilisation
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux GL d'immobilisations**, puis sélectionnez le lien associé.  
2. Créez une ligne journal initiale et complétez les champs, le cas échéant. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Dans le champ **Type compta. immo**, sélectionnez **Cession**.  
4. Sélectionnez l'action **Insérer contrepartie immo.**. Une seconde ligne journal est créée pour le compte de contrepartie qui est configuré pour le report de la cession.  

    > [!NOTE]  
    >   L'étape 4 ne fonctionne que si vous avez configuré ce qui suit : la fenêtre **Fiche groupe compta. immo.** pour le groupe de validation de l'immobilisation, le champ **Cession immobilisation** contient le compte débit général et le champ **Compte contrepartie cession** contient le compte général auquel vous souhaitez valider les écritures contrepartie pour appréciation. Pour en savoir plus, voir la section « Pour configurer des groupes de report d'immobilisation » dans [Configurer des informations d'immobilisation générales pour les immobilisations](fa-how-setup-general.md).  
5. Sélectionnez l'action **Valider**.  

Si vous vendez une immobilisation ou en cédez une partie, vous devez d'abord diviser l'immobilisation avant de pouvoir enregistrer la transaction cession. Pour en savoir plus, voir [Transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md).  

## <a name="to-view-disposal-ledger-entries"></a>Pour visualiser des écritures cession
Lorsque vous vendez ou cédez une immobilisation, la valeur de cession est reportée dans le grand livre où vous pouvez afficher le résultat.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Immobilisations**, puis choisissez le lien associé.  
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Lois d'amortissement**.  
3. Sélectionnez la loi d'amortissement pour laquelle vous souhaitez afficher les écritures, puis sélectionnez l'action **Écritures comptables**.  
4. Sélectionnez une ligne avec **Cession** dans le champ **Catégorie compta. immo.**, puis sélectionnez l'action **Naviguer**.  
5. Dans la fenêtre **Naviguer**, sélectionnez la ligne d'écriture comptable, puis l'action **Afficher**.  

La fenêtre **Écritures comptables** s'ouvre. Vous pouvez y voir les écritures résultant de la validation de la cession.  

## <a name="see-also"></a>Voir aussi
[Immobilisations](fa-manage.md)  
[Paramétrage d'immobilisations](fa-setup.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

