---
title: Conversation instantanée avec Copilot (version préliminaire)
description: Découvrez comment utiliser Conversation instantanée avec Copilot pour rechercher des données et obtenir de l’aide dans Business Central.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 03/18/2024
ms.custom: bap-template
ms.collection:
  - bap-ai-copilot
  - get-started
---

# Conversation instantanée avec Copilot (version préliminaire)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

Cet article explique comment discuter avec Copilot pour obtenir des réponses sur les données de votre compagnie et une assistance pour les tâches et les sujets liés à Business Central.

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## A propos de la conversation instantanée avec Copilot

Microsoft Copilot est l’assistant alimenté par l’IA qui aide à stimuler la créativité, à augmenter la productivité et à éliminer les tâches fastidieuses. Vous pouvez discuter avec Copilot dans Business Central pour répondre aux questions et trouver des données métier en exprimant ce que vous recherchez en langage naturel. Vous pouvez utiliser le chat pour :

- Recherchez des données commerciales pour la compagnie avec laquelle vous travaillez dans Business Central. Utilisez le chat pour rechercher (et ouvrir) des données sur les entités/enregistrements liés aux processus métier, tels que les clients, les fournisseurs, les documents de vente, les articles, etc. Par exemple, demandez à Copilot : « Montrez-moi le dernier document de vente pour Adatum. »
- Expliquez un concept ou obtenez des conseils sur la façon d’accomplir une tâche. Par exemple, demandez "Aidez-moi à comprendre les dimensions" ou "Comment reporter un document de vente".
- Comprendre le but et l’utilisation typique des champs individuels. Lorsque vous choisissez **Demander à Copilot** dans une info-bulle pour un champ, le chat s’ouvre avec une invite d’explication pour le nom du champ et Copilot fournit des informations à ce sujet. Copilot renvoie aux articles référencés, il est donc facile de vérifier la description.

  Les réponses fournies par Copilot sont basées uniquement sur la Dynamics 365 Business Central documentation officielle, disponible sur Microsoft Learn à l’adresse [Dynamics 365 Business Central documentation](/dynamics365/business-central/).

Conversation instantanée avec Copilot évite de devoir naviguer dans l’interface utilisateur ou dans l’aide du produit, ce qui permet de gagner du temps et d’augmenter la productivité.
  
> [Regarder la vidéo](https://go.microsoft.com/fwlink/?linkid=2250609)

## Conditions préalables

- Fonctionnalité Conversation instantanée avec Copilot activée. Cette tâche est effectuée par un administrateur. [En savoir plus sur la configuration des fonctionnalités Copilot et IA](enable-ai.md).
- La langue d'affichage dans Business Central est définie sur l'une des versions locales de l’anglais : en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA. . [En savoir plus sur la modification de la langue](ui-change-basic-settings.md#language).
- Votre environnement Business Central se trouve dans n’importe quel pays/région à l’exception du Canada (cette fonctionnalité n’est pas encore disponible au Canada).

## Commencez à utiliser Conversation instantanée avec Copilot

1. Dans le coin supérieur droit de l’écran, sélectionnez le ![Affiche l’icône Conversation instantanée avec Copilot](media/chat-copilot-icon.png) **Copilote** icône ![Affiche la couleur numéro 1](media/callout-number-1.svg).

   Le volet **Copilot** s’affiche sur la droite, comme illustré dans la figure suivante :

    ![Affiche l’icône du volet Conversation instantanée avec Copilot avec des légendes](media/chat-with-copilot-pane.svg)

1. Dans le **poser une question** boîte en bas ![Affiche la légende numéro 2](media/callout-number-2.svg), saisissez votre question, puis sélectionnez la pointe de flèche ou appuyez sur <kbd>Entrer</kbd> pour obtenir une réponse.

   Le texte que vous saisissez, souvent appelé *invite* en termes de Copilot, cela peut prendre la forme d’une question, d’une déclaration ou d’une commande.

   > [!TIP]
   > Copilot comprend quelques fonctionnalités qui peuvent vous aider à rédiger des questions :
   > - Pour commencer à formuler une question, sélectionnez l’un des guides d’invite&mdash;**Trouver**, **Expliquer**, ou **Guide**&mdash;disponible en haut du volet ![Affiche la légende numéro 3](media/callout-number-3.svg) ou du ![Affiche l’icône du guide d’invite](media/prompt-guide-icon.png) **Afficher les invites** icône ci-dessus **poser une question** boîte ![Affiche la légende numéro 4](media/callout-number-4.svg). Les guides d’invite sont de courtes phrases prédéfinies qui commencent une question ou une invite. En plus de vous faire gagner du temps, ils sont conçus pour guider les réponses de Copilot vers une catégorie de réponses. Ils vous aident également à comprendre comment formuler les questions pour obtenir les meilleures réponses.
   > - Sélectionnez les suggestions d’invite au-dessus du **Afficher les invites** bouton ![Affiche la légende numéro 5](media/callout-number-5.svg) pour poser automatiquement une question prédéfinie afin d’avoir un aperçu du fonctionnement des questions et des réponses. Les suggestions rapides ne sont disponibles que lorsque vous utilisez la compagnie de démonstration CRONUS.

1. Passez en revue les réponses affichées dans le volet Copilot ![Affiche la légende numéro 6](media/callout-number-6.svg).

   En fonction de votre question, la réponse peut contenir du texte, des liens vers des enregistrements ou des pages dans Business Central, ainsi que des liens vers des articles d’aide de Business Central sur Microsoft Learn.

1. Posez une autre question pour affiner la réponse.

   Chat mémorise le contexte, ce qui signifie que vous n’avez pas besoin de répéter les points clés de la question d’origine.

## Effacer le chat pour recommencer

Si vous souhaitez passer à un autre sujet de conversation avec Copilot, sélectionnez le ![Affiche l’icône de discussion claire](media/clear-chat-icon.png) **Démarrer une nouvelle session de discussion Copilot** icône en bas du volet Copilot au-dessus de la boîte de questions. Cette action efface la mémoire de Copilot de vos derniers messages. Recommencer est souvent utile après une longue conversation avec de nombreux messages, et cela peut aider Copilot à fournir des réponses plus précises.

Le chat est également effacé si vous fermez ou vous déconnectez de Business Central.

## <a name="tips"></a>Tirer le meilleur parti de vos questions

Cette section fournit des moyens vous permettant d’améliorer les réponses que vous obtenez de Copilot.

- Poser des questions claires et précises.
- Soyez concis et évitez les phrases longues ou multiples.
- Posez une question à la fois. <!--Avoid asking about multiple questions in one message.-->
- Utilisez un langage naturel, en exprimant les questions de manière amicale et conversationnelle.
- Utilisez des mots-clés, des expressions et des termes dont vous savez qu’ils sont utilisés dans Business Central, que ce soit dans l’application ou dans la documentation.
- Si la réponse initiale ne répond pas entièrement à vos questions, posez des questions complémentaires ou reformulez la dernière question.
- Si vous posez une question sur un sujet différent de la question précédente, effacez la session de discussion en cours pour recommencer.

## Exemples d’invites

Vos questions à Copilot varient naturellement en fonction de votre rôle, de votre tâche actuelle, des processus suivis par votre organisation et de la façon dont vous vous exprimez avec des mots. Les exemples suivants présentent différentes façons de poser des questions dans le volet de discussion et peuvent vous inciter à rédiger vos propres questions en fonction de votre propre situation.

Invite : `Find the Item with Description 'ATHENS Desk'`

Dans cet exemple, vous donnez des instructions claires à Copilot pour localiser un seul enregistrement. Par exemple, vous laissez entendre que l’enregistrement se trouve dans la liste Éléments. Vous indiquez que le champ ’Description’ doit être un texte spécifique que vous avez tapé en utilisant des guillemets et avec une utilisation correcte des majuscules. Copilot répond généralement avec précision lorsqu’on lui donne quelques indices précis, mais vous pouvez également utiliser un langage plus informel comme dans l’exemple suivant.

Invite : `give me the latest invoice for adatum`

Dans cet exemple, vous demandez à Copilot de localiser un enregistrement, mais la question est moins précise et peut entraîner une réponse moins précise. Copilot peut souvent comprendre, ou deviner, que la facture que vous recherchez n’est pas une facture d’achat mais une facture de vente issue de la liste des factures de vente reportées. Copilot devra également faire correspondre `adatum` avec `Adatum Corporation`, c’est-à-dire le nom complet et précis du nom du client vendeur associé à la facture.

Invite : `Show me customer ledger entries for Adatum from about three weeks ago`

Dans cet exemple, vous demandez au copilote de résoudre un casse-tête de date courant qui nécessite généralement que vous ouvriez un calendrier pour référence ou que vous utilisiez des filtres de plage de dates avancés. Copilot peut généralement comprendre les expressions courantes et les termes commerciaux.

Invite : `How does I save my filterrings to do them later?`

Dans cet exemple, vous demandez à Copilot des conseils sur la façon d’effectuer certaines tâches dans Business Central. Copilot peut généralement comprendre l’intention de votre question, même s’il y a quelques erreurs grammaticales, fautes d’orthographe ou abréviations.

Invite : `Provide feedback on answers`

Vous pouvez évaluer les réponses que vous obtenez de Copilot en utilisant le bouton J’aime (pouce levé) pour une bonne note ou le bouton Je n’aime pas (pouce vers le bas) pour une mauvaise note. Lorsque vous sélectionnez le bouton Je n’aime pas, vous pouvez choisir une raison, notamment inexacte, inappropriée ou autre. Ces informations peuvent nous aider à améliorer les suggestions.

<!--
1. If you want help getting you're question started, select the prompts either from the **Find**, **Explain**, or **Guide** buttons at the top of the Coplit pane or use the **View Prompts** menu above **Ask a question** box at the bottom.

   Prompts are predefined short phrases that start a question. Apart from saving you time, they're designed to target responses to specific categories. They also help you undestand how you can phrase questions to get the responses.-->
## Voir aussi .

[Résoudre les problèmes des fonctionnalités de Copilot et d’IA](ai-copilot-troubleshooting.md)  
[Configuration des fonctionnalités de Copilot et d’IA](enable-ai.md)  
[FAQ sur l’IA responsable pour la discussion instantanée avec Copilot](faqs-chat-with-copilot.md)  
[Ressources d’aide dans Business Central](product-help-and-support.md)  
