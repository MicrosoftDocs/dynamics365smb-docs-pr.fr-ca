---
title: Utilisation de l’’extension PayPal Payments Standard
description: Cet article décrit comment utiliser l’extension standard pour permettre aux clients d’effectuer des paiements avec Paypal.
author: brentholtorf
ms.author: bholtorf
ms.topic: conceptual
ms.search.keywords: 'app, add-in, manifest, customize'
ms.search.form: '1070, 1071, 1073, 1074'
ms.date: 07/09/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="the-paypal-payments-standard-extension"></a>Extension PayPal Payments Standard

L’extension PayPal Payments Standard peut vous aider à augmenter vos niveaux de service client en permettant à vos clients de payer plus facilement leurs factures.

Au lieu de collecter les paiements par virement bancaire ou par crédit Cartes, les clients peuvent payer via leur compte PayPal. Lorsque vous envoyez une facture vente par courriel, le corps du message et le document PDF en pièce jointe contiennent un lien Paypal. Si le client choisit le lien, la page de service de son compte PayPal s’ouvre et affiche les détails du paiement. Le client peut ensuite payer la facture comme tout autre paiement Paypal.

Le service PayPal Payments Standard fournit les avantages suivants :

* Les paiements client arrivent plus rapidement sur votre compte bancaire.
* Les clients disposent de davantage de méthodes de paiement de leurs factures.
* Paypal offre un service de paiement fiable, que les clients apprécient plutôt que de devoir saisir leurs données de carte de crédit sur des sites Web.
* Paypal propose plusieurs méthodes de gestion des paiements, y compris le traitement de cartes de crédit, les comptes Paypal, ainsi que d'autres sources.
* Le lien Paypal peut être ajouté aux documents vente automatiquement ou manuellement par l'utilisateur.
* Le service PayPal Payments Standard n’implique aucun frais mensuels ni de frais de configuration.
* Étant donné qu’il s’agit d’une extension, vous pouvez facilement activer le service PayPal Payment Standard si votre activité l’exige et au moment de votre choix.  

Pour en savoir plus sur la configuration de l’extension, accédez à [Activer le paiement client via PayPal](sales-how-enable-payment-service-extensions.md).

## <a name="register-payments-automatically-for-business-accounts"></a>Enregistrez automatiquement les paiements pour les comptes professionnels

[!INCLUDE [prod_short](includes/prod_short.md)] peut enregistrer automatiquement les paiements si vous disposez d’un compte Business Merchant pour la plateforme de commerce PayPal. Lorsque vos clients utilisent le lien PayPal pour payer une facture, [!INCLUDE [prod_short](includes/prod_short.md)] publie les entrées et Fermer le document.

Pour utiliser cette fonctionnalité, sur la page **Configuration de l’enregistrement des paiements** dans [!INCLUDE [prod_short](includes/prod_short.md)], activez l’option **Enregistrer automatiquement les paiements.** activez et vérifiez les comptes que vous utiliserez pour les paiements. Si vous décidez que vous ne souhaitez pas enregistrer automatiquement les paiements, vous pouvez le désactiver à nouveau.

> [!TIP]
> Les développeurs peuvent utiliser des comptes sandbox pour tester la configuration. Pour ce faire, modifiez l’URL PayPal en **sandbox.paypal.com**. [!INCLUDE [prod_short](includes/prod_short.md)] utilise la notification de paiement instantanée (IPN) de PayPal via notify_url.

## <a name="see-also"></a>Voir aussi .

[Personnalisation de [!INCLUDE[prod_short](includes/prod_short.md)] à l'aide des extensions](ui-extensions.md)  
[Définition des ventes](sales-setup-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
