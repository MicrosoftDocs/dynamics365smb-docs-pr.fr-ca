---
title: 'Procédure : inverser un report de sortie | Microsoft Docs'
description: Il arrive qu'un report de production doive être inversé. C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 5901ad209149c113497d676a5c86379fc8424a0e
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5392759"
---
# <a name="reverse-output-posting"></a><span data-ttu-id="76711-104">Inverser un report de production</span><span class="sxs-lookup"><span data-stu-id="76711-104">Reverse Output Posting</span></span>
<span data-ttu-id="76711-105">Il arrive qu'un report de production doive être inversé.</span><span class="sxs-lookup"><span data-stu-id="76711-105">There are times when output posting must be reversed.</span></span> <span data-ttu-id="76711-106">C'est le cas, par exemple, si une erreur de saisie de données a été commise et qu'une quantité de production incorrecte a été reportée sur un bon de production.</span><span class="sxs-lookup"><span data-stu-id="76711-106">An example of this would be if a data entry error occurred and an incorrect amount of output is posted to a production order.</span></span>  

## <a name="to-reverse-an-output-posting"></a><span data-ttu-id="76711-107">Pour inverser un report de production</span><span class="sxs-lookup"><span data-stu-id="76711-107">To reverse an output posting</span></span>  
1.  <span data-ttu-id="76711-108">Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Journal de sortie**, puis sélectionnez le lien associé.</span><span class="sxs-lookup"><span data-stu-id="76711-108">Choose the ![Lightbulb that opens the Tell Me feature](media/ui-search/search_small.png "Tell me what you want to do") icon, enter **Output Journal**, and then choose the related link.</span></span> <span data-ttu-id="76711-109">Sélectionnez votre lot.</span><span class="sxs-lookup"><span data-stu-id="76711-109">Select your batch.</span></span>  
2. <span data-ttu-id="76711-110">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="76711-110">Fill in the fields as necessary.</span></span> <span data-ttu-id="76711-111">Pour plus d'informations, voir [Exécuter en lot la production et les temps d'exécution](production-how-to-post-output-quantity.md).</span><span class="sxs-lookup"><span data-stu-id="76711-111">For more information, see [Batch Post Output and Run Times](production-how-to-post-output-quantity.md).</span></span>
3.  <span data-ttu-id="76711-112">Dans le champ **Écriture de référence**, sélectionnez l'écriture article associée.</span><span class="sxs-lookup"><span data-stu-id="76711-112">In the **Applies-To Entry** field, select the associated item ledger entry.</span></span> <span data-ttu-id="76711-113">Cette opération inverse les écritures capacité et du grand livre d'articles.</span><span class="sxs-lookup"><span data-stu-id="76711-113">This reverses the capacity and item ledger entries.</span></span>  
4. <span data-ttu-id="76711-114">Reportez la contrepassation en reportant le journal.</span><span class="sxs-lookup"><span data-stu-id="76711-114">Post the reversal by posting the journal.</span></span>  

<span data-ttu-id="76711-115">Les écritures journal production sont reportées dans le grand livre article comme un ajustement positif.</span><span class="sxs-lookup"><span data-stu-id="76711-115">The output journal entries are posted to the item ledger as a positive adjustment.</span></span>  

## <a name="see-also"></a><span data-ttu-id="76711-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="76711-116">See Also</span></span>  
 <span data-ttu-id="76711-117">[Production](production-manage-manufacturing.md)  </span><span class="sxs-lookup"><span data-stu-id="76711-117">[Manufacturing](production-manage-manufacturing.md)  </span></span>  
 [<span data-ttu-id="76711-118">Paramétrage de la production</span><span class="sxs-lookup"><span data-stu-id="76711-118">Setting Up Manufacturing</span></span>](production-configure-production-processes.md)  
 <span data-ttu-id="76711-119">[Planification](production-planning.md)    </span><span class="sxs-lookup"><span data-stu-id="76711-119">[Planning](production-planning.md)    </span></span>  
 [<span data-ttu-id="76711-120">Inventaire</span><span class="sxs-lookup"><span data-stu-id="76711-120">Inventory</span></span>](inventory-manage-inventory.md)  
 [<span data-ttu-id="76711-121">Procédure d'achat</span><span class="sxs-lookup"><span data-stu-id="76711-121">Purchasing</span></span>](purchasing-manage-purchasing.md)  
 <span data-ttu-id="76711-122">[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="76711-122">[Working with [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)</span></span>  


[!INCLUDE[footer-include](includes/footer-banner.md)]