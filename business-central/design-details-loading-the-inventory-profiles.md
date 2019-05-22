---
title: Détails de conception - Chargement des profils d'inventaire | Microsoft Docs
description: Pour trier les nombreuses sources de demande et d'approvisionnement, le système de planification les organise sur deux chronologies appelées profils d'inventaire.
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
redirect_url: design-details-balancing-demand-and-supply
ms.openlocfilehash: 09f74e83bdc467378144f586dd3a33a0fc1ba213
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1242179"
---
# <a name="design-details-loading-the-inventory-profiles"></a>Détails de conception : chargement des profils inventaire
Pour trier les nombreuses sources de demande et d'approvisionnement, le système de planification les organise sur deux chronologies appelées profils d'inventaire.  

 Les types normaux de demande et d'approvisionnement dont les dates d'échéance correspondent ou sont ultérieures à la date début de la planification sont chargés dans chaque profil d'inventaire. Une fois chargés, les différents types de demande et d'approvisionnement sont triés en fonction des priorités générales, comme la date d'échéance, les codes de plus bas niveau, l'emplacement et la variante. De plus, des priorités d'ordre s'appliquent aux différents types pour s'assurer que la demande la plus importante soit satisfaite en premier. Pour plus d'informations, voir [Détails de conception : Affecter une priorité aux commandes](design-details-prioritizing-orders.md).  

 Comme indiqué précédemment, la demande peut également être négative. Cela signifie qu'il doit être traité comme approvisionnement ;, toutefois, contrairement aux types courants d'approvisionnement, la demande négative est considérée comme approvisionnement fixe. Le système de planification peut la prendre en compte, mais ne proposera en aucun cas de la modifier.  

 Généralement le système de planification tient compte de toutes les commandes approvisionnement après la date de début de la planification comme susceptibles de changer pour répondre à une demande. Toutefois, dès qu'une quantité est reportée à partir d'une commande approvisionnement, elle ne peut plus être modifiée par le système de planification. Par conséquent, les différents ordres suivants ne peuvent pas être replanifiés :  

-   Bons de production libérés pour lesquels la consommation ou la production a été reportée.  

-   Ordres d'assemblage pour lesquels la consommation ou la production a été reportée.  

-   Transférez les ordres pour lesquels la livraison a été reportée.  

-   Commandes achat pour lesquelles la réception a été reportée.  

 Outre le chargement des types d'offre et de demande, certains types sont chargés en fonction de règles et de dépendances spéciales décrites ci-après.  

## <a name="item-dimensions-are-separated"></a>Les axes article sont distincts  
 Le programme d'approvisionnement doit être calculé par combinaison des dimensions d'article, comme la variante et l'emplacement. Toutefois, il n'y a pas de raison de calculer des combinaisons théoriques. Seules ces combinaisons contenant une demande et/ou un approvisionnement doivent être calculées.  

 Le système de planification contrôle cela en parcourant le profil d'inventaire. Lorsqu'une nouvelle combinaison est trouvée, le programme crée un enregistrement de contrôle interne qui contient les informations de combinaison réelles. Le programme insère l'unité de stock comme enregistrement de contrôle, ou boucle externe. Par conséquent, les paramètres de planification appropriés en fonction d'une combinaison de variante et d'emplacement sont définis, et le programme peut passer à la boucle interne.  

> [!NOTE]  
>  Le programme ne requiert pas que l'utilisateur saisisse un enregistrement d'unités de stock en entrant la demande et/ou l'approvisionnement pour une combinaison particulière de variante et de emplacement. Par conséquent, si une unité de stock n'existe pas pour une combinaison donnée, le programme crée son propre enregistrement d'unité de stock temporaire à partir des données de fiche article. Si Emplacement obligatoire a la valeur Oui sur la page Configuration inventaire, une unité de stock doit être créée ou Composantes à l'emplacement doit avoir la valeur Oui. Pour plus d'informations, voir [Détails de conception : demande à un magasin vide.](design-details-demand-at-blank-location.md).  

## <a name="seriallot-numbers-are-loaded-by-specification-level"></a>Les numéros de série/lot sont chargés en fonction du niveau de détail  
 Les attributs sous forme de numéros de série/lot sont chargés dans les profils d'inventaire avec l'offre et la demande auxquels ils sont affectés.  

 Les attributs de demande et d'approvisionnement sont réorganisés par priorité de commande ainsi que par leur niveau de spécification. Comme le numéro de série/lot reflète le niveau de la spécification, la demande plus spécifique, par exemple un numéro de lot sélectionné spécifiquement pour une ligne vente, recherche une correspondance avant une demande moins spécifique, par exemple une vente à partir de n'importe quel numéro de lot sélectionné.  

> [!NOTE]  
>  Il n'existe pas de règles de priorité dédiées pour les demandes et approvisionnements avec numéros de lot/série autres que le niveau de spécification défini leurs combinaisons numéro de série et de lot et la configuration du suivi des articles associés.  

 Lors de l'équilibrage, le système de planification considère un approvisionnement qui porte des numéros de série/lot comme non flexible et n'essaie pas d'augmenter ou de reprogrammer ce type de commandes d'approvisionnement (à moins qu'elles ne soient utilisées dans une relation Commande à commande). Voir les liens ordre pour ordre ne sont jamais rompus). Cela évite que l'approvisionnement ne reçoive plusieurs messages d'action, possiblement contradictoires, lorsqu'un approvisionnement comporte des attributs divers, comme une collection de différents numéros de série.  

 Il existe une autre raison pour laquelle un approvisionnement portant des numéros de série/lot est considéré comme non flexible. Dans la mesure où les numéros de série/lot sont généralement affectés très tard au cours du processus, cela représenterait une source de confusion si des modifications étaient proposées.  

 L'équilibrage des numéros de série/lot ne tient pas compte de la [Zone gelée](design-details-dealing-with-orders-before-the-planning-starting-date.md). Si l'offre et la demande ne sont pas synchronisées, le système de planification proposera des modifications ou suggèrera de nouvelles commandes, quelle que soit la date de début de la planification.  

## <a name="order-to-order-links-are-never-broken"></a>Les Liens ordre pour ordre ne sont jamais rompus  
 Lors de la planification d'un article commande-à-commande, l'approvisionnement lié ne doit pas être utilisé pour toute demande autre que ce à quoi il était prévu à l'origine. La demande liée ne doit pas être couverte par un autre approvisionnement aléatoire, même si, dans sa situation actuelle, il est disponible en termes de délai et de quantité. Par exemple, un ordre d'assemblage lié à un document de vente dans un scénario assembler pour commande ne peut pas être utilisé pour couvrir l'autre demande.  

 La demande et l'approvisionnement ordre pour ordre doivent être équilibrées exactement. Le système de planification assure l'approvisionnement en toutes circonstances sans tenir compte des paramètres de taille de commande, des modificateurs, ni des quantités dans l'inventaire (autres que les quantités liées aux commandes). Pour le même motif, le système suggère de diminuer les approvisionnements excédentaires si la demande liée est réduite.  

 Cet équilibre affecte également le temps. L'horizon limité accordé par la plage de temps n'est pas pris en compte ; l'approvisionnement sera reprogrammé si le délai de la demande a été modifié. Cependant, le seuil sera respecté et empêchera que des approvisionnements commande à commande soient programmés en sortie, sauf pour les approvisionnements internes d'un bon de production multiniveau (commande projet).  

> [!NOTE]  
>  Les numéros de série/lot peuvent également être spécifiés sur la demande ordre pour ordre. Dans ce cas, l'approvisionnement n'est pas considéré comme inflexible par défaut, comme c'est habituellement le cas pour les numéros de série/lot. Dans ce cas, le système augmentera/diminuera en fonction des modifications de la demande. En outre, si une demande contient différents numéros de série/lot, par exemple plusieurs numéros de lot, une commande d'approvisionnement est proposée par lot.  

> [!NOTE]  
>  Les prévisions ne doivent pas entraîner la création de commandes d'approvisionnement liées par un lien Commande à commande. Si la prévision est utilisée, elle doit être utilisée comme générateur d'une demande dépendante dans un environnement de fabrication.  

## <a name="component-need-is-loaded-according-to-production-order-changes"></a>Besoin composante est chargé en fonction des modifications du bon de production  
 Lors de la gestion des ordres de fabrication, le système de planification doit contrôler les composants nécessaires avant de les charger dans le profil de demande. Les lignes composante qui résultent d'un bon de production modifié remplaceront celles de la commande originale. Cela garantit que le système de planification fait en sorte que les lignes de planification pour les besoins de composante ne sont jamais dupliquées.  

##  <a name="BKMK_SafetyStockMayBeConsumed"></a> Le stock de sécurité peut être consommé  
 L'inventaire de sécurité est principalement un type de demande et est donc chargé dans le profil d'inventaire à la date début de la planification.  

 L'inventaire de sécurité est une quantité en inventaire mise de côté pour compenser les incertitudes de la demande pendant le délai de réapprovisionnement. Toutefois, il peut être consommé s'il s'avère nécessaire de l'utiliser pour répondre à une demande. Le système de planification assure dans ce cas le remplacement rapide du stock de sécurité en suggérant un ordre d'approvisionnement permettant le réapprovisionnement de la quantité du stock de sécurité à sa date de consommation. Cette ligne planification affiche une icône d'avertissement Exception qui indique au gestionnaire que le stock de sécurité est partiellement ou entièrement consommé via une commande d'exception de la quantité manquante.  

## <a name="forecast-demand-is-reduced-by-sales-orders"></a>La demande de prévision est réduite par les commandes vente  
 La prévision de la demande exprime une future demande anticipée. Lorsqu'une demande réelle est saisie, généralement comme commandes vente pour les articles produits, elle consomme la prévision.  

 La prévision proprement dite n'est pas réellement réduite par les commandes vente ; elle reste la même. Cependant, les quantités prévues utilisées dans le calcul de planification sont réduites (par les quantités de document de vente) avant que la quantité restante, le cas échéant, soit saisie dans le profil de l'inventaire de demande. Lorsque le système de planification examine les ventes réelles pendant une période, les documents de vente ouvertes et les écritures du grand livre d'articles des ventes livrées sont inclus, à moins qu'ils ne proviennent d'une commande ouverte.  

 Un utilisateur doit définir une période de prévision valide. La date de la quantité prévue définit le début de la période, et la date de la prévision suivante définit la fin de la période.  

 La prévision pour les périodes antérieures à la période de planification n'est pas utilisée, qu'elle soit consommée ou non. Le premier chiffre de prévision intéressant est la date même ou la date la plus proche précédant la date de début de la planification.  

 La prévision peut être pour une demande indépendante, telle que des documents de vente, ou une demande dépendante, comme des composantes de bon de production (prévision module). Un article peut avoir deux types de prévision. Lors de la planification, la consommation a lieu séparément, d'abord pour une demande indépendante puis pour une demande dépendante.  

## <a name="blanket-order-demand-is-reduced-by-sales-orders"></a>La demande de commande ouverte est réduite par les commandes vente  
 Des prévisions sont renseignées par la commande permanente ventes comme moyen de spécifier une future demande pour un client spécifique. Comme pour la prévision (non spécifiée), les ventes réelles doivent consommer la demande prévue, et la quantité restante doit être entrée dans le profil de l'inventaire de demande. À nouveau, la consommation ne réduit pas réellement la commande ouverte.  

 Le calcul de planification tient compte des commandes vente ouvertes liées à la ligne spécifique de la commande ouverte, mais ne tient compte d'aucune période valide. Il ne prend pas non plus en compte les commandes reportées, étant donné que la procédure de report a déjà réduit la quantité restante de commande ouverte.  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)   
 [Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)   
 [Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
 [Détails de conception : paramètres de planification](design-details-planning-parameters.md)
