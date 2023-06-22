---
title: "Procédure\_: regrouper des livraisons sur une seule facture | Microsoft Docs"
description: 'Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 12/16/2021
ms.author: edupont
---
# <a name="combine-shipments-on-a-single-invoice" />Regroupement de livraisons sur une seule facture

Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.  

Avant de pouvoir regrouper des livraisons, plusieurs livraisons vente pour le même client doivent être reportées dans la même devise. Autrement dit, vous devez avoir créé au moins deux documents de vente et les avoir reportés comme étant livrés, mais pas facturés. 

## <a name="to-manually-combine-shipments-on-a-single-invoice" />Regrouper manuellement les expéditions sur une seule facture

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**. Pour plus d'informations, reportez-vous à [Facturer des ventes](sales-how-invoice-sales.md).
3. Dans le champ **N° donneur d'ordre** entrez le client facturé pour les articles livrés.  
4. Dans le raccourci **Lignes**, sélectionnez l'action **Extraire lignes livraison**.  
5. Sélectionnez la ligne livraison que vous voulez inclure dans la facture :  

    - Pour insérer toutes les lignes, sélectionnez-les toutes et sélectionnez le bouton **OK**.  
    - Pour insérer des lignes spécifiques, sélectionnez-les et sélectionnez le bouton **OK**. Vous pouvez utiliser la touche Ctrl pour sélectionner plusieurs lignes qui ne sont pas séquentielles.  

    Si une ligne livraison incorrecte a été sélectionnée ou si vous voulez recommencer, supprimez simplement les lignes de la facture, puis exécutez de nouveau la fonction **Extraire lignes livraison**.  
7. Pour reporter la facture, sélectionnez l'action **Reporter**.  

> [!TIP]  
> Si vous avez livré des commandes pour lesquelles le **N° débiteur** est différent du **N° client facturé**. Ces lignes ne sont pas affichées dans le rapport **Extraire lignes livraison**. Utilisez la personnalisation pour ajouter le champ **N° débiteur** à la page et supprimez le filtre. Vous pouvez désormais ajouter des lignes livraison à la facture quelle que soit la valeur du champ **N° débiteur** tant que le champ **N° client facturé** sur les lignes livraison correspond à la valeur sur la facture vente.  

## <a name="to-automatically-combine-shipments-on-a-single-invoice" />Regrouper automatiquement les expéditions sur une seule facture

[!INCLUDE[prod_short](includes/prod_short.md)] ne sélectionne que les documents de vente où **Regrouper les B.L.** est coché. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Combiner les livraisons**, puis sélectionnez le lien associé. La page de demande de traitement en lot s'ouvre.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Cochez la case **Reporter factures**.  
4. Choisissez le bouton **OK**.  

> [!NOTE]  
>  Vous devez valider manuellement les avoirs si la case à cocher **Valider avoirs** n'a pas été activée pour le traitement par lots.  

## <a name="to-remove-open-sales-orders-after-combined-shipment-posting" />Pour supprimer des documents de vente ouverts après le report des livraisons regroupées

Lorsque des livraisons sont regroupées sur une facture et reportées, une facture vente reportées est créée pour les lignes facturées. Le champ **Quantité facturée** de la commande ouverte vente ou de la commande vente d'origine est mis à jour sur la base de la quantité facturée.  

Lorsque vous facturez des livraisons de cette manière, les commandes à partir desquelles les livraisons ont été reportées continuent à exister, même si elles ont été entièrement reportées et facturées.   

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Supprimer documents de vente facturés**, puis sélectionnez le lien associé.  
2. Dans le champ de filtre **N°**, les commandes vente à supprimer.  
3. Cliquez sur le bouton **OK**.  

Il est également possible de supprimer chacune des commandes vente manuellement.  

Répétez les étapes 1 à 3 pour tous les autres documents affectés, comme des commandes permanentes ventes.

## <a name="see-related-microsoft-trainingtrainingmodulesinvoicing-customers-dynamics--business-central" />Voir la [formation Microsoft](/training/modules/invoicing-customers-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
