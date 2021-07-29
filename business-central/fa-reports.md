---
title: Rapports et analyses des immobilisations
description: Découvrez les rapports et analyses disponibles dans la version standard de Business Central afin que vous puissiez suivre vos immobilisations.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: reporting
ms.date: 07/13/2021
ms.author: edupont
ms.openlocfilehash: c28e62a2de51323e0a7dcd2f4b5ea26d5896d718
ms.sourcegitcommit: a486aa1760519c380b8cdc8fdf614bed306b65ea
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/13/2021
ms.locfileid: "6543394"
---
# <a name="fixed-assets-reports-and-analytics-in-business-central"></a>Rapports et analyses d’immobilisation dans Business Central

Pour vous aider à gérer vos immobilisations dans [!INCLUDE [prod_short](includes/prod_short.md)], des rapports et des analyses standard sont intégrés. Ils vont au-delà des contraintes des rapports traditionnels pour vous aider à concevoir efficacement divers types de rapports.  

## <a name="reports"></a>Rapports

Le tableau suivant décrit certains des principaux rapports dans les rapports d’immobilisation.

| Rapport | Code objet | Description |
|--|--|--|
| **Liste des immobilisations** | 5601 | Affiche la liste des immobilisations et leurs informations de configuration pour un registre amortissement donné. |
| **Immo. - Liste des acquisitions** | 5608 | Répertoriez tous les actifs acquis dans une plage de dates donnée. Vous pouvez également inclure des immobilisations créées, mais pas encore acquises. |
| **Détails de l’immobilisation** | 5604 | Affiche les écritures immobilisation pour les immobilisations. |
| **Analyse de l’immobilisation** | 5600 | Rapport d’analyse où vous pouvez spécifier deux colonnes de date et trois colonnes de données à afficher dans le rapport. Par exemple, pour générer un rapport à utiliser pour le rapprochement avec le grand livre, ajoutez des colonnes pour le coût d’acquisition à la date finale, l’amortissement à la date finale et la valeur comptable à la date finale. Un rapport de contrôle peut comporter des acquisitions/écart net, une dépréciation/écart net et une appréciation/écart net de sorte que chaque modification apportée aux immobilisations puisse être vérifiée si nécessaire. Si vous sélectionnez le champ **Rapport budget** et spécifiez une date finale ultérieure, le rapport calcule l’amortissement ultérieur et peut donner des estimations pour l’amortissement ultérieur et les valeurs comptables, si vous avez sélectionné ces champs comme colonnes de rapport. |
| **Valeur projetée de l’immobilisation** | 5607 | Affiche les montants d’amortissement projetés et la valeur comptable pour une période ultérieure des actifs. Ce rapport est très pratique si vous utilisez différentes méthodes d’amortissement pour vos actifs et si vous souhaitez estimer l’amortissement de l’année prochaine, par exemple. Utilisez le rapport pour créer les montants budgétaires pour l’amortissement en sélectionnant un budget et le champ **Copier vers budget GL**. |
| **Immo. Valeur comptable 01** | 5605 | Affiche des informations détaillées concernant le coût d’acquisition, la valeur d’amortissement et la valeur comptable à la fois pour les immobilisations individuelles et les groupes d’immobilisations. Pour ces trois types de montants, les calculs sont effectués au début et à la fin d’une période spécifique et pour la période elle-même. Si vous sélectionnez le champ **Rapport budget**, le rapport calcule l’amortissement prévu pour la période. Saisissez un *type de groupe* si vous souhaitez que le rapport regroupe les immobilisations et imprime des sous-totaux. Par exemple, si vous avez configuré six classes immobilisation, sélectionnez l’option *Classe immobilisation* pour que les totaux de groupe soient imprimés pour chaque code des six classes.|
| **Immo. Valeur comptable 02** | 5606 |Affiche la répartition de la valeur comptable des immobilisations en fonction des variations d’acquisition, d’amortissement et d’appréciation au cours de la période, avec une ventilation supplémentaire par acquisitions et cessions au cours de la période. Utilisez ce rapport pour décrire les changements dans les immobilisations pour une période donnée lorsque de nombreux changements différents se produisent dans le groupe d’immobilisations. Si vous sélectionnez le champ **Rapport budget**, le rapport calcule l’amortissement prévu pour la période. Saisissez un *type de groupe* si vous souhaitez que le rapport regroupe les immobilisations et imprime des sous-totaux. Par exemple, si vous avez configuré six classes immobilisation, sélectionnez l’option *Classe immobilisation* pour que les totaux de groupe soient imprimés pour chaque code des six classes. |
| **Analyse de grand livre immobilisations**| 5610 |Affiche une analyse de vos immobilisations en incluant divers types de données, pour les immobilisations et les classes d’immobilisations. Vous pouvez positionner des filtres sur le raccourci Immobilisation pour n’inclure que certaines immobilisations dans le rapport. Dans le raccourci Options, personnalisez le rapport pour répondre à vos besoins spécifiques. Le rapport est similaire au rapport **Analyse de l’immobilisation**, mais notamment pour la conciliation avec le grand livre et notamment pour la validation des écritures de cession. Le rapport suppose que vous connaissiez les comptes du grand livre spécifiés dans la configuration de report. |
| **Registre d’immobilisation** |5603  |Affiche les écritures immobilisation reportées triées et réparties par numéro de registre. Vous pouvez déterminer les écritures des registres affichées en positionnant un filtre. Il est important de positionner un filtre; dans le cas contraire, le rapport risque en effet d’afficher de nombreuses informations. |

## <a name="see-also"></a>Voir aussi

[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Utilisation des dimensions](finance-dimensions.md)  
[Gestion des immobilisations](fa-manage.md)  
[Vue d’ensemble des fonctionnalités locales](about-localization.md)  
[Expériences de comptable dans [!INCLUDE[prod_long](includes/prod_long.md)]](finance-accounting.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
