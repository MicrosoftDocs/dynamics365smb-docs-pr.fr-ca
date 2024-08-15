---
title: Utilisation de la fonction de transfert de différence vers le compte pour rapprocher les paiements
description: 'Décrit comment traiter les paiements qui ne peuvent pas être appliqués à un document, par exemple, lorsqu’un taux de change entraîne une différence de montants.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'payment process, cash receipts'
ms.search.form: '1290, 1294, 1287'
ms.date: 07/08/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="reconcile-payments-that-cant-be-applied-automatically"></a>Rapprocher les paiements qui ne peuvent pas être appliqués automatiquement
Vous devrez peut-être parfois gérer des paiements sur votre compte bancaire qui ne peuvent pas être appliqués à une écriture ouverte de compte client, de fournisseur ou de compte bancaire associée. Les raisons peuvent être qu’aucun document n’existe dans [!INCLUDE[prod_short](includes/prod_short.md)] auquel le paiement peut être appliqué, ou que le document associé dans [!INCLUDE[prod_short](includes/prod_short.md)] a un montant différent du montant de la transaction, par exemple, en raison d’un taux de change. Sur la page **Journal de rapprochement des paiements**, tous les montants de transaction pour les paiements qui ne sont pas encore appliqués apparaissent dans le champ **Différence**, y compris les montants qui ne peuvent pas être appliqués pour des raisons telles que celles mentionnées ci-dessus.

Méthodes de résolution de ces types de paiements non lettrés :
* Affecter manuellement
* Utiliser le mappage de texte à compte
* Transférez un montant excédentaire vers une ligne journal pour créer et reporter l’écriture requise, comme le remboursement d’un trop-perçu.

Les paiements qui ne peuvent pas être appliqués peuvent apparaître sur les lignes du journal de rapprochement des paiements de différentes manières :

* La valeur du champ **Différence** est égale à celle du champ **Montant transaction**, ce qui indique qu'aucune partie du paiement ne peut être lettrée à une écriture comptable client, fournisseur ou compte bancaire ouverte associée.
* La valeur du champ **Différence** est inférieure à celle du champ **Montant transaction**, ce qui indique qu'une partie du paiement peut être lettrée à une écriture comptable client, fournisseur ou compte bancaire ouverte associée. La partie restante du paiement ne peut pas être appliquée et doit être rapprochée manuellement ou en la publiant directement sur un compte.

Pour rapprocher de tels paiements, vous pouvez choisir l’action **Transférer la différence vers un compte**, puis spécifier sur quel compte le montant du champ **Différence** sera reporté lorsque vous reportez le journal rapprochement bancaire. Vous pouvez le faire soit à partir de la page **Journal rapprochement bancaire** ou à partir de la page **Révision affectation paiement** que vous ouvrez en choisissant la valeur dans le champ **Fiabilité correspondance** ou en choisissant le champ **Différence**.

> [!TIP]  
>   Il existe une fonctionnalité similaire permettant de configurer le rapprochement automatique des paiements récurrents qui ne peuvent pas être affectés aux écritures ouvertes associées du grand livre client, fournisseur ou compte bancaire. Pour plus d'informations, voir [Mapper du texte sur les paiements récurrents aux comptes pour un rapprochement automatique](receivables-how-map-text-recurring-payments-accounts-auto-reconcilliation.md).

## <a name="to-reconcile-payments-that-cant-be-applied-automatically"></a>Pour rapprocher les paiements qui ne peuvent pas être appliqués automatiquement
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux rapprochement bancaire**, puis sélectionnez le lien associé.
2. Ouvrez un journal rapprochement paiement. Pour plus d'informations, reportez-vous à [Rapprocher les paiements à l'aide du lettrage automatique](receivables-how-reconcile-payments-auto-application.md).
3. Sélectionnez l'action **Transférer la différence vers un compte**. La page **Transférer la différence vers un compte** s'ouvre.
4. Dans le champ **Type compte**, spécifiez le type de compte sur lequel le montant du paiement sera validé.
5. Dans le champ **N° compte**, spécifiez le compte dans lequel le montant du paiement sera reporté.
6. Dans le champ **Description**, spécifiez le texte qui décrit cette validation de prélèvement. Par défaut, le texte du champ **Texte transaction** de la ligne feuille rapprochement bancaire est inséré.
7. Cliquez sur le bouton **OK**.

Si la valeur du champ **Différence** est égale à la valeur du champ **Montant transaction** lorsque vous validez la feuille rapprochement bancaire, l'intégralité du paiement sur la ligne feuille sera validé directement dans le compte contrepartie spécifié.

Si la valeur du champ **Différence** était inférieure à la valeur du champ **Montant transaction**, une ligne feuille supplémentaire est créée avec le même texte et la même date et avec la différence insérée dans le champ **Montant transaction**. Sur la ligne feuille d'origine, la différence est déduite de la valeur du champ **Montant transaction**, et le paiement demeure lettré à son écriture comptable client, fournisseur ou compte bancaire associée. Lorsque vous reportez le journal rapprochement paiement, une partie du paiement est reportée en tant que paiement affecté. L'autre partie du paiement est reportée directement dans le compte spécifié.

## <a name="see-also"></a>Voir aussi .
[Gestion des comptes client](receivables-manage-receivables.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
