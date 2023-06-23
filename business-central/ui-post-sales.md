---
title: Report de documents vente
description: En savoir plus sur les différentes fonctions de report pour reporter des documents vente et la manière de mettre à jour les documents reportés.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.search.form: '130, 142, 1350'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="posting-sales" />Report des ventes

Sous le menu **Report** dans un document vente, vous pouvez choisir parmi les fonctions de report suivantes :

* **Reporter**
* **Reporter et créer**
* **Reporter et envoyer**
* **Aperçu report**
* **Valider par lot**
* **Rapport de test**

> [!NOTE]
> Pour les documents de vente, vous pouvez également voir les options liées à la fonctionnalité de paiement anticipé. Pour plus d’informations, voir [Facturation des paiements anticipés](finance-invoice-prepayments.md).

Lorsque vous avez renseigné toutes les lignes et entré toutes les informations du document de vente, vous pouvez le reporter. Cela crée une livraison et une facture.

Lorsqu’un document de vente est reporté, le compte du client, le grand livre et les écritures article sont mis à jour.

Pour chaque commande vente, une écriture vente est créée dans la table **Écriture comptable**. Une écriture est également créée dans le compte client de la table **Écriture comptable client** et une écriture comptable est créée dans le compte client approprié. De plus, le report de la commande peut avoir pour résultat la création d’une écriture TVA et d’une écriture pour le montant de l'escompte. Le report d’une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la page **Configuration des ventes et des comptes à recevoir**.

Pour chaque ligne commande vente, une écriture comptable article est créée dans la table **Écriture comptable article** (si les lignes vente contiennent des numéros des articles) ou une écriture comptable est créée dans la table **Écriture comptable** (si les lignes vente contiennent un compte général). En outre, les commandes vente sont toujours enregistrées dans les tables **En-tête expédition vente** et **En-tête facture vente**.

[!INCLUDE [order-ship-invoice](includes/order-ship-invoice.md)]

Vous pouvez reporter, ou reporter et envoyer. Si vous choisissez de reporter et d'envoyer, un fichier PDF est généré, lequel peut être envoyé par la suite. Vous pouvez aussi choisir la fonction **Valider par lot**, qui vous permet de valider plusieurs commandes en même temps. Pour plus d'informations, voir [Reporter plusieurs documents en même temps](ui-batch-posting.md).

## <a name="viewing-ledger-entries" />Affichage des écritures

Lorsque le report est terminé, les lignes vente reportées sont supprimées de la commande. Un message vous indique lorsque le report est terminé. Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent des écritures reportées, telles que **Écritures client**, **Écritures**, **Écritures article**, **Livraisons vente reportées** et **Factures vente reportées**.  

Dans la plupart des cas, vous pouvez ouvrir des écritures à partir de la fiche ou du document concerné. Par exemple, sur la page **Fiche client**, sélectionnez l'action **Écritures**.

## <a name="editing-ledger-entries" />Modification des écritures

Vous pouvez modifier certains champs dans les documents d'achat reportés, tels que le champ **N° de suivi du colis**. . Pour plus d'informations, voir [Modifier les documents reportés](across-edit-posted-document.md). Pour les champs plus critiques qui concernent la piste d'audit, vous devez inverser ou annuler le report. Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).

## <a name="see-related-microsoft-trainingtrainingmodulesship-invoice-items-dynamics-365-business-centralindex" />Voir la [formation Microsoft](/training/modules/ship-invoice-items-dynamics-365-business-central/index) associée

## <a name="see-also" />Voir aussi

[Ventes](sales-manage-sales.md)  
[Reporter plusieurs documents en même temps](ui-batch-posting.md)  
[Modifier les documents reportés](across-edit-posted-document.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]  
