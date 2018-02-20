---
title: "Configurer une fiche emplacement et définir des acheminements de transfert| Microsoft Docs"
description: "Vous créez une fiche emplacement pour chaque emplacement où vous stockez des articles d'inventaire, par exemple, un entrepôt ou un centre de distribution, et configurez des acheminements pour le transfert d'articles entre emplacements."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 01/25/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 57e16fe7d7dd3edd832fb29773fc2a9c13cba153
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="set-up-locations"></a>Configurer des emplacements
Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez spécifier chaque emplacement avec une fiche emplacement et définir des acheminements transfert.

Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements. Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).

## <a name="to-create-a-location-card"></a>Pour créer une fiche emplacement
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Sélectionnez l'action **Nouveau**.
3. Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.

> [!NOTE]  
> De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

## <a name="to-create-a-transfer-route"></a>Pour créer un acheminement transfert
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), saisissez **Magasins**, puis sélectionnez le lien connexe.
2. Sinon, à partir de n'importe quelle fenêtre **Fiche magasin**, cliquez sur **Acheminements transfert**.
3. Sélectionnez l'action **Nouveau**.
4. Dans la fenêtre **Fiche magasin**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez à présent transférer des articles en inventaire entre deux emplacements. Pour plus d'informations, voir [Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).    

## <a name="see-also"></a>Voir aussi
[Gestion du stock](inventory-manage-inventory.md)  
[Transfert d'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

