---
title: "Procédure : Imprimer une liste des prélèvements inventaire d'un document de vente"
description: Vous pouvez imprimer une liste des prélèvements inventaire directement à partir d'un document de vente, des ventes, de la facture et d'autres documents vente sortants.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 48c1a45e1abc510ce98f405dcdecc5d91d1a9ac5
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5393734"
---
# <a name="print-the-picking-list"></a><span data-ttu-id="7668e-103">Imprimer la liste des prélèvements</span><span class="sxs-lookup"><span data-stu-id="7668e-103">Print the Picking List</span></span>
<span data-ttu-id="7668e-104">Vous pouvez imprimer une liste des prélèvements inventaire directement à partir d'un document de vente, d'une facture vente, ou d'autres documents qui déclenchent la livraison d'articles.</span><span class="sxs-lookup"><span data-stu-id="7668e-104">You can print an inventory picking list directly from a sales order, a sales invoice, or any other document that initiates shipment of items.</span></span>

<span data-ttu-id="7668e-105">Ce rapport est généralement utilisé dans les compagnies sans fonctionnalité dédiée à la gestion des entrepôts, de sorte qu'un préposé à l'inventaire peut simplement afficher ou imprimer la liste des prélèvements à partir du document vente associé.</span><span class="sxs-lookup"><span data-stu-id="7668e-105">This report is typically used in companies without dedicated functionality for warehouse management, so that an inventory worker can simply view or print the picking list from the related sales document.</span></span> <span data-ttu-id="7668e-106">Dans les compagnies avec un volume plus élevé ou des processus plus complexes, le prélèvement est planifié et effectué dans des documents entrepôt dédiés.</span><span class="sxs-lookup"><span data-stu-id="7668e-106">In companies with higher volume or more complex processes, picking is planned and performed in dedicated warehouse documents.</span></span> <span data-ttu-id="7668e-107">Pour plus d'informations, voir [Prélèvement d'articles](warehouse-pick-items.md).</span><span class="sxs-lookup"><span data-stu-id="7668e-107">For more information, see [Pick Items](warehouse-pick-items.md).</span></span>

## <a name="to-print-a-picking-list-from-a-sales-order"></a><span data-ttu-id="7668e-108">Pour imprimer une liste des prélèvements à partir d'un document de vente</span><span class="sxs-lookup"><span data-stu-id="7668e-108">To print a picking list from a sales order</span></span>  
<span data-ttu-id="7668e-109">La procédure suivante se base sur un document de vente.</span><span class="sxs-lookup"><span data-stu-id="7668e-109">The following procedure is based on a sales order.</span></span> <span data-ttu-id="7668e-110">Les étapes sont similaires pour tous les documents vente pouvant être utilisés pour lancer une livraison d'articles.</span><span class="sxs-lookup"><span data-stu-id="7668e-110">The steps are similar for all sales documents that can be used to initiate shipment of items.</span></span>

1. <span data-ttu-id="7668e-111">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche"), saisissez **Documents de vente**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="7668e-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Orders**, and then choose the related link.</span></span>  
2. <span data-ttu-id="7668e-112">Ouvrez le document de vente pour lequel vous souhaitez prélever des articles.</span><span class="sxs-lookup"><span data-stu-id="7668e-112">Open the sales order that you want to pick items for.</span></span>  
3. <span data-ttu-id="7668e-113">Choisir l'action **Rapport**, puis choisissez l'action **Liste de prélèvement par ordre**.</span><span class="sxs-lookup"><span data-stu-id="7668e-113">Choose the **Report** action, and then choose the **Picking List by Order** action.</span></span>  
4. <span data-ttu-id="7668e-114">Sélectionnez le bouton **Imprimer** pour imprimer la liste de prélèvements, ou le bouton **Aperçu** pour l'afficher à l'écran.</span><span class="sxs-lookup"><span data-stu-id="7668e-114">Choose the **Print** button to print the picking list or choose the **Preview** button to view it on the screen.</span></span>

<span data-ttu-id="7668e-115">Vous pouvez également enregistrer la liste des prélèvements en tant que document, par exemple, pour l'envoyer à quelqu'un ou pour l'ajouter en tant que pièce jointe au document de vente.</span><span class="sxs-lookup"><span data-stu-id="7668e-115">You can also save the picking list as a document, for example, to send to someone or to add as an attachment to the sales order.</span></span> <span data-ttu-id="7668e-116">Pour plus d'informations, voir [Gérer les pièces jointes, les liens et les notes sur les fiches et les documents](ui-how-add-link-to-record.md).</span><span class="sxs-lookup"><span data-stu-id="7668e-116">For more information, see [Manage Attachments, Links, and Notes on Cards and Documents](ui-how-add-link-to-record.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7668e-117">Si vous avez utilisé la fonction **Éclater nomenclature** sur le document de vente, seuls les composantes de l'élément d'assemblage associé sont affichées dans le rapport.</span><span class="sxs-lookup"><span data-stu-id="7668e-117">If you used the **Explode BOM** function on the sales order, then only the components of the related assembly item are shown in the report.</span></span> <span data-ttu-id="7668e-118">Pour plus d'informations, reportez-vous à [Utiliser les nomenclatures](inventory-how-work-BOMs.md).</span><span class="sxs-lookup"><span data-stu-id="7668e-118">For more information, see [Work with Bills of Material](inventory-how-work-BOMs.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7668e-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7668e-119">See Also</span></span>  
[<span data-ttu-id="7668e-120">Inventaire</span><span class="sxs-lookup"><span data-stu-id="7668e-120">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="7668e-121">Prélèvement d'articles</span><span class="sxs-lookup"><span data-stu-id="7668e-121">Pick Items</span></span>](warehouse-pick-items.md)  
<span data-ttu-id="7668e-122">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="7668e-122">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>   


[!INCLUDE[footer-include](includes/footer-banner.md)]