---
title: Établir rapidement des factures achat
description: Si vous devez payer le fournisseur en liquide ou par chèque, vous pouvez effectuer toutes les opérations nécessaires lorsque vous reportez la facture.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: ''
ms.date: 10/06/2020
ms.author: bholtorf
ms.openlocfilehash: fb442c7b1e9e7bdcb727ca6de157657e370e254f
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4746851"
---
# <a name="settle-purchase-invoices-promptly"></a>Établir rapidement des factures achat

Si vous devez payer le fournisseur en liquide ou par chèque, vous pouvez reporter le paiement lorsque vous reportez la facture.  

> [!NOTE]  
> Si vous payez fréquemment les factures par chèques, par transfert bancaire ou en espèces, il est conseillé de configurer un mode de règlement spécifique avec un compte de contrepartie et de saisir ce mode dans le champ **Mode de règlement** sur la fiche fournisseur. Le programme insère automatiquement le numéro du compte contrepartie sur l'en-tête facture à chaque fois que vous créez une facture. Pour plus d’informations, consultez [Définir les modes de règlement](finance-payment-methods.md).  

## <a name="to-settle-purchase-invoices-promptly"></a>Pour établir rapidement des factures achat

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Pour payer en liquide ou par virement bancaire, saisissez le numéro du compte règlement du grand livre ou du compte bancaire dans le champ **N° compte contrepartie**.  

> [!IMPORTANT]  
> Les champs **Type compte contrepartie** et **N° compte contrepartie** ne font pas partie de la présentation standard de l'en-tête facture. Afin de reporter le paiement d’une facture, vous devez contacter un partenaire Microsoft qui peut ajouter les champs par code.  
>
> Cette personnalisation n’est requise que si vous ne spécifiez pas de comptes de contrepartie sur les modes de paiement comme décrit ci-dessus.

## <a name="see-also"></a>Voir aussi

[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
