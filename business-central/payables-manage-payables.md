---
title: "Aperçu des tâches permettant de gérer la comptabilité fournisseur| Microsoft Docs"
description: "Décrit les tâches permettant de gérer les comptes fournisseur, par exemple, le paiement des créditeurs ou l'affectation de paiements sortants aux écritures pour fermer des factures ou des notes de crédit."
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 11/15/2018
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 9bc4eaf292c20c1525c499cde715964eb6e6631f
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

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
|Configurez des mappages entre le texte des paiements et des comptes de débit, de crédit et de contrepartie spécifiques afin que ces paiements soient reportés dans les comptes spécifiés lorsque vous reportez le journal rapprochement de paiement.|[Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md)|
| Affecter les paiements fournisseur aux factures achat impayées manuellement. |[Rapprocher les paiements fournisseur manuellement](payables-how-apply-purchase-transactions-manually.md) |
|Affectez automatiquement les paiements (entrants ou sortants) qui ont été enregistrés en tant que transactions sur votre compte bancaire en ligne à leurs écritures client, fournisseur et compte bancaire ouvertes associées. La liste est générée à partir d'un flux ou d'un fichier bancaire.|[Rapprocher les paiements à l'aide de l'affectation automatique](receivables-how-reconcile-payments-auto-application.md)|
|Gérer manuellement les paiements vers votre compte bancaire qui ne peuvent pas être affectés automatiquement, par exemple, parce qu'aucun document n'existe auquel le paiement peut être affecté ou le document connexe a un montant différent du montant de la transaction en raison d'une différence de devise.|[Rapprocher les paiements qui ne peuvent pas être affectés automatiquement](receivables-how-reconcile-payments-cannot-apply-auto.md)|
|Pour que l'évaluation de l'inventaire soit correcte, affectez les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez lors de l'achat.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|
|Si vous devez payer le fournisseur en liquide ou par chèque, vous pouvez reporter le paiement lorsque vous reportez la facture.|[Établir rapidement des factures achat](finance-how-to-settle-purchase-invoices-promptly.md)|
|Remboursez les frais personnels des employés pour leurs activités professionnelles en effectuant le paiement sur leur compte bancaire.|[Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md)|

## <a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  

