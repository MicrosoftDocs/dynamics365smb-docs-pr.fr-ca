---
title: "Définition des centres de coûts et des objets de coûts pour le plan comptable | Microsoft Docs"
description: "Vous pouvez transférer automatiquement les écritures de dépenses et de revenus à partir de la comptabilité générale vers la comptabilité analytique, que ce soit pour le report grand livre ou avec un traitement en lot. Lors du transfert, le système transfère uniquement les écritures déjà liées à un centre de coûts ou à un objet de coûts. Pour préparer un transfert pertinent, assurez-vous que les centres de coûts et les coûts associés sont définis correctement."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 92ad393733c758304743ec0b63c98c1612e7240b
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="defining-cost-centers-and-cost-objects-for-chart-of-accounts"></a>Définition des centres de coûts et des coûts associés pour le plan comptable
Vous pouvez transférer automatiquement les écritures de dépenses et de revenus à partir de la comptabilité générale vers la comptabilité analytique, que ce soit pour le report grand livre ou avec un traitement en lot. Lors du transfert, [!INCLUDE[d365fin](includes/d365fin_md.md)] transfère uniquement les écritures déjà liées à un centre de coûts ou aux coûts associés. Pour préparer un transfert pertinent, assurez-vous que les centres de coûts et les coûts associés sont définis correctement.  

## <a name="defining-default-dimension-values-for-general-ledger-accounts"></a>Définition des sections analytiques par défaut pour des comptes généraux  
Pour chaque compte général, vous pouvez définir des sections analytiques par défaut dans la table **Affectation analytique**. L'exemple suivant décrit la configuration requise pour avoir un centre de coût DÉPARTEMENT sans jamais avoir d'objet de coûts PROJET lors du report d'un compte du grand livre.  

|**Code axe analytique**|**Contrôle validation**|  
|------------------------------------------|-----------------------------------------|  
|Département|Code obligatoire|  
|Dossier|Pas de code|  

## <a name="defining-dimension-values-for-overhead-costs-and-direct-costs"></a>Définition des sections analytiques pour les frais généraux et les coûts directs  
 Vous pouvez transférer des frais généraux à un centre de coûts, et des coûts directs aux objet de coûts. Le tableau suivant décrit comment optimiser la combinaison des valeurs de configuration des dimensions.  

|Transférer vers|Report du centre de coûts|Report des objets de coûts|  
|-----------------|-------------------------|-------------------------|  
|Centre de coûts|Code obligatoire|Pas de code|  
|Objet de coûts|Pas de code|Code obligatoire|  

> [!NOTE]  
>  Pour vous assurer que le centre de coûts et l'objet de coûts prédéfinis que vous avez configurés dans le grand livre sont reportés automatiquement dans la comptabilité analytique, cochez la case **Vérifier reports GL** dans la fenêtre Configuration de la comptabilité analytique.  

## <a name="see-also"></a>Voir aussi  
[Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
[Configuration des centres de coûts](finance-how-to-set-up-cost-centers.md)   
[Configurer les objets de coûts](finance-how-to-set-up-cost-objects.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

