---
title: En savoir plus sur le grand livre et le COA| Microsoft Docs
description: "Décrit le grand livre, le plan comptable, et les catégories de compte."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 06/02/2017
ms.author: edupont
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 63d414f4c81a9e20b4bb81b632edd9c91fb34a87
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="understanding-the-general-ledger-and-the-coa"></a><span data-ttu-id="b021f-103">Familiarisation avec le grand livre et les COA</span><span class="sxs-lookup"><span data-stu-id="b021f-103">Understanding the General Ledger and the COA</span></span>
<span data-ttu-id="b021f-104">Le grand livre stocke vos données financières, et le plan comptable affiche les comptes sur lesquels toutes les écritures sont reportées.</span><span class="sxs-lookup"><span data-stu-id="b021f-104">The general ledger stores your financial data, and the chart of accounts shows the accounts that all general ledger entries are posted to.</span></span> [!INCLUDE[d365fin](includes/d365fin_md.md)]<span data-ttu-id="b021f-105"> inclut un plan comptable standard prêt à prendre en charge votre société.</span><span class="sxs-lookup"><span data-stu-id="b021f-105"> includes a standard chart of accounts that is ready to support your business.</span></span>

## <a name="general-ledger-setup-and-general-posting-setup"></a><span data-ttu-id="b021f-106">Configuration du grand livre et configuration du report général</span><span class="sxs-lookup"><span data-stu-id="b021f-106">General Ledger Setup and General Posting Setup</span></span>
<span data-ttu-id="b021f-107">La configuration du grand livre est la composante principale des processus financiers car elle définit comment vous reportez les données.</span><span class="sxs-lookup"><span data-stu-id="b021f-107">The setup of the general ledger is at the core of financial processes because it defines how you post data.</span></span>  

<span data-ttu-id="b021f-108">Dans la fenêtre **Paramètres comptabilité**, vous spécifiez comment gérer certains problèmes comptables dans votre société, par exemple :</span><span class="sxs-lookup"><span data-stu-id="b021f-108">In the **General Ledger Setup** window, you specify how to handle certain accounting issues in your company, such as:</span></span>  

* <span data-ttu-id="b021f-109">Les détails arrondissement facture</span><span class="sxs-lookup"><span data-stu-id="b021f-109">Invoice rounding details</span></span>  
* <span data-ttu-id="b021f-110">Les formats d'adresse</span><span class="sxs-lookup"><span data-stu-id="b021f-110">Address formats</span></span>  
* <span data-ttu-id="b021f-111">Rapports financiers</span><span class="sxs-lookup"><span data-stu-id="b021f-111">Financial reporting</span></span>  

<span data-ttu-id="b021f-112">De même, dans la fenêtre **Paramètres comptabilisation**, vous spécifiez comment vous souhaitez configurer les combinaisons de groupes généraux comptabilisation marché et de groupes généraux comptabilisation produit.</span><span class="sxs-lookup"><span data-stu-id="b021f-112">Similarly, in the **General Posting Setup** window, you specify how you want to set up combinations of general business and general product posting groups.</span></span> <span data-ttu-id="b021f-113">Les groupes comptabilisation mappent des entités telles que les clients, les fournisseurs, les éléments, les ressources et les documents vente et achat dans des comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="b021f-113">Posting groups map entities like customers, vendors, items, resources, and sales and purchase documents to general ledger accounts.</span></span> <span data-ttu-id="b021f-114">Saisissez une ligne pour chaque combinaison de groupes de report marché et de groupes de report produit.</span><span class="sxs-lookup"><span data-stu-id="b021f-114">You fill in a line for each combination of business posting group and product posting group.</span></span> <span data-ttu-id="b021f-115">Pour plus d'informations, voir [Paramètres du groupe comptabilisation](finance-posting-groups.md)</span><span class="sxs-lookup"><span data-stu-id="b021f-115">For more information, see [Posting Group Setups](finance-posting-groups.md)</span></span>  

## <a name="the-chart-of-accounts"></a><span data-ttu-id="b021f-116">Le plan comptable</span><span class="sxs-lookup"><span data-stu-id="b021f-116">The Chart of Accounts</span></span>
<span data-ttu-id="b021f-117">Le plan comptable affiche tous les comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="b021f-117">The chart of accounts shows all general ledger accounts.</span></span> <span data-ttu-id="b021f-118">Vous pouvez effectuer les opérations suivantes à partir du plan comptable :</span><span class="sxs-lookup"><span data-stu-id="b021f-118">From the chart of accounts, you can do things like:</span></span>  

* <span data-ttu-id="b021f-119">Afficher les rapports qui affichent les écritures et les soldes.</span><span class="sxs-lookup"><span data-stu-id="b021f-119">View reports that show general ledger entries and balances.</span></span>  
* <span data-ttu-id="b021f-120">Fermez votre état des résultats.</span><span class="sxs-lookup"><span data-stu-id="b021f-120">Close your income statement.</span></span>  
* <span data-ttu-id="b021f-121">Ouvrir la fiche compte du grand livre pour ajouter ou modifier des paramètres.</span><span class="sxs-lookup"><span data-stu-id="b021f-121">Open the G/L account card to add or change settings.</span></span>  
* <span data-ttu-id="b021f-122">Consulter la liste des groupes de report qui effectuent les reports vers ce compte.</span><span class="sxs-lookup"><span data-stu-id="b021f-122">See a list of posting groups that post to that account.</span></span>
* <span data-ttu-id="b021f-123">Afficher les soldes débit et crédit d'un seul compte</span><span class="sxs-lookup"><span data-stu-id="b021f-123">View separate debit and credit balances for a single account</span></span>  

<span data-ttu-id="b021f-124">Vous pouvez ajouter, modifier ou supprimer des comptes généraux.</span><span class="sxs-lookup"><span data-stu-id="b021f-124">You can add, change, or delete general ledger accounts.</span></span> <span data-ttu-id="b021f-125">Toutefois, pour éviter les différences, vous ne pouvez pas supprimer un compte du grand livre si ses données sont utilisées dans le plan comptable.</span><span class="sxs-lookup"><span data-stu-id="b021f-125">However, to prevent discrepancies, you can't delete a general ledger account if it's data is used in the chart of accounts.</span></span>  

## <a name="account-categories"></a><span data-ttu-id="b021f-126">Catégories de compte</span><span class="sxs-lookup"><span data-stu-id="b021f-126">Account Categories</span></span>
<span data-ttu-id="b021f-127">Vous pouvez personnaliser la structure de vos états financiers en mappant les comptes généraux aux catégories de comptes.</span><span class="sxs-lookup"><span data-stu-id="b021f-127">You can personalize the structure of your financial statements by mapping general ledger accounts to account categories.</span></span>  

<span data-ttu-id="b021f-128">La fenêtre **Catégories de compte général** affiche vos catégories et sous-catégories et les comptes généraux que leurs sont affectés.</span><span class="sxs-lookup"><span data-stu-id="b021f-128">The **G/L Account Categories** window shows your categories and subcategories, and the G/L accounts that are assigned to them.</span></span> <span data-ttu-id="b021f-129">Vous pouvez créer des sous-catégories et affecter ces catégories à des comptes existants.</span><span class="sxs-lookup"><span data-stu-id="b021f-129">You can create new subcategories and assign those categories to existing accounts.</span></span>  

<span data-ttu-id="b021f-130">Vous créez un groupe des catégories en effectuant une indentation d'autres sous-catégories sous une ligne de la fenêtre **Catégories de compte général**.</span><span class="sxs-lookup"><span data-stu-id="b021f-130">You create a category group by indenting other subcategories under a line in the **G/L Account Categories** window.</span></span> <span data-ttu-id="b021f-131">Cela vous facilite l'obtention d'une vue d'ensemble, car chaque groupement affiche un solde total.</span><span class="sxs-lookup"><span data-stu-id="b021f-131">This makes it easy for you to get an overview, because each grouping shows a total balance.</span></span> <span data-ttu-id="b021f-132">Par exemple, vous pouvez créer des sous-catégories pour différents types d'actifs puis créer des groupes des catégories pour différencier les immobilisations des actifs à court terme, par exemple.</span><span class="sxs-lookup"><span data-stu-id="b021f-132">For example, you can create subcategories for different types of assets, and then create category groups for fixed assets versus current assets.</span></span>  

<span data-ttu-id="b021f-133">Vous pouvez spécifier si les comptes de chaque sous-catégorie doivent être inclus dans des types spécifiques d'états.</span><span class="sxs-lookup"><span data-stu-id="b021f-133">You can specify whether the accounts in each subcategory must be included in specific types of reports.</span></span> <span data-ttu-id="b021f-134">Les catégories de compte vous aident à définir la présentation de vos états financiers.</span><span class="sxs-lookup"><span data-stu-id="b021f-134">The account categories help define the layout of your financial statements.</span></span>  

<span data-ttu-id="b021f-135">Par exemple, le solde relevé par défaut solde est doté d'une sous-catégorie pour la trésorerie dans Actifs à court terme.</span><span class="sxs-lookup"><span data-stu-id="b021f-135">For example, the default balance statement has a subcategory for Cash under Current Assets.</span></span> <span data-ttu-id="b021f-136">Si vous souhaitez que le solde relevé tienne compte du fonds de caisse et du compte chèque, vous pouvez :</span><span class="sxs-lookup"><span data-stu-id="b021f-136">If you want the balance statement consider petty cash and checking, you can:</span></span>  

1. <span data-ttu-id="b021f-137">Ajouter deux nouvelles sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="b021f-137">Add two new subcategories.</span></span> <span data-ttu-id="b021f-138">Une pour le fonds de caisse, et l'autre pour le compte chèque</span><span class="sxs-lookup"><span data-stu-id="b021f-138">One for petty cash, and one for your checking account.</span></span>  
2. <span data-ttu-id="b021f-139">Spécifier la définition d'état supplémentaire **Comptes de trésorerie** pour ces sous-catégories.</span><span class="sxs-lookup"><span data-stu-id="b021f-139">Specify the additional report definition **Cash Accounts** for these subcategories.</span></span>  
3. <span data-ttu-id="b021f-140">Effectuer une indentation sous la sous-catégorie **Trésorerie**.</span><span class="sxs-lookup"><span data-stu-id="b021f-140">Indent them under the **Cash** subcategory.</span></span>  

<span data-ttu-id="b021f-141">À la prochaine génération des tableaux d'analyse, votre relevé solde suivant affichera un solde total pour la trésorerie et deux lignes avec les soldes pour le fonds de caisse et le compte chèque.</span><span class="sxs-lookup"><span data-stu-id="b021f-141">The next time you generate account schedules your balance statement will show a total balance for cash and two lines with balances for petty cash and the checking account.</span></span>  

## <a name="see-also"></a><span data-ttu-id="b021f-142">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b021f-142">See Also</span></span>
[<span data-ttu-id="b021f-143">Finances</span><span class="sxs-lookup"><span data-stu-id="b021f-143">Finance</span></span>](finance.md)  
[<span data-ttu-id="b021f-144">Configuration ou modification du plan comptable</span><span class="sxs-lookup"><span data-stu-id="b021f-144">Setting Up or Changing the Chart of Accounts</span></span>](finance-setup-chart-accounts.md)  
[<span data-ttu-id="b021f-145">Veille économique</span><span class="sxs-lookup"><span data-stu-id="b021f-145">Business Intelligence</span></span>](bi.md)  
