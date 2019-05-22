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
ms.openlocfilehash: e13d59e939e71a252e08afc26d2fb1ec76b247c9
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1238542"
---
# <a name="block-items-from-sales-or-purchasing"></a><span data-ttu-id="c7ebe-103">Bloquer des articles pour la vente ou pour l'achat</span><span class="sxs-lookup"><span data-stu-id="c7ebe-103">Block Items from Sales or Purchasing</span></span>
<span data-ttu-id="c7ebe-104">Vous pouvez bloquer un article pour empêcher sa saisie dans des lignes vente ou achat, et vous pouvez le bloquer pour empêcher son report dans n'importe quelle transaction.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-104">You can block an item from being entered on sales or purchase lines, and you can block it from being posted in any transaction.</span></span>  

<span data-ttu-id="c7ebe-105">Le tableau suivant illustre ce qui se produit lorsque les articles sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-105">The following table illustrates what occurs when items are blocked.</span></span>  

|<span data-ttu-id="c7ebe-106">Option</span><span class="sxs-lookup"><span data-stu-id="c7ebe-106">Option</span></span>|<span data-ttu-id="c7ebe-107">Description</span><span class="sxs-lookup"><span data-stu-id="c7ebe-107">Description</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="c7ebe-108">**Bloqué à la vente**</span><span class="sxs-lookup"><span data-stu-id="c7ebe-108">**Sales Blocked**</span></span>|<span data-ttu-id="c7ebe-109">Vous ne pouvez pas saisir l'article dans un document vente ou dans un journal article vente.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-109">You cannot enter the item in a sales document or in a sales item journal.</span></span>|  
|<span data-ttu-id="c7ebe-110">**Bloqué à l'achat**</span><span class="sxs-lookup"><span data-stu-id="c7ebe-110">**Purchasing Blocked**</span></span>|<span data-ttu-id="c7ebe-111">Vous ne pouvez pas saisir l'article dans un document achat, dans un journal article achat, ou dans les processus de planification achat.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-111">You cannot enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.</span></span>|  
|<span data-ttu-id="c7ebe-112">**Bloqué**</span><span class="sxs-lookup"><span data-stu-id="c7ebe-112">**Blocked**</span></span>|<span data-ttu-id="c7ebe-113">Vous ne pouvez pas utiliser l'article pour une transaction d'article.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-113">You cannot use the item for any item transaction.</span></span> <span data-ttu-id="c7ebe-114">Pour plus d'informations sur le blocage d'un article pour quelle que raison possible, voir Fiche article.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-114">For more information about blocking an item for all purposes, see Item Card.</span></span>|  

## <a name="to-block-an-item-from-being-entered-on-sales-lines"></a><span data-ttu-id="c7ebe-115">Pour bloquer un article pour la saisie sur des lignes vente</span><span class="sxs-lookup"><span data-stu-id="c7ebe-115">To block an item from being entered on sales lines</span></span>  

1.  <span data-ttu-id="c7ebe-116">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-116">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="c7ebe-117">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à la vente**.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-117">Select the item that you want to block, and then select the **Sales Blocked** check box.</span></span>  

<span data-ttu-id="c7ebe-118">Si vous essayez de saisir l'article sur un document vente ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-118">If you try to enter the item on a sales document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-entered-on-purchase-lines"></a><span data-ttu-id="c7ebe-119">Pour bloquer un article pour la saisie sur des lignes achat</span><span class="sxs-lookup"><span data-stu-id="c7ebe-119">To block an item from being entered on purchase lines</span></span>  

1.  <span data-ttu-id="c7ebe-120">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-120">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="c7ebe-121">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à l'achat**.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-121">Select the item that you want to block, and then select the **Purchasing Blocked** check box.</span></span>  

<span data-ttu-id="c7ebe-122">Si vous essayez de saisir l'article sur un document achat ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-122">If you try to enter the item on a purchase document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-posted"></a><span data-ttu-id="c7ebe-123">Pour bloquer un article et empêcher son report</span><span class="sxs-lookup"><span data-stu-id="c7ebe-123">To block an item from being posted</span></span>
1. <span data-ttu-id="c7ebe-124">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-124">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>
2. <span data-ttu-id="c7ebe-125">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué**.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-125">Select the item that you want to block, and then select the **Blocked** check box.</span></span>

<span data-ttu-id="c7ebe-126">Si vous essayez de reporter tout type de transaction pour l'article, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="c7ebe-126">If you try to post any type of transaction for the item, you will now get an error message that the item is blocked.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7ebe-127">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c7ebe-127">See Also</span></span>  
[<span data-ttu-id="c7ebe-128">Enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="c7ebe-128">Register New Items</span></span>](inventory-how-register-new-items.md)  
[<span data-ttu-id="c7ebe-129">Stock</span><span class="sxs-lookup"><span data-stu-id="c7ebe-129">Inventory</span></span>](inventory-manage-inventory.md)  
