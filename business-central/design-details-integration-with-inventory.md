---
title: Détails de conception - Intégration avec l’inventaire
description: Les zones d’affectation Warehouse Management et Inventory interagissent dans l’inventaire physique et dans l’ajustement d’inventaire ou entrepôt.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/15/2021
ms.author: bholtorf
---
# Détails de conception : intégration avec l'inventaire

Les fonctionnalités Warehouse Management et Inventory interagissent dans l’inventaire physique et dans l’ajustement d’inventaire ou entrepôt.  

## Inventaire  

La page **Journal inventaire physique entrepôt** est utilisée avec la page **Journal inventaire physique** pour tous les emplacements entrepôts avancés. L'inventaire au niveau de la zone est calculé, et une liste imprimée est donnée au magasinier. La liste indique les articles dans lesquels les emplacements doivent être comptabilisés.  
  
L'employé d'entrepôt entre la quantité comptée sur la page **Journal inventaire physique entrepôt** puis reporte le journal.  
  
Si la quantité comptée est supérieure à la quantité indiquée sur la ligne journal, un mouvement est reporté pour cette différence à partir de la zone d'ajustement par défaut vers la zone dans laquelle les articles ont été comptés. Cela augmente la quantité dans la zone ayant fait l'objet du comptage et diminue la quantité dans la zone d'ajustement par défaut.  
  
Si la quantité comptée est inférieure à la quantité indiquée sur la ligne journal, un mouvement pour cette différence est reporté à partir de la zone ayant fait l'objet du comptage vers la zone d'ajustement par défaut. Cela diminue la quantité dans la zone ayant fait l'objet du comptage et augmente la quantité dans la zone d'ajustement par défaut.  
  
Dans les configurations d'entrepôt avancées, la valeur du champ **Quantité (calculée)** est extraite à partir des écritures article et celle du champ **Quantité (inventaire physique)** est extraite à partir des écritures entrepôt, à l'exception du contenu de la zone d'ajustement. Le champ **Quantité** spécifie la différence entre les deux premiers champs, qui doit être égale au contenu de l'emplacement ajustement.  
  
Lorsque vous reportez le journal inventaire physique, l'inventaire et la zone d'ajustement par défaut sont mis à jour.  

[!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]
  
## Ajustements d’entrepôt dans le grand livre article  

Vous utilisez la page **Journal article** et la fonction **Calculer ajustement entrepôt** pour ajuster l'inventaire dans le grand livre article conformément à un ajustement qui a été apporté sur la quantité d'un article dans une zone de stockage. Pour créer un lien entre l'inventaire et l'entrepôt, vous devez définir une zone d'ajustement par défaut par emplacement.  
  
La zone d'ajustement par défaut enregistre les articles dans l'entrepôt lorsque vous reportez une augmentation dans l'inventaire. Toutefois, si vous reportez une diminution, la quantité sur la zone par défaut est également diminuée. Dans les deux cas, des écritures du grand livre d'articles et des écritures entrepôt sont créées.  
  
> [!NOTE]  
> Les calculs d’inventaire n’incluent pas la zone d’ajustement.  
  
Pour ajuster le contenu de la zone, utilisez un journal article entrepôt, à partir duquel vous pouvez saisir le numéro d’article, le code d’emplacement, le code de zone et la quantité que vous voulez ajuster.  
  
Si vous saisissez une quantité positive et reportez la ligne, l'inventaire enregistré dans la zone augmente, et la quantité de la zone d'ajustement par défaut diminue en conséquence.  
  
## Voir aussi  

[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)  
[Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]