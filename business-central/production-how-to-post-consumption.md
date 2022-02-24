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
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 9200256cec074e547bc594950b1eb2d975a8ad9b
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2877893"
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
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
