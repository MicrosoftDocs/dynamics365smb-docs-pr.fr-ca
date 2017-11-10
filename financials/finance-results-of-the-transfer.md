---
title: "Résultats du transfert | Microsoft Docs"
description: "Cette rubrique décrit ce qui se produit après le transfert des écritures GL vers les écritures de coûts."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: general ledger, transfer, cost entries
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 9f1c3573137d7cd15c8b98813da514f8b8f2e1cd
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# <a name="results-of-transferring-general-ledger-entries-to-cost-entries"></a><span data-ttu-id="c90d6-103">Résultats du transfert des écritures GL vers les écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="c90d6-103">Results of Transferring General Ledger Entries to Cost Entries</span></span>
<span data-ttu-id="c90d6-104">Lors du transfert des écritures GL vers les écritures de coûts, [!INCLUDE[d365fin](includes/d365fin_md.md)] crée des connexions dans les écritures des tables **Écriture**, **Écriture de coûts** et **Registre de coûts** pour assurer le suivi des connexions entre les écritures de coûts et les écritures GL.</span><span class="sxs-lookup"><span data-stu-id="c90d6-104">During the transfer of general ledger entries to cost entries, [!INCLUDE[d365fin](includes/d365fin_md.md)] creates connections in the entries in the **G/L Entry** table, the **Cost Entry** table, and the **Cost Register** table to make it possible to trace the connections between cost entries and general ledger entries.</span></span>  

## <a name="general-ledger-entries"></a><span data-ttu-id="c90d6-105">Écritures journal général</span><span class="sxs-lookup"><span data-stu-id="c90d6-105">General Ledger Entries</span></span>  
<span data-ttu-id="c90d6-106">Pour chaque écriture GL transférée vers la comptabilité analytique, [!INCLUDE[d365fin](includes/d365fin_md.md)] renseigne le champ **N° écriture**.</span><span class="sxs-lookup"><span data-stu-id="c90d6-106">For each general ledger entry that is transferred to cost accounting, [!INCLUDE[d365fin](includes/d365fin_md.md)] fills the cost **Entry No.** field.</span></span>  

## <a name="cost-entries"></a><span data-ttu-id="c90d6-107">Écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="c90d6-107">Cost Entries</span></span>  
<span data-ttu-id="c90d6-108">Pour chaque écriture de coûts, [!INCLUDE[d365fin](includes/d365fin_md.md)] garde le numéro d'écriture de l'écriture GL correspondante dans le champ **N° Écriture** de la table **Écriture de coûts**.</span><span class="sxs-lookup"><span data-stu-id="c90d6-108">For each cost entry, [!INCLUDE[d365fin](includes/d365fin_md.md)] saves the entry number of the corresponding general ledger entry in the **G/L Entry No.** field in the **Cost Entry** table.</span></span>  

<span data-ttu-id="c90d6-109">Pour les écritures de coûts combinées, [!INCLUDE[d365fin](includes/d365fin_md.md)] garde le numéro de la dernière écriture comptable, à savoir l'écriture avec le numéro le plus élevé.</span><span class="sxs-lookup"><span data-stu-id="c90d6-109">For combined cost entries, [!INCLUDE[d365fin](includes/d365fin_md.md)] saves the entry number of the last general ledger entry, which is the entry with the highest entry number.</span></span>  

<span data-ttu-id="c90d6-110">Le champ **Compte du grand livre** de la table **Écriture de coûts** contient le numéro du compte GL, d'où provient l'écriture de coûts.</span><span class="sxs-lookup"><span data-stu-id="c90d6-110">The **G/L Account** field in the **Cost Entry** table contains the number of the general ledger account that the cost entry came from.</span></span>  

<span data-ttu-id="c90d6-111">Pour les écritures de coûts uniques, [!INCLUDE[d365fin](includes/d365fin_md.md)] transfère le texte de validation depuis l'écriture comptable vers le champ de texte **Description**.</span><span class="sxs-lookup"><span data-stu-id="c90d6-111">For single cost entries, [!INCLUDE[d365fin](includes/d365fin_md.md)] transfers the posting text from the general ledger entry to the **Description** text field.</span></span> <span data-ttu-id="c90d6-112">Pour les écritures combinées, le champ de texte indique que ces écritures sont transférées en tant qu'écritures combinées.</span><span class="sxs-lookup"><span data-stu-id="c90d6-112">For combined entries, the text field shows these entries are transferred as combined entries.</span></span> <span data-ttu-id="c90d6-113">Par exemple, pour une écriture combinée pour octobre 2013, le texte peut être **Écritures combinées, octobre 2013**.</span><span class="sxs-lookup"><span data-stu-id="c90d6-113">For example, for a combined entry for the month of October in 2013, the text can be **Combined Entries, October 2013**.</span></span>  

## <a name="cost-register"></a><span data-ttu-id="c90d6-114">Registre de coûts</span><span class="sxs-lookup"><span data-stu-id="c90d6-114">Cost Register</span></span>  
<span data-ttu-id="c90d6-115">Dans la table **Registre de coûts**, [!INCLUDE[d365fin](includes/d365fin_md.md)] crée une écriture à l'aide du transfert source depuis la comptabilité.</span><span class="sxs-lookup"><span data-stu-id="c90d6-115">In the **Cost Register** table, [!INCLUDE[d365fin](includes/d365fin_md.md)] creates an entry with the source transfer from general ledger.</span></span> <span data-ttu-id="c90d6-116">L'écriture enregistre le premier et le dernier numéros des écritures transférées, en plus des premier et dernier numéros des écritures de coûts créées.</span><span class="sxs-lookup"><span data-stu-id="c90d6-116">The entry records the first and last entry numbers of the general ledger entries that are transferred, in addition to the first and last entry numbers of the cost entries that are created.</span></span>  

## <a name="see-also"></a><span data-ttu-id="c90d6-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c90d6-117">See Also</span></span>  
<span data-ttu-id="c90d6-118">[Comment transférer les écritures comptables vers les écritures de coûts](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="c90d6-118">[How to: Transfer General Ledger Entries to Cost Entries](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md) </span></span>  
<span data-ttu-id="c90d6-119">[Critères de transfert des écritures comptables vers les écritures de coûts](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span><span class="sxs-lookup"><span data-stu-id="c90d6-119">[Criteria for Transferring General Ledger Entries to Cost Entries](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md) </span></span>  
<span data-ttu-id="c90d6-120">[Transfert automatique et écritures combinées](finance-automatic-transfer-combined-entries.md) </span><span class="sxs-lookup"><span data-stu-id="c90d6-120">[Automatic Transfer and Combined Entries](finance-automatic-transfer-combined-entries.md) </span></span>  
[<span data-ttu-id="c90d6-121">Transfert et report des écritures de coûts</span><span class="sxs-lookup"><span data-stu-id="c90d6-121">Transferring and Posting Cost Entries</span></span>](finance-transfer-and-post-cost-entries.md)  
