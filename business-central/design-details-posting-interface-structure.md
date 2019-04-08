---
title: Détails de conception- Structure de l'interface de report | Microsoft Docs
description: Cette rubrique donne un aperçu des procédures globales dans la structure de l'interface de report.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: posting, interface, design
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 236cbcc45ccca23905dcb79a491236c80b2bdebf
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813450"
---
# <a name="design-details-posting-interface-structure"></a>Détails de conception : Structure de l'interface de report
Dans la structure de l'interface de validation [!INCLUDE[d365fin](includes/d365fin_md.md)], il y a plusieurs procédures globales utilisant la même structure :  
  
* Code de procédure d'appel RunWithCheck et RunWithoutCheck – interface de report générique pour Ligne journal général  
* CustPostApplyCustLedgEntry – report de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées.  
* VendPostApplyVendLedgEntry – report de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées.  
* UnapplyCustLedgEntry – report de l'annulation de l'affectation client, appelé à partir du codeunit 226 CustEntry-Affecter les écritures reportées  
* UnapplyVendLedgEntry – report de l'annulation de l'affectation fournisseur, appelé à partir du codeunit 227 VendEntry-Affecter les écritures reportées  
  
## <a name="see-also"></a>Voir aussi  
[Détails de conception : Structure du moteur de validation](design-details-posting-engine-structure.md)