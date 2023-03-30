---
title: Configurer des modalités de paiement
description: 'Dans la version de base de Business Central, utilisez les modalités de paiement pour gérer les dates d’échéance et les escomptes de paiement.'
author: edupont04
ms.topic: conceptual
ms.search.form: 4
ms.date: 04/01/2021
ms.author: edupont
---
# Configurer des modalités de paiement

Les modalités de paiement déterminent la façon dont vous gérez les dates d’échéance et les escomptes de paiement. Vous pouvez configurer n’importe quel nombre de codes modalités de paiement et utiliser des formules date pour définir les modalités de paiement. Lorsque vous vous inscrivez pour la première fois à [!INCLUDE [prod_short](includes/prod_short.md)], la compagnie de démonstration fournit quelques méthodes de paiement que les entreprises utilisent souvent. Vous pouvez cependant en ajouter autant que nécessaire.  

Vous pouvez affecter des modalités de paiement aux clients et aux fournisseurs pour que les mêmes modalités soient toujours utilisées dans les documents achat et vente que vous créez pour eux. Si nécessaire, vous pouvez modifier les conditions du document de vente ou d’achat, par exemple si vous souhaitez qu’un client particulier vous paie dans les 7 jours au lieu des 14 jours par défaut. Cela ne modifie pas les conditions de paiement par défaut affecté au client. Les mêmes modalités de paiement sont utilisées pour les documents vente et achat.

Ensuite, lorsque vous reportez une facture, [!INCLUDE [prod_short](includes/prod_short.md)] calcule les escomptes de paiement en fonction des modalités de paiement. La date d’escompte de paiement, c’est-à-dire la dernière date à laquelle le client peut payer et recevoir un escompte sur le paiement, est également calculée à ce moment-là.  

De même, lorsque vous reportez une note de crédit, [!INCLUDE [prod_short](includes/prod_short.md)] calcule les escomptes de paiement possibles en fonction des modalités de paiement. Le système applique aux escomptes de paiement sur les notes de crédit les mêmes méthodes de calcul qu’aux escomptes de paiement sur les factures. Lorsqu’une note de crédit est affectée à une facture, le montant de l’escompte de paiement sur la note de crédit est retranché du montant de l’éventuel escompte de paiement sur la facture.  

Si vous souhaitez envoyer à vos clients des rappels de paiements en retard, vous devez configurer des niveaux et des conditions de rappel. Pour plus d’informations, voir [Configurer les niveaux et modalités de rappel](finance-setup-reminders.md).  

## Pour configurer des modalités de paiement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modalités de paiement**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

Après avoir configuré les modalités de paiement, affectez-les aux clients et fournisseurs. Vous pouvez éventuellement ajouter des modalités de paiement à vos modes de règlement.  

> [!TIP]
> Dans la version de base de [!INCLUDE [prod_short](includes/prod_short.md)], les modalités de paiement avec paiements partiels ne sont pas prises en charge. Au lieu de cela, vous devez utiliser la fonctionnalité de paiements anticipés. Pour plus d'informations, reportez\-vous à [Configuration des acomptes](finance-set-up-prepayments.md).
>
> Dans certains pays, vous *pouvez* configurer des modalités de paiement avec des paiements partiels. Pour savoir si cette fonctionnalité est prise en charge dans votre pays, consultez la section **Fonctionnalité locale** dans le volet de navigation sur le côté gauche d’un article [Microsoft Learn](about-localization.md).

## Voir aussi

[Paramétrer les modes de paiement](finance-payment-methods.md)  
[Configuration des paiements anticipés](finance-set-up-prepayments.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Vente](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]