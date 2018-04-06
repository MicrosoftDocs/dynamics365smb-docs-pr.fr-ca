---
title: "Détails de conception - tableau d'affectation de planification | Microsoft Docs"
description: "Cette rubrique donne un aperçu de ce qui se produit lorsque vous modifiez la planification d'un article."
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
ms.openlocfilehash: e7591196c3335f7640d37151054b22dd687b36e8
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-planning-assignment-table"></a>Détails de conception : tableau d'affectation de planification
Tous les articles doivent être planifiés. Cependant, il n'existe aucune raison de calculer une planification pour un article à moins qu'il n'y ait eu une modification de la configuration de l'offre ou de la demande depuis la dernière fois qu'un plan a été calculé.  
  
Si l'utilisateur a saisi un document de vente ou en a modifié une existante, il existe un motif au recalcul de la planification. Les autres motifs sont notamment une modification de prévision ou la quantité de stock de sécurité souhaitée. La modification de nomenclatures lorsque vous ajoutez ou supprimez une composante indique très probablement une modification, mais pour la composante uniquement.  
  
Pour plusieurs emplacements, l'affectation se fait au niveau de l'article par combinaison d'emplacements. Si, par exemple, un document de vente a été créée à un seul emplacement, le programme affecte l'article à cet emplacement spécifique pour la planification.  
  
La raison de la sélection d'articles pour la planification est une question de performances système. Si aucune modification du motif demande-approvisionnement d'un article n'a été apportée, le système de planification ne propose aucune action à effectuer. Sans l'affectation de planification, le système devrait effectuer les calculs pour tous les articles afin de déterminer quoi planifier, et cela purgerait des ressources du système.  
  
La table **Affectation planning** contrôle les événements d'offre et de demande et affecte les articles appropriés de façon à les planifier. Les événements suivants sont contrôlés :  
  
* Nouveau document de vente, bon de commande, bon de production, ordre d'assemblage ou ordre de transfert, nouvelle prévision ou composante.  
* Modification d'un article, d'une quantité, d'un emplacement, d'une variante, ou d'une date sur un document de vente, d'une prévision, d'une composante, d'un bon de commande, d'un bon de production, d'un ordre d'assemblage ou d'un ordre de transfert.  
* Annulation d'un document de vente, d'une prévision, d'une composante, d'un bon de commande, d'un bon de production, d'un ordre d'assemblage ou d'un ordre de transfert.  
* Consommation d'autres articles que planifiés.  
* Production d'autres articles que planifiés.  
* Modifications non planifiées dans l'inventaire.  
  
Pour ces déplacements directs de demande-approvisionnement, le système de suivi de commande et de messages d'action gère la table Affectation de planification et indique un motif de planification comme message d'action.  
  
Les modifications suivantes dans les données de base peuvent également provoquer un déséquilibre de planification :  
  
* Modification de l'état sur Certifié dans l'en-tête de la nomenclature de production (pour tous les articles utilisant cet en-tête).  
* Ligne supprimée (article enfant).  
* Modification de l'état sur Certifié dans l'en-tête itinéraire (pour tous les articles avec cette itinéraire).  
* Modifications des champs suivants de la fiche article.  
* Quantité du stock de sécurité ou délai de sécurité.  
* Délai de réapprovisionnement.  
* Point de commande.  
* N° de nomenclature de production (et tous les enfants de l'ancienne référence de nomenclature).  
* N° procédure  
* Méthode de réapprovisionnement.  
  
Dans ces cas, une nouvelle fonction, Gestion d'affectation de planification, met à jour la table et indique le motif de planification Solde période.  
  
Les modifications suivantes n'entraînent pas une affectation de planification :  
  
* Calendriers  
* Autres paramètres de planification sur la fiche article  
  
Lors du calcul d'un MPS ou d'un MRP, les restrictions suivantes s'appliquent :  
  
* PDP : Le système de planification vérifie que l'article indique une prévision de production ou un document de vente. Sinon, l'article n'est pas inclus dans le planning.  
* MRP : si le système de planification détecte que l'article est réapprovisionné par une ligne planification PDP ou une commande approvisionnement PDP, l'article sera laissé en dehors de la planification. Toutefois, toute demande des composants pertinents est incluse.  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : transferts de planification](design-details-transfers-in-planning.md)   
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)  

