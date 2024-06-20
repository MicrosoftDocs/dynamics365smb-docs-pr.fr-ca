---
title: Analyse des ventes
description: "Business\_Central contient de nombreuses fonctionnalités pour vous aider à collecter, analyser et partager des données de vente précieuses à des fins de Business Intelligence et de prise de décision dans l'organisation de vente."
author: kennienp
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '516, 9300, 5119, 9301, 9305'
ms.date: 04/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="sales-analytics"></a>Analyse des ventes

Les entreprises capturent des lots de données au cours de leurs activités quotidiennes, ce qui soutient une précieuse BI pour les gestionnaires de ventes :

- Opportunités
- Devis
- Documents de vente
- Factures vente

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des fonctionnalités pour vous aider à collecter, analyser et partager les données de vente de votre organisation :

- Analyse ad hoc sur les listes
- Analyse ad hoc des données dans Excel (en utilisant Ouvrir dans Excel)
- Outils d’analyse des ventes intégrés
- Rapports de vente intégrés

Chacune de ces fonctionnalités présente ses avantages et inconvénients, selon le type d’analyse des données et le rôle de l’utilisateur. Pour en savoir plus, consultez [Analyse, Business Intelligence et rapport](reports-bi-reporting.md).

Cet article vous présente comment utiliser ces fonctionnalités analytiques pour gagner des Informations sur les ventes.

## <a name="analytics-needs-in-sales"></a>Besoins analytiques en ventes

Lorsque l’on réfléchit aux besoins d’analyse en gestion des ventes, il peut être utile d’utiliser un modèle basé sur une personne décrites à un niveau élevé des différents besoins en matière d’analyse.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg" alt-text="Illustration de différents personnages pour l’analyse" lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas.svg":::

Les personnes occupant différents rôles ont des besoins différents en matière de données et utilisent les données de différentes manières. Par exemple, les professionnels de la gestion de patrimoine et de la finance interagissent avec les données différemment des professionnels de la vente.

:::image type="content" source="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg" alt-text="Illustration de la manière dont différentes personnes ont des besoins analytiques différents." lightbox="/dynamics365/business-central/dev-itpro/developer/media/analytics-personas-scenarios.svg":::

| Rôle              | Agrégation de données  | Façons typiques de consommer des données                          | 
|-------------------|-------------------| ----------------------------------------------------- |
|CCO / CFO / CEO    | Données performances  | Indicateurs de performance clés <br> Tableaux de bord <br> Rapports financiers           |
|Directeur des ventes      | Tendances, résumés | Rapports managériaux prédéfinis <br> Analyse ad hoc      | 
|Gestionnaire de comptes/vendeur | Informations détaillées     | Rapports exploitation prédéfinis <br> Données de tâche à l’écran |

<!-- 
## <a name="sales-kpis"></a>Sales KPIs

A key performance indicator (KPI) is a measurable value that shows how effectively you’re meeting your goals. In sales management, people often use the following KPIs to monitor their organization's sales performance:

- TODO  
-->

## <a name="use-financial-reporting-to-produce-financial-statements-and-kpis-related-to-sales"></a>Utiliser les rapports financiers pour produire des états financiers et des indicateurs de performance clés associés aux ventes

La fonctionnalité **Financial Reporting** vous donne un aperçu des données financières affichées dans votre plan comptable (COA). Vous pouvez configurer les rapports financiers pour analyser les chiffres dans les comptes du grand livre (GL) et comparer les écritures GL et les écritures budget. Spécifiquement pour la gestion des ventes, vous pouvez configurer des rapports financiers sur les comptes du grand livre (GL) que vous utilisez pour suivre les reports de vente.

Les dimensions jouent un rôle important dans la veille économique. Une dimension correspond à des données que vous ajoutez à une écriture en tant que paramètre. Les dimensions vous permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les régions, les produits et les représentants. Entre autres objectifs, utilisez des dimensions lors de la définition de vues d’analyse et de la création de rapports financiers. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

Pour en savoir plus sur les rapports financiers, voir [Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md).

## <a name="finance-reporting-across-business-units-or-legal-entities-related-to-sales"></a>Rapports financiers entre les unités fonctionnelles ou les entités juridiques associés aux ventes

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui rendent compte aux organisations mères. [!INCLUDE [prod_short](includes/prod_short.md)] fournit aux comptables des outils qui les aident à transférer les écritures de deux ou plusieurs compagnies (filiales) dans une compagnie consolidée. Spécifiquement pour la gestion des ventes, vous souhaiterez peut-être consolider les écritures GL pour vos comptes ventes pour suivre les indicateurs de performances clés de vente dans les unités fonctionnelles ou les entités juridiques.

Pour en savoir plus, reportez-vous à [Consolidation de la compagnie](finance-consolidated-company-reporting.md).

## <a name="ad-hoc-analysis-of-sales-data"></a>Analyse ad hoc des données de ventes

Parfois, il suffit de vérifier si les chiffres s’additionnent correctement ou de confirmer rapidement un chiffre. Les fonctionnalités suivantes sont idéales pour les analyses ad hoc :

- Analyses des données sur les pages de listes comptables
- Ouvrir dans Excel

La fonction Analyse des données vous permet d’ouvrir presque toutes les pages de liste, telles que les **Écritures GL**, les **Écritures client**, les **Écritures article** ou les **Factures reportées**, d’accéder au mode d'analyse, puis de regrouper, filtrer et faire pivoter les données comme bon vous semble.

:::image type="content" source="media/data-analysis-customer-ledger-entries.png" alt-text="Exemple de procédure pour effectuer une analyse des données Écritures client" lightbox="media/data-analysis-customer-ledger-entries.png":::

De la même manière, vous pouvez utiliser le **Ouvrir dans Excel** action pour ouvrir une page de liste, éventuellement filtrer la liste sur un sous-ensemble de données, puis utiliser Excel pour travailler avec les données. Par exemple, en utilisant des fonctionnalités telles que l’analyse des données, l’analyse de simulation ou la feuille de prévision.

:::image type="content" source="media/open-in-excel-customer-ledger-entries.png" alt-text="Exemple de procédure pour effectuer une analyse des données Écritures client avec Excel." lightbox="media/open-in-excel-customer-ledger-entries.png":::

> [!TIP]
> Si vous configuré OneDrive pour les fonctionnalités système, le classeur Excel s’ouvre dans votre navigateur.

Pour en savoir plus sur la manière d’effectuer une analyse ad hoc des données de ventes, accédez à [Analyse ad hoc des données de ventes](ad-hoc-analysis-sales.md). 

## <a name="built-in-reports-for-sales"></a>Rapports intégrés pour la vente

[!INCLUDE [prod_short](includes/prod_short.md)] comprend plusieurs rapports intégrés, fonctions de traçage et outils pour aider les organisations de vente à créer des rapports sur leurs données.

Pour obtenir un aperçu des rapports disponibles, choisir sur volet **Tous les rapports** en haut de votre page d’accueil. Cette Action ouvre l’explorateur de rôles, qui est filtré selon les fonctionnalités du **Rapport et analyse** option. Pour en savoir plus, voir [Recherche de rapports avec l’explorateur de rôles](ui-role-explorer.md). 

:::image type="content" source="media/report-explorer-sales.png" alt-text="Exemple de rapports sur le centre de rôle ventes." lightbox="media/report-explorer-sales.png":::

Les rapports intégrés sont disponibles en deux versions :

- Conçu pour l’impression (pdf).
- Conçu pour l’analyse dans Excel.

Pour en savoir plus sur les rapports pertinents pour les ventes, accédez aux [Rapports de ventes intégrés](sales-reports.md).

## <a name="on-screen-sales-analytics"></a>Analyse des ventes à l’écran

[!INCLUDE [prod_short](includes/prod_short.md)] comporte plusieurs pages qui vous donnent des aperçus des ventes et des tâches à accomplir. Voici des exemple pour commencer :

- [Ouvrez la **Devis** liste](https://businesscentral.dynamics.com/?page=9300)
- [Ouvrir la liste des **documents de vente**](https://businesscentral.dynamics.com/?page=9305)
- [Ouvrir la liste des **factures vente reportées**](https://businesscentral.dynamics.com/?page=143)
- [Ouvrez la liste des **Retour vente**](https://businesscentral.dynamics.com/?page=9304)
- [Calcul des dates promesse commande](sales-how-to-calculate-order-promising-dates.md)
- [Calculer les dates de livraison des documents de vente](sales-date-calculation-for-sales.md)
- [Suivi des paquets](sales-how-track-packages.md)
- [Afficher la disponibilité des articles](inventory-how-availability-overview.md)
- [État de la commande permanente ventes](sales-how-to-create-blanket-sales-orders.md#to-view-the-status-of-a-blanket-sales-order)
- [Afficher des lignes commande permanente ventes non reportées et reportées](sales-how-to-create-blanket-sales-orders.md#to-view-unposted-and-posted-blanket-sales-order-lines)


### <a name="show-sales-related-general-ledger-entries-and-balances-from-the-chart-of-accounts-page"></a>Afficher les écritures et les soldes du grand livre liées aux ventes à partir de la page Plan comptable

La page Plan comptable affiche tous les comptes du grand livre avec des chiffres agrégés reportés dans le grand livre. À partir de cette page, vous pouvez faire des choses comme :  

- Afficher les rapports qui affichent les écritures et les soldes.  
- Vérifiez une liste de groupes de report pour ce compte.
- Afficher les soldes débit et crédit d’un seul compte.

Spécifiquement pour les ventes, vous pouvez créer une vue sur la page Plan comptable qui affiche uniquement les comptes que vous utilisez pour reporter les écritures ventes.

:::image type="content" source="media/chart-of-accounts-page.png" alt-text="Exemple de la façon dont la page Plan comptable affiche des informations financières" lightbox="media/chart-of-accounts-page.png":::

Pour en savoir plus, allez à [Familiarisation avec le plan comptable](finance-general-ledger.md#the-chart-of-accounts).

### <a name="analyze-data-by-dimensions-related-to-sales"></a>Analyser des données par dimensions (associées aux ventes)

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur les documents, tels que les documents de vente. Les dimensions peuvent, par exemple, indiquer de quel projet ou département provient une écriture.  

Au lieu de configurer des comptes GL distincts pour chaque service ou site, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer une structure de plan comptable compliquée.

Pour plus d’informations, voir [Analyser des données par dimensions](bi-how-analyze-data-dimension.md).

## <a name="see-also"></a>Voir aussi .

[Consolidation de la compagnie](finance-consolidated-company-reporting.md)   
[Préparer des rapports financiers avec des données financières et des catégories de compte](bi-how-work-account-schedule.md)  
[Gestion des rapports financiers entre les unités fonctionnelles ou les entités juridiques](finance-consolidated-company-reporting.md)  
[Analyse ad hoc des données de ventes](ad-hoc-analysis-sales.md)   
[Rapports de vente intégrés](sales-reports.md)   
[Comprendre du plan comptable](finance-general-ledger.md#the-chart-of-accounts)  
[Analyser des données par dimensions](bi-how-analyze-data-dimension.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)   
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
