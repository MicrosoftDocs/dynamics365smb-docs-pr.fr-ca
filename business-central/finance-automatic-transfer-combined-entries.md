---
title: "Transfert automatique et écritures combinées | Microsoft Docs"
description: "En comptabilité analytique, vous pouvez transférer les écritures vers un type de coût à l'aide d'un report combiné. Vous pouvez spécifier si un type de coût reçoit des écritures combinées dans le champ **Combiner écritures** dans la définition du type de coût. Le tableau suivant décrit les différentes options."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 11/13/2018
ms.author: sgroespe
redirect_url: finance-transfer-and-post-cost-entries
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 6f58e569bea6a42a9ee695095ce308e7a69e2a8d
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

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

