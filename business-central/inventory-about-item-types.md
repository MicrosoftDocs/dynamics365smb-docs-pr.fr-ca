---
title: Comprendre les types d’articles
description: 'En savoir plus sur les types d''articles que vous pouvez gérer en inventaire, et comment les types affectentVous pouvez ajuster l’évaluation de l''inventaire d’un article à l’aide des méthodes FIFO ou d’évaluation du coût moyen, lorsque les coûts article sont modifiés pour des motifs autres que les transactions.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: null
ms.search.form: '9297, 5845, 30,'
ms.date: 05/24/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="about-item-types"></a>À propos des types d’articles

Dans le champ **Type** de la page **Fiche article**, vous pouvez sélectionner ce pourquoi l’article est utilisé dans votre activité, ce qui a une incidence sur le niveau de gestion que vous pouvez exercer sur l’article en inventaire. Le tableau suivant répertorie et décrit les trois types d’éléments disponibles.

|Option|Objectif courant|
|------|-----------|
|Inventaire|Les objets physiques, tels que les vélos, les téléphones et les bureaux, pour lesquels vous souhaitez pouvoir utiliser tous les processus d'inventaire. Les articles en inventaire peuvent également inclure des éléments non physiques, tels que des licences logicielles et des abonnements, si les éléments ont des numéros d’identification, tels que des numéros de série. Vous pouvez suivre entièrement les valeurs et la disponibilité des articles dans l’inventaire.|
|Hors inventaire|En règle générale, les articles hors inventaire sont des objets physiques, tels que des boulons ou des stylos, que votre entreprise consomme mais ne suit pas intégralement dans l'inventaire. Par exemple, parce que ce sont des articles qui ne coûtent pas cher et qu’ils ne sont utilisés qu’en interne.|
|Service|Une unité de temps de travail, telle qu'une heure de conseil, pour la prise en charge limitée de l'activité.|

> [!NOTE]
> Les types **Service** et **Hors inventaire** ne permettent pas de suivre les quantités et les valeurs d'inventaire. Seuls les types de transaction articles et fonctionnalités sélectionnés sont pris en charge. Le tableau suivant répertorie les fonctions que les trois types d’article prennent en charge.

|Type d'article|Ventes|Achats|Consommation de projet|Consommation de service|Consommation d'assemblage|Production Consommation|Résultat d'assemblage|Production|Transfert emplacement|Inventaire physique|Réévaluation de l'inventaire|Évaluation stock|Traçabilité|Réservation|Entreposage|Planific.|Planification commande|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Stocks|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
|Hors inventaire|Oui|Oui|Oui|Oui|Oui|Oui|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|Oui|
|Service|Oui|Oui|Oui|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|N°|Oui|

## <a name="costing-methods-for-types-of-items"></a>Modes évaluation stock pour les types d’articles

Lorsque vous reportez des transactions d'inventaire, les changements de quantité et de valeur en inventaire sont enregistrés dans les écritures du grand livre d'articles et les écritures valeur, respectivement.

Vous enregistrez le coût des articles en inventaire dans le champ **Coût indiqué (réel)** sur la page **Écritures valeur**. Lorsque vous rapprochez l’écriture dans le grand livre, le coût s’affiche dans le champ **Coût reporté au GL**. Pour en savoir plus sur l’évaluation du coûts de l'inventaire, voir [Détails de conception : Évaluation du coût de l'inventaire](design-details-inventory-costing.md).

Pour les articles hors inventaire et de service, le coût est enregistré dans le champ **Coût indiqué (avant bal. Stock)** sur la page **Écritures valeur**. Pour les articles hors stock et de service, le coût est spécifié sur les documents et journaux de vente, d’assemblage et de production. Spécifiez le coût par défaut dans le champ **Coût unitaire** sur les pages **Fiche article** et **Unité de stock**. Les coûts de ces types d’articles ne sont pas rapprochés avec le grand livre.

## <a name="catalog-and-service-items"></a>Articles de catalogue et de service

Configurez les articles que vous offrez à vos clients mais que vous ne gérer pas dans le système jusqu’à ce que vous vendre comme des articles de catalogue. Bien que les articles du catalogue soient similaires aux articles ordinaires du type **Non-inventaire** à cet égard, ne confondez pas les deux car il existe des différences. Pour en savoir plus, consultez [Utiliser les articles catalogue](inventory-how-work-nonstock-items.md).

Les articles clients pour lesquels vous effectuez un service, par exemple une imprimante, sont appelés des articles de service. Les articles de service n'ont rien à voir avec des articles courants ou de catalogue. Cependant, les composantes de service peuvent être des articles courants. Pour plus d’informations, voir [Configurer les articles de service et les composantes article de service](service-how-setup-service-items.md).

## <a name="see-also"></a>Voir aussi .

[Enregistrement des nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de stock](inventory-setup-inventory.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
