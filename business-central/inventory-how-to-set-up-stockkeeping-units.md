---
title: 'Procédure : configurer des unités de stock | Microsoft Docs'
description: Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 18923708fdad1b88714d2dcb2c61bfd2e4259f4b
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5785732"
---
# <a name="set-up-stockkeeping-units"></a>Configurer des unités de stock
Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné.  

 Les points de stock représentent un supplément des fiches article. Ils ne les remplacent pas, bien qu'ils soient liés à ces documents. Les unités de stock vous permettent de différencier des informations relatives à un article pour un emplacement donné, comme un entrepôt ou un centre de distribution, ou une variante donnée, comme plusieurs numéros de tablette et plusieurs informations de réapprovisionnement, pour un même article.  

## <a name="to-set-up-a-stockkeeping-unit"></a>Pour configurer une unité de stock  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Unités de stock**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Renseignez les champs de la fiche. Les champs suivants sont nécessaires : **N° article**, **Code d'emplacement** et/ou **Code variante**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

Après avoir configuré la première unité de stock pour un article, la case à cocher **Unité de stock existante** sur la fiche **Article** est activée.  

Pour créer plusieurs points de stock pour un article, utilisez le traitement par lots **Créer point de stock**.  

> [!NOTE]  
>  Les informations de la fiche **Point de stock** sont prioritaires par rapport à celles de la fiche **Article**.

> [!Warning]
> Si l'unité de stock est expédiée à la fabrication, le champ **Coût standard** n'est pas utilisé lors de la facturation et de l'ajustement du coût réel de l'article fabriqué. Celui utilisé est plutôt le champ **Coût standard** de la fiche article sous-jacente. En outre, tous les écarts sont calculés par rapport aux coûts totaux de l'article.<br /><br />
> Étant donné qu'il n'est pas possible d'affecter les nomenclatures de production et l'itinéraire aux unités de stock, le calcul du coût unitaire et le calcul lié des coûts totaux ne sont également pas disponibles sur les unités de stock. Pour plus d'informations, voir [À propos du calcul des coûts standard](finance-about-calculating-standard-cost.md)

## <a name="see-also"></a>Voir aussi  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]