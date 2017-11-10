---
title: "Importation des données de paie ou de salaire à l'aide de l'extension Ceridian Payroll | Microsoft Docs"
description: "Utilisez cette extension pour importer des transactions de paie à partir des services Ceridian HR/Payroll (US) et Ceridian PowerPay (Canada)."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms. search.keywords: app, add-in, manifest, customize, salary, wage
ms.date: 03/29/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 18b1dcd66b6816adc9fcb8b86d4f55834f51fd02
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="the-ceridian-payroll-extension-to-dynamics-365-for-financials"></a><span data-ttu-id="b2c59-103">Extension Ceridian Payroll pour Dynamics 365 for Financials</span><span class="sxs-lookup"><span data-stu-id="b2c59-103">The Ceridian Payroll Extension to Dynamics 365 for Financials</span></span>
<span data-ttu-id="b2c59-104">Pour tenir compte des paiements des salaires et des transactions associées, vous devez importer et reporter des transactions financières effectuées par votre fournisseur de paie dans le grand livre.</span><span class="sxs-lookup"><span data-stu-id="b2c59-104">To account for salary payments and related transactions, you must import and post financial transactions made by your payroll provider to the general ledger.</span></span>

<span data-ttu-id="b2c59-105">Pour cela, vous devez commencer par importer un fichier que vous recevez du fournisseur de paie dans la fenêtre **Feuille comptabilité**.</span><span class="sxs-lookup"><span data-stu-id="b2c59-105">To do this, you first import a file that you receive from the payroll provider into the **General Journal** window.</span></span> <span data-ttu-id="b2c59-106">Vous devez ensuite mapper les comptes externes du fichier de paie aux comptes généraux appropriés.</span><span class="sxs-lookup"><span data-stu-id="b2c59-106">Then you map the external accounts in the payroll file to the relevant G/L accounts.</span></span> <span data-ttu-id="b2c59-107">Enfin, vous devez reporter les transactions de paie en fonction du mappage de compte.</span><span class="sxs-lookup"><span data-stu-id="b2c59-107">Lastly, you post the payroll transactions according to the account mapping.</span></span> <span data-ttu-id="b2c59-108">Pour plus d'informations, voir [Procédure : Importer les transactions de paie](finance-how-import-payroll-transactions.md)..</span><span class="sxs-lookup"><span data-stu-id="b2c59-108">For more information, see [How to: Import Payroll Transactions](finance-how-import-payroll-transactions.md).</span></span>

<span data-ttu-id="b2c59-109">L'extension Ceridian Payroll vous permet d'importer des transactions de paie à partir des services Ceridian HR/Payroll (US) et Ceridian PowerPay (Canada).</span><span class="sxs-lookup"><span data-stu-id="b2c59-109">The Ceridian Payroll extension allows you to import payroll transactions from the Ceridian HR/Payroll (US) and Ceridian PowerPay (Canada) services.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2c59-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b2c59-110">See Also</span></span>
<span data-ttu-id="b2c59-111">[Personnalisation de [!INCLUDE[d365fin](includes/d365fin_md.md)] à l'aide des extensions ](ui-extensions.md)  </span><span class="sxs-lookup"><span data-stu-id="b2c59-111">[Customizing [!INCLUDE[d365fin](includes/d365fin_md.md)] Using Extensions ](ui-extensions.md)  </span></span>  
<span data-ttu-id="b2c59-112">[Finances](finance.md)  </span><span class="sxs-lookup"><span data-stu-id="b2c59-112">[Finance](finance.md)  </span></span>  
<span data-ttu-id="b2c59-113">[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span><span class="sxs-lookup"><span data-stu-id="b2c59-113">[Working with [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)</span></span>
