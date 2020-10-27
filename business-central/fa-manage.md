---
title: Gérer les immobilisations| Microsoft Docs
description: En savoir plus sur la fonctionnalité d'immobilisations et afficher un aperçu de l'utilisation des immobilisations.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: machinery, buildings
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 2886548e1af66e0f28eadc16c80f64263f3e1917
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3920632"
---
# <a name="fixed-assets"></a>Immobilisations
Le module Immobilisations dans [!INCLUDE[d365fin](includes/d365fin_md.md)] offre un aperçu des immobilisations et garantit un amortissement périodique correct. Elle vous permet également de connaître les coûts d'entretien, de gérer les polices d'assurance, de reporter les transactions d'immobilisations, et de générer des rapports et des statistiques variés.

Pour chaque immobilisation, vous devez créer une fiche contenant des informations la concernant. Vous pouvez configurer des bâtiments ou un équipement de production en tant qu'immobilisation principale avec une liste de composantes et vous pouvez les regrouper de différentes façons, comme par catégorie, département ou emplacement. Puis, vous pouvez commencer à acquérir, maintenir et commercialiser les immobilisations. Vous pouvez également paramétrer des immobilisations budgétées. Cela permet d'inclure dans des états des acquisitions et des ventes anticipées.

Pour conserver une trace des amortissements d'immobilisations ainsi que des autres transactions financières propres aux immobilisations, vous configurez un, voire plusieurs registres amortissement pour chaque immobilisation au sein de votre compagnie. L'amortissement est effectué en exécutant un rapport afin de calculer l'amortissement périodique et compléter un journal avec les écritures résultantes, prêtes à être reportées. [!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge plusieurs méthodes d'amortissement. Pour en savoir plus, voir [Méthodes d'amortissement](fa-depreciation-methods.md). Vous pouvez configurer plusieurs registres amortissement par immobilisation à différentes fins, telles qu'une pour la déclaration fiscale, et une autre pour les rapports internes.

Pour chaque immobilisation, vous pouvez enregistrer des coûts d'entretien et la date de la prochaine visite d'entretien. Le suivi des frais d'entretien peut être utile dans le cadre de l'élaboration du budget et de la prise de décisions concernant le remplacement éventuel d'une immobilisation.

Chaque immobilisation peut être liée à une ou à plusieurs polices d'assurance. Vous pouvez ainsi vérifier facilement la concordance des montants des polices d'assurance avec la valeur des immobilisations associées à ces polices. Cela facilite également le contrôle des primes d'assurance annuelles.

> [!NOTE]  
>   Vous pouvez enregistrer les transactions immobilisation sur la page **Journal GL immobilisation** ou sur la page **Journal immobilisations** , selon que les transactions sont destinées à des rapports financiers ou à la gestion interne. L'aide pour les immobilisations décrit uniquement la procédure d'utilisation de la page **Feuille compta. immo.** . Pour en savoir plus, voir [Configurer l'amortissement d'immobilisation](fa-how-setup-depreciation.md).

Pour pouvoir gérer les immobilisations, vous devez configurer les valeurs par défaut, la comptabilité des immobilisations, les groupes de report, les clés d'affectation, les journaux et les types de report. Pour plus d'informations, reportez-vous à [Paramétrage d'immobilisations](fa-setup.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Créer des immobilisations, affecter des méthodes d'amortissement, reporter des acquisitions et des valeurs résiduelles et imprimer les listes d'immobilisations. |[Acquérir des immobilisations](fa-how-acquire.md) |
| Enregistrer les visites de service, reporter les coûts d'entretien et surveiller les coûts d'entretien. |[Mettre à jour des immobilisations](fa-how-maintain.md) |
| Mettre à jour les informations d'assurance, reporter les coûts d'acquisition vers les polices d'assurance, modifier la couverture assurance, visualiser les statistiques assurance et répertorier les polices d'assurance. |[Assurer les immobilisations](fa-how-insure.md) |
| Reclasser les immobilisations, les transférer vers d'autres emplacements, les diviser ou les combiner. |[Transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md) |
| Ajustez les valeurs des immobilisations, reportez les appréciations et les transactions de dépréciation. |[Réévaluer les immobilisations](fa-how-revalue.md) |
| Calculer l'amortissement, reporter l'amortissement et analyser l'amortissement dans les rapports sur les immobilisations. |[Amortir des immobilisations](fa-how-depreciate-amortize.md) |
| Reporter les transactions de cession, visualiser les écritures cession et reporter les cessions partielles. |[Céder ou annuler des immobilisations](fa-how-dispose-retire.md) |
| Gérer les budgets d'immobilisations, budgéter les coûts d'acquisition, les cessions d'immobilisations et l'amortissement. |[Gérer les budgets pour les immobilisations](fa-how-manage-budgets.md) |

## <a name="video-overview"></a>Présentation de la vidéo
La vidéo suivante couvre les notions de base des immobilisations.

> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4AegS?rel=0]

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]  
 
