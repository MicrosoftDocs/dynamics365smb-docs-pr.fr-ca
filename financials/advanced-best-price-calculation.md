---
title: "Avancé : Calcul du meilleur prix| Microsoft Docs"
description: "Décrit comment l&quot;application de prix spéciaux et d&quot;escomptes ligne garantit que votre profit pour les transactions est toujours optimal."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: pricing, sales price
ms.date: 02/08/2017
ms.author: sgroespe
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: e4dbe800abef3fa4afe3eabec3450b6ee0f20080
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="advanced-best-price-calculation"></a>Avancé : calcul du meilleur prix
Lorsque vous avez enregistré des prix spéciaux et des remises de ligne pour les ventes et les achats, [!INCLUDE[d365fin](includes/d365fin_md.md)] s'assure que votre marge pour l'article est toujours optimale en calculant automatiquement le meilleur prix dans les documents achat et vente, sur le projet et les lignes feuille article.

Le meilleur prix est le prix le plus bas autorisé associé à l'escompte ligne le plus élevé autorisé à une date donnée. [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule automatiquement cette valeur lorsqu'il insère le prix unitaire et le pourcentage de remise de ligne pour des articles dans le nouveau document et les lignes feuille.

**Remarque** : Voici une description du calcul du meilleur prix pour la vente. Le calcul est le même pour les achats.

1. [!INCLUDE[d365fin](includes/d365fin_md.md)] vérifie la combinaison client facturé et article, et calcule le prix unitaire applicable et le pourcentage remise de ligne à l'aide des critères suivants :

    - Ce client a-t-il une entente pour des prix ou des escomptes ou appartient-il à un groupe bénéficiant d'un telle entente?
    - L'article ou le groupe escompte article sur la ligne est-il inclus dans l'une ou l'autre de ces ententes prix/escompte?
    - La date de commande (ou la date de report pour la facture et la note de crédit) est-elle comprise entre les dates début et de fin de l'entente prix/escompte?
    - Un code unité de mesure est-il spécifié? Si c'est le cas, [!INCLUDE[d365fin](includes/d365fin_md.md)] recherche des prix/remises possédant le même code unité, et des prix/remises sans code unité.

2. [!INCLUDE[d365fin](includes/d365fin_md.md)] vérifie si des accords prix/remise s'appliquent à des informations sur le document ou la ligne feuille, puis insère le prix unitaire applicable et le pourcentage remise de ligne, à l'aide des critères suivants :

    - Existe-t-il une quantité minimum à respecter dans l'entente de prix/escompte?
    - Existe-t-il une exigence en matière de devise à respecter dans l'entente de prix/escompte? Si c'est le cas, le prix le plus bas et l'escompte de ligne le plus élevé pour cette devise sont insérés, même si la devise locale permettrait d'offrir un meilleur prix. S'il n'existe aucun accord de prix/remise dans le code devise indiqué, [!INCLUDE[d365fin](includes/d365fin_md.md)] insère le prix le plus bas et la remise de ligne la plus élevée en DS.

Si aucun prix spécial ne peut être calculé pour l'article de la ligne, alors soit le coût unitaire direct, soit le prix unitaire à partir de la fiche article est inséré.

## <a name="see-also"></a>Voir aussi
[Procédure : enregistrer les prix de vente spéciaux et les remises](sales-how-record-sales-price-discount-payment-agreements.md)  
[Procédure : enregistrer les prix d'achat spéciaux et les remises](purchasing-how-record-purchase-price-discount-payment-agreements.md)  
[Définition des ventes](sales-setup-sales.md)  
[Ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

