---
title: "Comment configurer des modèles rangement | Microsoft Docs"
description: "À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 0316dfe2d8e601077ed67317b4a077036e0a8c33
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="set-up-put-away-templates"></a>Configurer des modèles rangement
À l'aide de la fonctionnalité de prélèvement et de rangement suggérée, la zone la plus appropriée pour vos articles à un moment donné est suggérée, en fonction du modèle rangement configuré pour l'entrepôt, des classements de zone et des quantités minimale et maximale définies pour les zones fixes.  

Vous pouvez configurer un certain nombre de modèles rangement et en sélectionner un pour gérer les rangements dans votre entrepôt. Vous pouvez également sélectionner un modèle rangement pour un article ou une unité de stock disposant d'exigences spéciales en matière de rangement.  

## <a name="to-set-up-put-away-templates"></a>Pour configurer des modèles rangement  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles de rangement**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Entrez un code représentant l'identificateur unique du modèle que vous allez créer.  
4.  Saisissez éventuellement une brève description.  
5.  Renseignez la première ligne avec les exigences de zone à satisfaire en priorité lors de la proposition d'un rangement.  
6.  Renseignez la deuxième ligne avec les exigences de zone à satisfaire en deuxième lieu lors de la recherche d'une zone de rangement. La deuxième ligne est utilisée uniquement si une zone répondant aux exigences de la première ligne ne peut être trouvée.  
7.  Continuez à renseigner les lignes jusqu'à ce que vous ayez décrit toutes les zones acceptables à utiliser au cours du rangement.  
8.  Sur la dernière ligne du modèle rangement, cochez la case **Rechercher zone dynamique**.  

Vous pouvez créer plusieurs modèles rangement et les appliquer comme vous le souhaitez. On se réfère d'abord au modèle rangement sélectionné éventuel pour l'article ou l'unité de stock. Si ces champs ne sont pas renseignés, alors le modèle rangement sélectionné pour l'entrepôt sur le raccourci **Politiques de zones** de la fiche emplacement sera utilisé.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

