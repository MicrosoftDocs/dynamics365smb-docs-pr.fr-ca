---
title: Comment configurer des modèles rangement | Microsoft Docs
description: À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/24/2020
ms.author: edupont
ms.openlocfilehash: 8e6f248768f558f3bc5e12002234ffb56b006759
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3780020"
---
# <a name="set-up-put-away-templates"></a>Configurer des modèles rangement

À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes.  

Vous pouvez configurer un certain nombre de modèles rangement et en sélectionner un pour gérer les rangements dans votre entrepôt. Vous pouvez également sélectionner un modèle rangement pour un article ou une unité de stock disposant d'exigences spéciales en matière de rangement.  

## <a name="to-set-up-put-away-templates"></a>Pour configurer des modèles rangement

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Modèles rangement**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Entrez un code représentant l'identificateur unique du modèle que vous allez créer.  
4. Saisissez éventuellement une brève description.  
5. Renseignez la première ligne avec les exigences de zone à satisfaire en priorité lors de la proposition d'un rangement.

    Par exemple, si vous souhaitez que la méthode de rangement par défaut soit basée sur des zones fixes, choisissez le champ **Rechercher zone statique**. [!INCLUDE[tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
6. Renseignez la deuxième ligne avec les exigences de zone à satisfaire en deuxième lieu lors de la recherche d'une zone de rangement. La deuxième ligne est utilisée uniquement si une zone répondant aux exigences de la première ligne ne peut être trouvée.  
7. Continuez à renseigner les lignes jusqu'à ce que vous ayez décrit toutes les zones acceptables à utiliser au cours du rangement.  
8. Sur la dernière ligne du modèle rangement, cochez la case **Rechercher zone dynamique**.  

Vous pouvez créer plusieurs modèles rangement et les appliquer comme vous le souhaitez. On se réfère d'abord au modèle rangement sélectionné éventuel pour l'article ou l'unité de stock. Si ces champs ne sont pas renseignés, alors le modèle rangement sélectionné pour l'entrepôt sur le raccourci **Politiques de zones** de la fiche emplacement sera utilisé.  

## <a name="see-also"></a>Voir aussi

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
