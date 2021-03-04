---
title: Taxe de vente au Canada| Microsoft Docs
description: En savoir plus sur la taxe de vente et la taxe sur les biens et les services au Canada.
services: project-madeira
documentationcenter: ''
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: sales tax, local
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 08b88f327089d11cf55a0caef7be986ddd75d998
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4749690"
---
# <a name="reporting-sales-tax-and-goodsservices-tax-in-canada"></a>Déclaration de la taxe de vente et taxe sur les biens/services au Canada
Au Canada, si un fournisseur n'a pas de présence commerciale dans la province dans laquelle les achats sont effectués, le fournisseur facture la taxe sur les biens et des services (Goods and Services Tax - GST) ou la taxe de vente harmonisée (Harmonized Sales Tax - HST) uniquement. Toutefois, si la province applique une taxe de vente provinciale (Provincial Sales Tax - PST), l'acheteur doit tout de même calculer le montant de la PST et le payer directement à la province. Lorsqu'un code zone de recouvrement provincial est sélectionné, [!INCLUDE[prod_short](../../includes/prod_short.md)] l'utilise pour calculer la PST et la valider de sorte que l'impôt à payer apparaisse à la fois dans la comptabilité et dans les enregistrement d'écriture TVA. Par conséquent, le code région fiscale sélectionné ici doit uniquement inclure la PST et non la GST.  

## <a name="submitting-the-gsthst-file"></a>Envoi du fichier GST/HST
Les informations sur les taxes dans les documents achat permettent de générer un transfert de fichier GST/HST en ligne que vous devez transmettre aux autorités fiscales. Ce champ inclut la taxe sur les biens et les services (GST) et la taxe de vente harmonisée (HST). Le fichier est créé dans un format de fichier .tax, qui peut être transféré en ligne.  

## <a name="see-also"></a>Voir aussi
[Fonctionnalités locales Canada](canada-local-functionality.md)  
[Finance](../../finance.md)  
[Configuration de Finance](../../finance-setup-finance.md)  
[Déclaration de la taxe de vente au Canada](ca-sales-tax.md)  
[Utilisation de [!INCLUDE[prod_short](../../includes/prod_short.md)]](../../ui-work-product.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]