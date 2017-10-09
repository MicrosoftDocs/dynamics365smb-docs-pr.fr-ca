---
title: "Corriger ou annuler une facture vente reportée| Microsoft Docs"
description: "Décrit comment corriger, rétablir ou annuler une facture vente reportée et affecter une note de crédit vente."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 08/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 6de89bc0865fbe8617e33288b9c0c8fe7da802ef
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-correct-or-cancel-unpaid-sales-invoices"></a>Procédure : corriger ou annuler des factures vente impayées
Vous pouvez corriger ou annuler une facture vente reportée. Cela est utile si vous faites une erreur ou si le client demande une modification.

> [!NOTE]  
>   Une fois la facture vente reportée entièrement ou partiellement payée, vous ne pouvez pas la corriger ou l'annuler à partir de celle-ci. Au lieu de cela, vous devez créer manuellement une note de crédit vente pour annuler la vente et rembourser le client, géré de manière facultative avec un retour vente. Pour plus d'informations, reportez-vous à [Procédure : traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).

Dans la fenêtre **Facture vente enregistrée**, vous pouvez sélectionnez l'action **Corriger** ou **Annuler** pour exécuter les actions décrites dans le tableau suivant.

| Action | Description |
| --- | --- |
| **Corriger** |La facture vente reportée est annulée. Une nouvelle facture vente avec les mêmes informations est créée. Vous pouvez créer une correction, puis continuer le processus de vente. La nouvelle facture vente a un numéro différent de celui de la facture vente initiale. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases Annulée et Payée sont cochées. |
| **Annuler** |La facture vente reportée est annulée. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases Annulée et Payée sont cochées. |

Lorsque vous corrigez ou annulez une facture vente reportée, la note de crédit vente de correction est affectée à toutes les écritures du grand livre et de l'inventaire physique créées lors du report de la facture vente initiale. Cette action inverse la facture vente reportée dans vos enregistrements financiers et laisse la note de crédit vente reportée de correction pour votre piste de vérification.

## <a name="to-correct-a-posted-sales-invoice"></a>Pour corriger une facture vente reportée
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures vente enregistrées**, puis sélectionnez le lien connexe.  
2. Sélectionnez la facture vente reportée à corriger.

    > [!NOTE]  
>   Si la case à cocher **Annulé** est activée, vous ne pouvez pas corriger la facture vente validée car elle l'a déjà été, ou a été annulée.
3. Dans la fenêtre **Facture vente enregistrée** sélectionnez l'action **Corriger**.  
4. Une nouvelle facture vente avec les mêmes informations et dans laquelle vous pouvez apporter une correction est créée. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale.
5. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

## <a name="to-cancel-a-posted-sales-invoice"></a>Pour annuler une facture vente reportée
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Factures vente enregistrées**, puis sélectionnez le lien connexe.  
2. Sélectionnez la facture vente reportée à annuler.

    > [!NOTE]  
>   Si la case à cocher **Annulé** est activée, vous ne pouvez pas annuler la facture vente validée car elle a déjà été annulée ou corrigée.
3. Dans la fenêtre **Facture vente enregistrée** sélectionnez l'action **Annuler**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.
4. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

## <a name="see-also"></a>Voir aussi
[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Procédure : envoyer des documents par e-mail](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

