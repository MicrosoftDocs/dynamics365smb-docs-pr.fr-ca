---
title: Transfert automatique et écritures combinées | Microsoft Docs
description: En comptabilité analytique, vous pouvez transférer les écritures vers un type de coût à l'aide d'un report combiné. Vous pouvez spécifier si un type de coût reçoit des écritures combinées dans le champ **Combiner écritures** dans la définition du type de coût. Le tableau suivant décrit les différentes options.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
redirect_url: finance-transfer-and-post-cost-entries
ms.openlocfilehash: 8f6b5328b3a7b8cdcb4582deda363bdd0361ed9a
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1239002"
---
# <a name="automatic-transfer-and-combined-entries"></a>Transfert automatique et écritures combinées
En comptabilité analytique, vous pouvez transférer les écritures vers un type de coût à l'aide d'un report combiné. Vous pouvez spécifier si un type de coût reçoit des écritures combinées dans le champ **Combiner écritures** dans la définition du type de coût. Le tableau suivant décrit les différentes options.  

|Combiner des écritures|Description|  
|---------------------|-----------------|  
|Aucun|Chaque écriture est transférée individuellement vers le type de coût correspondant.|  
|Jour|Les écritures, dont la date de report est identique, sont transférées en une seule écriture vers le type de coût correspondant.|  
|Mois|Toutes les écritures du même mois calendaire sont transférées en une seul écriture vers le type de coût correspondant.|  

> [!IMPORTANT]  
>  Si vous avez coché la case **Transférer automatiquement à partir du GL** sur la page **Configuration de la comptabilité analytique**, [!INCLUDE[d365fin](includes/d365fin_md.md)] met à jour la comptabilité analytique après chaque report dans le grand livre. Les écritures combinées ne sont pas possibles.  

## <a name="see-also"></a>Voir aussi  
 [Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md)   
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
