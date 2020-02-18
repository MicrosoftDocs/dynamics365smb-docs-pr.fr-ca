---
title: Corriger ou annuler une facture vente reportée| Microsoft Docs
description: Décrit comment corriger, rétablir ou annuler une facture vente reportée et affecter une note de crédit vente.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: undo, credit memo, return
ms.date: 01/25/2020
ms.author: sgroespe
ms.openlocfilehash: 95653acf28c553d8331e2c086b7e84f1518bc3c0
ms.sourcegitcommit: 877af26e3e4522ee234fbba606615e105ef3e90a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/28/2020
ms.locfileid: "2992058"
---
# <a name="correct-or-cancel-unpaid-sales-invoices"></a>Corriger ou annuler des factures vente impayées
Vous pouvez corriger ou annuler une facture vente reportée. Cela est utile si vous faites une erreur ou si le client demande une modification.

> [!NOTE]  
>   Une fois la facture vente reportée entièrement ou partiellement payée, vous ne pouvez pas la corriger ou l'annuler à partir de celle-ci. Au lieu de cela, vous devez créer manuellement une note de crédit vente pour annuler la vente et rembourser le client, géré de manière facultative avec un retour vente. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md).

Sur la page **Facture vente reportée**, vous pouvez sélectionner l'action **Corriger** ou **Annuler** pour exécuter les actions décrites dans le tableau suivant.

| Action | Description |
| --- | --- |
| **Corriger** |La facture vente reportée est annulée. Une nouvelle facture vente avec les mêmes informations est créée. Vous pouvez créer une correction, puis continuer le processus de vente. La nouvelle facture vente a un numéro différent de celui de la facture vente initiale. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases Annulée et Payée sont cochées. |
| **Annuler** |La facture vente reportée est annulée. Une note de crédit vente de correction est automatiquement créée et reportée pour annuler la facture vente reportée initiale. Sur la facture vente reportée initiale, les cases Annulée et Payée sont cochées. |

Lorsque vous corrigez ou annulez une facture vente reportée, la note de crédit vente de correction est affectée à toutes les écritures du grand livre et de l'inventaire physique créées lors du report de la facture vente initiale. Cette action inverse la facture vente reportée dans vos enregistrements financiers et laisse la note de crédit vente reportée de correction pour votre piste de vérification.

## <a name="to-correct-a-posted-sales-invoice"></a>Pour corriger une facture vente reportée
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Factures vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la facture vente reportée à corriger.

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas corriger la facture vente validée car elle l'a déjà été, ou a été annulée.
3. Sur la page **Facture vente reportée** sélectionnez l'action **Corriger**.  
4. Une nouvelle facture vente avec les mêmes informations et dans laquelle vous pouvez apporter une correction est créée. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale.
5. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

## <a name="to-cancel-a-posted-sales-invoice"></a>Pour annuler une facture vente reportée
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Factures vente reportées**, puis sélectionnez le lien associé.  
2. Sélectionnez la facture vente reportée à annuler.

    > [!NOTE]  
    >   Si la case à cocher **Annulé** est activée, vous ne pouvez pas annuler la facture vente validée car elle a déjà été annulée ou corrigée.
3. Sur la page **Facture vente reportée** sélectionnez l'action **Annuler**.

    Une note de crédit vente est automatiquement créée et reportée pour annuler la facture vente reportée initiale. La valeur du champ **Annulé** de la facture vente validée initiale devient **Oui**.
4. Sélectionnez l'action **Afficher un avoir correctif** pour afficher l'avoir vente validé qui annule la facture vente validée initiale.

### <a name="partial-invoice-posting-also-supported"></a>Report de facture partiel également pris en charge
Si l'annulation est liée à un report de facture partiel, la ligne de document de vente d'origine est mise à jour pour refléter la quantité facturée annulée. Les champs **Qté à facturer** et **Qté facturée** de la ligne de document de vente associée sont réinitialisés et affichent les valeurs avant le report partiel.

## <a name="see-also"></a>Voir aussi
[Vente](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
