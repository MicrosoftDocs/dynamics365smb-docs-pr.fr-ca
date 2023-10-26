---
title: Définir une politique de report des factures pour les utilisateurs
description: Utilisez les politiques de report des factures pour contrôler si un utilisateur peut reporter des factures de vente et d’achat.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 03/09/2023
ms.custom: bap-template
ms.search.forms: '119, 9807,'
---

# Définir une politique de report des factures pour les utilisateurs

Les entreprises ont souvent des processus uniques pour valider les factures de vente et d’achat et les livraisons. Par exemple, les processus peuvent varier d’une personne reportant tout sur un bon de commande à plusieurs employés. Vous pouvez empêcher les utilisateurs de valider des factures ou exiger que les factures soient reportées avec les livraisons ou les réceptions.

## Pour préciser une politique de report

Sur la page **Configuration de l’utilisateur**, dans les champs **Stratégie report facture vente** et **Stratégie report facture achat**, choisissez l’une des options suivantes :

* **Autorisé** (Par défaut) : conservez le comportement actuel, où un utilisateur peut choisir l’option de report à utiliser, comme **Livrer**, **Facturer** et **Livrer et facturer**. 
* **Interdit** : empêchez l’utilisateur de reporter des factures. Business Central affiche une boîte de dialogue de confirmation qui propose uniquement les options **Livrer** ou **Recevoir**.
* **Obligatoire** : autorisez l’utilisateur à reporter des factures avec les reçus ou les livraisons. Business Central affiche une boîte de dialogue de confirmation qui propose uniquement les options **Livrer et envoyer** ou **Recevoir et facturer**.

## Effet sur les documents

La table suivante décrit comment les stratégies de report des factures affectent les documents.

> [!NOTE]
> Lorsque vous reportez des factures vente et achat et des notes de crédit, vous ne disposez d’aucune option de report. Les documents reportent toujours les transactions physiques et financières ensemble. Vous ne pouvez pas reporter partiellement des factures et des notes de crédit.

|Document | Option 1 : Autoriser <br>Affiche une série d’options| Option 2 : Interdit <br>Boîte de dialogue de confirmation | Option 3 : obligatoire <br>Boîte de dialogue de confirmation|
|--|--|--|--|
|Document de vente |- Livrer <br>- Facturer <br>- Livrer et facturer |Souhaitez-vous reporter la livraison? |Souhaitez-vous reporter la livraison et la facture?|
|Facturation des ventes|Aucune option|Souhaitez-vous reporter la facture?|Souhaitez-vous reporter la facture?|
|Note de crédit vente|Aucune option|Souhaitez-vous reporter la note de crédit?|Souhaitez-vous reporter la note de crédit?|
|Retour vente |- Recevoir <br>- Facturer <br>- Réceptionner et facturer |Souhaitez-vous reporter cette réception? |Souhaitez-vous reporter la réception et la facture?|
|Prélèvement inventaire |- Livrer <br>- Livrer et facturer |Souhaitez-vous reporter la livraison? |Souhaitez-vous reporter la livraison et la facture?|
|Bon de commande |- Recevoir <br>- Facturer <br>- Réceptionner et facturer |Souhaitez-vous reporter cette réception? |Souhaitez-vous reporter la réception et la facture?|
|Facture achat|Aucune option|Souhaitez-vous reporter la facture?|Souhaitez-vous reporter la facture?|
|Note de crédit achat|Aucune option|Souhaitez-vous reporter la note de crédit?|Souhaitez-vous reporter la note de crédit?|
|Ordre de retour achat |- Livrer <br>- Facturer <br>- Livrer et facturer |Souhaitez-vous reporter la livraison? |Souhaitez-vous reporter la livraison et la facture?|
|Article dans l'inventaire à classer |- Recevoir <br>- Réceptionner et facturer |Souhaitez-vous reporter cette réception? |Souhaitez-vous reporter la réception et la facture?|
|Expédition entrepôt |- Livrer <br>- Livrer et facturer | Souhaitez-vous reporter la livraison? |Souhaitez-vous reporter la livraison et la facture?|

   > [!Note]
   > Le paramètre n’affecte pas le report des lignes du journal général où vous pouvez sélectionner **Facture** dans le champ **Type de document**.

## Voir aussi

[Facturer des ventes](sales-how-invoice-sales.md)  
[Enregistrer les achats avec les factures achat et les commandes](purchasing-how-record-purchases.md)  
[Acheter des articles pour une vente en créant des factures achat](purchasing-how-purchase-products-sale.md)
[Préparation aux activités commerciales](ui-get-ready-business.md)  
