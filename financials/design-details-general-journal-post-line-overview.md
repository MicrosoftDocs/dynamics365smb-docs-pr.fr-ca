---
title: "Aperçu de la ligne de report dans le journal général | Microsoft Docs"
description: "Cette rubrique décrit les modifications du Codeunit 12, **Journal général-Ligne report**, qui est l'objet d'application majeur pour le report dans le grand livre et le seul emplacement pour insérer des écritures GL, TVA, client et fournisseur."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, general ledger, post
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 77fa52505dc586dc11ca89e53f6eec75042d3606
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="general-journal-post-line-overview"></a><span data-ttu-id="a7809-103">Aperçu de la ligne report de journal général</span><span class="sxs-lookup"><span data-stu-id="a7809-103">General Journal Post Line Overview</span></span>
<span data-ttu-id="a7809-104">Le Codeunit 12, **Journal général-Ligne report**, est l'objet d'application majeur pour le report dans le grand livre et est le seul emplacement pour insérer des écritures GL, TVA, et client et fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a7809-104">Codeunit 12, **Gen. Jnl.-Post Line**, is the major application object for general ledger posting and is the only place to insert general ledger, VAT, and customer and vendor ledger entries.</span></span> <span data-ttu-id="a7809-105">Ce codeunit est également utilisé pour toutes les opérations Affecter, Annuler l'affectation et Inverser.</span><span class="sxs-lookup"><span data-stu-id="a7809-105">This codeunit is also used for all Apply, Unapply and Reverse operations.</span></span>  
  
<span data-ttu-id="a7809-106">Alors que le codeunit a été amélioré dans chaque version au cours des dix dernières années, son architecture est, au fond, restée inchangée.</span><span class="sxs-lookup"><span data-stu-id="a7809-106">While the codeunit has been improved in each release over the last ten years, its architecture remained essentially unchanged.</span></span> <span data-ttu-id="a7809-107">Le codeunit est devenu très grand, avec approximativement 7 600 lignes de code.</span><span class="sxs-lookup"><span data-stu-id="a7809-107">The codeunit became very large, with approximately 7,600 code lines.</span></span> <span data-ttu-id="a7809-108">Avec cette version de [!INCLUDE[d365fin](includes/d365fin_md.md)], l'architecture est modifiée et le codeunit a été rendu plus simple et plus facile à modifier.</span><span class="sxs-lookup"><span data-stu-id="a7809-108">With this release of [!INCLUDE[d365fin](includes/d365fin_md.md)], the architecture is changed and the codeunit has been made simpler and more maintainable.</span></span> <span data-ttu-id="a7809-109">Cette documentation présente les modifications et fournit les informations dont vous aurez besoin pour la mise à niveau.</span><span class="sxs-lookup"><span data-stu-id="a7809-109">This documentation introduces the changes and provides information that you will need for upgrade.</span></span>  
  
## <a name="old-architecture"></a><span data-ttu-id="a7809-110">Ancienne architecture</span><span class="sxs-lookup"><span data-stu-id="a7809-110">Old Architecture</span></span>  
<span data-ttu-id="a7809-111">L'ancienne architecture avait les fonctions suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7809-111">The old architecture had the following features:</span></span>  
  
* <span data-ttu-id="a7809-112">Il y a eu une utilisation extensive des variables globales, qui ont augmenté la possibilité d'erreurs masquées dues à l'utilisation de variables avec une portée incorrecte.</span><span class="sxs-lookup"><span data-stu-id="a7809-112">There was extensive use of global variables, which increased the possibility of hidden errors due to use of variables with the wrong scope.</span></span>  
* <span data-ttu-id="a7809-113">Il y a eu beaucoup de procédures longues (avec plus de 100 lignes de code) qui présentaient également une complexité cyclomatique élevée (c'est-à-dire, beaucoup de formulations imbriquées CASSE, RÉPÉTITION, SI), ce qui a rendu le code très difficile à mire et modifier.</span><span class="sxs-lookup"><span data-stu-id="a7809-113">There were many long procedures (with more than 100 code lines) that also had high cyclomatic complexity (that is, a lot of CASE, REPEAT, IF nested statements), which made the code very difficult to read and maintain.</span></span>  
* <span data-ttu-id="a7809-114">Plusieurs procédures qui n'étaient utilisées que localement et ne devaient être utilisées que localement n'ont pas été marquées comme locales.</span><span class="sxs-lookup"><span data-stu-id="a7809-114">Several procedures that were only used locally and were only meant to be used locally were not marked as local.</span></span>  
* <span data-ttu-id="a7809-115">La plupart des procédures n'avaient pas de paramètres et utilisaient des variables globales.</span><span class="sxs-lookup"><span data-stu-id="a7809-115">Most procedures had no parameters and used global variables.</span></span> <span data-ttu-id="a7809-116">Certains utilisaient des paramètres et écrasaient les variables globales par des valeurs locales.</span><span class="sxs-lookup"><span data-stu-id="a7809-116">Some used parameters and overrode global variables with locals.</span></span>  
* <span data-ttu-id="a7809-117">Les combinaisons de code pour trouver les comptes du grand livre et créer des écritures et les écritures TVA n'ont pas été standardisées et varient d'un endroit à l'autre.</span><span class="sxs-lookup"><span data-stu-id="a7809-117">Code patterns for searching the general ledger accounts and creating general ledger and VAT entries was not standardized and varied from place to place.</span></span> <span data-ttu-id="a7809-118">En outre, il y a beaucoup de duplication de code et une symétrie rompue entre le code client et fournisseur.</span><span class="sxs-lookup"><span data-stu-id="a7809-118">In addition, there was a lot of code duplication and broken symmetry between customer and vendor code.</span></span>  
* <span data-ttu-id="a7809-119">Une grande partie du code dans le codeunit 12, approximativement 30 %, est lié aux calculs d'escompte de paiement et de tolérance, même si ces fonctions ne sont pas nécessaires dans de nombreux pays ou régions.</span><span class="sxs-lookup"><span data-stu-id="a7809-119">A large part of the code in codeunit 12, approximately 30 percent, related to payment discount and tolerance calculations, although these features are not needed in many countries or regions.</span></span>  
* <span data-ttu-id="a7809-120">Report, Affecter, Annuler l'affectation, Inverser, Escompte de paiement et tolérance, ainsi qu'Ajustement du taux de change ont été associés dans le codeunit 12 à l'aide d'une longue liste de variables globales.</span><span class="sxs-lookup"><span data-stu-id="a7809-120">Posting, Apply, Unapply, Reverse, Payment Discount and Tolerance, and Exchange Rate Adjustment were married together in codeunit 12 using a long list of global variables.</span></span>  
  
### <a name="new-architecture"></a><span data-ttu-id="a7809-121">Nouvelle architecture</span><span class="sxs-lookup"><span data-stu-id="a7809-121">New Architecture</span></span>  
<span data-ttu-id="a7809-122">Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], le codeunit 12 présente les améliorations suivantes :</span><span class="sxs-lookup"><span data-stu-id="a7809-122">In [!INCLUDE[d365fin](includes/d365fin_md.md)], codeunit 12 has had the following improvements:</span></span>  
  
* <span data-ttu-id="a7809-123">Le Codeunit 12 a été remanié en procédures plus petites (toutes inférieures à 100 lignes de code).</span><span class="sxs-lookup"><span data-stu-id="a7809-123">Codeunit 12 has been refactored into smaller procedures (all less than 100 code lines).</span></span>  
* <span data-ttu-id="a7809-124">Des motifs standardisés pour la recherche des comptes du grand livre ont été mis en œuvre à l'aide des fonctions d'aide des tableaux de groupes de report.</span><span class="sxs-lookup"><span data-stu-id="a7809-124">Standardized patterns for the search of general ledger accounts have been implemented by using helper functions from Posting Group tables.</span></span>  
* <span data-ttu-id="a7809-125">Un cadre de moteur de report a été mis en œuvre pour gérer le début et la fin des transactions et pour trouver la création dans les écritures et les écritures TVA, la collection d'ajustement TVA, et le calcul des montants supplémentaires en devise.</span><span class="sxs-lookup"><span data-stu-id="a7809-125">A Posting Engine Framework has been implemented to manage the start and finish of transactions and to isolate the creation to general ledger and VAT entries, the collection of VAT adjustment, and the calculation of additional currency amounts.</span></span>  
* <span data-ttu-id="a7809-126">La duplication de code a été éliminée.</span><span class="sxs-lookup"><span data-stu-id="a7809-126">Code duplication has been eliminated.</span></span>  
* <span data-ttu-id="a7809-127">De nombreuses fonctions de participation ont été transférées vers les tables d'écritures client et fournisseur correspondantes.</span><span class="sxs-lookup"><span data-stu-id="a7809-127">Many helper functions have been transferred to corresponding customer and vendor ledger entry tables.</span></span>  
* <span data-ttu-id="a7809-128">L'utilisation des variables globales a été réduite, de façon à ce que chaque procédure utilise des paramètres et contienne sa propre logique d'affectation.</span><span class="sxs-lookup"><span data-stu-id="a7809-128">The use of global variables has been minimized, so that each procedure uses parameters and encapsulates its own application logic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7809-129">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="a7809-129">See Also</span></span>  
<span data-ttu-id="a7809-130">[Détails de conception : Structure de l'interface de report](design-details-posting-interface-structure.md) </span><span class="sxs-lookup"><span data-stu-id="a7809-130">[Design Details: Posting Interface Structure](design-details-posting-interface-structure.md) </span></span>  
[<span data-ttu-id="a7809-131">Détails de conception : Structure du moteur de validation</span><span class="sxs-lookup"><span data-stu-id="a7809-131">Design Details: Posting Engine Structure</span></span>](design-details-posting-engine-structure.md)
