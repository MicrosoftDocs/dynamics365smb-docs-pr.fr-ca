---
title: Utilisation de l'affectation automatique pour rapprocher les paiements | Microsoft Docs
description: Sur la page Règles d'affectation de paiement, vous définissez des règles pour définir comment les paiements/transactions bancaires doivent être automatiquement affectés à leurs écritures ouvertes associées lorsque vous utilisez la fonction Affecter automatiquement sur la page Journal rapprochement bancaire.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: payment process, direct payment posting, reconcile payment, expenses, cash receipts
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 64756cdc1a95cc0bb866fa4b7f87ecea0f1282ff
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3191941"
---
# <a name="set-up-rules-for-automatic-application-of-payments"></a>Configurer des règles pour l'affectation automatique des paiements
Sur la page **Règles affectation paiement**, vous définissez des règles pour définir comment le texte de paiement (sur une transaction bancaire) est automatiquement mis en correspondance avec le texte des écritures ouvertes dans les deux processus suivants :
- Affecter automatiquement les paiements à leurs factures ouvertes (impayées), notes de crédit ou autres écritures associées lorsque vous utilisez la fonction **Affecter automatiquement** sur la page **Journal rapprochement bancaire**. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).

- Faites correspondre automatiquement les transactions bancaires avec leurs écritures de compte bancaire internes associées lorsque vous choisissez l'action **Faire correspondre automatiquement** sur la page **Rapprochement bancaire**. Pour plus d'informations, voir [Rapprocher des comptes bancaires](bank-how-reconcile-bank-accounts-separately.md).

Pour définir de nouvelles règles d'affectation de paiement, choisissez quels types de données sur une ligne journal rapprochement bancaire doivent correspondre aux données sur une ou plusieurs écritures ouvertes avant que le paiement associé ne soit automatiquement affecté aux écritures ouvertes. La qualité de chaque affectation automatique est indiquée par une valeur de **Faible** à **Élevée** dans le champ **Fiabilité correspondance** sur la page **Journal rapprochement bancaire** selon la règle d'affectation de paiement qui a été utilisée.

Chaque ligne de la page **Règles d'affectation de paiement** représente une règle d'affectation de paiement. Les règles sont appliquées dans l'ordre spécifié par le champ **Ordre de tri**. Si plusieurs règles sont utilisées simultanément, c'est la fiabilité correspondance de la règle dont l'ordre de tri est le plus élevé qui est utilisée.

La fonction d'affectation automatique est basée sur des critères de correspondance classés par priorité. La fonction essaie d'abord, par ordre de priorité, de faire correspondre le texte dans les cinq champs **Partie associée** d'une ligne journal avec le texte du compte bancaire, du nom ou de l'adresse des clients ou des fournisseurs dont les documents impayés représentent des écritures ouvertes. La fonction essaie ensuite de faire correspondre le texte des champs **Texte transaction** et **Info transaction supplémentaire** sur une ligne journal avec le texte des champs **N° du document externe** et **N° document** sur les écritures ouvertes. Enfin, la fonction essaie de faire correspondre le montant du champ **Montant relevé** d'une ligne journal avec le montant sur les écritures ouvertes.

> [!NOTE]
> La correspondance de texte n'est possible que pour les textes contenant plus de quatre caractères.

Outre les critères de correspondance, les remarques suivantes s'appliquent concernant le signe du montant règlement :

- Pour les montants négatifs, une correspondance est d'abord établie par rapport aux écritures ouvertes représentant les factures client, et ensuite par rapport aux notes de crédit fournisseur.
- Pour les montants positifs, une correspondance est d'abord établie par rapport aux écritures ouvertes représentant les factures fournisseur, et ensuite par rapport aux notes de crédit client.

## <a name="to-set-up-a-payment-application-rule"></a>Pour configurer une règle d'affectation de paiement
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Règles affectation paiement**, puis sélectionné le lien associé.
2. Définissez une règle d'affectation de paiement, nouvelle ou modifiée, en renseignant les champs sur une ligne tel que décrit dans le tableau suivant.

|Champ|Description|
|-|-|
|**Fiabilité correspondance**|Spécifie la fiabilité de la règle d'affectation que vous définissez sur la ligne. <br /></br>Une valeur spécifiée dans ce champ est affichée dans le champ **Fiabilité correspondance** sur la page **Journal rapprochement bancaire** en fonction de la qualité de l'affectation de paiement automatique sur la ligne journal.|
|**Priorité**|Spécifie la priorité de la règle d'affectation par rapport aux autres règles d'affectation définies en tant que lignes sur la page **Règles affectation paiement**. 1 représente la priorité la plus élevée.|
|**Correspondance partie associée**|Spécifie la quantité d'informations sur le client ou le fournisseur (par exemple, l'adresse, le nom de la ville et le numéro de compte bancaire) sur la ligne journal rapprochement bancaire qui doivent correspondre aux informations sur l'écriture ouverte avant que la règle d'affectation soit utilisée pour affecter automatiquement le paiement à l'écriture ouverte.|
|**Correspondance N° doc./N° doc. ext.**|Spécifie si le texte de la ligne journal rapprochement bancaire doit correspondre à la valeur du champ **N° document** ou du champ **N° document externe** sur l'écriture ouverte avant que la règle d'affectation soit utilisée pour affecter automatiquement le paiement à l'écriture ouverte.|
|**Correspondance montant avec tolérance**|Spécifie combien d'écritures pour un client ou un fournisseur doivent correspondre au montant (tolérance de règlement comprise) avant que la règle d'affectation soit utilisée pour affecter automatiquement un paiement à l'écriture ouverte.|

Le tableau suivant montre les règles d'affectation de paiement définies dans la version générique de [!INCLUDE[d365fin](includes/d365fin_md.md)].

> [!Important]
> Les règles d'affectation de paiement peuvent être différentes dans votre implémentation de [!INCLUDE[d365fin](includes/d365fin_md.md)].

| Fiabilité correspondance | Priorité | Correspondance partie associée | Correspondance N° doc./N° doc. ext. | Correspondance montant avec tolérance |
|------------------|----------|-----------------------|--------------------------------|--------------------------------|
| Élevée             | 1        | Intégrale                 | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 2        | Intégrale                 | Oui - Multiple                 | Correspondances multiples               |
| Élevée             | 3        | Intégrale                 | Oui                            | Une correspondance                      |
| Élevée             | 4        | Intégrale                 | Oui                            | Correspondances multiples               |
| Élevée             | 5        | Partielle             | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 6        | Partielle             | Oui - Multiple                 | Correspondances multiples               |
| Élevée             | 7        | Partielle             | Oui                            | Une correspondance                      |
| Élevée             | 8        | Intégrale                 | Non                             | Une correspondance                      |
| Élevée             | 9        | Non                    | Oui - Multiple                 | Une correspondance                      |
| Élevée             | 10       | Non                    | Oui - Multiple                 | Correspondances multiples               |
| Moyenne           | 1        | Intégrale                 | Oui - Multiple                 | Non applicable                 |
| Moyenne           | 2        | Intégrale                 | Oui                            | Non applicable                 |
| Moyenne           | 3        | Intégrale                 | Non                             | Correspondances multiples               |
| Moyenne           | 4        | Partielle             | Oui - Multiple                 | Non applicable                 |
| Moyenne           | 5        | Partielle             | Oui                            | Non applicable                 |
| Moyenne           | 6        | Non                    | Oui                            | Une correspondance                      |
| Moyenne           | 7        | Non                    | Oui-Multiple                   | Non applicable                 |
| Moyenne           | 8        | Partielle             | Non                             | Une correspondance                      |
| Moyenne           | 9        | Non                    | Oui                            | Non applicable                 |
| Faible              | 1        | Intégrale                 | Non                             | Aucune correspondance                     |
| Faible              | 2        | Partielle             | Non                             | Correspondances multiples               |
| Faible              | 3        | Partielle             | Non                             | Aucune correspondance                     |
| Faible              | 4        | Non                    | Non                             | Une correspondance                      |
| Faible              | 5        | Non                    | Non                             | Correspondances multiples               |

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/reconciliation-journals-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Rapprocher les paiements à l'aide de l'application automatique](receivables-how-reconcile-payments-auto-application.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
