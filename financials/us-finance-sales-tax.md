---
title: "Paramétrage des groupes taxes, zones de recouvrement et autorités de recouvrement aux États-Unis et au Canada | Microsoft Docs"
description: "En savoir plus sur la manière dont la taxe de vente est configurée, et sur le fonctionnement des groupes fiscaux, des régions fiscales (états, comtés, villes et localités), des juridictions de taxe et des spécifications de taxe."
services: project-madeira
documentationcenter: 
author: edupont04
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: local
ms.date: 03/29/2017
ms.author: edupont
ms.translationtype: Human Translation
ms.sourcegitcommit: 81636fc2e661bd9b07c54da1cd5d0d27e30d01a2
ms.openlocfilehash: 763bb1b954b30734b0f81f121a6534c83442321a
ms.contentlocale: fr-ca
ms.lasthandoff: 07/07/2017


---
# <a name="reporting-sales-tax-in-the-us-and-canada"></a>Déclaration de la taxe de vente aux États-Unis et au Canada
Lorsque vous commencez à utiliser [!INCLUDE[d365fin](includes/d365fin_md.md)], vous pouvez exécuter un guide de configuration assistée afin de rapidement et facilement configurer les informations relatives à la Sales Tax pour votre société, vos clients et vos fournisseurs. En quelques minutes, vous êtes prêt à créer des documents vente et des documents achat pour lesquels la taxe de vente est calculée correctement. Ceci est expliqué [dans notre billet de blog](https://madeira.microsoft.com/blog/sales-tax-setup-made-easy).
Si vous passez à la section Ma compagnie vierge, nous vous recommandons de commencer par utiliser chacun des guides de configuration assistée, y compris celui qui concerne la taxe de vente. Si vous préférez configurer la taxe de vente par vous-même, cet article explique ce que vous devez prendre en compte.  

## <a name="tax-groups-tax-areas-and-tax-jurisdictions"></a>Groupes taxes, zones de recouvrement et autorités de recouvrement
Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], un groupe taxes représente un groupe d'articles ou de ressources soumis au même conditions pour ce qui est des taxes. Par exemple, vous pouvez configurer un groupe fiscal pour les articles soumis à la taxe et un autre pour les articles non soumis à la taxe. Vous devez affecter des codes groupe fiscal aux articles en inventaire et aux comptes du grand livre. De même, vous devez affecter des codes de région fiscale aux clients, aux emplacements et aux paramètres de votre compagnie. Le guide de configuration assistée vous aide à effectuer ces opérations.  

Chaque région fiscale correspond à un regroupement d'autorités fiscales basé sur une situation géographique particulière. Par exemple, la région fiscale de Miami, Floride, comprend trois autorités fiscales de la taxe de vente : la ville (Miami), le comté (Dade) et l'état (Floride). [!INCLUDE[d365fin](includes/d365fin_md.md)] inclut un ensemble limité de zones de recouvrement avec une configuration par défaut, mais vous pouvez les modifier et ajouter de nouvelles zones de recouvrement.  

Si vous configurez de nouvelles zones et juridictions de recouvrement, vous devez veiller à bien remplir les champs correctement. Aux États-Unis, les états, les comtés, les villes et les localités peuvent prélever la taxe de vente. Au Canada, le gouvernemental fédéral et les provinces sont en mesure de prélever la taxe de vente. Les compagnies recueillent la taxe de vente et la versent aux autorités gouvernementales pour les produits vendus aux utilisateurs finaux. La taxe de vente peut également être facturée sur une taxe de vente existante. Par exemple, la taxe peut être calculée sur un montant facture vente qui comprend déjà la taxe imposée par d'autres autorités.  

Au Canada, les montants de taxe doivent être détaillés dans les documents concernant chaque juridiction fiscale. Jusqu'à quatre autorités de recouvrement peuvent apparaître dans un document, et les autorités dotées du même ordre d'impression sont regroupées lors de l'impression.  

## <a name="tax-details"></a>Détails fiscaux
La fenêtre **USA spécifications taxe** affiche différentes combinaisons de zones de recouvrement de la Sales Tax et de groupes de taxe afin d'établir les taux de taxe. Pour chaque juridiction fiscale, nous vous recommandons de configurer un groupe fiscal pour la taxe de vente normale, un autre groupe fiscal pour les articles ou les services qui ne sont pas soumis à la taxe et un groupe fiscal supplémentaire pour chaque type d'article ou de service traité avec un taux de taxe de vente différent dans cette juridiction fiscale.  

Aux États-Unis, lorsque vous vendez à un client dans un magasin où vous n'avez pas de *situs*(ou un magasin légal dans cet état) vous ne percevez pas la Sales Tax. Pour les magasins dans lesquels vous n'avez pas de situs, assurez-vous que la valeur des champs **Taxe inférieure minimum** and **Taxe supérieure maximum** est égale à 0,00.  

## <a name="see-also"></a>Voir aussi
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Taxe sur les ventes et taxe sur les biens et les services au Canada](ca-finance-tax.md)  
[Configuration simplifiée de la Sales Tax](https://madeira.microsoft.com/blog/sales-tax-setup-made-easy)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

