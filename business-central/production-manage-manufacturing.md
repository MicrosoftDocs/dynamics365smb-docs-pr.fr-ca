---
title: Exécuter la production | Microsoft Docs
description: Lorsque la demande est planifiée et les matières ont été produites conformément aux nomenclatures de production, les opérations de production réelles peuvent commencer et être exécutées selon la séquence définie par l'itinéraire du bon de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 85c5a8fda1f390ff4f4ac71b36a087712003b38e
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5383260"
---
# <a name="manufacturing"></a>Production
> [!NOTE]
> La fonctionnalité décrite dans ces rubrique et sous-rubriques n'est visible dans l'interface utilisateur que si vous avez l'expérience **Premium**. Pour plus d'informations, voir [Modifier les fonctionnalités affichées](ui-experiences.md).

Lorsque la demande est planifiée et les matières ont été produites conformément aux nomenclatures de production, les opérations de production réelles peuvent commencer et être exécutées selon la séquence définie par l'itinéraire du bon de production.  

Du point de vue du système, une grande partie de l'exécution de la production consiste à reporter cette dernière dans la base de données pour enregistrer l'avancement et mettre à jour l'inventaire avec les articles terminés. Le report de la production peut être effectuée manuellement en renseignant et en reportant les lignes journal après les opérations de production. La validation peut également être automatisée en utilisant la consommation en amont. Dans ce cas, la consommation de matières est automatiquement reportée en même temps que la production lors du changement de l'état du bon de production en Terminé.  

Outre le journal lot de report de la production pour plusieurs bons de production, vous pouvez utiliser la page **Journal production** pour reporter la consommation et/ou la production d'une ligne bon de production.

Avant de pouvoir commencer à produire des articles, vous devez procéder à diverses configurations, telles que les ateliers, les itinéraires et les nomenclatures de production. Pour plus d'informations, voir [Paramétrage de la production](production-configure-production-processes.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Comprendre le fonctionnement des ordres de fabrication.|[À propos des ordres de fabrication](production-about-production-orders.md)|
|Créer manuellement des ordres de fabrication.|[Créer des ordres de fabrication](production-how-to-create-production-orders.md)|
|Confier à un sous-traitant toutes les opérations ou les opérations sélectionnées dans un ordre de fabrication.|[Sous-traiter la production](production-how-to-subcontract-manufacturing.md)|
|Enregistrez et reportez la sortie de production, ainsi que la consommation matière et temps, pour une seule ligne bon de production libéré.|[Reporter la consommation et la production pour une ligne bon de production libéré](production-how-to-register-consumption-and-output.md)|  
|Exécutez en lot la quantité de composantes utilisées par opération dans un journal qui peut traiter plusieurs ordres de fabrication planifiés.|[Exécuter en lot la consommation](production-how-to-post-consumption.md)|
|Reportez la quantité de produits finis et le temps passé par opération dans un journal qui peut traiter plusieurs bons de production libérés.|[Exécuter en lot la production et les temps d'exécution](production-how-to-post-output-quantity.md)|
|Annuler la production, par exemple à cause d'un montant incorrect et d'erreurs de saisie.  |[Inverser un report de production](production-how-to-reverse-output-posting.md)|  
|Reporter le nombre d'articles produits dans chaque opération terminée qui ne sont pas considérés comme produits finis, mais comme rebuts.|[Reporter le rebut](production-how-to-post-scrap.md)|
|Affichez la charge de l'atelier en tant que résultat des bons de production planifiés et libérés.|[Afficher la charge des ateliers et des unités de production](production-how-to-view-the-load-on-work-centers.md)|      
|Utilisez la page **Journal capacité** pour reporter les capacités consommées qui ne sont pas affectées à un bon de production, comme les travaux d'entretien.|[Reporter des capacités](production-how-to-post-capacities.md)|  
|Calculer et ajuster le coût des articles finis et des composants consommés à des fins de rapprochement bancaire.|[À propos des coûts des bons de production achevés](finance-about-finished-production-order-costs.md)|  

## <a name="see-also"></a>Voir aussi  
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  


[!INCLUDE[footer-include](includes/footer-banner.md)]