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
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: e306b0caeb58bfe7bd04f93ac64d8b593f70f695
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4751265"
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