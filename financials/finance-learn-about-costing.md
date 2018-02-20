---
title: "À propos de l'évaluation du stock | Microsoft Docs"
description: "La gestion des coûts d'inventaire fait référence à l'enregistrement et au report des coûts d'exploitation de l'entreprise. Inclut le report des coûts de fabrication et des coûts inventaire qui constituent la valeur des articles."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 5c942b0e0dcdc025fdeca6373fe30b485a147ad2
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

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
|Comprendre la manière dont la valeur de l'inventaire est reflétée dans le grand livre.|[Génération de rapports sur les coûts et rapprochement avec le grand livre](finance-report-costs-and-reconcile-with-the-general-ledger.md)|  
|Apprendre la manière dont les frais annexes, tels que les frais de transport ou d'assurance, peuvent affecter des composantes supplémentaires au coût unitaire d'un article.|[Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md)|  
|Obtenir des informations sur la manière dont les périodes d'inventaire permettent à une compagnie de contrôler la valeur de l'inventaire dans le temps en définissant des périodes plus courtes qui peuvent être fermées au report lorsque la fin de l'exercice financier approche.|[Utiliser les périodes d'inventaire](finance-how-to-work-with-inventory-periods.md)|  
|Comprendre tous les mécanismes du moteur d'évaluation, notamment ce qui se produit lorsque vous reportez des transactions d'assemblage et de production.|[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)|

## <a name="see-also"></a>Voir aussi
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

