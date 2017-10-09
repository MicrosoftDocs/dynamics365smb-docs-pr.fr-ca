---
title: Configurer des contrats de service | Microsoft Docs
description: "Découvrez comment configurer des contrats de service."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: service, cost, service order
ms.date: 08/22/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 3eea1854139de9bdfd5dc992159dbc060c79509d
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---

# <a name="how-to-set-up-service-contracts"></a><span data-ttu-id="f4b1f-103">Procédure : configurer des contrats de service</span><span class="sxs-lookup"><span data-stu-id="f4b1f-103">How to: Set Up Service Contracts</span></span>
<span data-ttu-id="f4b1f-104">Avant de pouvoir utiliser les contrats, vous devez définir les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="f4b1f-104">Before you can work with contracts, you must set up the following:</span></span> 

* <span data-ttu-id="f4b1f-105">**Groupes contrats de service** : regroupent les contrats de service liés, quelle que soit la nature de cette relation.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-105">**Service contract groups**, which gather service contracts that are related in some way.</span></span>
* <span data-ttu-id="f4b1f-106">**Groupes comptes contrat de service** : permettent de regrouper les comptes contrat de service pour les factures service créées pour les contrats de service.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-106">**Service contract account groups**, which are used to group the service contract accounts together for service invoices created for service contracts.</span></span> <span data-ttu-id="f4b1f-107">Vous affectez ces groupes aux contrats de service.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-107">You assign these groups to service contracts.</span></span>  
* <span data-ttu-id="f4b1f-108">**Modèles contrat** : définissent les présentations des contrats incluant les détails de contrat de service les plus couramment utilisés.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-108">**Contract templates** that define contract layouts of contracts that include the most commonly used service contract details.</span></span> <span data-ttu-id="f4b1f-109">Vous pouvez créer des devis contrat de service à l'aide de modèles.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-109">When you create service contract quotes, you can create them by using templates.</span></span> <span data-ttu-id="f4b1f-110">Lorsque vous créez un devis contrat, les champs contiennent automatiquement la valeur des champs du modèle.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-110">When you create a contract quote, the fields automatically contain the contents of the template fields.</span></span>
* <span data-ttu-id="f4b1f-111">**Modèles client** : permettent de créer des devis pour les contacts ou les clients potentiels qui ne sont pas enregistrés comme clients dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="f4b1f-111">**Customer templates** that let you create quotes for contacts or potential customers who are not registered as customers in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span>  

## <a name="to-set-up-a-service-contract-group"></a><span data-ttu-id="f4b1f-112">Pour configurer un groupe de contrats de service</span><span class="sxs-lookup"><span data-stu-id="f4b1f-112">To set up a service contract group</span></span>  
1. <span data-ttu-id="f4b1f-113">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes contrats de service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-113">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contract Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f4b1f-114">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-114">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. <span data-ttu-id="f4b1f-115">Activez la case à cocher **Escompte sur cdes contrat seulement** si vous souhaitez que les escomptes de paiement contrat ou service ne soient valides que pour les commandes contrat de service, telles qu'un entretien.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-115">Choose the **Disc. on Contr. Orders Only** check box if you want contract or service discounts to be valid only for contract service orders, such as maintenance.</span></span>  

## <a name="to-set-up-a-service-contract-account-group"></a><span data-ttu-id="f4b1f-116">Pour configurer un groupe comptes contrats de service</span><span class="sxs-lookup"><span data-stu-id="f4b1f-116">To set up a service contract account group</span></span>  
1. <span data-ttu-id="f4b1f-117">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Groupes comptes contrat serv.**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Serv. Contract Account Groups**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f4b1f-118">Créez un groupe comptes contrat de service.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-118">Create a new service contract account group.</span></span>   
3. <span data-ttu-id="f4b1f-119">Renseignez les champs **Code** et **Désignation**.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-119">Fill in the **Code** and **Description** fields.</span></span> <span data-ttu-id="f4b1f-120">Ces champs décrivent le groupe compte service.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-120">These fields describe the service account group.</span></span>  
4. <span data-ttu-id="f4b1f-121">Renseignez le champ **Compte contrat non prépayé**, puis sélectionnez le numéro de compte du grand livre du compte non prépayé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-121">Fill in the **Non-Prepaid Contract Acc.** field, choose general ledger account number for the non-prepaid account.</span></span>  
5. <span data-ttu-id="f4b1f-122">Dans le champ **Compte contrat prépayé**, sélectionnez le numéro de compte du grand livre du compte prépayé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-122">In the **Prepaid Contract Acc.** field, choose the general ledger account number for the prepaid account.</span></span>  

## <a name="to-set-up-a-contract-template"></a><span data-ttu-id="f4b1f-123">Pour configurer un modèle de contrat</span><span class="sxs-lookup"><span data-stu-id="f4b1f-123">To set up a contract template</span></span>  
1. <span data-ttu-id="f4b1f-124">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles contrat de service**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-124">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Service Contract Templates**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f4b1f-125">Créez un modèle contrat de service.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-125">Create a new service contract template.</span></span>  
3. <span data-ttu-id="f4b1f-126">Dans le champ **N°**,</span><span class="sxs-lookup"><span data-stu-id="f4b1f-126">In the **No.**</span></span> <span data-ttu-id="f4b1f-127">saisissez le numéro du modèle de contrat.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-127">field, enter a number for the contract template.</span></span>  
  
     <span data-ttu-id="f4b1f-128">Si vous avez configuré une souche de numéros pour les modèles contrat dans la fenêtre **Paramètres Gestion des services**, vous pouvez appuyer sur la touche Entrée pour que le programme saisisse le numéro modèle contrat suivant.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-128">Alternatively, if you have set up number series for contract templates in the **Service Mgt. Setup** window, you can press the Enter key to enter the next available contract template number.</span></span> <span data-ttu-id="f4b1f-129">Renseignez les autres champs, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-129">Fill in the other fields if appropriate.</span></span>  
  
4. <span data-ttu-id="f4b1f-130">Dans le raccourci **Facture**, renseignez les champs **Code gpe cptes contrat serv.**, **Période de facturation**, etc.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-130">On the **Invoice** FastTab, fill in the **Serv. Contract Acc. Group Code** field, the **Invoice Period**, and so on.</span></span> <span data-ttu-id="f4b1f-131">Renseignez les autres champs, si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-131">Fill in the other fields if appropriate.</span></span>  
5. <span data-ttu-id="f4b1f-132">Sélectionnez l'action **Escomptes service** pour ajouter des escomptes contrat.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-132">Choose the **Service Discounts** action to add contract discounts.</span></span>  

## <a name="to-set-up-a-customer-template"></a><span data-ttu-id="f4b1f-133">Pour configurer un modèle client</span><span class="sxs-lookup"><span data-stu-id="f4b1f-133">To set up a customer template</span></span>  
1. <span data-ttu-id="f4b1f-134">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Modèles de clients**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-134">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Customer Templates**, and then choose the related link.</span></span>  
2. <span data-ttu-id="f4b1f-135">Créez une fiche modèle client.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-135">Create a new customer template card.</span></span>  
3. <span data-ttu-id="f4b1f-136">Sur le raccourci **Général**, entrez un code et une description pour le modèle client respectivement dans les champs **Code** et **Description**.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-136">On the **General** FastTab, enter a code and a description for the customer template in the **Code** and **Description** fields respectively.</span></span> 
4. <span data-ttu-id="f4b1f-137">Pour définir les critères de recherche, renseignez les autres champs tels que **Code pays/région**, **Code secteur** et **Code langue**.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-137">To define search criteria, fill in the other fields, such as **Country/Region Code**, **Territory Code**, and **Language Code**.</span></span>  
5. <span data-ttu-id="f4b1f-138">Renseignez les champs **Groupe de report de marché** et **Groupe de report de client**.</span><span class="sxs-lookup"><span data-stu-id="f4b1f-138">Fill in the **Gen. Bus. Posting Group** and **Customer Posting Group** fields.</span></span>  

## <a name="see-also"></a><span data-ttu-id="f4b1f-139">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="f4b1f-139">See Also</span></span>
[<span data-ttu-id="f4b1f-140">Paramétrage de la gestion des services</span><span class="sxs-lookup"><span data-stu-id="f4b1f-140">Setting Up Service Management</span></span>](service-setup-service.md)
