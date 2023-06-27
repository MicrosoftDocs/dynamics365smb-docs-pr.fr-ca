---
title: À propos de la comptabilité analytique
description: La comptabilité analytique vous permet de cerner les coûts liés à l'exploitation d'un activié. Les informations sur la comptabilité analytique sont conçues pour analyser divers problèmes.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '1101, 1103, 1105, 1108, 1111, 1112, 1124, 1123'
ms.date: 08/23/2022
ms.author: edupont
---
# <a name="about-cost-accounting" />À propos de la comptabilité analytique

La comptabilité analytique vous permet de cerner les coûts liés à l'exploitation d'un activié. Les informations sur la comptabilité analytique sont conçues pour analyser :  

- Les types de coûts encourus dans la gestion d’une entreprise  
- Emplacement des coûts encourus
- Qui prend en charge les coûts  

En comptabilité analytique, vous affectez des coûts réels et budgétés relatifs à l'exploitation, aux départements, aux produits et aux projets pour analyser la rentabilité de votre compagnie.  

## <a name="workflow-in-cost-accounting" />Flux de travail en comptabilité analytique

La comptabilité analytique est constituée des composants principaux suivants :  

- Types de coûts, centres de coûts et coûts associés  
- Écritures de coûts et feuilles de coûts  
- Affectations des coûts  
- Budgets des coûts
- Rapports sur les coûts  

Le schéma suivant présente le flux de travail en comptabilité analytique.  

![Vue d’ensemble de la comptabilité analytique.](media/costaccountingoverview.png "CostAccountingOverview")  

## <a name="cost-types-cost-centers-and-cost-objects" />Types de coûts, centres de coûts et coûts associés

Vous définissez les types de coûts, les centres de coûts et les coûts associés pour analyser leur type, leur source et la personne qui les prend en charge.  

Tout d’abord, vous définissez un plan des types de coûts avec une structure et une fonctionnalité qui ressemblent au plan comptable général. Vous pouvez créer votre propre plan des types de coûts, ou le faire en transférant les comptes GL des états des résultats.  

Les centres de coûts sont les départements et les centres de profit responsables des coûts et des revenus. Le nombre de centres de coûts configurés dans la comptabilité analytique est souvent supérieur aux dimensions configurées dans le grand livre. En règle générale, le grand livre utilise uniquement les centres de coûts de premier niveau pour les coûts directs et les coûts initiaux. En comptabilité analytique, des centres de coûts supplémentaires sont créés pour des niveaux d'affectation supplémentaires.  

Les objets de coûts sont les biens, les groupes de biens ou les services d’une compagnie. Ce sont les « produits finis » d’une compagnie qui prennent en charge les coûts.  

Vous pouvez lier les centres de coûts aux départements et les objets de coûts aux projets au sein de la compagnie. Dans le grand livre, vous pouvez lier les centres de coûts et les objets de coûts à toutes les dimensions et les compléter avec les informations des sous-totaux et des titres.  

## <a name="cost-entries-and-cost-journals" />Écritures de coûts et feuilles de coûts

Les coûts opérationnelles peuvent être transférés vers le grand livre. Vous pouvez transférer automatiquement les écritures à partir du grand livre vers les écritures de coûts à chaque report. Vous pouvez également utiliser un traitement en lot pour transférer les écritures vers les écritures de coûts en fonction du report récapitulatif journalier ou mensuel.  

Dans les journaux de coûts, vous pouvez reporter les coûts et les activités qui ne proviennent pas du grand livre ou qui ne sont pas générés par les affectations. Par exemple, vous pouvez reporter les coûts opérationnels, les frais internes, les allocations et les écritures de correction entre les types de coûts, les centres de coûts et les objets de coûts, de manière individuelle ou récurrente.  

## <a name="cost-allocations" />Affectations des coûts

Les affectations déplacent les coûts et les revenus entre les types de coûts, les centres de coûts et les coûts associés. Les frais généraux sont d'abord reportés sur les centres de coûts, puis sur les objets de coûts. Par exemple, vous pouvez réaliser cette imputation dans un département des ventes, qui vend plusieurs biens simultanément. Les frais généraux du département, tels que les salaires, les fournitures et les frais de déplacement, sont initialement affectés au centre de coûts de vente, et sont ensuite répartis entre les différents produits (objets de coûts) vendus, ainsi que sur les matériaux achetés (coûts directs) utilisés dans ces produits.

La base d’affectation utilisée et la précision de la définition d’affectation ont une incidence sur les résultats des affectations de coûts. La définition de l'affectation permet d'affecter les coûts depuis des pré-centres de coûts vers les centres de coûts principaux, puis depuis des centres de coûts vers des objets de coûts.  

Chaque affectation comporte une source et au moins une cible. Vous pouvez affecter des valeurs réelles ou budgétées à l’aide de la méthode d’affectation statique qui repose sur une valeur définie, par exemple, les mètres carrés utilisés ou un ratio d’affectation prédéfini, comme 5:2:4. Vous pouvez également affecter des valeurs réelles ou budgétées à l'aide de la méthode d'affectation dynamique avec neuf bases d'affectation prédéfinies et 12 plages de dates dynamiques.  

## <a name="cost-budgets" />Budgets des coûts

De manière similaire à la budgétisation dans le grand livre, vous pouvez créer des budgets pour planifier les coûts au cours d’une certaine période (un exercice financier, par exemple), qui peuvent être affectés à un centre de coûts (département de la compagnie) ou à un objet de coûts associé (produit ou service). Vous pouvez créer autant de budgets de coûts que nécessaire. Vous pouvez ensuite copier le budget de coûts vers le budget de grand livre et vice versa. Et vous pouvez transférer des coûts budgétés en tant que coûts réels.

## <a name="cost-reporting" />Rapports sur les coûts

La plupart des rapports et des statistiques reposent sur les écritures de coûts reportées. Vous pouvez définir le tri des résultats et utiliser des filtres pour définir les informations à afficher. Vous pouvez créer des états pour analyser la distribution des coûts. En outre, vous pouvez utiliser les rapports financiers standard pour définir le mode d’affichage du plan des types de coûts.  

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/paths/use-cost-accounting-dynamics-365-business-central/) associée

## <a name="see-also" />Voir aussi .

[Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
[Finance](finance.md)  
[Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
