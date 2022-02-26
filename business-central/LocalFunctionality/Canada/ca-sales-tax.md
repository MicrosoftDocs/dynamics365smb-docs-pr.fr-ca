---
title: Déclaration de la taxe de vente au Canada [CA]
description: En savoir plus sur la manière dont la taxe de vente est configurée, et sur le fonctionnement des groupes fiscaux, des régions fiscales (états, comtés, villes et localités), des juridictions de taxe et des spécifications de taxe au Canada.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 10/12/2021
ms.author: edupont
ms.openlocfilehash: 4a0200e9f76e72653293caabbf3be6634e782274
ms.sourcegitcommit: c35a132cc615629e4f873177755a39ab58783e38
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/14/2021
ms.locfileid: "7643910"
---
# <a name="reporting-sales-tax-in-canada"></a>Déclaration de la taxe de vente au Canada

[!INCLUDE [sales-tax](../includes/CAMXUS/sales-tax-setup.md)]

Si vous configurez de nouvelles zones et juridictions de recouvrement, vous devez veiller à bien remplir les champs correctement. Au Canada, le gouvernemental fédéral et les provinces sont en mesure de prélever la taxe de vente. Les compagnies recueillent la taxe de vente et la versent aux autorités gouvernementales pour les produits vendus aux utilisateurs finaux. La taxe de vente peut également être facturée sur une taxe de vente existante. Par exemple, la taxe peut être calculée sur un montant facture vente qui comprend déjà la taxe imposée par d'autres autorités.  

Au Canada, les montants de taxe doivent être détaillés dans les documents concernant chaque juridiction fiscale. Jusqu'à quatre autorités de recouvrement peuvent apparaître dans un document, et les autorités dotées du même ordre d'impression sont regroupées lors de l'impression.  

## <a name="tax-details"></a>Détails fiscaux

La page **Détails fiscaux** affiche différentes combinaisons de juridictions de taxe de vente et de groupes de taxe de vente afin d'établir des taux de taxe de vente. Pour chaque juridiction fiscale, nous vous recommandons de configurer un groupe fiscal pour la taxe de vente normale, un autre groupe fiscal pour les articles ou les services qui ne sont pas soumis à la taxe et un groupe fiscal supplémentaire pour chaque type d'article ou de service traité avec un taux de taxe de vente différent dans cette juridiction fiscale. [!INCLUDE [tooltip-inline-tip_md](../../includes/tooltip-inline-tip_md.md)]  

<!--COMMENTING OUT DUE TO ISSUE #535: In Canada, when you sell to a customer at a location where you do not have a *situs*—or a legal location in that state—you do not collect sales tax. For locations in which you do not have a situs, ensure that both the **Tax Below Minimum** and **Tax Above Maximum** fields are 0.00.  -->

## <a name="see-also"></a>Voir aussi

[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance-setup-finance.md)  
[Taxe sur les ventes et taxe sur les biens et les services au Canada](sales-tax-goods-services.md)  
[Configurer la taxe de vente - Regarder une vidéo](https://www.youtube.com/watch?v=qMs4BoSytN8&index=13&list=PLcakwueIHoT8K1m148oMqo7amR2a7Bz-8)  
[Utilisation de [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]