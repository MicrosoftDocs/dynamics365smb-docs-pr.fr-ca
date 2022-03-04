---
title: Détails de conception - Demande et approvisionnement | Microsoft Docs
description: Cette rubrique présente le concept de demande, qui désigne toute sorte de demande brute, par exemple un document de vente et un besoin composante d'un bon de production.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, demand, supply, inventory, planning
ms.date: 06/08/2021
ms.author: edupont
ms.openlocfilehash: 3b5f390343f74bc559cce48b2037edd125f829ca
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8143644"
---
# <a name="design-details-demand-at-blank-location"></a>Détails de conception : demande à un magasin vide.
Quand un utilisateur crée un événement de demande, comme une ligne document de vente, le programme lui permet parfois de spécifier un code d'emplacement et parfois non, autrement dit il doit utiliser un emplacement vide.

Pour la demande avec ou sans code d'emplacement, le système de planification opère directement lorsque :

- Les lignes demande comportent toujours des codes d'emplacement et le système exploite intégralement les unités de stock, y compris la configuration d'emplacement pertinente.
- Les lignes demande ne comportent jamais de codes d'emplacement, et le système n'utilise ni les unités de stock ni la configuration d'emplacement (reportez-vous au dernier cas de figure dans la section suivante).

Toutefois, si des événements de demande ont parfois des codes d'emplacement et parfois pas, le système de planification suit certaines règles en fonction de la configuration.

## <a name="demand-at-location"></a>Demande à l'emplacement
Lorsque le système de planification détecte une demande dans un emplacement, il peut procéder de plusieurs manières en fonction de trois valeurs de configuration critiques. Lors de l'exécution d'une planification, le système recherche trois valeurs de configuration l'une après l'autre et effectue la planification en conséquence.

1. Le champ **Magasin obligatoire** est-il activé ?

    Si oui :

2. Existe-t-il une unité de stock pour l'article ?

    Si oui :

    L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.

    Si non :

3. Le champ Mag. composant par déf contient-il le code magasin demandé ?

  Si oui :

  L'article est planifié en fonction des paramètres de planification de la fiche article.

  Si non :

  L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour lot, Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide. Les articles pour lesquels Méthode réapprovisionnement = Commande continuent à utiliser Commande, tout comme les autres paramètres.

> [!NOTE]
> La configuration de planification exceptionnelle produite en dernière réaction à l'étape 3 ci-dessus est appelée dans ce qui suit « solution minimale ». Cette configuration de planification ne couvre que la demande exacte, et tous les autres configuration de planification sont ignorés.

Pour plus d'informations sur les variations de cette logique de planification, voir la section Scénarios ci-dessous.

## <a name="demand-at-blank-location"></a>Demande dans un emplacement vide
Même si le champ **Emplacement obligatoire** est sélectionné, le programme autorise la création de lignes demande sans code d'emplacement, ce que l'on appelle également un emplacement vide. Il s'agit d'un écart pour le système, car il a plusieurs valeurs de configuration accordées pour gérer les emplacements (voir ci-dessus) et, par conséquent, le moteur de planification ne crée pas de ligne planification pour une telle ligne demande.

Si le champ **Emplacement obligatoire** n'est pas activé mais que des valeurs de configuration d'emplacement ont été définies, cela est également considéré comme un écart, et le système de planification réagira en utilisant la « solution minimale » : l'article est planifié comme suit : Méthode réapprovisionnement = Lot pour lot (la commande conserve la valeur Commande), Inclure inventaire = Oui, Tous les autres paramètres de planification ont la valeur Vide.

## <a name="scenarios"></a>Cas de figure
Les scénarios suivants décrivent les variations de la demande dans un emplacement vide et la manière dont le système de planification opte pour la « solution minimale ».

### <a name="setup-1"></a>Configuration 1 :
Emplacement obligatoire = Oui

L'unité de stock a pour valeur ROUGE

Composantes à l'emplacement = BLEU

#### <a name="case-11-demand-is-at-red-location"></a>Situation 1.1 : la demande concerne un emplacement ROUGE.
L'article est planifié en fonction des paramètres de planification de la fiche unité de stock.

#### <a name="case-12-demand-is-at-blue-location"></a>Situation 1.2 : la demande concerne un emplacement BLEU.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-13-demand-is-at-green-location"></a>Situation 1.3 : la demande concerne un emplacement VERT.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-14-demand-is-at-blank-location"></a>Situation 1.4 : la demande concerne un emplacement BLANC.
L'article n'est pas planifié, car aucun emplacement n'est défini sur la ligne de réquisition.

### <a name="setup-2"></a>Configuration 2 :
Emplacement obligatoire = Oui

Il n'existe pas d'unité de stock

Composantes à l'emplacement = BLEU

#### <a name="case-21-demand-is-at-red-location"></a>Situation 2.1 : la demande concerne un emplacement ROUGE.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-22-demand-is-at-blue-location"></a>Situation 2.2 : la demande concerne un emplacement BLEU.
L'article est planifié en fonction des paramètres de planification de la fiche article.

### <a name="setup-3"></a>Configuration 3 :
Emplacement obligatoire = Non

Il n'existe pas d'unité de stock

Composantes à l'emplacement = BLEU

#### <a name="case-31-demand-is-at-red-location"></a>Situation 3.1 : la demande concerne un emplacement ROUGE.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-32-demand-is-at-blue-location"></a>Situation 3.2 : la demande concerne un emplacement BLEU.
L'article est planifié en fonction des paramètres de planification de la fiche article.

#### <a name="case-33-demand-is-at-blank-location"></a>Situation 3.3 : la demande concerne un emplacement BLANC.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

### <a name="setup-4"></a>Configuration 4 :
Emplacement obligatoire = Non

Il n'existe pas d'unité de stock

Composantes à l'emplacement = VIDE

#### <a name="case-41-demand-is-at-blue-location"></a>Situation 4.1 : la demande concerne un emplacement BLEU.
L'article est planifié comme suit : Méthode réapprovisionnement = Lot pour Lot (la commande conserve la valeur Commande), Inclure inventaire = Oui. Tous les autres paramètres de planification ont la valeur Vide.

#### <a name="case-42-demand-is-at-blank-location"></a>Situation 4.2 : la demande concerne un emplacement BLANC.
L'article est planifié en fonction des paramètres de planification de la fiche article.

Comme illustré dans le dernier cas de figure, le seul moyen d'obtenir des résultats corrects pour une ligne demande sans code emplacement consiste à désactiver toutes les valeurs de configuration relatives aux emplacements. De la même manière, le seul moyen d'obtenir des résultats de planification stables pour les demandes dans des emplacements consiste à utiliser des unités de stock. Par conséquent, si les compagnies planifient souvent des demandes dans des emplacements, il leur est fortement recommandé d'utiliser le module Unités de stock.

## <a name="see-also"></a>Voir aussi  
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)   
[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)   
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]