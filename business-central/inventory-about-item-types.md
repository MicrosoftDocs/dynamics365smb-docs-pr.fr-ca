---
title: Comprendre les types d'articles | Microsoft Docs
description: Vous pouvez ajuster l'évaluation de l'inventaire d'un article à l'aide des méthodes FIFO ou d'évaluation coût moyen, par exemple, lorsque les coûts article sont modifiés pour des motifs autres que les transactions.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: a262975a6797e0b9addc4990c4aba98a9ca467b2
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5382439"
---
# <a name="about-item-types"></a>À propos des types d'articles
Dans le champ **Type** de la page **Fiche article**, vous pouvez sélectionner ce pourquoi l'article est utilisé dans votre activité et donc la manière dont il est géré dans le système. Trois options existent :

|Option|Objectif courant|
|------|-----------|
|Stocks|Une unité réelle, telle qu'une bicyclette, pour la prise en charge totale de l'activité.|
|Hors inventaire|Une unité réelle, par exemple un boulon, pour une prise en charge limitée de l'activité, par exemple, car l'article est uniquement utilisé en interne et a un coût bas.|
|Service|Une unité de temps de travail, telle qu'une heure de conseil, pour la prise en charge limitée de l'activité.|

Le type **Inventaire** implique un suivi complet de la quantité et de la valeur de l'inventaire. Par conséquent, tous les types de transaction article sont pris en charge, et les articles de type Inventaire peuvent être utilisés avec toutes les fonctionnalités de gestion des articles.

Les types **Service** et **Hors inventaire** ne requièrent pas le suivi de la quantité et de la valeur de l'inventaire. Par conséquent, seuls les types de transaction articles et fonctionnalités sélectionnés sont pris en charge.

Les trois types d'article prennent en charge les fonctions suivantes respectivement.

|Type d'article|Vente|Achats|Consommation de projet|Consommation de service|Consommation d'assemblage|Production Consommation|Résultat d'assemblage|Production|Transfert emplacement|Inventaire physique|Réévaluation de l'inventaire|Évaluation stock|Traçabilité|Réservation|Entreposage|Planification|
|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|-|
|Stocks|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|Oui|
|Hors inventaire|Oui|Oui|Oui|Oui|Oui|Oui|Non|Non|Non|Non|Non|Non|Non|Non|Non|Non|
|Service|Oui|Oui|Oui|Non|Non|Non|Non|Non|Non|Non|Non|Non|Non|Non|Non|Non|

## <a name="costing-methods-for-types-of-items"></a>Modes évaluation stock pour les types d'articles
Lorsque vous reportez des transactions d'inventaire, les changements de quantité et de valeur en inventaire sont enregistrés dans les écritures du grand livre d'articles et les écritures valeur, respectivement. 

Pour les articles d'inventaire, le coût est reporté dans le champ **Coût indiqué (réel)** sur la page **Écritures valeur**, et lorsqu'il est rapproché du grand livre, le coût sera indiqué dans le champ **Coût reporté au GL**. Pour plus d'informations, voir [Détails de conception : Évaluation stock](design-details-inventory-costing.md).

Pour les articles hors inventaire et de service, le coût est enregistré dans le champ **Coût indiqué (avant bal. stock)** sur la page **Écritures valeur**. Pour les articles hors inventaire et de service, le coût est spécifié sur les documents et journaux de vente, d'assemblage et de production. Le coût par défaut peut être spécifié dans le champ **Coût unitaire** sur les pages **Fiche article** et **Unité de stock**. Les coûts de ces types d'articles ne sont pas rapprochés du grand livre. 

## <a name="catalog-and-service-items"></a>Articles de catalogue et de service
Les articles que vous offrez à vos clients mais que vous ne souhaitez pas gérer dans le système jusqu'à ce que vous commenciez à les vendre peuvent être définis comme des articles de catalogue. Les articles de catalogue ne doivent pas être confondus avec les articles normaux de type Hors inventaire. Pour en savoir plus, voir [Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md).

Les articles des clients pour lesquels vous effectuez un service, par exemple une imprimante, sont appelés des articles de service. Les articles de service n'ont rien à voir avec des articles courants ou de catalogue. Cependant, les composantes de service peuvent être des articles courants. Pour plus d'informations, voir [Configurer les articles de service et les composantes article de service](service-how-setup-service-items.md).

## <a name="see-also"></a>Voir aussi
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de stock](inventory-setup-inventory.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Stock](inventory-manage-inventory.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]