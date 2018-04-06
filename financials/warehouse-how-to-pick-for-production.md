---
title: "Comment prélever pour la fabrication dans les configurations de stockage de base | Microsoft Docs"
description: "Lorsque l'entrepôt appelle un traitement de prélèvement sans appeler de traitement d'expédition, vous pouvez utiliser la fenêtre **Prélèvement stock** pour organiser et enregistrer le prélèvement des composants."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/21/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 68702e384ea750535a8d7e5b83ee619856b6a34b
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="pick-for-production-or-assembly"></a>Prélever pour la fabrication et l'assemblage
Le mode de rangement de vos composantes de prélèvement pour les bons de production ou les ordres d'assemblage dépend de la configuration de l'entrepôt en tant qu'emplacement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Dans les configurations d'entrepôt de base où l'emplacement requiert un traitement de prélèvement sans nécessiter de traitement de livraison, vous pouvez utiliser la fenêtre **Prélèvement inventaire** pour organiser et enregistrer le prélèvement des composantes.  

Dans les configurations d'entrepôt de base, vous devez prélever les ordres d'assemblage dans la fenêtre **Mouvement d'inventaire**. Pour plus d'informations, reportez-vous à la section « Traitement d'un article à assembler pour commande dans les prélèvements stock » dans [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).  

Dans les configurations d'entrepôt avancées où les emplacements requièrent des prélèvements et des livraisons, vous utilisez la fenêtre **Prélèvement entrepôt** pour ajouter des composantes aux bons de production ou aux ordres d'assemblage.

> [!NOTE]  
>  Les importantes différences suivantes existent entre les prélèvements inventaire et les mouvements d'inventaire :  
>   
>  -   Lorsque vous enregistrez un prélèvement inventaire pour une opération interne, telle que la production, la consommation des composantes prélevées est reportée en même temps. Lorsque vous enregistrez un mouvement d'inventaire pour une opération interne, vous enregistrez seulement le mouvement physique des articles requis dans une zone de la zone Opérations sans reporter la consommation.  
> -   Lorsque vous utilisez des prélèvements stock, le champ **Code emplacement** sur une ligne composant d'ordre de fabrication. définit l'emplacement de *prélèvement* où les composants sont déduits lors de la validation de la consommation. Lorsque vous utilisez des mouvements de stock, le **Code emplacement** sur des lignes composant d'ordre cde fabrication définit l'emplacement *placement* dans la zone Opérations où l'employé du magasin doit placer les composants.  

Si une condition préalable du système pour le prélèvement ou le déplacement de composantes pour les documents d'origine est qu'une demande sortante d'entrepôt existe pour informer la zone d'entrepôt du besoin de composante. La demande désenlogement est créée lorsque l'état du bon de production devient Libéré ou lorsqu'un bon de production libéré est créé.  

## <a name="to-pick-components-in-basic-warehouse-configurations"></a>Pour prélever les composantes dans les configurations d'entrepôt de base
Dans les configurations d'entrepôt de base, dans lesquelles l'emplacement est configuré pour utiliser uniquement le prélèvement, vous pouvez prélever des composantes pour les activités de production à l'aide de la fenêtre **Prélèvement inventaire**. Pour plus d'informations, voir [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Prélèvements inventaire**, puis sélectionnez le lien associé.  
2.  Pour accéder aux composantes du bon de production, choisissez l'action **Extraire documents sources**, puis sélectionnez le bon de production libéré.  
3.  Procédez au prélèvement, puis enregistrez les informations sur le prélèvement réel dans le champ **Qté prélevée**.  
4.  Lorsque les lignes sont prêtes à être reportées, choisissez l'action **Reporter**. Les écritures entrepôt nécessaires sont alors créées et la consommation des articles est reportée.  

Vous pouvez également créer un **Prélèvement de stock** directement à partir de la commande de fabrication lancée. Choisissez l'action **Créer prélèvement/rangement inventaire**, cochez la case **Créer prélèvement inventaire**, puis choisissez le bouton **OK**.

Vous pouvez également utiliser la fenêtre **Mouvement d'inventaire** pour déplacer des articles entre zones ad hoc, c'est-à-dire sans référence à un document source.
Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

### <a name="handling-assemble-to-order-items-with-inventory-picks"></a>Traitement des articles à assembler pour commande dans les prélèvements stock
La fenêtre **Prélèvement inventaire** est également utilisée pour prélever et livrer les ventes lorsque les articles doivent être assemblés avant de pouvoir être livrés. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).

Les articles à livrer ne sont pas physiquement présents dans une zone tant qu'ils ne sont pas assemblés et reportés comme production dans une zone de la zone d'assemblage. Cela signifie que le prélèvement des articles à assembler pour commande en vue d'une livraison est effectué suivant un flux spécial. Depuis une zone, les employés d'entrepôt déposent des éléments d'assemblage sur le quai de livraison, puis reportent le prélèvement inventaire. Le prélèvement inventaire reporté reporte ensuite les résultats d'assemblage, la consommation de composantes et la livraison vente.

Vous pouvez configurer [!INCLUDE[d365fin](includes/d365fin_md.md)] pour créer automatiquement un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage. Pour cela, vous devez sélectionner le champ **Créer des mouvements automatiquement** dans la fenêtre **Configuration d'assemblage**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Les lignes prélèvement inventaire pour les articles vente sont créées de différentes manières, selon qu'aucune, certaines ou toutes les quantités des lignes vente sont assemblées pour commande.

Dans les ventes courantes où vous utilisez des prélèvements inventaire pour reporter la livraison des quantités de l'inventaire, une ligne prélèvement inventaire, ou plusieurs si l'article se trouve dans différentes zones, sont créées pour chaque ligne document de vente. Cette ligne prélèvement est basée sur la quantité indiquée dans le champ **Qté à livrer**.

Dans les ventes assembler pour commande où la quantité totale de la ligne document de vente est assemblée pour commande, une ligne prélèvement inventaire est créée pour cette quantité. Cela signifie que la valeur du champ Quantité à assembler correspond à la valeur du champ **Qté à livrer**. Le champ **Assembler pour commande** est sélectionné sur la ligne.

Si un flux de résultats d'assemblage est configuré pour l'emplacement, la valeur du champ **Code de zone livr. ass. pr comm.** ou du champ **Code de zone depuis assemblage**, de cette commande, est insérée dans le champ **Code de zone** de la ligne prélèvement inventaire.

Si aucun code de zone n'est spécifié sur la ligne document de vente et qu'aucun flux résultats d'assemblage n'est configuré pour l'emplacement, le champ **Code de zone** de la ligne prélèvement inventaire est vide. L'employé d'entrepôt doit ouvrir la fenêtre **Contenu de la zone** et sélectionner la zone où les articles d'assemblage sont assemblés.

Dans les scénarios de combinaison, où une partie de la quantité doit d'abord être assemblée et l'autre doit être prélevée à partir de l'inventaire, un minimum de deux lignes prélèvement inventaire sont créées. Une ligne prélèvement est calculée pour la quantité à assembler pour commande. L'autre ligne prélèvement dépend de quelles zones peuvent satisfaire à la quantité restante en inventaire. Les codes de zone sur les deux lignes sont renseignés de différentes manières comme indiqué pour les deux types de vente différents respectivement. Pour plus d'informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="to-pick-components-in-advanced-warehouse-configurations"></a>Pour prélever les composantes pour les configurations d'entrepôt avancées
Dans les configurations d'entrepôt avancées, dans lesquelles l'emplacement est configuré pour utiliser le prélèvement ainsi que la livraison, vous pouvez prélever des composantes pour les activités de production et d'assemblage à l'aide de la fenêtre **Prélèvement entrepôt**. Pour plus d'informations, voir [Prélever des articles avec les prélèvements entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md).

Vous pouvez également utiliser la fenêtre **Feuille mouvement** pour déplacer des articles entre emplacements ad hoc, c'est-à-dire sans référence à un document origine. Pour plus d'informations, voir [Déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md).  

Vous ne pouvez pas créer de toutes pièces un document prélèvement entrepôt car une activité de prélèvement fait toujours partie d'un flux de travail, soit dans un scénario d'extraction, soit dans un scénario de déplacement.  

Vous pouvez créer le document prélèvement entrepôt par déplacement en sélectionnant l'action **Créer un prélèvement d'entrepôt** dans le document source, par exemple, un ordre d'assemblage ou une livraison entrepôt libérée. Pour plus d'informations, voir [Prélever des articles avec les prélèvements entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md).  

Sinon, vous pouvez créer le document prélèvement entrepôt par extraction à l'aide de la fenêtre **Feuille prélèvement** pour détecter les demandes de prélèvement, à la fois pour l'expédition et les opérations internes, puis créer les documents prélèvement entrepôt requis.  

La procédure suivante explique un scénario d'extraction dans lequel vous prélevez des composants d'un ordre de fabrication lancé via la fenêtre **Feuille prélèvement**. Cette procédure s'applique également aux ordres d'assemblage.  

Pour créer des demandes de prélèvement dans le cadre de scénarios d'extraction et de déplacement, il faut que les documents origine en question soient libérés. Libérez les documents origine des opérations internes en procédant comme suit.  

 |Document origine|Méthode de libération|  
 |---------------------|--------------------|  
 |Bon de production|Remplacez le type commande par un bon de production libéré.|  
 |Ordre d'assemblage|Remplacez l'état actuel par l'état Libéré.|  

## <a name="to-pick-components-using-the-pick-worksheet"></a>Pour prélever des composants à partir des feuilles prélèvement  

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille prélèvement**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Extraire documents entrepôt**, puis sélectionnez les lignes composante du bon de production libéré.  
3.  Vérifiez les lignes, triez-les pour assurer un prélèvement optimisé et, si nécessaire, combinez les avec d'autres lignes de la feuille pour utiliser au mieux la disponibilité de l'employé.  
4.  Choisissez l'action **Créer prélèvement**.  
5.  Définissez le mode de création des documents prélèvement entrepôt et la manière de trier les lignes prélèvement en renseignant les champs de la fenêtre **Créer prélèvement** .  
6.  Cliquez sur le bouton **OK**.

Les documents prélèvement entrepôt sont maintenant créés avec des lignes prélèvement pour chaque composante devant servir à l'opération interne.

Si la zone Opérations internes (par exemple, un atelier de production) est configurée avec une zone par défaut pour les composantes à utiliser dans l'opération, ce code de zone est inséré dans les lignes Emplacement qui figurent sur le document prélèvement entrepôt pour indiquer aux magasiniers où placer les articles. Pour plus d'informations, voir [Configurer des entrepôts de base avec les zones d'opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md).

## <a name="filling-the-consumption-bin"></a>Renseignement de la zone consommation
Ce graphique indique comment le champ **Code de zone** sur les lignes composante bon de production est renseigné en fonction de la configuration de votre emplacement.

![Organigramme Flux d'emplacement](media/binflow.png "BinFlow")

## <a name="see-also"></a>Voir aussi
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

