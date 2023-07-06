---
title: Déclaration TPS/TVH au Canada
description: En savoir plus sur la façon de déclarer la taxe de vente et la taxe sur les biens et les services au Canada.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'sales tax, local'
ms.date: 06/25/2021
ms.author: edupont
---
# <a name="reporting-goodsservices-tax-and-harmonized-sales-tax-in-canada"></a><a name="reporting-goodsservices-tax-and-harmonized-sales-tax-in-canada"></a><a name="reporting-goodsservices-tax-and-harmonized-sales-tax-in-canada"></a>Déclaration de la taxe sur les biens/services et de la taxe de vente harmonisée au Canada

Au Canada, si un fournisseur n'a pas de présence commerciale dans la province dans laquelle les achats sont effectués, le fournisseur facture la taxe sur les biens et des services (Goods and Services Tax - TPS) ou la taxe de vente harmonisée (Harmonized Sales Tax - TVH) uniquement. Toutefois, si la province applique une taxe de vente provinciale (Provincial Sales Tax - TVQ), l'acheteur doit tout de même calculer le montant de la TVQ et le payer directement à la province. Lorsqu'un code zone de recouvrement provincial est sélectionné, [!INCLUDE[prod_short](../../includes/prod_short.md)] l'utilise pour calculer la TVQ et la valider de sorte que l'impôt à payer apparaisse à la fois dans la comptabilité et dans les enregistrement d'écriture TVA. Par conséquent, le code région fiscale sélectionné ici doit uniquement inclure la TVQ et non la TPS.  

## <a name="submitting-the-gsthst-file"></a><a name="submitting-the-gsthst-file"></a><a name="submitting-the-gsthst-file"></a>Envoi du fichier TPS/TVH

Les informations sur les taxes dans les documents achat permettent de générer un transfert de fichier TPS/TVH en ligne que vous devez transmettre aux autorités fiscales. Ce champ inclut la taxe sur les biens et les services (TPS) et la taxe de vente harmonisée (TVH). Le fichier est créé dans un format de fichier .tax, qui peut être transféré en ligne. Utilisez le traitement en lot Transfert de fichiers par Internet TPS/TVH pour générer le fichier .tax.

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi

[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance-setup-finance.md)  
[Déclaration de la taxe de vente au Canada](ca-sales-tax.md)  
[Utiliser [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)
[Configurer des méthodes de calcul et de report pour la taxe sur la valeur ajoutée](../../finance-setup-vat.md)  


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
