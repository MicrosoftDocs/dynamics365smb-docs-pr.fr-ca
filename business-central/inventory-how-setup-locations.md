---
title: Configurer une fiche emplacement et définir des acheminements de transfert| Microsoft Docs
description: Vous créez une fiche emplacement pour chaque emplacement où vous stockez des articles d'inventaire, par exemple, un entrepôt ou un centre de distribution, et configurez des acheminements pour le transfert d'articles entre emplacements.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 10/01/2019
ms.author: SorenGP
ms.openlocfilehash: 5554bb1576705cd1f3cbcddc7ef33da7b5db3796
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2878327"
---
# <a name="set-up-locations"></a>Configurer des emplacements
Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez spécifier chaque emplacement avec une fiche emplacement et définir des acheminements transfert.

Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements. Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).
<br><br>  
  
> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq]

## <a name="to-create-a-location-card"></a>Pour créer une fiche emplacement
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacements**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.

> [!NOTE]  
> De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

## <a name="to-create-a-transfer-route"></a>Pour créer un acheminement transfert
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Acheminements transfert**, puis sélectionnez le lien associé.
2. Sinon, à partir de n'importe quelle page **Fiche emplacement**, cliquez sur **Acheminements transfert**.
3. Sélectionnez l'action **Nouveau**.
4. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez à présent transférer des articles en inventaire entre deux emplacements. Pour plus d'informations, voir [Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).    

## <a name="see-also"></a>Voir aussi
[Gestion du stock](inventory-manage-inventory.md)  
[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)
