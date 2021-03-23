---
title: 'Procédure : vendre des articles en inventaire dans des flux assembler pour commande | Microsoft Docs'
description: Si l'article est configuré pour la fiche d'assemblage pour commande, le processus par défaut de document de vente considère que l'article n'est pas en inventaire et doit être assemblé pour ce document de vente spécifique. Par conséquent, un ordre d'assemblage lié est automatiquement créé lorsque vous ajoutez l'article à une ligne document de vente.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: kit, kitting
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 929f4ff71cf0f5a1c2365b72f6d639e8c7be15c0
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5386609"
---
# <a name="sell-inventory-items-in-assemble-to-order-flows"></a>Vente d'articles d'inventaire dans des flux à assembler pour commande
Si le champ **Politique d'assemblage** de la fiche article d'un élément d'assemblage indique **Assembler pour commande**, le processus par défaut de document de vente considère que l'article n'est pas en inventaire et doit être assemblé pour ce document de vente spécifique. Par conséquent, un ordre d'assemblage lié est automatiquement créé lorsque vous ajoutez l'article à une ligne document de vente. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md). Toutefois, si une partie de la quantité sur commande vente est déjà disponible en stock, alors vous pouvez diminuer la quantité d'ordre d'assemblage en changeant le champ **Quantité à assembler pour commande** de la ligne commande vente.  

Ce scénario est rare parce que les articles à assembler pour commande sont toujours censés être personnalisés, et il est peu probable qu'ils soient en inventaire dans la configuration qui est demandée par un autre client. Néanmoins, si une compagnie a des quantités assembler pour commande en inventaire à cause de retours ou d'annulations de commande, ces quantités doivent être prélevées et vendues avant que de nouvelles soient assemblées.  

> [!NOTE]  
>  Aucune fonctionnalité n'existe sur les commandes vente qui vous alerte automatiquement ou vous aide à déduire les quantités d'ordre d'assemblage qui sont déjà disponibles. Au lieu de cela, vous devez contrôler les informations de disponibilité, par exemple dans le récapitulatif **Détails ligne vente**.  

Une fonctionnalité similaire est disponible lorsque vous vendez des éléments d'assemblage de l'inventaire et qu'une partie ou l'ensemble de la quantité n'est pas disponible et peut être fournie dans un ordre d'assemblage. Pour plus d’informations, voir [Vente simultanée d'articles à assembler pour commande et d'articles d'inventaire](assembly-how-to-sell-assemble-to-order-items-and-inventory-items-together.md).  

> [!NOTE]  
>  Certaines règles s'appliquent au champ **Qté à livrer** sur les lignes document de vente qui contiennent une combinaison de quantités assembler pour commande et de quantités inventaire. Pour plus d'informations, voir la section Scénarios de combinaison dans [Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md).  

Dans cette procédure, vous remplacez les quantités à assembler pour commande par les quantités en inventaire sur une ligne document de vente. Les étapes comprennent la vérification des disponibilités existantes, la détection de la quantité de l'ordre d'assemblage associé, puis la réservation de la quantité en inventaire pour s'assurer qu'elle est prélevée et livrée pour la commande.  

## <a name="to-sell-inventory-items-in-assemble-to-order-flows"></a>Vendre des articles en inventaire dans des flux assembler pour commande  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Créez un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  
3.  Sur une ligne document de vente pour un article à assembler pour commande, dans le champ **Quantité**, entrez la quantité demandée.  
4.  Dans le récapitulatif **Détails ligne vente**, déterminez si une partie ou la totalité de la quantité demandée est disponible.  
5.  Dans le champ **Quantité à assembler pour commande**, déduisez la quantité disponible de manière à ce que seule la quantité indisponible soit assemblée à la commande. Le champ **Quantité réservée** est diminué en conséquence pour refléter que la relation ordre pour ordre, ou la réservation, s'applique uniquement à la quantité à assembler.  
6.  Sur le raccourci **Lignes**, choisissez **Fonctions**, puis choisissez l'action **Réserver**.  
7.  Sur la page **Réservation**, sélectionnez la ou les lignes d'écriture article qui contiennent des quantités disponibles, sélectionnez **Réserver à partir de la ligne courante**, puis sélectionnez le bouton **OK**.  

    Sur la page **Document de vente**, le champ **Quantité réservée** indique maintenant que l'ensemble de la quantité ligne commande est réservé. Le champ **Quantité à assembler pour commande** indique toujours la sous-quantité qui doit être assemblée.  

8.  Libérez le document de vente pour prélever les articles en inventaire et assembler les articles indisponibles. Pour plus d'informations, voir [Assembler des articles](assembly-how-to-assemble-items.md).  

> [!CAUTION]  
>  Le champ **Code de zone** du document de vente peut être prérempli en fonction du champ **Code zone livr. ass. pr comm.** ou du champ **Code zone depuis assemblage** de la fiche emplacement. Dans ce cas, le champ **Code de zone** de la ligne document de vente peut être incorrect dans cette combinaison de quantités assembler pour commande et assembler pour stock. Il est judicieux de consulter le champ **Code emplacement** et de s'assurer que le placement fonctionne pour toutes les quantités. Sinon, entrez les deux quantités différentes sur des lignes document de vente distinctes.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Réserver des articles](inventory-how-to-reserve-items.md)  
[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Inventaire](inventory-manage-inventory.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]