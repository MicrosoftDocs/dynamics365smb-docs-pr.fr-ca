---
title: "Activités entrepôt | Microsoft Docs"
description: "Entre la réception des biens et leur livraison, une série d'utilisations entrepôt internes a lieu pour assurer un flux efficace dans l'entrepôt, ainsi que pour organiser et mettre à jour les inventaires de la compagnie."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 604f7e55067efaebed412683ed51ce8717562688
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="warehouse-management"></a>Gestion d'entrepôt
Entre la réception des biens et leur livraison, une série d'utilisations entrepôt internes a lieu pour assurer un flux efficace dans l'entrepôt, ainsi que pour organiser et mettre à jour les inventaires de la compagnie.

Les activités entrepôt courantes incluent le rangement d'articles, leur déplacement entre plusieurs entrepôts et leur prélèvement à des fins d'assemblage, de production et de livraison. Assembler des articles pour les ventes ou l'inventaire peut également être considéré comme des activités entrepôt, mais cela est traité ailleurs. Pour plus d'informations, voir [Gestion d'assemblage](assembly-assemble-items.md).  

Dans les entrepôts importants, vous pouvez séparer ces tâches de traitement par département et gérer l'intégration par un flux suggéré. Dans les installations plus simples, le flux est moins formalisé et vous pouvez exécuter les activités entrepôt avec les rangements et prélèvements stock. Pour plus d'informations sur les configurations entrepôt de base et avancées, voir [Détails de conception : vue d'ensemble d'entrepôt](design-details-warehouse-overview.md).

Avant d'effectuer des activités entrepôt, vous devez configurer le système pour la complexité de traitement d'entrepôt appropriée. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Enregistrez la réception d'articles dans les emplacements entrepôts, soit avec un bon de commande uniquement, dans les configurations d'emplacement simples, soit avec une réception entrepôt, en cas de traitement d'entrepôt partiellement ou entièrement automatisé dans l'emplacement.|[Réceptionner des articles](warehouse-how-receive-items.md)|
|Contourner les processus de rangement et de prélèvement pour expédier un article directement de la réception ou fabrication à l'expédition.|[Transborder des articles](warehouse-how-to-cross-dock-items.md)|    
|Ranger les articles provenant des achats, retours vente, transferts ou de la production en fonction du processus d'entrepôt configuré.|[Rangement des articles](warehouse-put-away-items.md)|
|Déplacez des articles d'une zone à l'autre dans l'entrepôt.|[Déplacement d'articles](warehouse-move-items.md)|
|Prélever des articles à livrer, transférer ou consommer en assemblage ou production, en fonction du processus d'entrepôt configuré.|[Prélèvement des articles](warehouse-pick-items.md)|
|Enregistrez la livraison d'articles à partir d'emplacements entrepôts, soit avec un document de vente uniquement, dans les configurations d'emplacement simples, soit avec une livraison entrepôt, en cas de processus d'entrepôt partiellement ou entièrement automatisés dans l'emplacement.|[Livrer des articles](warehouse-how-ship-items.md)|  

## <a name="see-also"></a>Voir aussi  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 

