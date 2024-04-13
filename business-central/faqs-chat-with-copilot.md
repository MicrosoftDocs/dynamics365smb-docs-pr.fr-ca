---
title: FAQ sur l’IA responsable pour Conversation instantanée avec Copilot (version préliminaire)
description: 'Cette FAQ fournit des informations sur la technologie d’IA utilisée pour discuter avec Copilot dans Business Central. Elle comprend également des éléments à prendre en compte et des détails clés sur la façon dont l’IA est utilisée, comment elle a été testée et évaluée, et toutes les limitations spécifiques.'
ms.date: 03/18/2024
ms.custom:
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: 'copilot, AI, chat'
---
# FAQ sur l’IA responsable pour Conversation instantanée avec Copilot (version préliminaire)

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

Cette foire aux questions (FAQ) décrit l’impact de l’IA dans la conversation avec Copilot dans [!INCLUDE[prod_short](includes/prod_short.md)]. Si vous êtes intéressé par les questions générales sur l’utilisation de cette fonctionnalité, accédez à [FAQ pour Conversation instantanée avec Copilot](chat-with-copilot-faq.md).

## Qu'est-ce qu'une Conversation instantanée avec Copilot ?

Microsoft Copilot est l’assistant alimenté par l’IA qui aide à stimuler la créativité, à augmenter la productivité et à éliminer les tâches fastidieuses. Vous pouvez discuter avec Copilot dans Business Central pour répondre aux questions et trouver des données métier en exprimant ce que vous recherchez en langage naturel.

Conversation instantanée avec Copilot, également appelé chat, est une fonctionnalité interactive qui répond aux questions et recherche des données commerciales liées à [!INCLUDE[prod_short](includes/prod_short.md)], sans que les utilisateurs aient à naviguer dans l’interface utilisateur ou dans la documentation du produit. Le volet Copilot est disponible partout dans le [!INCLUDE[prod_short](includes/prod_short.md)] client.

Les utilisateurs posent des questions en langage naturel, telles que "Comment puis-je livrer des marchandises à mes clients directement depuis mes fournisseurs ? » Ou "Avons-nous des chaises de bureau en stock pour moins de 600 $ ?" En réponse, Copilot fournit des réponses en langage naturel. Selon les questions, les réponses peuvent inclure du texte brut, des liens vers des enregistrements ou des pages dans [!INCLUDE[prod_short](includes/prod_short.md)], et des liens vers [!INCLUDE[prod_short](includes/prod_short.md)] articles d’aide sur Microsoft Learn.

## Quelles sont les fonctionnalités de Conversation instantanée avec Copilot ?

Vous pouvez discuter avec Copilot pour obtenir des réponses aux catégories de questions suivantes :

### Expliquer et guider

Les utilisateurs peuvent demander à Copilot d’expliquer un concept spécifique lié à [!INCLUDE[prod_short](includes/prod_short.md)], comme ce que sont les dimensions, ou fournir des conseils sur la façon d’accomplir une tâche, comme comment reporter un document de vente. Copilot fouille le fonctionnaire [!INCLUDE[prod_short](includes/prod_short.md)] documentation publiée par Microsoft et fournit une réponse basée sur la documentation.

- Copilot utilise les connaissances sur Microsoft Learn (pas une recherche Web étendue) pour effectuer une recherche sémantique uniquement dans Dynamics 365 [!INCLUDE[prod_short](includes/prod_short.md)] documentation sur Microsoft Learn.

- Copilot n’agit pas, ne crée pas de nouvelles données et ne modifie aucune configuration. Il résume simplement tous les paragraphes qu’il trouve sur Microsoft Learn qui correspondent à la question ou à l’invite dans le chat.

### Rechercher des données d’entreprise et des pages associées

Les utilisateurs peuvent demander à Copilot de localiser les pages par nom ou demander des enregistrements en fonction de leurs champs et contraintes. Si Copilot trouve une correspondance, il répond avec un lien vers l’enregistrement ou la page concernée, que l’utilisateur peut ensuite choisir d’ouvrir.

- Copilot convertit l’entrée en langage naturel en une requête composée de critères de recherche, de tri et de filtrage dans une table.

  La capacité utilise les capacités natives de recherche de données de [!INCLUDE[prod_short](includes/prod_short.md)] pour trouver des données correspondantes à partir de tables au sein de la base de données des compagnies. La recherche s’exécute sous la propre identité de l’utilisateur pour des raisons de sécurité et de conformité. Il ne recherche pas en dehors du [!INCLUDE[prod_short](includes/prod_short.md)] base de données.

- Copilot n’agit pas, ne crée pas de nouvelles données et ne modifie aucune configuration. Il résume uniquement les dossiers reçus du [!INCLUDE[prod_short](includes/prod_short.md)] recherche de données natives. 

## Quelle est l’utilisation prévue de Conversation instantanée avec Copilot ?

La Conversation instantanée est conçu pour une utilisation en entreprise et pour répondre aux questions relatives à [!INCLUDE[prod_short](includes/prod_short.md)] et les données métier qu’il contient. La fonctionnalité permet aux utilisateurs de résoudre des tâches courantes telles que rechercher des enregistrements ou obtenir des conseils en s’exprimant dans leurs propres mots, ce qui rend le travail plus facile et plus accessible. [!INCLUDE[prod_short](includes/prod_short.md)].

## Comment Conversation instantanée avec Copilot a-t-il été évalué ? Quelles mesures sont utilisées pour évaluer les performances ?

- La fonctionnalité a subi des tests approfondis au cours desquels de nombreux textes en anglais couvrant un large éventail de sujets et de styles d’expression d’intention ont été remis à Copilot. Les résultats ont été évalués en fonction de leur exactitude, de leur pertinence et de leur sécurité.
- La fonctionnalité est conçue conformément à la Norme IA Responsable de Microsoft. [Découvrez-en davantage sur l’IA responsable auprès de Microsoft](https://aka.ms/RAI).

## Comment Microsoft surveille-t-il la qualité du contenu généré ?

Microsoft a mis en place divers systèmes pour garantir que le contenu généré par Copilot est de la plus haute qualité, détecter les abus et garantir la sécurité de nos clients et de leurs données.

Les utilisateurs ont la possibilité de fournir des commentaires sur chaque réponse Copilot et de signaler tout contenu inexact ou inapproprié pour aider Microsoft à améliorer cette fonctionnalité. 

- Vous fournissez des commentaires en utilisant l’icône J’aime (pouce levé) ou Je n’aime pas (pouce vers le bas) sur la volet **Copilot** dans [!INCLUDE[prod_short](includes/prod_short.md)].
- Nous analysons et utilisons les commentaires des utilisateurs sur la fonctionnalité pour nous aider à améliorer les réponses.
- Si vous rencontrez un contenu généré inapproprié, signalez-le à Microsoft en utilisant ce formulaire de commentaires : [Signaler un abus](https://go.microsoft.com/fwlink/?linkid=2249810).
- Microsoft peut désactiver les fonctionnalités pilotées par Copilot pour certains clients si un abus de la fonctionnalité est détecté.

## Quelle sont les limites de Conversation instantanée avec Copilot ? Comment les utilisateurs peuvent-ils minimiser l’impact des limitations Conversation instantanée avec Copilot lors de l’utilisation du système ?

- Limitations générales de l'IA

  Les systèmes d’IA sont des outils précieux, mais ils ne sont pas déterministes. Le contenu qu’ils génèrent peut ne pas être totalement exact. Il est donc important d’utiliser votre jugement pour examiner et vérifier les réponses de Copilot avant de prendre des décisions qui pourraient affecter les parties prenantes telles que les clients et les partenaires. Pour la plupart des réponses, Copilot inclura également des citations ou des liens de référence que vous pourrez utiliser pour vérifier rapidement si Copilot a trouvé la bonne réponse. Par exemple, lorsqu’on lui demande comment effectuer une tâche, Copilot inclut des liens vers l’article source. Lorsqu’on lui demande de rechercher un enregistrement en fonction de critères spécifiques, Copilot inclut des liens qui décrivent la page de liste qu’il a identifiée comme sujet de conversation, ainsi que tous les filtres ou tris appliqués pour obtenir une réponse.

- Limites linguistiques

  - La Conversation instantanée n’est pris en charge qu’en anglais pour les langues suivantes : en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA. .

    Si la langue d’affichage [!INCLUDE[prod_short](includes/prod_short.md)] ne fait pas partie de ces paramètres régionaux, le chat n’est pas disponible.

  - La qualité des réponses peut être moindre dans les conditions suivantes :
    - La langue locale est différente de en-US.
    - Lorsque le paramètre de langue de l’utilisateur dans [!INCLUDE[prod_short](includes/prod_short.md)] diffère de la langue principale des données dans la [!INCLUDE[prod_short](includes/prod_short.md)] base de données.

- Limitations spécifiques au secteur, au produit et au sujet

   La Conversation instantanée comprend des mécanismes de sécurité intégrés qui empêchent la génération indésirable de contenus préjudiciables, tels que des contenus sexuellement explicites ou des incitations à la violence. Parfois, les clients opèrent dans des secteurs, vendent des produits et des services, ou travaillent avec des processus qui chevauchent naturellement ce qui pourrait être considéré comme inapproprié dans d’autres contextes, ou travaillent avec des données susceptibles de déclencher ces protections. La Conversation instantanée peut ne pas fonctionner aussi bien dans ces cas-là.

<!--## What operational factors and settings allow for effective and responsible use of the feature?-->

## Quelles données Conversation instantanée avec Copilot collecte-t-il et comment sont-elles utilisées

Microsoft n’utilise pas les données de votre compagnie, y compris le texte que vous envoyez à Copilot, pour former les modèles d’IA fondamentaux au profit des autres. Les administrateurs de la compagnie ont un contrôle total pour gérer ces données qui font partie de leur abonnement Azure. Étant donné que les administrateurs ou d’autres personnes de votre compagnie peuvent avoir accès à ces données, comme déterminé par votre employeur, nous recommandons aux utilisateurs de ne pas saisir de données sensibles telles que des mots de passe ou d’autres secrets.

## Qu’offre Conversation instantanée avec Copilot pour la sécurité

Conversation instantanée est conçu pour être sécurisé et s’exécute sous l’identité de l’utilisateur, héritant de toutes les autorisations de sécurité et autres restrictions et ne fonctionnant jamais en dehors de la sécurité de la plateforme [!INCLUDE[prod_short](includes/prod_short.md)]. Cela signifie que Copilot ne peut accéder qu’aux données auxquelles l’utilisateur a accès.

Pour les utilisateurs disposant de l’autorisation SUPER, le chat peut localiser plus facilement les données non sécurisées qui sont généralement plus difficiles d’accès pour les autres utilisateurs. Les organisations qui n’appliquent pas le modèle de sécurité [!INCLUDE[prod_short](includes/prod_short.md)] pour restreindre les tables et les objets auxquels chaque utilisateur ou rôle d’utilisateur a accès peuvent courir un risque élevé lorsqu’elles utilisent le chat. Par conséquent, nous recommandons à votre organisation de mettre en œuvre le modèle de sécurité [!INCLUDE[prod_short](includes/prod_short.md)] ou de désactiver le chat.

## Voir aussi .

[Conversation instantanée avec Copilot (version préliminaire)](chat-with-copilot.md)

