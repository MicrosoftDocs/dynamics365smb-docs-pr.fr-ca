---
title: Création d'ordres d'assemblage permanents
description: Créez des commandes permanentes ventes pour les éléments d'assemblage personnalisés avant d'effectuer régulièrement les documents de vente réels en fonction de l'entente commande permanente.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: kit, kitting
ms.search.form: 900, 901, 902, 903, 904, 907, 910, 916, 920, 921, 922, 923, 940, 941, 942, 930, 931, 932, 914, 915, 905
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 45550b0aa5c3d55b8988b597ebef038df108a7a2
ms.sourcegitcommit: 5a02f8527faecdffcc54f9c5c70cefe8c4b3b3f4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/04/2022
ms.locfileid: "8384003"
---
# <a name="create-blanket-assembly-orders"></a>Création d'ordres d'assemblage permanents
Vous pouvez utiliser la gestion d'assemblage pour personnaliser un élément d'assemblage sur la demande d'un client au cours du processus de vente. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).  

 Comme pour tout autre type d'article, vous pouvez également créer des commandes permanentes ventes pour les éléments d'assemblage personnalisés avant de créer périodiquement les documents de vente réels en fonction de l'entente commande permanente. Ce processus implique plusieurs étapes supplémentaires lorsque vous le comparez à la création d'une commande permanente ventes classique, et il utilise une variante d'un ordre d'assemblage associé, qui est un ordre d'assemblage permanent.

> [!NOTE]  
>  Comme toutes les commandes permanentes, les quantités des commandes permanentes d'assemblage ne sont que des prévisions et ne sont pas opérationnelles avant d'être converties en ordres d'assemblage réels. Par conséquent, la fonctionnalité commande, comme le calcul de disponibilité, la réservation et la traçabilité des articles, n'est pas active sur les ordres d'assemblage permanents.  

## <a name="to-create-a-blanket-assembly-order-for-an-assemble-to-order-item"></a>Pour créer un ordre d'assemblage permanent pour un article à assembler pour commande  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente permanents**, puis sélectionnez le lien associé.  
2. Créez une commande permanente ventes avec une ligne pour un élément d'assemblage. Pour plus de détails, reportez-vous à la rubrique [Créer des commandes permanentes ventes](sales-how-to-create-blanket-sales-orders.md).  
3. Dans le champ **Quantité à assembler pour commande** de la ligne d'ordre d'assemblage permanent, saisissez la quantité entière.

    > [!NOTE]  
    >  Vous ne devez pas créer d'ententes commande permanente pour une quantité partielle. Par conséquent, vous devez entrer la même quantité que vous avez saisie dans le champ **Quantité** de la ligne commande permanente ventes.  

4. Choisissez l'action **Assembler pour commande**, puis choisissez l'action **Lignes Assembler pour commande**. Sinon, choisissez le champ **Quantité à assembler pour commande** sur la ligne.  
5. Sur la page **Lignes Assembler pour commande**, vérifiez ou modifiez les lignes d'ordre d'assemblage en fonction de l'entente commande permanente que vous avez passée avec le client. Des informations supplémentaires sont disponibles en choisissant **Afficher document** pour ouvrir l'ordre d'assemblage permanent complet. Vous ne pouvez pas modifier le contenu de la plupart des champs, et vous ne pouvez pas reporter.  
6. Lorsque vous avez ajusté les lignes d'ordre d'assemblage en fonction de l'entente commande permanente, fermez la page **Lignes Assembler pour commande** pour revenir à la page **Commande permanente ventes**.  
7. Lorsque le client souhaite créer un document de vente en fonction de la commande permanente ventes convenue, créez un document de vente pour l'élément ou les éléments d'assemblage convenus. Pour plus de détails, reportez-vous à la rubrique [Créer des commandes permanentes ventes](sales-how-to-create-blanket-sales-orders.md).

L'ordre d'assemblage permanent associé et toutes les personnalisations sont liées à ce nouveau document de vente pour préparer l'assemblage de l'article ou des articles à vendre.  

## <a name="see-also"></a>Voir aussi
[Créer des commandes permanentes ventes](sales-how-to-create-blanket-sales-orders.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]