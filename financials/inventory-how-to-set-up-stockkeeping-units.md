---
title: "Procédure : configurer des unités de stock | Microsoft Docs"
description: "Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/23/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 2c13559bb3dc44cdb61697f5135c5b931e34d2a8
ms.openlocfilehash: e5ac1c791b10c26a3cecd20711e7899bb7eaee3c
ms.contentlocale: fr-ca
ms.lasthandoff: 09/22/2017

---
# Comment configurer des points de stock
Vous pouvez utiliser des unités de stock pour enregistrer des informations relatives à vos articles pour un code d'emplacement ou variante donné.  

 Les points de stock représentent un supplément des fiches article. Ils ne les remplacent pas, bien qu'ils soient liés à ces documents. Les unités de stock vous permettent de différencier des informations relatives à un article pour un emplacement donné, comme un entrepôt ou un centre de distribution, ou une variante donnée, comme plusieurs numéros de tablette et plusieurs informations de réapprovisionnement, pour un même article.  

## Pour configurer une unité de stock  

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Unités de stock**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  
3.  Renseignez les champs de la fiche. Les champs suivants sont nécessaires : **N° article**, **Code d'emplacement** et/ou **Code variante**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

Après avoir configuré la première unité de stock pour un article, la case à cocher **Unité de stock existante** sur la fiche **Article** est activée.  

Pour créer plusieurs points de stock pour un article, utilisez le traitement par lots **Créer point de stock**.  

> [!NOTE]  
>  Les informations de la fiche **Point de stock** sont prioritaires par rapport à celles de la fiche **Article**.  

## Voir aussi  
[Procédure : enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

