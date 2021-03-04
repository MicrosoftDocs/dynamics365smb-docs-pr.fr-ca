---
title: Détails de conception - Évaluation de l'inventaire | Microsoft Docs
description: L’évaluation de l'inventaire est la détermination du coût d’un article d'inventaire.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: ad2698338f717541665cc5b53f6196c02f694562
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4751440"
---
# <a name="design-details-inventory-valuation"></a>Détails de conception : évaluation de l'inventaire
L’évaluation de l'inventaire est la détermination du coût qui est affecté à un article d'inventaire, comme exprimé par l’équation suivante.  

Fin inventaire = Début inventaire + achats nets – coût des biens vendus  

Le calcul de l'évaluation de l'inventaire utilise le champ **Coût indiqué (réel)** des écritures valeur pour l'article. Les écritures sont classées en fonction du type d’écriture correspondant aux composantes de coût, au coût direct, au coût indirect, à l’écart, à la réévaluation et à l’arrondissement de coût. Pour plus d'informations, voir [Détails de conception : composants des coûts](design-details-cost-components.md).  

Les écritures sont affectées les unes en fonction des autres, soit par une affectation fixe, soit en fonction du principe général coût-flux défini par le mode d’évaluation du coût. Une écriture de diminution d'inventaire peut être affectée avec plusieurs écritures d'augmentation avec des dates de report différentes et éventuellement différents coûts d’acquisition. Pour plus d'informations, voir [Détails de conception : traçabilité](design-details-item-application.md). Par conséquent, le calcul de la valeur d'inventaire d’une date donnée est basée sur l’ajout des écritures valeur positives et négatives.  

## <a name="inventory-valuation-report"></a>Rapport Évaluation de l'inventaire  
Pour calculer la valeur du stock dans le rapport **Évaluation du stock**, le rapport commence par calculer la valeur de stock de l'article à une date de début donnée. Il ajoute ensuite la valeur des augmentations d'inventaire et soustrait la valeur des diminutions d'inventaire jusqu'à une date fin donnée. Le résultat final est la valeur inventaire à la date fin. Le rapport calcule ces valeurs en additionnant les valeurs dans le champ **Coût indiqué (réel)** dans les écritures valeur, à l'aide des dates de report en tant que filtres.  

Le rapport imprimé affiche toujours les montants réels, c'est-à-dire le coût des écritures qui ont été reportées comme étant facturées. Le rapport imprime également le coût prévu des écritures reportées comme étant réceptionnées ou livrées, si vous sélectionnez le champ Inclure coûts prévus sur le raccourci Options.  

> [!IMPORTANT]  
>  Les valeurs dans le rapport **Évaluation du stock** sont rapprochées au compte Inventory dans la comptabilité, ce qui signifie que les écritures valeur en question ont été validées en comptabilité.  

> [!IMPORTANT]  
>  Les montants des colonnes **Valeur** de l'état sont basés sur la date de comptabilisation des transactions d'un article.  

## <a name="inventory-valuation---wip-report"></a>Rapport Évaluation de l'inventaire - TEC  
Une compagnie manufacturière doit déterminer la valeur de trois types d'inventaire :  

* Inventaire de matières premières  
* Inventaire TEC  
* Inventaire de produits finis  

La valeur de l'inventaire TEC est déterminée par l'équation suivante :  

* Fin inventaire TEC = début inventaire TEC + coût de fabrication – coût des produits fabriqués  

À l'instar de l'inventaire des achats, les écritures valeur constituent la base de l'évaluation de l'inventaire. Le calcul est effectué à l'aide des valeurs du champ **Coût indiqué (réel)** des écritures valeur article et capacité associées à un bon de production.  

L'objectif de l'évaluation de l'inventaire TEC est de déterminer la valeur des articles dont la fabrication n'est pas encore terminée à une date donnée. Par conséquent, la valeur inventaire TEC est basée sur les écritures valeur associées à la consommation et aux écritures du grand livre de capacité. Les écritures de consommation doivent être entièrement facturées à la date de l'évaluation. Par conséquent, l'état **Inventory Valuation – WIP** indique les coûts représentant la valeur stock TEC pour deux catégories : consommation et capacité.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : rapprochement de comptabilité](design-details-reconciliation-with-the-general-ledger.md)   
[Détails de conception : réévaluation](design-details-revaluation.md)   
[Détails de conception : report de bon de production](design-details-production-order-posting.md)
[Gestion des coûts de l'inventaire](finance-manage-inventory-costs.md)  
[Finance](finance.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]