---
title: Immobilisations| Microsoft Docs
description: "Décrit la procédure de gestion des immobilisations."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: machinery, buildings
ms.date: 03/23/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: d57603202d9e2e5304c899eaf764dde8cfa6369d
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="fixed-assets"></a>Immobilisations
Le module Immobilisations dans [!INCLUDE[d365fin](includes/d365fin_md.md)] offre un aperçu des immobilisations et garantit un amortissement périodique correct. Elle vous permet également de connaître les coûts d'entretien, de gérer les polices d'assurance, de reporter les transactions d'immobilisations, et de générer des rapports et des statistiques variés.

Pour chaque immobilisation, vous devez créer une fiche contenant des informations la concernant. Vous pouvez configurer des bâtiments ou un équipement de production en tant qu'immobilisation principale avec une liste de composantes et vous pouvez les regrouper de différentes façons, comme par catégorie, département ou emplacement. Puis, vous pouvez commencer à acquérir, maintenir et commercialiser les immobilisations. Vous pouvez également paramétrer des immobilisations budgétées. Cela permet d'inclure dans des états des acquisitions et des ventes anticipées.

Pour conserver une trace des amortissements d'immobilisations ainsi que des autres transactions financières propres aux immobilisations, vous configurez un, voire plusieurs registres amortissement pour chaque immobilisation au sein de votre compagnie. L'amortissement est effectué en exécutant un rapport afin de calculer l'amortissement périodique et compléter un journal avec les écritures résultantes, prêtes à être reportées. [!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge plusieurs méthodes d'amortissement. Pour en savoir plus, voir [Méthodes d'amortissement](fa-depreciation-methods.md). Vous pouvez configurer plusieurs registres amortissement par immobilisation à différentes fins, telles qu'une pour la déclaration fiscale, et une autre pour les rapports internes.

Pour chaque immobilisation, vous pouvez enregistrer des coûts d'entretien et la date de la prochaine visite d'entretien. Le suivi des frais d'entretien peut être utile dans le cadre de l'élaboration du budget et de la prise de décisions concernant le remplacement éventuel d'une immobilisation.

Chaque immobilisation peut être liée à une ou à plusieurs polices d'assurance. Vous pouvez ainsi vérifier facilement la concordance des montants des polices d'assurance avec la valeur des immobilisations associées à ces polices. Cela facilite également le contrôle des primes d'assurance annuelles.

**Remarque** : vous pouvez enregistrer les transactions immobilisation dans la fenêtre **Feuille compta. immo.** ou dans la fenêtre **Feuille immo.**, selon que les transactions sont destinées pour des rapports financiers ou pour la gestion interne. L'aide pour les immobilisations décrit uniquement la procédure d'utilisation de la fenêtre **Feuille compta. immo.**. Pour en savoir plus, voir [Procédure : configurer l'amortissement d'immobilisation](fa-how-setup-depreciation.md).

**Remarque** : Cette fonctionnalité nécessite que votre expérience soit définie sur **Suite**. Pour plus d'informations, voir [Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md).

Pour pouvoir gérer les immobilisations, vous devez configurer les valeurs par défaut, la comptabilité des immobilisations, les groupes de report, les clés d'affectation, les journaux et les types de report. Pour plus d'informations, reportez-vous à [Paramétrage d'immobilisations](fa-setup.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

| À | Voir |
| --- | --- |
| Créer des immobilisations, affecter des méthodes d'amortissement, reporter des acquisitions et des valeurs résiduelles et imprimer les listes d'immobilisations. |[Procédure : acquérir des immobilisations](fa-how-acquire.md) |
| Enregistrer les visites de service, reporter les coûts d'entretien et surveiller les coûts d'entretien. |[Procédure : mettre à jour des immobilisations](fa-how-maintain.md) |
| Mettre à jour les informations d'assurance, reporter les coûts d'acquisition vers les polices d'assurance, modifier la couverture assurance, visualiser les statistiques assurance et répertorier les polices d'assurance. |[Procédure : garantir des immobilisations](fa-how-insure.md) |
| Reclasser les immobilisations, les transférer vers d'autres emplacements, les diviser ou les combiner. |[Procédure : transférer, fractionner ou regrouper les immobilisations](fa-how-trans-split-combine.md) |
| Ajustez les valeurs des immobilisations, reportez les appréciations et les transactions de dépréciation. |[Procédure : réévaluer des immobilisations](fa-how-revalue.md) |
| Calculer l'amortissement, reporter l'amortissement et analyser l'amortissement dans les rapports sur les immobilisations. |[Procédure : amortir des immobilisations](fa-how-depreciate-amortize.md) |
| Reporter les transactions de cession, visualiser les écritures cession et reporter les cessions partielles. |[Procédure : céder ou annuler des immobilisations](fa-how-dispose-retire.md) |
| Gérer les budgets d'immobilisations, budgéter les coûts d'acquisition, les cessions d'immobilisations et l'amortissement. |[Procédure : gérer les budgets pour les immobilisations](fa-how-manage-budgets.md) |

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Personnalisation de votre [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md)  
[Finance](finance.md)  
[Bienvenue dans [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](index.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

## [!INCLUDE[d365fin](includes/free_trial_md.md)]
