---
title: Détails de conception : structure de l’interface de report
description: Cette rubrique donne un aperçu des procédures globales et les détails de la conception dans la structure de l’interface de report.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting, interface, design
ms.date: 06/15/2021
ms.author: edupont
ms.openlocfilehash: 80805675a3ecb1c847f0a55c2dc50008faa3b21f
ms.sourcegitcommit: e562b45fda20ff88230e086caa6587913eddae26
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/30/2021
ms.locfileid: "6318394"
---
# <a name="design-details-posting-interface-structure"></a>Détails de conception : Structure de l'interface de report
Dans la structure de l'interface de validation [!INCLUDE[prod_short](includes/prod_short.md)], il y a plusieurs procédures globales utilisant la même structure :  
  
* Code de procédure d'appel RunWithCheck et RunWithoutCheck – interface de report générique pour Gen. Jnl Line.  
* CustPostApplyCustLedgEntry – report de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées.  
* VendPostApplyVendLedgEntry – report de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées.  
* UnapplyCustLedgEntry – report de l'annulation de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées  
* UnapplyVendLedgEntry – report de l'annulation de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : Structure du moteur de validation](design-details-posting-engine-structure.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]