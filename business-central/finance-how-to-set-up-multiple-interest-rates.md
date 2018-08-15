---
title: "Comment paramétrer plusieurs taux d'intérêt"
description: "Vous pouvez calculer les intérêts avec plusieurs taux d'intérêts pour une période donnée. Le calcul des intérêts ressemble à tous les intérêts financiers, avec une variation uniquement du taux d'intérêt pour une période donnée."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 12/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 0af01fe46f6b7df1149825c35a9fc0cc19482403
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="set-up-multiple-interest-rates"></a><span data-ttu-id="d2124-104">Paramétrer plusieurs taux d'intérêt</span><span class="sxs-lookup"><span data-stu-id="d2124-104">Set Up Multiple Interest Rates</span></span>
<span data-ttu-id="d2124-105">Plusieurs taux d'intérêt multiples sont utilisés pour différentes périodes pour les paiements retardés dans les transactions commerciales.</span><span class="sxs-lookup"><span data-stu-id="d2124-105">Multiple interest rates are used for different periods for delayed payments in trade transactions.</span></span> <span data-ttu-id="d2124-106">Par exemple, un gouvernement définit l'intérêt maximum à prélever pour un consommateur.</span><span class="sxs-lookup"><span data-stu-id="d2124-106">For example, a government specifies the maximum interest to be levied for a consumer.</span></span> <span data-ttu-id="d2124-107">Ce taux d'intérêt peut être modifié deux fois par an le 1er janvier et le 1er juillet inclus.</span><span class="sxs-lookup"><span data-stu-id="d2124-107">This interest rate can be changed twice a year on 01 January and 01 July.</span></span> <span data-ttu-id="d2124-108">Le taux d'intérêt entre les sociétés (B2B) est accepté par les parties et il n'existe aucune limite à ce groupe de clients.</span><span class="sxs-lookup"><span data-stu-id="d2124-108">The interest rate between businesses (B2B) is agreed by the parties and there is no limit to that customer group.</span></span> <span data-ttu-id="d2124-109">Le taux annoncé est généralement quatre fois supérieur aux intérêts bancaires normaux.</span><span class="sxs-lookup"><span data-stu-id="d2124-109">The announced rate is usually four percent more than the normal bank interest.</span></span>

<span data-ttu-id="d2124-110">Lorsque vous créez des modalités de frais financiers et des modalités de rappel, pour la pénalité de retard de paiement, vous pouvez spécifier plusieurs taux d'intérêt afin que les frais de pénalité soient calculés sur la base de plusieurs taux d'intérêt à différentes périodes.</span><span class="sxs-lookup"><span data-stu-id="d2124-110">When you create finance charge terms and reminder terms, for delayed payment penalty, you can specify multiple interest rates so that the penalty fee is calculated from different interest rates in different periods.</span></span> <span data-ttu-id="d2124-111">Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).</span><span class="sxs-lookup"><span data-stu-id="d2124-111">For more information, see [Collect Outstanding Balances](receivables-collect-outstanding-balances.md).</span></span>

## <a name="to-set-up-multiple-interest-rates"></a><span data-ttu-id="d2124-112">Pour paramétrer plusieurs taux d'intérêt</span><span class="sxs-lookup"><span data-stu-id="d2124-112">To set up multiple interest rates</span></span>  
1.  <span data-ttu-id="d2124-113">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Conditions intérêts de retard**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d2124-113">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Finance Charge Terms**, and then choose the related link.</span></span>  
2.  <span data-ttu-id="d2124-114">Dans la fenêtre **Modalités de frais financiers**, sélectionnez la modalité financière requise, puis sélectionnez l'action **Taux d'intérêt**.</span><span class="sxs-lookup"><span data-stu-id="d2124-114">In the **Finance Charge Terms** window, select the required finance term, and then choose the **Interest Rates** action.</span></span>  
3.  <span data-ttu-id="d2124-115">Renseignez les champs selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="d2124-115">Fill in the fields as necessary.</span></span> [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4.  <span data-ttu-id="d2124-116">Cliquez sur le bouton **OK**.</span><span class="sxs-lookup"><span data-stu-id="d2124-116">Choose the **OK** button.</span></span>  
5.  <span data-ttu-id="d2124-117">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Conditions de relance**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="d2124-117">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **Reminder Terms**, and then choose the related link.</span></span>  
6.  <span data-ttu-id="d2124-118">Dans la fenêtre **Modalités de rappel**, sélectionnez la modalité de rappel, puis sélectionnez l'action **Niveaux**.</span><span class="sxs-lookup"><span data-stu-id="d2124-118">In the **Reminder Terms** window, select the required reminder term, and then choose the **Levels** action.</span></span>  
7.  <span data-ttu-id="d2124-119">Dans la fenêtre **Niveaux rappel**, sélectionnez le champ **Calculer intérêts**.</span><span class="sxs-lookup"><span data-stu-id="d2124-119">In the **Reminder Levels** window, select the **Calculate Interest** field.</span></span>  

<span data-ttu-id="d2124-120">Lorsque vous émettez une note de frais financiers, la note affiche les frais financiers avec plusieurs taux d'intérêt pour une période spécifique.</span><span class="sxs-lookup"><span data-stu-id="d2124-120">When you issue a finance charge memo, the memo shows the finance charges with multiple interest rates for a specific time period.</span></span> <span data-ttu-id="d2124-121">La note affiche également les informations contact du client, de la compagnie émettant la note, du montant supplémentaire, et du montant total.</span><span class="sxs-lookup"><span data-stu-id="d2124-121">The memo also contains the contact details of the customer, the company issuing the memo, the additional amount, and the total amount.</span></span> <span data-ttu-id="d2124-122">L'écriture ouverture sur la facture est affichée en gras.</span><span class="sxs-lookup"><span data-stu-id="d2124-122">The opening entry on the memo is displayed in bold.</span></span> <span data-ttu-id="d2124-123">Les intérêts sont calculés avec plusieurs taux d'intérêt pour une période spécifique et sont imprimés après l'écriture ouverture de la facture.</span><span class="sxs-lookup"><span data-stu-id="d2124-123">The finance charges are calculated with multiple interest rates for a specific time period and are printed after the opening entry of the memo.</span></span>  

## <a name="see-also"></a><span data-ttu-id="d2124-124">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d2124-124">See Also</span></span>  
[<span data-ttu-id="d2124-125">Collecte des soldes restants</span><span class="sxs-lookup"><span data-stu-id="d2124-125">Collect Outstanding Balances</span></span>](receivables-collect-outstanding-balances.md)  
[<span data-ttu-id="d2124-126">Configuration de Finance</span><span class="sxs-lookup"><span data-stu-id="d2124-126">Setting Up Finance</span></span>](finance-setup-finance.md)
