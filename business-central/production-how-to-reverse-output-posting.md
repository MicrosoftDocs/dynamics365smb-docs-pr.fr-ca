---
title: 'Procédure : inverser le report de production'
description: Il arrive qu'un report de production doive être inversé. Cette rubrique décrit la procédure d’inversion du report de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/22/2021
ms.author: edupont
ms.openlocfilehash: b1d3d05876beb452d8a3fd1ac917e40f1ffe7320
ms.sourcegitcommit: a7cb0be8eae6ece95f5259d7de7a48b385c9cfeb
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/08/2021
ms.locfileid: "6440363"
---
# <a name="reverse-output-posting"></a>Inverser un report de production
Il arrive qu'un report de production doive être inversé. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production.  

## <a name="to-reverse-an-output-posting"></a>Pour inverser un report de production  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal de sortie**, puis choisissez le lien associé. Sélectionnez votre lot.  
2. Renseignez les champs selon vos besoins. Pour plus d'informations, voir [Exécuter en lot la production et les temps d'exécution](production-how-to-post-output-quantity.md).
3.  Dans le champ **Écriture de référence**, sélectionnez l'écriture article associée. Cette opération inverse les écritures capacité et du grand livre d'articles.  
4. Reportez la contrepassation en reportant le journal.  

Les écritures journal production sont reportées dans le grand livre article comme un ajustement positif.  

## <a name="see-also"></a>Voir aussi  
 [Production](production-manage-manufacturing.md)    
 [Paramétrage de la production](production-configure-production-processes.md)  
 [Planification](production-planning.md)      
 [Inventaire](inventory-manage-inventory.md)  
 [Procédure d'achat](purchasing-manage-purchasing.md)  
 [Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]