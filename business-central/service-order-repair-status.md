---
title: Configurer les états des commandes service et des réparations | Microsoft Docs
description: Vous devez configurer neuf options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/15/2020
ms.author: edupont
ms.openlocfilehash: f9b8fa679254e4886993ee29a1ceba1cf2542cda
ms.sourcegitcommit: 2d2dfb6c3eca1322835f0167dc7dab614346972e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/19/2020
ms.locfileid: "4038471"
---
# <a name="set-up-statuses-for-service-orders-and-repairs"></a><span data-ttu-id="9e564-103">Configurer les états des commandes service et des réparations</span><span class="sxs-lookup"><span data-stu-id="9e564-103">Set Up Statuses for Service Orders and Repairs</span></span>

<span data-ttu-id="9e564-104">Vous devez configurer des options d'état de réparation qui identifient la progression de la réparation et de l'entretien des articles de service dans les commandes service.</span><span class="sxs-lookup"><span data-stu-id="9e564-104">You must set up repair status options that identify the progress of repair and maintenance of service items in service orders.</span></span> <span data-ttu-id="9e564-105">Vous devez configurer au moins neuf options d'état réparation qui identifient les situations ou les actions effectuées lors de la maintenance des articles de service.</span><span class="sxs-lookup"><span data-stu-id="9e564-105">You must set up at least nine repair status options that identify situations or actions taken when servicing service items.</span></span>  

<span data-ttu-id="9e564-106">Vous pouvez définir le niveau de priorité des options d'état de commande service.</span><span class="sxs-lookup"><span data-stu-id="9e564-106">You can set the priority level for service order status options.</span></span> <span data-ttu-id="9e564-107">Quatre niveaux de priorité sont disponibles : **Très haute**, **Haute**, **Moyenne** et **Basse**.</span><span class="sxs-lookup"><span data-stu-id="9e564-107">The four priorities are **High**, **Medium High**, **Medium Low**, and **Low**.</span></span>  

<span data-ttu-id="9e564-108">Lorsque vous modifiez l'état réparation d'un article de service d'une commande service, l'état commande service est mis à jour.</span><span class="sxs-lookup"><span data-stu-id="9e564-108">When you change the repair status of a service item in a service order, the service order status is updated.</span></span> <span data-ttu-id="9e564-109">L'état réparation de chaque article de service est lié à l'état commande service.</span><span class="sxs-lookup"><span data-stu-id="9e564-109">The repair status of each service item is linked to the service order status.</span></span> <span data-ttu-id="9e564-110">Si les articles de service sont liés à plusieurs options d'état commande service, l'état de commande service dont la priorité est la plus élevée est sélectionné.</span><span class="sxs-lookup"><span data-stu-id="9e564-110">If the service items are linked to two or more service order status options, the service order status with the highest priority is selected.</span></span>  

<span data-ttu-id="9e564-111">Avant de pouvoir configurer un état de réparation, vous devez définir des priorités d'état de service.</span><span class="sxs-lookup"><span data-stu-id="9e564-111">Before you can set up a repair status, you must set up service status priorities.</span></span>

## <a name="to-set-up-service-status-priorities"></a><span data-ttu-id="9e564-112">Pour configurer les priorités état service</span><span class="sxs-lookup"><span data-stu-id="9e564-112">To set up service status priorities</span></span>

1. <span data-ttu-id="9e564-113">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **État commande service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9e564-113">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Service Order Status**, and then choose the related link.</span></span>  
2. <span data-ttu-id="9e564-114">Sélectionnez l'état commande service pour lequel vous voulez configurer une priorité.</span><span class="sxs-lookup"><span data-stu-id="9e564-114">Select the service order status you want to set a priority for.</span></span>  
3. <span data-ttu-id="9e564-115">Dans le champ **Priorité**, choisissez la priorité souhaitée pour cet état commande service.</span><span class="sxs-lookup"><span data-stu-id="9e564-115">In the **Priority** field, choose the priority you want for this service order status.</span></span>  

<span data-ttu-id="9e564-116">Répétez les étapes 2 et 3 pour configurer la priorité des quatre options état : **Suspendu**, **En cours**, **Terminé** et **En attente**.</span><span class="sxs-lookup"><span data-stu-id="9e564-116">Repeat steps 2 and 3 until you have set the priority for each of the four status options: **Pending**, **In Process**, **Finished**, and **On Hold**.</span></span>  

## <a name="to-set-up-a-repair-status"></a><span data-ttu-id="9e564-117">Pour configurer un état réparation</span><span class="sxs-lookup"><span data-stu-id="9e564-117">To set up a repair status</span></span>

1. <span data-ttu-id="9e564-118">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **État réparation**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="9e564-118">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Repair Status**, and then choose the related link.</span></span>
2. <span data-ttu-id="9e564-119">Créez un état réparation.</span><span class="sxs-lookup"><span data-stu-id="9e564-119">Create a new repair status.</span></span>  
3. <span data-ttu-id="9e564-120">Renseignez les champs **Code** et **Désignation**.</span><span class="sxs-lookup"><span data-stu-id="9e564-120">Fill in the **Code** and **Description** fields.</span></span>  
4. <span data-ttu-id="9e564-121">Dans le champ **État commande service**, choisissez l'état de la commande auquel lier l'état de réparation.</span><span class="sxs-lookup"><span data-stu-id="9e564-121">In the **Service Order Status** field, choose the order status to link the repair status to.</span></span> <span data-ttu-id="9e564-122">Le champ **Priorité** affiche la priorité de l'état de la commande service que vous avez choisie.</span><span class="sxs-lookup"><span data-stu-id="9e564-122">The **Priority** field displays the priority of the service order status you have chosen.</span></span>  
5. <span data-ttu-id="9e564-123">Choisissez un état réparation.</span><span class="sxs-lookup"><span data-stu-id="9e564-123">Choose a repair status.</span></span> <span data-ttu-id="9e564-124">Vous ne pouvez en choisir qu'un.</span><span class="sxs-lookup"><span data-stu-id="9e564-124">You can choose only one.</span></span> <span data-ttu-id="9e564-125">L'état réparation ne peut pas être lié à une option d'état réparation.</span><span class="sxs-lookup"><span data-stu-id="9e564-125">A repair status cannot be linked more than one repair status option.</span></span>  
6. <span data-ttu-id="9e564-126">Pour reporter des commandes service comprenant des articles de service avec cet état réparation, choisissez le champ **Report autorisé**.</span><span class="sxs-lookup"><span data-stu-id="9e564-126">To be able to post service orders, including service items, with this repair status, choose the **Posting Allowed** field.</span></span>  
7. <span data-ttu-id="9e564-127">Pour pouvoir faire passer manuellement l'option d'état de la commande service sur **Suspendu** dans des commandes service comprenant des articles de service avec l'état réparation, choisissez la case à cocher **État Suspendu autorisé**.</span><span class="sxs-lookup"><span data-stu-id="9e564-127">To be able to manually change the service order status option to **Pending** in service orders including service items with this repair status, choose the **Pending Status Allowed** check box.</span></span>  
8. <span data-ttu-id="9e564-128">Choisissez de la même manière les cases à cocher **État En cours autorisé**, **État Terminé autorisé** et **État En attente autorisé**.</span><span class="sxs-lookup"><span data-stu-id="9e564-128">Choose the **In Process Status Allowed**, **Finished Status Allowed**, and **On Hold Status Allowed** check boxes in the same way.</span></span>

<span data-ttu-id="9e564-129">Répétez ces étapes pour chaque option d'état réparation à créer.</span><span class="sxs-lookup"><span data-stu-id="9e564-129">Repeat these steps for each of the repair status options you want to create.</span></span>

## <a name="see-also"></a><span data-ttu-id="9e564-130">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="9e564-130">See Also</span></span>

[<span data-ttu-id="9e564-131">État commande service et état réparation</span><span class="sxs-lookup"><span data-stu-id="9e564-131">Service Order Status and Repair Status</span></span>](service-service-order-status-and-repair-status.md)  
[<span data-ttu-id="9e564-132">Paramétrage de la gestion des services</span><span class="sxs-lookup"><span data-stu-id="9e564-132">Setting Up Service Management</span></span>](service-setup-service.md)  
