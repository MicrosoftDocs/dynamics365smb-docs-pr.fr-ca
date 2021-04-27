---
title: Pratiques recommandées pour la configuration globale de la planification | Microsoft Docs
description: Le raccourci Planification de la page Configuration de la fabrication comporte plusieurs champs permettant de définir les règles globales pour la planification des approvisionnements.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: c91bde42378992ef1c1e9613fb94d9bac2d4f57c
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5785358"
---
# <a name="setup-best-practices-global-planning-setup"></a><span data-ttu-id="8d716-103">Pratiques de configuration recommandées : configuration globale de la planification</span><span class="sxs-lookup"><span data-stu-id="8d716-103">Setup Best Practices: Global Planning Setup</span></span>
<span data-ttu-id="8d716-104">Le raccourci **Planification** de la page **Configuration de la fabrication** comporte plusieurs champs permettant de définir les règles globales pour la planification des approvisionnements.</span><span class="sxs-lookup"><span data-stu-id="8d716-104">The **Planning** FastTab on the **Manufacturing Setup** page contains several fields that define global rules for supply planning.</span></span>  

 <span data-ttu-id="8d716-105">Le tableau suivant fournit les meilleures pratiques sur la procédure de configuration de champs paramètres sélectionnés de planification générale.</span><span class="sxs-lookup"><span data-stu-id="8d716-105">The following table provides best practices on how to set up selected global planning parameter fields.</span></span> <span data-ttu-id="8d716-106">Pour plus d'informations sur un champ donné, sélectionnez le lien correspondant dans la colonne **Configuration d'un champ**.</span><span class="sxs-lookup"><span data-stu-id="8d716-106">For more information about a field, choose the link in the **Setup field** column.</span></span>  

|<span data-ttu-id="8d716-107">Champ de configuration</span><span class="sxs-lookup"><span data-stu-id="8d716-107">Setup field</span></span>|<span data-ttu-id="8d716-108">Meilleure pratique</span><span class="sxs-lookup"><span data-stu-id="8d716-108">Best practice</span></span>|<span data-ttu-id="8d716-109">Commentaire</span><span class="sxs-lookup"><span data-stu-id="8d716-109">Comment</span></span>|  
|-----------------|-------------------|-------------|  
|<span data-ttu-id="8d716-110">Prévision sur magasin</span><span class="sxs-lookup"><span data-stu-id="8d716-110">Use Forecast on Locations</span></span>|<span data-ttu-id="8d716-111">Indiquez si vous avez des prévisions pour des entrepôts spécifiques.</span><span class="sxs-lookup"><span data-stu-id="8d716-111">Select if you have forecasts for specific locations.</span></span>||  
|<span data-ttu-id="8d716-112">Mag. composant par déf.</span><span class="sxs-lookup"><span data-stu-id="8d716-112">Components at Location</span></span>|<span data-ttu-id="8d716-113">Si les articles ne sont pas définis comme unités de stock, sélectionnez le code d'emplacement de l'entrepôt principal.</span><span class="sxs-lookup"><span data-stu-id="8d716-113">If items are not defined as SKUs, select the location code of your main warehouse.</span></span>|<span data-ttu-id="8d716-114">Cela s'applique également si vous utilisez uniquement la feuille de réquisition.</span><span class="sxs-lookup"><span data-stu-id="8d716-114">This also applies if you only use the requisition worksheet.</span></span>|  
|<span data-ttu-id="8d716-115">Niveau de dépassement de capacité vide</span><span class="sxs-lookup"><span data-stu-id="8d716-115">Blank Overflow Level</span></span>|<span data-ttu-id="8d716-116">Sélectionnez **Autoriser calcul par défaut** si vous effectuez une migration de Microsoft Dynamics NAV 5.0 ou d'une version antérieure.</span><span class="sxs-lookup"><span data-stu-id="8d716-116">Select **Allow Default Calculation** if you are migrating from Microsoft Dynamics NAV 5.0 or earlier.</span></span>|<span data-ttu-id="8d716-117">Ne l'utilisez que si vous souhaitez autoriser tout ou partie de vos articles à franchir le point de réapprovisionnement.</span><span class="sxs-lookup"><span data-stu-id="8d716-117">Use only if you want to allow all or some of your items to overflow the reorder point.</span></span>|  
|<span data-ttu-id="8d716-118">Période tampon par défaut</span><span class="sxs-lookup"><span data-stu-id="8d716-118">Default Dampener Period</span></span>|<span data-ttu-id="8d716-119">Doit être compris entre 1D et 5D.</span><span class="sxs-lookup"><span data-stu-id="8d716-119">Set between 1D and 5D.</span></span><br /><br /> <span data-ttu-id="8d716-120">Si vous débutez en planification avec [!INCLUDE[prod_short](includes/prod_short.md)], définissez une plus longue période.</span><span class="sxs-lookup"><span data-stu-id="8d716-120">If new to planning in [!INCLUDE[prod_short](includes/prod_short.md)], then set a longer period.</span></span>|<span data-ttu-id="8d716-121">Quand les utilisateurs sont plus au fait des différents motifs des messages d'action, raccourcissez la période tampon pour autoriser plus de propositions de modification.</span><span class="sxs-lookup"><span data-stu-id="8d716-121">When users are more familiar with the different reasons for action messages, then shorten the dampener period to allow more change suggestions.</span></span>|  
|<span data-ttu-id="8d716-122">Quantité tampon par défaut (%)</span><span class="sxs-lookup"><span data-stu-id="8d716-122">Default Dampener Quantity %</span></span>|<span data-ttu-id="8d716-123">Définissez à entre 5 et 20 % de la taille du lot de l'article.</span><span class="sxs-lookup"><span data-stu-id="8d716-123">Set between 5 and 20 percent of the item’s lot size.</span></span>||  

## <a name="see-also"></a><span data-ttu-id="8d716-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d716-124">See Also</span></span>  
 <span data-ttu-id="8d716-125">[Pratiques de configuration recommandées : planification de l'approvisionnement](setup-best-practices-supply-planning.md) </span><span class="sxs-lookup"><span data-stu-id="8d716-125">[Setup Best Practices: Supply Planning](setup-best-practices-supply-planning.md) </span></span>  
 <span data-ttu-id="8d716-126">[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md) </span><span class="sxs-lookup"><span data-stu-id="8d716-126">[Design Details: Supply Planning](design-details-supply-planning.md) </span></span>  
 [<span data-ttu-id="8d716-127">Configurez les modules complexes à l'aide des meilleures pratiques</span><span class="sxs-lookup"><span data-stu-id="8d716-127">Set Up Complex Application Areas Using Best Practices</span></span>](set-up-complex-application-areas-using-best-practices.md)  
 <span data-ttu-id="8d716-128">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="8d716-128">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>


[!INCLUDE[footer-include](includes/footer-banner.md)]