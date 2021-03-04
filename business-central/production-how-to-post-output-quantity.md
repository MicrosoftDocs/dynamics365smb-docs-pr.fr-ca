---
title: "Procédure : exécuter en lot la sortie de production et les temps d'exécution | Microsoft Docs"
description: La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 82e28246f1a1c65c7bd702023d9c68c614383cc2
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759152"
---
# <a name="batch-post-output-and-run-times"></a>Exécuter en lot la production et les temps d'exécution
La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.  

> [!NOTE]
> L'inventaire est automatiquement mis à jour uniquement lorsque vous reportez la quantité sortie durant la dernière opération.  

## <a name="to-post-output-quantities-for-one-or-more-production-order-lines"></a>Pour reporter les quantités sorties pour une ou plusieurs lignes bon de production
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.  
2. Renseignez les champs en indiquant les données relatives à la fabrication et à la production. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Si l'opération est achevée, sélectionnez le champ **Terminé**.  

    Si l'emplacement entrepôt dans lequel les articles doivent être rangés utilise des zones mais n'exige pas le traitement des rangements, affectez un code de zone à la ligne journal pour indiquer l'endroit où les articles doivent être placés dans l'entrepôt. Pour plus d'informations, voir [Rangement du résultat de fabrication ou d'assemblage](warehouse-how-to-put-away-production-output.md).  

4. Choisissez l'action **Reporter** pour reporter les opérations. La quantité produite est reportée. L'article peut être livré.  

## <a name="to-post-run-times-for-one-or-more-production-order-lines"></a>Pour reporter les temps d'exécution pour une ou plusieurs lignes bon de production
Le temps d'exécution représente l'avancement des travaux en prenant en compte le temps de travail nécessaire.    

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.  
2. Renseignez les champs en indiquant les données relatives à la fabrication et à la production.  
3.  Si l'opération est achevée, sélectionnez le champ **Terminé**.  
4. Choisissez l'action **Reporter** pour reporter le temps passé par opération. Les écritures du grand livre de capacité sont mises à jour pour les unités de production ou les ateliers utilisés.

## <a name="see-also"></a>Voir aussi  
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]