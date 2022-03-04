---
title: Annuler un report en reportant une écriture de contrepassation
description: Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.search.form: 20, 25, 29, 38, 202, 5912,
ms.date: 07/22/2021
ms.author: edupont
ms.openlocfilehash: 2a9689db234280c2bcca5e32ade2a82488c15de5
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8147736"
---
# <a name="reverse-journal-postings-and-undo-receiptsshipments"></a>Inverser des reports journal et annuler des réceptions/livraisons

L’inversion des reports journal n’est pas seulement utilisée pour corriger les erreurs, mais elle peut également être utilisée pour effacer une ancienne écriture de régularisation avant d’en saisir une nouvelle, par exemple. Vous sélectionnez l’écriture et créez une écriture de contrepassation (écritures identiques aux écritures originales mais avec le signe opposé dans le champ du montant) portant le même numéro de document et la même date de report que l’écriture d’origine. Une fois l'écriture inversée, créez l'écriture correcte.

Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général. Une écriture ne peut être inversée qu'une seule fois.

Pour annuler une réception ou un report de livraison, avant qu'ils soient reportés comme facturés, vous pouvez utiliser la fonction **Annuler** sur le document reporté. Vous pouvez annuler des quantités de type **Article** et **Ressource**.

Si vous avez effectué un report de quantité négative incorrect, comme un bon de commande avec, par exemple, un nombre d'articles incorrect et que vous l'avez reporté comme étant reçu (mais non facturé), vous pouvez annuler ce report.

Si vous avez effectué un report de quantité positive incorrect, comme une livraison vente ou une livraison retour achat avec un nombre d'articles incorrect et que vous l'avez reportée comme étant livrée (mais non facturée), vous pouvez annuler ce report.   

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a>Pour inverser le report journal d'une écriture grand livre
Vous pouvez inverser des écritures sur toutes les pages **Écritures**. La procédure suivante se base sur la page **Écritures**.
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures**, puis sélectionnez le lien associé.
2. Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**. Notez qu'elle doit provenir d'un report journal.
3. Sur la page **Inverser les écritures de transaction**, choisissez l'action **Inverser**.
4. Choisissez le bouton **Oui** dans le message de confirmation.

> [!NOTE]
> Vous ne pouvez pas inverser des écritures qui ont été reportées avec des informations provenant d'un travail ou qui présentent des gains et pertes réalisés au sein de la même transaction.

## <a name="to-post-a-negative-entry"></a>Pour reporter une écriture négative  
Vous pouvez utiliser le champ **Correction** pour reporter un débit négatif au lieu d'un crédit, ou pour reporter un crédit négatif au lieu d'un débit sur un compte. Pour répondre aux exigences légales, ce champ est visible par défaut sur tous les journaux. Les champs **Montant débit** et **Montant crédit** comprennent l'écriture initiale et l'écriture corrigée. Ces champs n'ont aucune incidence sur le solde du compte.  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux**, puis choisissez le lien associé.  
2.  Dans le champ **Nom de la feuille**, sélectionnez le nom de feuille requis.  
3.  Entrez les informations dans les champs pertinents.  
4.  Dans la ligne journal que vous souhaitez activer pour les écritures négatives, sélectionnez la case à cocher **Correction**.  
5.  Pour reporter le journal, sélectionnez l'action **Reporter**, puis le bouton **Oui**.

## <a name="to-undo-a-quantity-posting-on-a-posted-purchase-receipt"></a>Pour annuler un report de quantité sur une réception d'achat reportée  
La procédure d'annulation d'une réception reportée d'articles ou de ressources est décrite ci-après. La procédure est identique pour des livraisons reportées.

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réceptions achat reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la réception reportée à annuler.  
3.  Sélectionnez la ligne ou les lignes à annuler.  
4.  Choisissez l'action **Annuler réception**.

Une ligne de correction est insérée sous la ligne de la réception sélectionnée. Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est insérée sur la réception entrepôt reportée.  

Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.

## <a name="to-undo-and-then-redo-a-quantity-posting-on-a-posted-return-shipment"></a>Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée
La procédure d'annulation d'une livraison retour reportée d'articles ou de ressources et de nouveau report du retour achat avec une nouvelle quantité est décrite ci-après. La procédure est identique pour les réceptions retour reportées.

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons retour reportées**, puis sélectionnez le lien associé.  
2.  Ouvrez la livraison de retour reportée à annuler.
3. Sélectionnez la ligne ou les lignes à annuler.  

4.  Choisissez l'action **Annuler livraison retour**.  

    Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.  

    Retournez à présent au retour achat pour un nouveau report.  

5.  Sur la page **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour** .  
6.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Retours achat**, puis sélectionnez le lien associé.  
7.  Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.  
8.  Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.  

## <a name="see-also"></a>Voir aussi

[Annuler le report d'assemblage](assembly-how-to-undo-assembly-posting.md)  
[Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md)  
[Utilisation de journaux généraux](ui-work-general-journals.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]