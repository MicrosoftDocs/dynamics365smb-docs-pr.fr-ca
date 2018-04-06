---
title: "Configurer les états des commandes service et des réparations | Microsoft Docs"
description: "Vous devez configurer neuf options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service."
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
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 8ffd5d6893b2b6c8ce7b7377c586f4f5414279b5
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-statuses-for-service-orders-and-repairs"></a>Configurer les états des commandes service et des réparations
Vous devez configurer des options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service. Vous devez configurer au moins neuf options d'état réparation qui identifient les situations ou les actions effectuées lors de la maintenance des articles de service.  

Vous pouvez définir le niveau de priorité des options d'état de commande service. Quatre niveaux de priorité sont disponibles : Très haute, Haute, Moyenne et Basse.  
  
Lorsque vous modifiez l'état réparation d'un article de service d'une commande service, l'état commande service est mis à jour. L'état réparation de chaque article de service est lié à l'état commande service. Si les articles de service sont liés à plusieurs options d'état commande service, l'état de commande service dont la priorité est la plus élevée est sélectionné.  

## <a name="to-set-up-a-repair-status"></a>Pour configurer un état réparation  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **État de la réparation**, puis sélectionnez le lien associé. 2. Créez un état réparation.  
3. Renseignez les champs **Code** et **Désignation**.  
4. Dans le champ **État commande service**, choisissez l'état de la commande auquel lier l'état de réparation. Le champ **Priorité** affiche la priorité de l'état de la commande service que vous avez choisie.  
5. Choisissez un état réparation. Vous ne pouvez en choisir qu'un.  
6. Pour reporter des commandes service comprenant des articles de service avec cet état réparation, choisissez le champ **Report autorisé**.  
7. Pour pouvoir faire passer manuellement l'option d'état de la commande service sur **Suspendu** dans des commandes service comprenant des articles de service avec l'état réparation, choisissez la case à cocher **État Suspendu autorisé**.  
8. Choisissez de la même manière les cases à cocher **État En cours autorisé**, **État Terminé autorisé** et **État En attente autorisé**.
  
## <a name="to-set-up-service-status-priorities"></a>Pour configurer les priorités état service  
1. Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **État commande service**, puis sélectionnez le lien associé.  
2. Sélectionnez l'état commande service pour lequel vous voulez configurer une priorité.  
3. Dans le champ **Priorité**, choisissez la priorité souhaitée pour cet état commande service. Répétez cette étape pour chaque état.  
  
## <a name="see-also"></a>Voir aussi  
[Description des commandes service et de l'état réparation]()  
[Paramétrage de la gestion des services](service-setup-service.md)  

