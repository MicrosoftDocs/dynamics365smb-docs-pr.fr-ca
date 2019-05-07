---
title: Paramétrer les immobilisations| Microsoft Docs
description: En savoir plus sur la série de tâches que vous devez effectuer pour configurer les immobilisations, telles que les machines ou les bâtiments.
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: machinery, buildings
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: c7a8ac11ffe4d9a1e19956a40ae57a62b43c096f
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "926049"
---
# <a name="setting-up-fixed-assets"></a><span data-ttu-id="bb768-103">Paramétrage d'immobilisations</span><span class="sxs-lookup"><span data-stu-id="bb768-103">Setting Up Fixed Assets</span></span>
<span data-ttu-id="bb768-104">Avant de pouvoir utiliser les immobilisations, vous devez définir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="bb768-104">Before you can work with Fixed Assets, you need to define a few things:</span></span>  

* <span data-ttu-id="bb768-105">Comment assurer, maintenir et amortir les immobilisations.</span><span class="sxs-lookup"><span data-stu-id="bb768-105">How you insure, maintain, and depreciate fixed assets.</span></span>  
* <span data-ttu-id="bb768-106">La manière dont vous enregistrez les coûts et d'autres valeurs dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="bb768-106">How you record costs and other values in the general ledger.</span></span>  

<span data-ttu-id="bb768-107">Le tableau ci-dessous contient des liens vers des informations supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="bb768-107">The table below has links to more information.</span></span> <span data-ttu-id="bb768-108">Après avoir défini ces éléments, vous pouvez démarrer diverses activités.</span><span class="sxs-lookup"><span data-stu-id="bb768-108">After you set those things up, you can start various activities.</span></span> <span data-ttu-id="bb768-109">Pour plus d'informations, reportez-vous à [Immobilisations](fa-manage.md).</span><span class="sxs-lookup"><span data-stu-id="bb768-109">For more information, see [Fixed Assets](fa-manage.md).</span></span>  

> [!NOTE]  
>   <span data-ttu-id="bb768-110">Vous pouvez enregistrer les transactions immobilisation sur les pages **Journal GL immobilisation** ou **Journal immobilisation**, selon que les transactions sont destinées à des rapports financiers ou pour la gestion interne.</span><span class="sxs-lookup"><span data-stu-id="bb768-110">You can record fixed asset transactions in the **Fixed Asset G/L Journal** or **Fixed Asset Journal** pages, depending on whether the transactions are for financial reporting or for internal management.</span></span> <span data-ttu-id="bb768-111">L'aide pour les immobilisations décrit uniquement la procédure d'utilisation de la page **Feuille compta. immo.**.</span><span class="sxs-lookup"><span data-stu-id="bb768-111">Help for Fixed Assets only describes how to use the **Fixed Asset G/L Journal** page.</span></span>  

<span data-ttu-id="bb768-112">Lorsque vous activez une activité immobilisation dans la section **Intégration GL** sur la page **Fiche registre amortissement**, la page **Journal GL immobilisation** sera utilisée pour reporter les transactions pour l'activité.</span><span class="sxs-lookup"><span data-stu-id="bb768-112">When you enable a fixed asset activity in the **G/L Integration** section on the **Depreciation Book Card** page, the **Fixed Asset G/L Journal** page is used to post transactions for the activity.</span></span>

<span data-ttu-id="bb768-113">Le tableau suivant décrit une série de tâches et inclut des liens vers les rubriques qui les décrivent.</span><span class="sxs-lookup"><span data-stu-id="bb768-113">The following table describes a sequence of tasks, with links to the topics that describe them.</span></span>  

| <span data-ttu-id="bb768-114">À</span><span class="sxs-lookup"><span data-stu-id="bb768-114">To</span></span> | <span data-ttu-id="bb768-115">Voir</span><span class="sxs-lookup"><span data-stu-id="bb768-115">See</span></span> |
| --- | --- |
| <span data-ttu-id="bb768-116">Configurer les comptes du grand livre par défaut, les clés d'affectation, les modèles journal et les lots pour le report des immobilisations et configurer les catégories et sous-catégories d'immobilisation, telles que Corporelles et Incorporelles.</span><span class="sxs-lookup"><span data-stu-id="bb768-116">Set up default G/L accounts, allocation keys, journal templates and batches for fixed asset posting, and set up fixed asset classes and subclasses, such as Tangible and Intangible.</span></span> |[<span data-ttu-id="bb768-117">Configurer des informations générales pour les immobilisations</span><span class="sxs-lookup"><span data-stu-id="bb768-117">Set Up General Fixed Assets Information</span></span>](fa-how-setup-general.md) |
| <span data-ttu-id="bb768-118">Créer des registres amortissement, définir différentes méthodes d'amortissement, procéder à l'intégration dans le grand livre et activer la duplication d'écritures dans plusieurs registres amortissement.</span><span class="sxs-lookup"><span data-stu-id="bb768-118">Create depreciation books, define various depreciation methods, integrate with the general ledger, and enable duplication of entries in several depreciation books.</span></span> |[<span data-ttu-id="bb768-119">Configurer un amortissement immobilisation</span><span class="sxs-lookup"><span data-stu-id="bb768-119">Set Up Fixed Asset Depreciation</span></span>](fa-how-setup-depreciation.md) |
| <span data-ttu-id="bb768-120">Activer l'assurance des immobilisations, configurer les informations générales d'assurance, une fiche assurance par police et préparer les journaux pour reporter les coûts d'assurance.</span><span class="sxs-lookup"><span data-stu-id="bb768-120">Enable insurance of fixed assets, set up general insurance information, an insurance card per policy, and prepare journals to post insurance costs.</span></span> |[<span data-ttu-id="bb768-121">Configurer une assurance immobilisation</span><span class="sxs-lookup"><span data-stu-id="bb768-121">Set Up Fixed Asset Insurance</span></span>](fa-how-setup-insurance.md) |
| <span data-ttu-id="bb768-122">Activer l'entretien des immobilisations, configurer les informations générales propres à l'entretien, configurer les comptes de report de l'entretien et définir les types de travaux d'entretien.</span><span class="sxs-lookup"><span data-stu-id="bb768-122">Enable maintenance of fixed assets, set up general maintenance information, set up maintenance posting accounts, and define types of maintenance work.</span></span> |[<span data-ttu-id="bb768-123">Configurer l'entretien d'une immobilisation</span><span class="sxs-lookup"><span data-stu-id="bb768-123">Set Up Fixed Asset Maintenance</span></span>](fa-how-setup-maintenance.md) |
| <span data-ttu-id="bb768-124">En savoir plus sur les différentes méthodes d'amortissement des immobilisations.</span><span class="sxs-lookup"><span data-stu-id="bb768-124">Learn about different fixed asset depreciation methods.</span></span> |[<span data-ttu-id="bb768-125">Méthodes d'amortissement</span><span class="sxs-lookup"><span data-stu-id="bb768-125">Depreciation Methods</span></span>](fa-depreciation-methods.md) |

## <a name="see-also"></a><span data-ttu-id="bb768-126">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="bb768-126">See Also</span></span>
[<span data-ttu-id="bb768-127">Immobilisations</span><span class="sxs-lookup"><span data-stu-id="bb768-127">Fixed Assets</span></span>](fa-manage.md)  
[<span data-ttu-id="bb768-128">Finance</span><span class="sxs-lookup"><span data-stu-id="bb768-128">Finance</span></span>](finance.md)  
[<span data-ttu-id="bb768-129">Mise en route</span><span class="sxs-lookup"><span data-stu-id="bb768-129">Getting Started</span></span>](product-get-started.md)  
<span data-ttu-id="bb768-130">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="bb768-130">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
