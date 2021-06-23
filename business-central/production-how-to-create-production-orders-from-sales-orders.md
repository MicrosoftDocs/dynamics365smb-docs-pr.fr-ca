---
title: Créer des bons de production à partir de documents de vente
description: Vous pouvez créer des bons de production à partir de documents de vente.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 05/28/2021
ms.author: edupont
ms.openlocfilehash: 438f4d4e1833ba607ceedb9f5d9450c0a4dbb680
ms.sourcegitcommit: f9a190933eadf4608f591e2f1b04c69f1e5c0dc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/28/2021
ms.locfileid: "6115246"
---
# <a name="create-production-orders-from-sales-orders"></a>Créer des bons de production à partir de documents de vente
Vous pouvez créer des bons de production pour les articles produits directement à partir des documents de vente.  

## <a name="to-create-a-production-order-from-a-sales-order"></a>Pour créer un bon de production à partir d'un document de vente  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Sélectionnez le document de vente pour lequel vous voulez créer un bon de production.  
3.  Sélectionnez l'action **Planification**. Sur la page **Planification document de vente**, vous pouvez afficher la disponibilité de l'article de document de vente.  
4.  Sélectionnez l'action **Créer O.F**.  
5.  Sélectionnez l'état et le type de commande.  
6.  Choisissez le bouton **Oui** pour créer un ou plusieurs bons de production pour les lignes ayant **Bon de production** dans le champ **Système réapprovisionnement**.


> [!NOTE]  
> Les lignes de demandes du bon de production créé qui ont **Bon de production** dans le champ **Système réapprovisionnement** représentent des bons de production sous-jacents. Après avoir généré ces bons de production, n’oubliez pas d’identifier toute demande de composante non réalisée pour ceux-ci à l’aide de la page **Planification commande** ou de la fonction **Replanifier** à partir d’ordres créés. 

## <a name="order-type"></a>Type de commande  
Vous pouvez choisir entre deux façons de créer les bons de production, comme indiqué dans le tableau suivant.

|Option|Description|
|------|-----------|
|O.F. article|Un bon de production est créé pour chaque bon de production nécessaire qui est représenté par une ligne dans la fenêtre **Planification document de vente**.|
|O.F. projet|Un bon de production est créé pour tous les bons de production nécessaires qui sont représentés par des lignes dans la fenêtre **Planification document de vente**. |

Lorsque vous utilisez des projets de commande, le champ **Type origine** du bon de production indique **En-tête vente** et la commande comporte plusieurs lignes, une pour chaque article de la ligne vente à produire.  


## <a name="see-also"></a>Voir aussi  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
