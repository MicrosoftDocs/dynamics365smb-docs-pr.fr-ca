---
title: Gérer les immobilisations (contient une vidéo)
description: En savoir plus sur la fonctionnalité d’immobilisations et afficher un aperçu de l’utilisation et de la gestion de vos immobilisations.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'machinery, buildings'
ms.search.form: '5604, 5606, 5664, 5601, 5602, 5658, 5603, 5671, 5641, 5629, 5633, 5634, 5649, 5622, 5650'
ms.date: 05/06/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="manage-fixed-assets"></a>Gérer des immobilisations

Le module Immobilisations dans [!INCLUDE[prod_short](includes/prod_short.md)] offre un aperçu des immobilisations et garantit un amortissement correct. Elle vous permet également de suivre les coûts d'entretien, de gérer les polices d’assurance, de reporter les transactions d’immobilisations, et de générer divers rapports et statistiques.

## <a name="video-overview"></a>Présentation de la vidéo

La vidéo suivante couvre les notions de base des immobilisations :

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4AegS?rel=0]

## <a name="initial-setup-of-fixed-assets"></a>Configuration initiale des immobilisations

Avant de pouvoir gérer les immobilisations, vous devez effectuer les configurations suivantes :

- Valeur par défaut
- Comptabilité immobilisations
- Groupes et types de report
- Clés d’affectation
- Journaux immobilisation

Pour en savoir plus, accédez à [Configuration des Immobilisations](fa-setup.md).

## <a name="fixed-assets-analytics"></a>Analyse des immobilisations

Cette section décrit les outils analytiques que vous pouvez utiliser pour obtenir des informations dans vos données sur vos Immobilisations.

| Pour... | Voir |
| --- | --- |
| Découvrez les fonctionnalités d’analyse des données sur les immobilisations. | [Vue d’ensemble de l’analyse des immobilisations](fa-analytics-overview.md) |
| Effectuez une analyse ad hoc des données Immobilisations directement sur les pages de liste et les requêtes. | [Analyse ad hoc des données Immobilisations](ad-hoc-analysis-fa.md) |
| Explorez des rapports intégrés sur les immobilisations. | [Rapports immobilisations intégrés](fa-reports.md) |
| Surveillez les coûts d'entretien. | [Surveiller les coûts d’entretien](fa-how-maintain.md#to-monitor-maintenance-costs)|
| Surveillance des couvertures d’assurance. | [Surveillance des couvertures d’assurance](fa-how-insure.md#to-monitor-insurance-coverage) |
| Affichez des écritures cession. | [Afficher des écritures cession](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| Visualiser des valeurs de cession prévues. | [Affichage des valeurs de cession prévues](fa-how-manage-budgets.md#to-view-projected-disposal-values) |

## <a name="register-fixed-assets"></a>Enregistrer Immobilisations

Pour chaque immobilisation, vous devez créer une fiche contenant des informations les concernant. Par exemple, vous pouvez configurer des bâtiments ou du matériel de production en tant qu'actifs principaux avec une liste de composantes. Vous pouvez regrouper les actifs de différentes manières par exemple, par classe, par département ou par emplacement. Puis, vous pouvez acquérir, maintenir et commercialiser les immobilisations. Vous pouvez également paramétrer des immobilisations budgétées. La budgétisation vous permet par exemple d’inclure dans des rapports des acquisitions et des ventes anticipées.

| À  | Voir |
| --- | --- |
| Gérer les budgets d'immobilisations, budgéter les coûts d'acquisition, les cessions d'immobilisations et l'amortissement. |[Gestion des budgets pour les immobilisations](fa-how-manage-budgets.md) |
| Créer des immobilisations, affecter des méthodes d'amortissement, reporter des acquisitions et des valeurs résiduelles et imprimer les listes d'immobilisations. |[Acquisition des immobilisations](fa-how-acquire.md) |

## <a name="set-up-depreciations-for-your-fixed-assets"></a>Configurer les Amortissement des immobilisations

Pour suivre des amortissements d’immobilisations et d’autres transactions financières pour les immobilisations, configurez un voire plusieurs registres amortissement pour chacune. Voici quelques étapes pour amortir les actifs :

1. Exécutez un rapport pour calculer l'amortissement périodique.
1. Renseignez un journal avec les écritures résultantes.
1. Reportez le journal.

[!INCLUDE[prod_short](includes/prod_short.md)] prend en charge plusieurs méthodes d'amortissement. Pour en savoir plus, consultez [Méthodes amortissement](fa-depreciation-methods.md). Vous pouvez configurer plusieurs registres d'amortissement pour chaque immobilisation à différentes fins, par exemple une pour la déclaration fiscale et une autre pour les rapports internes.

| À  | Voir |
| --- | --- |
| En savoir plus sur les différentes méthodes d'amortissement des immobilisations. |[Méthodes d'amortissement](fa-depreciation-methods.md) |
| Calculer l'amortissement, reporter l'amortissement et analyser l'amortissement dans les rapports sur les immobilisations. |[Amortissement des immobilisations](fa-how-depreciate-amortize.md) |
| Affichez les valeurs de registre d’amortissement modifiées. | [Afficher les valeurs de registre d’amortissement modifiées](fa-how-trans-split-combine.md#to-view-changed-depreciation-book-values-due-to-fixed-asset-reclassification) |
| Enregistrez les transactions immobilisation manuellement sur la page **Journal GL immobilisation** ou sur la page **Journal immobilisations**, selon que les transactions sont destinées à des rapports financiers ou à la gestion interne. | [Configuration des amortissements](fa-how-setup-depreciation.md) |

## <a name="fixed-assets-maintenance-and-insurance"></a>Entretien et assurance des immobilisations

Vous pouvez enregistrer des coûts d'entretien et la date du prochain service pour chaque actif. Le suivi des frais d’entretien peut être important dans le cadre de l’élaboration du budget et de la prise de décisions concernant le remplacement éventuel d’une immobilisation. Vous pouvez rattacher chaque immobilisation à une ou plusieurs polices d’assurance et vérifier que les primes des polices correspondent à la valeur des actifs.

| À  | Voir |
| --- | --- |
| Enregistrer les visites de service, reporter les coûts d'entretien et surveiller les coûts d'entretien. |[Mise à jour des immobilisations](fa-how-maintain.md) |
| Surveillez les coûts d'entretien. | [Surveiller les coûts d’entretien](fa-how-maintain.md#to-monitor-maintenance-costs)|
| Mettre à jour les informations d'assurance, reporter les coûts d'acquisition vers les polices d'assurance, modifier la couverture assurance, visualiser les statistiques assurance et répertorier les polices d'assurance. |[Assurance des immobilisations](fa-how-insure.md) |
| Surveillance des couvertures d’assurance. | [Surveillance des couvertures d’assurance](fa-how-insure.md#to-monitor-insurance-coverage) |

## <a name="reclassify-transfer-split-upcombine-adjust-value-write-down-and-dispose-fixed-assets"></a>Reclasser, transférer, diviser/regrouper, ajuster la valeur, déprécier et céder des immobilisations

| À  | Voir |
| --- | --- |
| Reclasser les immobilisations, les transférer vers d'autres emplacements, les diviser ou les combiner. |[Transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md) |
| Ajustez les valeurs des immobilisations, reportez les appréciations et les transactions de dépréciation. |[Réévaluation des immobilisations](fa-how-revalue.md) |
| Reporter les transactions de cession, visualiser les écritures cession et reporter les cessions partielles. |[Cession ou annulation des immobilisations](fa-how-dispose-retire.md) |
| Affichez des écritures cession. | [Afficher des écritures cession](fa-how-dispose-retire.md#to-view-disposal-ledger-entries) |
| Visualiser des valeurs de cession prévues. | [Affichage des valeurs de cession prévues](fa-how-manage-budgets.md#to-view-projected-disposal-values) |

## <a name="see-also"></a>Voir aussi .

[Paramétrage d'immobilisations](fa-setup.md)  
[Vue d’ensemble de l’analyse des immobilisations](fa-analytics-overview.md)  
[Vue d’ensemble de Finances](finance.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modification des fonctionnalités affichées](ui-experiences.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
