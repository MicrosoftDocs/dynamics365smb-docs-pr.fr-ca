---
title: Détails de conception - ligne de report dans le journal général | Microsoft Docs
description: Cette rubrique fournit une analyse des concepts et principes qui sont utilisés pour reconcevoir la fonction de ligne de report au journal général dans Business Central.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: design, general journal, posting, codeunit 12
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 3ea2ea8a4ef5bbdff70346022ee226fd5e26748d
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5777833"
---
# <a name="design-details-general-journal-post-line"></a><span data-ttu-id="7bed5-103">Détails de conception : Ligne report de journal général</span><span class="sxs-lookup"><span data-stu-id="7bed5-103">Design Details: General Journal Post Line</span></span>
<span data-ttu-id="7bed5-104">Cette documentation fournit une analyse technique détaillée des concepts et principes qui sont utilisés pour reconcevoir la fonction de ligne validation feuille comptabilité dans [!INCLUDE[prod_short](includes/prod_short.md)].</span><span class="sxs-lookup"><span data-stu-id="7bed5-104">This documentation provides detailed technical insight into the concepts and principles that are used to redesign the general journal posting line feature in [!INCLUDE[prod_short](includes/prod_short.md)].</span></span> <span data-ttu-id="7bed5-105">La nouvelle conception rend le codeunit 12 plus simple et plus facile à modifier.</span><span class="sxs-lookup"><span data-stu-id="7bed5-105">The redesign makes codeunit 12 simpler and more maintainable.</span></span> <span data-ttu-id="7bed5-106">La documentation commence par des présentations conceptuelles de la nouvelle conception.</span><span class="sxs-lookup"><span data-stu-id="7bed5-106">The documentation starts by describing conceptual overviews of the redesign.</span></span> <span data-ttu-id="7bed5-107">Alors il explique l'architecture technique pour indiquer les modifications découlant de la nouvelle conception.</span><span class="sxs-lookup"><span data-stu-id="7bed5-107">Then it explains the technical architecture to show the changes that result from the redesign.</span></span>  

## <a name="in-this-section"></a><span data-ttu-id="7bed5-108">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="7bed5-108">In This Section</span></span>  
[<span data-ttu-id="7bed5-109">Aperçu de la ligne validation de feuille comptabilité</span><span class="sxs-lookup"><span data-stu-id="7bed5-109">General Journal Post Line Overview</span></span>](design-details-general-journal-post-line-overview.md)  
[<span data-ttu-id="7bed5-110">Détails de conception : Structure de l'interface de validation</span><span class="sxs-lookup"><span data-stu-id="7bed5-110">Design Details: Posting Interface Structure</span></span>](design-details-posting-interface-structure.md)  
[<span data-ttu-id="7bed5-111">Détails de conception : Structure du moteur de validation</span><span class="sxs-lookup"><span data-stu-id="7bed5-111">Design Details: Posting Engine Structure</span></span>](design-details-posting-engine-structure.md)  
[<span data-ttu-id="7bed5-112">Codeunit 12 modifications : variables globales de mappage pour la ligne de validation de feuille comptabilité</span><span class="sxs-lookup"><span data-stu-id="7bed5-112">Codeunit 12 Changes: Mapping Global Variables for General Journal Post Line</span></span>](design-details-codeunit-12-changes-mapping-global-variables-for-general-journal-post-line.md)  
[<span data-ttu-id="7bed5-113">Codeunit 12 modifications : modifications dans les procédures de validation de feuille comptabilité</span><span class="sxs-lookup"><span data-stu-id="7bed5-113">Codeunit 12 Changes: Changes in General Journal Post Procedures</span></span>](design-details-codeunit-12-changes-changes-in-general-journal-post-procedures.md)  

## <a name="see-also"></a><span data-ttu-id="7bed5-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7bed5-114">See Also</span></span>  
[<span data-ttu-id="7bed5-115">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="7bed5-115">Working with General Journals</span></span>](ui-work-general-journals.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]