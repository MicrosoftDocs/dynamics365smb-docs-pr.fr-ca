---
title: 'Procédure : regrouper des livraisons sur une seule facture | Microsoft Docs'
description: Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 757f7cd38a6325df0e8dc0d283d58c42a8ab823e
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4748278"
---
# <a name="combine-shipments-on-a-single-invoice"></a>Regroupement de livraisons sur une seule facture
Si vous souhaitez facturer plusieurs bons de livraison à la fois, vous pouvez utiliser la fonction de regroupement des bons de livraison.  

Avant de pouvoir regrouper des livraisons, plusieurs livraisons vente pour le même client doivent être reportées dans la même devise. Autrement dit, vous devez avoir créé au moins deux documents de vente et les avoir reportés comme étant livrés, mais pas facturés. 

## <a name="to-manually-combine-shipments-on-a-single-invoice"></a>Regrouper manuellement les expéditions sur une seule facture  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Factures vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**. Pour plus d'informations, reportez-vous à [Facturer des ventes](sales-how-invoice-sales.md).
3. Dans le champ **N° donneur d'ordre** entrez le client facturé pour les articles livrés.  
4. Dans le raccourci **Lignes**, sélectionnez l'action **Extraire lignes livraison**.  
5. Sélectionnez la ligne livraison que vous voulez inclure dans la facture :  

    - Pour insérer toutes les lignes, sélectionnez-les toutes et sélectionnez le bouton **OK**.  
    - Pour insérer des lignes spécifiques, sélectionnez-les et sélectionnez le bouton **OK**. Vous pouvez utiliser la touche Ctrl pour sélectionner plusieurs lignes qui ne sont pas séquentielles.  

    Si une ligne livraison incorrecte a été sélectionnée ou si vous voulez recommencer, supprimez simplement les lignes de la facture, puis exécutez de nouveau la fonction **Extraire lignes livraison**.  
7. Pour reporter la facture, sélectionnez l'action **Reporter**.  

## <a name="to-automatically-combine-shipments-on-a-single-invoice"></a>Regrouper automatiquement les expéditions sur une seule facture  
[!INCLUDE[prod_short](includes/prod_short.md)] ne sélectionne que les documents de vente où **Regrouper les B.L.** est coché. 

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Regrouper les livraisons**, puis sélectionnez le lien associé. La page de demande de traitement en lot s'ouvre.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Cochez la case **Reporter factures**.  
4. Choisissez le bouton **OK**.  

> [!NOTE]  
>  Vous devez valider manuellement les avoirs si la case à cocher **Valider avoirs** n'a pas été activée pour le traitement par lots.  

## <a name="to-remove-open-sales-orders-after-combined-shipment-posting"></a>Pour supprimer des documents de vente ouverts après le report des livraisons regroupées 
Lorsque des livraisons sont regroupées sur une facture et reportées, une facture vente reportées est créée pour les lignes facturées. Le champ **Quantité facturée** de la commande permanente ventes ou du document de vente d'origine est mis à jour sur la base de la quantité facturée.  

Lorsque vous facturez des livraisons de cette manière, les commandes à partir desquelles les livraisons ont été reportées continuent à exister, même si elles ont été entièrement reportées et facturées.   

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Supprimer les documents de vente facturés**, puis sélectionnez le lien.  
2. Dans le champ de filtre **N°**, les commandes vente à supprimer.  
3. Cliquez sur le bouton **OK**.  

Il est également possible de supprimer chacune des commandes vente manuellement.  

Répétez les étapes 1 à 3 pour tous les autres documents affectés, comme des commandes permanentes ventes.

## <a name="see-also"></a>Voir aussi  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]