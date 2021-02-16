---
title: 'Procédure : exécuter en lot la consommation | Microsoft Docs'
description: Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: ad21fa7f0a18b3549bdab19c07e0065d5fb684dd
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759177"
---
# <a name="batch-post-production-consumption"></a>Exécuter en lot la consommation de la production
Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.

Vous pouvez également configurer le système pour reporter automatiquement (*consommer*) les composantes lorsque vous lancez ou terminez des bons de production. Pour plus d'informations, voir [Activer la consommation des composantes en fonction de la sortie réalisée](production-how-to-flush-components-according-to-operation-output.md).

## <a name="to-post-consumption-for-one-or-more-production-order-lines"></a>Pour reporter la consommation pour une ou plusieurs lignes bon de production  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal consommation**, puis sélectionnez le lien associé.  
2.  Renseignez les champs en indiquant les données relatives au bon de production et à la consommation. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Si l'entrepôt dans lequel les composantes sont stockées est configuré pour utiliser des zones mais pas le traitement de prélèvement, affectez un code de zone à la ligne journal pour indiquer d'où les articles doivent être prélevés dans l'entrepôt. Pour plus d'informations, voir [Prélever pour la fabrication ou l'assemblage](warehouse-how-to-pick-for-production.md).  
3.  Choisissez l'action **Reporter** pour reporter la consommation. Les écritures article associées sont réduites.

## <a name="see-also"></a>Voir aussi  
[Production](production-manage-manufacturing.md)    
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
