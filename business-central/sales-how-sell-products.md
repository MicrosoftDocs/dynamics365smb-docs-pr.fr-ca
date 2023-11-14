---
title: Créer un document de vente client et vendre des produits
description: Décrit comment créer un document de vente pour enregistrer votre entente avec un client pour vendre ou commercialiser des produits à des conditions spécifiques.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'trade, partial deliveries, customer sales order, shipping advice, partial shipments,'
ms.search.form: '42, 48, 9305'
ms.date: 09/02/2022
ms.author: bholtorf
---
# Vente de produits avec un document de vente client

Cet article fournit des conseils aux utilisateurs sur le moment d’utiliser un document de vente plutôt qu’une simple facture. Si votre processus de vente exige que vous ne livriez que partiellement une commande, par exemple si la quantité totale n’est pas disponible d’un coup, vous devez traiter cette vente en créer un document de vente.

Vous devez également utiliser les documents de vente si vous commercialisez des articles en les livrant directement du fournisseur au client, dans ce qui est appelé une livraison directe. En savoir plus sur [Créer des livraisons directes](sales-how-drop-shipment.md). Pour tous les autres aspects, les documents de vente fonctionnent de la même manière que les factures vente. En savoir plus sur [Facturer des ventes](sales-how-invoice-sales.md).

Lorsque vous livrez les produits, entièrement ou partiellement, vous reportez le document de vente comme étant livré ou livré et facturé pour créer les écritures article et client associées dans votre système. Lorsque vous reportez le document de vente, vous pouvez également envoyer par courriel le document en pièce jointe au format PDF. Vous pouvez faire en sorte que le corps du message soit prérempli avec un résumé des informations de commande et de paiement, par exemple un lien vers Paypal. Pour plus d’informations, voir [Livrer des articles](warehouse-how-ship-items.md) et [Envoyer des documents par courriel](ui-how-send-documents-email.md).

Dans les environnements d'entreprise où le client paie immédiatement, par exemple par PayPal ou en espèces, le paiement est enregistré immédiatement lorsque vous reportez le document de vente comme facturé, c'est-à-dire la facture vente reportée est fermée comme entièrement affectée. Vous sélectionnez la méthode appropriée dans le champ **Code mode de paiement** du document de vente. Reportez-vous à l'étape 5 ci-dessous. Pour les paiements électroniques, tels que PayPal, vous devez également renseigner le champ **Service de paiement**. En savoir plus, [Activer les paiements client via les services de paiement](sales-how-enable-payment-service-extensions.md).

Vous pouvez même créer des commandes à paiement direct pour les clients non enregistrés en configurant une fiche « client en espèces », vers laquelle vous pointez sur le document de vente. En savoir plus sur [Configurer les clients effectuant un achat au comptoir](finance-how-to-set-up-cash-customers.md).

## Créer un document de vente

> [!NOTE]  
> La procédure suivante suppose que le client est déjà configuré. Pour obtenir des instructions sur la façon de procéder, voir [Enregistrer de nouveaux clients](sales-how-register-new-customers.md).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Sélectionnez **Nouveau** pour créer une écriture.
3. Dans le champ **Client**, entrez le nom d'un client existant.

    D’autres champs de la page **Document de vente** sont désormais renseignés avec les informations standard sur le client sélectionné.  

4. Renseignez les champs restants de la page **Document de vente**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    > Si vous autorisez le client à payer immédiatement, par exemple, par carte de crédit ou par PayPal, renseignez le champ **Code mode de règlement**. Le paiement est ensuite enregistré dès que vous reportez le document de vente comme facturé. Si vous sélectionnez *Espèces*, le paiement est enregistré dans un compte de contrepartie spécifié.

    Vous êtes maintenant prêt à renseigner les lignes document de vente avec les articles en inventaire ou les services que vous voulez que le client achète.

    Si vous avez défini des lignes vente récurrentes pour le client, tel qu’un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la commande par l’intermédiaire de l’action **Extraire les lignes vente récurrentes**.
5. Sous le raccourci **Lignes**, dans le champ **Type**, sélectionnez le type de produit, de frais ou de transaction à reporter pour le client sur la ligne vente.

6. Dans le champ **N°**, saisissez le numéro d’un article inventaire ou d’un service.

    Laissez le champ **N°** vide si la ligne est destinée à un :

    * Commentaire. Saisissez le commentaire dans le champ **Description**.
    * Article de catalogue. Sélectionnez l'action **Sélectionner articles de catalogue**. En savoir plus sur [Utiliser des éléments de catalogue](inventory-how-work-nonstock-items.md).
7. Dans le champ **Quantité**, saisissez le nombre d'articles à vendre.

    > [!NOTE]  
    > Pour les articles de type *Ressource* ou *Service*, la quantité est une unité de temps, telle que les heures, comme indiqué dans le champ **Code unité de mesure** de la ligne. Pour plus d’informations, voir [Configuration des unités de mesure article](inventory-how-setup-units-of-measure.md).

    Le champ **Montant ligne** est mis à jour pour indiquer la valeur du champ **Prix unitaire** multipliée par le nombre du champ **Quantité**.

    Le prix et les montants ligne sont affichés avec ou sans la Sales Tax en fonction de la valeur que vous avez sélectionné dans le champ **Prix incluant les taxes** de la fiche client.
8. Dans le champ **% remise ligne**, saisissez un pourcentage si vous souhaitez accorder au client une remise sur le produit. La valeur du champ **Montant ligne** est mise à jour en conséquence.

    Si vous avez défini des prix article spéciaux sur le raccourci **Prix vente et escomptes ligne vente** dans la fiche client ou article, le prix et le montant de la ligne devis sont automatiquement mis à jour si les critères de prix convenus sont réunis. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).
9. Pour ajouter un commentaire sur la ligne commande que le client peut afficher dans le document de vente imprimé, saisissez un commentaire sur une ligne vierge, dans le champ **Description**.  
10. Répétez les étapes 5 à 9 pour chaque article que vous souhaitez vendre au client.

    Les champs totaux sous les lignes sont automatiquement mis à jour lorsque vous créez ou modifiez des lignes pour afficher les montants qui seront reportés dans les livres.

    > [!NOTE]
    > Dans de très rares cas, les montants reportés peuvent différer de ce qui est affiché dans les champs des totaux. Cela est généralement dû aux calculs d’arrondissement par rapport à la TVA ou à la taxe de vente.
    >
    > Pour vérifier les montants qui seront réellement reportés, utilisez la page **Statistiques**, qui tient compte des calculs d’arrondissement. Aussi, si vous choisissez l'action **Libérer**, les champs de totaux seront mis à jour pour inclure les calculs d’arrondissement.  

11. Dans le champ **Montant d’escompte de la facture**, vous pouvez entrer un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC**.

    Si vous avez défini des escomptes facture pour le client, le pourcentage spécifié est automatiquement inséré dans le champ **% escompte facture** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant escompte facture sans TVA**. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md).
12. Pour livrer seulement une partie de la quantité commandée, entrez la quantité dans le champ **Qté à livrer**. La valeur est copiée automatiquement dans le champ **Qté à facturer**.

    > [!NOTE]
    > Si le champ **Avis de livraison** est défini comme **Terminé** dans le raccourci **Livraison et facturation**, vous ne pouvez pas reporter de livraisons partielles. En savoir plus sur [Traiter les livraisons partielles](sales-how-send-partial-shipments.md).
13. Pour facturer seulement une partie de la quantité livrée, entrez la quantité dans le champ **Qté à facturer**. La quantité doit être inférieure à la valeur du champ **Qté à expédier**.  
14. Lorsque les lignes commande vente sont renseignées, sélectionnez l'action **Valider et envoyer**.

[!INCLUDE [order-ship-invoice](includes/order-ship-invoice.md)]

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode de réception de documents par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. En savoir plus, [Configurer des profils d’envoi de documents](sales-how-setup-document-send-profiles.md).

Les écritures article et client associées sont à présent créées dans votre système, et le document de vente est sorti en tant que document au format PDF. Lorsque le document de vente est entièrement reporté, il est supprimé de la liste des documents de vente et remplacé par de nouveaux documents dans la liste des factures vente reportées et la liste des livraisons vente reportées.  

## Numéro de document externe

[!INCLUDE [ext-doc-no-sales](includes/ext-doc-no-sales.md)]

## Voir aussi .

[Facturation des ventes](sales-how-invoice-sales.md)  
[Validation des ventes](ui-post-sales.md)  
[Livrer des articles](warehouse-how-ship-items.md)  
[Réalisation de livraisons directes](sales-how-drop-shipment.md)  
[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Imprimer la liste des prélèvements](sales-how-print-picking-list.md)  
[Traiter les livraisons partielles](sales-how-send-partial-shipments.md)  
[Stock](inventory-manage-inventory.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
