---
title: Corriger ou annuler une facture vente reportée
description: 'Cette rubrique décrit comment corriger, annuler, ou annuler une facture vente reportée et affecter un note de crédit vente.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'undo, credit memo, return'
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="correct-or-cancel-unpaid-sales-invoices"></a><a name="correct-or-cancel-unpaid-sales-invoices"></a>Corriger ou annuler des factures vente impayées

Vous pouvez corriger ou annuler une facture vente reportée impayée, à condition qu’elle n’ait pas été entièrement livrée. Cela est utile si vous faites une erreur ou si le client demande une modification avant l’exécution de la livraison. Dans tous les autres scénarios, nous vous recommandons de créer directement une note de crédit vente de correction. Pour plus d’informations, consultez [Créer une note de crédit vente à partir d’une facture vente reportée](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).  

> [!NOTE]  
> Une fois la facture vente reportée entièrement ou partiellement payée, vous ne pouvez pas la corriger ou l'annuler à partir de celle-ci. Au lieu de cela, vous devez créer manuellement une note de crédit vente pour annuler la vente et rembourser le client, géré de manière facultative avec un retour vente. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).

La différence entre l’annulation ou la correction d’une facture vente reportée qui n’a pas été payée ou livrée est décrite dans le tableau suivant.

| Action | Description |
| --- | --- |
| **Annuler** |La facture vente reportée est annulée. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases **Annulée** et **Payée** sont cochées. |
| **Corriger** |La facture vente reportée est annulée. Une nouvelle facture vente avec les mêmes informations est créée, sauf si le document de vente reporté a été reporté à partir d’un document de vente. Dans ce cas, nous vous suggérons d’annuler la facture vente reportée à la place, puis d’effectuer la correction et de poursuivre le processus de vente à partir du document de vente d’origine. <br/><br/>La nouvelle facture vente a un numéro différent de celui de la facture vente initiale. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases **Annulée** et **Payée** sont cochées. |

Lorsque vous corrigez ou annulez une facture vente reportée, la note de crédit vente de correction est affectée à toutes les écritures du grand livre et de l'inventaire physique créées lors du report de la facture vente initiale. Cette action inverse la facture vente reportée dans vos enregistrements financiers et laisse la note de crédit vente reportée de correction pour votre piste de vérification.  

> [!TIP]
> Si vous avez reporté une facture de paiement anticipé pour une facture vente que vous corrigez ou annulez ensuite, vous devez également corriger ou annuler le paiement anticipé. Pour plus d'informations, voir [Corriger des paiements anticipés](finance-how-to-correct-prepayments.md).

## <a name="to-cancel-a-posted-sales-invoice"></a><a name="to-cancel-a-posted-sales-invoice"></a>Pour annuler une facture vente reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la facture vente reportée à annuler.

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas annuler la facture vente validée car elle a déjà été annulée ou corrigée.
3. Sur la page **Facture vente reportée** sélectionnez l'action **Annuler**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.
4. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

### <a name="partial-invoice-posting-also-supported"></a><a name="partial-invoice-posting-also-supported"></a>Report partiel de facture également pris en charge

Si l'annulation est liée à un report de facture partiel, la ligne de document de vente d'origine est mise à jour pour refléter la quantité facturée annulée. Les champs **Qté à facturer** et **Qté facturée** de la ligne de document de vente associée sont réinitialisés et affichent les valeurs avant le report partiel.

## <a name="to-correct-a-posted-sales-invoice"></a><a name="to-correct-a-posted-sales-invoice"></a>Pour corriger une facture vente reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la facture vente reportée à corriger.

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas corriger la facture vente validée car elle l'a déjà été, ou a été annulée.
3. Sur la page **Facture vente reportée** sélectionnez l'action **Corriger**.  

    > [!NOTE]
    > Si la facture vente a été reportée à partir d’un document de vente, nous vous recommandons d’*annuler* cette facture vente, puis de traiter la correction à partir du document de vente d’origine. Si le document de vente d’origine a été supprimé, par exemple s'il a été entièrement livré, vous pouvez créer un nouveau document de vente en utilisant l’action **Copier le document**. Pour plus d’informations, consultez [Créer une note de crédit vente en copiant une facture vente reportée](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-by-copying-a-posted-sales-invoice).
4. Une nouvelle facture vente avec les mêmes informations et dans laquelle vous pouvez apporter une correction est créée. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale.
5. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

## <a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/ship-invoice-items-dynamics-365-business-central/) associée

## <a name="see-also"></a><a name="see-also"></a>Voir aussi .

[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
