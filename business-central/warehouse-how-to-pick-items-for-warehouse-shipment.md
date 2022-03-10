---
title: Prélever des articles pour une livraison entrepôt
description: Découvrez comment utiliser les documents de prélèvement entrepôt pour créer et traiter les informations de prélèvement avant de reporter la livraison entrepôt.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 7335c388efc48f3c9a04238e7727817f28a7757f
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8128540"
---
# <a name="pick-items-for-warehouse-shipment"></a>Prélever des articles pour une livraison entrepôt
Lorsque l'emplacement est configuré pour exiger un traitement des prélèvements entrepôt ainsi qu'un traitement des livraisons entrepôt, vous pouvez utiliser les documents prélèvement entrepôt pour créer et traiter les informations de prélèvement avant le report de la livraison entrepôt.  

Vous ne pouvez pas créer de toutes pièces un document prélèvement entrepôt car une activité de prélèvement fait toujours partie d'un flux de travail, soit dans un scénario d'extraction, soit dans un scénario de déplacement.  

Vous pouvez créer des documents prélèvement entrepôt en mode extraction en ouvrant un document livraison entrepôt vide, détecter les documents sources qui sont libérés pour la livraison, puis créer des lignes prélèvement entrepôt pour ces livraisons. Vous pouvez utiliser les fonctions **Obtenir documents sources** ou **Utiliser filtre pour obtenir documents sources** pour détecter les documents sources qui sont prêts pour livraison.

Sinon, vous pouvez utiliser la page **Feuille prélèvement** pour extraire et créer les lignes prélèvement en mode lots. Pour plus d'informations, voir [Planifier des prélèvements dans des feuilles](warehouse-how-to-plan-picks-in-worksheets.md).  

Vous pouvez également créer des documents prélèvement entrepôt en mode pousser à partir de la page **Livraison entrepôt** en sélectionnant **Créer prélèvement**.  

> [!NOTE]  
>  Le prélèvement pour la livraison entrepôt des articles assemblés au document de vente en cours de livraison suit les mêmes étapes que les prélèvements entrepôt ordinaires pour la livraison, comme décrit dans cette rubrique. Cependant, le nombre de lignes prélèvement par quantité à livrer peut varier considérablement, car ce sont les composantes qui sont prélevées et non l'élément d'assemblage.  
>   
>  Les lignes prélèvement entrepôt sont créées suivant la valeur du champ **Quantité restante** sur les lignes de l'ordre d'assemblage associé à la ligne document de vente en cours de livraison. Ceci garantit le prélèvement de toutes les composantes en une seule tâche.  
>   
>  Pour plus d’informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les livraisons entrepôt ».  
>   
>  Pour plus d'informations sur le prélèvement de composantes pour les ordres d'assemblage en général, notamment les situations où l'élément d'assemblage n'est pas dû dans une livraison vente, voir [Prélever pour la fabrication ou l'assemblage](warehouse-how-to-pick-for-production.md).  

## <a name="to-pick-items-for-warehouse-shipment"></a>Pour prélever des articles pour une livraison entrepôt  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements**, puis choisissez le lien associé.  

    Si vous souhaitez travailler à un prélèvement particulier, sélectionnez-le dans la liste ou filtrez cette dernière afin de trouver les prélèvements qui vous ont été spécifiquement affectés. Ouvrez la fiche prélèvement.  
2.  Si le champ **Code utilisateur affecté** est vide, entrez votre code pour vous identifier si nécessaire.  
3.  Exécutez le prélèvement réel des articles.  

    Si l'entrepôt est configuré pour utiliser des zones, les zones par défaut des articles sont utilisées pour suggérer où prendre les articles. Les instructions apparaissent sur deux lignes distinctes, une ligne au moins pour chaque type d'action, prélèvement et placement.  

    Si l'entrepôt est configuré pour utiliser un prélèvement et rangement dirigé, le classement de zone est utilisé pour calculer les meilleures zones à partir desquelles prélever, et ces zones sont ensuite suggérées sur les lignes prélèvement. Les instructions apparaissent sur deux lignes distinctes, une ligne au moins pour chaque type d'action, prélèvement et placement.  

4.  Lorsque vous avez effectué le prélèvement et placé les articles dans la zone de livraison, choisissez l'action **Enregistrer prélèvement**.  

La personne responsable de la livraison peut alors apporter les articles au quai de chargement et reporter la livraison, dont le document origine lié, sur la page **Livraison entrepôt** . Pour plus d'informations, voir [Livrer des articles](warehouse-how-ship-items.md).   

En plus de prélever les documents sources, comme indiqué dans cette rubrique, vous pouvez prendre et placer les articles entre les zones sans faire référence aux documents sources. Pour plus d'informations, voir [Prélever et ranger sans document origine](warehouse-how-to-create-put-aways-from-internal-put-aways.md).  

## <a name="handling-assemble-to-order-items-in-warehouse-shipments"></a>Traitement des articles à assembler pour commande dans les livraisons entrepôt
Dans des scénarios assembler pour commande, le champ **Qté à livrer** sur les lignes livraison entrepôt est utilisé pour enregistrer le nombre d'unités assemblées. La quantité spécifiée est ensuite reportée comme résultat d'assemblage lorsque la livraison entrepôt est reportée.

Pour d'autres lignes livraison entrepôt, la valeur du champ **Qté à livrer** est zéro dès le début.

Lorsque les travailleurs chargés de l’assemblage finissent d’assembler les pièces ou l’ensemble de la quantité à assembler pour commande, ils l’enregistrent dans le champ **Qté à livrer** de la ligne livraison entrepôt et sélectionnent ensuite l'action **Reporter livraison**. Le résultat est que le résultat d'assemblage correspondant est reporté, y compris la consommation de composantes. Une livraison vente pour la quantité est reportée pour le document de vente.

À partir de l'ordre d'assemblage, vous pouvez choisir **Ligne livraison entrepôt Assembler pour commande** pour accéder à la ligne livraison entrepôt. Ceci peut être utile pour les travailleurs qui n'utilisent pas généralement la page **Livraison entrepôt**.

Une fois la livraison entrepôt reportée, divers champs de la ligne document de vente sont mis à jour pour afficher la progression dans l'entrepôt. Les champs suivants sont également mis à jour pour afficher le nombre de quantités à assembler pour commande qui restent à assembler et livrer :

- **Qté restante entrepôt ATO**
- **Qté restante entrepôt ATO (base)**

> [!NOTE]
> Dans les scénarios de combinaison, où une partie de la quantité doit d'abord être assemblée et l'autre doit être livrée à partir de l'inventaire, deux lignes livraison entrepôt sont créées. L'une est pour la quantité à assembler pour commande et l'autre est destinée à la quantité en inventaire.

> Dans ce cas, la quantité à assembler pour commande est traitée comme décrit dans cette rubrique, et la quantité en inventaire est traitée comme toute autre ligne livraison entrepôt normale. Pour plus d'informations sur les scénarios de combinaison, consultez [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]