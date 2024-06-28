---
title: FAQ Conversation instantanée avec Copilot
description: Cet article couvre les réponses aux questions courantes sur la conversation instantanée Copilot dans Business Central.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection:
  - bap-ai-copilot
ms.date: 05/17/2024
ms.custom: bap-template jswymer
---
# <a name="chat-with-copilot-faq"></a>FAQ Conversation instantanée avec Copilot

[!INCLUDE[preview-banner](includes/preview-banner.md)]

Cet article couvre les réponses aux questions courantes sur la conversation instantanée Copilot dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour les questions liées à l’IA et au chat, consultez [FAQ sur l’IA responsable pour le chat avec Copilot](faqs-chat-with-copilot.md).

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## <a name="can-admins-grant-or-deny-permission-to-individual-users-to-get-access-to-chat"></a>Les administrateurs peuvent-ils accorder ou refuser l’autorisation à des utilisateurs individuels d’accéder au chat ?

Non, aucune autorisation ou autorisation n’est définie pour le chat. Si le chat est activé sur la page [Capacités Copilot et de l’IA](enable-ai.md) , chaque utilisateur d’un environnement a accès au chat.
 
## <a name="is-chat-available-on-tablet-phone-or-other-form-factors"></a>Le chat est-il disponible sur tablette, téléphone ou autre format ?

Non, le volet de discussion n’est disponible que sur le [!INCLUDE[web_client](includes/web_client.md)] client Web.

## <a name="i-dont-use-business-central-in-english-what-are-my-options"></a>Je n’utilise pas Business Central en anglais. Quelles sont mes options ?

Pour le moment, le chat n’est disponible qu’en anglais. Vous pouvez changer votre langue d’utilisateur en anglais dans [Mes paramètres](ui-change-basic-settings.md#language).

## <a name="what-version-of-business-central-do-i-need-for-chat"></a>De quelle version de Business Central ai-je besoin pour profiter du chat ?

Le chat est disponible en préversion publique à partir de la version 24.0 (1re vague de lancement 2024).

## <a name="does-chat-work-with-my-customizations"></a>Le chat fonctionne-t-il avec mes personnalisations ?

Cela dépend du type de question que vous posez à Copilot. Par exemple :

- Lorsque vous posez des questions pour localiser des enregistrements, Copilot est capable de trouver des enregistrements dans vos tables personnalisées identifiés à l’aide de champs personnalisés.
- Lorsque vous demandez une explication ou des conseils, Copilot n’a accès à aucune information sur vos personnalisations ou à la documentation de vos modules complémentaires.

## <a name="how-do-i-open-a-record-or-page-with-chat"></a>Copilot ne semble jamais ouvrir le dossier ou la page que j’ai demandé. Qu’est-ce que je fais mal ?

Lorsque vous demandez à Copilot de rechercher des enregistrements dans [!INCLUDE[prod_short](includes/prod_short.md)], il affiche tous les enregistrements qu’il trouve sous forme de vignettes ou de liens sélectionnables dans le volet de discussion. En aperçu, Copilot ne navigue automatiquement vers aucune page.

## <a name="why-do-i-get-different-answers-from-copilot-for-the-same-question"></a>Les réponses que je reçois de Copilot varient même si je pose la même question. Est-ce un bug ?

Copilot peut parfois répondre de différentes manières. Les réponses ne sont pas nécessairement identiques.

## <a name="how-do-i-use-the-copy-function-on-chat-messages"></a>Quand dois-je utiliser la fonction Copier sur les messages de chat ?

Vous pouvez utiliser le bouton Copier pour copier un message précédent dans votre conversation avec Copilot, le coller dans la zone de saisie pour réessayer ou essayer une variante de votre message à Copilot.

## <a name="can-i-customize-or-extend-chat"></a>Comment personnaliser ou étendre le chat ?

En aperçu, le volet de discussion et les réponses de Copilot ne peuvent en aucun cas être modifiés par la personnalisation, les compléments ou la personnalisation.

## <a name="does-copilot-search-for-data-in-other-companies-or-environments"></a>Copilot trouve-t-il des données dans d’autres compagnies ou environnements?

Copilot recherche uniquement les enregistrements de l’entreprise à laquelle vous êtes actuellement connecté&mdash; même si votre organisation utilise plusieurs environnements ou entreprises pour séparer les données.

## <a name="what-can-i-do-if-the-chat-pane-doesnt-show"></a>Le volet de discussion Copilot ne s’affiche pas. Que puis-je faire ?

Vérifiez que votre langue d’utilisateur dans Mes paramètres est définie sur l’anglais et que votre environnement est de version 24.0 ou ultérieure. Sur la page Copilot and AI Capabilities, assurez-vous que les administrateurs ont activé le consentement pour les données dans toutes les zones géographiques et ont activé le chat. Assurez-vous que la localisation de votre environnement n’est pas le Canada.

Si vous ne voyez toujours pas la fonctionnalité de discussion avec Copilot, il est possible que Microsoft déploie toujours la fonctionnalité dans votre région. Copilot sera d’abord déployé auprès des clients américains en avril 2024, puis, au fil des semaines, il sera déployé dans d’autres pays/régions.

## <a name="why-does-copilot-only-show-three-records-in-the-chat-pane"></a>Pourquoi Copilot n’affiche-t-il que trois enregistrements dans le volet Chat ?

Lorsque vous demandez à Copilot de récupérer des enregistrements, la façon dont vous formulez la question détermine la manière dont Copilot identifie et applique des filtres sur les pages pour trouver ce que vous recherchez. Pour que les réponses restent compactes et concises, le volet Chat affiche un maximum de trois vignettes d’enregistrement, même lorsque Copilot trouve un plus grand nombre d’enregistrements pertinents.

## <a name="why-does-copilot-give-incorrect-answers-to-calculations"></a>Copilot renvoie des réponses incorrectes aux totaux et autres calculs

En version préliminaire, Chat with Copilot peut localiser des enregistrements, expliquer des concepts et vous guider sur la manière d’effectuer des tâches dans Business Central. D’autres cas d’utilisation ne sont pas pris en charge, tels que l’addition d’un champ dans plusieurs enregistrements ou le calcul du montant mensuel moyen. Nous espérons ajouter des capacités mathématiques de base à Copilot à l’avenir.

## <a name="can-i-use-speech-instead-of-typing-my-prompts"></a>Puis-je utiliser la parole au lieu de taper mes invites ?

Vous pouvez discuter avec Copilot en utilisant la saisie vocale pour parler au lieu de saisir vos mots dans le volet Chat. La saisie vocale utilise la reconnaissance vocale en ligne et est disponible avec Windows. Pour utiliser la voix, activez la boîte de message de discussion, puis utilisez le raccourci <kbd>Windows</kbd>+<kbd>H</kbd>  et commencez à parler. Pour plus d’informations, consultez [Utiliser la saisie vocale pour parler au lieu de taper sur votre PC](https://support.microsoft.com/windows/use-voice-typing-to-talk-instead-of-type-on-your-pc-fec94565-c4bd-329d-e59a-af033fa5689f).

## <a name="next-steps"></a>Étapes suivantes

[Conversation instantanée avec Copilot (version préliminaire)](chat-with-copilot.md)
