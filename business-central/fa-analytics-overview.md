---
title: Analyse Immobilisations
description: 'Découvrez comment collecter, analyser et partager des données sur les immobilisations à des fins de Business Intelligence.'
author: brentholtorf
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '5601, 5600, 5615, 5616, 5617'
ms.date: 05/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="fixed-assets-analytics"></a>Analyse Immobilisations

Les entreprises possédant des immobilisations capturent de nombreuses données les concernant au cours de leurs activités quotidiennes. Ces données soutiennent une précieuse business intelligence (BI) pour les gestionnaires d’immobilisations :

- Acquisitions actifs
- Dépréciations d’actifs
- Assurance et entretien
- Budget actif

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des fonctionnalités pour vous aider à collecter, analyser et partager les données sur les immobilisations votre organisation :

- Rapports financiers (pour des états financiers et des indicateurs de performance clés sur les comptes immobilisations)
- Analyse ad hoc sur les listes
- Analyse ad hoc des données dans Excel (en utilisant open dans Excel)
- Outils d'analyse sur les immobilisations intégrés
- Rapports immobilisations intégrés

> [!NOTE]
> L’analyse des immobilisations est un peu différente des autres domaines. Vous devez analyser les données déjà présentes, telles que les acquisitions d’actifs, les dépréciations et les assurances, mais également les données futures (projetées), telles que les dépréciations et les mises hors service d’actifs. Pour ce dernier type d’analyse, [!INCLUDE[prod_short](includes/prod_short.md)] dispose de rapports intégrés permettant de calculer ces chiffres.

Chaque fonctionnalités présente ses avantages et inconvénients, selon le type d’analyse des données et le rôle de l’utilisateur. Pour en savoir plus, consultez [Analyse, Business Intelligence et rapport](reports-bi-reporting.md).

Cet article décrit les façons d’utiliser ces fonctionnalités analytiques pour obtenir des informations sur vos immobilisations.

## <a name="analytics-needs-in-asset-management"></a>Besoins analytiques dans la gestion des actifs

Quand on réfléchit aux besoins d’analyse en gestion des actifs, il peut être utile d’utiliser un modèle basé sur une personne décrites à un niveau élevé des besoins en matière d’analyse.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration de différents personnages pour l’analyse" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

En matière de données, Les personnes occupant différents rôles ont des besoins différents et utilisent les données de différentes manières. Par exemple, les professionnels de la gestion de patrimoine et de la finance interagissent avec les données différemment des professionnels de la vente.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration de la manière dont différentes personnes ont des besoins analytiques différents." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Rôle              | Agrégation de données  | Façons typiques de consommer des données                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CFO / COO / CEO                 | Données performances  | Indicateurs de performance clés <br> Tableaux de bord <br> Rapports financiers           |
|Gestion des immobilisations / Contrôleur   | Tendances, résumés | Rapports managériaux prédéfinis <br> Analyse ad hoc      | 
|Aide-comptable                      | Informations détaillées     | Rapports exploitation prédéfinis <br> Données de tâche à l’écran |

## <a name="asset-management-kpis"></a>KPI Gestion des immobilisations

Un indicateur de performance clé (KPI) est une valeur mesurable qui montre l’efficacité avec laquelle vous atteignez vos objectifs. En gestion d'actifs, les gens utilisent souvent les KPI suivants pour surveiller l'utilisation des actifs de leur organisation :

- Chiffre d’affaires total des actifs
- Le rendement des actifs

## <a name="use-financial-reporting-to-produce-financial-statements-and-kpis-related-to-fixed-assets"></a>Utiliser les rapports financiers pour produire des états financiers et des indicateurs de performance clés associés aux immobilisations

La fonctionnalité **Financial Reporting** vous donne un aperçu des données financières affichées dans votre plan comptable (COA). Vous pouvez configurer les rapports financiers pour analyser les chiffres dans les comptes du grand livre (GL) et comparer les écritures GL et les écritures budget. Spécifiquement pour la gestion des immobilisations, vous pouvez configurer des rapports financiers sur les comptes du grand livre (GL) que vous utilisez pour suivre les reports d'immobilisations.

Les dimensions jouent un rôle important dans la veille économique. Une dimension correspond à des données que vous pouvez ajouter à une écriture en tant que paramètre. Les dimensions vous permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les produits et les représentants, et de récupérer facilement ces groupes à des fins d’analyse. Entre autres objectifs, vous utilisez des dimensions lors de la définition de vues d’analyse et de la création de rapports financiers. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

Pour en savoir plus sur les rapports financiers, voir [Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md).

## <a name="finance-reporting-across-business-units-or-legal-entities-related-to-fixed-assets"></a>Rapports financiers entre les unités fonctionnelles ou les entités juridiques (associés aux immobilisations)

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui rendent compte aux organisations mères. [!INCLUDE [prod_short](includes/prod_short.md)] fournit aux comptables des outils qui les aident à transférer les écritures de deux ou plusieurs compagnies (filiales) dans une compagnie consolidée. Spécifiquement pour la gestion des immobilisations, vous souhaiterez peut-être consolider les écritures GL pour vos comptes immobilisations pour suivre les indicateurs de performances clés des immobilisations dans les unités fonctionnelles ou les entités juridiques.

Pour en savoir plus, reportez-vous à [Consolidation de la compagnie](finance-consolidated-company-reporting.md).

## <a name="ad-hoc-analysis-of-fixed-assets-data"></a>Analyse ad hoc des données Immobilisations

Parfois, il suffit de vérifier si les chiffres s’additionnent correctement ou de confirmer rapidement un chiffre. Les fonctionnalités suivantes sont idéales pour les analyses ad hoc :

- Analyses des données sur les pages de listes comptables
- Ouvrir dans Excel

La fonction d’analyse des données vous permet d’ouvrir presque toutes les pages de liste, telles que les **Écritures GL** ou les **Écritures immobilisation**, d’entrer en mode analyse, puis de regrouper, filtrer et faire pivoter les données comme bon vous semble.

:::image type="content" source="media/data-analysis-fa-ledger-entries-asset-overview-current-value.png" alt-text="Exemple de procédure pour effectuer une analyse des données sur la page Écritures immobilisation pour voir la valeur d’un actif." lightbox="media/data-analysis-fa-ledger-entries-asset-overview-current-value.png":::

De la même manière, vous pouvez utiliser l’action **Ouvrir dans Excel** pour ouvrir une page de liste pour les écritures, éventuellement filtrer la liste sur un sous-ensemble de données, puis utiliser Excel pour travailler avec les données. Par exemple, en utilisant des fonctionnalités telles que l’analyse des données, l’analyse de simulation ou la feuille de prévision.

<!-- :::image type="content" source="media/open-in-excel-gl-entries.png" alt-text="Example of how to do data analysis on the G/L entries data using Excel." lightbox="media/open-in-excel-gl-entries.png"::: -->

> [!TIP]
> Si vous configuré OneDrive pour les fonctionnalités système, le classeur Excel s’ouvre dans votre navigateur à l’aide d’Excel pour le Web. 

Pour plus d’informations sur la manière d’effectuer une analyse ad hoc sur la comptables immobilisation, voir [Analyse ad hoc sur les données Immobilisations](ad-hoc-analysis-fa.md).


## <a name="built-in-reports-for-fixed-assets"></a>Rapports intégrés pour les immobilisations

[!INCLUDE [prod_short](includes/prod_short.md)] comprend plusieurs rapports, fonctions de traçage et outils incorporés qui aident les auditeurs ou contrôleurs chargés de rendre compte sur les Immobilisations.

Pour obtenir un aperçu des rapports disponibles, choisir sur **Tous les rapports** en haut de votre page d’accueil. Cette Action ouvre la page l’explorateur de rôles, qui est filtré selon les fonctionnalités du **Rapport et analyse** option. Pour rechercher des rapports relatifs aux immobilisations, dans le champ **Rechercher** , saisissez **immobilisations**. Pour en savoir plus, voir [Recherche de rapports avec l’explorateur de rôles](ui-role-explorer.md).

:::image type="content" source="media/report-explorer-fixed-assets.png" alt-text="Exemple de rapports sur le centre de rôle finance." lightbox="media/report-explorer-fixed-assets.png":::

<!-- Built-in reports come in two flavors:

- Designed for print (pdf).
- Designed for analysis in Excel. -->

Pour plus d’informations sur les rapports pertinents pour les immobilisations, consultez [Rapports intégrés sur les immobilisations](fa-reports.md).

## <a name="on-screen-fixed-assets-analytics"></a>Analyses des immobilisations à l'écran

[!INCLUDE [prod_short](includes/prod_short.md)] comporte plusieurs pages qui vous donnent des aperçus des Immobilisations et des tâches à accomplir. Voici des exemple pour commencer :

- [Calculer l’amortissement, reporter l’amortissement et analyser l’amortissement](fa-how-depreciate-amortize.md)
- [Surveiller les coûts d’entretien](fa-how-maintain.md#monitor-maintenance-costs)
- [Surveillance des couvertures d’assurance](fa-how-insure.md#to-monitor-insurance-coverage)
- [Afficher les valeurs de registre d’amortissement modifiées](fa-how-trans-split-combine.md#to-view-changed-depreciation-book-values-due-to-fixed-asset-reclassification)
- [Afficher des écritures cession](fa-how-dispose-retire.md#to-view-disposal-ledger-entries)
- [Affichage des valeurs de cession prévues](fa-how-manage-budgets.md#to-view-projected-disposal-values)

### <a name="show-fixed-asset-general-ledger-entries-and-balances-from-the-chart-of-accounts-page"></a>Afficher les écritures et les soldes du grand livre immobilisations à partir de la page Plan comptable

La page Plan comptable affiche tous les comptes GL avec des chiffres agrégés dans le grand livre. À partir de cette page, vous pouvez faire des choses comme :  

- Afficher les rapports qui affichent les écritures et les soldes.  
- Vérifiez une liste de groupes de report pour ce compte.
- Afficher les soldes débit et crédit d’un seul compte.

Spécifiquement pour les Immobilisations, vous pouvez créer une vue sur la page Plan comptable qui affiche uniquement les comptes d’actifs, ou peut-être uniquement les comptes d’actifs que vous utilisez pour reporter les écritures immobilisations.

:::image type="content" source="media/chart-of-accounts-page-fa.png" alt-text="Exemple de la façon dont la page Plan comptable affiche des informations financières" lightbox="media/chart-of-accounts-page-fa.png":::

Pour en savoir plus, allez à [Familiarisation avec le plan comptable](finance-general-ledger.md#the-chart-of-accounts).

### <a name="analyze-data-by-dimensions-related-to-fixed-assets"></a>Analyser des données par dimensions (associées aux immobilisations)

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur des documents, tels que des journaux immobilisation. Les dimensions peuvent, par exemple, indiquer le service ou l'emplacement dont est issue une écriture.  

Au lieu de configurer des comptes GL distincts pour chaque service ou site, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer une structure de plan comptable compliquée.

Pour plus d’informations, voir [Analyser des données par dimensions](bi-how-analyze-data-dimension.md)

## <a name="see-also"></a>Voir aussi .

[Gestion des rapports financiers entre les unités fonctionnelles ou les entités juridiques](finance-consolidated-company-reporting.md)  
[Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md)  
[Comprendre du plan comptable](finance-general-ledger.md#the-chart-of-accounts)  
[Analyse ad hoc des données Immobilisations](ad-hoc-analysis-fa.md)   
[Rapports immobilisations intégrés](fa-reports.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
