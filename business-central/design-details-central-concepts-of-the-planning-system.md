---
title: 'Détails de conception : concepts centraux du système de planification'
description: Les fonctions de planification suggèrent des actions possibles pour l’utilisateur en fonction de la situation de l’offre/de la demande et des paramètres de planification des articles.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/24/2021
ms.author: edupont
ms.openlocfilehash: a9218bf8d8fa2c7f84b08380742df17bd7be7afe
ms.sourcegitcommit: 8ad79e0ec6e625796af298f756a142624f514cf3
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9605175"
---
# <a name="design-details-central-concepts-of-the-planning-system"></a>Détails de conception : concepts centraux du système de planification

Les fonctions de planification se trouvent dans un traitement en lot qui sélectionne d'abord les articles appropriés et la période à planifier. Puis, en fonction du code de bas niveau de chaque article (position nomenclature), le traitement en lot appelle un codeunit, qui calcule un programme d’approvisionnement en équilibrant les séries offre-demande et en suggérant des actions possibles que l'utlisateur doit prendre. Les actions suggérées apparaissent sous forme de lignes dans la feuille planification ou la feuille de réquisition.  

![Contenu de la page Feuilles planification.](media/design_details_central_concepts_of_the_planning_system_planning_worksheets.png "Contenu de la page Feuilles planification")  

Le gestionnaire d'une compagnie, par exemple un acheteur ou un gestionnaire de production, est censé être l'utilisateur du système de planification. Le système de planification aide l'utilisateur en effectuant les calculs étendus mais relativement simples d'une planification. L'utilisateur peut alors se consacrer à résoudre les problèmes plus difficiles, par exemple lorsque les choses diffèrent de la normale.  

Le système de planification est guidé par la demande prévue et réelle des clients, par exemple, les commandes prévisionnelles et les documents de vente. L'exécution du calcul de planification a pour effet que l'application suggère à l'utilisateur de prendre des mesures spécifiques concernant l'approvisionnement possible auprès des fournisseurs, des départements Production ou Assemblage, ou les transferts à partir d'autres entrepôts. Ces actions suggérées peuvent être de créer de nouvelles commandes d'approvisionnement, comme des bons de commande ou de production. S'il y a déjà des commandes d'approvisionnement, les actions suggérées peuvent être d'augmenter ou d'accélérer les commandes pour répondre à l'évolution de la demande.  

Un autre objectif du système de planification est de garantir que l'inventaire n'augmente pas inutilement. En cas de baisse de la demande, le système de planification suggère à l'utilisateur de reporter, de réduire ou d'annuler des commandes d'approvisionnement existantes.  

MRP et PDP, Calculer la variation nette planifiée et Calculer la planification régénérative sont toutes des fonctions dans un seul codeunit qui contient la logique de planification. Cependant, le calcul du programme d'approvisionnement implique différents sous-systèmes.  

Notez que le système de planification ne comprend aucune logique dédiée pour le nivellement de la capacité ou la planification précise. Par conséquent, un tel travail de planification s'effectue en tant que discipline séparée. Le manque d'intégration directe entre les deux domaines signifie également que des changements substantiels de capacité ou de calendrier obligeront à exécuter de nouveau la planification.  

## <a name="planning-parameters"></a>Paramètres de planification

Les paramètres de planification que l'utilisateur définit pour un article ou un groupe d'articles contrôlent les actions que le système de planification va proposer dans les différentes situations. Les paramètres de planification sont définis sur chaque fiche article pour contrôler quand, combien et comment réapprovisionner.  

Les paramètres de planification peuvent également être définis pour toute combinaison d'article, de variante et d'emplacement en définissant une unité de stock pour chaque combinaison nécessaire, puis en spécifiant différents paramètres.  

Pour plus d'informations, voir [Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md) et [Détails de conception : paramètres de planification](design-details-planning-parameters.md).  

## <a name="planning-starting-date"></a>Date début de la planification

Pour éviter un plan d'approvisionnement incorporant des commandes ouvertes dans le passé et proposant des actions potentiellement impossibles, le système de planification traite toutes les dates antérieures à la date début de la planification comme zone gelée dans laquelle les règles spécifiques suivantes s'appliquent :  

L'ensemble de l'offre et de la demande antérieur à la date début de la période de planification sera considéré comme faisant partie de l'inventaire ou comme étant livré.  

En d'autres termes, il est supposé que la planification pour le passé est exécutée conformément au planning donné.  

Pour plus d'informations, voir [Traiter les commandes avant la date début de la planification](design-details-balancing-demand-and-supply.md#dealing-with-orders-before-the-planning-starting-date).  

## <a name="dynamic-order-tracking-pegging"></a>Chaînage dynamique (Origine des besoins)

Le suivi de commande dynamique, avec sa création simultanée de messages d'action dans la feuille planification, ne fait pas partie du système de planification des approvisionnements dans [!INCLUDE[prod_short](includes/prod_short.md)]. Cette fonction lie, en temps réel, la demande et des montants qui pourraient les couvrir, chaque fois qu'une nouvelle demande ou un approvisionnement est créé ou modifié.  

Par exemple, si l’utilisateur entre ou modifie un document de vente, le système de chaînage dynamique recherche immédiatement l’approvisionnement approprié pour couvrir la demande. Cela peut être à partir de l'inventaire ou d'une commande d'approvisionnement prévue (telle qu'un bon de commande ou un bon de production). Lorsqu'une source d'approvisionnement est trouvée, le système crée un lien entre la demande et l'approvisionnement, et l'affiche sur des pages en lecture seule qui sont consultées depuis les lignes document associées. Lorsque l'approvisionnement approprié est introuvable, le système de suivi de commande dynamique crée des messages d'action dans la feuille de planification avec des suggestions de plan d'approvisionnement reflétant l'équilibre dynamique. Par conséquent, le système chaînage dynamique offre un système de planification de base qui peut être utile au gestionnaire et à d'autres rôles dans la chaîne d'approvisionnement interne.  

Par conséquent, le suivi de commande dynamique peut être considéré comme un outil qui aide l'utilisateur à déterminer s'il faut accepter les suggestions de commande d'approvisionnement. Du côté de l'approvisionnement, un utilisateur peut visualiser quelle demande a créé l'approvisionnement, et du côté de la demande, quel approvisionnement doit couvrir la demande.  

![Exemple de chaînage dynamique.](media/NAV_APP_supply_planning_1_dynamic_order_tracking.png "Exemple de chaînage dynamique")  

Pour plus d'informations, voir [Détails de conception : réservation, chaînage et message d'action](design-details-reservation-order-tracking-and-action-messaging.md).  

Dans les compagnies avec un faible flux d'articles et des structures de produits moins avancées, il peut être adéquat d'utiliser le suivi de commande dynamique comme principal moyen de planification de l'approvisionnement. Toutefois, dans des environnements où l'utilisation est plus intense, le système de planification doit être utilisé pour assurer une planification d'approvisionnement correctement équilibrée à tout moment.  

### <a name="dynamic-order-tracking-versus-the-planning-system"></a>Comparaison entre le chaînage dynamique et le système de planification

À première vue, il peut être difficile de différencier le système de planification du chaînage dynamique. Les deux fonctions affichent une sortie dans la feuille planification en suggérant les actions que le gestionnaire doit entreprendre. Toutefois, la manière dont cette production est produite diffère.  

Le système de planification traite l'ensemble de la configuration de demande et d'approvisionnement d'un article au travers de tous les niveaux de la hiérarchie de nomenclature, alors que le chaînage dynamique gère uniquement la situation de la commande qui l'a activée. Lors de l'équilibre de l'offre et de la demande, le système de planification crée des liens dans un mode de lots activé par l'utilisateur, alors que le suivi de commande dynamique crée les liens automatiquement et à la volée, chaque fois que l'utilisateur saisit une demande ou une offre dans l'application, comme un document de vente ou un bon de commande.  

Le chaînage dynamique crée des liens entre la demande et l'approvisionnement lorsque les données sont saisies, sur la base du principe premier arrivé, premier servi. Cela peut conduire du désordre dans les priorités. Par exemple, un document de vente saisi en premier, avec une date d'échéance au mois suivant, peut être lié à l'approvisionnement en inventaire, alors que le document de vente suivant à échéance le lendemain peut entraîner la création d'un bon de commande par un message d'action afin de le couvrir, comme illustré ci-dessous.  

![Exemple de chaînage dans la planification de l’approvisionnement 1.](media/NAV_APP_supply_planning_1_dynamic_order_tracking_graph.png "Exemple de chaînage dans la planification de l'approvisionnement 1")  

Par contre, le système de planification traite l'ensemble des demandes et approvisionnements pour un article spécifique, par ordre de priorité en fonction des dates d'échéance et des types de commande., c.-à-d., sur la base du principe de priorité selon les besoins. Il supprime les liens traçabilité commande qui ont été créés de façon dynamique et les rétablit en fonction de la priorité date d'échéance. Lorsque le système de planification a été exécuté, il a résolu tous les déséquilibres entre la demande et l'approvisionnement, comme illustré ci-dessous pour les mêmes données.  

![Exemple de chaînage dans la planification de l’approvisionnement 2.](media/NAV_APP_supply_planning_1_planning_graph.png "Exemple de chaînage dans la planification de l'approvisionnement 2")  

Après l'exécution de la planification, il ne reste aucun message d'action dans la table Écriture message d'action, parce qu'ils ont été remplacés par les actions suggérées dans la feuille planification  

Pour plus d’informations, voir [Liens traçabilité commande lors de la planification](design-details-balancing-demand-and-supply.md#seriallot-numbers-are-loaded-by-specification-level).  

## <a name="sequence-and-priority-in-planning"></a>Séquence et priorité de la planification

Lors de l'établissement d'un plan, la séquence des calculs est importante que le travail soit réalisé dans un délai raisonnable. En outre, la gestion des priorités des besoins et ressources joue un rôle important pour obtenir les meilleurs résultats.  

Le système de planification dans [!INCLUDE[prod_short](includes/prod_short.md)] est axé sur les demandes. Les articles de niveau supérieur doivent être planifiés avant les articles de bas niveau, car la planification des articles de niveau supérieur peut générer une demande supplémentaire d'articles de niveau inférieur. Ceci signifie, par exemple, que les emplacements de détail doivent être planifiés avant que les centres de distribution ne soient planifiés, car le programme pour un emplacement de détail peut inclure une demande supplémentaire du centre de distribution. Sur un niveau d’équilibre détaillé, cela signifie également qu’un document de vente ne doit pas déclencher une nouvelle commande d’approvisionnement si une commande d’approvisionnement déjà libérée peut couvrir le document de vente. De même, un approvisionnement portant un numéro de lot spécifique ne doit pas être affecté pour couvrir une demande générique si une autre demande requiert ce lot spécifique.  

### <a name="item-priority--low-level-code"></a>Priorité d’article / Code plus bas niveau

Dans un environnement de fabrication, la demande d'un article fini et pouvant être vendu a pour résultat une demande dérivée pour les composantes qui constituent l'article fini. La structure de nomenclature contrôle la structure des composantes et peut couvrir plusieurs niveaux d'articles semi-finis. La planification d'un article à un niveau va créer une demande dérivée pour des composantes au niveau suivant, etc. Cela peut entraîner une demande dérivée pour les articles achetés. Par conséquent, le système de planification planifie les articles par ordre de leur classement dans la hiérarchie de nomenclature totale, en commençant par les articles terminés vendables au niveau supérieur et en continuant dans la structure produit jusqu'aux articles du plus bas niveau (en fonction du code plus bas niveau.)  

![Planification des nomenclatures.](media/NAV_APP_supply_planning_1_BOM_planning.png "Planification des nomenclatures")  

Les chiffres indiquent dans quelle séquence le système fait des propositions pour les commandes d'approvisionnement au niveau supérieur, et en supposant que l’utilisateur accepte ces propositions, pour tous les articles au niveau inférieur également.  

Pour plus d'informations sur la fabrication, voir [Chargement des profils d'inventaire](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).  

#### <a name="optimizing-performance-for-low-level-calculations"></a>Optimisation des performances pour les calculs de plus bas niveau

Les calculs de code plus bas niveau peuvent avoir un impact sur les performances du système. Pour atténuer l’impact, vous pouvez désactiver **Calcul de code plus bas niveau dynamique** sur la page **Configuration de la fabrication**. Quand vous le faites, [!INCLUDE[prod_short](includes/prod_short.md)] vous suggère de créer une écriture file d'attente des travaux récurrente qui met à jour quotidiennement les codes de bas niveau. Vous pouvez vous assurer que la tâche s’exécutera en dehors des heures de travail en spécifiant une heure de début dans le champ **Date/heure de début au plus tôt**.

Vous pouvez également activer la logique qui accélère les calculs de code plus bas niveau en sélectionnant **Optimiser le calcul du code plus bas niveau** sur la page **Configuration de la fabrication**. 

> [!IMPORTANT]
> Si vous choisissez d’optimiser les performances, [!INCLUDE[prod_short](includes/prod_short.md)] utilise de nouvelles méthodes de calcul pour déterminer les codes plus bas niveau. Si vous disposez d’une extension qui repose sur les événements utilisés par les anciens calculs, l’extension peut cesser de fonctionner.   

### <a name="locations--transfer-level-priority"></a>Emplacements/priorité de niveau transfert

Les compagnies actives dans plusieurs emplacements peuvent être amenées à planifier chaque emplacement individuellement. Par exemple, le niveau de stock de sécurité d’un article et sa méthode de réapprovisionnement peuvent différer d’un emplacement à un autre. Dans ce cas, les paramètres de planification doivent être spécifiés par article et également par emplacement.  

Ceci est pris en charge avec l'utilisation des unités de stock, où des paramètres de planification individuels peuvent être spécifiés au niveau des unités de stock. Une unité de stock peut être considérée comme un article dans un emplacement spécifique. Si l'utilisateur n'a pas défini une unité de stock pour cet emplacement, l'application utilisera par défaut les paramètres définis sur la fiche article. L'application calcule un plan pour les emplacements actifs uniquement, c'est-à-dire les emplacements où il existe une offre et une demande pour l'article donné.  

En principe, tout article peut être traité dans n’importe quel emplacement, mais l’application du programme du concept d’emplacement est assez stricte. Par exemple, un document de vente dans un emplacement ne peut pas être satisfait par une certaine quantité en inventaire dans un autre emplacement. La quantité en inventaire doit d'abord être transférée à l'emplacement spécifié sur le document de vente.  

![Planification pour unités de stock.](media/NAV_APP_supply_planning_1_SKU_planning.png "Planification d'unités de stock")  

Pour plus d'informations, voir [Détails de conception : transferts de planification](design-details-transfers-in-planning.md)  

### <a name="order-priority"></a>Priorité de commande

Dans une unité de stock donnée, la date demandée ou disponible représente la priorité la plus élevée ; la demande du jour doit être traitée avant la demande des jours suivants. Mais en plus de ce type de priorité, les différents types de demande et d’approvisionnement doivent être triés en fonction de l’importance commerciale pour choisir quelle demande doit être satisfaite avant de répondre à une autre demande. Du côté de l'approvisionnement, la priorité de la commande indique la source d'approvisionnement qui doit être affectée avant d'affecter d'autres sources d'approvisionnement.  

Pour en savoir plus, voir [Affecter une priorité aux commandes](design-details-balancing-demand-and-supply.md#prioritizing-orders).  

## <a name="demand-forecasts-and-blanket-orders"></a>Prévisions de demande et commandes permanentes

Les prévisions et les commandes permanentes représentent la demande anticipée. La commande permanente, qui regroupe les achats prévus d’un client sur une certaine période, se charge d’amortir l’incertitude de la prévision globale. La commande permanente est une prévision spécifique au client qui s'ajoute à la prévision non spécifiée comme illustré ci-dessous.  

![Planification avec prévisions.](media/NAV_APP_supply_planning_1_forecast_and_blanket.png "Planification avec prévisions")  

Pour plus d’informations, reportez-vous à la section [La demande de prévision est réduite par les documents de vente](design-details-balancing-demand-and-supply.md#forecast-demand-is-reduced-by-sales-orders).  

## <a name="planning-assignment"></a>Affectation de planification

Tous les articles doivent être planifiés. Cependant, il n'existe aucune raison de calculer une planification pour un article à moins qu'il n'y ait eu une modification de la configuration de l'offre ou de la demande depuis la dernière fois qu'un plan a été calculé.  

Si l'utilisateur a saisi un document de vente ou en a modifié une existante, il existe un motif au recalcul de la planification. Les autres motifs sont notamment une modification de prévision ou la quantité de stock de sécurité souhaitée. La modification de nomenclatures lorsque vous ajoutez ou supprimez une composante indique très probablement une modification, mais pour la composante uniquement.  

Le système de planification contrôle ces événements et affecte les articles appropriés pour la planification.  

Pour plusieurs emplacements, l'affectation se fait au niveau de l'article par combinaison d'emplacements. Si, par exemple, un document de vente a été créé à un seul emplacement, l'application affecte l'article à cet emplacement spécifique pour la planification.  

La raison de la sélection d'articles pour la planification est une question de performances système. Si aucune modification du motif demande-approvisionnement d’un article n’a été apportée, le système de planification ne propose aucune action à effectuer. Sans l'affectation de planification, le système devrait effectuer les calculs pour tous les articles afin de déterminer quoi planifier, et cela purgerait des ressources du système.  

La liste complète des motifs pour affecter un article à la planification est disponible dans [Détails de conception : tableau d'affectation de planification](design-details-planning-assignment-table.md).  

Les options de planification dans [!INCLUDE[prod_short](includes/prod_short.md)] sont les suivantes :  

-   Calculer planning régénératif – calcule tous les articles sélectionnés, que ce soit nécessaire ou non.  
-   Calculer la planification Variation nette – calcule uniquement les articles sélectionnés dont la configuration offre-demande a été modifiée et, par conséquent, qui ont été affectés à la planification.  

Certains utilisateurs croient que la planification des variations nettes doit être exécutée à la volée, par exemple, quand les documents de vente sont saisies. Toutefois, ceci peut être source de confusion car le chaînage dynamique et les messages d'action sont également calculés à la volée. En outre, [!INCLUDE[prod_short](includes/prod_short.md)] offre un contrôle en temps réel de la disponibilité à la vente, qui fournit des alertes contextuelles lors de la saisie de documents de vente si la demande ne peut pas être traitée dans le programme d'approvisionnement actif.  

En plus de ces considérations, le système de planification planifie uniquement les articles que l'utilisateur a préparés avec les paramètres de planification appropriés. Sinon, nous considérons que l'utilisateur organisera les articles manuellement ou semi-automatiquement à l'aide de la fonction Planification commande.  

Pour plus d'informations sur les procédures de planification automatiques, voir [Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md).  

## <a name="item-dimensions"></a>Dimensions d’article

L'offre et la demande peuvent contenir des codes variante et des codes d'emplacement qui doivent être respectés lorsque le système de planification équilibre l'offre et la demande.  

Le système traite les codes de variante et d'emplacement en tant que dimensions d'article sur une ligne document de vente, une écriture inventaire, etc. Par conséquent, il calcule un plan pour chaque combinaison de variante et d'emplacement, comme si la combinaison était un numéro d'article distinct.  

Au lieu de calculer une combinaison théorique de variante et emplacement, l'application ne calcule que les combinaisons réellement existantes dans la base de données.  

Pour plus d'informations sur la manière dont le système de planification traite les codes d'emplacement sur demande, voir [Détails de conception : demande à un emplacement vide](design-details-balancing-demand-and-supply.md).  

## <a name="item-attributes"></a>Attributs article

Outre les dimensions d'article générales, par exemple le numéro d'article, le code variante, le code d'emplacement et le type de commande, chaque événement d'offre et de demande peut comporter des spécifications supplémentaires sous forme de numéros de série/lot. Le système de planification planifie ces attributs de certaines manières en fonction de leur niveau de spécification.  

Un lien ordre pour ordre entre l'offre et la demande est un autre type d'attribut qui affecte le système de planification.  

### <a name="specific-attributes"></a>Attributs spécifiques

Certains attributs de la demande sont spécifiques et doivent correspondre exactement à un approvisionnement correspondant. Les deux attributs spécifiques suivants existent :  

-   Numéros de série/lot demandés qui nécessitent une application spécifique (si la case à cocher **NS - Traçabilité spéc.** ou **N° lot - Traçabilité spéc.** est sélectionnée sur la page **Fiche code traçabilité** pour le code de traçabilité utilisé par l'article.)  
-   Établit un lien vers les commandes d'approvisionnement créées manuellement ou automatiquement pour une demande spécifique (liens commande à commande).  

Pour les attributs, le système de planification applique les règles suivantes :  

-   Une demande avec des attributs spécifiques peut être satisfaite uniquement par un approvisionnement aux attributs correspondants.  
-   L'approvisionnement avec des attributs spécifiques peut également répondre à la demande qui ne demande pas spécifiquement ces attributs.  

Par conséquent, si une demande d'attributs spécifiques ne peut pas être satisfaite par l'inventaire ou les approvisionnements prévisionnels, le système de planification suggère une nouvelle commande d'approvisionnement pour couvrir la demande spécifique, quels que soient les paramètres de planification.  

### <a name="non-specific-attributes"></a>Attributs non spécifiques

Les articles avec numéros de série/lot sans configuration de traçabilité spécifique peuvent conserver les numéros de série/lot qui n'ont pas besoin d'être affectés exactement au même numéro de série/lot, mais peuvent être affectés à n'importe quel numéro de série/lot. Cela offre au système de planification plus de liberté pour répondre, par exemple, à une demande de série fabriquée avec un approvisionnement de série, généralement dans l'inventaire.  

Des demandes-approvisionnements avec des numéros de série et/ou de lot, spécifiques ou non spécifiques, sont considérés comme de haute priorité et sont donc exempts de la zone gelée, c'est-à-dire qu'ils font partie de la planification même s'ils sont dus avant la date début de la planification.  

Pour plus d’informations, reportez-vous à la section [Les numéros de série/lot sont chargés en fonction du niveau de spécification](design-details-balancing-demand-and-supply.md#seriallot-numbers-are-loaded-by-specification-level).

Pour plus d'informations sur la manière dont le système de planification équilibre les attributs, voir [Les numéros de série et/ou de lot et les liens Ordre pour ordre sont exempts de la zone gelée](design-details-balancing-demand-and-supply.md#seriallot-numbers-and-order-to-order-links-are-exempt-from-the-frozen-zone).  

## <a name="order-to-order-links"></a>Liens ordre pour ordre

Un approvisionnement ordre pour ordre signifie qu'un article est acheté, assemblé ou produit pour couvrir exclusivement une demande spécifique. Généralement, il se rapporte aux A-items et la motivation pour choisir cette méthode peut être que la demande n'est pas fréquente, le délai de production est insignifiant ou les attributs requis varient.  

Il existe un autre cas particulier d'utilisation des liens commande à commande : la liaison d'un ordre d'assemblage à un document de vente dans un scénario assembler pour commande.  

Les liens commande à commande sont affectés entre la demande et l'approvisionnement de quatre manières :  

-   Lorsque l'article planifié utilise l'ordre de méthode de réapprovisionnement.  
-   Lors de l'utilisation de la méthode de fabrication Prod. pour commande pour créer des bons de production de type multiniveau ou projet (la production avait besoin de composantes sur le même bon de production).  
-   Lors de la création des bons de production pour les documents de vente avec la fonction Planification document de vente.  
-   En assemblant un article à un document de vente. (La politique d'assemblage est définie sur Assembler pour commande.  

Dans ces instances, le système de planification suggère uniquement de commander la quantité nécessaire. Une fois que créé, l'achat, la production ou l'ordre d'assemblage continueront à correspondre à la demande correspondante. Par exemple, en cas de modification du délai ou de la quantité d'un document de vente, le système de planification suggère que la commande d'approvisionnement correspondante soit modifiée en conséquence.  

Lorsqu'il existe des liens commande à commande, le système de planification n'implique pas d'approvisionnement ou d'inventaire lié dans la procédure d'équilibre. C'est à l'utilisateur d'évaluer si l'approvisionnement lié doit être utilisé pour couvrir une autre ou une nouvelle demande et, dans ce cas, de supprimer la commande d'approvisionnement ou de réserver l'approvisionnement lié manuellement.  

Les réservations et les liens traçabilité commande s'arrêteront si une situation devient impossible, tels que déplacer la demande à une date antérieure à l'approvisionnement. Toutefois, le lien ordre pour ordre s'adapte à tout changement dans la demande ou l'approvisionnement correspondant et le lien n'est de ce fait jamais rompu.  

## <a name="reservations"></a>Réservations

Le système de planification n’inclut pas de quantité réservée dans le calcul. Par exemple, si un document de vente a été totalement ou partiellement réservé par rapport à la quantité de l'inventaire, la quantité réservée dans l'inventaire ne peut pas être utilisée pour couvrir l'autre demande. Le système de planification n'inclut pas cet ensemble demande-approvisionnement dans ses calculs.  

Cependant, le système de planification inclut toujours les quantités réservées dans le profil d'inventaire prévisionnel parce que toutes les quantités doivent être considérées pour déterminer quand le point de réapprovisionnement a été passé et la quantité de réapprovisionnement nécessaire pour atteindre et ne pas dépasser le niveau d'inventaire maximum. Par conséquent, les réservations inutiles augmenteront les risques d'épuisement des niveaux d'inventaire parce que la logique de planification ne détecte pas les quantités réservées.  

La figure suivante permet de visualiser la manière dont les réservations peuvent gêner le programme le plus faisable.  

![Planification avec réservations.](media/NAV_APP_supply_planning_1_reservations.png "Planification avec réservations")  

Pour plus d'informations, voir [Détails de conception : réservation, chaînage et message d'action](design-details-reservation-order-tracking-and-action-messaging.md).  

## <a name="warnings"></a>Alertes

La première colonne dans la feuille planification concerne les champs d'avertissement. Les lignes planification créées pour une situation inhabituelle affichent une icône d'avertissement dans ce champ. L'utilisateur peut cliquer dessus pour consulter des informations supplémentaires.  

L'approvisionnement pour les lignes planification avec avertissements n'est normalement pas modifié en fonction des paramètres de planification. Au lieu de cela, le système de planification propose uniquement un approvisionnement pour couvrir la quantité de demande exacte. Cependant, le système peut être configuré pour respecter certains paramètres de planification pour les lignes planification avec certains avertissements. Pour plus d'informations, reportez-vous à la description de ces options pour le traitement par lots **Calc. planning - F. planning** et le traitement en lot **Calculer planification - F. demande** respectivement.  

Les informations d'avertissement sont affichées sur la page **Éléments planification non suivis**, qui est également utilisée pour afficher les liens de suivi de commande vers des entités réseau hors commande. Les types d'alerte suivants existent :  

-   Urgence  
-   Exception  
-   Attention  

![Avertissements dans la feuille planification.](media/NAV_APP_supply_planning_1_warnings.png "Avertissements dans la feuille planification")  

### <a name="emergency"></a>Urgence

L'avertissement Urgence est affiché dans deux situations :  

-   Lorsque l'inventaire est négatif à la date début de la planification.  
-   Lorsqu'il existe des événements d'offre ou de demande rétroactifs.  

Si l’inventaire d’un article est négatif à la date début de la planification, le système de planification suggère un approvisionnement d’urgence afin que la quantité négative arrive à la date début de la planification. Le texte d'avertissement indique la date début et la quantité de la commande d'urgence. Pour plus d'informations, voir [Traitement de l'inventaire négatif prévisionnel](design-details-handling-reordering-policies.md#handling-projected-negative-inventory).  

Les lignes document avec une date d'échéance antérieure à la date début de la planification sont consolidées dans une commande d'approvisionnement d'urgence pour que l'article arrive à la date début de la planification.  

### <a name="exception"></a>Exception

L'avertissement Exception s'affiche si le stock disponible prévu descend en dessous du stock de sécurité. Le système de planification suggère une commande d'approvisionnement pour répondre aux besoins à la date d'échéance. Le texte d'avertissement indique la quantité du stock de sécurité et la date à laquelle elle est entamée.  

Entamer le stock de sécurité est considéré comme une exception car cela ne doit pas se produire si le point de commande a été correctement défini. Pour plus d'informations, voir [Le rôle du point de commande](design-details-handling-reordering-policies.md#the-role-of-the-reorder-point).  

En règle générale, les propositions de commande exceptionnelles permettent de s'assurer que le stock disponible prévu n'est jamais inférieur au niveau de stock de sécurité. Cela signifie que la quantité proposée est suffisante pour couvrir le stock de sécurité, sans prendre en compte les paramètres de planification. Toutefois, dans certains cas, des modificateurs de commande sont pris en compte.  

> [!NOTE]  
>  Le système de planification peut consommer le stock de sécurité intentionnellement, puis le réapprovisionne immédiatement. Pour plus d'informations, reportez-vous à [Le stock de sécurité peut être consommé](design-details-balancing-demand-and-supply.md#loading-the-inventory-profiles).

### <a name="attention"></a>Attention

L'avertissement Attention est affiché dans trois situations :  

-   La date début de la planification est antérieure à la date de travail.  
-   La ligne planification suggère de changer un bon de commande ou de production libéré.  
-   L'inventaire prévisionnel dépasse le niveau de dépassement de capacité à la date d'échéance. Pour plus d'informations, voir [Rester sous le niveau de dépassement de capacité](design-details-handling-reordering-policies.md#staying-under-the-overflow-level).  

> [!NOTE]  
>  Dans les lignes planification comportant des avertissements, le champ **Accepter message d'action** n'est pas sélectionné, car le gestionnaire doit poursuivre l'étude de ces lignes avant de mettre en application ce plan.  

## <a name="error-logs"></a>Journaux des erreurs

Dans la page de demande Calculer le plan, l'utilisateur peut sélectionner le champ **Arrêter et afficher la première erreur** pour arrêter l'exécution de la planification quand il rencontre la première erreur. Au même moment, un message affiche des informations sur l'erreur. S'il y a une erreur, seules les lignes planification traitées avant la détection de l'erreur apparaissent dans la feuille planification.  

Si le champ n'est pas activé, le traitement en lot Calculer planification se poursuit jusqu'à ce qu'il soit terminé. Les erreurs éventuelles n'interrompent pas le traitement en lot. S'il y a une ou plusieurs erreurs, une fois l'exécution de l'application terminée, celle-ci affiche un message indiquant le nombre d'articles concernés par les erreurs. La page **Journal des erreurs de planification** s'ouvre ensuite pour afficher des informations supplémentaires sur l'erreur et pour fournir des liens vers les documents ou les fiches de configuration concernés.  

![Messages d’erreur dans la feuille planification.](media/NAV_APP_supply_planning_1_error_log.png "Messages d'erreur dans la feuille planification")  

## <a name="planning-flexibility"></a>Flexibilité planification

Il n'est pas toujours pratique de planifier une commande d'approvisionnement existante, par exemple si la fabrication a commencé ou si du personnel supplémentaire est engagé un jour spécifique pour faire le travail. Pour indiquer si une commande existante peut être modifiée par le système de planification, toutes les lignes de commande d'approvisionnement ont un champ Flexibilité de planification avec deux options : Illimité ou Aucun. Si le champ est défini sur Aucune, le système de planification ne tente pas de modifier la ligne commande d'approvisionnement.  

Le champ peut être manuellement défini par l'utilisateur, cependant, dans certains cas il est automatiquement paramétré par le système. Le fait que la flexibilité de planification peut être définie manuellement par l'utilisateur est important, parce que cela permet d'adapter facilement l'utilisation de la fonction dans différents flux de travail et cas commerciaux.  

Pour plus d'informations sur l'utilisation de ce champ, voir [Détails de conception : transferts de planification](design-details-transfers-in-planning.md).  

## <a name="order-planning"></a>Planification commande

L'outil de base de planification de l'approvisionnement représenté par la page **Planification commande** est conçu pour la prise de décision manuelle. Il ne tient compte d'aucun paramètre de planification et n'est donc pas traité ultérieurement dans ce document. Pour plus d’informations, consultez [Planifier de nouvelles demandes commande par commande](production-how-to-plan-for-new-demand.md).  

> [!NOTE]  
>  Il n'est pas recommandé d'utiliser la Planification commande si la compagnie utilise déjà les feuilles de réquisition ou de planification. Les commandes d'approvisionnement créées via la page **Planification commande** peuvent être modifiées ou supprimées pendant les planifications automatisées. En effet, la planification automatisée utilise les paramètres de planification qui n'ont peut-être pas été pris en compte par l'utilisateur ayant créé la planification manuelle sur la page Planification de commande.  

## <a name="finite-loading"></a>Chargement limité

[!INCLUDE[prod_short](includes/prod_short.md)] est un système ERP standard, et non un système d'affectation ou de gestion d'atelier. Il prévoit une utilisation faisable des ressources via un calendrier approximatif, mais il ne crée pas et ne met pas à jour automatiquement des calendriers détaillés sur la base de priorités ou de règles d'optimisation.  

L'utilisation prévue de la fonction Capacité critique est 1) : pour éviter la surcharge de ressources spécifiques et 2) : pour s'assurer qu'aucune capacité n'est laissée non affectée si elle peut augmenter le délai d'exécution d'un ordre de fabrication. La fonction n'inclut pas d'équipements ni d'options pour gérer les priorités ou optimiser des opérations, comme on s'attendrait à en trouver dans un système d'affectation. Toutefois, elle permet de fournir des informations de capacité approximative utiles pour identifier des goulots d'étranglement et éviter de surcharger des ressources.  

Lors de la planification avec des ressources avec contraintes de capacité, le système veille à ce qu'aucune ressource ne soit chargée au-dessus de sa capacité définie (charge critique). Ceci est effectué en affectant chaque opération à l'emplacement du temps disponible le plus proche. Si le créneau n'est pas assez long pour effectuer toute l'opération, l'opération est répartie en au moins deux parties placées dans les créneaux disponibles les plus proches.  

> [!NOTE]  
> En cas de répartition des opérations, le temps de préparation n'est affecté qu'une fois car on suppose qu'un certain ajustement manuel est effectué pour optimiser le calendrier.  

Le seuil peut être ajouté aux ressources pour réduire la répartition des opérations. Cela permet au système de programmer une charge sur le dernier jour possible en dépassant légèrement le pourcentage de charge critique si ceci peut réduire le nombre d'opérations qui sont divisées.  

Cela complète la planification des concepts centraux en relation avec la planification des approvisionnements dans [!INCLUDE[prod_short](includes/prod_short.md)]. Les sections suivantes examinent les concepts plus profonds et les placent dans le cadre des procédures de planification de base, de l'équilibrage de l'approvisionnement et de la demande, ainsi que de l'utilisation des méthodes de réapprovisionnement.  

## <a name="see-also"></a>Voir aussi .

[Détails de conception : transferts de planification](design-details-transfers-in-planning.md)  
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)  
[Détails de conception : tableau d'affectation de planification](design-details-planning-assignment-table.md)  
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)  
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
