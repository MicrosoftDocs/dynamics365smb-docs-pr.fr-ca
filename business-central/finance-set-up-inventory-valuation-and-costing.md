---
title: Configuration de l’évaluation et du coût de l’inventaire
description: 'Pour vous assurer que les coûts ajustés sont enregistrés correctement, vous devez configurer plusieurs champs et pages avant de commencer à effectuer des transactions article.'
author: SorenGP
ms.topic: conceptual
ms.search.keywords: null
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="setting-up-inventory-valuation-and-costing"></a>Configuration de l'évaluation de l'inventaire et des coûts

Pour vous assurer que les coûts ajustés sont enregistrés correctement, vous devez configurer plusieurs champs et pages avant de commencer à effectuer des transactions article. En règle générale, les entreprises choisissent une méthode d'évaluation des coûts spécifique et l’appliquent aux articles en inventaire, par exemple, pour les aider à suivre la valeur des articles en stock.  

> [!TIP]
> Pour une introduction à l'évaluation des coûts dans [!INCLUDE [prod_short](includes/prod_short.md)], voir [À propos de l’évaluation des coûts de l'inventaire](finance-learn-about-costing.md).

Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.

|**Pour**|**Voir**|  
|------------|-------------|
|Spécifiez un mode d'évaluation coût par défaut de la compagnie pour régir la manière dont son coût entrant est utilisé pour évaluer la valeur de l'inventaire et le coût des biens vendus.|[Configurer des informations générales relatives à l'inventaire](inventory-how-setup-general.md)|  
|Spécifiez un mode évaluation des articles individuels s’ils nécessitent un mode évaluation stock différent.|[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)|  
|S'assurer que les coûts sont automatiquement reportés dans le grand livre lorsqu'une transaction d'inventaire est reportée.|Champ **Report coûts automatique** sur la page **Configuration de l'inventaire**|  
|S'assurer que les coûts prévus sont reportés au grand livre afin de visualiser, à partir des comptes du grand livre provisoires, une estimation des montants dus et du coût des articles échangés avant qu'ils ne soient effectivement facturés.|Champ **Report coût prévu au GL** sur la page **Configuration inventaire**|  
|Configurer le système afin d'ajuster automatiquement toute modification des coûts chaque fois que vous reportez des transactions d'inventaire.|[Ajuster coûts et prix article](inventory-how-adjust-item-costs.md)|  
|Définir si le coût moyen doit être calculé uniquement par article ou par article pour chaque unité de stock et pour chaque variante de l’article.|Champ **Type calcul coût moyen** sur la page **Configuration de l'inventaire**|  
|Sélectionnez la période que l'application doit utiliser pour calculer le coût moyen pondéré des articles qui utilisent la méthode évaluation coût moyen.|Champ **Période coût moyen** sur la page **Configuration de l'inventaire**|  
|Définir des périodes d'inventaire pour contrôler la valeur de l'inventaire dans le temps en refusant d'accorder le report de transactions lorsque les périodes d'inventaire sont fermées.|[Utiliser les périodes d'inventaire](finance-how-to-work-with-inventory-periods.md)|  
|Assurez-vous que les retours vente sont affectés à la transaction sortante initiale afin de préserver la valeur d'inventaire.|Champ**Coût d'inversion exact obligatoire** sur la page **Configuration ventes et à recevoir**|  
|Assurez-vous que les retours achat sont affectés à la transaction entrante initiale afin de préserver la valeur d'inventaire.|Champ **Inversion coût exact obligatoire** sur la page **Achats**|
|Configurer les règles d'arrondissement à appliquer lors de l'ajustement ou de la proposition des prix article et lors de l'ajustement ou de la proposition des coûts standard.|Page **Méthode d'arrondissement**|  

## <a name="see-also"></a>Voir aussi

[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Configurer des informations générales relatives à l'inventaire](inventory-how-setup-general.md)  
[Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Pratiques de configuration recommandées : mode évaluation stock](setup-best-practices-costing-method.md)  
[Détails de conception : Évaluation des coûts de l'inventaire](design-details-inventory-costing.md)  
[Détails de conception : Modifier le mode évaluation stock pour les articles](design-details-changing-costing-methods.md)  
[Utiliser Business Central](ui-work-product.md)  
[Finance](finance.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
