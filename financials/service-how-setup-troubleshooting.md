---
title: "Configurer les processus de dépannage | Microsoft Docs"
description: "Découvrez comment configurer des processus qui aident les conseillers du service clientèle à identifier et à résoudre les problèmes liés aux articles de service."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: service, service item, troubleshoot, repairs, maintenance
ms.date: 08/22/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 5876bf5d959d106eefb9b0f765e42e74dd13ab07
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---

# <a name="setting-up-troubleshooting-for-service-items"></a><span data-ttu-id="30cf4-103">Configuration du dépannage pour les articles de service</span><span class="sxs-lookup"><span data-stu-id="30cf4-103">Setting Up Troubleshooting for Service Items</span></span>
<span data-ttu-id="30cf4-104">Vous pouvez configurer des instructions de dépannage qui aident les techniciens à résoudre les problèmes pendant la maintenance.</span><span class="sxs-lookup"><span data-stu-id="30cf4-104">You can set up troubleshooting guidelines that help technicians solve problems when providing service.</span></span> <span data-ttu-id="30cf4-105">Par exemple, les instructions peuvent être une liste d'étapes pour effectuer une réparation, ou une série de questions à poser sur les articles.</span><span class="sxs-lookup"><span data-stu-id="30cf4-105">For example, guidelines might be a list of steps to perform a repair, or a series of questions to ask about the items.</span></span> <span data-ttu-id="30cf4-106">Une fois que vous avez configuré les instructions de dépannage, vous pouvez les affecter à des groupes articles de service, des articles de service et des articles.</span><span class="sxs-lookup"><span data-stu-id="30cf4-106">After you set up troubleshooting guidelines, you can assign them to service item groups, service items, and items.</span></span> <span data-ttu-id="30cf4-107">Il existe une hiérarchie d'héritage pour les instructions.</span><span class="sxs-lookup"><span data-stu-id="30cf4-107">There is an inheritance hierarchy for guidelines.</span></span> <span data-ttu-id="30cf4-108">Si vous les affectez à un groupe articles de service, les articles inclus dans le groupe héritent des instructions sauf si vous les spécifiez pour les articles.</span><span class="sxs-lookup"><span data-stu-id="30cf4-108">If you assign them to a service item group, the items included in the group will inherit the guidelines unless you specify them for the items.</span></span> <span data-ttu-id="30cf4-109">De même, les articles de service héritent des instructions des articles.</span><span class="sxs-lookup"><span data-stu-id="30cf4-109">Similarly, service items will inherit guidelines from items.</span></span>  

## <a name="to-set-up-troubleshooting-guidelines"></a><span data-ttu-id="30cf4-110">Pour configurer des instructions dépannage</span><span class="sxs-lookup"><span data-stu-id="30cf4-110">To set up troubleshooting guidelines</span></span>
1. <span data-ttu-id="30cf4-111">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Dépannage**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="30cf4-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Troubleshooting**, and then choose the related link.</span></span>  
2. <span data-ttu-id="30cf4-112">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="30cf4-112">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-assign-troubleshooting-guidelines-to-items-service-items-or-service-item-groups"></a><span data-ttu-id="30cf4-113">Pour affecter des instructions de dépannage à des articles, des articles de service ou des groupes articles de service</span><span class="sxs-lookup"><span data-stu-id="30cf4-113">To assign troubleshooting guidelines to items, service items, or service item groups</span></span>
1. <span data-ttu-id="30cf4-114">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Articles**, **Articles de service** ou **Groupe d'articles de service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="30cf4-114">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Items**, **Service Items**, or **Service Item Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="30cf4-115">Sélectionnez l'entité appropriée, puis l'action **Dépannage**.</span><span class="sxs-lookup"><span data-stu-id="30cf4-115">Choose the relevant entity, and then choose the **Troubleshooting** action.</span></span>  

## <a name="see-also"></a><span data-ttu-id="30cf4-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="30cf4-116">See Also</span></span>
[<span data-ttu-id="30cf4-117">Gestion des services</span><span class="sxs-lookup"><span data-stu-id="30cf4-117">Service Management</span></span>](service-service.md)