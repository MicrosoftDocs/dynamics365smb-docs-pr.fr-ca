---
title: Configurer les capacités Copilot et IA
description: Cet article explique comment activer Copilot sur un environnement.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 02/27/2024
ms.custom: bap-template
ms.search.form: 7775
ms.collection:
  - bap-ai-copilot
---

# Configuration des fonctionnalités de Copilot et d’IA 

<!--[!INCLUDE[ai-preview](includes/ai-preview.md)]-->

<!--This article explains how you can control the ability to create AI-powered item marketing text with Copilot for your organization. This task is done by an admin. There are two requirements that you must fulfill to make the feature available to users:-->

Cet article explique comment contrôler Copilot et d’autres fonctionnalités de l’IA dans Business Central. Cette tâche est effectuée par un administrateur. Copilot est une fonctionnalité système et fait partie intégrante de Business Central. Comme pour la plupart des fonctionnalités du système, vous n’accordez pas l’accès à des utilisateurs individuels et vous ne pouvez pas non plus activer ou désactiver Copilot. Cependant, Copilot offre des contrôles de gouvernance des données et la possibilité de désactiver les capacités individuelles de Copilot et d’IA pour chaque environnement. Il existe différents niveaux de contrôle d’accès aux fonctionnalités d’IA, en fonction de la fonctionnalité :

- Autoriser le mouvement des données entre les régions géographiques.

  Cette tâche n’est requise que si votre environnement Business Central se trouve dans une zone géographique autre que celle qu’Azure OpenAI Service utilise. [en savoir plus](#allow-data-movement-across-geographies)

- Activez la fonctionnalité sur la page **Fonctionnalités de Copilot et de l’IA**. [en savoir plus](#activate-features)

<!-- For 2024 there are no AI features governed by **Feature Management**, so this section is not shown
- Enable the specific feature if it's governed by **Feature Management**.

  Check whether  of 2024 release wave 1, chat with Copilot, marketing text suggestions, and bank account reconciliation assist features are included under **Feature Management**. [Learn more](#enable-feature-in-feature-management)
<!-- 
- Enable the specific feature, if it's still governed by **Feature Management**.

  In 2023 release wave 2, both the marketing text suggestions and bank account reconciliation assist features are included under **Feature Management**. [Learn more](#enable-feature-in-feature-management)-->

Si l’une de ces conditions n’est pas remplie, la fonctionnalité ne peut pas être utilisée.-->

## Conditions préalables

- Vous utilisez Business Central Online <!--[preview version](ai-preview-getstarted.md) of Business Central that's enabled for Copilot.-->
- Vous disposez des autorisations d’administrateur ou de super autorisations dans Business Central.  <!--For more information, go to [Configure AI-powered item marketing text with Copilot](enable-ai.md).-->

## Autoriser le déplacement des données entre les zones géographiques

Cette tâche s’applique uniquement si le commutateur **Autoriser le mouvement des données** s’affiche en haut de l’écran **Fonctionnalités de Copilot et de l’IA**. Si le lien **Comment gérer les données de mon copilote ?** s’affiche à la place du bouton **Autoriser le déplacement des données**, ignorez cette étape.

![Affiche une capture d’écran du commutateur Autoriser le mouvement des données sur Copilot et Page Capacités de l’IA.](media/allow-data-movement-v2.png)

Le commutateur **Autoriser le déplacement des données** indique que l’emplacement de votre environnement Business Central&mdash;c’est-à-dire la région où les données sont traitées et stockées&mdash;n’est pas la même que la région d’Azure OpenAI Service utilisée par Copilot. Si vous souhaitez activer Copilot, vous devez autoriser le déplacement des données entre les régions. Pour en savoir plus sur le déplacement des données, consultez [Déplacement des données Copilot entre régions](ai-copilot-data-movement.md). 

Pour autoriser le déplacement des données en dehors de votre région géographique, procédez comme suit :

1. Dans Business Central, recherchez et ouvrez la page **Fonctionnalités Copilot et de l’IA**.
1. Activez le commutateur **Autoriser le déplacement des données**.

   Le commutateur **Autoriser le déplacement des données** est activé par défaut pour les environnements dans les régions Azure d’Europe de l’Ouest et d’Europe du Nord.

Vous pouvez désactiver le déplacement des données en désactivant le commutateur **Autoriser le déplacement des données**. Une fois qu’un Azure OpenAI Service est disponible dans la région de votre environnement Business Central, votre environnement y est automatiquement connecté et le commutateur n’est plus disponible.

<!-- Don't review
| Australia, United Kingdom, United States | Within the respective geographical region |
| Europe, France, Germany, Norway, Switzerland  | Sweden or Switzerland |
| Asia Pacific, Brazil, Canada, India, Japan, Singapore, South Africa, South Korea, United Arab Emirates  | United States |-->



<!--Note

If your environment is hosted in North America, Copilot will use an Azure OpenAI endpoint in North America to process your data.
If your environment is hosted in Europe, Copilot will use an Azure OpenAI endpoint in Europe to process your data.
If your environment is hosted anywhere else, Copilot will use an Azure OpenAI endpoint outside of the region in which the environment is hosted.
To opt in 

Copilot and other AI capabilities use Azure OpenAI Service.  and are provided by default to only those customers with environments that have United States as their geography for data processing and storage. While the Azure OpenAI Service is available in multiple geographies including Australia, Canada, United States, France, Japan and UK, Copilot does not follow the same regional rollout schedule.

Meanwhile, customers with environments outside the United States can use Copilot AI features by opting in to share relevant data with the Azure OpenAI Service in United States or Switzerland.

The information in the following table outlines the Azure OpenAI service that's used by the Copilot services based on the geography of their Dynamics 365 environment when they opt-in to share data.-->

## Activer les fonctionnalités

Toutes les fonctionnalités de Copilot et d’IA sont actives par défaut lorsqu’elles sont mises à disposition en avant-première ou lorsqu’elles deviennent généralement disponibles. Via la page **Fonctionnalités de Copilot et de l’IA**, vous pouvez désactiver ou réactiver des fonctionnalités individuelles pour tous les utilisateurs.

1. Dans Business Central, recherchez et ouvrez la page **Fonctionnalités Copilot et de l’IA**.

1. La page répertorie toutes les fonctionnalités disponibles liées à Copilot et à l’IA et leur état actuel, qui peut être actif ou inactif. Les fonctionnalités sont divisées en deux sections&mdash;une section pour les fonctionnalités en version préliminaire et une autre pour les fonctionnalités généralement disponibles. 

   [![Affiche le tableau de bord Business Central et la liste de vérification pour Copilot](media/copilot-and-ai-capabilties-page.svg)](media/copilot-and-ai-capabilties-page.svg#lightbox)

   - Pour activer une fonctionnalité, sélectionnez-la dans la liste, puis sélectionnez l’action **Activer**.
   - Pour désactiver une fonctionnalité, sélectionnez-la, puis sélectionnez l’action **Désactiver**. 

<!-- don't review 

<!-- For 2024 there are no AI features governed by **Feature Management**, so this section is not shown
## Enable feature in Feature Management

When individual Copilot capabilities are released in Business Central minor updates, these capabilities are optional until the next major update. **Feature Management** is used to turn on or off features that are in preview, like bank reconciliation, and some features that are generally available, like marketing text suggestions. [Learn more about feature management](/dynamics365/business-central/dev-itpro/administration/feature-management).

1. In Business Central, search for and open the **Feature Management** page.
2. To enable a feature, set the **Enabled for** column to **All users**. To disable a feature, set the **Enabled for** column to **None**. Use the following table to help you determine the switch that applies to the Copilot and AI capability you want to enable:

   - **Feature Preview: Bank account reconciliation with Copilot** enables the bank account reconciliation assist feature.
   - **Feature Preview: Chat with Copilot** enables the chat with Copilot feature.
   - **Feature preview: Create AI-powered product descriptions with Copilot** enables the marketing text suggestions feature.

   For more information about feature management in general, go to [Feature Management](/dynamics365/business-central/dev-itpro/administration/feature-management).-->

## Accorder l’accès utilisateur

Les capacités Copilot et IA peuvent offrir des fonctionnalités destinées à tous les utilisateurs de votre organisation ou à des rôles d’utilisateur spécifiques. La plupart des fonctionnalités de Copilot et d’IA offrent un contrôle d’accès à l’aide d’autorisations et d’ensembles d’autorisations dans le système de gestion des autorisations de Business Central. [En savoir plus sur les autorisations et les ensembles d’autorisations](ui-define-granular-permissions.md).

Le tableau suivant répertorie les autorisations requises pour utiliser les fonctionnalités Copilot fournies par Business Central.

|Fonctionnalités Copilot|Autorisations requises|
|-|-|
|Assistance pour les analyses|**ANALYSE DES DONNÉES – EXEC** ensemble d'autorisations définir ou exécuter l’autorisation sur l’objet système 9640 **Autoriser le mode d’analyse des données**. Ce sont les mêmes autorisations nécessaires pour accéder au mode analyse.|
|Aide au rapprochement bancaire|Autorisation à la page 7250 **Compte bancaire. Rec. Proposition AI** et page 7252 **Trans. Vers GL Acc. Proposition d’IA**.|
|Discuter |Il n’existe aucune autorisation ou ensemble d’autorisations qui contrôlent l’accès au chat par utilisateur. Si le chat est activé, il est disponible pour tous les utilisateurs.|
|Suggestions de texte marketing |Autorisation à la page 5836 **Texte marketing Copilot**|

Pour accorder ou refuser l’accès à des fonctionnalités non Microsoft Copilot et IA spécifiques, consultez la documentation ou l’éditeur de cette fonctionnalité pour identifier les autorisations requises.

## Étapes suivantes

Après avoir activé et accepté les fonctionnalités, vous êtes prêt à les essayer. Accédez à :

- [Ajouter du texte marketing aux articles](item-marketing-text.md)
- [Analyse des données dans le mode d'analyse avec Copilot](analysis-assist.md)  
- [Conversation instantanée avec Copilot](chat-with-copilot.md)
- [Rapprocher à l’aide de l’assistant de rapprochement de compte bancaire](bank-reconciliation-with-copilot.md)

## Voir aussi .

[Résoudre les problèmes des fonctionnalités de Copilot et d’IA](ai-copilot-troubleshooting.md)  
[FAQ sur l’assistance pour les analyses](faqs-analysis-assist.md)  
[FAQ pour l’aide au rapprochement bancaire](faqs-bank-reconciliation.md)  
[FAQ sur la conversation instantanée avec Copilot](faqs-chat-with-copilot.md)  
[FAQ pour les suggestions de texte marketing](faqs-marketing-text.md)  
[Vue d’ensemble des suggestions de texte marketing](ai-overview.md)  