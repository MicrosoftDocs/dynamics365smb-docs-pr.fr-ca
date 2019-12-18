---
title: Aperçu de la ligne de report dans le journal général | Microsoft Docs
description: Cette rubrique décrit les modifications du codeunit 12, **Journal général-Ligne report**, qui est l'objet d'application majeur pour le report dans le grand livre et est le seul emplacement pour insérer des écritures grand livre, des écritures TVA et des écritures client et fournisseur.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, general ledger, post
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 9de46d66fe13a798dda812b74f19b9ed247b84fd
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2880410"
---
# <a name="general-journal-post-line-overview"></a>Aperçu de la ligne report de journal général
Le Codeunit 12, **Journal général-Ligne report**, est l'objet d'application majeur pour le report dans le grand livre et est le seul emplacement pour insérer des écritures GL, TVA, et client et fournisseur. Ce codeunit est également utilisé pour toutes les opérations Affecter, Annuler l'affectation et Inverser.  
  
Alors que le codeunit a été amélioré dans chaque version au cours des dix dernières années, son architecture est, au fond, restée inchangée. Le codeunit est devenu très grand, avec approximativement 7 600 lignes de code. Avec cette version de [!INCLUDE[d365fin](includes/d365fin_md.md)], l'architecture est modifiée et le codeunit a été rendu plus simple et plus facile à modifier. Cette documentation présente les modifications et fournit les informations dont vous aurez besoin pour la mise à niveau.  
  
## <a name="old-architecture"></a>Ancienne architecture  
L'ancienne architecture avait les fonctions suivantes :  
  
* Il y a eu une utilisation extensive des variables globales, qui ont augmenté la possibilité d'erreurs masquées dues à l'utilisation de variables avec une portée incorrecte.  
* Il y a eu beaucoup de procédures longues (avec plus de 100 lignes de code) qui présentaient également une complexité cyclomatique élevée (c'est-à-dire, beaucoup de formulations imbriquées CASSE, RÉPÉTITION, SI), ce qui a rendu le code très difficile à mire et modifier.  
* Plusieurs procédures qui n'étaient utilisées que localement et ne devaient être utilisées que localement n'ont pas été marquées comme locales.  
* La plupart des procédures n'avaient pas de paramètres et utilisaient des variables globales. Certains utilisaient des paramètres et écrasaient les variables globales par des valeurs locales.  
* Les combinaisons de code pour trouver les comptes du grand livre et créer des écritures et les écritures TVA n'ont pas été standardisées et varient d'un endroit à l'autre. En outre, il y a beaucoup de duplication de code et une symétrie rompue entre le code client et fournisseur.  
* Une grande partie du code dans le codeunit 12, approximativement 30 %, est lié aux calculs d'escompte de paiement et de tolérance, même si ces fonctions ne sont pas nécessaires dans de nombreux pays ou régions.  
* Report, Affecter, Annuler l'affectation, Inverser, Escompte de paiement et tolérance, ainsi qu'Ajustement du taux de change ont été associés dans le codeunit 12 à l'aide d'une longue liste de variables globales.  
  
### <a name="new-architecture"></a>Nouvelle architecture  
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], le codeunit 12 présente les améliorations suivantes :  
  
* Le Codeunit 12 a été remanié en procédures plus petites (toutes inférieures à 100 lignes de code).  
* Des motifs standardisés pour la recherche des comptes du grand livre ont été mis en œuvre à l'aide des fonctions d'aide des tableaux de groupes de report.  
* Un cadre de moteur de report a été mis en œuvre pour gérer le début et la fin des transactions et pour trouver la création dans les écritures et les écritures TVA, la collection d'ajustement TVA, et le calcul des montants supplémentaires en devise.  
* La duplication de code a été éliminée.  
* De nombreuses fonctions de participation ont été transférées vers les tables d'écritures client et fournisseur correspondantes.  
* L'utilisation des variables globales a été réduite, de façon à ce que chaque procédure utilise des paramètres et contienne sa propre logique d'affectation.  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : Structure de l'interface de report](design-details-posting-interface-structure.md)   
[Détails de conception : Structure du moteur de validation](design-details-posting-engine-structure.md)
