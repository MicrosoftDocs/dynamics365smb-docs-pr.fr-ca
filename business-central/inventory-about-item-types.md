---
title: Comprendre les types d’articles
description: 'Vous pouvez ajuster l’évaluations de l’inventaire d’un article à l’aide des méthodes FIFO ou d’évaluation inventaire moyen, lorsque les coûts article sont modifiés pour des motifs autres que les transactions.'
documentationcenter: ''
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.search.form: '9297, 5845, 30,'
ms.date: 06/16/2021
ms.author: edupont
---
# <a name="about-item-types"></a><a name="about-item-types"></a><a name="about-item-types"></a>À propos des types d'articles
Dans le champ **Type** de la page **Fiche article**, vous pouvez sélectionner ce pourquoi l’article est utilisé dans votre activité, ce qui a une incidence sur le niveau de gestion que vous pouvez exercer sur l’article en inventaire. Le tableau suivant répertorie et décrit les trois types d’éléments disponibles.

|Option|Objectif courant|
|------|-----------|
|Inventaire|Les objets physiques, tels que les vélos, les téléphones et les bureaux, pour lesquels vous souhaitez pouvoir utiliser tous les processus d'inventaire. Cela peut également inclure des éléments non physiques, tels que des licences logicielles et des abonnements, si les éléments ont des numéros d’identification, tels que des numéros de série. Vous pouvez suivre entièrement les valeurs et la disponibilité des articles dans l’inventaire.|
|Hors inventaire|En règle générale, les articles hors inventaire sont des objets physiques, tels que des boulons ou des stylos, qu’une entreprise consomme mais ne souhaite pas suivre entièrement dans l'inventaire. Par exemple, parce que ce sont des articles qui ne coûtent pas cher et qu’ils ne sont utilisés qu’en interne.|
|Service|Une unité de temps de travail, telle qu'une heure de conseil, pour la prise en charge limitée de l'activité.|

> [!NOTE]
> Les types **Service** et **Hors inventaire** ne prennent pas en charge le suivi des quantités et les valeurs d'inventaire. Seuls les types de transaction articles et fonctionnalités sélectionnés sont pris en charge.

Le tableau suivant répertorie les fonctions que les trois types d’article prennent en charge.

|Type d'article|Ventes|Achats|Consommation de projet|Consommation de service|Consommation d'assemblage|Production Consommation|Résultat d'assemblage|Production|Transfert emplacement|Inventaire physique|Réévaluation de l'inventaire|Évaluation stock|Traçabilité|Réservation|Entreposage|Planific.|Planification commande|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Stocks|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
|Hors inventaire|Oui|Oui|Oui|Oui|Oui|Oui|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|Oui|
|Service|Oui|Oui|Oui|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|Oui|

## <a name="costing-methods-for-types-of-items"></a><a name="costing-methods-for-types-of-items"></a><a name="costing-methods-for-types-of-items"></a>Modes évaluation stock pour les types d'articles
Lorsque vous reportez des transactions d'inventaire, les changements de quantité et de valeur en inventaire sont enregistrés dans les écritures du grand livre d'articles et les écritures valeur, respectivement. 

Pour les articles d'inventaire, le coût est reporté dans le champ **Coût indiqué (réel)** sur la page **Écritures valeur**, et lorsqu'il est rapproché du grand livre, le coût sera indiqué dans le champ **Coût reporté au GL**. Pour plus d'informations, voir [Détails de conception : Évaluation stock](design-details-inventory-costing.md).

Pour les articles hors inventaire et de service, le coût est enregistré dans le champ **Coût indiqué (avant bal. stock)** sur la page **Écritures valeur**. Pour les articles hors inventaire et de service, le coût est spécifié sur les documents et journaux de vente, d'assemblage et de production. Le coût par défaut peut être spécifié dans le champ **Coût unitaire** sur les pages **Fiche article** et **Unité de stock**. Les coûts de ces types d'articles ne sont pas rapprochés du grand livre. 

## <a name="catalog-and-service-items"></a><a name="catalog-and-service-items"></a><a name="catalog-and-service-items"></a>Articles de catalogue et de service
Les articles que vous offrez à vos clients mais que vous ne souhaitez pas gérer dans le système jusqu'à ce que vous commenciez à les vendre peuvent être définis comme des articles de catalogue. Les articles de catalogue ne doivent pas être confondus avec les articles normaux de type Hors inventaire. Pour en savoir plus, voir [Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md).

Les articles des clients pour lesquels vous effectuez un service, par exemple une imprimante, sont appelés des articles de service. Les articles de service n'ont rien à voir avec des articles courants ou de catalogue. Cependant, les composantes de service peuvent être des articles courants. Pour plus d'informations, voir [Configurer les articles de service et les composantes article de service](service-how-setup-service-items.md).

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de l'inventaire](inventory-setup-inventory.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
