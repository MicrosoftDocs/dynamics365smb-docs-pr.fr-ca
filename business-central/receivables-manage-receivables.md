---
title: "Aperçu des tâches permettant de gérer la comptabilité client | Microsoft Docs"
description: "Décrit les tâches permettant de gérer les montant à recevoir et d'affecter les paiements aux écritures client ou fournisseur."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customer payment, debtor, balance due, AR
ms.date: 04/30/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 75501b9402bb1c14fcfeb2fc6e61f055a2247493
ms.openlocfilehash: 01a195130a6834256b30efea8c06841c88af354d
ms.contentlocale: fr-ca
ms.lasthandoff: 05/15/2018

---
# <a name="managing-receivables"></a>Gestion des comptes client
Une étape normale de n'importe quelle opération financière consiste à rapprocher des comptes bancaires, ce qui nécessite d'affecter les paiements entrants avec des écritures fournisseur ou client pour fermer les factures vente et les notes de crédit achat comme payées.

Bien que la plupart des clients dans les environnements B2B payent un certain temps après la livraison en laissant les factures vente reportées ouvertes jusqu'à ce qu'elles soient fermées (affectées) par le département Comptabilité client à la réception du paiement, certaines factures vente peuvent être payées immédiatement, par exemple avec PayPal. Ces factures sont immédiatement affectées comme payées lors de leur report et n'apparaissent donc pas comme paiements à traiter dans la Comptabilité client. Pour plus d'informations, voir [Facturation des ventes](sales-how-invoice-sales.md), par exemple.  

Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], l'une des méthodes les plus rapides pour enregistrer les paiements à partir de la fenêtre **Feuille rapprochement bancaire** consiste à importer un fichier ou un flux de relevé bancaire. Les paiements sont affectés aux écritures client ou fournisseur ouvertes selon les correspondances entre le texte de paiement et les informations d'écriture. Vous pouvez consulter et modifier les correspondances avant de reporter le journal, puis fermer les écritures compte bancaire pour les écritures lorsque vous reportez le journal. Le compte bancaire est rapproché lorsque tous les paiements sont affectés.

D'autres fenêtres vous permettent d'affecter des paiements ou de rapprocher des comptes bancaires :

* La fenêtre **Rapprochements bancaires** qui vous permet de rapprocher des comptes bancaires en mettant en correspondance les lignes de relevé bancaire importées avec les écritures de compte bancaire du système. Vous pouvez également rapprocher des paiements par chèque. Pour plus d'informations, reportez vous à [Rapprocher des comptes bancaires séparément](bank-how-reconcile-bank-accounts-separately.md). Vous ne pouvez pas affecter des paiements.
* La fenêtre **Enregistrement de paiement** qui vous permet d'affecter manuellement les paiements reçus en liquide, par chèque ou par transaction bancaire par rapport à une liste générée de documents vente impayés. Notez que cette fonctionnalité est uniquement disponible pour les documents vente. Vous ne pouvez pas affecter des paiements sortants, et vous ne pouvez pas rapprocher des comptes bancaires.
* La fenêtre **Feuille règlement** où vous pouvez valider manuellement les réceptions dans un compte général, client ou autre en saisissant une ligne règlement. Vous pouvez affecter la réception ou le remboursement à une ou plusieurs écritures ouvertes avant de reporter le journal des encaissements, ou à partir des écritures client. Vous ne pouvez pas rapprocher des comptes bancaires.  

Une autre tâche de gestion des comptes client consiste à collecter des soldes restants, notamment pour gérer les frais financiers et l'émission de rappels. [!INCLUDE[d365fin](includes/d365fin_md.md)] offre d'autres méthodes pour effectuer ces opérations. Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).  

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.  

| À | Voir |
| --- | --- |
| Affecter des paiements aux écritures client ou fournisseur ouvertes sur la base d'un fichier ou flux de relevé de compte bancaire importé, et rapprocher le compte bancaire lorsque tous les paiements sont affectés. |[Lettrage automatique des paiements et rapprochement des comptes bancaires](receivables-apply-payments-auto-reconcile-bank-accounts.md) |
| Affectez des paiements à des écritures client ouvertes selon la saisie manuelle dans la liste des documents vente non payés. |[Rapprocher les paiements client manuellement à partir de la liste des documents vente échus](receivables-how-reconcile-customer-payments-list-unpaid-sales-documents.md) |
| Reportez des encaissements ou des remboursements pour des clients dans le journal des encaissements et affectez-les à des écritures client, à partir du journal ou des écritures reportées. |[Rapprocher les paiements client manuellement](receivables-how-apply-sales-transactions-manually.md) |
| Rappeler aux clients les soldes échus, calculer les intérêts et les frais financiers, et gérer les comptes clients. |[Collecte des soldes restants](receivables-collect-outstanding-balances.md) |
|Assurez-vous de connaître le coût des articles livrés en affectant les coûts articles ajoutés, tels que le fret, la manutention, les assurances et le transport, que vous encourez après la vente.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|
|Configurer une valeur de tolérance selon laquelle le système ferme une facture même si le paiement, tenant compte d'éventuels escomptes, ne couvre pas intégralement le montant de la facture.|[Utilisation des tolérances de règlement et des tolérances d'escompte de paiement](finance-payment-tolerance-and-payment-discount-tolerance.md)|
## <a name="see-also"></a>Voir aussi
[Vente](sales-manage-sales.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
## [!INCLUDE[d365fin](includes/training_link_md.md)]

