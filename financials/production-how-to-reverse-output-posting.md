---
title: "Procédure : inverser un report de sortie | Microsoft Docs"
description: "Il arrive qu'un report de production doive être inversé. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 7ac453ff87d78e6be0567ba93b58c0f8938f4052
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-reverse-output-posting"></a>Procédure : inverser le report de production
Il arrive qu'une validation de production doive être contrepassée. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été validée pour un ordre de fabrication.  

## <a name="to-reverse-an-output-posting"></a>Pour inverser un report de production  
1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille production**, puis sélectionnez le lien connexe. Sélectionnez votre lot.  
2. Renseignez les champs selon vos besoins. Pour plus d'informations, voir [Procédure : exécuter en lot la sortie et les temps d'exécution](production-how-to-post-output-quantity.md).
3.  Dans le champ **Écriture de référence**, sélectionnez l'écriture article associée. Cette opération inverse les écritures capacité et du grand livre d'articles.  
4. Reportez la contrepassation en reportant le journal.  

Les écritures journal production sont reportées dans le grand livre article comme un ajustement positif.  

## <a name="see-also"></a>Voir aussi  
 [Production](production-manage-manufacturing.md)    
 [Paramétrage de la production](production-configure-production-processes.md)  
 [Planification](production-planning.md)      
 [Stock](inventory-manage-inventory.md)  
 [Procédure d'achat](purchasing-manage-purchasing.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

