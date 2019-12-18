---
title: 'Détails de conception : structure de report de traçabilité | Microsoft Docs'
description: Découvrez comment utiliser les écritures article comme principal opérateur des numéros traçabilité article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, item tracking, posting, inventory
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: a016863dc7dd5667074060a21e352ce4a56444cd
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2880170"
---
# <a name="design-details-item-tracking-posting-structure"></a>Détails de conception : structure de report de traçabilité
Pour s'aligner sur la fonctionnalité d'évaluation du coût de l'inventaire et obtenir une solution plus simple et plus robuste, les écritures du grand livre d'articles sont utilisées comme principal opérateur des numéros traçabilité.  
  
Les numéros traçabilité sur les entités réseau de commande et les entités réseau sans rapport avec les commandes sont spécifiés dans la table **Ecriture réservation** (T337). Des numéros traçabilité qui sont liés aux informations historiques sont récupérés directement à partir des écritures du grand livre d'articles qui sont associées à la transaction en question. Cela signifie que les écritures du grand livre d'articles reflètent la spécification de suivi d'article de la ligne de commande reportée.  
  
La page **Lignes traçabilité** extrait les informations de T337 et les écritures article et les affiche par le biais de la table temporaire, **Spécification traçabilité** (T336). T336 contient également les données temporaires dans la **page lignes traçabilité** pour les quantités de traçabilité article restant à facturer.  
  
## <a name="one-to-many-relation"></a>Relation un-à-plusieurs  
La table **Lien écriture article**, qui sert à lier une ligne document validée avec ses écritures comptables article correspondantes, est composée de deux parties principales :  
  
* Un pointeur vers la ligne document validée, le champ **N° ligne commande**. .  
* Un numéro de séquence pointant vers une écriture comptable article, le champ **N° écriture article**.  
  
La fonctionnalité du champ **N° écriture** existant, qui relie une écriture article à une ligne document reporté, gère la relation typique un à un lorsqu'aucun numéro traçabilité n'est indiqué sur la ligne document reportée. Si des numéros traçabilité existent, le champ **N° séquence** est laissé vide, et la relation un à plusieurs est gérée par la table **Lien écriture article**. Si la ligne document reportée possède des numéros traçabilité, mais n'est liée qu'à une seule écriture du grand livre d'articles, le champ **N° séquence** gère la relation, et le n° d'enregistrement est créé dans la table **Lien écriture article**.  
  
## <a name="codeunits-80-and-90"></a>Codeunits 80 et 90  
Pour répartir les écritures du grand livre d'articles lors du report, le code dans codeunit 80 et codeunit 90 est encerclé par des boucles qui s'exécutent à travers des variables de bilan temporaire global. Ce code appelle codeunit 22 avec une ligne journal article. Ces variables sont initialisées lorsque les numéros de suivi des articles existent pour la ligne document. Pour garder un code simple, cette structure de bouclage est toujours utilisée. Si aucun numéro traçabilité n'existe pour la ligne document, un enregistrement unique est inséré, et la boucle ne s'exécute qu'une fois.  
  
## <a name="posting-the-item-journal"></a>Report du journal article  
Des numéros traçabilité sont transférés via des écritures réservation en relation avec l'écriture du grand livre d'articles, et la répétition en boucle par l'intermédiaire des numéros traçabilité se produit dans le codeunit 22. Ce concept fonctionne de la même manière lorsqu'une ligne journal article est utilisée indirectement pour reporter un document de vente ou un bon de commande que lorsqu'une ligne journal article est utilisée directement. Lorsque la feuille article est utilisée directement, le champ **Code ligne source** pointe vers la ligne feuille article elle-même.  
  
## <a name="code-unit-22"></a>Unité de code 22  
Les Codeunits 80 et 90 bouclent l'appel du codeunit 22 lors du report de facture des numéros traçabilité et lors de la facturation des livraisons ou des réceptions existantes.  
  
Lors du report de quantité des numéros traçabilité, le codeunit 22 extrait les numéros traçabilité des écritures dans T337 liées au report. Ces écritures sont placées directement sur la ligne journal article.  
  
Codeunit 22 se répète en boucle via les numéros traçabilité et répartit le report dans les écritures du grand livre article correspondantes qui contiennent les numéros traçabilité. Les informations relatives aux écritures du grand livre d'articles qui sont créées sont renvoyées à T337 à l'aide d'un enregistrement temporaire T336, qui est appelé par une procédure dans le codeunit 22. Cette procédure est déclenchée lorsque le codeunit 22 a terminé son exécution car à ce stade, l'objet du codeunit 22 contient les informations. Lorsque l'enregistrement temporaire T336 est récupéré, les codeunits 80 et 90 créent des enregistrements dans le tableau **Lien écriture article** pour lier les écritures comptables article créées à l'expédition ou la ligne de réception créée. Codeunits 80 ou codeunit 90 convertit ensuite les enregistrements T336 temporaires en enregistrements réels T336 liés à la ligne en question. Cependant, cette conversion se produit uniquement si la ligne document reportée n'est pas supprimée, parce qu'elle n'est que partiellement reportée.  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : traçabilité](design-details-item-tracking.md)   
[Détails de conception : création de traçabilité](design-details-item-tracking-design.md)