---
title: Annuler un report en reportant une écriture inversée
description: 'Si vous trouvez une erreur dans un journal général reporté, vous pouvez utiliser l’action de contrepassation de transaction pour annuler le report avec une piste d’audit correcte.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 05/07/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Inverser des reports journal et annuler des réceptions/livraisons

L'inversion des reports journal est utile, par exemple, pour corriger les erreurs et pour effacer une ancienne écriture de régularisation avant d’en saisir une nouvelle. Une écriture inversée est identique à l’écriture d’origine, mais a un signe opposé dans le champ **Montant**. L’écriture inversée doit avoir le même numéro de document et la même date de report que l’écriture d’origine. Une fois l’écriture inversée, créez l’écriture correcte.

Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général. Une écriture ne peut être inversée qu’une fois.

Pour annuler une réception ou un report de livraison, avant qu'ils soient reportés comme facturés, vous pouvez utiliser la fonction **Annuler** sur le document reporté. Vous pouvez annuler des quantités de type **Article** et **Ressource**.

Si vous avez reporté une quantité négative incorrecte, comme un bon de commande avec un nombre d’articles incorrect, comme reçue mais non facturée, vous pouvez annuler ce report.

Si vous avez reporté une quantité positive incorrecte, comme une livraison vente ou une livraison retour achat avec un nombre d’articles incorrect, comme livrée mais pas facturée, vous pouvez annuler ce report.

## Pour inverser le report journal d'une écriture grand livre

Vous pouvez inverser des écritures sur toutes les pages **Écritures**. La procédure suivante se base sur la page **Écritures**.

> [!NOTE]
> L’écriture doit être émise depuis un report journal.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures**, puis sélectionnez le lien associé.
2. Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**.
3. Sur la page **Inverser les écritures de transaction**, choisissez l'action **Inverser**.
4. Cliquez sur **Oui** pour confirmer la contrepassation.

## Pour reporter une écriture négative  

Utilisez le champ **Correction** pour reporter un débit négatif au lieu d’un crédit, ou pour reporter un crédit négatif au lieu d’un débit sur un compte. Par défaut, le champ est disponible dans tous les journaux. Les champs **Montant débit** et **Montant crédit** comprennent l'écriture initiale et l'écriture corrigée. Ces champs n'ont aucune incidence sur le solde du compte.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux**, puis choisissez le lien associé.  
2. Dans le champ **Nom de la feuille**, sélectionnez le nom de feuille requis.  
3. Entrez les informations dans les champs pertinents.  
4. Dans la ligne journal que vous souhaitez activer pour les écritures négatives, sélectionnez la case à cocher **Correction**.  
5. Pour reporter le journal, sélectionnez l'action **Reporter**, puis le bouton **Oui**.

## Pour annuler une quantité sur une réception d’achat reportée  

Les étapes suivantes décrivent comment annuler une réception reportée d’articles ou de ressources. La procédure est identique pour des livraisons reportées.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réceptions achat reportées**, puis sélectionnez le lien associé.  
2. Ouvrez la réception reportée à annuler.  
3. Sélectionnez la ligne ou les lignes à annuler.  
4. Choisissez l'action **Annuler réception**.

Une ligne de correction est ajoutée sous la ligne de la réception sélectionnée. Si la quantité a été reçue dans une réception entrepôt, une ligne de correction est ajoutée sur la réception entrepôt reportée.  

Les champs **Quantité reçue** et **Qté reçue non facturée** de la commande achat associée sont remis à zéro.

## Pour annuler, puis effectuer à nouveau le report de quantité sur une livraison retour reportée

Les étapes suivantes décrivent comment :

* Annuler une livraison de retour d’articles ou de ressources reportée.
* Reportez à nouveau le retour achat avec une nouvelle quantité.

La procédure est identique pour les réceptions retour reportées.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons retour reportées**, puis sélectionnez le lien associé.  
2. Ouvrez la livraison de retour reportée à annuler.
3. Sélectionnez la ligne ou les lignes à annuler.  

4. Choisissez l'action **Annuler livraison retour**.  

    Une ligne de correction est insérée dans le document reporté et les champs **Qté retour livrée** et **Livraison retour non facturée** du retour sont remis à zéro.  

    Retournez à présent au retour achat pour un nouveau report.  

5. Sur la page **Livraison retour reportée**, notez le numéro situé dans le champ **N° retour** .  
6. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Retours achat**, puis sélectionnez le lien associé.  
7. Ouvrez la commande retour concernée, puis sélectionnez l'action **Rouvrir**.  
8. Corrigez l'écriture dans le champ **Quantité** et reportez à nouveau le retour achat.  

[!INCLUDE [rev-general-journal](includes/rev-general-journal.md)]

## Inverser une écriture client et fournisseur avec une écriture gain ou perte réalisé(e)

Vous pouvez utiliser l’action **Inverser la transaction** pour annuler les paiements qui ont été affectés à des écritures provenant de devises étrangères et qui ont été ajustés à l’aide du traitement en lot Ajustement du taux de change. La fonctionnalité est compatible à la fois avec les achats et les ventes.

Voici un scénario simple qui illustre son fonctionnement :

1. Reportez une facture vente pour un client en utilisant une devise étrangère.
2. Ajustez le taux de change pour cette devise.
3. Reportez un paiement affecté à la facture.
4. Annulez l'affectation et inversez la transaction de paiement, par exemple, à partir de la page **Écritures client**.

## Voir aussi .

[Annuler le report d’assemblage](assembly-how-to-undo-assembly-posting.md)  
[Reporter directement des transactions dans le grand livre](finance-how-post-transactions-directly.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]