---
title: Détails de conception- Structure de l'interface de report | Microsoft Docs
description: Cette rubrique donne un aperçu des procédures globales dans la structure de l'interface de report.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting, interface, design
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: b852d6e5d7f96cfba64de219ca414de60cea3a31
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5777610"
---
# <a name="design-details-posting-interface-structure"></a><span data-ttu-id="eaeb1-103">Détails de conception : Structure de l'interface de report</span><span class="sxs-lookup"><span data-stu-id="eaeb1-103">Design Details: Posting Interface Structure</span></span>
<span data-ttu-id="eaeb1-104">Dans la structure de l'interface de validation [!INCLUDE[prod_short](includes/prod_short.md)], il y a plusieurs procédures globales utilisant la même structure :</span><span class="sxs-lookup"><span data-stu-id="eaeb1-104">In the [!INCLUDE[prod_short](includes/prod_short.md)] posting interface structure, there are several global procedures that use the same structure:</span></span>  
  
* <span data-ttu-id="eaeb1-105">Code de procédure d'appel RunWithCheck et RunWithoutCheck – interface de report générique pour Gen.</span><span class="sxs-lookup"><span data-stu-id="eaeb1-105">RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen.</span></span> <span data-ttu-id="eaeb1-106">Jnl Line.</span><span class="sxs-lookup"><span data-stu-id="eaeb1-106">Jnl Line.</span></span>  
* <span data-ttu-id="eaeb1-107">CustPostApplyCustLedgEntry – report de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="eaeb1-107">CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="eaeb1-108">VendPostApplyVendLedgEntry – report de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="eaeb1-108">VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="eaeb1-109">UnapplyCustLedgEntry – report de l'annulation de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="eaeb1-109">UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries</span></span>  
* <span data-ttu-id="eaeb1-110">UnapplyVendLedgEntry – report de l'annulation de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="eaeb1-110">UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eaeb1-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="eaeb1-111">See Also</span></span>  
[<span data-ttu-id="eaeb1-112">Détails de conception : Structure du moteur de validation</span><span class="sxs-lookup"><span data-stu-id="eaeb1-112">Design Details: Posting Engine Structure</span></span>](design-details-posting-engine-structure.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]