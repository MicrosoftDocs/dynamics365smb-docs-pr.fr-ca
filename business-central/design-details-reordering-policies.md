---
title: Détails de conception - Méthodes de réapprovisionnement | Microsoft Docs
description: Cette rubrique donne un aperçu des méthodes de réapprovisionnement.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
redirect_url: design-details-handling-reordering-policies
ms.openlocfilehash: 1212c6f2f7e9da03a15c7fb39496d85869ef3e73
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "912322"
---
# <a name="design-details-reordering-policies"></a>Détails de conception : méthodes de réapprovisionnement
Les méthodes de réapprovisionnement définissent la quantité à commander lorsque l'article doit être réapprovisionné. Quatre différentes méthodes de réapprovisionnement existent.  

## <a name="fixed-reorder-qty"></a>Qté fixe de commande.
La méthode Qté fixe de commande est liée à la planification de l'inventaire des articles C courants (coûts d'inventaire faible, faible risque d'obsolescence, et/ou plusieurs articles). Cette méthode est généralement utilisée conjointement avec un point de commande reflétant la demande anticipée lors du délai de l'article.  

### <a name="calculated-per-time-bucket"></a>Calculé par plage de temps  
 Si le système de planification détecte que le point de commande a été atteint ou dépassé lors d'une plage de temps (cycle de commande), au-dessous ou sur le point de commande au début de la période et au-dessous ou sur le point de commande à la fin de la période, il propose de créer une commande d'approvisionnement pour la quantité nécessaire à recommander et ensuite la programme à partir de la première date à l'issue de la plage de temps.  

 Le concept de point de commande délimité par un intervalle de planification réduit le nombre de suggestions d'approvisionnement. Cela reflète un processus manuel d'évaluation fréquente de l'entrepôt pour vérifier le contenu réel des différents emplacements.  

### <a name="creates-only-necessary-supply"></a>Crée uniquement l'approvisionnement nécessaire  
 Avant de proposer une commande approvisionnement pour répondre à un point de commande, le système de planification vérifie si l'approvisionnement a déjà été commandé pour être reçu dans le délai de réapprovisionnement de l'article. Si une commande approvisionnement existante résout le problème en amenant l'inventaire prévisionnel à un niveau égal ou supérieur au point de réapprovisionnement dans le délai, le système ne suggère pas de nouvelle commande approvisionnement.  

 Les commandes approvisionnement qui sont créées spécifiquement pour répondre à un point de commande sont exclues de l'équilibrage ordinaire d'approvisionnement, et ne seront en aucun cas modifiées par la suite. Par conséquent, si un article utilisant un point de commande doit être éliminé (non réapprovisionné), il est recommandé d'étudier les commandes d'approvisionnement ouvertes manuellement ou de modifier la méthode de réapprovisionnement en Lot pour lot, le système peut alors réduire ou annuler l'approvisionnement superflu.  

### <a name="combines-with-order-modifiers"></a>Associe avec les modificateurs d'ordre  
 Les modificateurs de commande, qté minimum commande, qté maximum commande et multiple de commande, ne doivent pas jouer un grand rôle lorsque la stratégie de quantité fixe de commande est utilisée. Toutefois, le système de planification prend encore ces modificateurs en compte et diminue la quantité commande maximum spécifiée (et crée au moins deux approvisionnements pour atteindre la quantité commande totale), augmente la commande jusqu'à la quantité commande minimum spécifiée ou arrondit la quantité commandée pour répondre à un multiple spécifié de la commande.  

### <a name="combines-with-calendars"></a>Combinaison avec des calendriers  
 Avant de proposer une nouvelle commande d'approvisionnement pour répondre à un point de commande, le système de planification vérifie si la commande est programmée pour un jour chômé, en fonction des calendriers définis dans le champ **Code calendrier principal** des pages **Informations compagnie** et **Fiche emplacement**.  

 Si la date programmée est un jour chômé, le système de planification déplace la commande en aval à la date de travail la plus proche. Cela peut entraîner une commande qui satisfait un point de commande mais ne pas satisfait une certaine demande spécifique. Pour une telle demande non soldée, le système de planification crée un approvisionnement supplémentaire.  

### <a name="should-not-be-used-with-forecast"></a>Ne doit pas être utilisé avec la prévision  
 Étant donné que la demande prévue est déjà exprimée au niveau du point de commande il n'est pas nécessaire d'inclure une prévision dans la planification d'un article à l'aide d'un point de commande. S'il est important de baser le programme sur une prévision, utilisez la stratégie lot pour lot.  

### <a name="must-not-be-used-with-reservations"></a>Ne doit pas être utilisé avec les réservations  
 Si l'utilisateur a réservé une quantité, par exemple une quantité dans l'inventaire, pour une certaine demande éloignée, la base de planification est dérangée. Même si le niveau d'inventaire projeté est acceptable par rapport au point de réapprovisionnement, les quantités peuvent ne pas être disponibles. Le système peut essayer de compenser cela en créant des commandes exception ; toutefois, il est conseillé de définir le champ Reserve sur Never pour les articles prévus comme utilisant un point de commande.

## <a name="maximum-qty"></a>Qté maximum
La stratégie de la quantité maximum permet de conserver l'inventaire à l'aide d'un point de réapprovisionnement.  

Tout ce qui concerne la stratégie Qté fixe de commande s'applique également à cette méthode. La seule différence est la quantité de l'approvisionnement proposé. Lors de l'utilisation de la stratégie de la quantité maximum, la quantité de réapprovisionnement est définie de façon dynamique en fonction du niveau d'inventaire prévisionnel et diffère donc généralement de celle de la stratégie commande à commande.  

### <a name="calculated-per-time-bucket"></a>Calculé par plage de temps  
La quantité de réapprovisionnement est déterminée au moment (à la fin d'une plage de temps) où le système de planification détecte le que le point de réapprovisionnement a été dépassé. Le système mesure l'écart entre le niveau d'inventaire prévisionnel actuel et l'inventaire maximal spécifié. Cela constitue la quantité à recommander. Le système vérifie ensuite si l'approvisionnement a déjà été commandé ailleurs pour être reçu dans les délais et, si c'est le cas, réduit la quantité de la nouvelle commande d'approvisionnement des quantités déjà commandées.  

Le système s'assure que l'inventaire prévisionnel atteint au moins le niveau du point de réapprovisionnement (dans la cas où l'utilisateur oublierait de spécifier une quantité d'inventaire maximum).  

### <a name="combines-with-order-modifiers"></a>Associe avec les modificateurs d'ordre  
En fonction de la configuration, il peut être préférable de combiner la stratégie de la quantité maximum avec des modificateurs de commande pour garantir une quantité de commande minimale ou de l'arrondir au nombre supérieur d'unités de mesure d'achat, ou de le diviser en davantage de lots comme défini par la quantité maximum commande.  

### <a name="combines-with-calendars"></a>Combinaison avec des calendriers  
Avant de proposer une commande d'approvisionnement pour répondre à un point de commande, le système de planification vérifie si la commande est programmée pour un jour chômé, en fonction des calendriers définis dans le champ **Code calendrier principal** des pages **Informations compagnie** et **Fiche emplacement**.  

Si la date programmée est un jour chômé, le système de planification déplace la commande en aval à la date de travail la plus proche. Cela peut entraîner une commande qui satisfait un point de commande mais ne pas satisfait une certaine demande spécifique. Pour une telle demande non soldée, le système de planification crée un approvisionnement supplémentaire.

## <a name="order"></a>Ordre
Dans un environnement de fabrication à la commande, un article est acheté ou produit pour couvrir exclusivement une demande spécifique. Généralement, il se rapporte aux articles A, et la motivation pour choisir cette méthode de réapprovisionnement de commande peut être que la demande n'est pas fréquente, le délai de production est insignifiant ou les attributs requis varient.  

Le programme crée un lien commande à commande, qui agit en tant que connexion préliminaire entre l'approvisionnement, une commande d'approvisionnement ou un inventaire, et la demande qu'il va traiter.  

Outre l'utilisation de la méthode de commande, le lien commande à commande peut s'appliquer lors de la planification, comme suit :  

* Lors de l'utilisation de la méthode de fabrication Prod. pour commande pour créer des bons de production de type multiniveau ou projet (la production avait besoin de composantes sur le même bon de production).  
* Lors de l'utilisation de la fonction Planification document de vente pour créer un bon de production à partir d'un document de vente.  

Même si une compagnie manufacturière se considère comme un environnement de fabrication à la commande, il peut être préférable d'utiliser une méthode de réapprovisionnement Lot pour lot si les articles sont des standards purs sans variation au niveau des attributs. Par conséquent, le système utilise l'inventaire non planifié et additionne uniquement les documents de vente ayant la même date de livraison ou faisant partie d'une plage de temps définie.  

### <a name="order-to-order-links-and-past-due-dates"></a>Liens commande à commande et dates d'échéance passées  
Contrairement à la plupart des ensembles approvisionnement-demande, les commandes liées avec des dates d'échéance antérieures à la date début de la planification sont entièrement planifiées par le système. La raison commerciale de cette exception est que les ensembles spécifiques approvisionnement-demande doivent être synchronisés jusqu'à l'exécution. Pour plus d'informations sur la zone gelée qui s'applique à la plupart des types de demande-approvisionnement, voir [Détails de conception : traiter les commandes avant la date début de la planification](design-details-dealing-with-orders-before-the-planning-starting-date.md).

## <a name="lot-for-lot"></a>Lot pour lot
La méthode lot pour lot est la plus souple, parce que le système réagit uniquement à la demande réelle, de plus il agit sur une demande anticipée à partir de commandes de prévision et de commandes ouvertes, puis détermine la quantité commande en fonction de la demande. La méthode lot pour lot cible les articles A et B pour lesquels l'inventaire peut être accepté mais doit être évité.  

Par certains côtés, la méthode lot pour lot ressemble à la méthode de commande, mais elle a une approche générique des articles ; elle peut accepter des quantités en inventaire, et elle regroupe une demande et un approvisionnement correspondants dans des plages de temps définies par l'utilisateur.  

L'intervalle de planification est défini dans le champ **Intervalle de planification**. Le système travaille avec une plage de temps minimum d'un jour, car il s'agit de la plus petite unité de mesure de temps des événements d'offre et de demande dans le système (même si, dans la pratique, l'unité de mesure de temps des bons de production et des besoins de composantes peut être des secondes).  

La plage de temps fixe également des limites lorsqu'une commande d'approvisionnement existante doit être reprogrammée pour répondre à une demande donnée. Si l'approvisionnement se trouve dans la plage de temps, il est reprogrammé en entrée ou en sortie pour répondre à la demande. Sinon, s'il a lieu précédemment, il provoque une accumulation d'inventaire inutile et doit être annulé. S'il se trouve plus tard, une commande approvisionnement est créée à la place.  

Avec cette méthode, il est également possible de définir un stock de sécurité pour compenser les fluctuations possibles de l'approvisionnement, ou répondre à une demande soudaine.  

Étant donné que la quantité de la commande d'approvisionnement est basée sur la demande réelle, il peut sembler judicieux d'utiliser les modificateurs de commande : arrondir la quantité commandée pour répondre à un multiple spécifié de la commande (ou unité de mesure d'achat), augmenter la commande à une quantité de commande minimale spécifiée, ou réduire la quantité à la quantité maximale spécifiée (et ainsi créer deux ou plusieurs approvisionnements pour atteindre la quantité nécessaire totale).

## <a name="see-also"></a>Voir aussi  
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)
