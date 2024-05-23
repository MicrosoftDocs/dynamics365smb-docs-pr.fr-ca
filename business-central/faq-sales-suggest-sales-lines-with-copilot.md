---
title: FAQ sur les suggestions de ligne vente de Copilot
description: Cette FAQ fournit des informations sur la technologie d’IA utilisée dans Business Central.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: article
ms.search.form: null
ms.date: 02/02/2024
ms.service: dynamics-365-business-central
ms.collection: bap-ai-copilot
ms.custom: responsible-ai-faqs
---

# <a name="faq-for-sales-line-suggestions-with-copilot-preview"></a>FAQ sur les suggestions de ligne vente de Copilot (version préliminaire)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

Cette foire aux questions (FAQ) décrit l’impact de la fonctionnalité suggestions de ligne vente sur l’IA dans [!INCLUDE [prod_short](includes/prod_short.md)].

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## <a name="what-is-sales-line-suggestions-with-copilot"></a>Que sont les suggestions de ligne vente de Copilot ?

La suggestion de lignes de vente avec Copilot peut aider à créer des lignes sur des documents de vente tels que des devis, des commandes et des factures basées sur une saisie structurée ou un langage naturel. Il ne s’agit pas d’un chat à usage général, mais d’une expérience très spécifique et intégrée que vous pouvez utiliser sur les documents de vente. La fonctionnalité offre deux compétences distinctes qui vous aident à trouver des données sur des produits individuels ou sur l’ensemble des documents.

## <a name="what-are-capabilities-of-sales-line-suggestions-with-copilot"></a>Quelles sont les capacités des suggestions de lignes de vente avec Copilot ?

* Rechercher produits

  Les informations qui décrivent les produits sont stockées à plusieurs endroits dans [!INCLUDE [prod_short](includes/prod_short.md)]. Par exemple, les numéros d’articles et les descriptions sont stockés dans le **Article** table, plusieurs codes-barres sont stockés dans le **Référence de l’article** table et les propriétés du produit sont stockées dans le **Attributs de l’article** tableau. Bien que vous puissiez demander *Vélo rouge*, le produit réel pourrait être *VTT cramoisi*, où *Vélo* est une catégorie de produits et *rouge* est un attribut.

* Rechercher un document par référence

  Les gens répètent souvent une commande précédente, ou du moins l’utilisent comme point de départ. Mais il peut être difficile de trouver le bon ordre dans une pile de commandes. Vous vous souvenez peut-être de certains identifiants de la commande, qui peuvent être un numéro attribué par la compagnie ou un numéro de référence reçu d’un client. Être capable d’utiliser des invites telles que *Besoin de la dernière facture d’avril* devrait vous aider à trouver une commande plus rapidement.

## <a name="what-is-the-intended-use-of-sales-line-suggestions-with-copilot"></a>Quelle est l’utilisation prévue de suggestions de ligne vente avec Copilot ?

* Rechercher produits

  Destiné à répondre aux invites des utilisateurs pour rechercher des produits basés sur des descriptions vagues, incomplètes ou inexactes.

  Étant donné que le nombre moyen d’articles (produits/services) pour [!INCLUDE [prod_short](includes/prod_short.md)] clients est de 10 000, trouver les bons peut être difficile sans expérience ou connaissances préalables. La manière dont les données sont stockées dans [!INCLUDE [prod_short](includes/prod_short.md)] ne facilite pas les choses, car vous devez effectuer plusieurs recherches ou exercices de filtrage sur les différentes pages qui stockent les données produits.

  Copilot extrait les produits et les quantités demandés et identifie le terme et les attributs de recherche principaux, afin que vous puissiez saisir votre invite plus rapidement. Ensuite, Copilot effectue une recherche avancée dans plusieurs tables associées, applique des synonymes, corrige les fautes de frappe et évalue la qualité du résultat de la recherche.

* Rechercher un document par référence

  Destiné à répondre aux demandes des utilisateurs pour trouver des documents de vente existants pour un client spécifique en utilisant des informations partielles ou approximatives.

  Dans les environnements B2B, les utilisateurs sont souvent confrontés à des demandes récurrentes et les préparateurs de commandes peuvent recevoir des demandes pour répéter un document antérieur ou au moins l’utiliser comme point de départ. Mais il peut être difficile d’en trouver un pour plusieurs raisons :

  - Tout au long de son cycle de vie, un document de vente peut évoluer du devis à la commande jusqu’à la facture reportée ou l’expédition. Les documents peuvent également être archivés.
  - Vous disposez peut-être d’un identificateur exact, mais vous ne pouvez pas dire ce qu’il représente. Par exemple, s’agit-il d’un numéro de commande, d’un numéro de facture ou d’une référence externe ?
  - Parfois, vous avez une date ou un point, mais pas de pièce d’identité pour le document.

  Pour rechercher manuellement un document source, vous devrez ouvrir plusieurs pages et utiliser la recherche et le filtrage plusieurs fois. Cependant, Copilot peut simplifier cela en une seule requête en langage naturel qui vous permet d’exprimer ce que vous recherchez à votre manière. 

  * *Récupérez les produits de la commande 103031*
  * *Besoin de produits de la dernière facture d’août*

## <a name="how-was-sales-line-suggestions-with-copilot-evaluated-what-metrics-are-used-to-measure-performance"></a>Évaluation les suggestions de ligne vente de Copilot ? Quelles mesures sont utilisées pour évaluer les performances ?

La fonctionnalité a subi des tests approfondis où de nombreuses invites en anglais américain représentant à la fois une utilisation typique et une utilisation par de mauvais acteurs. Les tests étaient basés sur les données de démonstration de [!INCLUDE [prod_short](includes/prod_short.md)] et sur un vaste catalogue de produits labellisés disponibles en open source.

Cette fonctionnalité est conçue conformément à la Norme IA Responsable de Microsoft. [Découvrez-en davantage sur l’IA responsable auprès de Microsoft](https://aka.ms/RAI).

## <a name="what-are-the-limitations-of-sales-line-suggestions-with-copilot-how-can-users-minimize-the-impact-of-the-sales-line-suggestions-with-copilot-limitations-when-using-the-system"></a>Quelle sont les limitations de suggestions de ligne vente avec Copilot ? Comment les utilisateurs peuvent-ils minimiser l’impact des limitations suggestions de ligne vente avec Copilot lors de l’utilisation du système ?

* Rechercher produits
  
  La recherche de produits fonctionne mieux en anglais. Bien que vous puissiez utiliser cette fonctionnalité dans n’importe quelle langue [!INCLUDE [prod_short](includes/prod_short.md)] prend en charge, les recherches d’articles dans d’autres langues peuvent être moins précises.

Si votre secteur ou domaine chevauche ce que Microsoft considère comme des sujets sensibles (tels que les drogues, la violence, le divertissement pour adultes, etc.), Copilot peut s’en remettre à des réponses neutres et organisées ou donner des réponses inexactes.

Les suggestions de lignes de vente remplissent uniquement les champs **Taper** comme **Article**, **N°**, et **Quantité** comme décrit. D’autres domaines, notamment **Unité de mesure**, **Prix ​​unitaire**, et **Emplacement** utilisent la logique actuelle et sont renseignés soit en fonction des paramètres de l’élément, soit des valeurs héritées de l’en-tête du document.

Le **Code de variante** n’est actuellement pas pris en charge. Si vous pouvez expédier un produit dans deux couleurs différentes, par exemple, Copilot trouvera le produit recherché mais laissera le champ **Code de variante** vide. Vous devrez renseigner le champ manuellement.

La façon dont vous nommez vos produits peut affecter le résultat. Par exemple, l’utilisation d’abréviations énigmatiques plutôt que de noms conviviaux peut réduire la qualité du résultat.

Pour les produits, le tableau suivant répertorie les tables et les champs recherchés par Copilot.

|Table  |Champs  |
|---------|---------|
|**Articles**     |  * N°<br>* Description<br>* Description 2<br>* Description de la recherche<br>* GTIN<br>* Numéro d’article du fournisseur       |
|**Variante d’article**     | * Code<br>* Description<br>* Description 2          |
|**Référence d’article**     | * N° de référence.<br>* Description<br>* Description 2        |
|**Attributs d’article**     | * Nom<br>* Valeur        |
|**Catégorie article**     |  * Code<br>* Description<br>* Catégorie parent – niveau 1           |
|**Traduction article**     | * Langue<br>* Description<br>* Description 2          |
|**Identificateur article**     |  * Code       |
|**Ligne texte étendu**     |  * Texte      |

* Rechercher documents par référence

  Actuellement, vous pouvez lancer la suggestion de lignes de vente à partir des documents de vente, des factures et des devis, et rechercher les documents suivants :

  * Documents de vente
  * Devis
  * Factures vente
  * Factures vente reportées
  * Expéditions vente reportées

  Copilot recherche les champs suivants

  * N° document
  * N° doc. externe
  * Votre référence
  * N° devis
  * Date de document
  * N° client débiteur

  Copilot ne renvoie pas toutes les lignes du type Article. Seuls les numéros d’articles, les codes de variantes et les quantités sont transférés. Les quantités du document source sont converties en **Unité de mesure des ventes**.

## <a name="in-which-geographies-and-languages-is-sales-lines-suggestions-available"></a>Dans quelles zones géographiques et langues les suggestions de lignes ventes est-elle disponible ?

À l'exception du Canada, cette fonctionnalité est disponible dans toutes les localisations de pays/région d’environnement et dans n’importe quelle langue d’utilisateur. En raison d’une prise en charge linguistique limitée, la fonctionnalité ne sera pas initialement disponible pour les clients canadiens car elle ne respecte pas la conformité linguistique réglementaire. Pour cette capacité disponible pour les environnements client situés dans des pays/régions où Azure OpenAI Service n’est pas déployé, les administrateurs doivent d’abord consentir à autoriser le déplacement des données au-delà des frontières pour que [!INCLUDE [prod_short](includes/prod_short.md)] se connecte à Azure OpenAI Service.  

## <a name="what-operational-factors-and-settings-allow-for-effective-and-responsible-use-of-the-feature"></a>Quels facteurs et paramètres opérationnels permettent une utilisation efficace et responsable de la fonctionnalité ?

Les suggestions basées sur l’IA peuvent parfois être incorrectes ou incomplètes. Vous devez toujours vérifier l’exactitude des suggestions de Copilot avant de choisir de les conserver. Les correspondances et suggestions de Copilot ne sont pas enregistrées dans la base de données [!INCLUDE [prod_short](includes/prod_short.md)] tant que vous n’avez pas cliqué sur le bouton **Conserver** et quitté la fenêtre Copilot. Vous pouvez modifier et corriger toutes les suggestions avant de choisir de les conserver ou après leur insertion dans un document de vente.

### <a name="what-is-expected-of-administrators-and-end-users-when-using-sales-lines-suggestions"></a>Qu’attend-on des administrateurs et utilisateurs finaux lors de l’exploitation d’une utilisation de suggestions de lignes ventes ?

Chaque utilisateur individuel choisit d’utiliser ou non **Suggestions de lignes de vente**. Même lorsque la fonctionnalité est activée par les administrateurs et disponible, vous pouvez choisir de l’utiliser toujours, parfois ou jamais.  

Les administrateurs prennent la décision globale d’utiliser les capacités ou non Copilot dans [!INCLUDE [prod_short](includes/prod_short.md)]. Si les administrateurs activent Copilot, ils doivent s’assurer qu’ils accordent l’accès aux utilisateurs appropriés.   

> [REMARQUE !]
> - Nous ne prenons pas en charge cette fonctionnalité dans [!INCLUDE [prod_short](includes/prod_short.md)] sur site ou dans les nuages privés.
> - Les partenaires ne peuvent pas étendre cette fonctionnalité. Cela signifie que les développeurs partenaires ne peuvent pas modifier, remplacer ou étendre.

## <a name="is-copilot-the-only-means-to-create-sales-lines"></a>Copilot est-il le seul moyen de créer des lignes de vente ?

Non, l’utilisation de Copilot est facultative. [!INCLUDE [prod_short](includes/prod_short.md)] propose des moyens non basés sur l’IA pour insérer des lignes de vente ou copier des documents. Les organisations peuvent utiliser les deux approches en même temps.  

## <a name="how-do-i-give-feedback-about-ai-generated-content"></a>Comment puis-je donner mon avis sur le contenu généré par l’IA ?

Chaque fois que Copilot propose des suggestions, vous pouvez fournir des commentaires à Microsoft directement à partir de la fenêtre Copilot, en utilisant les commandes J’aime et Je n’aime pas. Vos commentaires restent anonymes et nous utilisons ces données afin d’évaluer et d’améliorer la qualité du service.  

## <a name="see-also"></a>Voir aussi .

[Proposition de lignes sur les documents de vente avec Copilot](sales-suggest-sales-lines-with-copilot.md)  
[Configuration des fonctionnalités de Copilot et d’IA](enable-ai.md)  
[FAQ sur l’IA responsable pour Dynamics 365 Business Central](responsible-ai-overview.md)  
