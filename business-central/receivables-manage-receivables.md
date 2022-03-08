---
title: Aperçu des tâches permettant de gérer la comptabilité client | Microsoft Docs
description: Décrit les tâches permettant de gérer les montant à recevoir et d'affecter les paiements aux écritures client ou fournisseur.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customer payment, debtor, balance due, AR
ms.date: 01/13/2020
ms.author: sgroespe
ms.openlocfilehash: 387b8269e5da978c25c1c5436f5a737fa055a78c
ms.sourcegitcommit: ead69ebe5b29927876a4fb23afb6c066f8854591
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/14/2020
ms.locfileid: "2954173"
---
# <a name="managing-receivables"></a>Gestion des comptes client
Une étape normale de n'importe quelle opération financière consiste à rapprocher des comptes bancaires, ce qui nécessite d'affecter les paiements entrants avec des écritures fournisseur ou client pour fermer les factures vente et les notes de crédit achat comme payées.

Bien que la plupart des clients dans les environnements B2B payent un certain temps après la livraison en laissant les factures vente reportées ouvertes jusqu'à ce qu'elles soient fermées (affectées) par le département Comptabilité client à la réception du paiement, certaines factures vente peuvent être payées immédiatement, par exemple avec PayPal. Ces factures sont immédiatement affectées comme payées lors de leur report et n'apparaissent donc pas comme paiements à traiter dans la Comptabilité client. Pour plus d'informations, voir [Facturation des ventes](sales-how-invoice-sales.md), par exemple.  

Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], l'une des méthodes les plus rapides pour enregistrer des paiements est d'accéder à la page **Journal rapprochement bancaire** et d'importer un fichier ou un flux de relevé bancaire. Les paiements sont affectés aux écritures client ou fournisseur ouvertes selon les correspondances entre le texte de paiement et les informations d'écriture. Vous pouvez consulter et modifier les correspondances avant de reporter le journal, puis fermer les écritures compte bancaire pour les écritures lorsque vous reportez le journal. Le compte bancaire est rapproché lorsque tous les paiements sont affectés.

D'autres pages vous permettent d'affecter des paiements ou de rapprocher des comptes bancaires :

* La page **Rapprochements comptes bancaires** qui vous permet de rapprocher des comptes bancaires en mettant en correspondance les lignes de relevé bancaire importées avec les écritures de compte bancaire du système. Vous pouvez également rapprocher des paiements par chèque. Pour plus d'informations, voir [Rapprocher des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md). Vous ne pouvez pas affecter des paiements.
* La page **Enregistrement de paiement** qui vous permet d'affecter manuellement les paiements reçus en liquide, par chèque ou par transaction bancaire par rapport à une liste générée de documents vente impayés. Notez que cette fonctionnalité est uniquement disponible pour les documents vente. Vous ne pouvez pas affecter des paiements sortants, et vous ne pouvez pas rapprocher des comptes bancaires.
* La page **Journal des encaissements** où vous pouvez reporter manuellement les réceptions dans un compte général, client ou autre en saisissant une ligne paiement. Vous pouvez affecter la réception ou le remboursement à une ou plusieurs écritures ouvertes avant de reporter le journal des encaissements, ou à partir des écritures client. Vous ne pouvez pas rapprocher des comptes bancaires.

Les pages **Journal rapprochement bancaire** et **Rapprochement bancaire** utilisent une logique de correspondance automatique que vous pouvez configurer sur la page **Règles affectation paiement**. Pour plus d'informations, voir [Configurer des règles pour l'affectation automatique des paiements](receivables-how-set-up-payment-application-rules.md).

Les autres aspects de la gestion des comptes client comprennent le recouvrement des soldes échus, y compris les intérêts de retard et des rappels, et de définir les comptes bancaires pour autoriser le retrait des paiements des clients de leur compte automatiquement.

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.  

| À | Voir |
| --- | --- |
| Affecter des paiements aux écritures client ou fournisseur ouvertes sur la base d'un fichier ou flux de relevé de compte bancaire importé, et rapprocher le compte bancaire lorsque tous les paiements sont affectés. |[Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Affecter des paiements aux écritures client ouvertes selon la liste des documents vente échus sur la page **Enregistrement de paiement**. |[Rapprocher les paiements client à partir de la liste des documents vente échus](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md) |
| Reporter des encaissements ou des remboursements pour des clients dans le journal des encaissements et les affecter à des écritures client, à partir du journal ou des écritures reportées. |[Rapprocher les paiements clients avec le journal des encaissements ou les écritures client](receivables-how-apply-sales-transactions-manually.md) |
| Rappeler aux clients les soldes échus, calculer les intérêts et les intérêts de retard, et gérer les comptes clients. |[Collecte des soldes restants](receivables-collect-outstanding-balances.md) |
|Avec le consentement de votre client, collectez les paiements directement à partir du compte bancaire du client en euro uniquement.|[Recouvrement de paiements par prélèvement automatique SEPA](finance-collect-payments-with-sepa-direct-debit.md)|
|Bloquez la saisie ou le report d'un client sur des documents, par exemple à cause de son insolvabilité.|[Bloquer des clients](receivables-how-block-customers.md)|
|Assurez-vous de connaître le coût des articles livrés en affectant les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez après la vente.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|
|Configurer une valeur de tolérance selon laquelle le système ferme une facture même si le paiement, tenant compte d'éventuels escomptes, ne couvre pas intégralement le montant de la facture.|[Utilisation des tolérances de règlement et des tolérances d'escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md)|
| Prévoyez quand les paiements seront exécutés en retard pour les documents vente. | [Extension Prévisions de retard de paiement](ui-extensions-late-payment-prediction.md) |

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/paths/process-customer-vendor-payments-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi
[Vente](sales-manage-sales.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
