---
title: Configuration des groupes fiscaux, des régions fiscales et des juridictions fiscales au Canada | Microsoft Docs
description: En savoir plus sur la manière dont la taxe de vente est configurée, et sur le fonctionnement des groupes fiscaux, des régions fiscales (états, comtés, villes et localités), des juridictions de taxe et des spécifications de taxe.
services: project-madeira
documentationcenter: ''
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 10/01/2018
ms.author: edupont
ms.openlocfilehash: c6086c948de8efb0aec89ed8cc2de25b3ca8f474
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "826567"
---
# <a name="reporting-sales-tax-in-canada"></a>Déclaration de la taxe de vente au Canada
Lorsque vous commencez à utiliser [!INCLUDE[d365fin](../../includes/d365fin_md.md)], vous pouvez exécuter un guide de configuration assistée afin de rapidement et facilement configurer les informations relatives à la Sales Tax pour votre société, vos clients et vos fournisseurs. En quelques minutes, vous êtes prêt à créer des documents vente et des documents achat pour lesquels la taxe de vente est calculée correctement. Ceci est expliqué [dans notre billet de blog](https://madeira.microsoft.com/blog/sales-tax-setup-made-easy).
Si vous passez à la section Ma compagnie vierge, nous vous recommandons de commencer par utiliser chacun des guides de configuration assistée, y compris celui qui concerne la taxe de vente. Si vous préférez configurer la taxe de vente par vous-même, cet article explique ce que vous devez prendre en compte.  

## <a name="tax-groups-tax-areas-and-tax-jurisdictions"></a>Groupes taxes, zones de recouvrement et autorités de recouvrement
Dans [!INCLUDE[d365fin](../../includes/d365fin_md.md)], un groupe taxes représente un groupe d'articles ou de ressources soumis au même conditions pour ce qui est des taxes. Par exemple, vous pouvez configurer un groupe fiscal pour les articles soumis à la taxe et un autre pour les articles non soumis à la taxe. Vous devez affecter des codes groupe fiscal aux articles en inventaire et aux comptes du grand livre. De même, vous devez affecter des codes de région fiscale aux clients, aux emplacements et aux paramètres de votre compagnie. Le guide de configuration assistée vous aide à effectuer ces opérations.  

Chaque région fiscale correspond à un regroupement d'autorités fiscales basé sur une situation géographique particulière. Par exemple, la région fiscale de Miami, Floride, comprend trois autorités fiscales de la taxe de vente : la ville (Miami), le comté (Dade) et l'état (Floride). [!INCLUDE[d365fin](../../includes/d365fin_md.md)] inclut un ensemble limité de zones de recouvrement avec une configuration par défaut, mais vous pouvez les modifier et ajouter de nouvelles zones de recouvrement.  

Si vous configurez de nouvelles zones et juridictions de recouvrement, vous devez veiller à bien remplir les champs correctement. Au Canada, le gouvernemental fédéral et les provinces sont en mesure de prélever la taxe de vente. Les compagnies recueillent la taxe de vente et la versent aux autorités gouvernementales pour les produits vendus aux utilisateurs finaux. La taxe de vente peut également être facturée sur une taxe de vente existante. Par exemple, la taxe peut être calculée sur un montant facture vente qui comprend déjà la taxe imposée par d'autres autorités.  

Au Canada, les montants de taxe doivent être détaillés dans les documents concernant chaque juridiction fiscale. Jusqu'à quatre autorités de recouvrement peuvent apparaître dans un document, et les autorités dotées du même ordre d'impression sont regroupées lors de l'impression.  

## <a name="tax-details"></a>Détails fiscaux
La page **Détails fiscaux** affiche différentes combinaisons de juridictions de taxe de vente et de groupes de taxe de vente afin d'établir des taux de taxe de vente. Pour chaque juridiction fiscale, nous vous recommandons de configurer un groupe fiscal pour la taxe de vente normale, un autre groupe fiscal pour les articles ou les services qui ne sont pas soumis à la taxe et un groupe fiscal supplémentaire pour chaque type d'article ou de service traité avec un taux de taxe de vente différent dans cette juridiction fiscale.  

Au Canada, lorsque vous vendez à un client dans un lieu où vous n'avez pas de *situs*(ou un lieu légal dans cette province), vous ne percevez pas la taxe de vente. Pour les magasins dans lesquels vous n'avez pas de situs, assurez-vous que la valeur des champs **Taxe inférieure minimum** and **Taxe supérieure maximum** est égale à 0,00.  

## <a name="see-also"></a>Voir aussi
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance-setup-finance.md)  
[Taxe sur les ventes et taxe sur les biens et les services au Canada](sales-tax-goods-services.md)  
[Configurer la taxe de vente - Regarder une vidéo](https://www.youtube.com/watch?v=qMs4BoSytN8&index=13&list=PLcakwueIHoT8K1m148oMqo7amR2a7Bz-8)  
[Utilisation de [!INCLUDE[d365fin](../../includes/d365fin_md.md)]](../../ui-work-product.md)  
