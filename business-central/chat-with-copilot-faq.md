---
title: FAQ Conversation instantanée avec Copilot
description: 'Apprenez à discuter avec Copilot, un assistant virtuel qui vous aide à utiliser Business Central. Trouvez des réponses aux questions courantes sur les fonctionnalités, les paramètres et les limitations du chat.'
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection:
  - bap-ai-copilot
ms.date: 06/13/2024
ms.custom: bap-template jswymer
---
# FAQ Conversation instantanée avec Copilot

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Cet article couvre les réponses aux questions courantes sur la conversation instantanée Copilot dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour les questions liées à l’IA et au chat, consultez [FAQ sur l’IA responsable pour le chat avec Copilot](faqs-chat-with-copilot.md).

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Les administrateurs peuvent-ils accorder ou refuser l’autorisation à des utilisateurs individuels d’accéder au chat ?

Non, aucune autorisation ou autorisation n’est définie pour le chat. Si le chat est activé sur la page [Capacités Copilot et de l’IA](enable-ai.md) , chaque utilisateur d’un environnement a accès au chat.
 
## Le chat est-il disponible sur tablette, téléphone ou autre format ?

Non, le volet de discussion n’est disponible que sur le [!INCLUDE[web_client](includes/web_client.md)] client Web.

## Je n’utilise pas Business Central en anglais. Quelles sont mes options ?

Pour le moment, le chat n’est disponible qu’en anglais. Vous pouvez changer votre langue d’utilisateur en anglais dans [Mes paramètres](ui-change-basic-settings.md#language).

## De quelle version de Business Central ai-je besoin pour du chat ?

Le chat est disponible en préversion publique à partir de la version 24.0 (1re vague de lancement 2024).

## Le chat fonctionne-t-il avec mes personnalisations ?

Cela dépend du type de question que vous posez à Copilot. Par exemple :

- Si vous posez des questions pour rechercher des enregistrements, il peut rechercher des enregistrements dans vos tables personnalisées qui utilisent des champs personnalisés.
- Lorsque vous demandez une explication ou des conseils à Copilot, n’a accès à aucune information sur vos personnalisations ou à la documentation de vos modules complémentaires.

## Comment ouvrir un enregistrement ou une page avec chat ?

Lorsque vous demandez à Copilot de rechercher des enregistrements dans [!INCLUDE[prod_short](includes/prod_short.md)], il affiche tous les enregistrements qu’il trouve sous forme de vignettes ou de liens sélectionnables dans le volet de discussion. En aperçu, Copilot ne navigue automatiquement vers aucune page.

## Pourquoi est-ce que je reçois des réponses différentes de Copilot pour la même question ?

Copilot peut parfois répondre de différentes manières. Les réponses ne sont pas Toujours identiques.

## Comment dois-je utiliser la fonction Copier sur les messages de chat ?

Vous pouvez utiliser le bouton Copier pour copier un message précédent dans votre conversation avec Copilot, le coller dans la zone de saisie pour réessayer ou essayer une variante de votre message à Copilot.

## Comment personnaliser ou étendre le chat ?

En aperçu, le volet de discussion et les réponses de Copilot ne peuvent en aucun cas être modifiés par la personnalisation, les compléments ou la personnalisation.

## Copilot recherche-t-il des données dans d’autres compagnies ou environnements?

Copilot recherche uniquement les enregistrements de la compagnie à laquelle vous êtes actuellement connecté. Il ne recherche pas de données dans plusieurs environnements ou compagnies.

## Que puis-je faire si le volet de discussion ne s’affiche pas ?

Vérifiez que votre langue d’utilisateur dans **Mes paramètres** est définie sur l’anglais et que votre environnement est de version 24.0 ou ultérieure. Sur la page Copilot and AI Capabilities, assurez-vous que l’administrateurs a activé le consentement pour les données dans toutes les zones géographiques et ont activé le chat. Assurez-vous aussi que la localisation de votre environnement n’est pas le Canada.

Si vous ne voyez toujours pas la fonctionnalité de discussion avec Copilot, il est possible que Microsoft déploie la fonction toujours dans votre région. Copilot sera d’abord déployé auprès des clients américains en avril 2024, puis, au fil des semaines, dans d’autres pays/région.

## Pourquoi Copilot n’affiche-t-il que trois enregistrements dans le volet Chat ?

Lorsque vous demandez à Copilot de rechercher des enregistrements, la façon dont vous formulez la question détermine la manière dont Copilot identifie et applique des filtres sur les pages pour trouver ce que vous recherchez. Pour que les réponses restent concises, le volet Chat affiche un maximum de trois vignettes d’enregistrement, même lorsque Copilot trouve des enregistrements plus pertinents.

## Pourquoi Copilot donne-t-il des réponses incorrectes aux calculs ?

En version préliminaire, Conversation instantanée avec Copilot peut vous aider à rechercher des enregistrements, à expliquer des concepts et à vous guider sur la manière d’effectuer des tâches dans Business Central. D’autres cas d’utilisation ne sont pas pris en charge, tels que l’addition d’un champ dans plusieurs enregistrements ou le calcul du montant mensuel moyen. Nous espérons ajouter des capacités mathématiques de base à Copilot à l’avenir.

## Puis-je utiliser la parole au lieu de taper mes invites ?

Vous pouvez discuter avec Copilot en utilisant la saisie vocale pour parler au lieu de saisir vos mots dans le volet Chat. La saisie vocale utilise la reconnaissance vocale en ligne et est disponible avec Windows. Pour utiliser la voix, activez la boîte de message de chat, puis utilisez le <kbd>Windows</kbd>+<kbd>H</kbd> raccourci et commencez à parler. Pour plus d’informations, voir [Utilisez la saisie vocale pour parler au lieu de taper sur votre PC](https://support.microsoft.com/windows/use-voice-typing-to-talk-instead-of-type-on-your-pc-fec94565-c4bd-329d-e59a-af033fa5689f).

## Étapes suivantes

- [Conversation instantanée avec Copilot (version préliminaire)](chat-with-copilot.md)
