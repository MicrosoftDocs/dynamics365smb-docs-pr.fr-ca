---
title: "Détails de conception - Intégration avec l'inventaire | Microsoft Docs"
description: "Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: dda69814c0f8b2a21a3e927e2e357817090549f4
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="design-details-integration-with-inventory"></a>Détails de conception : intégration avec l'inventaire
Les modules Warehouse Management et Inventaire interagissent dans l'inventaire physique et dans l'ajustement de l'inventaire ou de l'entrepôt.  
  
## <a name="physical-inventory"></a>Inventaire physique  
 La page **Journal inventaire physique entrepôt** est utilisée avec la page **Journal inventaire physique** pour tous les emplacements entrepôts avancés. L'inventaire au niveau de la zone est calculé, et une liste imprimée est donnée au magasinier. La liste indique les articles dans lesquels les emplacements doivent être comptabilisés.  
  
 L'employé d'entrepôt entre la quantité comptée sur la page **Journal inventaire physique entrepôt** puis reporte le journal.  
  
 Si la quantité comptée est supérieure à la quantité indiquée sur la ligne journal, un mouvement est reporté pour cette différence à partir de la zone d'ajustement par défaut vers la zone dans laquelle les articles ont été comptés. Cela augmente la quantité dans la zone ayant fait l'objet du comptage et diminue la quantité dans la zone d'ajustement par défaut.  
  
 Si la quantité comptée est inférieure à la quantité indiquée sur la ligne journal, un mouvement pour cette différence est reporté à partir de la zone ayant fait l'objet du comptage vers la zone d'ajustement par défaut. Cela diminue la quantité dans la zone ayant fait l'objet du comptage et augmente la quantité dans la zone d'ajustement par défaut.  
  
 Dans les configurations d'entrepôt avancées, la valeur du champ **Quantité (calculée)** est extraite à partir des écritures article et celle du champ **Quantité (inventaire physique)** est extraite à partir des écritures entrepôt, à l'exception du contenu de la zone d'ajustement. Le champ **Quantité** spécifie la différence entre les deux premiers champs, qui doit être égale au contenu de l'emplacement ajustement.  
  
 Lorsque vous reportez le journal inventaire physique, l'inventaire et la zone d'ajustement par défaut sont mis à jour.  
  
### <a name="warehouse-adjustments-to-the-item-ledger"></a>Ajustements entrepôt dans le grand livre article  
 Vous utilisez la page **Journal article** et la fonction **Calculer ajustement entrepôt** pour ajuster l'inventaire dans le grand livre article conformément à un ajustement qui a été apporté sur la quantité d'un article dans une zone de stockage. Pour créer un lien entre l'inventaire et l'entrepôt, vous devez définir une zone d'ajustement par défaut par emplacement.  
  
 La zone d'ajustement par défaut enregistre les articles dans l'entrepôt lorsque vous reportez une augmentation dans l'inventaire. Toutefois, si vous reportez une diminution, la quantité sur la zone par défaut est également diminuée. Dans les deux cas, des écritures du grand livre d'articles et des écritures entrepôt sont créées.  
  
> [!NOTE]  
>  La zone d'ajustement n'est pas incluse dans le calcul de disponibilité.  
  
 Si vous souhaitez ajuster le contenu de la zone, vous pouvez utiliser le journal article entrepôt, à partir duquel vous pouvez saisir le numéro d'article, le code de zone, le code de zone et la quantité que vous voulez ajuster.  
  
 Si vous saisissez une quantité positive et reportez la ligne, l'inventaire enregistré dans la zone augmente, et la quantité de la zone d'ajustement par défaut diminue en conséquence.  
  
## <a name="see-also"></a>Voir aussi  
 [Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)   
 [Détails de conception : disponibilité dans l'entrepôt](design-details-availability-in-the-warehouse.md)
