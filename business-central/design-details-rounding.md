---
title: Détails de conception - Arrondissement | Microsoft Docs
description: Des arrondissements résiduels peuvent se produire lorsque vous évaluez le coût d'une diminution d'inventaire qui est mesurée dans une quantité différente de l'augmentation d'inventaire correspondante. Les reliquats d'arrondissement sont calculés pour tous les modes d'évaluation du coût lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: d8fac07df8d83b46a6ab8ed4d20a50a81c0731d5
ms.sourcegitcommit: 0953171d39e1232a7c126142d68cac858234a20e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/09/2021
ms.locfileid: "6214863"
---
# <a name="design-details-rounding"></a>Détails de conception : arrondissement
Des arrondissements résiduels peuvent se produire lorsque vous évaluez le coût d'une diminution d'inventaire qui est mesurée dans une quantité différente de l'augmentation d'inventaire correspondante. Les reliquats d'arrondissement sont calculés pour tous les modes d'évaluation du coût lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**.  

 Lorsque vous utilisez le mode d'évaluation des coûts moyen, le montant résiduel arrondi est calculé et enregistré sur une base cumulative écriture par écriture.  

 Lorsque vous utilisez un mode d'évaluation des coûts autre que Moyenne, le montant résiduel est calculé lorsque l'augmentation d'inventaire a été totalement affectée, c'est-à-dire lorsque la quantité restante pour l'augmentation d'inventaire est égale à zéro. Une écriture distincte est ensuite créée pour l'arrondissement résiduel, et la date de report de l'écriture arrondissement correspond à la date de report de la dernière écriture valeur facturée de l'augmentation d'inventaire.  

## <a name="example"></a>Exemple :  
 L'exemple suivant présente la manière dont les différents reliquats d'arrondissement sont traités pour le mode évaluation des coûts moyen et pour le mode évaluation des coûts non moyen, respectivement. Dans les deux cas, le traitement en lot **Ajuster coûts - Écr. article** a été exécuté.  

 La table suivante montre les écritures du grand livre d'articles sur lesquelles l'exemple est basé.  

|Date de report|Quantité|N° séquence |  
|------------------|--------------|---------------|  
|01/01/20|3|1|  
|01/02/20|-1|2|  
|01/03/20|-1|3|  
|01/04/20|-1|4|  

 Pour un article utilisant le mode évaluation des coûts moyen, l'arrondissement résiduel (1/300) est calculé avec la première diminution (numéro de séquence 2) et est reporté sur le numéro de séquence 3. Par conséquent, le numéro de séquence 3 est évalué à –3,34.  

 Le tableau suivant montre les écritures valeur résultantes.  

|Date de report|Quantité|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|01/01/20|3|10|1|1|  
|01/02/20|-1|-3,33|2|2|  
|01/03/20|-1|-3,34|3|3|  
|01/04/20|-1|-3,33|4|4|  

 Pour un article utilisant une méthode d'évaluation coût autre que Moyenne, l'arrondissement résiduel (0,01) est calculé lorsque la quantité restante pour l'augmentation d'inventaire est égale à zéro. Le montant résiduel arrondi a une écriture distincte (numéro 5).  

 Le tableau suivant montre les écritures valeur résultantes.  

|Date de report|Quantité|Coût indiqué (réel)|N° écriture article gr. livre|N° séquence |  
|------------------|--------------|----------------------------|---------------------------|---------------|  
|01/01/20|3|10|1|1|  
|01/02/20|-1|-3,33|2|2|  
|01/03/20|-1|-3,33|3|3|  
|01/04/20|-1|-3,33|4|4|  
|01/01/20|0|-0,01|1|5|  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)   
 [Détails de conception : Modes évaluation stock](design-details-costing-methods.md) [Gestion des composants des coûts](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]