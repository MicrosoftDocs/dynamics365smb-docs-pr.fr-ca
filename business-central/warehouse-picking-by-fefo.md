---
title: Comment activer le prélèvement par FEFO | Microsoft Docs
description: First-Expired-First-Out (FEFO) est une méthode de tri qui garantit que les articles les plus anciens, ceux qui ont les dates d'expiration les plus anciennes, sont prélevés en premier.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 1855391f5bf2c0807ac4ffcd8d42e0ea8122fd87
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8141867"
---
# <a name="enable-picking-items-by-fefo"></a>Activer le prélèvement d'articles par FEFO
First-Expired-First-Out (FEFO) est une méthode de tri qui garantit que les articles les plus anciens, ceux qui ont les dates d'expiration les plus anciennes, sont prélevés en premier.  

 Cette fonctionnalité ne fonctionne que lorsque les critères suivants sont réunis :  

-   L'article doit avoir un numéro de série/lot.  
-   Dans la configuration du code de traçabilité article de l'article, le champ **Traçabilité d'entrepôt par numéro de série** ou le champ **Traçabilité d'entrepôt par numéro de lot** doit être sélectionné.  
-   L'article doit être reporté dans l'inventaire avec une date d'expiration.  
-   Dans l'emplacement, les boutons de basculement **Prélèvement requis**, **Prélèvement par FEFO**, et **Zone obligatoire** doivent être activés.  

 Lorsque tous les critères sont réunis, les articles aux numéros de série/lot à prélever sont triés par ancienneté de prélèvements et mouvements, sauf pour les articles qui utilisent la traçabilité par numéro de série ou de lot.  

> [!NOTE]  
> Si certains articles avec numéros de série ou lot utilisent une traçabilité spécifique, ceux-ci sont respectés en premier et, en dessous, les numéros de série/lot non spécifiques restants sont listés selon FEFO.
<br /><br />
Si deux articles avec des numéros de série ou de lot ont la même date d'expiration, l’application sélectionne celui avec le plus petit numéro de lot ou de série.
<br /><br />
Lors du prélèvement d'articles avec numéro de série/de lot dans les emplacements configurés pour un prélèvement et un rangement suggérés, seules les quantités des zones de type *Prélèvement* sont prélevées selon FEFO.  
<br /><br />
Pour activer des mouvements selon FEFO, laissez le champ **Depuis zone** vide sur la page **Mouvement d'inventaire** ou les pages **Feuille mouvement**.  
<br /><br />
Si le champ **Report expiration strict** est sélectionné sur la **Fiche Code traçabilité**, seuls les articles non expirés seront inclus dans le prélèvement et les lignes seront triées selon le principe FEFO.

## <a name="see-also"></a>Voir aussi  
[Prélèvement des articles](warehouse-pick-items.md)   
[Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md)   
[Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md)   
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Stock](inventory-manage-inventory.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]