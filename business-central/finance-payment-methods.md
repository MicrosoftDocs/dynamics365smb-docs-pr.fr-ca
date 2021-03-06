---
title: Paramétrer les modes de paiement
description: Vous utilisez des modes de règlement, par exemple, les chèques, le transfert bancaire, les espèces, ou Paypal, pour définir la façon dont les factures vente et achat sont payées.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: check, bank transfer, cash, PayPal
ms.date: 04/01/2021
ms.author: bholtorf
ms.openlocfilehash: 1e836b43392cd915a77c5ee85d5a322753dcd5df
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5773965"
---
# <a name="set-up-payment-methods"></a>Paramétrer les modes de paiement

Les modes de règlement définissent le mode de paiement que vous souhaitez voir vos clients utiliser, et comment vous souhaitez payer les fournisseurs. Le mode peut varier pour chaque client ou fournisseur. Les exemples de modes de règlement courants sont **virement**, **espèces**, **chèque** ou **dépôt**.

Vous pouvez affecter un mode de règlement aux clients et aux fournisseurs pour que le même mode soit toujours utilisé dans les documents achat et vente que vous créez pour eux. Si nécessaire, vous pouvez modifier le mode du document vente ou achat. Par exemple, si vous souhaitez payer une facture achat donnée en espèces plutôt que par le chèque. Cela ne modifie pas le mode de règlement par défaut affecté au fournisseur.

Les mêmes modes de règlement sont utilisés pour les documents vente et achat. Par exemple, un mode de règlement _espèces_ est utilisé lorsque vous effectuez des paiements et lorsque vous recevez les. [!INCLUDE[prod_short](includes/prod_short.md)] sait que lorsque vous créez une facture vente vous pensez recevoir le paiement, et inversement pour les factures achat.

Toutefois, les notes de crédit pour les retours sont des exceptions, parce que le règlement s'effectue dans le sens inverse, de vous à votre client et de votre fournisseur à vous. Par conséquent, un mode de règlement par défaut n'est pas affecté aux notes de crédit. Il existe, cependant, une solution si vous avez spécifié des conditions de paiement pour le client ou le fournisseur. Bien que le champ **Calculer escompte de paiement sur les notes de crédit** ne soit pas prévu pour cela, si vous activez la case à cocher sur la page **Modalités de paiement**, un mode de règlement par défaut est ajouté lorsque vous créez une note de crédit. <br><br>  

> [!Video https://www.microsoft.com/videoplayer/embed/RE476Ys?rel=0]

## <a name="to-set-up-a-payment-method"></a>Pour configurer un mode de règlement

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des modes de règlement que les entreprises utilisent souvent. Vous pouvez cependant en ajouter autant que nécessaire.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Modes de règlement**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez éventuellement ajouter des modalités de paiement à votre mode de paiement. Pour plus d’informations, voir [Configurer des modalités de paiement](finance-payment-terms.md).  

## <a name="to-assign-a-payment-method-to-a-customer-or-vendor"></a>Pour affecter un mode de règlement à un client ou fournisseur

1. Choisissez l'icône d'![ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Client** ou **Fournisseur**, puis sélectionnez le lien associé.
2. Dans le champ **Code mode de règlement**, choisissez le mode à utiliser par défaut pour le client ou le fournisseur.

## <a name="see-also"></a>Voir aussi

[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)  
[Configurer des modalités de paiement](finance-payment-terms.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]