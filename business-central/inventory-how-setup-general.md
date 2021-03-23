---
title: Définir la configuration inventaire général
description: Décrit comment définir la configuration inventaire général afin que vous puissiez gérer votre entrepôt et votre stock.
author: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, stock
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 10344ae85edc8a63dcff1a5a5927bf2d19045810
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5389409"
---
# <a name="set-up-general-inventory-information"></a><span data-ttu-id="e025b-103">Configurer des informations générales relatives à l'inventaire</span><span class="sxs-lookup"><span data-stu-id="e025b-103">Set Up General Inventory Information</span></span>

<span data-ttu-id="e025b-104">Vous pouvez spécifier votre configuration d'inventaire générale sur la page **Configuration de l'inventaire**.</span><span class="sxs-lookup"><span data-stu-id="e025b-104">You specify your general inventory setup on the **Inventory Setup** page.</span></span>

## <a name="to-set-up-general-inventory-information"></a><span data-ttu-id="e025b-105">Pour configurer des informations générales relatives à l'inventaire</span><span class="sxs-lookup"><span data-stu-id="e025b-105">To set up general inventory information</span></span>

1. <span data-ttu-id="e025b-106">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration inventaire**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="e025b-106">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Inventory Setup**, and then choose the related link.</span></span>
2. <span data-ttu-id="e025b-107">Sur la page **Configuration de l'inventaire**, renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="e025b-107">On the **Inventory Setup** page, fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

<span data-ttu-id="e025b-108">Pour des informations détaillées sur les champs d'évaluation des coûts **Report coûts automatique**, **Report coûts prévus** et **Mode évaluation coûts par défaut**, consultez [Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Détails de conception : évaluation du coût de l'inventaire](design-details-inventory-costing.md) et [Détails de conception : report du coût prévu](design-details-expected-cost-posting.md).</span><span class="sxs-lookup"><span data-stu-id="e025b-108">For detailed information about the costing fields, **Automatic Cost Posting**, **Expected Cost Posting to G/L**, and **Default Costing Method**, see [Reconcile Inventory Costs with the General Ledger](finance-how-to-post-inventory-costs-to-the-general-ledger.md), [Design Details: Inventory Costing](design-details-inventory-costing.md), and [Design Details: Expected Cost Posting](design-details-expected-cost-posting.md).</span></span> <span data-ttu-id="e025b-109">Pour plus d’informations sur l'évaluation des coûts en général, voir [Gestion des coûts d'inventaire](finance-manage-inventory-costs.md).</span><span class="sxs-lookup"><span data-stu-id="e025b-109">For more information about costing in general, see [Managing Inventory Costs](finance-manage-inventory-costs.md).</span></span>  

<span data-ttu-id="e025b-110">Vous pouvez inclure un délai entrepôt par défaut pour votre inventaire sur la page **Configuration de l'inventaire** ou pour votre emplacement dans le calcul de la promesse de livraison sur la ligne achat.</span><span class="sxs-lookup"><span data-stu-id="e025b-110">If you want to include warehouse handling time in the order promising calculation on the purchase line, you can set it up as a default for the inventory, on the **Inventory Setup** page, and for your location.</span></span> <span data-ttu-id="e025b-111">Pour plus d'informations, voir [Calculer des dates promesse livraison](sales-how-to-calculate-order-promising-dates.md).</span><span class="sxs-lookup"><span data-stu-id="e025b-111">For more information, see [Calculate Order Promising Dates](sales-how-to-calculate-order-promising-dates.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="e025b-112">Le bouton de basculement **Ajustement automatique des coûts** est activé par défaut pour garantir que les valeurs de l'inventaire soient toujours correctes dans le grand livre, qui à son tour maintient vos statistiques vente et profit à jour.</span><span class="sxs-lookup"><span data-stu-id="e025b-112">The **Automatic Cost Adjustment** toggle is turned on by default to ensure that inventory values are always correct in the general ledger, which in turn keeps your sales and profit statistics up to date.</span></span> <span data-ttu-id="e025b-113">Les modifications de coût des écritures entrantes, telles que celles des sorties achat ou production, sont affectées aux écritures sortantes correspondantes, telles que les ventes ou les transferts.</span><span class="sxs-lookup"><span data-stu-id="e025b-113">Cost changes from inbound entries, such as those for purchases or production output, are assigned to the related outbound entries, such as sales or transfers.</span></span> <span data-ttu-id="e025b-114">Ceci est utile pour les nouveaux clients et petites entreprises [!INCLUDE[prod_short](includes/prod_short.md)] avec des niveaux de transaction d'inventaire relativement bas.</span><span class="sxs-lookup"><span data-stu-id="e025b-114">This is helpful for new [!INCLUDE[prod_short](includes/prod_short.md)] customers and small businesses with relatively low inventory transaction levels.</span></span> <span data-ttu-id="e025b-115">Cependant, à mesure que l’entreprise se développe et que les niveaux d'inventaire augmentent, cela peut ralentir les performances du système.</span><span class="sxs-lookup"><span data-stu-id="e025b-115">However, as a business grows and inventory levels increase, this can slow down system performance.</span></span> <span data-ttu-id="e025b-116">Pour minimiser les performances réduites lors du report, sélectionnez une option de temps pour définir jusqu’où dans le passé depuis la date de travail une transaction entrante peut se produire pour déclencher potentiellement l’ajustement des entrées de valeur sortantes associées.</span><span class="sxs-lookup"><span data-stu-id="e025b-116">To minimize reduced performance during posting, select a time option to define how far back in time from the work date an inbound transaction can occur to potentially trigger adjustment of related outbound value entries.</span></span> <span data-ttu-id="e025b-117">Sinon, vous pouvez ajuster manuellement les coûts à intervalles réguliers avec le traitement en lot Ajuster coûts - Écr. article.</span><span class="sxs-lookup"><span data-stu-id="e025b-117">Alternatively, you can manually adjust costs at regular intervals with the Adjust Cost - Item Entries batch job.</span></span>

## <a name="see-also"></a><span data-ttu-id="e025b-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="e025b-118">See Also</span></span>
[<span data-ttu-id="e025b-119">Configuration du stock</span><span class="sxs-lookup"><span data-stu-id="e025b-119">Set Up Inventory</span></span>](inventory-setup-inventory.md)  
<span data-ttu-id="e025b-120">[Détails de conception : modes évaluation stock](design-details-costing-methods.md)  </span><span class="sxs-lookup"><span data-stu-id="e025b-120">[Design Details: Costing Methods](design-details-costing-methods.md)  </span></span>  
[<span data-ttu-id="e025b-121">Gestion du stock</span><span class="sxs-lookup"><span data-stu-id="e025b-121">Manage Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="e025b-122">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="e025b-122">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>  
[<span data-ttu-id="e025b-123">Modifier les fonctionnalités affichées</span><span class="sxs-lookup"><span data-stu-id="e025b-123">Change Which Features are Displayed</span></span>](ui-experiences.md)  
[<span data-ttu-id="e025b-124">Fonctionnalités marché</span><span class="sxs-lookup"><span data-stu-id="e025b-124">General Business Functionality</span></span>](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]