---
title: Familiarisation avec le report des documents achat | Microsoft Docs
description: En savoir plus sur les différentes fonctions de report pour reporter des documents achat et la manière de mettre à jour les documents reportés.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 687a63e1d53db4c120070de0a353b3501a335d27
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3914945"
---
# <a name="posting-purchases"></a>Report des achats
Sur un document achat, vous pouvez faire votre choix parmi les actions de report suivantes :

* **Reporter**
* **Aperçu report**
* **Valider et Imprimer**
* **Rapport de test**
* **Valider par lot**

Lorsqu’un document achat est reporté, le compte du fournisseur, le grand livre, les écritures du grand livre d'articles et les écritures ressource sont mis à jour.

Pour chaque document achat, une écriture achat est créée dans la table **Écriture** . Une écriture est également créée dans le compte fournisseur de la table **Ecriture fournisseur** et une autre dans le compte fournisseur approprié. De plus, le report de l'achat peut entraîner la création d'une écriture TVA et d'une écriture pour le montant de l'escompte. Le report d'une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la table **Configuration des achats et des comptes à payer** .

Pour chaque ligne achat, les écritures suivantes sont créées :
- Une écriture dans la table **Écriture du grand livre d'articles** si la ligne achat est de type **Article** .
- Une écriture dans la table **Écriture** si la ligne achat est de type **Compte du grand livre** .
- Une écriture dans la table **Écriture ressource** si la ligne achat est de type **Ressource** .

En outre, les documents achat sont toujours enregistrés dans les tables **En-tête réception achat** et **En-tête facture achat** .

Avant de commencer à reporter, vous pouvez effectuer une rapport de test qui contient toutes les informations du bon de commande et indique les erreurs afférentes. Pour imprimer l’état, sélectionnez **Validation** , puis **Impression test** .

> [!IMPORTANT]  
>   Lorsque vous reportez un bon de commande pour des articles, vous pouvez créer une réception et une facture. Celles-ci peuvent être faites simultanément ou séparément. Vous pouvez également créer une réception partielle et une facture partielle en renseignant les champs **Qté à recevoir** et **Qté à facturer** sur chaque ligne commande achat avant la validation. Remarquez que vous ne pouvez pas créer de facture pour un article qui n'a pas été reçu. C'est-à-dire que, avant de pouvoir facturer, vous devez avoir validé une réception, ou vous devez choisir de réceptionner et de facturer en même temps.

Vous pouvez soit reporter, soit reporter et imprimer. Si vous choisissez de reporter et d’imprimer, un rapport est imprimé lorsque la commande est reportée. Vous pouvez aussi choisir la fonction **Valider par lot** , qui vous permet de valider plusieurs commandes en même temps. Pour plus d'informations, voir [Reporter plusieurs documents en même temps](ui-batch-posting.md).

## <a name="viewing-ledger-entries"></a>Affichage des écritures
Lorsque le report est terminé, les lignes achat reportées sont supprimées de la commande. Un message vous indique lorsque le report est terminé. Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent les écritures reportées, comme les pages **Écritures fournisseur** , **Écritures** , **Écritures article** , **Écritures ressource** , **Réceptions achat** et **Factures achat reportées** .

Dans la plupart des cas, vous pouvez ouvrir des écritures à partir de la fiche ou du document concerné. Par exemple, sur la page **Fiche fournisseur** , sélectionnez l'action **Écritures** .

## <a name="editing-ledger-entries"></a>Modification des écritures
Vous pouvez modifier certains champs sur les documents achat reportés, tels que le champ **Référence de paiement** . Pour plus d'informations, voir [Modifier les documents reportés](across-edit-posted-document.md). Pour les champs plus critiques qui concernent la piste d'audit, vous devez inverser ou annuler le report. Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/receive-invoice-dynamics-d365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Modifier les documents reportés](across-edit-posted-document.md)  
[Reporter plusieurs documents en même temps](ui-batch-posting.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Validation des documents et des feuilles](ui-post-documents-journals.md)  
[Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
