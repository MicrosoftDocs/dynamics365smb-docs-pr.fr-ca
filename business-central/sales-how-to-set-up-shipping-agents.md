---
title: 'Procédure : configurer des agents de livraison | Microsoft Docs'
description: Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 221578a174c6bd0dd87377340e97cd54a98d177b
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5778407"
---
# <a name="set-up-shipping-agents"></a>Configurer des agents de livraison
Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.  

Si vous saisissez une adresse Internet pour l'agent de livraison, et que l'agent de livraison fournit des prestations de traçabilité des colis sur Internet, vous pouvez utiliser la fonction de suivi de colis automatique. Pour plus d'informations, voir [Suivre des colis](sales-how-track-packages.md).

Lorsque vous configurez des agents de livraison sur vos documents de vente, vous pouvez également spécifier les services proposés par chaque agent de livraison.  
Pour chaque agent de livraison, vous pouvez configurer un nombre illimité de services et spécifier un délai de livraison pour chaque service.  

Lorsque vous avez affecté une service agent de livraison à une ligne document de vente, le délai de livraison du service est inclus dans le calcul de la promesse de livraison, pour cette ligne. Pour plus d'informations, voir [Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).

## <a name="to-set-up-a-shipping-agent"></a>Pour configurer un agent de livraison  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Agents de livraison**, puis sélectionnez le lien associé.  
2.  Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].  
3.  Sélectionnez l'action **Services agent de livraison**.
4. Dans la fenêtre **Services agent de livraison**, renseignez les champs selon vos besoins.

> [!NOTE]  
>  Si vous supprimez l'agent de livraison de la ligne commande, le code prestation agent de livraison est également supprimé. La valeur des champs basée en partie sur la prestation agent de livraison est ensuite recalculée.  

## <a name="see-also"></a>Voir aussi
[Configurer des méthodes de livraison](sales-how-set-up-shipment-methods.md)  
[Suivre des colis](sales-how-track-packages.md)    
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]