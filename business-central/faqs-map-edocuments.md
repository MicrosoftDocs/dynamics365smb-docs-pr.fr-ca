---
title: FAQ sur le mappage des documents électroniques avec les bons de commande
description: "Cette FAQ fournit des informations sur la technologie d’IA utilisée dans Business\_Central, ainsi que des considérations et des détails clés sur la façon dont l’IA est utilisée, comment elle a été testée et évaluée, ainsi que toute limitation spécifique."
ms.date: 02/23/2024
ms.custom:
  - responsible-ai-faqs
ms.topic: article
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.collection:
  - bap-ai-copilot
---

# FAQ sur le mappage de documents électroniques avec des bons de commande à l’aide de Copilot (version préliminaire)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Cette foire aux questions (FAQ) décrit l’impact de la fonctionnalité **Aide à la mise en correspondance de documents électroniques** sur l’IA dans [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## Qu'est-ce que Aide à la mise en correspondance de documents électroniques ?

Les documents électroniques (e-documents) constituent la base des transactions commerciales modernes. Ils représentent des documents critiques tels que les factures et les reçus qui circulent dans les deux sens jusqu’à la livraison et la réception. Vous pouvez générer et transmettre des factures électroniques sous forme numérique dans un format structuré qui facilite le traitement automatisé des factures. Cependant, le traitement des factures numériques entrantes peut s’avérer plus complexe pour les équipes chargées des comptes créditeurs.  

Dans les petites et moyennes entreprises (PME), l’équipe des comptes créditeurs joue un rôle central dans le suivi précis des obligations des fournisseurs. Leur principale responsabilité est d’enregistrer avec précision les factures entrantes. Atteindre la précision peut nécessiter des efforts, en particulier lorsqu’ils rapprochent les factures externes des fournisseurs avec les bons de commande existants. Les divergences dans les codes, les descriptions et les unités de mesure présentent souvent des problèmes, car ces éléments peuvent ne pas correspondre entre les différents systèmes et compagnies. En outre, des coûts inattendus, tels que les frais de transport, peuvent apparaître sous forme d’éléments de campagne distincts nécessitant un ajustement manuel. Les comptables doivent également inclure les numéros et les dates des factures dans les documents. Il est important de noter que la relation entre les bons de commande et les factures externes n’est pas toujours directe. Vous pouvez recevoir plusieurs factures externes pour le même bon de commande.

Historiquement, [!INCLUDE [prod_short](includes/prod_short.md)] pourrait générer de nouvelles factures d’achat sur la base des factures électroniques reçues. Cependant, faire correspondre manuellement les factures avec les bons de commande existants était un processus long et sujet aux erreurs.

**Aide au rapprochement des documents électroniques** utilise l’IA générative pour rationaliser ce processus en automatisant l’analyse des factures électroniques externes. La fonctionnalité permet aux comptables de demander à Copilot de faire correspondre les lignes des factures électroniques entrantes avec les lignes des bons de commande dans [!INCLUDE [prod_short](includes/prod_short.md)].

## Quelles sont les capacités de l’Aide à la mise en correspondance de documents électroniques ?

Copilot fournit une assistance basée sur l’IA pour faire correspondre la facture numérique reçue avec les bons de commande existants [!INCLUDE [prod_short](includes/prod_short.md)]. Copilot fait correspondre les lignes en fonction des éléments suivants :

- Similitude des descriptions
- Unités de mesure
- Quantités disponibles pour la facturation
- Montants

Copilot identifie des descriptions similaires si elles ont l’unité de mesure et les prix appropriés, mais il peut également trouver des correspondances dans des cas plus complexes. Par exemple, il peut identifier si une facture électronique comporte deux lignes avec une variante du même article et une seule ligne dans le bon de commande ; [!INCLUDE [prod_short](includes/prod_short.md)] fait correspondre ces lignes tant que les descriptions sont similaires et que les prix sont identiques.

Copilot ne se connecte pas à votre service de point de terminaison de documents électroniques pour récupérer ou envoyer des bons numériques. Cette tâche reste entièrement sous votre contrôle et constitue un préalable à l’utilisation de l’assistance de Copilot. Cela est vrai, que les documents numériques soient ajoutés à [!INCLUDE [prod_short](includes/prod_short.md)] à l’aide d’une connexion avec un service de point de terminaison ou saisis manuellement.  

## Quelle est l’utilisation prévue de l’aide au rapprochement des documents électroniques ?  

L’objectif de la fonctionnalité **Aide à la mise en correspondance de documents électroniques** est d’aider l’équipe de comptabilité fournisseurs à faire correspondre les bons de commande existants avec les factures électroniques entrantes. Une grande partie de cette activité tourne autour de la correspondance de chaînes. [!INCLUDE [prod_short](includes/prod_short.md)] offre une fonctionnalité qui automatise une partie de cette activité, et les LLM ont été identifiés comme une opportunité de compléter cette fonctionnalité et de réduire davantage l’effort manuel.  

## Comment l’Aide à la mise en correspondance de documents électroniques a-t-elle été évaluée ? Quelles mesures sont utilisées pour évaluer les performances ?

Cette fonctionnalité a été testée en utilisant des combinaisons des informations suivantes :

- Descriptions des éléments externes
- Unités de mesure
- Quantités et montants
- Descriptions tâche standard
- Différentes langues
- Autres paramètres qui couvrent les variations typiques et les limites de données pour chaque champ 

Les données de test représentent à la fois une utilisation typique et une utilisation par des acteurs malveillants. Les performances ont été mesurées par rapport à la mise en correspondance manuelle des mêmes données dans les factures électroniques et les bons de commande.

## Quelles sont les limites de l’Aide à la mise en correspondance de documents électroniques ? Comment les utilisateurs peuvent-ils minimiser l’impact des limitations de la Aide à la mise en correspondance de documents électroniques lors de l’utilisation du système ?

**L’assistance au rapprochement des documents électroniques** fonctionne mieux lorsque les descriptions d’articles externes (facture électronique) et internes ([!INCLUDE [prod_short](includes/prod_short.md)]), ainsi que les unités de mesure, sont toutes dans la même langue. Les langues mixtes des descriptions d’article entraînent souvent moins de correspondances et de suggestions.  

La correspondance suggérée des articles des factures électroniques avec les articles des bons de commande fonctionne mieux en anglais. Bien que vous puissiez utiliser cette fonctionnalité dans n’importe quelle langue [!INCLUDE [prod_short](includes/prod_short.md)] prise en charge, vous risquez de rencontrer moins de correspondances d’éléments dans d’autres langues. Pour en savoir plus sur la Langue, allez [Dans quelles zones géographiques et langues l’Aide à la mise en correspondance de documents électroniques est-elle disponible ?](#in-which-geographies-and-languages-is-e-documents-matching-assistance-available).

## Dans quelles zones géographiques et langues l’Aide à la mise en correspondance de documents électroniques est-elle disponible ?

- Géographies disponibles

   La fonction Copilot est disponible dans tous les supports pris en charge [Pays/régions Business Central](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). Mais pour les environnements client situés dans des pays/régions où Azure OpenAI Service n’est pas déployé, les administrateurs doivent d’abord consentir à autoriser le déplacement des données au-delà des frontières pour que [!INCLUDE [prod_short](includes/prod_short.md)] se connecte à Azure OpenAI Service. En savoir plus [Déplacement des données Copilot entre des zones géographiques](ai-copilot-data-movement.md).

- Langues disponibles

   [!INCLUDE[e-docs-matching-language-support](includes/e-docs-matching-language-support.md)]

## Quels facteurs et paramètres opérationnels permettent une utilisation efficace et responsable de la fonctionnalité ?

Copilot complète l’algorithme de cartographie qui [!INCLUDE [prod_short](includes/prod_short.md)] fournit déjà et mappe les lignes que l’algorithme n’a pas fait.

### Qu’est-ce qu’on attend des utilisateurs lorsqu’ils utilisent l’Aide à la mise en correspondance de documents électroniques ?

<!--Not sure that this is the right content for this section. Seems like it belongs more in the overview article because it's more related to how to use the feature-->

Après avoir mappé les factures électroniques entrantes avec les bons de commande, vous devez mapper les lignes sur les documents.

La page **Mappage des bons de commande** affiche toutes les lignes des deux documents. Ici, vous pouvez effectuer le mappage manuellement, ce qui peut être difficile s’il y a beaucoup de lignes.

Vous pouvez utiliser l’ **Aide à la mise en correspondance de documents électroniques** pour mapper des lignes en fonction des critères suivants :

- Similitude de leurs descriptions
- Unités de mesure
- Quantités disponibles pour la facturation
- Montants

Les correspondances de Copilot peuvent être incorrectes ou incomplètes. Vous devez toujours vérifier leur exactitude avant de choisir de les conserver. Les correspondances et suggestions de Copilot sont enregistrées dans [!INCLUDE [prod_short](includes/prod_short.md)] lorsque vous choisissez **Conserver** et quittez Copilot. Vous pouvez modifier et corriger toute correspondance ou suggestion avant de choisir de les conserver. 

### Qu’attend-on des administrateurs et utilisateurs lors de l’exploitation d’une Aide à la mise en correspondance de documents électroniques ?

Les utilisateurs, tels que les comptables, les autres personnes qui reçoivent les factures électroniques, doivent toujours vérifier l’exactitude des correspondances et des suggestions fournies par Copilot avant de choisir de les conserver. Nous vous recommandons de consulter les lignes de bon de commande pour vérifier leur exactitude et détecter toute anomalie. Vous décidez si vous souhaitez utiliser l’ **Aide à la mise en correspondance de documents électroniques**. Même lorsque l’ **Aide à la mise en correspondance de documents électroniques** est activée par les administrateurs et disponible, vous pouvez toujours choisir de l’utiliser toujours, parfois ou jamais.  

Les administrateurs prennent la décision globale d’utiliser ou non Copilot dans [!INCLUDE [prod_short](includes/prod_short.md)]. S’ils activent Copilot, les administrateurs doivent s’assurer qu’ils accordent l’accès aux éléments appropriés.

> [REMARQUE !]
> - Nous ne prenons pas en charge la fonctionnalité [!INCLUDE [prod_short](includes/prod_short.md)] sur site ou dans les nuages privés.
> - Les partenaires ne peuvent pas étendre cette fonctionnalité. Les développeurs partenaires ne peuvent pas modifier, remplacer ou étendre cette fonctionnalité. 

## Copilot est-il le seul moyen de faire correspondre les documents électroniques aux bons de commande ?  

Non, c’est à vous de décider si vous utilisez Copilot. [!INCLUDE [prod_short](includes/prod_short.md)] propose des moyens non basés sur l’IA pour faire correspondre les articles de la facture électronique reçue avec les articles des bons de commande dans [!INCLUDE [prod_short](includes/prod_short.md)]. Les organisations peuvent aussi utiliser les deux approches en même temps.  

## Comment puis-je donner mon avis sur le contenu généré par l’IA ?  

Chaque fois que Copilot propose des correspondances ou des suggestions, vous pouvez fournir des commentaires à Microsoft directement à partir de la fenêtre Copilot, en utilisant les commandes **J’aime** et **Je n’aime pas**. Vos commentaires restent anonymes et nous utilisons ces données afin d’évaluer et d’améliorer la qualité du service.  

## Voir aussi .

[Vue d’ensemble des documents électroniques](finance-edocuments-overview.md)  
[Mappage de documents électroniques avec des lignes bon de commande avec Copilot](map-edocuments-with-copilot.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
