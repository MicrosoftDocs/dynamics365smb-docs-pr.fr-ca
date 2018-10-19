---
title: "Procédure : affecter des zones par défaut à des articles | Microsoft Docs"
description: "Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: e6c6c8a54ae638fa90bca94e43a38d120b5fd3f6
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="assign-default-bins-to-items"></a>Affecter des zones par défaut à des articles
Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article. Les emplacements par défaut sont définis dans la fenêtre **Contenu emplacement**.  

## <a name="to-assign-a-default-bin-to-an-item"></a>Pour affecter une zone par défaut à un article
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Feuille création contenu de la zone**, puis sélectionnez le lien associé.  
2.  Renseignez le code de zone et les informations article pour chaque zone que vous souhaitez définir par défaut pour un article. Veillez à sélectionner le champ **Valeur par défaut**.  
3.  Choisissez l'action **Créer contenu de la zone**. Des zones par défaut sont maintenant affectées à votre article.  

> [!NOTE]  
>  Lorsqu'un article est rangé, si une zone par défaut ne lui est pas affectée, la zone dans laquelle l'article est rangé est affectée par défaut.  

## <a name="to-change-the-default-bin-for-an-item"></a>Pour modifier la zone par défaut pour un article  
Vous pouvez être amené à modifier l'affectation de la zone par défaut pour un article ou à affecter une zone par défaut à un nouvel article.    
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Contenus de la zone**, puis sélectionnez le lien associé.  
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
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

