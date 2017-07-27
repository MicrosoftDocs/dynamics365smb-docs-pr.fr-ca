---
title: "Annuler un report journal en reportant une écriture de contrepassation| Microsoft Docs"
description: "Si vous avez effectué une erreur de report dans le journal général, vous pouvez utiliser la fonction Inverser la transaction pour annuler le report avec une piste d'audit correcte."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: reimbursement
ms.date: 06/15/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 8126a53d59e72276eb1558fd65fe3c0cd53600cc
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="how-to-reverse-journal-posting"></a>Procédure : inverser un report journal
Pour annuler un report journal erroné, sélectionnez l'écriture et créez une écriture inverse (écritures identiques aux écritures originales mais avec le signe opposé dans le champ de montant) portant les mêmes numéro de document et date de report que l'écriture d'origine. Une fois l'écriture inversée, créez l'écriture correcte.

Vous pouvez uniquement inverser les écritures reportées à partir d'une ligne journal général. Une écriture ne peut être inversée qu'une seule fois.

Pour plus d'informations sur la validation d'une feuille comptabilité, voir [Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md).

Vous pouvez inverser des écritures dans toutes les fenêtres **Écritures comptables**. La procédure suivante se base sur la fenêtre **Écritures comptables**.

## <a name="to-reverse-the-journal-posting-of-a-general-ledger-entry"></a>Pour inverser le report journal d'une écriture grand livre
1. Choisissez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Ecritures comptables**, puis sélectionnez le lien connexe.
2. Sélectionnez l'écriture à contrepasser, puis cliquez sur l'action **Contrepasser la transaction**. Notez qu'elle doit provenir d'un report journal.
3. Dans la fenêtre **Contrepasser les écritures de transaction**, sélectionnez l'écriture voulue, puis sélectionnez l'action **Contrepasser**.
4. Choisissez le bouton **Oui** dans le message de confirmation.

## <a name="see-also"></a>Voir aussi
[Procédure : Valider les transactions directement vers la comptabilité](finance-how-post-transactions-directly.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Finances](finance.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

