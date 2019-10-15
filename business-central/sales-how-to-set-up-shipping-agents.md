---
title: 'Procédure : configurer des agents de livraison | Microsoft Docs'
description: Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 27b362c9c9aabec842e28e631ca2b93c1515f2fc
ms.sourcegitcommit: 02e704bc3e01d62072144919774f1244c42827e4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2019
ms.locfileid: "2311990"
---
# <a name="set-up-shipping-agents"></a>Configurer des agents de livraison
Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.  

Si vous saisissez une adresse Internet pour l'agent de livraison, et que l'agent de livraison fournit des prestations de traçabilité des colis sur Internet, vous pouvez utiliser la fonction de suivi de colis automatique. Pour plus d'informations, voir [Suivre des colis](sales-how-track-packages.md).

Lorsque vous configurez des agents de livraison sur vos documents de vente, vous pouvez également spécifier les services proposés par chaque agent de livraison.  
Pour chaque agent de livraison, vous pouvez configurer un nombre illimité de services et spécifier un délai de livraison pour chaque service.  

Lorsque vous avez affecté une service agent de livraison à une ligne document de vente, le délai de livraison du service est inclus dans le calcul de la promesse de livraison, pour cette ligne. Pour plus d'informations, voir [Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).

## <a name="to-set-up-a-shipping-agent"></a>Pour configurer un agent de livraison  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Agents de livraison**, puis sélectionnez le lien associé.  
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
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
