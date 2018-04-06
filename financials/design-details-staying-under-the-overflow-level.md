---
title: "Détails de conception - Rester sous le niveau de dépassement de capacité | Microsoft Docs"
description: "Lors de l'utilisation de Qté maximum et Qté fixe de commande, le système de planification se concentre sur l'inventaire prévisionnel dans la plage de temps donnée uniquement. Cela signifie que le système de planification peut vous proposer l'approvisionnement superflu lorsqu'une demande négative ou des changements d'approvisionnement positifs se produisent en dehors de la plage de temps donnée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/06/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: bbfafc41f22a5582b90683bdacf8135e78e46843
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="design-details-staying-under-the-overflow-level"></a>Détails de conception : rester sous le niveau de dépassement de capacité
Lors de l'utilisation des stratégies Qté maximum et Qté fixe de commande, le système de planification se concentre sur l'inventaire prévisionnel dans la plage de temps donnée uniquement. Cela signifie que le système de planification peut vous proposer l'approvisionnement superflu lorsqu'une demande négative ou des changements d'approvisionnement positifs se produisent en dehors de la plage de temps donnée. Si, pour cette raison, un approvisionnement superflu est proposé, le système de planification calcule la quantité à soustraire (ou supprimer) de l'approvisionnement pour éviter l'approvisionnement superflu. Cette quantité est appelée « niveau de dépassement de capacité ». Le dépassement de capacité est communiqué comme ligne de planification avec une action **Changer qté (diminuer)** ou **Annuler** et le message d'avertissement suivant :  

*Attention : l'inventaire prévisionnel [xx] est supérieur au niveau de dépassement de capacité [xx] à la date d'échéance [xx].*  

![Niveau de dépassement de capacité d'inventaire](media/supplyplanning_2_overflow1_new.png "supplyplanning_2_overflow1_new")  

##  <a name="calculating-the-overflow-level"></a>Calcul du niveau de dépassement de capacité  
Le niveau de dépassement de capacité est calculé de différentes manières en fonction de la configuration de planification.  

### <a name="maximum-qty-reordering-policy"></a>Méthode de réapprovisionnement Qté maximum  
Niveau de dépassement de capacité = Inventaire maximum  

> [!NOTE]  
>  Si une quantité de commande minimum existe, elle sera ajoutée comme suit : Niveau de dépassement de capacité = Inventaire maximum + Quantité commande minimum.  

### <a name="fixed-reorder-qty-reordering-policy"></a>Méthode de réapprovisionnement Qté fixe de commande  
Niveau de dépassement de capacité = Quantité de réappro. + Point de commande  

> [!NOTE]  
>  Si la quantité minimum commande est supérieure au point de commande, alors elle remplace comme suit : Niveau de dépassement de capacité = Quantité de réappro. + Quantité minimum commande  

### <a name="order-multiple"></a>Commande multiple  
Si un multiple de commande existe, il ajuste le niveau de dépassement de capacité pour les deux méthodes de réapprovisionnement Qté maximum et Qté fixe de commande.  

##  <a name="creating-the-planning-line-with-overflow-warning"></a>Création de la ligne planification avec l'avertissement de dépassement capacité  
Lorsqu'un approvisionnement existant rend l'inventaire prévisionnel supérieur au niveau de dépassement de capacité à la fin d'une plage de temps, une ligne planification est créée. Pour avertir sur le potentiel approvisionnement superflu, la ligne de planification a un message d'avertissement, le champ **Accept Action Message** n'est pas sélectionné, et le message d'action est Cancel ou Change Qty.  

### <a name="calculating-the-planning-line-quantity"></a>Calcul de la quantité pour la ligne planification  
Quantité pour la ligne planification = Quantité d'approvisionnement actif – (Inventaire prévisionnel – Niveau de dépassement de capacité)  

> [!NOTE]  
>  Comme pour toutes les lignes d'avertissement, les quantités maximales/minimales de commande ou les multiples de commande sont ignorés.  

### <a name="defining-the-action-message-type"></a>Définir le type de message d'action  

-   Si la quantité de la ligne planification est supérieure à 0, le message d'action est Changer qté.  
-   Si la quantité de la ligne planification est égale ou inférieure à 0, le message d'action est Annuler  

### <a name="composing-the-warning-message"></a>Composition du message d'avertissement  
Dans le cas d'un dépassement de capacité, la fenêtre **Éléments planification sans suivi** affiche un message d'avertissement avec les informations suivantes :  

-   Le niveau d'inventaire prévisionnel qui a déclenché l'avertissement  
-   Niveau de dépassement de capacité calculé  
-   Date d'échéance d'un événement d'approvisionnement.  

Exemple : « L'inventaire prévisionnel 120 est supérieur au niveau de dépassement de capacité 60 au 28/01/11 »  

## <a name="scenario"></a>Scénario  
Dans ce scénario, un client modifie une document de vente de 70 à 40 pièces entre deux exécutions de planification. La fonction de dépassement de capacité intervient pour réduire l'achat qui a été proposé pour la quantité de ventes initiale.  

### <a name="item-setup"></a>Configuration d'article  

|Politique réapprovisionnement|Qté maximum|  
|-----------------------|------------------|  
|Quantité maximum commande|100|  
|Point de réapprovisionnement|50|  
|Stocks|80|  

### <a name="situation-before-sales-decrease"></a>Situation avant la sortie de vente  

|Evénement|Changer qté|Inventaire projeté|  
|-----------|-----------------|-------------------------|  
|Un jour|Aucun|80|  
|Vente|-70|10|  
|Fin de la plage de temps|Aucun|10|  
|Suggérer un nouveau bon de commande|+90|100|  

### <a name="situation-after-sales-decrease"></a>Situation après la sortie de vente  

|Activer|Changer qté|Inventaire projeté|  
|------------|-----------------|-------------------------|  
|Un jour|Aucun|80|  
|Vente|-40|40|  
|Achat|+90|130|  
|Fin de la plage de temps|Aucun|130|  
|Proposer de réduire l'achat<br /><br /> achat de 90 à 60|-30|100|  

### <a name="resulting-planning-lines"></a>Lignes planification résultantes  
 Une ligne planification (avertissement) est créée pour réduire l'achat de 30 pour passer de 90 à 60 pour conserver l'inventaire prévisionnel à 100 conformément au niveau de dépassement de capacité.  

![Planifier en fonction du niveau de dépassement de capacité](media/nav_app_supply_planning_2_overflow2.png "nav_app_supply_planification_2_overflow2")  

> [!NOTE]  
>  Sans la fonction Dépassement de capacité, aucun avertissement n'est créé si le niveau d'inventaire prévisionnel dépasse l'inventaire maximum. Cela pourrait entraîner un approvisionnement superflu de 30.  

## <a name="see-also"></a>Voir aussi  
[Détails de conception : méthodes de réapprovisionnement](design-details-reordering-policies.md)   
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)   
[Détails de conception : gestion des méthodes de réapprovisionnement](design-details-handling-reordering-policies.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)

