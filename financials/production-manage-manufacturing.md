---
title: "Exécuter la production | Microsoft Docs"
description: "Lorsque la demande est planifiée et les matières ont été produites conformément aux nomenclatures de production, les opérations de production réelles peuvent commencer et être exécutées selon la séquence définie par l'itinéraire du bon de production."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/26/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 8b2e20e694279a8c06188e0e429ef3b4fb43aea2
ms.openlocfilehash: e27ceb91b25669a31d95256385cb7e5acd9160bd
ms.contentlocale: fr-ca
ms.lasthandoff: 09/27/2017

---
# <a name="manufacturing"></a>Production
Lorsque la demande est planifiée et les matières ont été produites conformément aux nomenclatures de production, les opérations de production réelles peuvent commencer et être exécutées selon la séquence définie par l'itinéraire du bon de production.  

Du point de vue du système, une grande partie de l'exécution de la production consiste à reporter cette dernière dans la base de données pour enregistrer l'avancement et mettre à jour l'inventaire avec les articles terminés. Le report de la production peut être effectuée manuellement en renseignant et en reportant les lignes journal après les opérations de production. La validation peut également être automatisée en utilisant la consommation en amont. Dans ce cas, la consommation de matières est automatiquement reportée en même temps que la production lors du changement de l'état du bon de production en Terminé.  

Outre le journal lot pour le report de sortie de plusieurs bons de production, vous pouvez utiliser la fenêtre **Journal production** pour reporter la consommation et/ou la sortie d'une ligne bon de production.

Avant de pouvoir commencer à produire des articles, vous devez procéder à diverses configurations, telles que les ateliers, les itinéraires et les nomenclatures de production. Pour plus d'informations, voir [Paramétrage de la production](production-configure-production-processes.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Comprendre le fonctionnement des ordres de fabrication.|[À propos des ordres de fabrication](production-about-production-orders.md)|
|Créer manuellement des ordres de fabrication.|[Procédure : créer des ordres de fabrication](production-how-to-create-production-orders.md)|
|Confier à un sous-traitant toutes les opérations ou les opérations sélectionnées dans un ordre de fabrication.|[Procédure : sous-traiter la production](production-how-to-subcontract-manufacturing.md)|
|Enregistrez et reportez la sortie de production, ainsi que la consommation matière et temps, pour une seule ligne bon de production libéré.|[Procédure : reporter la consommation et la sortie pour une ligne bon de production libéré](production-how-to-register-consumption-and-output.md)|  
|Exécutez en lot la quantité de composantes utilisées par opération dans un journal qui peut traiter plusieurs ordres de fabrication planifiés.|[Procédure : exécuter en lot la consommation](production-how-to-post-consumption.md)|
|Reportez la quantité de produits finis et le temps passé par opération dans un journal qui peut traiter plusieurs bons de production libérés.|[Procédure : exécuter en lot la sortie et les temps d'exécution](production-how-to-post-output-quantity.md)|  
|Reporter le nombre d'articles produits dans chaque opération terminée qui ne sont pas considérés comme produits finis, mais comme rebuts.|[Procédure : reporter le rebut](production-how-to-post-scrap.md)|
|Affichez la charge de l'atelier en tant que résultat des bons de production planifiés et libérés.|[Procédure : afficher la charge des ateliers et des unités de production](production-how-to-view-the-load-on-work-centers.md)|      
|Utiliser la fenêtre **Feuille capacité** pour valider les capacités consommées qui ne sont pas affectées à un ordre de fabrication, telles que les travaux de maintenance.|[Comment valider les capacités](production-how-to-post-capacities.md)|  
|Calculer et ajuster le coût des articles finis et des composants consommés à des fins de rapprochement bancaire.|[À propos des coûts des bons de production achevés](finance-about-finished-production-order-costs.md)|  

## <a name="see-also"></a>Voir aussi  
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)      
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

