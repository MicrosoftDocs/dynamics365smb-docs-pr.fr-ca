---
title: Rupture de charge avec prélèvement et rangement dirigé
description: Découvrez comment activer la rupture de charge automatique avec prélèvement et rangement dirigé, ainsi que le déconditionnement pour prélèvement, rangement, mouvement, etc.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.search.form: 5703, 7352
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: f16fb21773a519edc77fca615d679e106b397af8
ms.sourcegitcommit: 5a02f8527faecdffcc54f9c5c70cefe8c4b3b3f4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/04/2022
ms.locfileid: "8382777"
---
# <a name="enable-automatic-breaking-bulk-with-directed-put-away-and-pick"></a>Activer la rupture de charge automatique avec prélèvement et rangement dirigé
Pour les emplacements qui utilisent un prélèvement et un rangement suggérés, [!INCLUDE[prod_short](includes/prod_short.md)] peut procéder, dans de nombreux cas, à un déconditionnement automatique (division d'une unité de mesure plus grande en unités de mesure plus petites) lorsqu'il crée des instructions entrepôt répondant aux exigences de documents sources, de bons de production ou de prélèvements et de rangements internes. Parfois, le déconditionnement peut également nécessiter le regroupement de petites unités de mesure afin de répondre à des demandes sortantes en divisant l'unité de mesure la plus grande du document origine ou du bon de production en unités de mesure plus petites disponibles dans l'entrepôt.   

## <a name="breakbulking-in-picks"></a>Déconditionnement pour prélèvement  
Pour stocker des articles dans plusieurs unités et permettre de les combiner automatiquement selon vos besoins au cours du prélèvement, sélectionnez le champ **Autoriser déconditionnement** de la fiche magasin.  

Pour répondre à une tâche, l'application recherche automatiquement un article de la même unité de mesure. S'il ne trouve pas ce type d'article et que vous avez sélectionné ce champ, l'application vous propose de diviser une unité de mesure plus grande en fonction de l'unité de mesure nécessaire.  

Si le système trouve uniquement des unités de mesure plus petites, il vous suggère de rassembler des articles afin de répondre à la quantité du bon de production ou de livraison. En fait, il divise la plus grande unité de mesure du document origine en unités de mesure de prélèvement plus petites.  

## <a name="breakbulking-in-put-aways"></a>Déconditionnement pour rangement  
Au niveau du rangement de l'entrepôt, l'application propose automatiquement des lignes action Emplacement dans l'unité de mesure de rangement, par exemple, pièces, même si les articles arrivent dans une unité de mesure différente.  

## <a name="breakbulking-in-movements"></a>Déconditionnement pour mouvement  
L'application effectue également un déconditionnement automatique au niveau des mouvements de réapprovisionnement, si le champ **Autoriser déconditionnement** est sélectionné sur le raccourci **Option** de la page **Calculer réappro. zone**.  

Vous pouvez afficher les résultats de la conversion entre deux unités de mesure sous forme de lignes déconditionnement intermédiaire dans les instructions rangement, prélèvement ou mouvement.  

> [!NOTE]  
>  Si vous sélectionnez le champ **Configurer filtre déconditionnement** dans l'en-tête instruction entrepôt, l'application masque les lignes déconditionnement chaque fois que la plus grande unité de mesure est utilisée dans son intégralité. Par exemple, si une palette comprend 12 pièces et que vous allez utiliser les 12 pièces, le prélèvement vous indique de prendre 1 palette et d'y placer les 12 pièces. Par contre, si vous ne devez prélever que 9 pièces, les lignes déconditionnement ne sont pas masquées, même si vous avez sélectionné le champ **Filtre déconditionnement**, étant donné que vous devez placer les trois pièces restantes dans un autre endroit de l'entrepôt.  

> [!NOTE]  
>  Pour optimiser l'utilisation des unités de mesure dans l'entrepôt (également avec la fonctionnalité de déconditionnement), effectuez dès que vous le pouvez les opérations suivantes :  
>   
> - Configurez l'unité de mesure de base d'un article en tant que plus petite unité de mesure à gérer dans les processus concernant l'entrepôt.  
> - Configurez les autres unités de mesure de l'article en tant que multiples de l'unité de mesure de base.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de Warehouse Management](warehouse-setup-warehouse.md) 
[Gestion d’assemblage](assembly-assemble-items.md)
[Détails de conception : Warehouse Management](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]