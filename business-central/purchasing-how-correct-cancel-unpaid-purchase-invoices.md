---
title: "Corriger ou annuler des factures achat impayées | Microsoft Docs"
description: "Explique comment corriger, rétablir ou annuler une facture achat reportée et créer automatiquement une note de crédit achat."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 08/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 43fa63ce0c69c1f040faec4c257fa179a3a3fa31
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="correct-or-cancel-unpaid-purchase-invoices"></a>Corriger ou annuler des factures achat impayées
Vous pouvez corriger ou annuler une facture achat reportée. Cela est utile si vous souhaitez corriger une erreur de saisie, ou si vous souhaitez modifier l'achat assez tôt dans le processus de commande.

Si vous avez déjà payé des produits sur la facture achat reportée, vous ne pouvez pas la corriger ni l'annuler à partir de la facture achat reportée elle-même. Au lieu de cela, vous devez créer manuellement une note de crédit achat pour inverser l'achat, éventuellement géré à l'aide d'un retour achat. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md).

Dans la fenêtre **Facture achat enregistrée**, vous pouvez cliquer sur le bouton **Corriger** ou **Annuler**. Lorsque vous corrigez ou annulez une facture achat reportée, la note de crédit achat de correction est affectée à toutes les écritures du grand livre et de l'inventaire physique créées lors du report de la facture achat initiale. Cette action inverse la facture achat reportée dans vos enregistrements financiers et laisse la note de crédit achat reportée de correction pour votre piste de vérification. L'utilisation des boutons **Corriger** et **Annuler** est décrite ci-après.

## <a name="to-correct-a-posted-purchase-invoice"></a>Pour corriger une facture achat reportée
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Factures achat enregistrées**, puis sélectionnez le lien connexe.  
2. Sélectionnez la facture achat reportée à corriger.  

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas corriger la facture achat validée car elle l'a déjà été, ou a été annulée.
3. Dans la fenêtre **Facture achat enregistrée** sélectionnez **Corriger**.

    Une nouvelle facture achat avec les mêmes informations et dans laquelle vous pouvez apporter une correction est créée. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md). La valeur du champ **Annulé** de la facture achat validée initiale devient **Oui**.

    Une note de crédit achat est automatiquement créée et reportée pour annuler la facture achat reportée initiale.
4. Sélectionnez **Afficher un avoir correctif** pour afficher l'avoir achat validé qui annule la facture achat validée initiale.

## <a name="to-cancel-a-posted-purchase-invoice"></a>Pour annuler une facture achat reportée
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Factures achat enregistrées**, puis sélectionnez le lien connexe.  
2. Sélectionnez la facture achat reportée à annuler.

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas annuler la facture achat validée car elle l'a déjà été, ou a été corrigée.
3. Dans la fenêtre **Facture achat enregistrée** sélectionnez **Annuler**.

    Une note de crédit achat est automatiquement créée et reportée pour annuler la facture achat reportée initiale. La valeur du champ **Annulé** de la facture achat validée initiale devient **Oui**.
4. Sélectionnez **Afficher un avoir correctif** pour afficher l'avoir achat validé qui annule la facture achat validée initiale.

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

