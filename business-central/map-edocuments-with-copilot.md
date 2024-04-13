---
title: Mappage de documents électroniques avec des lignes bon de commande avec Copilot
description: Découvrez comment utiliser Copilot pour mapper des documents électroniques aux lignes de bon de commande.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: altotovi
ms.topic: how-to
ms.collection:
  - get-started
  - bap-ai-copilot
ms.date: 02/23/2024
ms.custom: bap-template
---

# Mappage de documents électroniques avec des lignes bon de commande avec Copilot (version préliminaire)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

À mesure que les processus d’approvisionnement deviennent de plus en plus numériques, la fonctionnalité de documents électroniques de Business Central joue un rôle clé dans l’automatisation de la réception et du traitement des factures des fournisseurs. Copilot peut vous aider dans ce processus en améliorant le mappage et la mise en correspondance des factures des fournisseurs avec les bons de commande. Cela réduit les tâches fastidieuses qui comprendraient normalement des recherches approfondies et la saisie de données. L’avantage est aggravé par le fait que les factures des fournisseurs ne correspondent souvent pas exactement aux bons de commande, auquel cas Copilot est mieux placé pour identifier les bons de commande correspondants. Les capacités de rapprochement améliorées profitent particulièrement aux petites et moyennes entreprises qui ont besoin d’un suivi efficace des documents pour les lignes bon de commande. Copilot est l’assistant de travail basé sur l’IA qui stimule la créativité et améliore la productivité des utilisateurs de Business Central.

> [!IMPORTANT]
> - Il s’agit d’une fonctionnalité en version préliminaire prêt pour la production pour les environnements de production et sandbox dans n’importe quel pays, à l’exception du Canada.
> - Les fonctionnalités en version préliminaire prêtes pour la production sont soumises à des conditions d’utilisation supplémentaires. En savoir plus : [Conditions d’utilisation supplémentaires pour la version préliminaire de Dynamics 365](https://go.microsoft.com/fwlink/?linkid=2105274)
> - Le contenu généré par l’IA est peut-être incorrect.

Dans la version initiale de l’application de **document électronique**, nous avons introduit des scénarios fondamentaux pour les documents électroniques pour l’ensemble du processus de vente. Cependant, il est nécessaire d’améliorer et d’automatiser le traitement des documents reçus, notamment dans le contexte des processus d’achat. Copilot affine la façon dont vous gérez les documents électroniques dans le processus d’achat, notamment en ce qui concerne les bons de commande. Le cadre de documents électroniques vous permet de spécifier le type de document d’achat à créer pour chaque fournisseur lorsque vous recevez des factures électroniques de sa part. Auparavant, la seule option consistait à créer une facture d’achat, soit sous forme de document, soit sous forme de journal du grand livre.

Vous pouvez désormais mettre à jour un bon de commande existant dans Business Central avec les informations reçues dans la facture électronique.

<!--
> [!NOTE]
> - This feature is available as a production-ready preview for production and sandbox environments in any country localization, with the exception of Canada. Production-ready previews are subject to supplemental terms of use. For more information, see [Supplemental terms of use for Dynamics 365 preview](https://go.microsoft.com/fwlink/?linkid=2105274).
> - AI-generated content may be incorrect.-->


## Identifier des bons de commande

Tout d’abord, vous pouvez identifier les bons de commande que vous pouvez automatiquement rapprocher.

## Mapper les lignes

Copilot vous aide à faire correspondre automatiquement les lignes de facture électronique avec les lignes de bon de commande et offre des informations de correspondance supplémentaires pour améliorer les correspondances.

Une fois qu’ils ont été rapprochés et mappés, Business Central met à jour le bon de commande rapproché avec les informations de réception pertinentes pour garantir que les bonnes quantités sont reçues sur les lignes de commande.

## Voir aussi .

[Vue d’ensemble des documents électroniques](finance-edocuments-overview.md)  
[Utilisation des documents électroniques dans les ventes et les achats](finance-how-use-edocuments.md)  
[Résoudre les problèmes des fonctionnalités de Copilot et d’IA](ai-copilot-troubleshooting.md)  
[FAQ sur l’IA responsable pour l’assistance au rapprochement bancaire](faqs-bank-reconciliation.md)  
