---
title: 'Procédure : transférer les écritures GL vers les écritures de coûts | Microsoft Docs'
description: Vous pouvez transférer les écritures vers les écritures de coûts.
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
redirect_url: finance-transfer-and-post-cost-entries
ms.openlocfilehash: a33fb434cc239de951d18783911c879587a3ace0
ms.sourcegitcommit: addfb47612cc2e4e98dfd7e338b6f41cde405d5c
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/16/2019
ms.locfileid: "939044"
---
# <a name="transfer-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="8d4cb-103">Transférer les écritures grand livre vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="8d4cb-103">Transfer General Ledger Entries to Cost Entries</span></span>
<span data-ttu-id="8d4cb-104">Vous pouvez transférer les écritures vers les écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-104">You can transfer general ledger entries to cost entries.</span></span>  

<span data-ttu-id="8d4cb-105">Avant d'exécuter le transfert des écritures vers des écritures de coûts, vous devez vous y préparer pour éviter tout report manuel de correction.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-105">Before you run the process for transferring general ledger entries to cost entries, you must prepare the transfer to avoid manual correction posting.</span></span>  

## <a name="to-prepare-the-transfer"></a><span data-ttu-id="8d4cb-106">Pour préparer le transfert</span><span class="sxs-lookup"><span data-stu-id="8d4cb-106">To prepare the transfer</span></span>  

1.  <span data-ttu-id="8d4cb-107">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration de la comptabilité analytique**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-107">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Cost Accounting Setup**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="8d4cb-108">Sur la page **Configuration comptabilité analytique**, vérifiez que le champ **Date début pour transfert GL** est défini sur la valeur appropriée.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-108">On the **Cost Accounting Setup** page, verify that the **Starting Date for G/L Transfer** field is set to the correct value.</span></span>  
3.  <span data-ttu-id="8d4cb-109">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable des types de coûts**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-109">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Cost Types**, and then choose the related link.</span></span>  
4.  <span data-ttu-id="8d4cb-110">Sur la page **Fiche type de coût**, vérifiez que le champ **Plage compte du grand livre** est lié correctement de sorte que chaque type de coût récupère les écritures du grand livre.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-110">On the **Cost Type Card** page, verify that the **G/L Account Range** field is linked correctly for each cost type to take entries from the general ledger.</span></span>  
5.  <span data-ttu-id="8d4cb-111">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Plan comptable**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-111">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Chart of Accounts**, and then choose the related link.</span></span>  
6.  <span data-ttu-id="8d4cb-112">Pour chaque compte GL approprié, sur la page **Fiche compte du grand livre**, vérifiez que le champ **N° type coût**</span><span class="sxs-lookup"><span data-stu-id="8d4cb-112">For each relevant general ledger account, on the **G/L Account Card** page, verify that the **Cost Type No.**</span></span> <span data-ttu-id="8d4cb-113">est lié correctement à un type de coût.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-113">field is linked correctly to a cost type.</span></span> <span data-ttu-id="8d4cb-114">Pour plus d'informations, voir [Configuration du contrôle de gestion](finance-set-up-cost-accounting.md).</span><span class="sxs-lookup"><span data-stu-id="8d4cb-114">For more information, see [Setting Up Cost Accounting](finance-set-up-cost-accounting.md).</span></span>  
7.  <span data-ttu-id="8d4cb-115">Vérifiez que toutes les écritures GL comprennent des valeurs de dimension correspondant à un centre de coûts et à un objet de coûts.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-115">Verify that all relevant general ledger entries have dimension values that correspond to a cost center and a cost object.</span></span>  

## <a name="to-transfer-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="8d4cb-116">Pour transférer les écritures vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="8d4cb-116">To transfer general ledger entries to cost entries</span></span>  
1.  <span data-ttu-id="8d4cb-117">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Transférer les écritures comptables vers CA**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-117">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Transfer GL Entries to CA**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="8d4cb-118">Cliquez sur le bouton **Oui** pour démarrer le transfert.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-118">Choose the **Yes** button to start the transfer.</span></span> <span data-ttu-id="8d4cb-119">Le processus transfère toutes les écritures qui n'ont pas encore été transférées.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-119">The process transfers all general ledger entries that have not already been transferred.</span></span>  

    <span data-ttu-id="8d4cb-120">Lors du transfert, le processus crée des connexions dans les écritures des tables **Écriture de coûts** et **Registre de coûts**.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-120">During the transfer, the process creates connections in the entries in the **Cost Entry** table and the **Cost Register** table.</span></span> <span data-ttu-id="8d4cb-121">Cela permet d'identifier l'origine des écritures de coûts.</span><span class="sxs-lookup"><span data-stu-id="8d4cb-121">This makes it possible to trace the source of cost entries.</span></span>  

## <a name="see-also"></a><span data-ttu-id="8d4cb-122">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8d4cb-122">See Also</span></span>  
<span data-ttu-id="8d4cb-123">[Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="8d4cb-123">[Transferring and Posting Cost Entries](finance-transfer-and-post-cost-entries.md) </span></span>  
[<span data-ttu-id="8d4cb-124">Paramétrage du contrôle de gestion</span><span class="sxs-lookup"><span data-stu-id="8d4cb-124">Setting Up Cost Accounting</span></span>](finance-set-up-cost-accounting.md)   
