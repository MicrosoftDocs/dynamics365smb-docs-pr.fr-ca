---
title: Détails de conception - Ecart | Microsoft Docs
description: L'écart est défini comme la différence entre le coût réel et le coût standard, telle que décrite dans la formule suivante.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: a0ff9ed014897a1a285dc3f6817299ec38bc9886
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3920882"
---
# <a name="design-details-variance"></a>Détails de conception : écart
L'écart est défini comme la différence entre le coût réel et le coût standard, telle que décrite dans la formule suivante.  

 coût réel – coût standard = variance  

 Si le coût réel change, par exemple, si vous reportez des frais annexes à une date ultérieure, l'écart est mis à jour en conséquence.  

> [!NOTE]  
>  La réévaluation n'affecte pas le calcul de l'écart, puisqu'elle modifie uniquement la valeur de l'inventaire.  

## <a name="example"></a>Exemple :  
 L'exemple suivant présente la manière de calculer l'écart pour les articles achetés. Il est basé sur le scénario suivant :  

1.  L'utilisateur achète un article à 90,00 $, mais le coût standard est de 100,00 $. Par conséquent, la tolérance achat nette est de -10 $.  
2.  10,00 $ sont crédités sur le compte tolérance achat.  
3.  L'utilisateur reporte des frais article de 20,00 $. Par conséquent, le coût réel passe à 110 $, et la valeur de la tolérance achat passe à 10 $.  
4.  20,00 $ sont débités sur le compte tolérance achat. Par conséquent, la tolérance achat nette est de 10 $.  
5.  L'utilisateur réévalue l'article de 100,00 $ à 70,00 $. Cela n'affecte pas le calcul de l'écart, uniquement la valeur de l'inventaire.  

 Le tableau suivant montre les écritures valeur résultantes.  

 ![Calcul variance achat](media/design_details_inventory_costing_11_purchase_variance.png "Calcul variance achat")  

## <a name="determining-the-standard-cost"></a>Déterminer le coût standard  
 Le coût standard est utilisé pour calculer l'écart et le montant à capitaliser. Dans la mesure où le coût standard peut être modifié dans le temps en raison du calcul de mise à jour manuel, vous avez besoin d'un certain point dans le temps où le coût standard est fixe pour le calcul de l'écart. Ce point correspond au moment de la facturation de l'augmentation d'inventaire. Pour les articles fabriqués ou assemblés, le point auquel le coût standard est déterminé est lorsque le coût est ajusté.  

 Le tableau suivant montre la manière dont les différentes parts de coût sont calculées pour les articles produits et assemblés lorsque vous utilisez la fonction Calculer coût standard.  

|Coût total|Article acheté|Article produit/assemblé|  
|----------------|--------------------|------------------------------|  
|**Coût standard**||Coût matière niveau unique + Coût opératoire niveau unique + Coût s/traitance niveau unique + Frais gén. opérat. niveau unique + Frais gén. fabrication niveau unique.|  
|**Coût matériel à niveau unique**|Coût unitaire|![Équation 1](media/design_details_inventory_costing_11_equation_1.png "Équation 1")|  
|**Coût capacité à niveau unique**|Non applicable|![Équation 2](media/design_details_inventory_costing_11_equation_2.png "Équation 2")|  
|**Coût s/traitance niveau unique**|Non applicable|![Équation 3](media/design_details_inventory_costing_11_equation_3.png "Équation 3")|  
|**Frais gén. capac. niv. unique**|Non applicable|![Équation 4](media/design_details_inventory_costing_11_equation_4.png "Équation 4")|  
|**Frais gén. fabric. niv. unique**|Non applicable|(Coût matière niveau unique + Coût opératoire niveau unique + Coût s/traitance niveau unique) * Coût indirect % / 100 + Frais généraux|  
|**Coût matière multi-niveau**|Coût unitaire|![Équation 5](media/design_details_inventory_costing_11_equation_5.png "Équation 5")|  
|**Coût capacité multi-niveau**|Non applicable|![Équation 6](media/design_details_inventory_costing_11_equation_6.png "Équation 6")|  
|**Coût s/traitance multi-niv.**|Non applicable|![Équation 7](media/design_details_inventory_costing_11_equation_7.png "Équation 7")|  
|**Frais généraux opératoires multi-niveaux**|Non applicable|![Équation 8](media/design_details_inventory_costing_11_equation_8.png "Équation 8")|  
|**Frais gén. matière multi-niv.**|Non applicable|![Équation 9](media/design_details_inventory_costing_11_equation_9.png "Équation 9")|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : Modes évaluation stock](design-details-costing-methods.md) [Gestion des composants des coûts](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
