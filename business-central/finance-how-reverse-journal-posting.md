---
title: Annuler un report en reportant une écriture de contrepassation | Microsoft Docs
description: Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: f2767fca96e1f3689fc4806d878381d02622f261
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1243743"
---
# <a name="reverse-postings"></a>Inverser des reports
Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine. Une fois l'écriture inversée, créez l'écriture correcte.

Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général. Une écriture ne peut être inversée qu'une seule fois.

Pour plus d'informations sur le report d'un journal général, voir [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).

Si vous avez effectué un report de quantité négatif incorrect, comme un bon de commande avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant reçu (mais non facturé), vous pouvez annuler ce report.

Si vous avez effectué un report de quantité positif incorrect, comme un retour commande achat avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant livré (mais non facturé), vous pouvez annuler ce report.   

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a>Pour inverser le report journal d'une écriture grand livre
Vous pouvez inverser des écritures sur toutes les pages **Écritures**. La procédure suivante se base sur la page **Écritures**.
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Écritures**, puis sélectionnez le lien associé.
2. Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**. Notez qu'elle doit provenir d'un report journal.
3. Sur la page **Inverser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Inverser**.
4. Choisissez le bouton **Oui** dans le message de confirmation.

## <a name="to-undo-a-quantity-posting-on-a-posted-purchase-receipt"></a>Pour annuler un report de quantité sur une réception d'achat reportée  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Réceptions achat reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la réception reportée à annuler.  
3.  Sélectionnez la ligne ou les lignes à annuler.  
4.  Choisissez l'action **Annuler réception**.

    Une ligne de correction est insérée sous la ligne de la réception sélectionnée.  

    Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est insérée dans la réception entrepôt reportée.  

    Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.

## <a name="to-undo-and-then-redo-a-quantity-posting-on-a-posted-return-shipment"></a>Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Livraisons retour reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la livraison de retour reportée à annuler.
3. Sélectionnez la ligne ou les lignes à annuler.  

4.  Choisissez l'action **Annuler livraison retour**.  

    Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.  

    Retournez à présent au retour achat pour un nouveau report.  

5.  Sur la page **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour** .  
6.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Retours achat**, et sélectionnez le lien associé.  
7.  Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.  
8.  Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.  

## <a name="to-post-a-negative-entry"></a>Pour reporter une écriture négative  
Vous pouvez utiliser le champ **Correction** pour reporter un débit négatif au lieu d'un crédit, ou pour reporter un crédit négatif au lieu d'un débit sur un compte. Pour répondre aux exigences légales, ce champ est visible par défaut sur tous les journaux. Les champs **Montant débit** et **Montant crédit** comprennent l'écriture initiale et l'écriture corrigée. Ces champs n'ont aucune incidence sur le solde du compte.  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux généraux**, puis sélectionnez le lien associé.  
2.  Dans le champ **Nom de la feuille**, sélectionnez le nom de feuille requis.  
3.  Entrez les informations dans les champs pertinents.  
4.  Dans la ligne journal que vous souhaitez activer pour les écritures négatives, sélectionnez la case à cocher **Correction**.  
5.  Pour reporter le journal, sélectionnez l'action **Reporter**, puis le bouton **Oui**.

## <a name="see-also"></a>Voir aussi
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Finances](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
