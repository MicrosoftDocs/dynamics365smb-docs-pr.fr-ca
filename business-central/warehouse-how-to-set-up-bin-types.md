---
title: Configurer des types de zone
description: Affectez des types et des activités de flux de base aux zones et, ce faisant, définissez la manière dont les zones sont utilisées pour des activités entrepôt particulières.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 7367
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: f45908cf5a1d4352039cf83ab1db2719caca8a53
ms.sourcegitcommit: cdb57f14960f58b1d36a1b373fbf35dfed5fad9e
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/23/2022
ms.locfileid: "8334600"
---
# <a name="set-up-bin-types"></a>Configurer des types de zone
Vous pouvez diriger la circulation des articles vers les emplacements que vous avez définis pour des activités entrepôt particulières. Vous attribuez à chaque zone ses activités de flux de base, et définissez de cette façon la manière dont une zone est utilisée, en lui affectant un type.  

Il existe six types. Votre entrepôt peut fonctionner avec la totalité de ces six types de zones, mais vous pouvez également décider de n'utiliser que les types RÉCEPT., RANGPRÉLÈV., LIVR. et CQ. Ces quatre types de zones permettent à des propositions relatives à la prise en charge du flux des articles d'être effectuées et vous permettent d'enregistrer les différences d'inventaire.  

## <a name="to-set-up-the-bin-types-you-want-to-use"></a>Pour configurer les types de zones que vous souhaitez utiliser  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Types de zone**, puis sélectionnez le lien associé.  
2.  Sur la page **Types zone**, créez un code à 10 caractères pour chaque type de zone.  
3.  Sélectionnez les activités qui peuvent être effectuées avec chaque type de zone.  

> [!NOTE]  
>  Les types de zone ne sont applicables qu'en cas d'utilisation d'un prélèvement et d'un rangement suggérés pour votre emplacement.  

Le type de zone ne définit que la manière dont une zone donnée est utilisée lors du traitement du flux d'articles dans l'entrepôt. Vous pouvez toujours remplacer les propositions d'un document entrepôt, et vous pouvez également placer ou prendre des articles dans une zone en réalisant un mouvement entrepôt.  

Les types de zones que vous pouvez créer sont répertoriés ci-après.  

|Type zone|Description|  
|------------------|---------------------------------------|  
|RECEPT.|Les articles enregistrés en tant que réceptions reportées, mais pas encore rangées.|  
|LIVR.|Les articles prélevés pour des lignes livraison entrepôt, mais pas encore reportés en tant qu'articles livrés.|  
|RANG.|Généralement, les articles devant être stockés dans de grandes unités de mesure, mais auxquels vous ne souhaitez pas accéder à des fins de prélèvement. Étant donné que ces zones ne sont pas utilisées pour le prélèvement, que ce soit pour des bons de production ou des livraisons, l'utilisation d'une zone de type Rangement risque d'être limitée, mais ce type de zone peut se révéler utile si vous avez acheté une grande quantité d'articles. La priorité des zones de ce type doit toujours être peu élevée. Ainsi, lors du rangement des articles reçus, ce sont les zones RANGPRÉLÈV. de priorité plus élevée associés à l'article concerné qui sont rangées en premier lieu. Lorsque vous utilisez ce type de zone, vous devez régulièrement procéder au réapprovisionnement des zones, afin que les articles stockés dans ces zones puissent également être disponibles dans les zones de type RANGPRÉLÈV. ou PRÉLÈV.|  
|PRELEV.|Les articles devant être utilisés uniquement pour des prélèvements (par exemple, des articles dont la date d'expiration est proche et que vous avez déplacés dans ce type de zone). Attribuez un classement élevé à ces zones afin qu'elles soient proposées en premier pour le prélèvement.|  
|RGMT/PRLVT|Articles dans des zones qui sont proposés à la fois pour les fonctions de rangement et de prélèvement. Les emplacements de ce type ont vraisemblablement un classement différent. Vous pouvez configurer vos zones de stockage en vrac comme ce type de zone avec un classement peu élevé par rapport à vos zones prélèvement ordinaires ou vos zones prélèvement en aval.|  
|CQ|Cet emplacement est utilisé pour des ajustements stock, si vous le spécifiez sur la fiche magasin dans le champ **Code empl. ajustement**. Vous pouvez également configurer des emplacements de ce type pour des articles défectueux ou en cours de contrôle. Vous pouvez déplacer des articles vers ce type de zone afin que le flux habituel des articles ne puisse pas y accéder.<br /><br /> **NOTE :** contrairement à tous les autres types d'emplacement, les cases à cocher pour le traitement des articles sont toutes désactivées par défaut pour le type **CQ**. Cela signifie que tout contenu que vous placez dans une zone de type CQ est exclu des flux d'articles.|  

## <a name="see-also"></a>Voir aussi
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
