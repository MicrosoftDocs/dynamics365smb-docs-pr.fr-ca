---
title: 'Procédure : inverser un report de sortie | Microsoft Docs'
description: Il arrive qu'un report de production doive être inversé. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: fb107d6d165ede233799ab165d735c030c0c8bba
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813110"
---
# <a name="reverse-output-posting"></a>Inverser un report de production
Il arrive qu'un report de production doive être inversé. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production.  

## <a name="to-reverse-an-output-posting"></a>Pour inverser un report de production  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal de sortie**, puis sélectionnez le lien associé. Sélectionnez votre lot.  
2. Renseignez les champs selon vos besoins. Pour plus d'informations, voir [Exécuter en lot la production et les temps d'exécution](production-how-to-post-output-quantity.md).
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
