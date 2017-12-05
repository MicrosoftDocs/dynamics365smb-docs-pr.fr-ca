---
title: "Aperçu des tâches permettant de gérer la comptabilité fournisseur| Microsoft Docs"
description: "Décrit les tâches permettant de gérer les comptes fournisseur, par exemple, le paiement des créditeurs ou l'affectation de paiements sortants aux écritures pour fermer des factures ou des notes de crédit."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 06/28/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: daa014eaa78caa7a317b05ca92ff27c1d1530c06
ms.openlocfilehash: 2939c4bf99b0fec05fd3625af589f05710a05a3c
ms.contentlocale: fr-ca
ms.lasthandoff: 10/17/2017

---
# <a name="managing-payables"></a>Gestion des comptes fournisseur
Une grande partie de la gestion des comptes fournisseurs consiste à payer vos fournisseurs, ou à rembourse vos employés pour leurs dépenses. Vous pouvez utiliser les fonctions pour ajouter des lignes de paiement pour les factures achat échues dans la fenêtre **Feuille paiement** . Pour envoyer des transactions à votre banque, vous pouvez exporter plusieurs lignes journal paiement vers un fichier, puis télécharger ce fichier vers votre banque. Vous pouvez également effectuer des paiements par chèque, notamment pour transmettre des chèques en tant que paiements électroniques.

Une autre tâche courante consiste à affecter les paiements sortants à leurs écritures fournisseur ou employé correspondantes afin de fermer les factures achat, les notes de crédit achat ou les comptes employés comme payés. Vous pouvez effectuer cette tâche dans la fenêtre **Feuille rapprochement bancaire** en important un fichier de relevé bancaire pour enregistrer rapidement les paiements. Les paiements sont affectés aux écritures client, fournisseur ou employé ouvertes en faisant correspondre le texte de paiement et les informations d'écriture. Il existe plusieurs manières de vérifier et de modifier les correspondances avant de reporter le journal. Vous pouvez choisir de fermer les écritures de compte bancaire ouvertes associées aux écritures affectées lorsque vous reportez le journal. Le compte bancaire est automatiquement rapproché lorsque tous les paiements sont affectés.

Sinon, vous pouvez affecter les paiements sortants manuellement dans la fenêtre **Journal paiement** ou à partir des écritures fournisseur ou employé associées.

Le tableau suivant décrit une série de tâches associées aux comptes fournisseur et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Générez les paiements fournisseurs ou les remboursements employés dus, préparez les paiements par chèque, et exportez les paiements vers un fichier bancaire lors du report. |[Effectuer des paiements](payables-make-payments.md) |
| Affecter les paiements fournisseur automatiquement aux factures achat impayées en important un fichier de relevé de compte bancaire. |[Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Affecter les paiements fournisseur aux factures achat impayées manuellement. |[Procédure : rapprocher les paiements fournisseur manuellement](payables-how-apply-purchase-transactions-manually.md) |
|Pour que l'évaluation de l'inventaire soit correcte, affectez les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez lors de l'achat.|[Procédure : Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|

## <a name="see-also"></a>Voir aussi
[Achats](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Procédure : Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

