---
title: Importer les transactions de paie| Microsoft Docs
description: "Pour gérer les paies, vous importez et reportez des transactions financières de votre fournisseur de paie dans le grand livre, en utilisant une extension de paie telle que Ceridian ou Quickbooks."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: Ceridian, Quickbooks, salary
ms.date: 06/16/2017
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: e7dcdc0935a8793ae226dfc2f9709b5b8f487a62
ms.openlocfilehash: 52ed67b2f2e08cbb2f4104c2b0c26f662212a9f4
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="import-payroll-transactions"></a><span data-ttu-id="80599-103">Importer les transactions de paie</span><span class="sxs-lookup"><span data-stu-id="80599-103">Import Payroll Transactions</span></span>
<span data-ttu-id="80599-104">Pour tenir compte des paiements des salaires et des transactions associées, vous devez importer et reporter des transactions financières effectuées par votre fournisseur de paie dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="80599-104">To account for salary payments and related transactions, you must import and post financial transactions made by your payroll provider to the general ledger.</span></span> <span data-ttu-id="80599-105">Pour cela, vous devez commencer par importer un fichier que vous recevez du fournisseur de paie dans la fenêtre **Feuille comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="80599-105">To do this, you first import a file that you receive from the payroll provider into the **General Journal** window.</span></span> <span data-ttu-id="80599-106">Vous devez ensuite mapper les comptes externes du fichier de paie aux comptes généraux appropriés.</span><span class="sxs-lookup"><span data-stu-id="80599-106">Then you map the external accounts in the payroll file to the relevant G/L accounts.</span></span> <span data-ttu-id="80599-107">Enfin, vous devez reporter les transactions de paie en fonction du mappage de compte.</span><span class="sxs-lookup"><span data-stu-id="80599-107">Lastly, you post the payroll transactions according to the account mapping.</span></span>

> [!NOTE]  
>   <span data-ttu-id="80599-108">Pour utiliser cette fonctionnalité, une extension pour l'importation de la paie doit être installée et activée.</span><span class="sxs-lookup"><span data-stu-id="80599-108">To use this functionality, an extension for payroll import must be installed and enabled.</span></span> <span data-ttu-id="80599-109">Les extensions Salaire de Ceridian et Importer le fichier de paie de Quickbooks sont préinstallées dans [!INCLUDE[d365fin](includes/d365fin_md.md)].</span><span class="sxs-lookup"><span data-stu-id="80599-109">The Ceridian Payroll and the Quickbooks Payroll File Import extensions are pre-installed in [!INCLUDE[d365fin](includes/d365fin_md.md)].</span></span> <span data-ttu-id="80599-110">Pour plus d'informations, voir [Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md).</span><span class="sxs-lookup"><span data-stu-id="80599-110">For more information, see [Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md).</span></span>

## <a name="to-import-a-payroll-file"></a><span data-ttu-id="80599-111">Pour importer un fichier de paie</span><span class="sxs-lookup"><span data-stu-id="80599-111">To import a payroll file</span></span>
1. <span data-ttu-id="80599-112">Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles comptabilité**, puis sélectionnez le lien connexe.</span><span class="sxs-lookup"><span data-stu-id="80599-112">Choose the ![Search for Page or Report](media/ui-search/search_small.png "Search for Page or Report icon") icon, enter **General Journals**, and then choose the related link.</span></span>
2. <span data-ttu-id="80599-113">Dans le nom feuille comptabilité pertinent, sélectionnez l'action **Importer les transactions de paie**.</span><span class="sxs-lookup"><span data-stu-id="80599-113">In the relevant general journal batch, choose the **Import Payroll Transactions** action.</span></span> <span data-ttu-id="80599-114">Un guide de configuration assistée s'ouvre.</span><span class="sxs-lookup"><span data-stu-id="80599-114">An assisted setup guide opens.</span></span>
3. <span data-ttu-id="80599-115">Suivez les étapes de la fenêtre **Importer les transactions de paie**.</span><span class="sxs-lookup"><span data-stu-id="80599-115">Follow the steps in the **Import Payroll Transactions** window.</span></span>

    > [!TIP]  
    >   <span data-ttu-id="80599-116">Dans l'étape à propos du mappage des enregistrements de paie externes dans les comptes généraux, les mappages que vous effectuez seront reconnus la prochaine fois que les mêmes enregistrements seront importés.</span><span class="sxs-lookup"><span data-stu-id="80599-116">In the step about mapping the external payroll records to your G/L accounts, the mappings that you make will be remembered next time the same records are imported.</span></span> <span data-ttu-id="80599-117">Cela vous permettra d'économiser du temps car vous n'avez pas à remplir manuellement le champ **N° compte** dans le journal général à chaque importation de transactions de paie récurrentes.</span><span class="sxs-lookup"><span data-stu-id="80599-117">This will save you time as you do not have to manually fill in the **Account No.** field in the general journal every time you have imported recurring payroll transactions.</span></span>   

    <span data-ttu-id="80599-118">Lorsque vous cliquez sur le bouton **OK** dans le guide de configuration assistée, la fenêtre **Feuille comptabilité** est complétée par des lignes représentant les transactions contenues dans le fichier de paie et par les comptes appropriés des champs **Compte général** en fonction des mappages effectués dans le guide.</span><span class="sxs-lookup"><span data-stu-id="80599-118">When you choose the **OK** button in the assisted setup guide, the **General Journal** window is filled with lines representing the transactions that the payroll file contains and with the relevant accounts prefilled in the **G/L Account** fields according to mappings you made in the guide.</span></span>
4. <span data-ttu-id="80599-119">Modifiez ou reportez les lignes journal comme pour toute autre transaction du journal général.</span><span class="sxs-lookup"><span data-stu-id="80599-119">Edit or post the journal lines as for any other general ledger transactions.</span></span> <span data-ttu-id="80599-120">Pour plus d'informations, voir [Reporter les transactions directement dans le grand livre](finance-how-post-transactions-directly.md).</span><span class="sxs-lookup"><span data-stu-id="80599-120">For more information, see [Post Transactions Directly to the General Ledger](finance-how-post-transactions-directly.md).</span></span>   

## <a name="see-also"></a><span data-ttu-id="80599-121">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="80599-121">See Also</span></span>
[<span data-ttu-id="80599-122">Finances</span><span class="sxs-lookup"><span data-stu-id="80599-122">Finance</span></span>](finance.md)  
<span data-ttu-id="80599-123">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions](ui-extensions.md)</span><span class="sxs-lookup"><span data-stu-id="80599-123">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions](ui-extensions.md)</span></span>  
[<span data-ttu-id="80599-124">Utilisation de feuilles comptabilité</span><span class="sxs-lookup"><span data-stu-id="80599-124">Working with General Journals</span></span>](ui-work-general-journals.md)  
