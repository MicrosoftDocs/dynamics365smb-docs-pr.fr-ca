---
title: "Détails de conception- Structure de l'interface de report | Microsoft Docs"
description: "Cette rubrique donne un aperçu des procédures globales dans la structure de l'interface de report."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting, interface, design
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: 97b1bc02f848d583240a1701e41be4b639422a6c
ms.contentlocale: fr-ca
ms.lasthandoff: 12/14/2017

---
# <a name="design-details-posting-interface-structure"></a><span data-ttu-id="b113f-103">Détails de conception : Structure de l'interface de report</span><span class="sxs-lookup"><span data-stu-id="b113f-103">Design Details: Posting Interface Structure</span></span>
<span data-ttu-id="b113f-104">Dans la structure de l'interface de validation [!INCLUDE[d365fin](includes/d365fin_md.md)], il y a plusieurs procédures globales utilisant la même structure :</span><span class="sxs-lookup"><span data-stu-id="b113f-104">In the [!INCLUDE[d365fin](includes/d365fin_md.md)] posting interface structure, there are several global procedures that use the same structure:</span></span>  
  
* <span data-ttu-id="b113f-105">Code de procédure d'appel RunWithCheck et RunWithoutCheck – interface de report générique pour Ligne journal général</span><span class="sxs-lookup"><span data-stu-id="b113f-105">RunWithCheck and RunWithoutCheck call procedure Code – generic posting interface for Gen. Jnl Line.</span></span>  
* <span data-ttu-id="b113f-106">CustPostApplyCustLedgEntry – report de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="b113f-106">CustPostApplyCustLedgEntry – post customer application, called from codeunit 226 CustEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="b113f-107">VendPostApplyVendLedgEntry – report de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées.</span><span class="sxs-lookup"><span data-stu-id="b113f-107">VendPostApplyVendLedgEntry – post vendor application, called from codeunit 227 VendEntry-Apply Posted Entries.</span></span>  
* <span data-ttu-id="b113f-108">UnapplyCustLedgEntry – report de l'annulation de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="b113f-108">UnapplyCustLedgEntry – post unapply of customer application, called from codeunit 226 CustEntry-Apply Posted Entries</span></span>  
* <span data-ttu-id="b113f-109">UnapplyVendLedgEntry – report de l'annulation de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées</span><span class="sxs-lookup"><span data-stu-id="b113f-109">UnapplyVendLedgEntry – post unapply of vendor application, called from codeunit 227 VendEntry-Apply Posted Entries</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b113f-110">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b113f-110">See Also</span></span>  
[<span data-ttu-id="b113f-111">Détails de conception : Structure du moteur de validation</span><span class="sxs-lookup"><span data-stu-id="b113f-111">Design Details: Posting Engine Structure</span></span>](design-details-posting-engine-structure.md)
