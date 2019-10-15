---
title: Vérifier les paiements affectés automatiquement et appliquer à nouveau les paiements manuellement | Microsoft Docs
description: Après l'affectation automatique des paiements, vous pouvez consulter toutes les écritures d'un paiement et appliquer à nouveau manuellement celles dont l'affectation était incorrecte.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, reconcile payment, expenses, cash receipts
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: e87b4c4c22c83f482fcc777eac95df72acbb9eb6
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2316534"
---
# <a name="review-or-apply-payments-manually-after-automatic-application"></a>Réviser ou affecter les paiements manuellement après une affectation automatique
Pour chaque ligne journal représentant un paiement sur la page **Journal rapprochement paiement**, vous pouvez ouvrir la page **Affectation paiement** pour afficher toutes les écritures ouvertes candidates au paiement et les informations détaillées pour chaque écriture sur la correspondance des données sur laquelle une affectation de paiement est basée. Ici, vous pouvez affecter les paiements manuellement ou réaffecter les paiements qui ont été automatiquement affectés à une écriture incorrecte. Pour plus d'informations sur l'affectation automatique, voir [Rapprocher les paiements à l'aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md).

> [!IMPORTANT]  
>   Lorsque le compte bancaire pour lequel vous rapprochez des paiements est configuré pour la devise locale, la page **Affectation paiement** affiche toutes les écritures ouvertes dans la devise locale, y compris les écritures ouvertes pour les documents qui ont été initialement facturés en devise étrangère. Les paiements appliqués aux écritures avec devises converties peuvent donc être validés avec différents montants que celui qui figure sur le document d'origine en raison des taux de change potentiellement différents utilisés respectivement par la banque et [!INCLUDE[d365fin](includes/d365fin_md.md)].

Par conséquent, nous vous recommandons de rechercher les codes devise étrangère dans le champ **Code devise** de la page **Affectation paiement** pour vérifier si les affectations sont basés sur des devises converties. Pour rechercher le montant du document initial dans la devise étrangère et visualiser le taux de change utilisé, choisissez le champ **N° écriture référence**, puis, dans le menu contextuel, sélectionnez le bouton de vue détaillée pour ouvrir la page **Écritures client** ou **Écritures fournisseur**.

Aucun ajustement profits et pertes requis en raison de conversions de devise n'est géré automatiquement par [!INCLUDE[d365fin](includes/d365fin_md.md)]..

> [!NOTE]  
>   Vous ne pouvez pas affecter des écritures avec un signe différent du signe figurant sur le paiement. Par exemple, pour fermer une note de crédit négative et sa facture positive associée, vous devez d'abord affecter la note de crédit à la facture, puis affecter le paiement à la facture avec le montant restant réduit.

> [!WARNING]  
>   Si vous utilisez des escomptes de paiement, et si la date de paiement est antérieure à la date d'échéance de paiement, le champ **Montant ouvert escompte incl.** de la page **Affectation paiement** sera utilisé pour la correspondance. Sinon, la valeur du champ **Montant ouvert** sera utilisée. Si le paiement a été effectué avec un montant avec escompte après la date d'échéance du paiement, ou si le montant total a été payé mais qu'un escompte a été accordé, le montant ne correspondra pas.

> [!NOTE]  
>   Vous ne pouvez affecter un paiement qu'à un seul compte. Si vous souhaitez diviser l'affectation sur plusieurs écritures ouvertes, par exemple pour affecter le paiement d'une somme forfaitaire, les écritures ouvertes doivent être pour le même compte. Pour plus d'informations, reportez-vous aux étapes 7 et 8 de la procédure de cette rubrique.

## <a name="to-review-or-apply-payments-after-automatic-application"></a>Pour réviser ou affecter les paiements après une affectation automatique
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux rapprochement paiement**, puis sélectionnez le lien associé.
2. Ouvrez le journal de rapprochement de paiement pour un compte bancaire pour lequel vous souhaitez rapprocher les paiements. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).
3. Sur la page **Journal rapprochement paiement**, sélectionnez un paiement que vous souhaitez réviser ou affecter manuellement à une ou plusieurs écritures ouvertes, puis sélectionnez l'action **Affecter manuellement**.
4. Cochez la case **Lettré** sur la ligne de l'écriture ouverte à laquelle vous voulez lettrer le paiement.
5. Le montant du paiement, qui est également indiqué dans le champ **Montant transaction** de la page **Affectation paiement** est inséré dans le champ **Montant affecté**, mais vous pouvez modifier la valeur du champ, par exemple si vous souhaitez affecter le montant à plusieurs écritures ouvertes.
6. Pour lettrer une partie du montant payé à une autre écriture ouverte pour le compte, par exemple pour lettrer un paiement forfaitaire, cochez la case **Lettré** pour la ligne. Le montant affecté est automatiquement déduit du montant des transactions pour refléter la répartition sur les deux écritures ouvertes.
7. Pour affecter une partie d'un paiement à une ou plusieurs écritures ouvertes qui n'existent pas dans la base de données, créez une ligne sous la ligne pour le même compte. Dans le champ **Montant lettré**, entrez le montant à lettrer sur la nouvelle ligne, puis ajustez la valeur du champ **Montant lettré** de la ligne existante.
8. Répétez les étapes 5, 6 ou 7 pour les autres écritures ouvertes auxquelles vous souhaitez affecter un paiement complet ou partiel.
9. Lorsque vous avez révisé un lettrage de paiement ou lettré manuellement une ou plusieurs écritures ouvertes, sélectionnez l'action **Accepter le lettrage**.

La page **Affectation paiement** se ferme puis, dans la fenêtre **Journal rapprochement paiement**, la valeur du champ **Fiabilité correspondance** est modifiée et définie sur **Accepté** pour vous indiquer que vous avez révisé ou affecté manuellement le paiement.

## <a name="see-also"></a>Voir aussi
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
