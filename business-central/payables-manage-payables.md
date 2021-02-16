---
title: Aperçu des tâches permettant de gérer la comptabilité fournisseur| Microsoft Docs
description: Décrit les tâches permettant de gérer les comptes fournisseur, par exemple, le paiement des créditeurs ou l'affectation de paiements sortants aux écritures pour fermer des factures ou des notes de crédit.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 9257259fd6de8e118dd48057809cba79576469a5
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759552"
---
# <a name="managing-payables"></a>Gestion des comptes fournisseur

Une grande partie de la gestion des comptes fournisseurs consiste à payer vos fournisseurs, ou à rembourse vos employés pour leurs dépenses. Vous pouvez utiliser les fonctions pour ajouter des lignes de paiement pour les factures achat échues sur la page **Journal paiement** . Pour envoyer des transactions à votre banque, vous pouvez exporter plusieurs lignes journal paiement vers un fichier, puis télécharger ce fichier vers votre banque. Vous pouvez également effectuer des paiements par chèque, notamment pour transmettre des chèques en tant que paiements électroniques.

Une autre tâche courante consiste à affecter les paiements sortants à leurs écritures fournisseur ou employé correspondantes afin de fermer les factures achat, les notes de crédit achat ou les comptes employés comme payés. Vous pouvez effectuer cette tâche sur la page **Journal rapprochement paiement** en important un fichier de relevé bancaire pour enregistrer les paiements. Les paiements sont affectés aux écritures client, fournisseur ou employé ouvertes en faisant correspondre le texte de paiement et les informations d'écriture. Il existe plusieurs manières de vérifier et de modifier les correspondances avant de reporter le journal. Vous pouvez choisir de fermer les écritures de compte bancaire ouvertes associées aux écritures affectées lorsque vous reportez le journal. Le compte bancaire est automatiquement rapproché lorsque tous les paiements sont affectés.

Sinon, vous pouvez affecter les paiements sortants manuellement sur la page **Journal paiement** ou à partir des écritures fournisseur ou employé associées.

Le tableau suivant décrit une série de tâches associées aux comptes fournisseur et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Générez les paiements fournisseurs ou les remboursements employés dus, préparez les paiements par chèque, et exportez les paiements vers un fichier bancaire lors du report. |[Effectuer des paiements](payables-make-payments.md) |
| Affecter les paiements fournisseur automatiquement aux factures achat impayées en important un fichier de relevé de compte bancaire. |[Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Affecter les paiements fournisseur aux factures achat impayées manuellement. |[Rapprocher des paiements fournisseur avec le journal paiement ou à partir des écritures fournisseur](payables-how-apply-purchase-transactions-manually.md) |
|Pour que l'évaluation de l'inventaire soit correcte, affectez les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez lors de l'achat.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|
|Remboursez les frais personnels des employés pour leurs activités professionnelles en effectuant le paiement sur leur compte bancaire.|[Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md)|

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/process-customer-vendor-payments-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  
