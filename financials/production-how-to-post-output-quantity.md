---
title: "Procédure : exécuter en lot la sortie de production et les temps d'exécution | Microsoft Docs"
description: "La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée."
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
ms.openlocfilehash: ee5ee5d08804439a79f8029eaa25ab7547349a1b
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-batch-post-output-and-run-times"></a>Procédure : exécuter en lot la sortie et les temps d'exécution
La quantité produite représente l'avancée des travaux en prenant en compte la quantité achevée.  

> [!NOTE]
> L'inventaire est automatiquement mis à jour uniquement lorsque vous reportez la quantité sortie durant la dernière opération.  

## <a name="to-post-output-quantities-for-one-or-more-production-order-lines"></a>Pour reporter les quantités sorties pour une ou plusieurs lignes bon de production
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Journal de sortie**, puis sélectionnez le lien associé.  
2. Renseignez les champs en indiquant les données relatives à la fabrication et à la production. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Si l'opération est achevée, sélectionnez le champ **Terminé**.  

    Si l'emplacement entrepôt dans lequel les articles doivent être rangés utilise des zones mais n'exige pas le traitement des rangements, affectez un code de zone à la ligne journal pour indiquer l'endroit où les articles doivent être placés dans l'entrepôt. Pour plus d'informations, voir [Procédure : rangement du résultat de fabrication ou d'assemblage](warehouse-how-to-put-away-production-output.md).  

4. Choisissez l'action **Reporter** pour reporter les opérations. La quantité produite est reportée. L'article peut être livré.  

## <a name="to-post-run-times-for-one-or-more-production-order-lines"></a>Pour reporter les temps d'exécution pour une ou plusieurs lignes bon de production
Le temps d'exécution représente l'avancement des travaux en prenant en compte le temps de travail nécessaire.    

1.  Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuille production**, puis sélectionnez le lien connexe.  
2. Renseignez les champs en indiquant les données relatives à la fabrication et à la production.  
3.  Si l'opération est achevée, sélectionnez le champ **Terminé**.  
4. Choisissez l'action **Reporter** pour reporter le temps passé par opération. Les écritures du grand livre de capacité sont mises à jour pour les unités de production ou les ateliers utilisés.

## <a name="see-also"></a>Voir aussi  
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

