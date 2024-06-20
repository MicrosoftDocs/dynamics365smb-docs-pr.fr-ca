---
title: Suggestions de ligne vente de Copilot
description: Apprenez à proposer des lignes sur les documents de vente avec Copilot.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: 'Copilot, AI, sell'
ms.search.form: null
ms.date: 02/02/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
ms.collection: bap-ai-copilot
---

# <a name="suggest-lines-on-sales-documents-with-copilot-preview"></a>Proposition de lignes sur les documents vente avec Copilot (version préliminaire)

[!INCLUDE[preview-banner](includes/preview-banner.md)]

Cet article explique comment créer plus rapidement des documents de vente en laissant Copilot suggérer les articles à ajouter aux lignes des documents de vente pour vos clients.

[!INCLUDE[production-ready-preview-dynamics365](includes/production-ready-preview-dynamics365.md)]

## <a name="about-sales-line-suggestions-with-copilot"></a>Sur les suggestions de ligne vente de Copilot

La suggestion de lignes de vente avec Copilot peut aider à créer des lignes sur des documents de vente tels que des devis, des commandes et des factures basées sur une saisie structurée ou un langage naturel. Il ne s’agit pas d’un chat à usage général, mais d’une expérience très spécifique et intégrée que vous pouvez utiliser sur les documents de vente. La fonctionnalité offre deux compétences distinctes qui vous aident à trouver des données sur des produits individuels ou sur l’ensemble des documents.

* Rechercher produits

  Les informations qui décrivent les produits sont stockées à plusieurs endroits dans [!INCLUDE [prod_short](includes/prod_short.md)]. Par exemple, les numéros d’articles et les descriptions sont stockés dans le **Article** table, plusieurs codes-barres sont stockés dans le **Référence de l’article** table et les propriétés du produit sont stockées dans le **Attributs de l’article** tableau. Bien que vous puissiez demander *Vélo rouge*, le produit réel pourrait être *VTT cramoisi*, où *Vélo* est une catégorie de produits et *rouge* est un attribut.

* Rechercher documents par référence

  Les gens répètent souvent une commande précédente, ou du moins l’utilisent comme point de départ. Mais il peut être difficile de trouver le bon ordre dans une pile de commandes. Vous vous souvenez peut-être de certains identifiants de la commande, qui peuvent être un numéro attribué par la compagnie ou un numéro de référence reçu d’un client. Être capable d’utiliser des invites telles que *Besoin de la dernière facture d’avril* devrait vous aider à trouver une commande plus rapidement.

## <a name="available-languages"></a>Conditions préalables

* La suggestion de ligne de vente avec Copilot est activée et activée par un administrateur. Pour en savoir plus sur l’activation des fonctionnalités d’IA, accédez à [Configurer les fonctionnalités de Copilot et d’IA](enable-ai.md).
* Vous êtes familier avec la création de documents de vente.

## <a name="prerequisites"></a>Disponibilité géographique

Le tableau suivant présente les Microsoft Azure zones géographiques dans lesquelles sa fonctionnalité est disponible.

|Région Azure d’environnement  |Zone géographique desservant Azure OpenAI Service   |Action d’administrateur requise pour déverrouiller Copilot  |
|---------|---------|---------|
|Allemagne (Nord, Centre-Ouest)     | Suède ou Suisse        |  Oui       |
|Norvège (Est, Ouest)     | Suède ou Suisse        | Oui     |
|Singapour     |         |         |
|Afrique du Sud (Nord, Ouest)     |   États-Unis      |   Oui      |
|Suisse (Nord, Ouest)     |  Suède ou Suisse       |    Oui     |
|Émirats arabes unis (Nord, Ouest)     |    États-Unis     |   Oui     |
|États-Unis (Centre, Est, Centre-Nord, Centre-Sud, Ouest)     |   États-Unis      |   N°      |
|Europe (Ouest, Nord)     |   Suède ou Suisse      |   Oui      |
|Asie Pacifique     |         |         |
|Australie (Sud-Est)     |   États-Unis      |    Oui     |
|Amérique du Sud     |         |         |
|Inde (Centre, Sud)     |    États-Unis     |   Oui      |
|Japon (Est, Ouest)     |    États-Unis     |    Oui     |
|France (Centre, Sud)     |    Suède ou Suisse     |    Oui     |
|Corée (Centre, Sud)     |    États-Unis     |    Oui     |

## <a name="examples-of-prompts"></a>Exemples de invites

Les suggestions de lignes de vente avec Copilot peuvent gérer une grande variété de saisies rapides. Cette section propose quelques exemples d’invites pour divers scénarios que nous avons testés.

### <a name="sample-inquiry-to-repeat-the-past-document"></a>Exemple de demande pour répéter le document précédent

Invite : *Besoin de tous les produits de la facture 103031*

### <a name="during-phone-call-user-quickly-types-list-of-required-products-and-quantities-not-always-accurate-enough-or-using-internal-product-names"></a>Au cours d’un appel téléphonique, l’utilisateur saisit rapidement la liste des produits et des quantités requis, pas toujours assez précise ou en utilisant des noms de produits internes

Invite : *2 bicyclettes rouges pour enfants*

Notez que l’invite fonctionne, même avec plusieurs fautes de frappe.

### <a name="a-user-copies-an-inquiry-from-an-inbound-communication-and-pastes-it-to-the-sales-lines-suggestions-page"></a>Un utilisateur copie une demande à partir d’une communication entrante et la colle dans la page Suggestions de lignes de vente

Invite : *Bonjour, je souhaite acheter des accessoires pour mon ordinateur portable XXXX, tels qu’une souris sans fil, une housse de clavier et une sacoche pour ordinateur portable. Je me demande si vous avez des recommandations ou des suggestions pour ces articles. Avez-vous des offres spéciales ou des réductions pour les clients fidèles comme moi? Cordialement, M.*

Notez que XXXX Laptop n’est pas inclus dans la recherche.

## <a name="suggest-lines-on-a-sales-document"></a>Suggérer lignes un document vente

Ce processus décrit comment suggérer des lignes sur un document de vente. Les étapes sont les mêmes pour les devis et factures.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Document de vente**, puis sélectionnez le lien associé.
1. Ouvrez le document de vente.
1. Dans le raccourci **Lignes**, sélectionnez l’action **Obtenir suggestions lignes**.
1. Dans la fenêtre **Suggérer des lignes avec Copilot** , saisissez votre invite ou sélectionnez-en une dans les guides d’invite.

## <a name="review-save-discard-or-regenerate-suggestions"></a>Examiner, enregistrer, supprimer ou régénérer les suggestions

Une fois que Copilot a suggéré les éléments à ajouter aux lignes, examinez ses suggestions et décidez si elles correspondent à ce que vous souhaitez :

* Pour ignorer une seule ligne proposée, sélectionnez-la dans la liste, puis sélectionnez l’action **Supprimer la ligne**.
* Pour supprimer toutes les lignes proposées et fermer la fenêtre Copilot, choisissez le bouton Supprimer (poubelle) à côté du bouton **Conserver** .
* Pour transférer les lignes affichées dans la fenêtre Copilot, choisissez **Conserver**. 

Il existe un champ **Fiabilité** qui affiche **Élevé (80+)**, **Moyen ( 60-80)** et **Faible (60-)** vous marquent et vous orientent vers les lignes qui nécessitent votre attention.

Cette étape confirme que vous souhaitez transférer les lignes vers un document de vente. Vous pouvez également y supprimer ou modifier les lignes transférées, ou supprimer l’intégralité du document.

## <a name="see-also"></a>Voir aussi .

[FAQ sur les suggestions de lignes de vente avec Copilot](faq-sales-suggest-sales-lines-with-copilot.md)
[Configurer les fonctionnalités de Copilot et d’IA](enable-ai.md)
