---
title: FAQ sur l’assistant de rapprochement de compte bancaire avec Copilot (version préliminaire)
description: 'Cette FAQ fournit des informations sur la technologie d’IA utilisée pour rapprocher les comptes bancaires et les relevés Business Central. Elle comprend également des éléments à prendre en compte et des détails clés sur la façon dont l’IA est utilisée, comment elle a été testée et évaluée, et toutes les limitations spécifiques.'
ms.date: 03/27/2024
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

# <a name="faq-for-bank-account-reconciliation-assist-with-copilot-preview"></a>FAQ sur l’assistant de rapprochement de compte bancaire avec Copilot (version préliminaire)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Cette foire aux questions (FAQ) décrit l’impact de l’IA sur l’assistance Microsoft Copilot pour le rapprochement des comptes bancaires dans [!INCLUDE[prod_short](includes/prod_short.md)].

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## <a name="what-is-bank-reconciliation-assist"></a>Qu’est-ce que l’assistant de rapprochement bancaire ?

Le rapprochement bancaire est une tâche comptable courante dans laquelle les organisations examinent leurs relevés de compte bancaire pour identifier les transactions qui doivent être enregistrées dans [!INCLUDE[prod_short](includes/prod_short.md)]. Par exemple, cette tâche est utilisée pour identifier les frais bancaires périodiques ou les petites dépenses des employés.

Le rapprochement bancaire est généralement un processus en plusieurs étapes. Tout d’abord, les relevés bancaires sont importés dans [!INCLUDE[prod_short](includes/prod_short.md)]. Ensuite, les transactions sont mises en correspondance avec les écritures. Enfin, de nouvelles écritures sont reportées pour refléter toutes les transactions résiduelles qui n’étaient pas connues auparavant dans vos grands livres.

Copilot dans [!INCLUDE[prod_short](includes/prod_short.md)] réduit les efforts manuels en faisant correspondre davantage de transactions et en suggérant des comptes du grand livre sur lesquels vous pouvez effectuer un report.

## <a name="what-are-the-capabilities-of-bank-reconciliation-assist"></a>Quelles sont les capacités de l’aide au rapprochement bancaire ?

Copilot fournit une assistance basée sur l’IA avec deux tâches distinctes :

- Amélioration de la correspondance des transactions avec les écritures

    [!INCLUDE[prod_short](includes/prod_short.md)] propose des règles automatisées qui font automatiquement correspondre de nombreuses transactions bancaires avec les écritures du grand livre. Cependant, ces règles sont rigides et aboutissent souvent à de nombreuses transactions sans correspondance qui nécessitent chacune un contrôle manuel et une comparaison associée. Copilot utilise la technologie d’IA pour inspecter les transactions non correspondances et identifier davantage de correspondances, en fonction des dates, des montants et des descriptions. Par exemple, si un client a payé plusieurs factures en une seule fois, Copilot rapproche la ligne de relevé bancaire unique avec les multiples écritures facture.

- Comptes du grand livre suggérés

    Pour les transactions bancaires résiduelles qui n’ont pu être mises en correspondance avec aucune écriture du grand livre, Copilot utilise la technologie d’IA pour comparer la description de la transaction avec les noms des comptes GL, puis suggère le compte GL le plus probable sur lequel effectuer le report. Par exemple, si des transactions sans correspondance ont le descriptif *Fuel Stop 24*, Copilot pourrait suggérer que vous les reportiez dans le compte *Transport*.

Copilot ne se connecte pas à votre banque pour récupérer ou envoyer des transactions. Cette tâche reste entièrement sous votre contrôle. Elle constitue une condition préalable pour utiliser l’assistance de Copilot, que ces transactions soient ajoutées à [!INCLUDE[prod_short](includes/prod_short.md)] via une connexion bancaire numérique, importée depuis un fichier de relevé bancaire ou saisie manuellement.

## <a name="what-is-the-intended-use-of-bank-reconciliation-assist"></a>Quelle est l’utilisation prévue de l’assistance au rapprochement bancaire ?

L’assistance au rapprochement des comptes bancaires est conçue pour améliorer exactitude des livres en aider les clients à identifier les nouvelles transactions que les clients doivent comptabiliser dans [!INCLUDE[prod_short](includes/prod_short.md)]. Elle n’est pas destinée à détecter les fraudes ou à identifier si les clients ont payé à temps.

## <a name="how-was-bank-reconciliation-assist-evaluated-what-metrics-are-used-to-measure-performance"></a>Comment l’aide au rapprochement bancaire a-t-elle été évaluée ? Quelles mesures sont utilisées pour évaluer les performances ?

L'aide rapprochement compte bancaire a été testée en utilisant des combinaisons de données de transactions bancaires synthétiques et de comptes du grand livre et d’écritures GL similaires qui couvrent les variations typiques et les limites de données pour chaque champ et dans différentes langues. Les données de test représentent à la fois une utilisation typique et une utilisation par des acteurs malveillants. Les performances ont été mesurées par rapport au rapprochement manuel des mêmes données.

## <a name="what-are-the-limitations-of-bank-reconciliation-assist-how-can-users-minimize-the-impact-of-these-limitations-when-they-use-the-system"></a>Quelles sont les limites de l’assistance au rapprochement bancaire ? Comment les utilisateurs peuvent-ils minimiser l’impact de ces limitations lors de l’utilisation du système ?

L’assistance au rapprochement des comptes bancaires fonctionne mieux lorsque les noms de comptes du grand livre, les descriptions d’écritures GL et les descriptions de transactions bancaires sont tous dans la même langue. Les langues mixtes des descriptions de transactions entraînent souvent moins de correspondances et de suggestions.

Les comptes généraux suggérés fonctionnent mieux dans l’une des langues prises en charge (voir la section suivante pour une liste des langues). Les utilisateurs peuvent rencontrer moins de correspondances de transactions et moins de comptes généraux suggérés dans d’autres langues.

## <a name="in-which-geographies-and-languages-is-bank-reconciliation-assist-available"></a>Dans quelles zones géographiques et langues l’assistance au rapprochement bancaire est-elle disponible ?

- Géographies disponibles

  Le assistance rapprochement Compte bancaire Copilot est disponible dans tous les supports pris en charge [Pays/régions Business Central](/dynamics365/business-central/dev-itpro/compliance/apptest-countries-and-translations). Pour les environnements client situés dans des pays/régions où Azure OpenAI Service n’est pas déployé, les administrateurs doivent consentir à autoriser le déplacement des données au-delà des frontières pour que [!INCLUDE [prod_short](includes/prod_short.md)] se connecte à Azure OpenAI Service. En savoir plus [Déplacement des données Copilot entre des zones géographiques](ai-copilot-data-movement.md).

- Langues disponibles

  [!INCLUDE[bank-recon-assist-language-support](includes/bank-recon-assist-language-support.md)]

Pour plus d’informations sur les langues, consultez la question précédente sur les limitations.

## <a name="what-is-expected-of-system-users-when-they-operate-bank-account-reconciliation-assist"></a>Qu’attend-on des utilisateurs système lors de l’exploitation d’une assistance au rapprochement des comptes bancaires ?

### <a name="during-bank-account-reconciliation"></a>Pendant un rapprochement bancaire

Les correspondances et suggestions basées sur l’IA peuvent parfois être incorrectes ou incomplètes. Les utilisateurs de l’assistance au rapprochement des comptes bancaires doivent vérifier l’exactitude des correspondances et des suggestions fournies par Copilot avant de choisir de les conserver. Les correspondances et suggestions de Copilot ne sont pas enregistrées dans la base de données [!INCLUDE[prod_short](includes/prod_short.md)] tant que vous n’avez pas cliqué sur le bouton **Conserver** et fermé la fenêtre Copilot. Vous pouvez modifier et corriger toute correspondance ou suggestion avant de choisir de les conserver.

### <a name="after-bank-account-reconciliation-is-completed"></a>Après le rapprochement bancaire fini

Nous recommandons aux utilisateurs de vérifier également l’exactitude et de corriger toute divergence après avoir fermé la fenêtre Copilot. Ce processus devrait inclure les activités suivantes :

- Consulter le rapport du test de rapprochement.
- S’assurer que votre organisation dispose des processus d’examen et d’audit appropriés.
- Rouvrez tous les rapprochements reportés via la fonction **Annuler**.
- Corriger toute écriture erronée grâce à l’inversion de report des écritures.

## <a name="what-is-expected-of-administrators-and-system-users-when-they-operate-bank-account-reconciliation-assist"></a>Qu’attend-on des administrateurs et utilisateurs système lors de l’exploitation d’une assistance au rapprochement des comptes bancaires ?

Les utilisateurs système, tels que les comptables, les trésoriers ou autres personnes travaillant sur la comptabilité d’entreprise, doivent toujours vérifier l’exactitude des correspondances et des suggestions fournies par Copilot avant de choisir de les conserver. Après le rapprochement avec Copilot, nous vous recommandons que les utilisateurs consulter le rapport de test de rapprochement pour vérifier l’exactitude et identifier toute divergence.

Les administrateurs doivent s’assurer que les utilisateurs comptables appropriés ont accès à cette fonctionnalité.

## <a name="is-copilot-the-only-means-of-completing-bank-account-reconciliation"></a>Copilot est-il le seul moyen de réaliser le rapprochement des comptes bancaires ?

N° L’utilisation de Copilot est facultative. [!INCLUDE[prod_short](includes/prod_short.md)] offre des moyens traditionnels, non basés sur l’IA, d’importer des relevés bancaires, d’exécuter des règles de correspondance prédéfinies et d’appliquer manuellement les correspondances et le report sur les comptes appropriés du grand livre. L’approche traditionnelle et Copilot peuvent être utilisées simultanément dans une organisation.

## <a name="how-do-i-give-feedback-about-ai-generated-content"></a>Comment puis-je donner mon avis sur le contenu généré par l’IA ?

Chaque fois que Copilot propose des correspondances ou des suggestions, vous pouvez fournir des commentaires à Microsoft directement à partir de la fenêtre Copilot, en utilisant les commandes J’aime et Je n’aime pas. Vos commentaires restent anonymes et nous utilisons ces données afin d’évaluer et d’améliorer la qualité du service.

## <a name="see-also"></a>Voir aussi .

[Rapprocher les comptes bancaires avec Copilot (version préliminaire)](bank-reconciliation-with-copilot.md)
