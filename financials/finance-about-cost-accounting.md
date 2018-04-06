---
title: "À propos de la comptabilité analytique | Microsoft Docs"
description: "La comptabilité analytique vous permet de cerner les coûts liés à l'exploitation d'un activié."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/16/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: b38e86fa63e179c1bd4ac78c29d7728716755e0c
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="about-cost-accounting"></a>À propos de la comptabilité analytique
La comptabilité analytique vous permet de cerner les coûts liés à l'exploitation d'un activié. Les informations sur la comptabilité analytique sont conçues pour analyser :  

-   Quels sont les types de coûts encourus lors de l'exploitation d'une société ?  
-   Quel est l'emplacement des coûts encourus ?  
-   Qui prend en charge les coûts ?  

En comptabilité analytique, vous affectez des coûts réels et budgétés relatifs à l'exploitation, aux départements, aux produits et aux projets pour analyser la rentabilité de votre compagnie.  

## <a name="workflow-in-cost-accounting"></a>Flux de travail en comptabilité analytique  
La comptabilité analytique est constituée des composants principaux suivants :  

-   Types de coûts, centres de coûts et coûts associés  
-   Écritures de coûts et feuilles de coûts  
-   Affectations des coûts  
-   Budgets des coûts
-   Rapports sur les coûts  

Le schéma suivant présente le flux de travail en comptabilité analytique.  

![Aperçu de comptabilité analytique](media/costaccountingoverview.png "CostAccountingOverview")  

## <a name="cost-types-cost-centers-and-cost-objects"></a>Types de coûts, centres de coûts et coûts associés  
Vous définissez les types de coûts, les centres de coûts et les coûts associés pour analyser leur type, leur source et la personne qui les prend en charge.  

Vous définissez un plan des types de coûts avec une structure et une fonctionnalité qui ressemblent au plan comptable général. Vous pouvez transférer les comptes état des résultats GL ou créer votre propre plan des types de coûts.  

Les centres de coûts sont les départements et les centres de profit responsables des coûts et des revenus. Le nombre de centres de coûts configurés dans la comptabilité analytique est souvent supérieur aux dimensions configurées dans le grand livre. En règle générale, le grand livre utilise uniquement les centres de coûts de premier niveau pour les coûts directs et les coûts initiaux. En comptabilité analytique, des centres de coûts supplémentaires sont créés pour des niveaux d'affectation supplémentaires.  

Les objets de coûts sont les biens, les groupes de biens ou les services d'une compagnie. Ce sont les produits finis d'une compagnie qui prennent en charge les coûts.  

Vous pouvez lier les centres de coûts aux départements et les objets de coûts aux projets au sein de la compagnie. Cependant, vous pouvez lier les centres de coûts et les objets de coûts à toutes les dimensions du grand livre et les compléter avec des sous-totaux et des titres.  

## <a name="cost-entries-and-cost-journals"></a>Écritures de coûts et feuilles de coûts  
Les coûts opérationnelles peuvent être transférés vers le grand livre. Vous pouvez transférer automatiquement les écritures à partir du grand livre vers les écritures de coûts à chaque report. Vous pouvez également utiliser un traitement en lot pour transférer les écritures vers les écritures de coûts en fonction du report récapitulatif journalier ou mensuel.  

Dans les journaux de coûts, vous pouvez reporter les coûts et les activités qui ne proviennent pas du grand livre ou qui ne sont pas générés par les affectations. Par exemple, vous pouvez reporter les coûts opérationnels, les frais internes, les allocations et les écritures de correction entre les types de coûts, les centres de coûts et les objets de coûts, de manière individuelle ou récurrente.  

## <a name="cost-allocations"></a>Affectations des coûts  
Les affectations déplacent les coûts et les revenus entre les types de coûts, les centres de coûts et les coûts associés. Les frais généraux sont d'abord reportés sur les centres de coûts, puis sur les objets de coûts. Par exemple, vous pouvez réaliser cette imputation dans un département des ventes, qui vend plusieurs biens simultanément. Les coûts directs peuvent être affectés directement à un objet de coûts, par exemple l'achat d'équipement pour un produit spécifique.  

La base d'affectation utilisée et la précision de la définition d'affectation ont une incidence sur les résultats des affectations de coûts. La définition de l'affectation permet d'affecter les coûts depuis des pré-centres de coûts vers les centres de coûts principaux, puis depuis des centres de coûts vers des objets de coûts.  

Chaque affectation comporte une source et au moins une cible. Vous pouvez affecter des valeurs réelles ou budgétées à l'aide de la méthode d'affectation statique qui repose sur une valeur définie, par exemple, la superficie ou un ratio d'affectation prédéfini, comme 5:2:4. Vous pouvez également affecter des valeurs réelles ou budgétées à l'aide de la méthode d'affectation dynamique avec neuf bases d'affectation prédéfinies et 12 plages de dates dynamiques.  

## <a name="cost-budgets"></a>Budgets des coûts  
Vous pouvez créer autant de budgets de coûts que vous le souhaitez. Vous pouvez copier le budget de coûts vers le budget de grand livre et vice versa. Vous pouvez transférer des coûts budgétés en tant que coûts réels.  

## <a name="cost-reporting"></a>Rapports sur les coûts  
La plupart des rapports et des statistiques reposent sur les écritures de coûts reportées. Vous pouvez définir le tri des résultats et utiliser des filtres pour définir les informations à afficher. Vous pouvez créer des états pour analyser la distribution des coûts. En outre, vous pouvez utiliser les tableaux d'analyse standard pour définir le mode d'affichage du plan des types de coûts.  

## <a name="see-also"></a>Voir aussi  
 [Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
 [Finance](finance.md)   
 [Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

