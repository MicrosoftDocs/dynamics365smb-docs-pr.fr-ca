---
title: "Détails de conception - Intégration avec l'inventaire | Microsoft Docs"
description: "Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 00a12f3f2203ed3b22cfee1af6aa8f155ca5fe4b
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="design-details-integration-with-inventory"></a>Détails de conception : intégration avec l'inventaire
Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt.  
  
## <a name="physical-inventory"></a>Inventaire physique  
 La fenêtre **Feuille inventaire entrepôt** est utilisée avec la fenêtre **Feuille inventaire** pour tous les entrepôts avancés. L'inventaire au niveau de la zone est calculé, et une liste imprimée est donnée au magasinier. La liste indique les articles dans lesquels les emplacements doivent être comptabilisés.  
  
 Le magasinier entre la quantité comptée dans la fenêtre **Feuille inventaire entrepôt** puis valide la feuille.  
  
 Si la quantité comptée est supérieure à la quantité indiquée sur la ligne journal, un mouvement est reporté pour cette différence à partir de la zone d'ajustement par défaut vers la zone dans laquelle les articles ont été comptés. Cela augmente la quantité dans la zone ayant fait l'objet du comptage et diminue la quantité dans la zone d'ajustement par défaut.  
  
 Si la quantité comptée est inférieure à la quantité indiquée sur la ligne journal, un mouvement pour cette différence est reporté à partir de la zone ayant fait l'objet du comptage vers la zone d'ajustement par défaut. Cela diminue la quantité dans la zone ayant fait l'objet du comptage et augmente la quantité dans la zone d'ajustement par défaut.  
  
 Dans les configurations d'entrepôt avancées, la valeur du champ **Quantité (calculée)** est extraite à partir des écritures article et celle du champ **Quantité (inventaire physique)** est extraite à partir des écritures entrepôt, à l'exception du contenu de la zone d'ajustement. Le champ **Quantité** spécifie la différence entre les deux premiers champs, qui doit être égale au contenu de l'emplacement ajustement.  
  
 Lorsque vous reportez le journal inventaire physique, l'inventaire et la zone d'ajustement par défaut sont mis à jour.  
  
### <a name="warehouse-adjustments-to-the-item-ledger"></a>Ajustements entrepôt dans le grand livre article  
 Vous utilisez la fenêtre **Feuille article** et la fonction **Calculer ajustement entrepôt** pour ajuster le stock dans l'écriture article conformément à ajustement qui a été apporté sur la quantité d'un article dans un emplacement entrepôt. Pour créer un lien entre l'inventaire et l'entrepôt, vous devez définir une zone d'ajustement par défaut par emplacement.  
  
 La zone d'ajustement par défaut enregistre les articles dans l'entrepôt lorsque vous reportez une augmentation dans l'inventaire. Toutefois, si vous reportez une diminution, la quantité sur la zone par défaut est également diminuée. Dans les deux cas, des écritures du grand livre d'articles et des écritures entrepôt sont créées.  
  
> [!NOTE]  
>  La zone d'ajustement n'est pas incluse dans le calcul de disponibilité.  
  
 Si vous souhaitez ajuster le contenu de la zone, vous pouvez utiliser le journal article entrepôt, à partir duquel vous pouvez saisir le numéro d'article, le code de zone, le code de zone et la quantité que vous voulez ajuster.  
  
 Si vous saisissez une quantité positive et reportez la ligne, l'inventaire enregistré dans la zone augmente, et la quantité de la zone d'ajustement par défaut diminue en conséquence.  
  
## <a name="see-also"></a>Voir aussi  
 [Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)   
 [Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md)
