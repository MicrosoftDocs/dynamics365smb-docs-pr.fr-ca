---
title: Champ État sur les documents
description: Pour en savoir plus sur l'état « En cours » et « Libéré » figurant sur les documents de devis, de commande ou de note de crédit.
author: rubenseishima
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: document, status, quote, order, credit memo, released, open, pending approval, pending prepayment,
ms.search.form: ''
ms.date: 09/19/2022
ms.author: a-reishima
ms.openlocfilehash: c96909b4ee37673ee7b0c752224478a144ad853e
ms.sourcegitcommit: 8ad79e0ec6e625796af298f756a142624f514cf3
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9608263"
---
# <a name="status-field-on-documents"></a>Champ État sur les documents

Lorsque vous créez un devis, un ordre ou une note de crédit, le champ **État** sur l’en-tête du document indique par défaut l'état **En cours**.

Après avoir renseigné le document, vous pouvez le libérer et [!INCLUDE[prod_short](includes/prod_short.md)] modifie la valeur du champ **État** en **Libéré**. Cet état indique que la commande est prête pour la phase de traitement suivante avant qu’elle soit reportée.

| état | Désignation |
| ------ | ----------- |
| Ouvert   | Vous pouvez apporter des modifications à ce document. |
| Libéré | Le document a été libéré vers la phase suivante du traitement et vous ne pouvez pas modifier les lignes de type *Article* et *Immobilisation*.<br /><br />Vous pouvez rouvrir un document libéré pour le modifier. Pour transférer le document modifié vers la phase suivante du traitement, vous devez le libérer une nouvelle fois. |
| Approbation en attente   | Le document est en attente d'approbation. |
| Paiement anticipé en attente | Une facture paiement anticipé a été reportée pour ce document. |

## <a name="releasing"></a>Lancement

Vous pouvez utiliser le processus de libération de différentes manières afin de faciliter le flux de travail normal, et de suivre, par exemple, les procédures de la compagnie concernant les approbations ou démarrer les activités entrepôt.

### <a name="approval-procedures"></a>Procédures d’approbation

Votre compagnie peut utiliser la procédure de libération pour indiquer qu’un autre utilisateur a approuvé le document, ou qu’un contact externe peut répondre aux spécifications du document, comme l’indiquent les exemples suivants :

* Vous pouvez uniquement libérer un bon de commande lorsque le fournisseur vous a indiqué qu'il est en mesure d'y répondre.
* Vous créez une commande et un deuxième utilisateur doit l'approuver (par exemple, pour des raisons de sécurité) avant que vous soyez autorisé à la libérer.
* La note de crédit que vous avez créée doit être libérée par le responsable chargé d'approuver tous les remboursements.

En savoir plus sur les flux de travail approbation sur [Utiliser les flux de travail](across-use-workflows.md).

### <a name="warehouse-activities"></a>Activités entrepôt

Si l'état de l’ordre est **Ouvert**, l’entrepôt ne commence pas à préparer la livraison et ne prévoit pas de recevoir les articles d’un bon de commande. Lorsque vous libérez la commande, vous indiquez qu'elle est terminée et que l'entrepôt peut l'inclure dans ses activités.

## <a name="reopening-a-released-order"></a>Réouverture d'un ordre libéré

Vous pouvez modifier un ordre libéré en le rouvrant. Cependant, vous pouvez uniquement augmenter la quantité de lignes déjà traitées par l'entrepôt.

Lorsque vous avez modifié l’ordre et que vous le libérez à nouveau, le programme recalcule la TVA et l'escompte facture.

Si vous apportez des modifications à un ordre libéré, vous devez les notifier à l'entrepôt.

> [!NOTE]
> Si vous souhaitez reporter un seul ordre ouvert ou une note de crédit sans le/la libérer au préalable, le programme lance automatiquement le document lorsque vous le reportez. Si vous reportez des ordres ou des notes de crédit à l’aide de la fonction **Reporter par lot**, vous pouvez uniquement reporter ceux que vous avez libérés.

## <a name="see-also"></a>Voir aussi .

[Vente de produits avec un document de vente client](sales-how-sell-products.md)  
[Enregistrer les achats avec les factures achat](purchasing-how-record-purchases.md)  
[Livrer des articles](warehouse-how-ship-items.md)  
[Réceptionner des articles](warehouse-how-receive-items.md)  
[Utilisation des flux d'approbation](across-how-use-approval-workflows.md)  
[Tri, recherche et filtrage de listes](ui-enter-criteria-filters.md)  
[Archiver des documents](across-how-to-archive-documents.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
