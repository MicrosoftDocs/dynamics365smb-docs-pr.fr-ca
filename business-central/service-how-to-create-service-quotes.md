---
title: "Procédure : créer des devis service | Microsoft Docs"
description: "Utilisez la fenêtre **Devis service** pour créer des documents dans lesquels vous saisissez des informations sur un service, tel que réparation et maintenance, pour des articles de service à la demande du client. Vous pouvez utiliser un devis service comme brouillon d'une commande service, et convertir le devis en commande."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 91928287d24c2b6199ea243bdc00e48e136adcfd
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-service-quotes"></a><span data-ttu-id="2e50c-104">Pour créer des devis service</span><span class="sxs-lookup"><span data-stu-id="2e50c-104">Create Service Quotes</span></span>
<span data-ttu-id="2e50c-105">Vous pouvez considérer les devis service comme la base des commandes service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-105">You can think of service quotes as the basis for service orders.</span></span> <span data-ttu-id="2e50c-106">En réalité, ils sont quasiment identiques.</span><span class="sxs-lookup"><span data-stu-id="2e50c-106">In fact, they are almost identical.</span></span> <span data-ttu-id="2e50c-107">Tous deux contiennent des informations, telles que l'identité du client, le type de commande, l'article nécessitant une maintenance, les informations de facturation et d'expédition et les informations sur la tâche de service réelle.</span><span class="sxs-lookup"><span data-stu-id="2e50c-107">They both contain information such as who the customer is, the type of order, the item that needs service, billing and shipping information, and information about the actual service work.</span></span>
 
<span data-ttu-id="2e50c-108">Vous pouvez utiliser un devis service comme brouillon d'une commande service, et convertir le devis en commande.</span><span class="sxs-lookup"><span data-stu-id="2e50c-108">You can use a service quote as a preliminary draft for a service order, and then convert the quote to a service order.</span></span>  
  
## <a name="to-create-a-service-quote"></a><span data-ttu-id="2e50c-109">Pour créer un devis service</span><span class="sxs-lookup"><span data-stu-id="2e50c-109">To create a service quote</span></span>  
1. <span data-ttu-id="2e50c-110">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Devis de service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="2e50c-110">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Quotes**, and then choose the related link.</span></span>  
2. <span data-ttu-id="2e50c-111">Créez un devis service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-111">Create a new service quote.</span></span>  
3. <span data-ttu-id="2e50c-112">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="2e50c-112">In the **No.**</span></span> <span data-ttu-id="2e50c-113">saisissez le numéro du devis service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-113">field, enter a number for the service quote.</span></span> <span data-ttu-id="2e50c-114">Si vous avez configuré une souche de numéros pour les devis service dans la fenêtre **Paramètres Gestion des services,** vous pouvez appuyer sur Entrée pour renseigner le numéro devis service suivant.</span><span class="sxs-lookup"><span data-stu-id="2e50c-114">Alternatively, if you have set up a number series for service quotes in the **Service Mgt. Setup** window, you can press Enter to select the next available service quote number.</span></span>  
4. <span data-ttu-id="2e50c-115">Dans le champ **N° client**,</span><span class="sxs-lookup"><span data-stu-id="2e50c-115">In the **Customer No.**</span></span>  <span data-ttu-id="2e50c-116">sélectionnez le client approprié dans la liste.</span><span class="sxs-lookup"><span data-stu-id="2e50c-116">field, select the relevant customer from the list.</span></span>  

  > [!Note]  
  >  <span data-ttu-id="2e50c-117">Les champs de client sont automatiquement renseignés avec les informations de la fiche **Client**.</span><span class="sxs-lookup"><span data-stu-id="2e50c-117">The customer fields are filled in automatically with information from the **Customer** card.</span></span> <span data-ttu-id="2e50c-118">Si une fiche **Client** n'existe pas pour le client et que vous avez configuré un modèle client, vous pouvez créer le client à partir du devis service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-118">If a **Customer** card does not exist for the customer, and you have set up a customer template, you can create the customer from the service quote.</span></span> <span data-ttu-id="2e50c-119">Renseignez les champs appropriés, puis choisissez l'action **Créer client**.</span><span class="sxs-lookup"><span data-stu-id="2e50c-119">Fill in the relevant fields, and then choose the **Create Customer** action.</span></span>  
  
5. <span data-ttu-id="2e50c-120">Selon les paramètres du raccourci **Champs obligatoires** de la fenêtre **Config. gestion des services**, vous pouvez être amené à renseigner le champ **Type commande service** et le champ **Code représentant**.</span><span class="sxs-lookup"><span data-stu-id="2e50c-120">Depending on the settings on the **Mandatory Fields** FastTab in the **Service Mgt. Setup** window, you may need to fill in the **Service Order Type** field and the **Salesperson Code** field.</span></span>  
6. <span data-ttu-id="2e50c-121">Renseignez les lignes article de service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-121">Fill in the service item lines.</span></span>  
7. <span data-ttu-id="2e50c-122">Enregistrez les coûts estimés dans les lignes service.</span><span class="sxs-lookup"><span data-stu-id="2e50c-122">Register estimated costs on the service lines.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e50c-123">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="2e50c-123">See Also</span></span>  
[<span data-ttu-id="2e50c-124">Créer commande service</span><span class="sxs-lookup"><span data-stu-id="2e50c-124">Create Service Orders</span></span>](service-how-to-create-service-orders.md)  
[<span data-ttu-id="2e50c-125">Travailler sur des tâches service</span><span class="sxs-lookup"><span data-stu-id="2e50c-125">Work on Service tasks</span></span>](service-how-to-work-on-service-tasks.md)  

 