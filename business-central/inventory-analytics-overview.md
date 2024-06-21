---
title: Analyse de l’inventaire
description: "Business\_Central contient de nombreuses fonctionnalités pour vous aider à collecter, analyser et partager des données précieuses sur votre inventaire à des fins de veille économique et de prise de décision dans votre organisation."
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '516, 9300, 5119, 9301, 9305'
ms.date: 05/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="inventory-analytics"></a>Analyse de l’inventaire

Les entreprises capturent un grand nombre de données au cours de leurs activités quotidiennes, ce qui permet aux gestionnaires d’inventaire de disposer d’informations décisionnelles (Business Intelligence) :

- Expédition des marchandises lorsque les documents de vente sont exécutés.
- Réceptions des articles lorsque les bons de commande sont exécutés.
- Mouvements d’articles entre emplacements.

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des fonctionnalités pour vous aider à collecter, analyser et partager les données d’inventaire de votre organisation :

- Analyse ad hoc sur les listes
- Analyse ad hoc des données dans Excel (en utilisant Ouvrir dans Excel)
- Outils d’analyse intégrés de l’inventaire
- Rapports d’inventaire intégrés

Chacune de ces fonctionnalités présente ses avantages et inconvénients, selon le type d’analyse des données et le rôle de l’utilisateur. Pour en savoir plus, consultez [Analyse, Business Intelligence et rapport](reports-bi-reporting.md).

Cet article vous explique comment d’utiliser ces fonctionnalités analytiques pour obtenir des informations concernant votre inventaire.

## <a name="analytics-needs-in-inventory"></a>Besoins d’analyse en matière d’inventaire

Lorsque l’on réfléchit aux besoins d’analyse en gestion de l’inventaire, il peut être utile d’utiliser un modèle basé sur un persona qui décrit différents besoins en matière d’analyse à un niveau élevé.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration de différents personnages pour l’analyse" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

Les personnes occupant différents rôles ont des besoins différents en matière de données et utilisent les données de différentes manières. Par exemple, les professionnels de la gestion de patrimoine et de la finance interagissent avec les données différemment des professionnels de la vente.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration de la manière dont différentes personnes ont des besoins analytiques différents." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Rôle              | Agrégation de données  | Façons typiques de consommer des données                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CFO / CFO / CEO    | Données performances  | KPI, tableaux de bord, rapports financiers           |
|Gestionnaire d’inventaire  | Tendances, résumés | Rapports de gestion intégrés, analyse ad hoc      | 
|Magasinier   | Informations détaillées     | Rapports opérationnels intégrés, données de tâches à l’écran |

<!-- 
## <a name="inventory-kpis"></a>Inventory KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In inventory management, people often use the following KPIs to monitor their organization's sales performance:

- TODO  
-->

## <a name="use-financial-reporting-to-produce-financial-statements-and-kpis-related-to-inventory"></a>Utiliser les rapports financiers pour produire des états financiers et des indicateurs de performance clés associés à l’inventaire

La fonctionnalité **Financial Reporting** vous donne un aperçu des données financières affichées dans votre plan comptable (COA). Vous pouvez configurer les rapports financiers pour analyser les chiffres dans les comptes du grand livre (GL) et comparer les écritures GL et les écritures budget. Spécifiquement pour la gestion de l’inventaire, vous pouvez configurer des rapports financiers sur les comptes du grand livre (GL) que vous utilisez pour suivre les reports d’inventaire.

Les dimensions jouent un rôle important dans la veille économique. Une dimension correspond à des données que vous ajoutez à une écriture en tant que paramètre. Les dimensions vous permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les régions, les produits et les représentants. Entre autres objectifs, utilisez des dimensions lors de la définition de vues d’analyse et de la création de rapports financiers. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

Pour en savoir plus sur les rapports financiers, voir [Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md).

## <a name="finance-reporting-across-business-units-or-legal-entities-related-to-inventory"></a>Rapports financiers entre les unités fonctionnelles ou les entités juridiques (associés à l’inventaire)

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui rendent compte aux organisations mères. [!INCLUDE [prod_short](includes/prod_short.md)] fournit aux comptables des outils qui les aident à transférer les écritures de deux ou plusieurs compagnies (filiales) dans une compagnie consolidée. Spécifiquement pour la gestion de l’inventaire, vous souhaiterez peut-être consolider les écritures GL pour vos comptes inventaire pour pouvoir suivre les indicateurs de performances clés de vente dans les unités fonctionnelles ou les entités juridiques.

Pour en savoir plus, reportez-vous à [Consolidation de la compagnie](finance-consolidated-company-reporting.md).

## <a name="ad-hoc-analysis-of-inventory-data"></a>Analyse ad hoc des données d’inventaire

Parfois, il suffit de vérifier si les chiffres s’additionnent correctement ou de confirmer rapidement un chiffre. Les fonctionnalités suivantes sont idéales pour les analyses ad hoc :

- Analyses des données sur les pages de listes comptables
- Ouvrir dans Excel

La fonction d’analyse des données vous permet d’ouvrir presque toutes les pages de liste, telles que les **Écritures article**, d’entrer en mode analyse, puis de regrouper, filtrer et faire pivoter les données comme bon vous semble.

:::image type="content" source="media/data-analysis-inventory-dead-stock.png" alt-text="Exemple de procédure pour effectuer une analyse des données de stock ancien sur la page Écritures article" lightbox="media/data-analysis-inventory-dead-stock.png":::

De la même manière, vous pouvez utiliser le **Ouvrir dans Excel** action pour ouvrir une page de liste, éventuellement filtrer la liste sur un sous-ensemble de données, puis utiliser Excel pour travailler avec les données. Par exemple, en utilisant des fonctionnalités telles que l’analyse des données, l’analyse de simulation ou la feuille de prévision.

<!-- :::image type="content" source="media/open-in-excel-item-ledger-entries.png" alt-text="Example of how to do data analysis on the Item Ledger Entries data using Excel." lightbox="media/open-in-excel-item-ledger-entries.png"::: -->

> [!TIP]
> Si vous configuré OneDrive pour les fonctionnalités système, le classeur Excel s’ouvre dans votre navigateur.

Pour en savoir plus sur la manière d’effectuer une analyse ad hoc des données d’inventaire, accédez à [Analyse ad hoc des données d’inventaire](ad-hoc-analysis-inventory.md).

## <a name="built-in-reports-for-inventory"></a>Rapports intégrés pour l’inventaire

[!INCLUDE [prod_short](includes/prod_short.md)] comprend plusieurs rapports intégrés, fonctions de traçage et outils pour aider les organisations chargées d’inventaires à déclarer leurs données.

Pour obtenir un aperçu des rapports disponibles, choisir sur **Tous les rapports** de votre page d’accueil. Cette Action ouvre l’explorateur de rapport, qui est filtré selon les fonctionnalités du **Rapport et analyse** option. Sous l’en-tête **Ventes et marketing** , choisissez **Explorer**. Pour en savoir plus, voir [Recherche de rapports avec l’explorateur de rôles](ui-role-explorer.md).

:::image type="content" source="media/report-explorer-sales.png" alt-text="Exemple de rapports sur le centre de rôle ventes." lightbox="media/report-explorer-sales.png":::

<!-- The built-in reports come in two flavors:

- Designed for print (pdf).
- Designed for analysis in Excel. -->

Pour en savoir plus sur les rapports pertinents pour l’inventaire, accédez à [Rapports d’inventaire et d’entrepôt intégrés](inventory-WMS-reports.md).

## <a name="on-screen-inventory-analytics"></a>Analyse de l’inventaire à l’écran

[!INCLUDE [prod_short](includes/prod_short.md)] comporte plusieurs pages qui vous donnent des aperçus de l’inventaire et des tâches à accomplir. Voici des exemple pour commencer :

- [Afficher la disponibilité des articles](inventory-how-availability-overview.md)
- [Suivi des articles avec les numéros de lot, de série et de paquet](inventory-how-work-item-tracking.md)
- [Traçabilité : articles suivis](inventory-how-to-trace-item-tracked-items.md)
- [Vérifier le rapprochement entre le livre inventaire et le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md#to-audit-the-reconciliation-between-the-inventory-ledger-and-the-general-ledger)
- [Afficher les articles transbordés dans une feuille prélèvement ou livraison](warehouse-how-to-cross-dock-items.md#to-view-cross-docked-items-in-a-shipment-or-pick-worksheet)

Le module de vente comprend également des pages d’analyse liées à l’inventaire :

- [Calcul des dates promesse commande](sales-how-to-calculate-order-promising-dates.md)
- [Calculer les dates de livraison des documents de vente](sales-date-calculation-for-sales.md)
- [Suivi des paquets](sales-how-track-packages.md)

### <a name="show-inventory-related-general-ledger-entries-and-balances-from-the-chart-of-accounts-page"></a>Afficher les écritures et les soldes du grand livre liés à l’inventaire à partir de la page Plan comptable

La page **Plan comptable** affiche tous les comptes du grand livre avec des chiffres agrégés reportés dans le grand livre. À partir de cette page, vous pouvez faire des choses comme :  

- Afficher les rapports qui affichent les écritures et les soldes.  
- Vérifiez une liste de groupes de report pour ce compte.
- Afficher les soldes débit et crédit d’un seul compte.

Spécifiquement pour la gestion de l’inventaire, vous pouvez créer une vue sur la page Plan comptable qui affiche uniquement les comptes que vous utilisez pour reporter les écritures inventaire.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Exemple de la façon dont la page Plan comptable affiche des informations financières" lightbox="media/chart-of-accounts-page.png":::

Pour en savoir plus, allez à [Familiarisation avec le plan comptable](finance-general-ledger.md#the-chart-of-accounts).

### <a name="analyze-inventory-data-by-dimensions"></a>Analyser des données d’inventaire par dimensions

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur les documents, tels que les documents de vente. Les dimensions peuvent, par exemple, indiquer de quel projet ou département provient une écriture.  

Au lieu de configurer des comptes GL distincts pour chaque service ou site, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer une structure de plan comptable compliquée.

Pour plus d’informations, voir [Analyser des données par dimensions](bi-how-analyze-data-dimension.md).

## <a name="see-also"></a>Voir aussi .

[Consolidation de la compagnie](finance-consolidated-company-reporting.md)   
[Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md)  
[Gestion des rapports financiers entre les unités fonctionnelles ou les entités juridiques](finance-consolidated-company-reporting.md)  
[Analyse ad hoc des données d’inventaire](ad-hoc-analysis-inventory.md)  
[Rapports d’inventaire et d’entrepôt intégrés](inventory-WMS-reports.md)  
[Comprendre du plan comptable](finance-general-ledger.md#the-chart-of-accounts)  
[Analyser des données par dimensions](bi-how-analyze-data-dimension.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)   
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
