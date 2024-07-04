---
title: Vue d’ensemble de la gestion de la durabilité
description: Découvrez la fonctionnalité de gestion de la durabilité en utilisant les informations et les ressources fournies.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD'
ms.search.form: null
ms.date: 06/19/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Vue d’ensemble de la gestion de la durabilité

> [!IMPORTANT]
> Cette fonctionnalité sera disponible dans Business Central à partir de la **1re vague de lancement 2024**. Tous les liens de référence seront activés une fois disponibles.

Business Central propose une fonctionnalité de gestion de la durabilité qui vous aide à surveiller et à gérer votre organisation et ses effets sur l’environnement. Cette fonctionnalité est conçue pour superviser et réguler l’empreinte environnementale d’une organisation en suivant diverses émissions de gaz à effet de serre (GES). Ainsi, cela facilite des informations appropriées. La fonctionnalité prend en charge le processus de base de collecte de données sur les émissions via des journaux durabilité. Vous pouvez soit saisir manuellement des données connues, soit utiliser des méthodes intégrées pour calculer l’empreinte des émissions.

> [!NOTE]
> Cette version initiale constitue une étape fondamentale et est entièrement indépendante des autres fonctionnalités de Business Central. Cependant, les versions futures viseront une intégration plus étroite et pourraient automatiser certains processus manuels.

La première version de la fonctionnalité se concentre sur les émissions de GES. La norme environnementale, sociale et de gouvernance (ESG) définit trois champs d’émission :

- **Émissions de champ 1** incluent les émissions émises par la combustion de produits stationnaires et mobiles, ainsi que par les émissions fugitives accidentelles.
- **Les émissions de champ 2** incluent les émissions indirectes provenant de la production d’énergie achetée auprès de fournisseurs d’électricité.
- **Émissions de champ 3** incluent un large spectre d’émissions, provenant des biens et services achetés et des biens d’équipement, des activités liées aux carburants et à l’énergie, aux transports en amont et en aval, aux déchets générés, aux voyages d’affaires et aux déplacements domicile-travail des employés, etc.

Cette fonctionnalité vous permet :

- Définir des facteurs d’émission pour différentes sources et catégories d’émissions de GES.
- Enregistrez les données d’émission dans des journaux de développement durable, soit manuellement, soit en utilisant des méthodes de calcul prédéfinies.
- Reportez des écritures émission dans le grand livre durabilité, où vous pouvez afficher et analyser les données d’émission selon différentes dimensions.
- Générez des rapports de durabilité qui montrent les performances en matière d’émissions de GES de votre organisation.

Pour vous familiariser avec Sustainability Manager, reportez-vous aux articles suivants.

| Article | Désignation |
|---------|-------------|
| **Fonctionnalité** |             |
| [Configuration de durabilité](finance-sustainability-setup.md) | Cet article fournit des informations pour vous aider à configurer correctement l’ensemble du module Développement durable. |
| [Plan comptable et comptabilité de durabilité](finance-sustainability-accounts-ledger.md) | Cet article fournit des informations sur la façon de configurer des plans comptables de durabilité (CoSA), des catégories de comptes et des sous-catégories. Et aussi, comment analyser les informations contenues dans les écritures du grand livre de durabilité. |
| [Enregistrer les entrées de durabilité](finance-sustainability-journal.md) | Utilisez cet article pour apprendre à travailler avec tous les types de journaux durabilité. |
| **Génération d’états** |             |
| [Analyse ad hoc des données de durabilité](ad-hoc-analysis-sustainability.md) | Cet article donne des informations sur la manière d’utiliser une analyse ad-hoc afin d’analyser les données de durabilité directement de liste de pages et requêtes. |
| [Rapports de durabilité et analyses dans Business Central](sustainability-reports.md) | Cet article fournit des informations sur l’utilisation des rapports et analyses intégrés liés à la durabilité dans Business Central. |
| **Intégrations** |             |
| [API de durabilité](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json) | Utilisez cet article pour savoir comment créer des applications connectées qui établissent une connexion point à point entre Business Central et des solutions ou services de durabilité hors Microsoft à l’aide d’API. |

## Voir aussi .

[Configuration de durabilité](finance-sustainability-setup.md)    
[Plan comptable et comptabilité de durabilité](finance-sustainability-accounts-ledger.md)    
[Enregistrer les entrées de durabilité](finance-sustainability-journal.md)    
[Analyse ad hoc des données de durabilité](ad-hoc-analysis-sustainability.md)    
[Rapports de durabilité et analyses dans Business Central](sustainability-reports.md)   
[API de durabilité](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Finances](finance.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
