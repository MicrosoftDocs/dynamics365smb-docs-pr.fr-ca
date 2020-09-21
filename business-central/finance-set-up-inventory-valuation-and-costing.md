---
title: Configuration de l'évaluation de l'inventaire et des coûts | Microsoft Docs
description: Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: a615e4b605267f12913dbcfee8e8a00e659369e4
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3780420"
---
# <a name="setting-up-inventory-valuation-and-costing"></a>Configuration de l'évaluation de l'inventaire et des coûts
Pour vous assurer que les coûts ajustés sont enregistrés correctement, vous devez configurer plusieurs champs et pages avant de commencer à effectuer des transactions article.

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Configurez un mode d'évaluation coût pour chaque article afin de régir la manière dont son coût entrant est utilisé pour évaluer la valeur d'inventaire et le coût des biens vendus.|[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)|  
|S'assurer que les coûts sont automatiquement reportés dans le grand livre lorsqu'une transaction d'inventaire est reportée.|Champ **Report coûts automatique** sur la page **Configuration de l'inventaire**|  
|S'assurer que les coûts prévus sont reportés au grand livre afin de visualiser, à partir des comptes du grand livre provisoires, une estimation des montants dus et du coût des articles échangés avant qu'ils ne soient effectivement facturés.|Champ **Report coût prévu au GL** sur la page **Configuration inventaire**|  
|Configurer le système afin d'ajuster automatiquement toute modification des coûts chaque fois que vous reportez des transactions d'inventaire.|[Ajuster coûts et prix article](inventory-how-adjust-item-costs.md)|  
|Définir si le coût moyen doit être calculé uniquement par article ou par article pour chaque référence SKU et pour chaque variante de l'article.|Champ **Type calcul coût moyen** sur la page **Configuration de l'inventaire**|  
|Sélectionnez la période que l'application doit utiliser pour calculer le coût moyen pondéré des articles qui utilisent la méthode évaluation coût moyen.|Champ **Période coût moyen** sur la page **Configuration de l'inventaire**|  
|Définir des périodes d'inventaire pour contrôler la valeur de l'inventaire dans le temps en refusant d'accorder le report de transactions lorsque les périodes d'inventaire sont fermées.|[Utiliser les périodes d'inventaire](finance-how-to-work-with-inventory-periods.md)|  
|Assurez-vous que les retours vente sont affectés à la transaction sortante initiale afin de préserver la valeur d'inventaire.|Champ**Coût d'inversion exact obligatoire** sur la page **Configuration ventes et à recevoir**|  
|Assurez-vous que les retours achat sont affectés à la transaction entrante initiale afin de préserver la valeur d'inventaire.|Champ**Coût d'inversion exact obligatoire** sur la page **Achats et à payer**|
|Configurer les règles d'arrondissement à appliquer lors de l'ajustement ou de la proposition des prix article et lors de l'ajustement ou de la proposition des coûts standard.|Page **Méthode d'arrondissement**|  

## <a name="see-also"></a>Voir aussi  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Utilisation de Business Central](ui-work-product.md)  
[Finance](finance.md)  
