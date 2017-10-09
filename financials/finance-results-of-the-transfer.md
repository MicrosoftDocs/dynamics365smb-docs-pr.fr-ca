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
# <a name="results-of-transferring-general-ledger-entries-to-cost-entries"></a>Résultats du transfert des écritures GL vers les écritures de coûts
Lors du transfert des écritures GL vers les écritures de coûts, [!INCLUDE[d365fin](includes/d365fin_md.md)] crée des connexions dans les écritures des tables **Écriture**, **Écriture de coûts** et **Registre de coûts** pour assurer le suivi des connexions entre les écritures de coûts et les écritures GL.  

## <a name="general-ledger-entries"></a>Écritures journal général  
Pour chaque écriture GL transférée vers la comptabilité analytique, [!INCLUDE[d365fin](includes/d365fin_md.md)] renseigne le champ **N° écriture**.  

## <a name="cost-entries"></a>Écritures de coûts  
Pour chaque écriture de coûts, [!INCLUDE[d365fin](includes/d365fin_md.md)] garde le numéro d'écriture de l'écriture GL correspondante dans le champ **N° Écriture** de la table **Écriture de coûts**.  

Pour les écritures de coûts combinées, [!INCLUDE[d365fin](includes/d365fin_md.md)] garde le numéro de la dernière écriture comptable, à savoir l'écriture avec le numéro le plus élevé.  

Le champ **Compte du grand livre** de la table **Écriture de coûts** contient le numéro du compte GL, d'où provient l'écriture de coûts.  

Pour les écritures de coûts uniques, [!INCLUDE[d365fin](includes/d365fin_md.md)] transfère le texte de validation depuis l'écriture comptable vers le champ de texte **Description**. Pour les écritures combinées, le champ de texte indique que ces écritures sont transférées en tant qu'écritures combinées. Par exemple, pour une écriture combinée pour octobre 2013, le texte peut être **Écritures combinées, octobre 2013**.  

## <a name="cost-register"></a>Registre de coûts  
Dans la table **Registre de coûts**, [!INCLUDE[d365fin](includes/d365fin_md.md)] crée une écriture à l'aide du transfert source depuis la comptabilité. L'écriture enregistre le premier et le dernier numéros des écritures transférées, en plus des premier et dernier numéros des écritures de coûts créées.  

## <a name="see-also"></a>Voir aussi  
[Comment transférer les écritures comptables vers les écritures de coûts](finance-how-to-transfer-general-ledger-entries-to-cost-entries.md)   
[Critères de transfert des écritures comptables vers les écritures de coûts](finance-criteria-for-transferring-general-ledger-entries-to-cost-entries.md)   
[Transfert automatique et écritures combinées](finance-automatic-transfer-combined-entries.md)   
[Transfert et report des écritures de coûts](finance-transfer-and-post-cost-entries.md)  

