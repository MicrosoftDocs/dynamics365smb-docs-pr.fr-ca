---
title: Détails de conception - Composantes des coûts | Microsoft Docs
description: Les composantes de coût sont différents types de coûts qui constituent la valeur d'une augmentation ou diminution d'inventaire.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: 639a982c81b29a2a51f24551d9c0814f7a3ac1c5
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3788056"
---
# <a name="design-details-cost-components"></a>Détails de conception : composants des coûts
Les composantes de coût sont différents types de coûts qui constituent la valeur d'une augmentation ou diminution d'inventaire.  

 Le tableau suivant montre les différents composants du coût et tous les composants de coût subordonnés dont ils sont composés.  

|Composante de coût|Composante subordonnée de coût|Description|  
|--------------------|--------------------------------|---------------------------------------|  
|Coût direct|Coût unitaire (prix d'achat direct)|Coûts qui ne peuvent pas être rapportés à des objets de coûts.|  
|Coût direct|Frais de transport (frais annexes)|Coûts qui ne peuvent pas être rapportés à des objets de coûts.|  
|Coût direct|Frais d'assurance (frais annexes)|Coûts qui ne peuvent pas être rapportés à des objets de coûts.|  
|Coût indirect||Coût qui ne peut pas être rapporté à un objet de coût.|  
|Écart|Écart achat|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Écart|Écart matière|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Écart|Écart capacité|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Écart|Écart sous-traitance|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Écart|Utilisation fixe de capacité|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Écart|Écart frais généraux production|Différence entre les coûts réel et standard, qui n'est validée que pour les articles utilisant le mode évaluation stock **Standard**.|  
|Réévaluation||Amortissement ou appréciation de la valeur inventaire en cours.|  
|Arrondissement||Reliquats créés par le mode de calcul de l'évaluation des diminutions d'inventaire.|  

> [!NOTE]  
>  Les frais de transport et d'assurance sont des frais annexes qui peuvent être ajoutés au coût d'un article à tout moment. Lorsque vous exécutez le traitement en lot **Ajuster coûts - Écr. article**, la valeur de toute diminution d'inventaire associée est mise à jour en conséquence.  

## <a name="see-also"></a>Voir aussi  
 [Détails de conception : stock évaluation stock](design-details-inventory-costing.md)   
 [Détails de conception : Ecart](design-details-variance.md) [Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
 [Finance](finance.md)  
 [Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
