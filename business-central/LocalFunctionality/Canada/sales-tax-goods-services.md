---
title: Déclaration GST/HST au Canada
description: En savoir plus sur la façon de déclarer la taxe de vente et la taxe sur les biens et les services au Canada.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales tax, local
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: 064c286fcb72aef9375c0e70ad302382b97c6756
ms.sourcegitcommit: 41876b559872fe7adbfa5b59a6e1a71dc907fb15
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/14/2021
ms.locfileid: "7921001"
---
# <a name="reporting-goodsservices-tax-and-harmonized-sales-tax-in-canada"></a>Déclaration de la taxe sur les biens/services et de la taxe de vente harmonisée au Canada

Au Canada, si un fournisseur n'a pas de présence commerciale dans la province dans laquelle les achats sont effectués, le fournisseur facture la taxe sur les biens et des services (Goods and Services Tax - GST) ou la taxe de vente harmonisée (Harmonized Sales Tax - HST) uniquement. Toutefois, si la province applique une taxe de vente provinciale (Provincial Sales Tax - PST), l'acheteur doit tout de même calculer le montant de la PST et le payer directement à la province. Lorsqu'un code zone de recouvrement provincial est sélectionné, [!INCLUDE[prod_short](../../includes/prod_short.md)] l'utilise pour calculer la PST et la valider de sorte que l'impôt à payer apparaisse à la fois dans la comptabilité et dans les enregistrement d'écriture TVA. Par conséquent, le code région fiscale sélectionné ici doit uniquement inclure la PST et non la GST.  

## <a name="submitting-the-gsthst-file"></a>Envoi du fichier GST/HST

Les informations sur les taxes dans les documents achat permettent de générer un transfert de fichier GST/HST en ligne que vous devez transmettre aux autorités fiscales. Ce champ inclut la taxe sur les biens et les services (GST) et la taxe de vente harmonisée (HST). Le fichier est créé dans un format de fichier .tax, qui peut être transféré en ligne. Utilisez le traitement en lot Transfert de fichiers par Internet GST/HST pour générer le fichier .tax.

## <a name="see-also"></a>Voir aussi

[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance-setup-finance.md)  
[Déclaration de la taxe de vente au Canada](ca-sales-tax.md)  
[Configurer des méthodes de calcul et de report de la taxe sur la valeur ajoutée](../../finance-setup-vat.md)  
[Utilisation de [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]