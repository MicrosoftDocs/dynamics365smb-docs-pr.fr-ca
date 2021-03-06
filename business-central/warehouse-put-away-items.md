---
title: Rangement d'articles | Microsoft Docs
description: L'activité entrepôt consistant à ranger les articles une fois reçus ou fabriqués s'exécute différemment selon la configuration des fonctionnalités du module Gestion d'entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: d19486956fbaa0addb58a71c13849b0bb32c958a
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5771584"
---
# <a name="putting-items-away"></a>Rangement des articles
L'activité entrepôt consistant à ranger les articles une fois reçus ou fabriqués s'exécute différemment selon la configuration des fonctionnalités du module Gestion d'entrepôt. Le niveau de complexité du paramétrage varie : aucune fonctionnalité entrepôt, configurations de stockage de base pour le traitement par commande dans une ou plusieurs activités uniquement, configurations avancées dans lesquelles toutes les activités entrepôt doivent être exécutées dans un flux suggéré. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Si vous décidez d'organiser et d'enregistrer vos informations de rangement avec des documents entrepôt, activez le champ **Rangement requis** dans la fiche emplacement. Ceci indique à l'application que, lorsque vous avez des articles qui entrent dans l'emplacement entrepôt via un document source entrant, vous souhaitez que le rangement de ces articles soit contrôlé par le système. Un document source entrant peut être un bon de commande, un retour vente, un ordre de transfert entrant ou un bon de production dont la production est prête à être rangée.  

Si votre emplacement est configuré pour exiger un traitement des rangements, mais pas un traitement des réceptions, vous utilisez la page **Rangement inventaire** pour organiser les informations de rangement, les imprimer, entrer le résultat du rangement effectif et reporter les informations de rangement, ce qui reporte les informations de réception pour le document source. En cas de bon de production, le processus de report reporte la production de la commande et termine le bon de production.

Si votre emplacement est configuré pour exiger à la fois le traitement des réceptions et des rangements, de sorte que vous ayez coché les deux champs **Réception requise** et **Rangement requis** dans la fiche emplacement, le rangement des articles exige un processus différent. Dans ce cas, vous utilisez la page **Rangement entrepôt** pour traiter le rangement. Le rangement entrepôt fonctionne comme le rangement inventaire, si ce n'est qu'au lieu de reporter les informations, vous enregistrez le rangement. Remarquez que l'enregistrement du rangement entrepôt ne reporte pas la réception des articles. Il met simplement à jour le contenu de la zone. En tant qu'administrateur entrepôt, vous pouvez utiliser des feuilles rangement pour organiser les informations de rangement avant de créer des instructions de rangement entrepôt.

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.   

|**Pour**|**Voir**|  
|------------|-------------|  
|Reportez la réception d'articles directement à partir du document commande entrante et donc enregistrez le rangement, car aucune configuration entrepôt n'existe.|[Réceptionner des articles](warehouse-how-receive-items.md)|  
|Ranger les articles par commande et reporter la réception dans la même activité dans une configuration entrepôt de base.|[Ranger des articles avec le rangement stock](warehouse-how-to-put-items-away-with-inventory-put-aways.md)|  
|Ranger les articles de plusieurs commandes dans une configuration entrepôt avancée.|[Ranger des articles avec le rangement entrepôt](warehouse-how-to-put-items-away-with-warehouse-put-aways.md)|  
|Ranger les articles fabriqués ou assemblés dans une configuration de stockage de base ou avancée.|[Rangement du résultat de fabrication ou d'assemblage](warehouse-how-to-put-away-production-output.md)|
|Planifiez des instructions de rangement optimisées pour plusieurs réceptions entrepôt reportées. Dans ce cas, les employés d'entrepôt n'ont pas à agir directement sur les réceptions.|[Planifier des rangements dans la feuille](warehouse-how-to-plan-put-aways-in-worksheets.md)|  
|Replacer les articles prélevés techniquement à l'aide d'un prélèvement interne, par exemple dans le cadre d'un bon de production pour lequel la quantité prévue n'a pas été consommée.|[Prélever et ranger sans document origine](warehouse-how-to-create-put-aways-from-internal-put-aways.md)|
|Éclatez une ligne rangement pour placer une partie de la quantité rangée dans les zones disponibles si la zone désignée est pleine.|[Répartir des lignes activité entrepôt](warehouse-how-to-split-warehouse-activity-lines.md)|
|Accéder immédiatement aux rangements qui vous ont été affectés en tant que magasinier.|[Trouver vos affectations d'entrepôt](warehouse-how-to-find-your-warehouse-assignments.md)|    

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]