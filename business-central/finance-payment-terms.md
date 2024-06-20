---
title: Configurer des modalités de paiement
description: Utilisez les modalités de paiement pour gérer les dates d'échéance et les escomptes de paiement.
author: brentholtorf
ms.topic: conceptual
ms.search.form: '4,'
ms.date: 09/05/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Configurer des modalités de paiement

Les modalités de paiement déterminent la façon dont vous gérez les dates d’échéance et les escomptes de paiement. Vous pouvez configurer n’importe quel nombre de codes modalités de paiement et utiliser des formules date pour définir les modalités de paiement. Lorsque vous vous inscrivez pour la première fois à [!INCLUDE [prod_short](includes/prod_short.md)], la compagnie de démonstration fournit quelques méthodes de paiement que les entreprises utilisent souvent. Vous pouvez cependant en ajouter autant que nécessaire.  

Si vous affectez des modalités de paiement aux clients et aux fournisseurs, les mêmes conditions sont toujours utilisées dans les documents achat et vente que vous créez pour eux. Les dates des documents vente et achat, et non leurs dates de report, sont utilisées pour calculer les dates d’échéance des paiements. Si nécessaire, vous pouvez modifier les conditions du document de vente ou d’achat, par exemple si vous souhaitez qu’un client particulier vous paie dans les 7 jours au lieu des 14 jours par défaut. La modification des conditions sur le document ne modifie pas les conditions de paiement par défaut attribuées au client. Les mêmes modalités de paiement sont utilisées pour les documents vente et achat.

Lorsque vous reportez une facture, [!INCLUDE [prod_short](includes/prod_short.md)] calcule les escomptes de paiement en fonction des modalités de paiement. La date d’escompte de paiement est la dernière date à laquelle le client peut obtenir un escompte. La date est également calculée lorsque vous reportez une facture.  

De même, lorsque vous reportez une note de crédit, [!INCLUDE [prod_short](includes/prod_short.md)] calcule les escomptes de paiement en fonction des modalités de paiement. Il calcule l'escompte sur les notes de crédit comme pour les escomptes sur les factures. Lorsque vous appliquez une note de crédit à une facture, [!INCLUDE [prod_short](includes/prod_short.md)] réduit le montant d'escompte de la facture du montant d'escompte de la note de crédit.  

Si vous souhaitez envoyer à vos clients des rappels de paiements en retard, vous devez configurer des niveaux et des conditions de rappel. Pour en savoir plus sur les rappels, reportez-vous à [Configurer des niveaux et modalités de rappel](finance-setup-reminders.md).  

## Pour configurer des modalités de paiement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de paiement**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

Après avoir configuré les modalités de paiement, affectez-les aux clients et fournisseurs. Vous pouvez éventuellement ajouter des modalités de paiement à vos modes de règlement.  

> [!TIP]
> Dans la version de base de [!INCLUDE [prod_short](includes/prod_short.md)], les modalités de paiement avec paiements partiels ne sont pas prises en charge. Au lieu de cela, vous devez utiliser la fonctionnalité de paiements anticipés. Pour en savoir plus sur les paiements anticipés, reportez-vous à [Configurer des paiements anticipés](finance-set-up-prepayments.md).
>
> Dans certains pays/régions, vous *pouvez* configurer des modalités de paiement avec des paiements partiels. Pour savoir si cette fonctionnalité est prise en charge dans votre pays/région, accédez à la section **Fonctionnalité locale** dans le sommaire sur le côté gauche d’un article [Microsoft Learn](about-localization.md).

## Voir aussi

[Configuration des modes de règlement](finance-payment-methods.md)  
[Configuration des paiements anticipés](finance-set-up-prepayments.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Vente](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
