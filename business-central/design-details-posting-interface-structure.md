---
title: Détails de conception- Structure de l'interface de report | Microsoft Docs
description: Cette rubrique donne un aperçu des procédures globales dans la structure de l'interface de report.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting, interface, design
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: 1e80b905d96fc2204b61b03c0970257755b9e105
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3787356"
---
# <a name="design-details-posting-interface-structure"></a><span data-ttu-id="7e905-103">Détails de conception : Structure de l'interface de report</span><span class="sxs-lookup"><span data-stu-id="7e905-103">Design Details: Posting Interface Structure</span></span>
<span data-ttu-id="7e905-104">Dans la structure de l'interface de validation [!INCLUDE[d365fin](includes/d365fin_md.md)], il y a plusieurs procédures globales utilisant la même structure :</span><span class="sxs-lookup"><span data-stu-id="7e905-104">In the [!INCLUDE[d365fin](includes/d365fin_md.md)] posting interface structure, there are several global procedures that use the same structure:</span></span>  
  
* <span data-ttu-id="7e905-105">Code de procédure d'appel RunWithCheck et RunWithoutCheck – interface de report générique pour Gen.</span><span class="sxs-lookup"><span data-stu-id="7e905-105">RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen.</span></span> <span data-ttu-id="7e905-106">Jnl Line.</span><span class="sxs-lookup"><span data-stu-id="7e905-106">Jnl Line.</span></span>  
* <span data-ttu-id="7e905-107">CustPostApplyCustLedgEntry – report de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="7e905-107">CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="7e905-108">VendPostApplyVendLedgEntry – report de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="7e905-108">VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="7e905-109">UnapplyCustLedgEntry – report de l'annulation de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="7e905-109">UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries</span></span>  
* <span data-ttu-id="7e905-110">UnapplyVendLedgEntry – report de l'annulation de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="7e905-110">UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e905-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="7e905-111">See Also</span></span>  
[<span data-ttu-id="7e905-112">Détails de conception : Structure du moteur de validation</span><span class="sxs-lookup"><span data-stu-id="7e905-112">Design Details: Posting Engine Structure</span></span>](design-details-posting-engine-structure.md)