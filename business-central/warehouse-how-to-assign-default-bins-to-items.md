---
title: 'Procédure : affecter des zones par défaut à des articles | Microsoft Docs'
description: Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 6777f71e35792b4bb4dfb44d1267b59b90109438
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5771889"
---
# <a name="assign-default-bins-to-items"></a>Affecter des zones par défaut à des articles
Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article. Les zones par défaut sont définies sur la page **Contenu de la zone**.  

## <a name="to-assign-a-default-bin-to-an-item"></a>Pour affecter une zone par défaut à un article
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Feuille de création du contenu de la zone**, puis sélectionnez le lien associé.  
2.  Renseignez le code de zone et les informations article pour chaque zone que vous souhaitez définir par défaut pour un article. Veillez à sélectionner le champ **Valeur par défaut**.  
3.  Choisissez l'action **Créer contenu de la zone**. Des zones par défaut sont maintenant affectées à votre article.  

> [!NOTE]  
>  Lorsqu'un article est rangé, si une zone par défaut ne lui est pas affectée, la zone dans laquelle l'article est rangé est affectée par défaut.  

## <a name="to-change-the-default-bin-for-an-item"></a>Pour modifier la zone par défaut pour un article  
Vous pouvez être amené à modifier l'affectation de la zone par défaut pour un article ou à affecter une zone par défaut à un nouvel article.    
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Contenus de la zone**, puis sélectionnez le lien associé.  
2.  Dans le champ **Filtre magasin**, sélectionnez le code emplacement approprié.  
3.  Recherchez l'écriture indiquant le contenu de la zone par défaut pour cet article et désactivez la case à cocher **Zone par déf.**.  
4.  Recherchez la ligne contenu de la zone que vous souhaitez configurer comme étant la nouvelle zone par défaut. Cochez la case **Zone par défaut**.  

> [!NOTE]  
>  Lorsqu'un article est rangé pour la première fois, et si une zone par défaut ne lui est pas affectée, le système lui affecte comme zone par défaut celle dans laquelle l'article est rangé.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]