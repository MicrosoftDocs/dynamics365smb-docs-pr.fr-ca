---
title: Configurer les états des commandes service et des réparations | Microsoft Docs
description: Vous devez configurer neuf options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: ba7edc6de37d41cd2bb31285c18d127be6612288
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8130056"
---
# <a name="set-up-statuses-for-service-orders-and-repairs"></a>Configurer les états des commandes service et des réparations

Vous devez configurer des options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service. Vous devez configurer au moins neuf options d'état réparation qui identifient les situations ou les actions effectuées lors de la maintenance des articles de service.  

Vous pouvez définir le niveau de priorité des options d'état de commande service. Quatre niveaux de priorité sont disponibles : **Très haute**, **Haute**, **Moyenne** et **Basse**.  

Lorsque vous modifiez l'état réparation d'un article de service d'une commande service, l'état commande service est mis à jour. L'état réparation de chaque article de service est lié à l'état commande service. Si les articles de service sont liés à plusieurs options d'état commande service, l'état de commande service dont la priorité est la plus élevée est sélectionné.  

Avant de pouvoir configurer un état de réparation, vous devez définir des priorités d'état de service.

## <a name="to-set-up-service-status-priorities"></a>Pour configurer les priorités état service

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **État commande service**, puis choisissez le lien associé.  
2. Sélectionnez l'état commande service pour lequel vous voulez configurer une priorité.  
3. Dans le champ **Priorité**, choisissez la priorité souhaitée pour cet état commande service.  

Répétez les étapes 2 et 3 pour configurer la priorité des quatre options état : **Suspendu**, **En cours**, **Terminé** et **En attente**.  

## <a name="to-set-up-a-repair-status"></a>Pour configurer un état réparation

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **État réparation**, puis choisissez le lien associé.
2. Créez un état réparation.  
3. Renseignez les champs **Code** et **Désignation**.  
4. Dans le champ **État commande service**, choisissez l'état de la commande auquel lier l'état de réparation. Le champ **Priorité** affiche la priorité de l'état de la commande service que vous avez choisie.  
5. Choisissez un état réparation. Vous ne pouvez en choisir qu'un. L'état réparation ne peut pas être lié à une option d'état réparation.  
6. Pour reporter des commandes service comprenant des articles de service avec cet état réparation, choisissez le champ **Report autorisé**.  
7. Pour pouvoir faire passer manuellement l'option d'état de la commande service sur **Suspendu** dans des commandes service comprenant des articles de service avec l'état réparation, choisissez la case à cocher **État Suspendu autorisé**.  
8. Choisissez de la même manière les cases à cocher **État En cours autorisé**, **État Terminé autorisé** et **État En attente autorisé**.

Répétez ces étapes pour chaque option d'état réparation à créer.

## <a name="see-also"></a>Voir aussi

[État commande service et état réparation](service-service-order-status-and-repair-status.md)  
[Paramétrage de la gestion des services](service-setup-service.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]