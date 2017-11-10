---
title: "Comment configurer des employés d'entrepôt | Microsoft Docs"
description: "Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu'employé d'entrepôt affecté à un emplacement par défaut, et éventuellement à d'autres emplacements."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 6fb0aa48352bc35c2e9ee399a3d0b17032a5ed7e
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-set-up-warehouse-employees"></a><span data-ttu-id="f961b-103">Procédure : configurer des employés d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f961b-103">How to: Set Up Warehouse Employees</span></span>
<span data-ttu-id="f961b-104">Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu'employé d'entrepôt affecté à un emplacement par défaut, et éventuellement à d'autres emplacements.</span><span class="sxs-lookup"><span data-stu-id="f961b-104">Each user who performs warehouse activities must be set up as a warehouse employee assigned to one default location and potentially more non-default locations.</span></span> <span data-ttu-id="f961b-105">Cette configuration d'utilisateur filtre toutes les utilisations entrepôt dans la base de donnée pour l'emplacement de l'employé, de sorte que l'employé peut uniquement effectuer les activités entrepôt à l'emplacement par défaut.</span><span class="sxs-lookup"><span data-stu-id="f961b-105">This user setup filters all warehouse activities across the database to the employee's location so that the employee can only perform the warehouse activities at the default location.</span></span> <span data-ttu-id="f961b-106">Un utilisateur peut être affecté à d'autres emplacements que ceux par défaut pour lesquels il peut consulter les lignes activité sans pour autant exécuter les activités.</span><span class="sxs-lookup"><span data-stu-id="f961b-106">A user can be assigned to additional non-default locations for which the employee can view activity lines but not perform the activities.</span></span>

## <a name="to-set-up-warehouse-employees"></a><span data-ttu-id="f961b-107">Pour configurer des employés d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f961b-107">To set up warehouse employees</span></span>  
1.  <span data-ttu-id="f961b-108">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Employés entrepôt**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f961b-108">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Warehouse Employees**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f961b-109">Sélectionnez l'action **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="f961b-109">Choose the **New** action.</span></span>  
3. <span data-ttu-id="f961b-110">Sélectionnez le champ **Code utilisateur**, puis sélectionnez l'utilisateur à ajouter comme magasinier.</span><span class="sxs-lookup"><span data-stu-id="f961b-110">Select the **User ID** field, and then select the user to be added as a warehouse employee.</span></span> <span data-ttu-id="f961b-111">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="f961b-111">Choose the **OK** button.</span></span>  
6.  <span data-ttu-id="f961b-112">Dans le champ **Code magasin**, entrez le code du magasin dans lequel va travailler l'utilisateur.</span><span class="sxs-lookup"><span data-stu-id="f961b-112">In the **Location Code** field, enter the code of the location where the user will be working.</span></span>  
7.  <span data-ttu-id="f961b-113">Activez la case à cocher **Par défaut** pour définir le magasin comme seul emplacement pour les activités entrepôt de l'employé.</span><span class="sxs-lookup"><span data-stu-id="f961b-113">Select the **Default** check box to define the location as the only location where the employee can perform warehouse activities.</span></span>  
8.  <span data-ttu-id="f961b-114">Répétez ces étapes pour affecter d'autres employés à des emplacements ou affecter d'autres emplacements à des employés d'entrepôt existants.</span><span class="sxs-lookup"><span data-stu-id="f961b-114">Repeat these steps to assign other employees to locations or assign non-default locations to existing warehouse employees.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f961b-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f961b-115">See Also</span></span>  
[<span data-ttu-id="f961b-116">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f961b-116">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="f961b-117">Stock</span><span class="sxs-lookup"><span data-stu-id="f961b-117">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="f961b-118">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="f961b-118">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="f961b-119">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="f961b-119">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="f961b-120">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="f961b-120">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="f961b-121">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="f961b-121">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
