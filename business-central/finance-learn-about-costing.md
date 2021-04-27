---
title: À propos de l'évaluation du stock | Microsoft Docs
description: La gestion des coûts d'inventaire fait référence à l'enregistrement et au report des coûts d'exploitation de l'entreprise. Inclut le report des coûts de fabrication et des coûts inventaire qui constituent la valeur des articles.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 33a6a66cb2ccdcee1cd5925548e7c224d244459e
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5770376"
---
# <a name="about-inventory-costing"></a>À propos de l'évaluation des coûts de stock
La gestion des coûts d'inventaire fait référence à l'enregistrement et au report des coûts d'exploitation de l'entreprise. Inclut le report des coûts de fabrication et des coûts inventaire qui constituent la valeur des articles.  

 Il est essentiel de comprendre les principes suivants : les méthodes d'évaluation du coût définissent le mode d'évaluation des articles lors de leur sortie de l'inventaire, l'ajustement des coûts met à jour le coût des marchandises vendues avec les coûts d'achat associés reportés après la vente, les valeurs en inventaire doivent être reportées sur les comptes du grand livre appropriés à intervalles réguliers.  

 Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Distinguer les cinq différentes méthodes d'évaluation des stocks au prix coûtant et leurs effets sur les flux de coûts.|[Détails de conception : modes évaluation stock](design-details-costing-methods.md)|  
|Apprendre comment les écritures d'affectation article associent de manière dynamique les diminutions d'inventaire avec les augmentations pour contrôler les flux de coûts.|[Détails de conception : lettrage article](design-details-item-application.md)|  
|Apprendre la manière dont le coût unitaire d'un article est continuellement mis à jour avec le coût de sa dernière transaction conformément à la méthode d'évaluation des stocks au prix coûtant associée à cet article.|[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)|  
|Apprendre la manière dont le coût moyen d'un article est calculé de manière dynamique en fonction de la période coût moyen sélectionnée.|[Détails de conception : coût moyen](design-details-average-cost.md)|  
|Distinguer les coûts prévus (non encore facturés) des coûts réels et apprendre la manière dont ils sont gérés dans le grand livre.|[Détails de conception : validation du coût prévu](design-details-expected-cost-posting.md)|  
|Comprendre le mécanisme d'ajustement des coûts, qui permet d'assurer que les coûts sont reportés même si des transactions d'inventaire ont lieu de manière aléatoire.|[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)|  
|Apprendre pourquoi les coûts standard sont souvent utilisés par les compagnies de production comme base d'évaluation pour les composantes et les produits finis.|[À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md)|  
|Comprendre la manière dont la valeur de l'inventaire est reflétée dans le grand livre.|[Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md)|  
|Apprendre la manière dont les frais annexes, tels que les frais de transport ou d'assurance, peuvent affecter des composantes supplémentaires au coût unitaire d'un article.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|  
|Obtenir des informations sur la manière dont les périodes d'inventaire permettent à une compagnie de contrôler la valeur de l'inventaire dans le temps en définissant des périodes plus courtes qui peuvent être fermées au report lorsque la fin de l'exercice financier approche.|[Utiliser les périodes d'inventaire](finance-how-to-work-with-inventory-periods.md)|  
|Comprendre tous les mécanismes du moteur d'évaluation, notamment ce qui se produit lorsque vous reportez des transactions d'assemblage et de production.|[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)|  

## <a name="see-also"></a>Voir aussi
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)    
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]