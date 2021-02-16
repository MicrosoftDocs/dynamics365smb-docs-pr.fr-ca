---
title: Comment prélever pour la fabrication dans les configurations de stockage de base | Microsoft Docs
description: Lorsque l'emplacement entrepôt nécessite un traitement de prélèvement sans nécessiter de traitement de livraison, vous pouvez utiliser la page **Prélèvement inventaire** pour organiser et enregistrer le prélèvement des composantes.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: a4ea3530a51ff7919118f436a8060f97d4056637
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4759802"
---
# <a name="pick-for-production-or-assembly-in-basic-warehouse-configurations"></a>Prélever pour la fabrication ou l'assemblage dans les configurations de stockage de base.
Le mode de rangement de vos composantes de prélèvement pour les bons de production ou les ordres d'assemblage dépend de la configuration de l'entrepôt en tant qu'emplacement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Dans les configurations d'entrepôt de base où l'emplacement nécessite un traitement de prélèvement sans nécessiter de traitement de livraison, vous pouvez utiliser la page **Prélèvement inventaire** pour organiser et enregistrer le prélèvement des composantes.  

Dans les configurations d'entreposage de base, vous devez prélever les ordres d'assemblage à l'aide de la page **Mouvement d'inventaire**. Pour plus d’informations, voir [Traitement des articles assembler pour commande dans les prélèvements inventaire](warehouse-how-to-pick-for-production.md#handling-assemble-to-order-items-with-inventory-picks).  

Dans les configurations d'entrepôt avancées où les emplacements nécessitent des prélèvements et des livraisons, vous utilisez la page **Prélèvement entrepôt** pour ajouter des composantes aux bons de production ou aux ordres d'assemblage. Pour plus d'informations, consultez [Prélever pour la fabrication ou l'assemblage dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

> [!NOTE]  
>  Les importantes différences suivantes existent entre les prélèvements inventaire et les mouvements d'inventaire :  
>   
>  -   Lorsque vous enregistrez un prélèvement inventaire pour une opération interne, telle que la production, la consommation des composantes prélevées est reportée en même temps. Lorsque vous enregistrez un mouvement d'inventaire pour une opération interne, vous enregistrez seulement le mouvement physique des articles requis dans une zone de la zone Opérations sans reporter la consommation.  
> -   Lorsque vous utilisez des prélèvements stock, le champ **Code emplacement** sur une ligne composant d'ordre de fabrication. définit l'emplacement de *prélèvement* où les composants sont déduits lors de la validation de la consommation. Lorsque vous utilisez des mouvements de stock, le **Code emplacement** sur des lignes composant d'ordre cde fabrication définit l'emplacement *placement* dans la zone Opérations où l'employé du magasin doit placer les composants.  

Si une condition préalable du système pour le prélèvement ou le déplacement de composantes pour les documents d'origine est qu'une demande sortante d'entrepôt existe pour informer la zone d'entrepôt du besoin de composante. La demande désenlogement est créée lorsque l'état du bon de production devient Libéré ou lorsqu'un bon de production libéré est créé.  

## <a name="to-pick-components-in-basic-warehouse-configurations"></a>Pour prélever les composantes dans les configurations d'entrepôt de base
Dans les configurations d'entrepôt de base où l'emplacement est configuré pour utiliser uniquement le prélèvement, vous pouvez prélever des composantes pour les activités de production à l'aide de la page **Prélèvement inventaire**. Pour plus d'informations, voir [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvements inventaire**, puis sélectionnez le lien associé.  
2.  Pour accéder aux composantes du bon de production, choisissez l'action **Extraire documents sources**, puis sélectionnez le bon de production libéré.  
3.  Procédez au prélèvement, puis enregistrez les informations sur le prélèvement réel dans le champ **Qté prélevée**.  
4.  Lorsque les lignes sont prêtes à être reportées, choisissez l'action **Reporter**. Les écritures entrepôt nécessaires sont alors créées et la consommation des articles est reportée.  

Vous pouvez également créer un **Prélèvement de stock** directement à partir de la commande de fabrication lancée. Choisissez l'action **Créer prélèvement/rangement inventaire**, cochez la case **Créer prélèvement inventaire**, puis choisissez le bouton **OK**.

Vous pouvez également utiliser la page **Mouvement d'inventaire** pour déplacer des articles entre zones ad hoc, c'est-à-dire sans référence à un document origine.
Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

### <a name="handling-assemble-to-order-items-with-inventory-picks"></a>Traitement des articles à assembler pour commande dans les prélèvements stock
La page **Prélèvement inventaire** est également utilisée pour prélever et livrer les ventes lorsque les articles doivent être assemblés avant de pouvoir être livrés. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).

Les articles à livrer ne sont pas physiquement présents dans une zone tant qu'ils ne sont pas assemblés et reportés comme production dans une zone de la zone d'assemblage. Cela signifie que le prélèvement des articles à assembler pour commande en vue d'une livraison est effectué suivant un flux spécial. Depuis une zone, les employés d'entrepôt déposent des éléments d'assemblage sur le quai de livraison, puis reportent le prélèvement inventaire. Le prélèvement inventaire reporté reporte ensuite les résultats d'assemblage, la consommation de composantes et la livraison vente.

Vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour créer automatiquement un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage. Pour cela, vous devez sélectionner le champ **Créer des mouvements automatiquement** sur la page **Configuration d'assemblage**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Les lignes prélèvement inventaire pour les articles vente sont créées de différentes manières, selon qu'aucune, certaines ou toutes les quantités des lignes vente sont assemblées pour commande.

Dans les ventes courantes où vous utilisez des prélèvements inventaire pour reporter la livraison des quantités de l'inventaire, une ligne prélèvement inventaire, ou plusieurs si l'article se trouve dans différentes zones, sont créées pour chaque ligne document de vente. Cette ligne prélèvement est basée sur la quantité indiquée dans le champ **Qté à livrer**.

Dans les ventes assembler pour commande où la quantité totale de la ligne document de vente est assemblée pour commande, une ligne prélèvement inventaire est créée pour cette quantité. Cela signifie que la valeur du champ Quantité à assembler correspond à la valeur du champ **Qté à livrer**. Le champ **Assembler pour commande** est sélectionné sur la ligne.

Si un flux de résultats d'assemblage est configuré pour l'emplacement, la valeur du champ **Code de zone livr. ass. pr comm.** ou du champ **Code de zone depuis assemblage**, de cette commande, est insérée dans le champ **Code de zone** de la ligne prélèvement inventaire.

Si aucun code de zone n'est spécifié sur la ligne document de vente et qu'aucun flux résultats d'assemblage n'est configuré pour l'emplacement, le champ **Code de zone** de la ligne prélèvement inventaire est vide. L'employé d'entrepôt doit ouvrir la page **Contenus de la zone** et sélectionner la zone où les articles d'assemblage sont assemblés.

Dans les scénarios de combinaison, où une partie de la quantité doit d'abord être assemblée et l'autre doit être prélevée à partir de l'inventaire, un minimum de deux lignes prélèvement inventaire sont créées. Une ligne prélèvement est calculée pour la quantité à assembler pour commande. L'autre ligne prélèvement dépend de quelles zones peuvent satisfaire à la quantité restante en inventaire. Les codes de zone sur les deux lignes sont renseignés de différentes manières comme indiqué pour les deux types de vente différents respectivement. Pour plus d'informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="filling-the-consumption-bin"></a>Renseigner la zone consommation
Ce graphique indique comment le champ **Code de zone** sur les lignes composante bon de production est renseigné en fonction de la configuration de votre emplacement.

![Organigramme Flux de zone](media/binflow.png "BinFlow")

## <a name="see-also"></a>Voir aussi
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
