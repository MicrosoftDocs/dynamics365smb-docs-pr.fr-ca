---
title: Comment configurer des agents de livraison
description: Découvrez comment configurer un code pour chacun de vos agents de livraison et saisir des informations descriptives concernant chacun d’entre eux et les services qu’ils proposent.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Configurer des agents de livraison
Vous pouvez définir un code pour chacun de vos transporteurs et saisir les informations qui les concernent.  

Si vous saisissez une adresse Internet pour l'agent de livraison, et que l'agent de livraison fournit des prestations de traçabilité des colis sur Internet, vous pouvez utiliser la fonction de suivi de colis automatique. Pour plus d'informations, voir [Suivre des colis](sales-how-track-packages.md).

Lorsque vous configurez des agents de livraison sur vos documents de vente, vous pouvez également spécifier les services proposés par chaque agent de livraison.  
Pour chaque agent de livraison, vous pouvez configurer un nombre illimité de services et spécifier un délai de livraison pour chaque service.  

Lorsque vous avez affecté une service agent de livraison à une ligne document de vente, le délai de livraison du service est inclus dans le calcul de la promesse de livraison, pour cette ligne. Pour plus d'informations, voir [Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).

## Pour configurer un agent de livraison  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Agents de livraison**, puis sélectionnez le lien associé.  
2.  Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].  
3.  Sélectionnez l'action **Services agent de livraison**.
4. Dans la fenêtre **Services agent de livraison**, renseignez les champs selon vos besoins.

> [!NOTE]  
>  Si vous supprimez l'agent de livraison de la ligne commande, le code prestation agent de livraison est également supprimé. La valeur des champs basée en partie sur la prestation agent de livraison est ensuite recalculée.  

## Voir aussi
[Configurer des méthodes de livraison](sales-how-set-up-shipment-methods.md)  
[Suivre des colis](sales-how-track-packages.md)    
[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]