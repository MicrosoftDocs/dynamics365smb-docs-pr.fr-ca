---
title: Comment transborder des articles | Microsoft Docs
description: "La fonctionnalité de transbordement est disponible si l'emplacement est configuré pour appeler un traitement des réceptions et des rangements entrepôt."
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
ms.openlocfilehash: 5e167129e8a8bc5f10a0f9de4c384c06de030bbb
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="how-to-cross-dock-items"></a><span data-ttu-id="9c3ae-103">Comment transborder des articles</span><span class="sxs-lookup"><span data-stu-id="9c3ae-103">How to: Cross-Dock Items</span></span>
<span data-ttu-id="9c3ae-104">La fonctionnalité de transbordement est disponible si l'emplacement est configuré pour appeler un traitement des réceptions et des rangements entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-104">Cross-docking functionality is available to you if you have set up your location to require warehouse receive and put-away processing.</span></span>  

<span data-ttu-id="9c3ae-105">Lorsque vous transbordez des articles, vous les manipulez en effectuant des réceptions et des expéditions, sans jamais les ranger. Vous évitez ainsi les processus de rangement et de prélèvement, et limitez la manipulation physique des articles.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-105">When you cross-dock items, you process items in receiving and shipping without ever placing them in storage, thereby expediting the item through the put-away and pick processes and limiting the physical handling of items.</span></span> <span data-ttu-id="9c3ae-106">Vous pouvez transborder des articles tant pour des livraisons que pour des bons de production.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-106">You can cross-dock items for both shipments and for production orders.</span></span> <span data-ttu-id="9c3ae-107">Lorsque vous préparez une livraison ou prélevez des articles pour la production, et que vous utilisez des zones, le programme tente d'abord automatiquement de prélever l'article dans une zone de transbordement avant d'envisager toute autre zone.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-107">When you prepare a shipment or pick items for production and you are using bins, the item is automatically picked from a cross-dock bin before any other bin.</span></span> <span data-ttu-id="9c3ae-108">Vous devez vérifier si les articles dont vous avez besoin sont disponibles dans la zone de transbordement avant de pouvoir accéder à ces articles dans leur zone de stockage habituel.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-108">You must look in the cross-dock area to see if the items you need are available there before you get the items in their usual storage area.</span></span>  

<span data-ttu-id="9c3ae-109">Lorsque vous avez calculé les quantités à transborder, des lignes rangement désignant la zone de transbordement sont créées pour effectuer les calculs de transbordement lors du report de la réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-109">If you have calculated cross-dock quantities, put-away lines to the cross-dock bin for cross-dock calculations are created when you post the receipt.</span></span> <span data-ttu-id="9c3ae-110">Les autres lignes rangement sont créées normalement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-110">Other put-away lines are created as usual.</span></span>  

<span data-ttu-id="9c3ae-111">Pour reporter immédiatement les articles à transborder afin qu'ils soient disponibles pour le prélèvement, vous devez aussi enregistrer un rangement pour les autres articles issus de la ligne réception, c'est-à-dire les articles à ranger.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-111">If you want to post the cross-dock items right away to make them available for picking, you must also register a put-away for the other items originating from the receipt line, namely those that need to be stored.</span></span> <span data-ttu-id="9c3ae-112">Si une partie seulement des articles d'une ligne réception doit être transbordée, efforcezvous de ranger le reste des articles le plus vite possible.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-112">If only some items on a receipt line are being cross-docked, you must therefore make an effort to put away the remaining items as quickly as possible.</span></span> <span data-ttu-id="9c3ae-113">Sinon, vous pouvez aussi instaurer dans votre entrepôt une politique encourageant les employés à effectuer le transbordement de lignes réception entières chaque fois que cela est possible.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-113">Alternatively, your warehouse policy could be to encourage cross-docking of entire receipt lines whenever possible.</span></span>  

<span data-ttu-id="9c3ae-114">Dans l'instruction de rangement, vous avez tout intérêt à effacer les lignes d'instructions, les lignes prélèvement et placement de chaque ligne réception, concernant des réceptions qui doivent être entièrement rangées.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-114">In the put-away instruction, you can to your advantage delete both Take and Place instruction lines for each receipt line that concern receipts that are to be fully put away in storage.</span></span> <span data-ttu-id="9c3ae-115">Ces lignes pourront être créées ultérieurement en tant que lignes rangement à partir de la feuille rangement ou de la réception reportée.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-115">These lines can later be created as put-away lines from the put-away worksheet or the posted receipt.</span></span> <span data-ttu-id="9c3ae-116">Une fois ces lignes effacées, vous pouvez ranger les articles à transborder et enregistrer les lignes concernant ces articles.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-116">When they are deleted, you can then put away and register the lines that concern cross-dock items.</span></span>  

<span data-ttu-id="9c3ae-117">Si vous avez sélectionné le champ **Utiliser feuille rangement** de la fiche emplacement et reporté votre réception en calculant les transbordements, toutes les lignes réception deviennent disponibles dans la feuille.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-117">If you have selected the **Use Put-away Worksheet** field on the location card and have posted your receipt with calculated cross-docks, all the receipt lines become available in the worksheet.</span></span> <span data-ttu-id="9c3ae-118">Les informations de transbordement sont perdues et ne peuvent plus être créées.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-118">The cross-dock information is lost and cannot be recreated.</span></span> <span data-ttu-id="9c3ae-119">Par conséquent, pour utiliser la fonctionnalité de transbordement, il vaut mieux que vous transfériez les lignes vers la feuille rangement en effaçant les instructions de rangement plutôt que d'utiliser la fonction de transfert automatique prévue dans le champ **Utiliser feuille rangement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-119">Therefore, if you wish to use cross-dock functionality, you should relay lines to the put-away worksheet by deleting put-away instructions rather than using the automatic relay function provided in the **Use Put-away Worksheet** field.</span></span>  

<span data-ttu-id="9c3ae-120">Lorsque vous reportez la réception entrepôt, et que le champ **Utiliser feuille rangement** n'est pas coché, les articles à transborder figurent dans des lignes distinctes dans l'instruction de rangement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-120">If you post the warehouse receipt and you do not have the **Use Put-away Worksheet** field selected, the items to be cross-docked appear as separate lines on the put-away instruction.</span></span> <span data-ttu-id="9c3ae-121">Le champ **Informations transbordement** de chaque ligne rangement indique si la ligne contient des articles à transborder, des articles provenant d'une même réception et devant tous être rangés ou des articles à ranger provenant d'une ligne réception dans laquelle certains des articles sont à transborder.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-121">The **Cross-Dock Information** field on each put-away line shows whether the line contains cross-dock items, items from the same receipt that all need to be stored, or items that need to be stored originating from a receipt line where some of the items are to be cross-docked.</span></span> <span data-ttu-id="9c3ae-122">Grâce à ce champ, les employés peuvent voir aisément pourquoi toute la quantité réceptionnée n'est pas rangée.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-122">With this field, employees can easily see why the full receipt quantity is not being placed in storage.</span></span>  

<span data-ttu-id="9c3ae-123">Le programme ne crée pas d'enregistrement distinct concernant les articles transbordés, mais les enregistre en tant qu'instructions de rangement ordinaires.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-123">The program does not keep separate records about items that have been cross-docked, but registers them as ordinary put-away instructions.</span></span>  

## <a name="to-set-up-the-warehouse-for-cross-docking"></a><span data-ttu-id="9c3ae-124">Pour configurer l'entrepôt en vue du transbordement</span><span class="sxs-lookup"><span data-stu-id="9c3ae-124">To set up the warehouse for cross-docking</span></span>  
1.  <span data-ttu-id="9c3ae-125">En cas d'utilisation de zones, configurez au moins une zone de transbordement. En cas d'utilisation d'un prélèvement et d'un rangement suggérés, configurez une zone de transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-125">Set up at least one cross-dock bin, if you are using bins. Set up a cross-dock zone, if you are using directed put-away and pick.</span></span>  

    <span data-ttu-id="9c3ae-126">Le champ **Zone transbordement** d'une zone de transbordement est activé. Ses types de zone devant être sélectionnés sont **Réception** et **Prélèvement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-126">A cross-dock bin has the **Cross-Dock Bin** field selected and must have both **Receive** and **Pick** bin types selected.</span></span> <span data-ttu-id="9c3ae-127">Pour plus d'informations, voir [Procédure : créer des zones](warehouse-how-to-create-individual-bins.md) et [Procédure : configurer des types de zone](warehouse-how-to-set-up-bin-types.md).</span><span class="sxs-lookup"><span data-stu-id="9c3ae-127">For more information, see [How to: Create Bins](warehouse-how-to-create-individual-bins.md) and [How to: Set Up Bin Types](warehouse-how-to-set-up-bin-types.md).</span></span>  

    <span data-ttu-id="9c3ae-128">Si vous utilisez des zones, créez une zone pour vos zones de transbordement, puis sélectionnez le champ **Zone transbordement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-128">If you are using zones, create a zone for your cross-dock bins, and select the **Cross-Dock Bin Zone** field.</span></span> <span data-ttu-id="9c3ae-129">Pour plus d'informations, reportez-vous à [Comment configurer des magasins de sorte qu'ils utilisent des emplacements](warehouse-how-to-set-up-locations-to-use-bins.md).</span><span class="sxs-lookup"><span data-stu-id="9c3ae-129">For more information, see [How to: Set Up Locations to Use Bins](warehouse-how-to-set-up-locations-to-use-bins.md).</span></span>  

2.  <span data-ttu-id="9c3ae-130">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Emplacement**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-130">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Location**, and then choose the related link.</span></span>  
3.  <span data-ttu-id="9c3ae-131">Dans la fenêtre **Emplacement**, sélectionnez l'emplacement dans lequel vous souhaitez configurer l'entrepôt pour le transbordement, puis choisissez l'action **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-131">In the **Location** window, select the location that you want to set up the warehouse for cross-docking, and then choose the **Edit** action.</span></span>  
4.  <span data-ttu-id="9c3ae-132">Sur le raccourci **Entrepôt**, cochez la case **Utiliser transbordement**, puis renseignez le champ **Calc. date d'échéance transbordement** en y indiquant la période pendant laquelle le programme doit rechercher des opportunités de transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-132">On the **Warehouse** FastTab, select the **Use Cross-Docking** check box and fill in the **Cross-Dock Due Date Calc.** field with the time to search for cross-dock opportunities.</span></span>

    <span data-ttu-id="9c3ae-133">L'option **Utiliser transbordement** n'est disponible que si vous avez coché les champs **Réception requise**, **Livraison requise**, **Prélèvement requis** et **Rangement requis**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-133">The **Use Cross-Docking** option is only available if the **Require Receive**, **Require Shipment**, **Require Pick**, and **Require Put-away** fields are selected.</span></span>  

5.  <span data-ttu-id="9c3ae-134">Si vous utilisez des zones, dans le raccourci **Zones**, renseignez le champ **Code de zone transbord.** en y insérant le code de la zone à utiliser comme zone de transbordement par défaut.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-134">If you are using bins, on the **Bins** FastTab, fill in the **Cross-Dock Bin Code** field with the code of the bin you would like to use as the default cross-dock bin.</span></span>  
6.  <span data-ttu-id="9c3ae-135">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), saisissez **Unité de stock**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-135">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Stockkeeping Unit**, and select the related link.</span></span>  
7.  <span data-ttu-id="9c3ae-136">Pour chaque article ou unité de stock que vous souhaitez pouvoir transborder, sélectionnez l'article, puis cliquez sur l'action **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-136">For each item or stockkeeping unit that you want to be able to cross-dock, select the item, and then choose the **Edit** action.</span></span>
8. <span data-ttu-id="9c3ae-137">Dans la fenêtre **Fiche unité de stock**, cochez la case **Utiliser transbordement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-137">In the **Stockkeeping Unit Card** window, select the **Use Cross-Docking** check box.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="9c3ae-138">Le transbordement n'est possible que si votre emplacement est configuré pour exiger un traitement des réceptions et des rangements entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-138">Cross-docking is only possible if your location is set up to require warehouse receive and put-away processing.</span></span>  

## <a name="to-cross-dock-items-without-viewing-the-opportunities"></a><span data-ttu-id="9c3ae-139">Pour transborder des articles sans afficher les opportunités</span><span class="sxs-lookup"><span data-stu-id="9c3ae-139">To cross-dock items without viewing the opportunities</span></span>  
1.  <span data-ttu-id="9c3ae-140">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Réceptions entrepôt**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-140">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Warehouse Receipts**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="9c3ae-141">Créer des réceptions entrepôt pour un article qui est arrivé et qui pourrait nécessiter un transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-141">Create a warehouse receipts for an item that has arrived and can perhaps be cross-docked.</span></span> <span data-ttu-id="9c3ae-142">Pour plus d'informations, voir [Procédure : réceptionner des articles](warehouse-how-receive-items.md).</span><span class="sxs-lookup"><span data-stu-id="9c3ae-142">For more information, see [How to: Receive Items](warehouse-how-receive-items.md).</span></span>  
3.  <span data-ttu-id="9c3ae-143">Renseignez le champ **Qté à recevoir**, puis choisissez l'action **Calculer transbordement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-143">Fill in the **Qty. to Receive** field, and then choose the **Calculate Cross-Dock** action.</span></span>  

    <span data-ttu-id="9c3ae-144">Les documents sources sortants demandant les articles programmés pour quitter l'entrepôt durant la période indiquée par la formule date sont identifiés.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-144">Outbound source documents requesting the items that are scheduled to leave the warehouse within the date formula time period are identified.</span></span>  [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="9c3ae-145"> calcule les quantités pour que vous puissiez effectuer un maximum de transbordements pour éviter de ranger des articles, sans entasser trop d'articles dans la zone de transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-145"> calculates quantities so that you can cross-dock as much as possible and avoid having to put items away, without piling up too many items in the cross-dock area.</span></span> <span data-ttu-id="9c3ae-146">La valeur du champ **Qté à transborder** est ainsi la plus petite de ces deux valeurs : la somme de toutes les lignes sortantes demandant l'article avant la fin de la période de prévision des transbordements, moins la quantité d'articles déjà placés dans la zone de transbordement ou la valeur du champ **Qté à recevoir** de la ligne réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-146">The value in the **Qty. to Cross-Dock** field is thus the sum of all the outbound lines requesting the item within the look-ahead period minus the quantity of the items that have already been placed in the cross-dock area, or it is the value in the **Qty. to Receive** field on the receipt line, whichever is smaller.</span></span> <span data-ttu-id="9c3ae-147">(Vous ne pouvez pas transborder plus d'articles que vous en avez reçus.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-147">You cannot cross-dock more than you have received.</span></span>  

4.  <span data-ttu-id="9c3ae-148">Pour transborder la quantité en suivant la procédure indiquée, reportez la réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-148">If you want to cross-dock the quantity as suggested, post the receipt.</span></span> <span data-ttu-id="9c3ae-149">Vous pouvez aussi décider de modifier la quantité à transborder pour augmenter ou réduire sa valeur, puis reporter la réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-149">You can also decide to change the quantity to cross-dock to a higher or lower value and then post the receipt.</span></span>  

    <span data-ttu-id="9c3ae-150">Les quantités à transborder apparaissent maintenant en tant que lignes dans l'instruction de rangement, en supposant que vous n'ayez pas activé le champ **Utiliser feuille rangement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-150">The amounts to be cross-docked now appear as lines in the put-away instruction, assuming the **Use Put-away Worksheet** field is cleared.</span></span> <span data-ttu-id="9c3ae-151">Les quantités non destinées au transbordement apparaissent aussi en tant que lignes dans l'instruction de rangement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-151">The quantities not cross-docked also become lines in the put-away instruction.</span></span>  

    <span data-ttu-id="9c3ae-152">Si vous possédez des zones, les articles transbordés ont été affectés à la zone de transbordement par défaut défini dans la fiche emplacement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-152">If you have bins, the cross-docked items have been assigned to the default cross-dock bin defined on the location card.</span></span>  

5.  <span data-ttu-id="9c3ae-153">Supprimez les lignes **prélèvement** et **placement** pour les articles qui ne font l'objet d'aucun transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-153">Delete the **Take** and **Place** lines for items that are not going to be cross-docked at all.</span></span>  
6.  <span data-ttu-id="9c3ae-154">Imprimez l'instruction de rangement pour les lignes restantes, puis placez les quantités de la réception à ranger dans les zones appropriées ou dans la zone appropriée de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-154">Print the put-away instruction for the remaining lines, and place the quantities of the receipt that need to be stored in the appropriate bins or in the appropriate area of the warehouse.</span></span> <span data-ttu-id="9c3ae-155">Placez les articles à transborder dans la zone qui leur est attribuée par la politique de l'entrepôt.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-155">Place the cross-dock items in the area or bin designated for them by warehouse policy.</span></span> <span data-ttu-id="9c3ae-156">Parfois, la politique de l'entrepôt peut nécessiter simplement de les laisser dans la zone de réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-156">Sometimes, warehouse policy might require that you to just leave them in the receiving area.</span></span>  
7.  <span data-ttu-id="9c3ae-157">Pour enregistrer les articles transbordés comme étant rangés et disponibles pour le prélèvement, choisissez l'action **Enregistrer**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-157">To register the cross-docked items as being put-away and available for picking, choose the **Register** action.</span></span>  

## <a name="to-cross-dock-items-after-viewing-the-opportunities"></a><span data-ttu-id="9c3ae-158">Pour transborder des articles après avoir affiché les opportunités</span><span class="sxs-lookup"><span data-stu-id="9c3ae-158">To cross-dock items after viewing the opportunities</span></span>  
1.  <span data-ttu-id="9c3ae-159">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Réceptions entrepôt**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-159">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Warehouse Receipts**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="9c3ae-160">Créer des réceptions entrepôt pour un article qui est arrivé et qui pourrait nécessiter un transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-160">Create a warehouse receipts for an item that has arrived and can perhaps be cross-docked.</span></span> <span data-ttu-id="9c3ae-161">Pour plus d'informations, voir [Procédure : réceptionner des articles](warehouse-how-receive-items.md).</span><span class="sxs-lookup"><span data-stu-id="9c3ae-161">For more information, see [How to: Receive Items](warehouse-how-receive-items.md).</span></span>  

    <span data-ttu-id="9c3ae-162">Vous souhaitez afficher les lignes document source demandant l'article avant de reporter la réception.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-162">You want to view the source document lines that are requesting the item before you post the receipt.</span></span>  
3.  <span data-ttu-id="9c3ae-163">Choisissez l'action **Calculer transbordement**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-163">Choose the **Calculate Cross-Dock** action.</span></span>  

    <span data-ttu-id="9c3ae-164">Dans la fenêtre **Opportunités transbordement**, vous pouvez voir les informations les plus importantes concernant les lignes demandant l'article, comme le type de document, la quantité demandée et la date d'échéance.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-164">In the **Cross-Dock Opportunities** window you can see the most important details about the lines requesting the item, such as type of document, quantity requested, and due date.</span></span> <span data-ttu-id="9c3ae-165">Ces informations peuvent vous aider à décider de la quantité d'articles à transborder, de l'endroit où placer ces articles dans la zone de transbordement ou de la manière de les regrouper.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-165">This information might help you to decide how much to cross-dock, where to place the items in the cross-dock area, or how to group them.</span></span>  

4.  <span data-ttu-id="9c3ae-166">Choisissez l'action **Remplir quantité à transborder** pour savoir comment les quantités figurant dans les lignes réception sont calculées.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-166">Choose **Autofill Qty. to Cross-Dock** action to see how the quantities on the receipt lines are calculated.</span></span> <span data-ttu-id="9c3ae-167">Lorsque vous modifiez le nombre d'articles dans le champ **Qté à transborder** de chaque ligne, le calcul est mis à jour lorsque vous effectuez des modifications.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-167">When you change the number of items in the **Qty. to Cross-Dock** field on each line, the calculation is updated as you make changes.</span></span> <span data-ttu-id="9c3ae-168">Cela ne signifie pas que le bon de production ou de livraison concerné reçoit réellement les articles dont le transbordement est proposé, car ces opérations ne sont qu'un simple test.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-168">This does not mean that the particular shipment or production order will actually receive the items being suggested for cross-docking, because these manipulations are for testing purposes only.</span></span> <span data-ttu-id="9c3ae-169">Toutefois, ce processus peut être intéressant à titre d'information si plusieurs unités de mesure sont utilisées.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-169">The process can be informative, however, if more than one unit of measure is involved.</span></span>  
5.  <span data-ttu-id="9c3ae-170">Pour réserver une quantité de l'article pour une ligne commande donnée, placez le curseur sur cette ligne, puis choisissez l'action **Réserver**.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-170">If you want to reserve a quantity of the item for a particular order line, place your cursor on that line, and then choose the **Reserve** action.</span></span> <span data-ttu-id="9c3ae-171">Dans la fenêtre **Réservation**, vous pouvez maintenant réserver n'importe quelle quantité disponible de l'article pour cette commande.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-171">In the **Reservation** window, you can now reserve any available quantity of the item for this specific order.</span></span> <span data-ttu-id="9c3ae-172">Cette réservation ne diffère pas des autres réservations, et le fait qu'elle ait été créée au cours d'un transbordement ne lui confère aucune priorité.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-172">This reservation is like any other reservation and does not have higher priority because it was created in connection with cross-docking.</span></span> <span data-ttu-id="9c3ae-173">Pour plus d'informations, voir [Procédure : réserver des articles](inventory-how-to-reserve-items.md).</span><span class="sxs-lookup"><span data-stu-id="9c3ae-173">For more information, see [How to: Reserve Items](inventory-how-to-reserve-items.md).</span></span>   
6.  <span data-ttu-id="9c3ae-174">Lorsque vous avez fini de refaire les calculs et que la réservation est terminée, sélectionnez le bouton **OK** pour insérer le calcul que vous venez de réviser dans le champ **Qté à transborder** de la ligne réception ou choisissez le bouton **Annuler** pour revenir à la réception entrepôt et y recalculer le transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-174">When you are finished recalculating or reserving, choose the **OK** button to bring the calculation as you have revised it into the **Qty. to Cross-Dock** field on the receipt line, or choose the **Cancel** button if you want to return to the warehouse receipt, where you can calculate the cross-dock again if you wish.</span></span>  
7.  <span data-ttu-id="9c3ae-175">Reportez à présent la réception. Vous pouvez ensuite passer à l'instruction de rangement, comme l'indiquent les étapes 3 à 7 de la section « Pour transborder des articles sans afficher les opportunités ».</span><span class="sxs-lookup"><span data-stu-id="9c3ae-175">Now post the receipt, and you can continue in the put-away instruction as described in steps 3 through 7 in the “To cross-dock items without viewing the opportunities” section.</span></span>  

> [!NOTE]  
>  <span data-ttu-id="9c3ae-176">Dans le rangement entrepôt, vous pouvez continuer de modifier les quantités en cours de transbordement ou de rangement dans le stock, selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-176">In the warehouse put-away, you can continue to change the quantities that are being put away in storage or cross-docked, as necessary.</span></span> <span data-ttu-id="9c3ae-177">Par exemple, vous pouvez décider de transborder une quantité supplémentaire afin d'expédier l'enregistrement du transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-177">For example, you might decide to cross-dock an extra quantity to expedite the cross-dock registration.</span></span>  

## <a name="to-view-cross-docked-items-in-a-shipment-or-pick-worksheet"></a><span data-ttu-id="9c3ae-178">Pour afficher des articles transbordés dans une feuille prélèvement ou livraison</span><span class="sxs-lookup"><span data-stu-id="9c3ae-178">To view cross-docked items in a shipment or pick worksheet</span></span>  
<span data-ttu-id="9c3ae-179">Si vous utilisez des zones, chaque fois que vous ouvrez une livraison ou la feuille prélèvement, vous pouvez voir le calcul mis à jour de la quantité de chaque article dans les zones de transbordement. Cette information est précieuse si vous attendez l'arrivée d'un article.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-179">If you are using bins, you can see, each time you open a shipment or the pick worksheet, an updated calculation of the quantity of each item in the cross-dock bins. This is valuable information if you are waiting for an item to come in.</span></span> <span data-ttu-id="9c3ae-180">Dès que vous voyez qu'un article est disponible dans la zone de transbordement, vous pouvez rapidement créer un prélèvement pour tous les articles de la livraison.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-180">When you see that the item is available in the cross-dock bin, you can then quickly create a pick for all the items on the shipment.</span></span> <span data-ttu-id="9c3ae-181">Dans la feuille prélèvement, vous pouvez modifier les lignes, puis créer un prélèvement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-181">In the pick worksheet, you can modify the lines as appropriate and then create a pick.</span></span>  

<span data-ttu-id="9c3ae-182">Lorsque vous prélevez des articles à livrer, vous devez commencer par rechercher les articles concernés dans la zone de transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-182">You have to look for items in the cross-dock area first when you pick items for shipment.</span></span> <span data-ttu-id="9c3ae-183">Si, au cours du processus de réception, vous avez noté les documents origine à la base du transbordement, vous saurez plus précisément si l'article que vous recherchez se trouve ou non dans la zone de transbordement.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-183">If you have noted during the receipt process the source documents that were the basis for cross-docking, you have a better idea of whether the item can be found in the cross-dock area or not.</span></span>  

<span data-ttu-id="9c3ae-184">Après la libération d'un bon de production, les lignes sont disponibles dans la feuille prélèvement et vous pouvez consulter le champ **Qté zone transbordement** pour voir si les articles que vous attendez sont arrivés et ont été placés dans les zones de transbordement. Lorsque vous créez une instruction de prélèvement, le programme vous propose de prélever d'abord les articles transbordés, après quoi il recherchera les articles dans les zones de stockage.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-184">When a production order has been released, the lines are available in the pick worksheet, and you can see in the **Qty. on Cross-Dock Bin** field whether the items you are waiting for have arrived and been placed in the cross-dock bins. When you create a pick instruction, the program suggests that you first pick the cross-docked items and will only later search for the item in storage bins.</span></span>  

<span data-ttu-id="9c3ae-185">Si vous n'utilisez pas de zones, n'oubliez pas de vérifier, de temps en temps, la zone de transbordement ou consultez les notifications de réception pour connaître l'arrivée des articles destinés à la production.</span><span class="sxs-lookup"><span data-stu-id="9c3ae-185">If you are not using bins, you must remember to check the cross-dock area from time to time, or rely on notifications from receipts that items for production have arrived.</span></span>  

## <a name="see-also"></a><span data-ttu-id="9c3ae-186">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9c3ae-186">See Also</span></span>  
[<span data-ttu-id="9c3ae-187">Gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="9c3ae-187">Warehouse Management</span></span>](warehouse-manage-warehouse.md)  
[<span data-ttu-id="9c3ae-188">Stock</span><span class="sxs-lookup"><span data-stu-id="9c3ae-188">Inventory</span></span>](inventory-manage-inventory.md)  
<span data-ttu-id="9c3ae-189">[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)   </span><span class="sxs-lookup"><span data-stu-id="9c3ae-189">[Setting Up Warehouse Management](warehouse-setup-warehouse.md)   </span></span>  
<span data-ttu-id="9c3ae-190">[Gestion d'assemblage](assembly-assemble-items.md)  </span><span class="sxs-lookup"><span data-stu-id="9c3ae-190">[Assembly Management](assembly-assemble-items.md)  </span></span>  
[<span data-ttu-id="9c3ae-191">Détails de conception : gestion d'entrepôt</span><span class="sxs-lookup"><span data-stu-id="9c3ae-191">Design Details: Warehouse Management</span></span>](design-details-warehouse-management.md)  
<span data-ttu-id="9c3ae-192">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="9c3ae-192">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>  
