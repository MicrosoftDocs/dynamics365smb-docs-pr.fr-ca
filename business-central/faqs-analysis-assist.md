---
title: FAQ sur l’assistance pour les analyses (version préliminaire)
description: 'Cette FAQ fournit des informations sur la technologie d’IA utilisée pour analyser les données des pages dans Business Central. Elle comprend également des éléments à prendre en compte et des détails clés sur la façon dont l’IA est utilisée, comment elle a été testée et évaluée, et toutes les limitations spécifiques.'
ms.date: 02/13/2024
ms.custom:
  - responsible-ai-faqs
ms.topic: article
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.search.keywords: 'copilot, AI'
ms.collection:
  - bap-ai-copilot
---

# FAQ sur l’assistance pour les analyses (version préliminaire)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

Cette foire aux questions (FAQ) décrit l’impact de la fonctionnalité analyser les données sur l’IA dans [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## Qu'est-ce Assistance pour les analyses ?

L’assistance à l’analyse est un copilote qui fournit une assistance pour travailler avec le [mode d’analyse des données](analysis-mode.md) dans Business Central. Le mode d’analyse des données vous permet d’organiser, d’agréger et de résumer les données sur des pages et des requêtes pour les rendre plus adaptées à l’analyse et à l’extraction d’informations significatives. Avec l’aide à l’analyse, vous pouvez construire automatiquement la vue des données que vous souhaitez analyser en exprimant vos besoins dans un langage simple et naturel, comme "afficher les fournisseurs par emplacement triés par nombre d’achats". L’assistance à l’analyse facilite le travail avec les données sans nécessiter de compétences techniques complexes.

## Quelles sont les capacités de l’assistance analyse ?

L’assistance à l’analyse s’appuie sur les outils de développement pour Copilot dans Business Central. Il utilise Azure Open AI Azure OpenAI pour convertir des instructions non structurées en une conception structurée pour afficher les données en mode analyse, sans créer, modifier ou mettre à jour lui-même les données commerciales du client.

## Quelle est l’utilisation prévue de l’assistance analyse ?

L’utilisation prévue de l’assistance à l’analyse est d’aider à créer des onglets d’analyse en mode d’analyse des données afin de présenter les données de manière à faciliter la conclusion. Toutefois, il est important de noter que l’assistance à l’analyse ne fournit pas d’informations ou de conclusions directes sur les données. C’est un outil qui aide les utilisateurs à organiser et visualiser leurs données. Cependant, c’est à l’utilisateur d’extraire des informations exploitables, de découvrir des tendances et de prendre des décisions éclairées pour générer de la valeur commerciale.

## Comment l’assistance analyse a-t-elle été évaluée ? Quelles mesures sont utilisées pour évaluer les performances ?

- La fonctionnalité a été testée basés sur les données de démonstration de [!INCLUDE[prod_short](includes/prod_short.md)] et d’autres catalogues de produits fictifs. Copilot a reçu de nombreuses invites dans les langues anglaises prises en charge. Les invites couvraient un large éventail d’instructions d’analyse de données et de styles d’expression d’intention. Les résultats ont été évalués en fonction de leur exactitude, de leur pertinence et de leur sécurité.

- La fonctionnalité est conçue conformément à la Norme IA Responsable de Microsoft. [Découvrez-en davantage sur l’IA responsable auprès de Microsoft](https://aka.ms/RAI).

## Comment Microsoft surveille-t-il la qualité du contenu généré ?

Microsoft a mis en place divers systèmes pour garantir que le contenu généré par Copilot est de la plus haute qualité, détecter les abus et garantir la sécurité de nos clients et de leurs données.

Les utilisateurs ont la possibilité de fournir des commentaires sur chaque réponse Copilot et de signaler tout contenu inexact ou inapproprié pour aider Microsoft à améliorer cette fonctionnalité.

- Si vous rencontrez un contenu généré inapproprié, signalez-le à Microsoft en utilisant ce formulaire de commentaires : [Signaler un abus](https://go.microsoft.com/fwlink/?linkid=2249810).

- Nous analysons et utilisons les commentaires des utilisateurs sur la fonctionnalité pour nous aider à améliorer les réponses.

  Vous fournissez des commentaires en utilisant l’icône J’aime (pouce levé) ou Je n’aime pas (pouce vers le bas) sur la volet **Copilot** dans [!INCLUDE[prod_short](includes/prod_short.md)].

- Microsoft peut désactiver les fonctionnalités pilotées par Copilot pour certains clients si un abus de la fonctionnalité est détecté.

## Quelles sont les limites de l’assistance analyse ? Comment les utilisateurs peuvent-ils minimiser l’impact des limitations assistance analyse lors de l’utilisation du système ?

- Limitations générales de l'IA

  Les systèmes d’IA sont des outils précieux, mais ils ne sont pas déterministes. Le contenu qu’ils génèrent peut ne pas être exact. Il est donc important d’utiliser votre jugement pour examiner et vérifier les réponses de Copilot avant de prendre des décisions qui pourraient affecter les parties prenantes telles que les clients et les partenaires.

- Limites linguistiques et géographiques :

  - L'assistance analyse n’est pris en charge qu’en anglais pour les langues suivantes : en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA. .

    Si la langue d’affichage dans Business Central ne fait pas partie des paramètres régionaux répertoriés, la fonctionnalité n’est pas disponible.

  - La qualité des réponses peut être moindre si :
    - La langue locale dans Business Central est différente de en-US.
    - Le paramètre de langue de l’utilisateur dans Business Central diffère de la langue principale des données métier dans la base de données [!INCLUDE[prod_short](includes/prod_short.md)].
  
  - Limitation géographique :
  
    La fonctionnalité est disponible dans tous les [pays/régions Business Central](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations) pris en charge, à l’exception du Canada, en raison de la conformité linguistique réglementaire. Cependant, la fonctionnalité utilise le service Microsoft Azure OpenAI, actuellement disponible pour Business Central dans certaines zones géographiques. Si votre environnement est situé dans un pays/une région où Azure OpenAI Service n’est pas disponible, les administrateurs doivent autoriser les données à se déplacer entre les zones géographiques. [En savoir plus](/dynamics365/business-central/ai-copilot-data-movement).

- Certaines limitations du secteur, du produit et du sujet :

  Les organisations qui opèrent dans certains domaines d’activité, tels que les soins médicaux, les médicaments, le droit et les armes, peuvent connaître une qualité de service inférieure.

## Quelles données analyse collecte-t-il et comment sont-elles utilisées

La fonctionnalité assistance analyse collecte les données minimales requises par Business Central pour offrir le service. Microsoft n’utilise pas les données de votre compagnie, y compris le texte que vous envoyez à Copilot, pour former les modèles fondamentaux au profit des autres. Pour plus d’informations, consultez les [Conditions de Dynamics 365 pour les fonctionnalités basées sur Azure OpenAI](https://go.microsoft.com/fwlink/?linkid=2236010).

Elle collecte également des données à partir des commentaires que l’utilisateur peut fournir à l’aide des icônes J’aime (pouce levé) ou Je n’aime pas (pouce vers le bas) sur la page **Copilot** assistance analyse. Les données sont anonymes et incluent le choix d’aimer ou de ne pas aimer, la raison de l’aversion si elle est fournie et la fonctionnalité Copilot à laquelle les commentaires s’appliquent.

## Voir aussi .

[Analyse des données avec Copilot (version préliminaire)](analysis-assist.md)
