---
title: Paramétrage de la gestion des services | Microsoft Docs
description: Aperçu des tâches de paramétrage de la gestion des services en fonction de la manière dont vos partenaires gère leurs services.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'service, service items, repairs, maintenance, fix'
ms.date: 03/20/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="setting-up-service-management"></a>Paramétrage de la gestion des services
Avant de pouvoir démarrer l'utilisation des fonctionnalités de gestion des services dans [!INCLUDE[prod_short](includes/prod_short.md)], il y a quelques éléments à configurer. Par exemple, vous pouvez établir le codage des services standard, les codes symptôme et panne, ainsi que configurer les articles de service et les types d’article de service requis par les besoins du service clientèle de votre compagnie.  

Lorsque vous configurez la gestion des services, vous devez choisir les services que vous allez fournir aux clients et les programmer. Un service correspond à un type de travail exécuté par une ou plusieurs ressources et fourni à un client. Ce peut être un type de réparation informatique. Un article de service correspond à l'équipement ou l'article associé au service : par exemple, un ordinateur à réparer, installé chez un client spécifique. Vous pouvez configurer les services afin de les intégrer au groupe d'articles de réparation ou d'entretien associés.  
  
Lorsque vous définissez un service, vous pouvez l'associer aux compétences requises pour l'exécuter. Afin d'optimiser l'efficacité des représentants du service client, vous pouvez également configurer des instructions dépannage en temps réel et affecter les coûts de démarrage courants (coûts déplacement ou autres frais).  

Le tableau suivant décrit une série de tâches et inclut des liens vers les articles qui les décrivent.  
  
| À | Voir |
| --- | --- |
| Configurez les codes qui affectent automatiquement les lignes des documents service pour les services que vous fournissez souvent. |[Configurer des codes prestations standards](service-how-setup-service-coding.md)|
| Définissez les paramètres généraux qui contrôlent les aspects des processus de gestion des services.|[Configuration des processus de service](service-setup-service-processes.md)|
| Définissez comment votre organisation utilise les rapports de pannes. |[Configurer le rapport de panne](service-how-setup-fault-reporting.md) |
| Configurez les offres de service que votre compagnie fournit aux clients.|[Configurer des offres de service](service-how-setup-service-offerings.md)|
| Fournissez des instructions de dépannage permettant aux responsables de la maintenance de fournir un service plus rapide. |[Configurer le dépannage](service-how-setup-troubleshooting.md) |
| Configurez l'affectation des ressources pour simplifier l'affectation de la ressource à une tâche service de manière appropriée. |[Configurer l'affectation des ressources](service-how-setup-resource-allocation.md) |
| Définissez la tarification des services, et paramétrez des coûts service supplémentaires pour évaluer des commandes service. |[Configuration de la tarification et des frais supplémentaires pour les services](service-how-setup-service-costs-pricing.md)|
| Configuration pour suivre les heures ressource et les états commande service afin de prévoir les besoins en charges de travail et en service.|[Configurer des heures de travail et des heures de service](service-how-setup-work-service-hours.md)|
| Configurez les options d'état de réparation pour surveiller la progression des réparations. | [Configurer les états des commandes service et des réparations](service-order-repair-status.md)|
| Configurez un programme d'articles de prêt, en vue de pouvoir prêter un article de substitution lorsque vous travaillez avec un article de service. |[Configuration d'un programme d'articles de prêt](service-how-setup-loaner-program.md) |
| Configurez les articles de service et les composantes article de service. |[Configurer des articles de service](service-how-setup-service-items.md) |
| Définir les bases pour créer des contrats de service et des devis contrat. |[Configurer des contrats de service](service-how-setup-service-contracts.md) |

## <a name="see-also"></a>Voir aussi
[Gestion des services](service-service.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
