---
title: "Procédure : transférer les écritures GL vers les écritures de coûts | Microsoft Docs"
description: "Vous pouvez transférer les écritures vers les écritures de coûts."
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
ms.openlocfilehash: cd52387ec1396164f6da1b87a2a97227901df592
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="transfer-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="29c7d-103">Transférer les écritures grand livre vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="29c7d-103">Transfer General Ledger Entries to Cost Entries</span></span>
<span data-ttu-id="29c7d-104">Vous pouvez transférer les écritures vers les écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="29c7d-104">You can transfer general ledger entries to cost entries.</span></span>  

<span data-ttu-id="29c7d-105">Avant d'exécuter le transfert des écritures vers des écritures de coûts, vous devez vous y préparer pour éviter tout report manuel de correction.</span><span class="sxs-lookup"><span data-stu-id="29c7d-105">Before you run the process for transferring general ledger entries to cost entries, you must prepare the transfer to avoid manual correction posting.</span></span>  

## <a name="to-prepare-the-transfer"></a><span data-ttu-id="29c7d-106">Pour préparer le transfert</span><span class="sxs-lookup"><span data-stu-id="29c7d-106">To prepare the transfer</span></span>  

1.  <span data-ttu-id="29c7d-107">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Configuration de la comptabilité analytique**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="29c7d-107">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Cost Accounting Setup**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="29c7d-108">Dans la fenêtre **Configuration de la comptabilité analytique**, vérifiez que le champ **Date début pour transfert grand livre** est défini sur la valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="29c7d-108">In the **Cost Accounting Setup** window, verify that the **Starting Date for G/L Transfer** field is set to the correct value.</span></span>  
3.  <span data-ttu-id="29c7d-109">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Plan comptable des types de coûts**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="29c7d-109">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Cost Types**, and then choose the related link.</span></span>  
4.  <span data-ttu-id="29c7d-110">Dans la fenêtre **Fiche type de coût**, vérifiez que le champ **Plage compte du grand livre** est lié correctement de sorte que chaque type de coût récupère les écritures du grand livre.</span><span class="sxs-lookup"><span data-stu-id="29c7d-110">In the **Cost Type Card** window, verify that the **G/L Account Range** field is linked correctly for each cost type to take entries from the general ledger.</span></span>  
5.  <span data-ttu-id="29c7d-111">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "icône Page ou état pour la recherche"), entrez **Plan comptable**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="29c7d-111">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>  
6.  <span data-ttu-id="29c7d-112">Pour chaque compte GL approprié, dans la fenêtre **Fiche compte GL**, vérifiez que le champ **N° type coût**</span><span class="sxs-lookup"><span data-stu-id="29c7d-112">For each relevant general ledger account, in the **G/L Account Card** window, verify that the **Cost Type No.**</span></span> <span data-ttu-id="29c7d-113">est lié correctement à un type de coût.</span><span class="sxs-lookup"><span data-stu-id="29c7d-113">field is linked correctly to a cost type.</span></span> <span data-ttu-id="29c7d-114">Pour plus d'informations, voir [Définition de la relation entre les types de coûts et les comptes généraux](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="29c7d-114">For more information, see [Defining the Relationship Between Cost Types and General Ledger Accounts](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md).</span></span>  
7.  <span data-ttu-id="29c7d-115">Vérifiez que toutes les écritures GL comprennent des valeurs de dimension correspondant à un centre de coûts et à un objet de coûts.</span><span class="sxs-lookup"><span data-stu-id="29c7d-115">Verify that all relevant general ledger entries have dimension values that correspond to a cost center and a cost object.</span></span>  

## <a name="to-transfer-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="29c7d-116">Pour transférer les écritures vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="29c7d-116">To transfer general ledger entries to cost entries</span></span>  
1.  <span data-ttu-id="29c7d-117">Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Transférer les écritures vers CA**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="29c7d-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Transfer GL Entries to CA**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="29c7d-118">Cliquez sur le bouton **Oui** pour démarrer le transfert.</span><span class="sxs-lookup"><span data-stu-id="29c7d-118">Choose the **Yes** button to start the transfer.</span></span> <span data-ttu-id="29c7d-119">Le processus transfère toutes les écritures qui n'ont pas encore été transférées.</span><span class="sxs-lookup"><span data-stu-id="29c7d-119">The process transfers all general ledger entries that have not already been transferred.</span></span>  

    <span data-ttu-id="29c7d-120">Lors du transfert, le processus crée des connexions dans les écritures des tables **Écriture de coûts** et **Registre de coûts**.</span><span class="sxs-lookup"><span data-stu-id="29c7d-120">During the transfer, the process creates connections in the entries in the **Cost Entry** table and the **Cost Register** table.</span></span> <span data-ttu-id="29c7d-121">Cela permet d'identifier l'origine des écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="29c7d-121">This makes it possible to trace the source of cost entries.</span></span>  

## <a name="see-also"></a><span data-ttu-id="29c7d-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="29c7d-122">See Also</span></span>  
 <span data-ttu-id="29c7d-123">[Critères de transfert des écritures comptables vers les écritures de coûts](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="29c7d-123">[Criteria for Transferring General Ledger Entries to Cost Entries](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span></span>  
 <span data-ttu-id="29c7d-124">[Transfert automatique et écritures combinées](finance-automatic-transfer-combined-entries.md) </span><span class="sxs-lookup"><span data-stu-id="29c7d-124">[Automatic Transfer and Combined Entries](finance-automatic-transfer-combined-entries.md) </span></span>  
 <span data-ttu-id="29c7d-125">[Résultats du transfert](finance-results-of-the-transfer.md) </span><span class="sxs-lookup"><span data-stu-id="29c7d-125">[Results of the Transfer](finance-results-of-the-transfer.md) </span></span>  
 <span data-ttu-id="29c7d-126">[Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="29c7d-126">[Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md) </span></span>  
 [<span data-ttu-id="29c7d-127">Définition de la relation entre les types de coûts et les comptes généraux</span><span class="sxs-lookup"><span data-stu-id="29c7d-127">Defining the Relationship Between Cost Types and General Ledger Accounts</span></span>](finance-defining-the-relationship-between-cost-types-and-general-ledger-accounts.md)   

