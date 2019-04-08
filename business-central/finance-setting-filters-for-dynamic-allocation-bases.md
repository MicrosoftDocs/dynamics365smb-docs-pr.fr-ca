---
title: Définition de filtres pour les bases d'affectation dynamique | Microsoft Docs
description: Le mode d'affectation dynamique dépend des valeurs modifiables. Par exemple, le nombre d'employés dans un centre de coûts ou le nombre d'articles vendus d'un objet de coûts pour une période donnée. Il existe neuf bases d'affectation prédéfinies et douze plages de dates dynamiques. Vous définissez plusieurs filtres en fonction de la base d'affectation.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 11/13/2018
ms.author: sgroespe
redirect_url: finance-define-and-allocate-costs
ms.openlocfilehash: fcf97328900bb21a85be51452b9e86da8398d195
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "814144"
---
# <a name="setting-filters-for-dynamic-allocation-bases"></a>Définition de filtres pour les bases d'affectation dynamique
Le mode d'affectation dynamique dépend des valeurs modifiables. Par exemple, le nombre d'employés dans un centre de coûts ou le nombre d'articles vendus d'un objet de coûts pour une période donnée. Il existe neuf bases d'affectation prédéfinies et douze plages de dates dynamiques. Vous définissez plusieurs filtres en fonction de la base d'affectation.  

## <a name="setting-filters-for-dynamic-allocation-bases"></a>Définition de filtres pour les bases d'affectation dynamique  
 Le tableau suivant affiche les filtres applicables aux diverses bases de ventilation et les valeurs valides dans les champs **Filtre n°** et **Filtre groupe**. Appuyez sur F1 dans le champ **Code filtre date** pour lire les descriptions détaillées.  

|**Base**|**Filtre n°**|**Code filtre date**|**Filtre centre de coûts**|**Filtre objet de coûts**|**Filtre groupe**|  
|--------------|----------------------------------------|----------------------------------------------|------------------------------------------------|------------------------------------------------|------------------------------------------|  
|Écritures|Compte général|Oui|Oui|Oui|N/A|  
|Écritures budget|Compte général|Oui|Oui|Oui|Nom de budget du grand livre|  
|Écritures du type de coût|Type coût|Oui|Oui|Oui|N/A|  
|Écritures budget des coûts|Type coût|Oui|Oui|Oui|Nom du budget|  
|Nombre de salariés|N/A|Oui|Oui|Oui|N/A|  
|Articles vendus (qté)|N° d'article|Oui|Oui|Oui|Groupe de report inventaire|  
|Articles achetés (qté)|N° d'article|Oui|Oui|Oui|Groupe de report inventaire|  
|Articles vendus (montant)|N° d'article|Oui|Oui|Oui|Groupe de report inventaire|  
|Articles achetés (montant)|Nombre d'articles|Oui|Oui|Oui|Groupe de report inventaire|  

## <a name="see-also"></a>Voir aussi  
[Définition et répartition des coûts](finance-define-and-allocate-costs.md)
