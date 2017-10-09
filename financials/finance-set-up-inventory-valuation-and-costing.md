---
title: "Configuration de l'évaluation de l'inventaire et des coûts | Microsoft Docs"
description: "Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: aa5ee6d9942390a2b4ad0aa8787172b0f7b141d0
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="setting-up-inventory-valuation-and-costing"></a>Configuration de l'évaluation de l'inventaire et des coûts
Pour vous assurer que les coûts ajustés sont enregistrés correctement, vous devez configurer plusieurs champs et fenêtres avant de commencer à effectuer des transactions article.

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|  
|Configurez un mode d'évaluation coût pour chaque article afin de régir la manière dont son coût entrant est utilisé pour évaluer la valeur d'inventaire et le coût des biens vendus.|[Procédure : enregistrer de nouveaux articles](inventory-how-register-new-items.md)|  
|S'assurer que les coûts sont automatiquement reportés dans le grand livre lorsqu'une transaction d'inventaire est reportée.|Champ **Report coûts automatique** de la page **Configuration de l'inventaire**|  
|S'assurer que les coûts prévus sont reportés au grand livre afin de visualiser, à partir des comptes du grand livre provisoires, une estimation des montants dus et du coût des articles échangés avant qu'ils ne soient effectivement facturés.|Champ **Report coût prévu au GL** de la page **Configuration de l'inventaire**|  
|Configurer le système afin d'ajuster automatiquement toute modification des coûts chaque fois que vous reportez des transactions d'inventaire.|[Procédure : ajustement des coûts article](inventory-how-adjust-item-costs.md)|  
|Définir si le coût moyen doit être calculé uniquement par article ou par article pour chaque référence SKU et pour chaque variante de l'article.|Champ **Type calcul coût moyen** de la page **Configuration de l'inventaire**|  
|Sélectionner la période que le programme doit utiliser pour calculer le coût moyen pondéré des articles qui utilisent la méthode évaluation stock Moyen.|Champ **Période coût moyen** de la page **Configuration de l'inventaire**|  
|Définir des périodes d'inventaire pour contrôler la valeur de l'inventaire dans le temps en refusant d'accorder le report de transactions lorsque les périodes d'inventaire sont fermées.|[Procédure : utiliser les périodes inventaire](finance-how-to-work-with-inventory-periods.md)|  
|Assurez-vous que les retours vente sont affectés à la transaction sortante initiale afin de préserver la valeur d'inventaire.|Champ**Coût retour identique obligatoire** de la page **Ventes**|  
|Assurez-vous que les retours achat sont affectés à la transaction entrante initiale afin de préserver la valeur d'inventaire.|Champ**Coût retour identique obligatoire** de la page **Achats**|
|Configurer les règles d'arrondissement à appliquer lors de l'ajustement ou de la proposition des prix article et lors de l'ajustement ou de la proposition des coûts standard.|Page **Méthode d'arrondissement**|  

## <a name="see-also"></a>Voir aussi  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Utilisation de Financials](ui-work-product.md)  
[Finance](finance.md)  

