---
title: FAQ Conversation instantanée avec Copilot
description: Cet article couvre les réponses aux questions courantes sur la conversation instantanée Copilot dans Business Central.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: conceptual
ms.collection:
  - bap-ai-copilot
ms.date: 02/27/2024
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

## <a name="which-business-central-version-do-i-need-to-experience-chat"></a>De quelle version de Business Central ai-je besoin pour profiter du chat ?

Le chat est disponible en préversion publique à partir de la version 24.0 (1re vague de lancement 2024).

## <a name="does-chat-work-with-my-customizations"></a>Le chat fonctionne-t-il avec mes personnalisations ?

Cela dépend du type de question que vous posez à Copilot. Par exemple :

- Lorsque vous posez des questions pour localiser des enregistrements, Copilot est capable de trouver des enregistrements dans vos tables personnalisées identifiés à l’aide de champs personnalisés.
- Lorsque vous demandez une explication ou des conseils, Copilot n’a accès à aucune information sur vos personnalisations ou à la documentation de vos modules complémentaires.

## <a name="copilot-never-seems-to-open-the-record-or-page-i-asked-for-what-am-i-doing-wrong"></a>Copilot ne semble jamais ouvrir le dossier ou la page que j’ai demandé. Qu’est-ce que je fais mal ?

Lorsque vous demandez à Copilot de rechercher des enregistrements dans [!INCLUDE[prod_short](includes/prod_short.md)], il affiche tous les enregistrements qu’il trouve sous forme de vignettes ou de liens sélectionnables dans le volet de discussion. En aperçu, Copilot ne navigue automatiquement vers aucune page.

## <a name="the-answers-i-get-from-copilot-vary-even-though-i-ask-the-same-question-is-it-a-bug"></a>Les réponses que je reçois de Copilot varient même si je pose la même question. Est-ce un bug ?

Copilot peut parfois répondre de différentes manières. Les réponses ne sont pas nécessairement identiques.

## <a name="when-should-i-use-the-copy-function-on-chat-messages"></a>Quand dois-je utiliser la fonction Copier sur les messages de chat ?

Vous pouvez utiliser le bouton Copier pour copier un message précédent dans votre conversation avec Copilot, le coller dans la zone de saisie pour réessayer ou essayer une variante de votre message à Copilot.

## <a name="how-do-i-customize-or-extend-chat"></a>Comment personnaliser ou étendre le chat ?

En aperçu, le volet de discussion et les réponses de Copilot ne peuvent en aucun cas être modifiés par la personnalisation, les compléments ou la personnalisation.

## <a name="does-copilot-find-data-in-other-companies-or-environments"></a>Copilot trouve-t-il des données dans d’autres compagnies ou environnements?

Même si votre organisation utilise plusieurs environnements ou compagnies pour séparer les données, Copilot recherche uniquement les enregistrements dans la compagnie à laquelle vous êtes actuellement connecté.

## <a name="the-copilot-chat-pane-doesnt-show-what-can-i-do"></a>Le volet de discussion Copilot ne s’affiche pas. Que puis-je faire ?

Vérifiez que votre langue d’utilisateur dans Mes paramètres est définie sur l’anglais et que votre environnement est de version 24.0 ou ultérieure. Sur la page Copilot and AI Capabilities, assurez-vous que les administrateurs ont activé le consentement pour les données dans toutes les zones géographiques et ont activé le chat. Assurez-vous que la localisation de votre environnement n’est pas le Canada.

Si vous ne voyez toujours pas la fonctionnalité de discussion avec Copilot, il est possible que Microsoft la déploie toujours dans votre région. Copilot sera d’abord déployé auprès des clients américains en avril 2024, puis, au fil des semaines, dans d’autres pays.

## <a name="next-steps"></a>Étapes suivantes

[Conversation instantanée avec Copilot (version préliminaire)](chat-with-copilot.md)
