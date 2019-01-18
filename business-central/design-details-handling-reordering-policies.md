---
title: "Détails de conception - Gestion des méthodes de réapprovisionnement | Microsoft Docs"
description: "Aperçu des tâches pour définir une méthode de réapprovisionnement dans la planification des approvisionnements."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 11/14/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: caf7cf5afe370af0c4294c794c0ff9bc8ff4c31c
ms.openlocfilehash: 42fc4a95c572f3afecc3b3a76ba987edd1fdd011
ms.contentlocale: fr-ca
ms.lasthandoff: 11/22/2018

---
# <a name="design-details-handling-reordering-policies"></a>Détails de conception : gestion des méthodes de réapprovisionnement
Pour qu'un article participe à la planification des approvisionnements, une méthode de regroupement doit être définie. Les quatre méthodes de réapprovisionnement disponibles sont les suivantes :  

* Qté fixe de commande.  
* Qté maximum  
* Ordre  
* Lot pour lot  

Les méthodes Qté fixe de commande et Qté maximum sont liées à la planification de l'inventaire. Bien que la planification de l'inventaire soit techniquement plus simple que la procédure de contrepartie, ces stratégies doivent coexister avec la contrepartie pas à pas de l'approvisionnement et du suivi de commande. Pour contrôler l'intégration entre les deux, et livrer la visibilité dans la logique de planification utilisée, des principes stricts régissent la façon dont les méthodes de réapprovisionnement sont traitées.  

## <a name="the-role-of-the-reorder-point"></a>Le rôle du point de commande
En plus de l'équilibrage général de la demande et de l'approvisionnement, le système de planification doit également surveiller les niveaux d'inventaire des articles affectés pour respecter les stratégies de réapprovisionnement définies.  

Un point de commande représente la demande lors d'un délai. Lorsque l'inventaire prévisionnel passe en dessous du niveau d'inventaire défini par le point de réapprovisionnement, il est temps de commander une plus grande quantité. Par ailleurs, l'inventaire doit diminuer progressivement et probablement atteindre zéro (ou le niveau d'inventaire de sécurité), jusqu'au moment du réapprovisionnement.  

Par conséquent, le système de planification suggère une commande d'approvisionnement planifiée en aval au moment où l'inventaire prévisionnel passe sous le point de réapprovisionnement.  

Le point de réapprovisionnement indique un certain niveau d'inventaire. Cependant, les niveaux d'inventaire peuvent changer de façon significative au cours de la plage de temps et, par conséquent, le système de planification doit constamment contrôler l'inventaire prévisionnel disponible.

## <a name="monitoring-the-projected-inventory-level-and-the-reorder-point"></a>Surveillance du niveau d'inventaire prévisionnel et du point de réapprovisionnement
L'inventaire est un type d'approvisionnement, mais pour la planification de l'inventaire, le système de planification différencie deux niveaux d'inventaire :  

* Inventaire prévisionnel  
* Inventaire disponible prévu  

### <a name="projected-inventory"></a>Inventaire projeté  
Normalement, l'inventaire prévisionnel est la quantité d'inventaire brut, y compris les demandes et approvisionnements du passé même s'ils n'ont pas été reportés, au début du processus de planification. Dans le futur, cela devient un niveau d'inventaire prévisionnel mobile qui est mis à jour par les quantités brutes d'un approvisionnement et d'une demande futurs parce que ceux-ci sont saisis suivant la planification (réservés ou affectés autrement).  

L'inventaire prévisionnel est utilisé par le système de planification pour contrôler le point de réapprovisionnement et pour déterminer la quantité de réapprovisionnement lorsque la méthode de réapprovisionnement Qté maximum est utilisée.  

### <a name="projected-available-inventory"></a>Inventaire disponible prévu  
L'inventaire prévisionnel disponible est la partie de l'inventaire prévisionnel qui est disponible à un moment donné pour honorer une demande. L'inventaire disponible prévu est utilisé par le moteur de planification lors du contrôle du niveau de stock de sécurité.  

L'inventaire disponible prévu est utilisé par le système de planification pour contrôler le niveau de stock de sécurité, parce que l'inventaire de sécurité doit toujours être disponible pour satisfaire une demande inattendue.  

### <a name="time-buckets"></a>Intervalles de planification  
Un contrôle strict de l'inventaire prévisionnel est crucial pour détecter le moment où le point de réapprovisionnement est atteint et pour calculer la quantité de commande correcte à l'aide de la stratégie de réapprovisionnement de la quantité maximum.  

Comme indiqué précédemment, le niveau d'inventaire prévisionnel est calculé au début de la période de planification. Il s'agit d'un niveau brut qui ne tient pas compte des réservations et des ventilations similaires. Pour contrôler ce niveau d'inventaire durant la séquence de planification, le système gère les changements cumulés sur une période de temps, une plage de temps. Le système garantit que la plage de temps est au moins d'un jour comme il s'agit de l'unité de temps la plus précise pour une demande ou un événement d'approvisionnement.  

### <a name="determining-the-projected-inventory-level"></a>Déterminer le niveau d'inventaire prévisionnel  
La séquence suivante décrit la manière dont le niveau d'inventaire prévisionnel est déterminé :  

* Lorsqu'un événement d'approvisionnement, tel qu'un bon de commande, a été totalement planifié, il augmente l'inventaire prévisionnel à sa date d'échéance.  
* Lorsqu'un événement de demande est entièrement satisfait, il ne diminue pas l'inventaire prévisionnel immédiatement. Au lieu de cela, il reporte un rappel de diminution. Il s'agit d'un enregistrement interne qui contient la date et la quantité de la contribution à l'inventaire prévisionnel.  
* Lorsqu'un événement d'approvisionnement ultérieur est planifié et placé sur la chronologie, les rappels de diminution reportés sont examinés un à un jusqu'à la date d'approvisionnement planifiée, tout en mettant à jour l'inventaire prévisionnel. Lors de ce processus, le niveau du point de réapprovisionnement du rappel interne d'augmentation peut être atteint ou dépassé.  
* Si une nouvelle commande approvisionnement est créée, le système vérifie si elle est saisie avant l'approvisionnement actif. Si c'est le cas, le nouvel approvisionnement devient l'approvisionnement actif et la procédure d'équilibrage reprend depuis le début.  

Voici une illustration graphique de ce principe :  

![Déterminer le niveau d'inventaire prévisionnel](media/nav_app_supply_planning_2_projected_inventory.png "Déterminer le niveau d'inventaire prévisionnel")  

1. L'approvisionnement **Sa** de 4 (fixe) ferme la demande **Da** de -3.  
2. CloseDemand : créez un rappel de baisse de -3 (pas affiché).  
3. L'approvisionnement **Sa** est fermé avec un excédent de 1 (plus aucune demande n'existe).  

     Cela augmente le niveau d'inventaire prévisionnel à +4, alors que l'inventaire **disponible** prévisionnel devient -1.  

4. L'approvisionnement suivant **Sb** de 2 (une autre commande) a déjà été placé dans la chronologie.  
5. Le système vérifie s'il y a des rappels de sortie précédant **Sb** (comme il n'y en a pas, aucune action n'est effectuée).  
6. Le système ferme l'approvisionnement **Sb** (plus aucune demande n'existe)—A : en réduisant à 0 (annuler) ou B : en le laissant tel quel.  

     Cela entraîne l'augmentation du niveau de stock projeté (A : +0 => +4 or B : +2 = +6).  

7. Le système effectue un contrôle final : existe-t-il un rappel de diminution ? Oui, il y en a un en date du **Da**.  
8. Le système ajoute le rappel de diminution -3 au niveau d'inventaire prévisionnel, soit A : +4 -3 = 1 ou B : +6 -3 = +3.  
9. Dans le cas A, le système crée une commande programmée en aval qui commence à la date **Da**.  

     Dans le cas de B, le point de commande est atteint et aucune commande n'est créée.

## <a name="the-role-of-the-time-bucket"></a>Rôle de la plage de temps
L'objectif de la plage de temps est de collecter les événements de demande sur la page de temps de manière à effectuer une commande d'approvisionnement commune.  

Pour les méthodes de réapprovisionnement qui utilisent un point de réapprovisionnement, vous pouvez définir une plage de temps. Cela garantit que la demande dans la même période est accumulée avant d'évaluer l'impact sur l'inventaire prévisionnel et de vérifier si le point de réapprovisionnement a été atteint. Si le point de réapprovisionnement est passé, une nouvelle commande approvisionnement est programmée en aval à partir de la fin de la période définie par la plage de temps. Les plages de temps débutent à la date de début de la planification.  

Le concept de plage de temps reflète le processus manuel de vérification fréquente du niveau d'inventaire plutôt que pour chaque transaction. L'utilisateur doit définir la fréquence (plage de temps). Par exemple, l'utilisateur regroupe les besoins article d'un fournisseur pour passer une commande hebdomadaire.  

![Exemple de plage de temps dans la planification](media/nav_app_supply_planning_2_reorder_cycle.png "Exemple de plage de temps dans la planification")  

La plage de temps est généralement utilisée pour éviter un effet cascade. Par exemple, une ligne équilibrée de demande et d'approvisionnement dans laquelle une demande antérieure est annulée ou une nouvelle demande est créée. Le résultat est que chaque commande d'approvisionnement est reprogrammée (excepté la dernière).

## <a name="staying-under-the-overflow-level"></a>Rester sous le niveau de dépassement de capacité
Lors de l'utilisation des stratégies Qté maximum et Qté fixe de commande, le système de planification se concentre sur l'inventaire prévisionnel dans la plage de temps donnée uniquement. Cela signifie que le système de planification peut vous proposer l'approvisionnement superflu lorsqu'une demande négative ou des changements d'approvisionnement positifs se produisent en dehors de la plage de temps donnée. Si, pour cette raison, un approvisionnement superflu est proposé, le système de planification calcule la quantité à soustraire (ou supprimer) de l'approvisionnement pour éviter l'approvisionnement superflu. Cette quantité est appelée « niveau de dépassement de capacité ». Le dépassement de capacité est communiqué comme ligne de planification avec une action **Changer qté (diminuer)** ou **Annuler** et le message d'avertissement suivant :  

*Attention : l'inventaire prévisionnel [xx] est supérieur au niveau de dépassement de capacité [xx] à la date d'échéance [xx].*  

![Niveau de dépassement de capacité d'inventaire](media/supplyplanning_2_overflow1_new.png "Niveau de dépassement de capacité d'inventaire")  

###  <a name="calculating-the-overflow-level"></a>Calcul du niveau de dépassement de capacité  
Le niveau de dépassement de capacité est calculé de différentes manières en fonction de la configuration de planification.  

#### <a name="maximum-qty-reordering-policy"></a>Méthode de réapprovisionnement Qté maximum  
Niveau de dépassement de capacité = Inventaire maximum  

> [!NOTE]  
>  Si une quantité de commande minimum existe, elle sera ajoutée comme suit : Niveau de dépassement de capacité = Inventaire maximum + Quantité commande minimum.  

#### <a name="fixed-reorder-qty-reordering-policy"></a>Méthode de réapprovisionnement Qté fixe de commande  
Niveau de dépassement de capacité = Quantité de réappro. + Point de commande  

> [!NOTE]  
>  Si la quantité minimum commande est supérieure au point de commande, alors elle remplace comme suit : Niveau de dépassement de capacité = Quantité de réappro. + Quantité minimum commande  

#### <a name="order-multiple"></a>Commande multiple  
Si un multiple de commande existe, il ajuste le niveau de dépassement de capacité pour les deux méthodes de réapprovisionnement Qté maximum et Qté fixe de commande.  

###  <a name="creating-the-planning-line-with-overflow-warning"></a>Création de la ligne planification avec l'avertissement de dépassement capacité  
Lorsqu'un approvisionnement existant rend l'inventaire prévisionnel supérieur au niveau de dépassement de capacité à la fin d'une plage de temps, une ligne planification est créée. Pour avertir sur le potentiel approvisionnement superflu, la ligne de planification a un message d'avertissement, le champ **Accept Action Message** n'est pas sélectionné, et le message d'action est Cancel ou Change Qty.  

#### <a name="calculating-the-planning-line-quantity"></a>Calcul de la quantité pour la ligne planification  
Quantité pour la ligne planification = Quantité d'approvisionnement actif – (Inventaire prévisionnel – Niveau de dépassement de capacité)  

> [!NOTE]  
>  Comme pour toutes les lignes d'avertissement, les quantités maximales/minimales de commande ou les multiples de commande sont ignorés.  

#### <a name="defining-the-action-message-type"></a>Définir le type de message d'action  

-   Si la quantité de la ligne planification est supérieure à 0, le message d'action est Changer qté.  
-   Si la quantité de la ligne planification est égale ou inférieure à 0, le message d'action est Annuler  

#### <a name="composing-the-warning-message"></a>Composition du message d'avertissement  
Dans le cas d'un dépassement de capacité, la page **Éléments planification non suivis** affiche un message d'avertissement avec les informations suivantes :  

-   Le niveau d'inventaire prévisionnel qui a déclenché l'avertissement  
-   Niveau de dépassement de capacité calculé  
-   Date d'échéance d'un événement d'approvisionnement.  

Exemple : « L'inventaire prévisionnel 120 est supérieur au niveau de dépassement de capacité 60 au 28/01/11 »  

### <a name="scenario"></a>Scénario  
Dans ce scénario, un client modifie une document de vente de 70 à 40 pièces entre deux exécutions de planification. La fonction de dépassement de capacité intervient pour réduire l'achat qui a été proposé pour la quantité de ventes initiale.  

#### <a name="item-setup"></a>Configuration d'article  

|Politique réapprovisionnement|Qté maximum|  
|-----------------------|------------------|  
|Quantité maximum commande|100|  
|Point de réapprovisionnement|50|  
|Stocks|80|  

#### <a name="situation-before-sales-decrease"></a>Situation avant la sortie de vente  

|Evénement|Changer qté|Inventaire projeté|  
|-----------|-----------------|-------------------------|  
|Un jour|Aucun|80|  
|Vente|-70|10|  
|Fin de la plage de temps|Aucun|10|  
|Suggérer un nouveau bon de commande|+90|100|  

#### <a name="situation-after-sales-ddecrease"></a>Situation après la sortie de vente  

|Activer|Changer qté|Inventaire projeté|  
|------------|-----------------|-------------------------|  
|Un jour|Aucun|80|  
|Vente|-40|40|  
|Achat|+90|130|  
|Fin de la plage de temps|Aucun|130|  
|Proposer de réduire l'achat<br /><br /> achat de 90 à 60|-30|100|  

#### <a name="resulting-planning-lines"></a>Lignes planification résultantes  
 Une ligne planification (avertissement) est créée pour réduire l'achat de 30 pour passer de 90 à 60 pour conserver l'inventaire prévisionnel à 100 conformément au niveau de dépassement de capacité.  

![Planifier en fonction de niveau de dépassement de capacité](media/nav_app_supply_planning_2_overflow2.png "Planifier en fonction de niveau de dépassement de capacité")  

> [!NOTE]  
>  Sans la fonction Dépassement de capacité, aucun avertissement n'est créé si le niveau d'inventaire prévisionnel dépasse l'inventaire maximum. Cela pourrait entraîner un approvisionnement superflu de 30.

## <a name="handling-projected-negative-inventory"></a>Traitement de l'inventaire négatif prévisionnel
Le point de commande exprime la demande anticipée lors du délai de l'article. Lorsque le point de commande est passé, il est temps de commander plus. Mais l'inventaire prévisionnel doit être suffisamment élevé pour couvrir la demande jusqu'à ce que la nouvelle commande soit reçue. Par ailleurs, le stock de sécurité doit se charger des fluctuations de la demande jusqu'à un niveau de service ciblé.  

 Par conséquent, le système de planification considère comme une urgence si une demande future ne peut pas être servie à partir de l'inventaire prévisionnel, ou exprimé d'une autre manière, si l'inventaire prévisionnel devient négatif. Le système traite une telle exception en suggérant une nouvelle commande d'approvisionnement pour satisfaire la partie de la demande qui ne peut pas être satisfaite par l'inventaire ou un autre approvisionnement. La taille de la nouvelle commande approvisionnement ne prend pas en compte l'inventaire maximum ou la quantité de réapprovisionnement, ni les modificateurs de commande Qté maximum commande, Qté minimum commande et Multiple de commande. Au lieu de cela, elle reflète l'insuffisance exacte.  

 La ligne planification de ce type de commande approvisionnement affiche une icône d'avertissement Urgence, et des informations supplémentaires sont fournies lors de la recherche pour informer l'utilisateur de la situation.  

 Dans la figure suivante, l'approvisionnement D représente une commande d'urgence pour ajuster l'inventaire négatif.  

 ![Suggestion de planification d'urgence pour éviter un inventaire négatif](media/nav_app_supply_planning_2_negative_inventory.png "Suggestion de planification d'urgence pour éviter un inventaire négatif")  

1.  L'approvisionnement **A**, stock prévisionnel initial, est inférieur au point de commande.  
2.  Un approvisionnement programmé en aval est créé (**C**).  

     (Quantité = inventaire maximum – Niveau d'inventaire projeté)  
3.  L'approvisionnement **A** est clôturé par la demande **B** qui n'est pas totalement couverte.  

     (La demande **B** peut tenter de programmer l'approvisionnement C, mais cela ne se produira pas en raison du concept de plage de temps.)  
4.  Un nouvel approvisionnement (**D**) est créé pour couvrir la quantité restante sur demande **B**.  
5.  La demande **B** est fermée (création d'un rappel dans l'inventaire prévisionnel).  
6.  Le nouvel approvisionnement **D** est clôturé.  
7.  L'inventaire prévisionnel est vérifié ; le point de réapprovisionnement n'a pas été dépassé.  
8.  L'approvisionnement **C** est fermé (plus aucune demande n'existe).  
9. Vérification finale : aucun rappel restant de niveau d'inventaire.  

> [!NOTE]  
>  L'étape 4 indique la manière dont le système réagit dans les versions antérieures à Microsoft Dynamics NAV 2009 SP1.  

Cela conclut la description des principes centraux en relation avec la planification d'inventaire sur la base des méthodes de réapprovisionnement. La section suivante décrit les caractéristiques des quatre méthodes de réapprovisionnement prises en charge.

## <a name="reordering-policies"></a>Méthodes de réapprovisionnement
Les méthodes de réapprovisionnement définissent la quantité à commander lorsque l'article doit être réapprovisionné. Quatre différentes méthodes de réapprovisionnement existent.  

### <a name="fixed-reorder-qty"></a>Qté fixe de commande.
La méthode Qté fixe de commande est liée à la planification de l'inventaire des articles C courants (coûts d'inventaire faible, faible risque d'obsolescence, et/ou plusieurs articles). Cette méthode est généralement utilisée conjointement avec un point de commande reflétant la demande anticipée lors du délai de l'article.  

#### <a name="calculated-per-time-bucket"></a>Calculé par plage de temps  
Si le système de planification détecte que le point de commande a été atteint ou dépassé lors d'une plage de temps (cycle de commande), au-dessous ou sur le point de commande au début de la période et au-dessous ou sur le point de commande à la fin de la période, il propose de créer une commande d'approvisionnement pour la quantité nécessaire à recommander et ensuite la programme à partir de la première date à l'issue de la plage de temps.  

Le concept de point de commande délimité par un intervalle de planification réduit le nombre de suggestions d'approvisionnement. Cela reflète un processus manuel d'évaluation fréquente de l'entrepôt pour vérifier le contenu réel des différents emplacements.  

#### <a name="creates-only-necessary-supply"></a>Crée uniquement l'approvisionnement nécessaire  
Avant de proposer une commande approvisionnement pour répondre à un point de commande, le système de planification vérifie si l'approvisionnement a déjà été commandé pour être reçu dans le délai de réapprovisionnement de l'article. Si une commande approvisionnement existante résout le problème en amenant l'inventaire prévisionnel à un niveau égal ou supérieur au point de réapprovisionnement dans le délai, le système ne suggère pas de nouvelle commande approvisionnement.  

Les commandes approvisionnement qui sont créées spécifiquement pour répondre à un point de commande sont exclues de l'équilibrage ordinaire d'approvisionnement, et ne seront en aucun cas modifiées par la suite. Par conséquent, si un article utilisant un point de commande doit être éliminé (non réapprovisionné), il est recommandé d'étudier les commandes d'approvisionnement ouvertes manuellement ou de modifier la méthode de réapprovisionnement en Lot pour lot, le système peut alors réduire ou annuler l'approvisionnement superflu.  

#### <a name="combines-with-order-modifiers"></a>Associe avec les modificateurs d'ordre  
Les modificateurs de commande, qté minimum commande, qté maximum commande et multiple de commande, ne doivent pas jouer un grand rôle lorsque la stratégie de quantité fixe de commande est utilisée. Toutefois, le système de planification prend encore ces modificateurs en compte et diminue la quantité commande maximum spécifiée (et crée au moins deux approvisionnements pour atteindre la quantité commande totale), augmente la commande jusqu'à la quantité commande minimum spécifiée ou arrondit la quantité commandée pour répondre à un multiple spécifié de la commande.  

#### <a name="combines-with-calendars"></a>Combinaison avec des calendriers  
Avant de proposer une nouvelle commande d'approvisionnement pour répondre à un point de commande, le système de planification vérifie si la commande est programmée pour un jour chômé, en fonction des calendriers définis dans le champ **Code calendrier principal** des pages **Informations compagnie** et **Fiche emplacement**.  

Si la date programmée est un jour chômé, le système de planification déplace la commande en aval à la date de travail la plus proche. Cela peut entraîner une commande qui satisfait un point de commande mais ne pas satisfait une certaine demande spécifique. Pour une telle demande non soldée, le système de planification crée un approvisionnement supplémentaire.  

#### <a name="should-not-be-used-with-forecast"></a>Ne doit pas être utilisé avec la prévision  
Étant donné que la demande prévue est déjà exprimée au niveau du point de commande il n'est pas nécessaire d'inclure une prévision dans la planification d'un article à l'aide d'un point de commande. S'il est important de baser le programme sur une prévision, utilisez la stratégie lot pour lot.  

#### <a name="must-not-be-used-with-reservations"></a>Ne doit pas être utilisé avec les réservations  
Si l'utilisateur a réservé une quantité, par exemple une quantité dans l'inventaire, pour une certaine demande éloignée, la base de planification est dérangée. Même si le niveau d'inventaire projeté est acceptable par rapport au point de réapprovisionnement, les quantités peuvent ne pas être disponibles. Le système peut essayer de compenser cela en créant des commandes exception ; toutefois, il est conseillé de définir le champ Reserve sur Never pour les articles prévus comme utilisant un point de commande.

### <a name="maximum-qty"></a>Qté maximum
La stratégie de la quantité maximum permet de conserver l'inventaire à l'aide d'un point de réapprovisionnement.  

Tout ce qui concerne la stratégie Qté fixe de commande s'applique également à cette méthode. La seule différence est la quantité de l'approvisionnement proposé. Lors de l'utilisation de la stratégie de la quantité maximum, la quantité de réapprovisionnement est définie de façon dynamique en fonction du niveau d'inventaire prévisionnel et diffère donc généralement de celle de la stratégie commande à commande.  

#### <a name="calculated-per-time-bucket"></a>Calculé par plage de temps  
La quantité de réapprovisionnement est déterminée au moment (à la fin d'une plage de temps) où le système de planification détecte le que le point de réapprovisionnement a été dépassé. Le système mesure l'écart entre le niveau d'inventaire prévisionnel actuel et l'inventaire maximal spécifié. Cela constitue la quantité à recommander. Le système vérifie ensuite si l'approvisionnement a déjà été commandé ailleurs pour être reçu dans les délais et, si c'est le cas, réduit la quantité de la nouvelle commande d'approvisionnement des quantités déjà commandées.  

Le système s'assure que l'inventaire prévisionnel atteint au moins le niveau du point de réapprovisionnement (dans la cas où l'utilisateur oublierait de spécifier une quantité d'inventaire maximum).  

#### <a name="combines-with-order-modifiers"></a>Associe avec les modificateurs d'ordre  
En fonction de la configuration, il peut être préférable de combiner la stratégie de la quantité maximum avec des modificateurs de commande pour garantir une quantité de commande minimale ou de l'arrondir au nombre supérieur d'unités de mesure d'achat, ou de le diviser en davantage de lots comme défini par la quantité maximum commande.  

### <a name="combines-with-calendars"></a>Combinaison avec des calendriers  
Avant de proposer une commande d'approvisionnement pour répondre à un point de commande, le système de planification vérifie si la commande est programmée pour un jour chômé, en fonction des calendriers définis dans le champ **Code calendrier principal** des pages **Informations compagnie** et **Fiche emplacement**.  

Si la date programmée est un jour chômé, le système de planification déplace la commande en aval à la date de travail la plus proche. Cela peut entraîner une commande qui satisfait un point de commande mais ne pas satisfait une certaine demande spécifique. Pour une telle demande non soldée, le système de planification crée un approvisionnement supplémentaire.

### <a name="order"></a>Ordre
Dans un environnement de fabrication à la commande, un article est acheté ou produit pour couvrir exclusivement une demande spécifique. Généralement, il se rapporte aux articles A, et la motivation pour choisir cette méthode de réapprovisionnement de commande peut être que la demande n'est pas fréquente, le délai de production est insignifiant ou les attributs requis varient.  

Le programme crée un lien commande à commande, qui agit en tant que connexion préliminaire entre l'approvisionnement, une commande d'approvisionnement ou un inventaire, et la demande qu'il va traiter.  

Outre l'utilisation de la méthode de commande, le lien commande à commande peut s'appliquer lors de la planification, comme suit :  

* Lors de l'utilisation de la méthode de fabrication Prod. pour commande pour créer des bons de production de type multiniveau ou projet (la production avait besoin de composantes sur le même bon de production).  
* Lors de l'utilisation de la fonction Planification document de vente pour créer un bon de production à partir d'un document de vente.  

Même si une compagnie manufacturière se considère comme un environnement de fabrication à la commande, il peut être préférable d'utiliser une méthode de réapprovisionnement Lot pour lot si les articles sont des standards purs sans variation au niveau des attributs. Par conséquent, le système utilise l'inventaire non planifié et additionne uniquement les documents de vente ayant la même date de livraison ou faisant partie d'une plage de temps définie.  

#### <a name="order-to-order-links-and-past-due-dates"></a>Liens commande à commande et dates d'échéance passées  
Contrairement à la plupart des ensembles approvisionnement-demande, les commandes liées avec des dates d'échéance antérieures à la date début de la planification sont entièrement planifiées par le système. La raison commerciale de cette exception est que les ensembles spécifiques approvisionnement-demande doivent être synchronisés jusqu'à l'exécution. Pour plus d'informations sur la zone gelée qui s'applique à la plupart des types de demande-approvisionnement, voir [Détails de conception : traiter les commandes avant la date début de la planification](design-details-dealing-with-orders-before-the-planning-starting-date.md).

### <a name="lot-for-lot"></a>Lot pour lot
La méthode lot pour lot est la plus souple, parce que le système réagit uniquement à la demande réelle, de plus il agit sur une demande anticipée à partir de commandes de prévision et de commandes ouvertes, puis détermine la quantité commande en fonction de la demande. La méthode lot pour lot cible les articles A et B pour lesquels l'inventaire peut être accepté mais doit être évité.  

Par certains côtés, la méthode lot pour lot ressemble à la méthode de commande, mais elle a une approche générique des articles ; elle peut accepter des quantités en inventaire, et elle regroupe une demande et un approvisionnement correspondants dans des plages de temps définies par l'utilisateur.  

L'intervalle de planification est défini dans le champ **Intervalle de planification**. Le système travaille avec une plage de temps minimum d'un jour, car il s'agit de la plus petite unité de mesure de temps des événements d'offre et de demande dans le système (même si, dans la pratique, l'unité de mesure de temps des bons de production et des besoins de composantes peut être des secondes).  

La plage de temps fixe également des limites lorsqu'une commande d'approvisionnement existante doit être reprogrammée pour répondre à une demande donnée. Si l'approvisionnement se trouve dans la plage de temps, il est reprogrammé en entrée ou en sortie pour répondre à la demande. Sinon, s'il a lieu précédemment, il provoque une accumulation d'inventaire inutile et doit être annulé. S'il se trouve plus tard, une commande approvisionnement est créée à la place.  

Avec cette méthode, il est également possible de définir un stock de sécurité pour compenser les fluctuations possibles de l'approvisionnement, ou répondre à une demande soudaine.  

Étant donné que la quantité de la commande d'approvisionnement est basée sur la demande réelle, il peut sembler judicieux d'utiliser les modificateurs de commande : arrondir la quantité commandée pour répondre à un multiple spécifié de la commande (ou unité de mesure d'achat), augmenter la commande à une quantité de commande minimale spécifiée, ou réduire la quantité à la quantité maximale spécifiée (et ainsi créer deux ou plusieurs approvisionnements pour atteindre la quantité nécessaire totale).

## <a name="see-also"></a>Voir aussi  
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : tableau d'affectation de planification](design-details-planning-assignment-table.md)   
[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)   
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)

