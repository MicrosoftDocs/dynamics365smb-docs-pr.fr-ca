---
title: Facturer des ventes
description: 'Décrit comment créer une facture vente, un document de vente ou, enregistrer votre entente avec un client pour vendre des produits à des conditions spécifiques.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'bill, sale, invoice, order'
ms.search.form: '43, 48, 9301'
ms.date: 09/01/2022
ms.author: edupont
---
# Facturer des ventes

Vous pouvez généralement créer un document de vente ou une facture vente pour enregistrer votre entente avec un client pour vendre certains produits selon certaines modalités de paiement et de livraison.  

Cependant, vous devez utiliser un document de vente au lieu d’une facture vente si vous :  

* Vous devez livrer uniquement une partie d’une quantité de commande, par exemple, si la quantité totale n’est pas disponible.  
* Livrez des produits après avoir reporté les factures vente correspondantes.
* Vendez des articles que votre fournisseur fournit directement à votre client (une livraison directe). En savoir plus sur [Créer des livraisons directes](sales-how-drop-shipment.md).  

Pour toutes les autres situations, les documents de vente et les factures vente fonctionnent de la même manière. Pour plus d’informations sur l’utilisation des documents de vente, voir [Vendre des produits](sales-how-sell-products.md).

Vous pouvez négocier avec le client en créant d’abord un devis, que vous pouvez convertir en facture vente ou en commande vente lorsque vous êtes d’accord sur la vente. En savoir plus, [Créer des devis](sales-how-make-offers.md).

## Créer des factures vente

Si le client décide d'acheter, vous reportez la facture vente pour créer les écritures quantité et valeur associées. Lorsque vous reportez la facture vente, vous pouvez également envoyer par courriel le document en pièce jointe au format PDF. Vous pouvez faire en sorte que le corps du message soit prérempli avec un résumé des informations de facturation et de paiement, par exemple un lien vers Paypal. Pour plus d'informations, voir [Envoyer des documents par courriel](ui-how-send-documents-email.md). Lorsque le client paie la facture, vous pouvez enregistrer ce paiement de différentes manières, selon la taille et les flux de travail favoris de votre organisation. En savoir plus sur la section [Enregistrement des paiements](#registering-payments).  

Les fiches article peuvent être de type **Inventaire**, **Service** et **Hors inventaire** pour spécifier si l’article est une unité d'inventaire physique, une unité de temps de travail ou une unité physique qui n’est pas conservée dans l'inventaire. En savoir plus sur [Enregistrer de nouveaux articles](inventory-how-register-new-items.md). Le processus de facture vente est identique pour les trois types d'article.

Vous pouvez remplir les champs relatifs au client sur la facture vente de deux façons selon que le client est déjà enregistré ou non. Reportez-vous à l’étape 2 de la procédure ci-dessous.

### Pour créer une facture vente :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente**, puis sélectionnez le lien associé.  
2. Dans le champ **Client**, entrez le nom d'un client existant. Si, toutefois, le client est nouveau et n’est donc pas enregistré, suivez ces étapes pour remplir les informations client standard sur la page **Facture vente** :

    1. Dans le champ **Nom du client**, entrez le nom du nouveau client.
    2. Dans la boîte de dialogue d’enregistrement du nouveau client, cliquez sur le bouton **Oui**.
    3. Sur la page **Sélectionnez un modèle pour un nouveau client**, sélectionnez un modèle sur lequel baser la nouvelle fiche client, puis cliquez sur **OK**.
    4. Une nouvelle fiche client affiche des informations sur le modèle client sélectionné. Renseignez les champs restants. En savoir plus sur [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).  
    5. Lorsque vous avez terminé la fiche client, choisissez **Fermer** pour revenir à la page **Facture vente**.

   Plusieurs champs de la facture vente sont désormais renseignés avec les informations que vous avez spécifiées sur la nouvelle fiche client.  
3. Renseignez les champs restants de la page **Facture vente**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > Si vous autorisez le client à payer immédiatement, par exemple, en liquide ou par PayPal, renseignez le champ **Code mode de règlement**. Le paiement est ensuite enregistré dès que vous reportez la facture vente. Si vous sélectionnez *Espèces*, le paiement est enregistré dans un compte de contrepartie spécifié.

    Vous êtes maintenant prêt à renseigner le raccourci **Lignes** pour les produits que vous vendez au client ou pour toute transaction avec le client que vous souhaitez enregistrer dans un compte du grand livre.

4. Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à reporter pour le client sur la ligne vente.
   * Si vous avez défini des lignes vente récurrentes pour le client, tel qu’un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l’intermédiaire de l’action **Extraire les lignes vente récurrentes**.
5. Dans le champ **N°**, sélectionnez un enregistrement à valider en fonction de la valeur du champ **Type**.

    Laissez le champ **N°** vide dans les cas suivants :

    * Si la ligne est destinée à un commentaire. Saisissez le commentaire dans le champ **Description**.
    * Si la ligne est destinée à un article de catalogue. Sélectionnez l'action **Sélectionner articles de catalogue**. En savoir plus sur [Utiliser des éléments de catalogue](inventory-how-work-nonstock-items.md).

6. Dans le champ **Quantité**, entrez le nombre d’unités du produit, de frais ou de la transaction que la ligne enregistre pour le client.  

    > [!NOTE]  
    > Si l’article est de type **Service** ou si le champ **Type** contient **Ressource**, la quantité est alors une unité de temps, telle que les heures, comme indiqué dans le champ **Code unité de mesure** de la ligne. Pour plus d’informations, voir [Configuration des unités de mesure article](inventory-how-setup-units-of-measure.md).

    La valeur du champ **Montant ligne** est calculée comme suit : *Prix unitaire* x *Quantité*.  

    Le prix et les montants ligne sont affichés avec ou sans la taxe de vente en fonction de la valeur que vous avez sélectionnée dans le champ **Prix incluant les taxes** de la fiche client.  
7. Si vous souhaitez accorder une remise, saisissez un pourcentage dans le champ **% remise ligne**. La valeur du champ **Montant ligne** est mise à jour en conséquence.  

    Si des prix article spéciaux sont définis sur le raccourci **Prix vente et remises ligne vente** dans la fiche client ou article, le prix et le montant de la ligne vente sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).  
8. Répétez les étapes 4 à 7 pour chaque produit ou frais que vous souhaitez facturer au client.

    Les champs totaux sous les lignes sont automatiquement mis à jour lorsque vous créez ou modifiez des lignes pour afficher les montants qui seront reportés dans les livres.

    > [!NOTE]
    > Dans de très rares cas, les montants reportés peuvent différer de ce qui est affiché dans les champs des totaux. Cela est généralement dû aux calculs d'arrondissement par rapport à la TVA ou à la taxe de vente.<br /><br />Pour vérifier les montants qui seront réellement reportés, vous pouvez utiliser la page **Statistiques**, qui tient compte des calculs d’arrondissement. Aussi, si vous choisissez l'action **Libérer**, les champs de totaux seront mis à jour pour inclure les calculs d’arrondissement.
9. Dans le champ **Montant escompte facture sans TVA**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.

    Si vous avez défini des escomptes facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% escompte facture** si les critères d'escompte sont réunis, et le montant associé est inséré dans le champ **Montant escompte facture sans TVA**. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).

10. Lorsque les lignes facture vente sont renseignées, sélectionnez l'action **Valider et envoyer**.  

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode de réception de documents par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. En savoir plus, [Configurer des profils d’envoi de documents](sales-how-setup-document-send-profiles.md).

Les écritures article et client associées sont à présent créées dans votre système, et la facture vente est sortie en tant que document au format PDF. La facture vente est supprimée de la liste des factures vente et remplacée par un nouveau document dans la liste des factures vente reportées.  

### Calcul d’escomptes facture pour des ventes

[!INCLUDE [sales-invoice-discounts](includes/sales-invoice-discounts.md)]

## Factures reportées

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

Vous pouvez facilement corriger ou annuler une facture vente reportée avant qu'elle ne soit payée. Cela est utile si vous souhaitez corriger une erreur de saisie, ou si le client demande une modification tôt dans le processus de commande. En savoir plus, [Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md) Si la facture vente reportée est payée, vous devez créer une note de crédit vente pour inverser la vente. En savoir plus, [Traiter les retours ou annulations des ventes](sales-how-process-sales-returns-cancellations.md)  

[Ouvrir la liste des **factures vente reportées**](https://businesscentral.dynamics.com/?page=143) dans [!INCLUDE [prod_short](includes/prod_short.md)].

## Enregistrement des paiements

Selon les besoins de votre entreprise, vous pouvez être payé et enregistrer ce paiement de diverses manières : manuellement, automatiquement, et via des services de paiement.  

Vous pouvez traiter les paiements directement depuis la fiche client. Utilisez l'action **Enregistrer les paiements client** pour obtenir un aperçu des factures impayées de ce client. Ensuite, marquez la facture comme payée entièrement ou partiellement. Ce rapprochement des paiements traite les paiements de vos clients en faisant correspondre les montants perçus sur votre compte bancaire avec les factures vente impayées associées, puis valide les paiements. Pour plus d’informations, reportez-vous à la section [Pour rapprocher les paiements individuellement](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md#to-register-customer-payments-individually).  

Dans les environnements d’entreprise où le client paie un certain temps après la livraison, conformément aux modalités de paiement, une facture vente reportée reste ouverte (impayée) jusqu’à ce que le département Comptabilité client vérifie la réception du paiement et affecte le paiement à la facture vente reportée. Cela peut être effectué manuellement ou automatiquement. Pour plus d'informations, voir [Rapprocher les paiements clients avec le journal des encaissements ou les écritures client](receivables-how-apply-sales-transactions-manually.md) et [Rapprocher les paiements à l'aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md).  

Dans les environnements d'entreprise où le client paie immédiatement, par exemple par PayPal ou en espèces, le paiement est enregistré immédiatement lorsque vous reportez la facture vente, c'est-à-dire la facture vente reportée est fermée comme entièrement affectée. Vous sélectionnez la méthode appropriée dans le champ **Code mode de paiement** du document de vente. Pour les paiements électroniques, tels que PayPal, vous devez également renseigner le champ **Service de paiement**. En savoir plus, [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).

Vous pouvez même créer des factures à paiement direct pour les clients non enregistrés en configurant une fiche « client en espèces », vers laquelle vous pointez sur la facture vente. En savoir plus sur [Configurer les clients effectuant un achat au comptoir](finance-how-to-set-up-cash-customers.md).  

> [!TIP]
> Si vous souhaitez envoyer à vos clients des rappels de paiements en retard, vous devez configurer des niveaux et des conditions de rappel. Pour plus d’informations, voir [Configurer les conditions et niveaux de rappel](finance-setup-reminders.md).  

## Numéros de document externe

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Voir la [formation Microsoft](/training/modules/invoicing-customers-dynamics-365-business-central/index) associée.

## Voir aussi .

[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Imprimer la liste des prélèvements](sales-how-print-picking-list.md)  
[Stock](inventory-manage-inventory.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Facturation en vrac à partir de Microsoft Bookings dans Business Central](finance-bookings.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
