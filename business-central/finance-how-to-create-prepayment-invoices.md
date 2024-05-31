---
title: Créer des factures de paiement anticipé
description: 'Traitez les situations où votre fournisseur ou vous-même exigez un paiement anticipé. Utilisez les pourcentages par défaut pour chaque ligne vente ou achat, ou ajustez le montant en fonction si nécessaire.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bhielse
ms.topic: how-to
ms.date: 10/04/2023
ms.custom: bap-template
ms.search.form: '42, 50, 9305, 9307'
ms.service: dynamics-365-business-central
---
# <a name="create-prepayment-invoices"></a>Créer des factures de paiement anticipé

Si vous demandez aux clients de payer avant de livrer leur commande, vous pouvez utiliser les fonctionnalités de paiement anticipé. Il en va de même si votre fournisseur vous demande de payer avant de vous livrer une commande.  

Vous pouvez lancer le traitement du paiement anticipé lorsque vous créez un document vente ou un bon de commande. Le pourcentage paiement anticipé par défaut pour un article donné sur la commande, ou pour le client ou le fournisseur, sera automatiquement inclus dans la facture de paiement anticipé résultante. Vous pouvez également spécifier un pourcentage paiement anticipé pour l'ensemble du document.

Après avoir créé un document de vente ou un bon de commande, vous pouvez créer une facture paiement anticipé à lui associer. Utilisez les pourcentages par défaut pour chaque ligne vente ou achat, ou ajustez le montant en fonction si nécessaire. Par exemple, vous pouvez spécifier un montant total pour la commande entière.  

La procédure suivante décrit comment facturer un paiement anticipé pour un document de vente. La procédure est identique pour les bons de commande.  

## <a name="to-create-a-prepayment-invoice"></a>Pour créer une facture paiement anticipé

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Créez un document de vente pour le client approprié. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  

    Sur le raccourci **Paiement anticipé**, le champ **% paiement anticipé** spécifie le pourcentage à utiliser pour calculer le montant paiement anticipé. Si un pourcentage de paiement anticipé par défaut figure sur la fiche client, le champ est renseigné automatiquement. Vous pouvez modifier le pourcentage. <!--This percentage is applied to lines where the item on that line does not already specify a prepayment percentage. The prepayment percentage is only copied from the header to lines that do not copy the default prepayment percentage from the item.-->  

    Choisissez le champ **Compresser paiement anticipé** si vous souhaitez créer des lignes sur la facture de paiement anticipé qui combinent des lignes du document de vente si :  

    - Elles ont le même compte du grand livre pour les paiements anticipés,comme déterminé par la configuration de report générale.  
    - Elles sont les mêmes dimensions.  

    Si vous souhaitez spécifier une facture paiement anticipé avec une ligne pour chaque ligne document de vente à laquelle un pourcentage de paiement anticipé est associé, ne choisissez pas le champ **Compresser paiement anticipé**.  

    La date d'échéance du paiement anticipé est calculée automatiquement en fonction de la valeur du **Code modalités de paiement anticipé**.

    > [!NOTE]
    > Lorsque certaines lignes d’une facture nécessitent un paiement anticipé de 100 % et d’autres non, et qu’une TVA s'applique sur le compte de paiement anticipé, le montant arrondi peut entraîner une erreur lorsque vous créez une facture de paiement anticipé. L’erreur se produit car le montant de la facture de paiement anticipé est supérieur aux montants des lignes du document. Pour résoudre le problème, modifiez les montants d’une ou de toutes les lignes nécessitant un paiement anticipé de 100 %. Le changement recalculera l’arrondissement du montant de la TVA et utilisera la différence d’arrondissement cumulée sur la dernière ligne modifiée.
    >
    > Deux autres façons de résoudre le problème sont les suivantes :
    >
    > * Créez un groupe de report produit TVA et une configuration de report TVA distincts avec un identificateur de TVA distinct, et utilisez-les pour les articles ou les lignes qui nécessitent un paiement anticipé de 100 %. L’arrondissement est effectué pour chaque identificateur de TVA, de sorte qu’un arrondissement séparé sera effectué pour les articles affectés au groupe de report produit TVA.
    > * Utilisez une facture distincte pour les articles ou les lignes nécessitant ou non des paiements anticipés à 100 %.

3. Renseignez les lignes vente.  

    Si vous avez spécifié un pourcentage paiement anticipé par défaut soit pour le client, soit sur le raccourci **Paiement anticipé** sur ce document, cette valeur est copiée sur chaque ligne. Vous pouvez modifier le contenu du champ **% acompte** sur la ligne.  

    > [!TIP]
    > Si vous ne voyez pas le champ **% paiement anticipé**, vous pouvez l’ajouter via la personnalisation.  Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

4. Pour visualiser le montant du paiement anticipé total, choisissez l'action **Statistiques**.

    Pour ajuster le montant de paiement anticipé total de la commande, vous pouvez modifier le contenu du champ **Montant paiement anticipé** de la page **Statistiques document de vente**.  

    Si le champ **Prix TVA comprise** est sélectionné, le champ **Montant acompte TTC** est modifiable.  

    Si vous modifiez la valeur du champ **Montant paiement anticipé**, le montant est réparti de façon proportionnelle entre toutes les lignes, à l’exception de celles qui contiennent la valeur **0** dans le champ **% paiement anticipé**.  

5. Pour effectuer un rapport de test avant de reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis choisissez **Rapport de test de paiement anticipé**.  
6. Pour reporter la facture de paiement anticipé, sélectionnez l'action **Paiement anticipé**, puis l'action **Reporter facture paiement anticipé**.  

    Pour reporter et imprimer la facture paiement anticipé, choisissez l'action **Reporter et imprimer facture paiement anticipé**.  

Vous pouvez émettre des factures paiement anticipé supplémentaires pour la commande. Pour émettre une autre facture, augmentez le montant du paiement anticipé sur une ou plusieurs lignes, ajustez la date document si nécessaire, puis reportez la facture paiement anticipé. Une nouvelle facture est créée pour la différence entre les montants de paiement anticipé facturés jusqu'ici et le nouveau montant de paiement anticipé.  

> [!NOTE]  
> Si vous êtes situé en Amérique du Nord, vous ne pouvez pas modifier le pourcentage de paiement anticipé après la facture paiement anticipé reportée. Cela est empêché dans la version nord\-américaine de [!INCLUDE[prod_short](includes/prod_short.md)], car le calcul de la taxe sur les ventes est sinon incorrect.  

 Lorsque vous êtes prêt à reporter le reste de la facture, reportez-le comme n'importe quelle facture. Le montant du paiement anticipé est automatiquement déduit du montant dû.  

## <a name="update-the-status-of-prepaid-orders-and-invoices-automatically"></a>Mettre à jour automatiquement l'état des commandes prépayées et des factures

Vous pouvez accélérer le traitement des commandes et des factures en configurant des entrées de file d’attente des travaux qui mettent automatiquement à jour l'état de ces documents. Lorsqu’une facture de paiement anticipé est payée, les entrées de la file d’attente des travaux peuvent changer automatiquement l'état du document de **Paiement anticipé en attente** sur **Validé**. Lorsque vous configurez les entrées de la file d’attente des travaux, les codeunits que vous devrez utiliser sont **384 Mise à jour En attente Paiement anticipé Ventes** et **384 Mise à jour En attente Paiement anticipé Achats**. Nous vous recommandons de programmer les entrées pour qu’elles s’exécutent fréquemment, par exemple, toutes les minutes. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## <a name="see-also"></a>Voir aussi .

[Facturation de paiements anticipés](finance-invoice-prepayments.md)  
[Procédure pas à pas : configuration et facturation d'acomptes](walkthrough-setting-up-and-invoicing-sales-prepayments.md)  
[Finance](finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Personnaliser votre espace de travail](ui-personalization-user.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
