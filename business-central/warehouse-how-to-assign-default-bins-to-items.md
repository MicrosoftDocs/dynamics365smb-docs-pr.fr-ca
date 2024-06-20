---
title: Affecter des zones par défaut à des articles
description: 'Si vous utilisez des zones dans un emplacement, l''affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.search.form: '7371, 7374, 7379'
ms.date: 06/25/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="assign-default-bins-to-items"></a>Affecter des zones par défaut à des articles
Si vous utilisez des zones dans un emplacement, l'affectation de zones par défaut à vos articles peut simplifier considérablement leur processus de livraison, de réception et de déplacement. Lorsqu'une zone par défaut est affectée à un article, cette zone est suggérée chaque fois que vous lancez une transaction pour cet article. Les zones par défaut sont définies sur la page **Contenu de la zone**.  

## <a name="to-assign-a-default-bin-to-an-item"></a>Pour affecter une zone par défaut à un article
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **euille de création du contenu de la zone**, et choisissez le lien associé.  
2.  Renseignez le code de zone et les informations article pour chaque zone que vous souhaitez définir par défaut pour un article. Veillez à sélectionner le champ **Valeur par défaut**.  
3.  Choisissez l'action **Créer contenu de la zone**. Des zones par défaut sont maintenant affectées à votre article.  

> [!NOTE]  
>  Lorsqu'un article est rangé, si une zone par défaut ne lui est pas affectée, la zone dans laquelle l'article est rangé est affectée par défaut.  

## <a name="to-change-the-default-bin-for-an-item"></a>Pour modifier la zone par défaut pour un article
Vous pouvez être amené à modifier l'affectation de la zone par défaut pour un article ou à affecter une zone par défaut à un nouvel article.
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Contenus de la zone**, puis sélectionnez le lien associé.  
2.  Dans le champ **Filtre magasin**, sélectionnez le code emplacement approprié.  
3.  Recherchez l'écriture indiquant le contenu de la zone par défaut pour cet article et désactivez la case à cocher **Zone par déf.**.  
4.  Recherchez la ligne contenu de la zone que vous souhaitez configurer comme étant la nouvelle zone par défaut. Cochez la case **Zone par défaut**.  

> [!NOTE]  
>  Lorsqu'un article est rangé pour la première fois, et si une zone par défaut ne lui est pas affectée, le système lui affecte comme zone par défaut celle dans laquelle l'article est rangé.  

## <a name="see-also"></a>Voir aussi
[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de Warehouse Management](warehouse-setup-warehouse.md) 
[Gestion des assemblages](assembly-assemble-items.md)
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
