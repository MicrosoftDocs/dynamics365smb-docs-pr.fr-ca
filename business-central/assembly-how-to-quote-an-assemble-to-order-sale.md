---
title: "Procédure : Établissement d'un devis de vente Assembler pour commande | Microsoft Docs"
description: "Vous pouvez utiliser la gestion d'assemblage pour personnaliser un élément d'assemblage sur la demande d'un client au cours du processus de vente."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: kit, kitting
ms.date: 08/15/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 046a42582dc66368fded90a4bb45add71a95d979
ms.openlocfilehash: 497d19dfdc8c972ff22aa0bcb65d96791bc8390e
ms.contentlocale: fr-ca
ms.lasthandoff: 07/02/2018

---
# <a name="quote-an-assemble-to-order-sale"></a><span data-ttu-id="dbda0-103">Établissement d'un devis de vente Assembler pour commande</span><span class="sxs-lookup"><span data-stu-id="dbda0-103">Quote an Assemble-to-Order Sale</span></span>
<span data-ttu-id="dbda0-104">Vous pouvez utiliser la gestion d'assemblage pour personnaliser un élément d'assemblage sur la demande d'un client au cours du processus de vente.</span><span class="sxs-lookup"><span data-stu-id="dbda0-104">You can use assembly management to customize an assembly item to a customer’s request during the sales process.</span></span> <span data-ttu-id="dbda0-105">Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).</span><span class="sxs-lookup"><span data-stu-id="dbda0-105">For more information, see [Sell Items Assembled to Order](assembly-how-to-sell-items-assembled-to-order.md).</span></span>  

<span data-ttu-id="dbda0-106">Lorsque vous vendez tout autre type d'article, vous pouvez également créer un devis pour un élément d'assemblage personnalisé avant de le convertir en document de vente.</span><span class="sxs-lookup"><span data-stu-id="dbda0-106">As when you sell any other type of item, you can also create a sales quote for a customized assembly item before converting it to a sales order.</span></span> <span data-ttu-id="dbda0-107">Ce processus implique plusieurs étapes supplémentaires lorsque vous le comparez à la création d'un devis normal et il recourt à une variation d'un ordre d'assemblage associé, qui est un devis d'assemblage.</span><span class="sxs-lookup"><span data-stu-id="dbda0-107">This process involves several extra steps when you compare it to creating a regular sales quote, and it uses a variation of a linked assembly order, which is an assembly quote.</span></span>

> [!NOTE]  
>  <span data-ttu-id="dbda0-108">Comme tous les types de devis, les quantités sur les devis d'assemblage ne sont pas utilisées en termes de disponibilité, planification ou réservations.</span><span class="sxs-lookup"><span data-stu-id="dbda0-108">Like all types of quotes, the quantities on assembly quotes are not used in availability, planning, or reservations.</span></span>  

## <a name="to-create-a-sales-quote-for-an-assemble-to-order-item"></a><span data-ttu-id="dbda0-109">Créer un devis pour un article à assembler pour commande</span><span class="sxs-lookup"><span data-stu-id="dbda0-109">To create a sales quote for an assemble-to-order item</span></span>  
1.  <span data-ttu-id="dbda0-110">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Devis**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="dbda0-110">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Sales Quote**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="dbda0-111">Créez une ligne devis avec une ligne pour un élément d'assemblage.</span><span class="sxs-lookup"><span data-stu-id="dbda0-111">Create a sales quote line with one line for an assembly item.</span></span> <span data-ttu-id="dbda0-112">Pour plus d'informations, voir [Créer des devis](sales-how-make-offers.md).</span><span class="sxs-lookup"><span data-stu-id="dbda0-112">For more information, see [Make Sales Quotes](sales-how-make-offers.md).</span></span>  
3.  <span data-ttu-id="dbda0-113">Dans le champ **Quantité à assembler pour commande**, entrez la quantité entière.</span><span class="sxs-lookup"><span data-stu-id="dbda0-113">In the **Qty. to Assemble to Order** field, enter the full quantity.</span></span>

    > [!NOTE]  
    >  <span data-ttu-id="dbda0-114">Vous ne devez pas établir un devis pour une quantité partielle.</span><span class="sxs-lookup"><span data-stu-id="dbda0-114">You should not quote a partial quantity.</span></span> <span data-ttu-id="dbda0-115">Par conséquent, vous devez entrer la même quantité que vous avez saisie dans le champ **Quantité** de la ligne devis.</span><span class="sxs-lookup"><span data-stu-id="dbda0-115">Therefore, you must enter the same quantity that you entered in the **Quantity** field on the sales quote line.</span></span>  

4.  <span data-ttu-id="dbda0-116">Sur le raccourci **Lignes**, sélectionnez **Ligne**, puis **Assembler pour commande** et **Lignes d'assemblage pour commande**.</span><span class="sxs-lookup"><span data-stu-id="dbda0-116">On the **Lines** FastTab, choose **Line**, choose **Assemble to Order**, and then choose **Assemble-to-Order Lines**.</span></span> <span data-ttu-id="dbda0-117">Sinon, choisissez le champ **Quantité à assembler pour commande** sur la ligne.</span><span class="sxs-lookup"><span data-stu-id="dbda0-117">Alternatively, choose the **Qty. to Assemble to Order** field on the line.</span></span>  
5.  <span data-ttu-id="dbda0-118">Dans la fenêtre **Lignes d'assemblage pour commande**, vérifiez ou modifiez les lignes d'assemblage pour commande en fonction du devis demandé par le client.</span><span class="sxs-lookup"><span data-stu-id="dbda0-118">In the **Assemble-to-Order Lines** window, review or modify the assembly order lines according to the quote that the customer is requesting.</span></span> <span data-ttu-id="dbda0-119">Des informations supplémentaires sont disponibles en choisissant **Afficher document** pour ouvrir la commande devis ouverte complète.</span><span class="sxs-lookup"><span data-stu-id="dbda0-119">If you want to view more information, choose the **Show Document** action to open the complete blanket quote order.</span></span> <span data-ttu-id="dbda0-120">Vous ne pouvez pas modifier le contenu de la plupart des champs, et vous ne pouvez pas reporter.</span><span class="sxs-lookup"><span data-stu-id="dbda0-120">You cannot change the contents of most fields, and you cannot post.</span></span>  
6.  <span data-ttu-id="dbda0-121">Lorsque vous avez ajusté les lignes d'ordre d'assemblage en fonction du devis, fermez la fenêtre **Lignes d'assemblage pour commande** pour revenir à la fenêtre **Devis**.</span><span class="sxs-lookup"><span data-stu-id="dbda0-121">When you have adjusted the assembly order lines according to the quote, close the **Assemble-to-Order Lines** window to return to the **Sales Quote** window.</span></span>  
7.  <span data-ttu-id="dbda0-122">Si le client accepte le devis, créez un document de vente pour l'élément d'assemblage qui a fait l'objet du devis.</span><span class="sxs-lookup"><span data-stu-id="dbda0-122">If the customer accepts the quote, then create a sales order for the quoted assembly item.</span></span> <span data-ttu-id="dbda0-123">Pour plus d'informations, voir [Créer des devis](sales-how-make-offers.md).</span><span class="sxs-lookup"><span data-stu-id="dbda0-123">For more information, see [Make Sales Quotes](sales-how-make-offers.md).</span></span> <span data-ttu-id="dbda0-124">Le devis d'assemblage associé et toutes les personnalisations sont liées à ce nouveau document de vente à préparer pour l'assemblage de l'article ou des articles à vendre.</span><span class="sxs-lookup"><span data-stu-id="dbda0-124">The linked assembly quote and any customizations are linked to that new sales order to prepare for assembly of the item or items to be sold.</span></span>  

## <a name="see-also"></a><span data-ttu-id="dbda0-125">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="dbda0-125">See Also</span></span>  
[<span data-ttu-id="dbda0-126">Gestion d'assemblage</span><span class="sxs-lookup"><span data-stu-id="dbda0-126">Assembly Management</span></span>](assembly-assemble-items.md)  
[<span data-ttu-id="dbda0-127">Utiliser les nomenclatures</span><span class="sxs-lookup"><span data-stu-id="dbda0-127">Work with Bills of Material</span></span>](inventory-how-work-BOMs.md)  
[<span data-ttu-id="dbda0-128">Stock</span><span class="sxs-lookup"><span data-stu-id="dbda0-128">Inventory</span></span>](inventory-manage-inventory.md)  
[<span data-ttu-id="dbda0-129">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="dbda0-129">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="dbda0-130">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="dbda0-130">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
