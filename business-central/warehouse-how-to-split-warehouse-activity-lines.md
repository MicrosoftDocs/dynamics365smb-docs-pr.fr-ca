---
title: Comment répartir des lignes activité entrepôt | Microsoft Docs
description: Dans le cadre de rangements, mouvements ou prélèvements entrepôt et de rangements et prélèvements inventaire, des zones sont proposées pour le prélèvement et le rangement des articles. Il arrive parfois que la quantité réelle disponible dans la zone soit insuffisante ou que l'espace de la zone proposé soit insuffisant pour le rangement de la quantité nécessaire. Dans ces cas, vous devez répartir la ligne de telle sorte que les articles d'une ligne soient prélevés ou placés dans plusieurs zones.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 1d1ae140b8a5b2816141696dd4c8eabf702c02da
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2876450"
---
# <a name="split-warehouse-activity-lines"></a>Répartir des lignes activité entrepôt
Dans le cadre de rangements, mouvements ou prélèvements entrepôt et de rangements et prélèvements inventaire, des zones sont proposées pour le prélèvement et le rangement des articles. Il arrive parfois que la quantité réelle disponible dans la zone soit insuffisante ou que l'espace de la zone proposé soit insuffisant pour le rangement de la quantité nécessaire. Dans ces cas, vous devez répartir la ligne de telle sorte que les articles d'une ligne soient prélevés ou placés dans plusieurs zones.  

La procédure suivante s'applique aux documents entrepôt, à savoir les lignes de rangement, de mouvement et de prélèvement entrepôt, ainsi que les lignes de rangement, de mouvement et de prélèvement inventaire.  

## <a name="to-split-warehouse-activity-lines"></a>Pour éclater des lignes activité entrepôt  
1.  Ouvrez une ligne activité entrepôt dans laquelle vous tentez de traiter une quantité insuffisante.  
2.  Dans le champ **Quantité à traiter**, entrez la quantité réduite que vous pouvez gérer.  
3.  Sur le raccourci **Lignes**, choisissez l'action **Actions**, choisissez **Fonctions**, puis choisissez l'action **Eclater ligne**. Une nouvelle ligne s'affiche. Il s'agit d'une copie de la ligne d'origine, à la différence près que la quantité que vous avez retirée de la ligne d'origine figure dans le champ **Quantité à traiter**.  
4.  Affectez à cette nouvelle ligne une zone appropriée et, en cas d'utilisation d'un prélèvement et d'un rangement suggérés, une zone, ou continuez à répartir la ligne autant de fois que nécessaire jusqu'à ce que vous ayez trouvé des zones appropriées pour toute la quantité.  

> [!NOTE]  
>  Si, en cas d'utilisation d'un prélèvement et d'un rangement suggérés dans l'emplacement, vous éclatez les lignes, vous devez bien connaître l'entrepôt et être capable de choisir une zone répondant aux exigences de stockage de l'article et aux exigences générales du document entrepôt. Par exemple, vous n'allez pas répartir une ligne d'un document prélèvement et placer certains articles au niveau du stockage en vrac.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
