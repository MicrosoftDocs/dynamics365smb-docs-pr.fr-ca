---
title: Comment bloquer des articles pour la vente ou pour l'achat
description: Dans Business Central, un article peut être signalé comme bloqué pour la vente, bloqué pour l'achat ou bloqué dans tous les cas.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 8c98e4b893783c795a49e05ab04dc70b03161c6a
ms.sourcegitcommit: bf5f89dfaf5ad9f8f9902941cf3dac3e9f3553e5
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 05/22/2019
ms.locfileid: "1594270"
---
# <a name="block-items-from-sales-or-purchasing"></a><span data-ttu-id="deec6-103">Bloquer des articles pour la vente ou pour l'achat</span><span class="sxs-lookup"><span data-stu-id="deec6-103">Block Items from Sales or Purchasing</span></span>
<span data-ttu-id="deec6-104">Vous pouvez bloquer un article pour empêcher sa saisie dans des lignes vente ou achat, et vous pouvez le bloquer pour empêcher son report dans n'importe quelle transaction.</span><span class="sxs-lookup"><span data-stu-id="deec6-104">You can block an item from being entered on sales or purchase lines, and you can block it from being posted in any transaction.</span></span>  

<span data-ttu-id="deec6-105">Le tableau suivant illustre ce qui se produit lorsque les articles sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="deec6-105">The following table illustrates what occurs when items are blocked.</span></span>  

|<span data-ttu-id="deec6-106">Option</span><span class="sxs-lookup"><span data-stu-id="deec6-106">Option</span></span>|<span data-ttu-id="deec6-107">Description</span><span class="sxs-lookup"><span data-stu-id="deec6-107">Description</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="deec6-108">**Bloqué à la vente**</span><span class="sxs-lookup"><span data-stu-id="deec6-108">**Sales Blocked**</span></span>|<span data-ttu-id="deec6-109">Vous ne pouvez pas saisir l'article dans un document vente ou dans un journal article vente.</span><span class="sxs-lookup"><span data-stu-id="deec6-109">You cannot enter the item in a sales document or in a sales item journal.</span></span>|  
|<span data-ttu-id="deec6-110">**Bloqué à l'achat**</span><span class="sxs-lookup"><span data-stu-id="deec6-110">**Purchasing Blocked**</span></span>|<span data-ttu-id="deec6-111">Vous ne pouvez pas saisir l'article dans un document achat, dans un journal article achat, ou dans les processus de planification achat.</span><span class="sxs-lookup"><span data-stu-id="deec6-111">You cannot enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.</span></span>|  
|<span data-ttu-id="deec6-112">**Bloqué**</span><span class="sxs-lookup"><span data-stu-id="deec6-112">**Blocked**</span></span>|<span data-ttu-id="deec6-113">Vous ne pouvez pas utiliser l'article pour une transaction d'article.</span><span class="sxs-lookup"><span data-stu-id="deec6-113">You cannot use the item for any item transaction.</span></span>|  

> [!NOTE]
> <span data-ttu-id="deec6-114">Les articles bloqués peuvent être retournés.</span><span class="sxs-lookup"><span data-stu-id="deec6-114">Blocked items can be returned.</span></span> <span data-ttu-id="deec6-115">Cela signifie qu'aucun des paramètres ci-dessus ne s'applique lorsque l'article est utilisé sur des retours et des notes de crédit.</span><span class="sxs-lookup"><span data-stu-id="deec6-115">This means that none of the above settings apply when the item is used on return orders and credit memos.</span></span>

## <a name="to-block-an-item-from-being-entered-on-sales-lines"></a><span data-ttu-id="deec6-116">Pour bloquer un article pour la saisie sur des lignes vente</span><span class="sxs-lookup"><span data-stu-id="deec6-116">To block an item from being entered on sales lines</span></span>  

1.  <span data-ttu-id="deec6-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="deec6-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="deec6-118">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à la vente**.</span><span class="sxs-lookup"><span data-stu-id="deec6-118">Select the item that you want to block, and then select the **Sales Blocked** check box.</span></span>  

<span data-ttu-id="deec6-119">Si vous essayez de saisir l'article sur un document vente ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="deec6-119">If you try to enter the item on a sales document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-entered-on-purchase-lines"></a><span data-ttu-id="deec6-120">Pour bloquer un article pour la saisie sur des lignes achat</span><span class="sxs-lookup"><span data-stu-id="deec6-120">To block an item from being entered on purchase lines</span></span>  

1.  <span data-ttu-id="deec6-121">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="deec6-121">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="deec6-122">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à l'achat**.</span><span class="sxs-lookup"><span data-stu-id="deec6-122">Select the item that you want to block, and then select the **Purchasing Blocked** check box.</span></span>  

<span data-ttu-id="deec6-123">Si vous essayez de saisir l'article sur un document achat ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="deec6-123">If you try to enter the item on a purchase document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-posted"></a><span data-ttu-id="deec6-124">Pour bloquer un article et empêcher son report</span><span class="sxs-lookup"><span data-stu-id="deec6-124">To block an item from being posted</span></span>
1. <span data-ttu-id="deec6-125">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="deec6-125">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>
2. <span data-ttu-id="deec6-126">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué**.</span><span class="sxs-lookup"><span data-stu-id="deec6-126">Select the item that you want to block, and then select the **Blocked** check box.</span></span>

<span data-ttu-id="deec6-127">Si vous essayez de reporter tout type de transaction pour l'article, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="deec6-127">If you try to post any type of transaction for the item, you will now get an error message that the item is blocked.</span></span>

## <a name="see-also"></a><span data-ttu-id="deec6-128">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="deec6-128">See Also</span></span>  
[<span data-ttu-id="deec6-129">Enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="deec6-129">Register New Items</span></span>](inventory-how-register-new-items.md)  
[<span data-ttu-id="deec6-130">Stock</span><span class="sxs-lookup"><span data-stu-id="deec6-130">Inventory</span></span>](inventory-manage-inventory.md)  
