---
title: Enregistrer les frais ou les revenus directement dans le grand livre| Microsoft Docs
description: "Pour les activités économiques qui ne sont pas représentées par un document, comme de plus petits frais ou règlements, vous pouvez créer les transactions associées en reportant des lignes de journal dans la fenêtre Journal général."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct posting, general ledger
ms.date: 06/28/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 6925c2ddb45973e060c7694a83bc03c7fbabcf41
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="post-transactions-directly-to-the-general-ledger"></a>Reporter les transactions directement dans le grand livre
La plupart des transactions financières sont reportées dans le grand livre via les documents commerciaux dédiés, tels que des factures achat et des documents de vente. Pour les activités économiques qui ne sont pas représentés par un document dans [!INCLUDE[d365fin](includes/d365fin_md.md)], comme de plus petits frais ou règlements, vous pouvez créer les transactions associées en validant des lignes de feuille dans la fenêtre **Feuille comptabilité**.

Une utilisation classique du journal général est de reporter les dépenses des employés avec leurs fonds propres au cours des activités professionnelles, pour un remboursement ultérieur. Pour plus d'informations, voir [Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md).

Les journaux généraux reportent les transactions financières directement sur les comptes du grand livre et d'autres comptes tels que les comptes bancaires, clients, fournisseurs et employés. Le report avec un journal général crée toujours des écritures dans les comptes du grand livre. C'est le cas même lorsque, par exemple, vous reportez une ligne journal sur un compte client, parce qu'une écriture est reportée dans un compte client du grand livre via un groupe de report. Vous pouvez personnaliser votre version d'un journal général en configurant un lot ou un modèle journal. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

Contrairement aux écritures qui sont reportées avec des documents qui nécessitent un processus de note de crédit, vous pouvez correctement inverser les écritures reportées avec le journal général. Pour plus d'informations, voir [Inverser des reports](finance-how-reverse-journal-posting.md).

## <a name="to-post-a-transaction-directly-to-a-general-ledger-account"></a>Pour reporter une transaction directement dans le compte GL
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles comptabilité**, puis sélectionnez le lien connexe.
2. Ouvrez le lot journal général approprié. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Sur une nouvelle ligne journal, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]    
4. Répétez l'étape 3 pour toutes les transactions distinctes que vous souhaitez reporter.

    > [!TIP]  
    > Si vous souhaitez saisir les lignes de transaction au-dessus d'une ligne compte contrepartie, par exemple, pour un compte bancaire, activez la case à cocher **Suggérer le montant contrepartie** de la ligne pour votre lot dans la fenêtre **Noms feuilles comptabilité**. Puis le champ **Montant** de la ligne compte contrepartie est automatiquement prérempli avec la valeur requise pour équilibrer les transactions.
5. Choisissez l'action **Valider** pour enregistrer les transactions sur les comptes généraux spécifiés.

## <a name="see-also"></a>Voir aussi
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Enregistrer et rembourser les frais des employés](finance-how-record-reimburse-employee-expenses.md)  
[Inverser des reports](finance-how-reverse-journal-posting.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

