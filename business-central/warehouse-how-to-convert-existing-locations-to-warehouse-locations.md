---
title: Comment convertir des emplacements existants en emplacements entrepôt | Microsoft Docs
description: Vous pouvez permettre à un emplacement d'inventaire d'utiliser les zones et de devenir l'entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 6f8b27c4b0abc4221bd081df8474876577e476e6
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3911875"
---
# <a name="convert-existing-locations-to-warehouse-locations"></a>Convertir des emplacements existants en entrepôts
Vous pouvez permettre à un emplacement d'inventaire d'utiliser les zones et de devenir l'entrepôt.  

Le traitement en lot qui active un emplacement pour une opération d'entrepôt crée des écritures d'entrepôt initiales pour la zone d'ajustement de l'entrepôt pour tous les articles stockés à cet emplacement. Ces écritures sont équilibrées lorsque les écritures d'inventaire physique entrepôt sont saisies après chaque traitement en lot.  

Vous pouvez créer des zones et des emplacements avant ou après la conversion. La seule zone devant être créée avant la conversion est celle qui servira ensuite de zone d'ajustement.  

> [!IMPORTANT]  
>  Pour supprimer toutes les quantités négatives et les éventuels documents entrepôt ouverts avant de convertir l'emplacement à des fins de gestion d'entrepôt, exécutez un rapport pour identifier les articles dont la quantité est négative et les documents entrepôt ouverts pour l'emplacement. Pour plus d'informations, reportez\-vous à la rubrique Vérifiez l'inventaire négatif.  

## <a name="to-enable-an-existing-location-to-operate-as-a-warehouse-location"></a>Activation d'un emplacement existant en tant qu'entrepôt  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Création emplacement entrepôt** , puis sélectionnez le lien associé.  
2.  Dans le champ **Code magasin** , indiquez le magasin que vous souhaitez activer pour un traitement d'entrepôt.  
3.  Dans le champ **Code de zone d'ajustement** , spécifiez dans quelle zone de l'emplacement les écritures entrepôt non synchronisées sont enregistrées. Pour plus d'informations, voir [Pour synchroniser les écritures entrepôt ajustées avec les écritures article associées](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).  

    À l'aide des écritures article ouvertes pour l'emplacement spécifié, des lignes journal entrepôt sont créées, lesquelles additionnent les combinaisons N° article, Code variante, Code unité de mesure et, si nécessaire, N° lot et N° de série dans les écritures article. Les lignes journal entrepôt sont ensuite reportées. Ce report crée des écritures d'entrepôt qui placent l'inventaire dans la zone d'ajustement entrepôt. Le **code emplacement ajustement** est également défini dans la fiche magasin.  

4.  Pour savoir quels articles ont été ajoutés à l'emplacement ajustement pendant le traitement par lots, vous pouvez exécuter l'état **Emplacement ajust. mag** .  
5.  Une fois le traitement par lots **Création entrepôt** terminé, vous devez effectuer et valider un inventaire physique entrepôt. Pour plus d'informations, voir [Inventaire, ajustement et reclassement de l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md).  

> [!NOTE]  
>  Il est recommandé de lancer le traitement en lot **Création entrepôt** à un moment où il ne risque pas de nuire au fonctionnement habituel du système. Étant donné que ce processus traite chaque écriture de la table **Écriture comptable article** , il peut durer plusieurs heures si cette table en comporte un grand nombre.  

 Dans le cas d'emplacements n'ayant pas utilisé de documents de gestion d'entrepôt avant la conversion, vous devez rouvrir et libérer les documents sources dont la réception ou la livraison n'était que partielle avant la conversion.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
