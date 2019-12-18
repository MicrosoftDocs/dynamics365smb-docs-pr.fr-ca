---
title: Comment bloquer des articles pour la vente ou pour l'achat
description: Dans Business Central, un article peut être signalé comme bloqué pour la vente, bloqué pour l'achat ou bloqué dans tous les cas.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 12/04/2019
ms.author: sgroespe
ms.openlocfilehash: 0218cf1b4982b9e8c5b5c2817590bc5ebd8f1941
ms.sourcegitcommit: b6e506a45a1cd632294bafa1c959746cc3a144f6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/06/2019
ms.locfileid: "2896071"
---
# <a name="block-items-from-sales-or-purchasing"></a><span data-ttu-id="32fa9-103">Bloquer des articles pour la vente ou pour l'achat</span><span class="sxs-lookup"><span data-stu-id="32fa9-103">Block Items from Sales or Purchasing</span></span>
<span data-ttu-id="32fa9-104">Vous pouvez bloquer un article pour empêcher sa saisie dans des lignes vente ou achat, et vous pouvez le bloquer pour empêcher son report dans n'importe quelle transaction.</span><span class="sxs-lookup"><span data-stu-id="32fa9-104">You can block an item from being entered on sales or purchase lines, and you can block it from being posted in any transaction.</span></span>  

<span data-ttu-id="32fa9-105">Le tableau suivant illustre ce qui se produit lorsque les articles sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="32fa9-105">The following table illustrates what occurs when items are blocked.</span></span>  

|<span data-ttu-id="32fa9-106">Option</span><span class="sxs-lookup"><span data-stu-id="32fa9-106">Option</span></span>|<span data-ttu-id="32fa9-107">Description</span><span class="sxs-lookup"><span data-stu-id="32fa9-107">Description</span></span>|  
|--------------------|------------|  
|<span data-ttu-id="32fa9-108">**Bloqué à la vente**</span><span class="sxs-lookup"><span data-stu-id="32fa9-108">**Sales Blocked**</span></span>|<span data-ttu-id="32fa9-109">Vous ne pouvez pas saisir l'article dans un document vente ou dans un journal article vente.</span><span class="sxs-lookup"><span data-stu-id="32fa9-109">You cannot enter the item in a sales document or in a sales item journal.</span></span>|  
|<span data-ttu-id="32fa9-110">**Bloqué à l'achat**</span><span class="sxs-lookup"><span data-stu-id="32fa9-110">**Purchasing Blocked**</span></span>|<span data-ttu-id="32fa9-111">Vous ne pouvez pas saisir l'article dans un document achat, dans un journal article achat, ou dans les processus de planification achat.</span><span class="sxs-lookup"><span data-stu-id="32fa9-111">You cannot enter the item in a purchase document, in a purchase item journal, or in purchase planning processes.</span></span>|  
|<span data-ttu-id="32fa9-112">**Bloqué**</span><span class="sxs-lookup"><span data-stu-id="32fa9-112">**Blocked**</span></span>|<span data-ttu-id="32fa9-113">Vous ne pouvez pas utiliser l'article pour une transaction d'article.</span><span class="sxs-lookup"><span data-stu-id="32fa9-113">You cannot use the item for any item transaction.</span></span>|  

> [!NOTE]
> <span data-ttu-id="32fa9-114">Les articles bloqués peuvent être retournés.</span><span class="sxs-lookup"><span data-stu-id="32fa9-114">Blocked items can be returned.</span></span> <span data-ttu-id="32fa9-115">Cela signifie qu'aucun des paramètres ci-dessus ne s'applique lorsque l'article est utilisé sur des retours et des notes de crédit.</span><span class="sxs-lookup"><span data-stu-id="32fa9-115">This means that none of the above settings apply when the item is used on return orders and credit memos.</span></span>

<span data-ttu-id="32fa9-116">Lorsque vous utilisez la fonction **Copier le document** pour créer des documents à partir de documents existants, vous êtes averti si des articles sur les lignes du document source sont bloqués.</span><span class="sxs-lookup"><span data-stu-id="32fa9-116">When you use the **Copy Document** function to create new documents based on existing documents, you are notified if any items on the source document lines are blocked.</span></span> <span data-ttu-id="32fa9-117">Les lignes de document bloquées sont exclues du nouveau document et une notification affiche une vue d'ensemble de toutes les lignes de document bloquées dans le document source.</span><span class="sxs-lookup"><span data-stu-id="32fa9-117">The blocked document lines are excluded from the new document, and a notification shows an overview of all document lines that are blocked in the source document.</span></span>

## <a name="to-block-an-item-from-being-entered-on-sales-lines"></a><span data-ttu-id="32fa9-118">Pour bloquer un article pour la saisie sur des lignes vente</span><span class="sxs-lookup"><span data-stu-id="32fa9-118">To block an item from being entered on sales lines</span></span>  

1.  <span data-ttu-id="32fa9-119">Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="32fa9-119">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="32fa9-120">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à la vente**.</span><span class="sxs-lookup"><span data-stu-id="32fa9-120">Select the item that you want to block, and then select the **Sales Blocked** check box.</span></span>  

<span data-ttu-id="32fa9-121">Si vous essayez de saisir l'article sur un document vente ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="32fa9-121">If you try to enter the item on a sales document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-entered-on-purchase-lines"></a><span data-ttu-id="32fa9-122">Pour bloquer un article pour la saisie sur des lignes achat</span><span class="sxs-lookup"><span data-stu-id="32fa9-122">To block an item from being entered on purchase lines</span></span>  

1.  <span data-ttu-id="32fa9-123">Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="32fa9-123">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="32fa9-124">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à l'achat**.</span><span class="sxs-lookup"><span data-stu-id="32fa9-124">Select the item that you want to block, and then select the **Purchasing Blocked** check box.</span></span>  

<span data-ttu-id="32fa9-125">Si vous essayez de saisir l'article sur un document achat ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="32fa9-125">If you try to enter the item on a purchase document or journal line, you will now get an error message that the item is blocked.</span></span>

## <a name="to-block-an-item-from-being-posted"></a><span data-ttu-id="32fa9-126">Pour bloquer un article et empêcher son report</span><span class="sxs-lookup"><span data-stu-id="32fa9-126">To block an item from being posted</span></span>
1. <span data-ttu-id="32fa9-127">Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="32fa9-127">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Items**, and then choose the related link.</span></span>
2. <span data-ttu-id="32fa9-128">Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué**.</span><span class="sxs-lookup"><span data-stu-id="32fa9-128">Select the item that you want to block, and then select the **Blocked** check box.</span></span>

<span data-ttu-id="32fa9-129">Si vous essayez de reporter tout type de transaction pour l'article, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.</span><span class="sxs-lookup"><span data-stu-id="32fa9-129">If you try to post any type of transaction for the item, you will now get an error message that the item is blocked.</span></span>

## <a name="see-also"></a><span data-ttu-id="32fa9-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32fa9-130">See Also</span></span>  
[<span data-ttu-id="32fa9-131">Enregistrer de nouveaux articles</span><span class="sxs-lookup"><span data-stu-id="32fa9-131">Register New Items</span></span>](inventory-how-register-new-items.md)  
[<span data-ttu-id="32fa9-132">Inventaire</span><span class="sxs-lookup"><span data-stu-id="32fa9-132">Inventory</span></span>](inventory-manage-inventory.md)  
