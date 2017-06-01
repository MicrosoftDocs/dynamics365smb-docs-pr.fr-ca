---
title: Gestion des comptes fournisseur| Microsoft Docs
description: Gestion des comptes fournisseur
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: vendor payment, creditor, debt, balance due, AP
ms.date: 03/28/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 92b16c52589a07661d9ff080e9ef8a0f6be633f7
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="managing-payables"></a>Gestion des comptes fournisseur
Une grande partie de la gestion des comptes fournisseur consiste à payer les fournisseurs. Vous pouvez utiliser les fonctions pour ajouter des lignes de paiement pour les factures achat échues dans la fenêtre **Feuille paiement** . Pour envoyer des transactions à votre banque, vous pouvez exporter plusieurs lignes journal paiement vers un fichier, puis télécharger ce fichier vers votre banque. Vous pouvez également effectuer des paiements par chèque, notamment pour transmettre des chèques en tant que paiements électroniques.

Une autre tâche courante consiste à affecter les paiements sortants à leurs écritures fournisseur associées afin de fermer les factures achat ou les notes de crédit achat comme payées. Vous pouvez effectuer cette tâche dans la fenêtre **Feuille rapprochement bancaire** en important un fichier de relevé bancaire pour enregistrer rapidement les paiements. Les paiements sont affectés aux écritures client ou fournisseur ouvertes en faisant correspondre le texte de paiement et les informations d'écriture. Il existe plusieurs manières de vérifier et de modifier les correspondances avant de reporter le journal. Vous pouvez choisir de fermer les écritures de compte bancaire ouvertes associées aux écritures affectées lorsque vous reportez le journal. Le compte bancaire est automatiquement rapproché lorsque tous les paiements sont affectés.

Sinon, vous pouvez lettrer les paiements sortants manuellement dans la fenêtre **Feuille paiement** ou à partir des écritures comptables fournisseur associées.

Le tableau suivant décrit une série de tâches associées aux comptes fournisseur et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Générer des paiements fournisseur échus classés par ordre de priorité en fonction des escomptes et des pénalités de retard. Éventuellement, exporter les paiements vers un fichier bancaire lors du report. |[Exécuter des paiements](payables-make-payments.md) |
| Affecter les paiements fournisseur automatiquement aux factures achat impayées en important un fichier de relevé de compte bancaire. |[Procédure : lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Affecter les paiements fournisseur aux factures achat impayées manuellement. |[Procédure : rapprocher les paiements fournisseur manuellement](payables-how-apply-purchase-transactions-manually.md) |

## <a name="see-also"></a>Voir aussi
[Achats](purchasing-manage-purchasing.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

