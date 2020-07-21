---
title: Comment prélever des articles avec les prélèvements stock | Microsoft Docs
description: Si un emplacement est configuré pour exiger un traitement des prélèvements mais pas un traitement des livraisons, vous utilisez les documents prélèvement inventaire pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents sources.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/25/2020
ms.author: sgroespe
ms.openlocfilehash: 7f8e7eb99e52fc3643028ca3c33ef178a3fde9f4
ms.sourcegitcommit: 63102669366eb26f9c32729848170bc2e5c4d6ae
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/25/2020
ms.locfileid: "3503783"
---
# <a name="pick-items-with-inventory-picks"></a>Prélever des articles avec les prélèvements stock

Lorsque votre emplacement est configuré pour exiger un traitement des prélèvements mais pas un traitement des livraisons, vous utilisez la page **Prélèvement inventaire** pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents origine. Le document source sortant peut être un document de vente, un retour achat, un transfert sortant ou un bon de production dont les composantes sont prêtes à être prélevées.

> [!NOTE]  
> Les composantes pour les commandes d'assemblage ne peuvent pas être prélevées ni reportées avec des prélèvements inventaire. À la place, utilisez la page **Mouvement d'inventaire**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).
>
> En cas de prélèvement et de livraison de quantités de lignes vente assemblées pour commande, vous devez suivre certaines règles en créant les lignes prélèvement inventaire. Pour plus d'informations, voir la section [Traitement des articles à assembler pour commande dans les prélèvements inventaire](#handling-assemble-to-order-items-with-inventory-picks).  

Vous pouvez créer un prélèvement inventaire de trois manières :  

- Créez le prélèvement en deux étapes en demandant d'abord un prélèvement inventaire en libérant le document source. Cela permet de signaler à l'entrepôt que le document d'origine est prêt pour le prélèvement. Le prélèvement inventaire peut ensuite être créé sur la page **Prélèvement inventaire** sur la base du document origine.  
- Créez le prélèvement inventaire directement à partir du document source proprement dit.  
- Vous pouvez créer des prélèvements inventaire pour plusieurs documents simultanément en utilisant le traitement en lot.  

## <a name="to-request-an-inventory-pick-by-releasing-the-source-document"></a>Pour demander un prélèvement inventaire en libérant le document source

Pour les documents de vente, les retours achat et les ordres de transfert sortants, vous créez la demande entrepôt en libérant l'ordre. La section suivante décrit comment procéder à partir d'un document de vente.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Sélectionnez le document de vente que vous voulez libérer, puis sélectionnez l'action **Libérer**.

Pour les bons de production, vous créez automatiquement la demande entrepôt pour le prélèvement de composantes, appelé *purge* lorsque l'état du bon de production passe à **Libéré** ou lorsque le bon de production libéré est créé. Pour plus d'informations, voir [Prélever pour la fabrication ou l'assemblage](warehouse-how-to-pick-for-production.md).

Une fois la demande entrepôt créée, l'employé d'entrepôt affecté aux prélèvements des articles peut voir que le document source est prêt à être prélevé et peut créer un nouveau document prélèvement sur la base de la demande entrepôt.  

## <a name="to-create-an-inventory-pick-based-on-the-source-document"></a>Pour créer un prélèvement inventaire en fonction du document source

Maintenant que la demande est créée, l'employé d'entrepôt peut créer un nouveau prélèvement inventaire sur la base du document source libéré.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvements inventaire**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
    Assurez-vous que le champ **N°** du raccourci **Général** est rempli.
3. Dans le champ **Document origine**, sélectionnez le type de document origine relatif au prélèvement.  
4. Dans le champ **N° origine**, sélectionnez le document origine.  
5. Sinon, choisissez l'action **Extraire document source** pour sélectionner le document à partir de la liste des documents sources sortants prêts pour le prélèvement dans l'emplacement.  
6. Choisissez le bouton **OK** pour renseigner les lignes prélèvement en fonction du document origine sélectionné.  

## <a name="to-create-an-inventory-pick-from-the-source-document"></a>Pour créer un prélèvement inventaire à partir du document source

1. Dans le document source, qui peut être un document de vente, un retour achat, un ordre de transfert sortant ou un bon de production, choisissez l'action **Créer prélèvement/rangement inventaire**.
2. Cochez la case **Créer prélèvement inventaire**.  
3. Cliquez sur le bouton **OK**. Un nouveau prélèvement inventaire sera créé.

## <a name="to-create-multiple-inventory-picks-with-a-batch-job"></a>Pour créer plusieurs prélèvements inventaire avec un traitement en lot

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Créer prélèv./rangement inventaire**, puis sélectionnez le lien associé.  
2. Sur le raccourci **Demande entrepôt**, utilisez les champs **Document origine** et **N° origine** pour opérer un filtrage sur certains types de documents ou des plages de numéros de document. Par exemple, vous pouvez créer des prélèvements uniquement pour des documents de vente.  
3. Sur le raccourci **Options**, cochez la case **Créer prélèvement inventaire**.
4. Cliquez sur le bouton **OK**. Les prélèvements stock spécifiés sont créés.

> [!NOTE]  
> En cas de prélèvement et de livraison de quantités de lignes vente assemblées pour commande, vous devez suivre certaines règles en créant les lignes prélèvement inventaire. Pour plus d'informations, voir la section [Traitement des articles à assembler pour commande dans les prélèvements inventaire](#handling-assemble-to-order-items-with-inventory-picks).  
>
> Dans les configurations d'entrepôt de base, les articles qui sont assemblés aux documents de vente sont prélevés à partir du document de vente associé, comme expliqué dans cette rubrique. Pour plus d'informations, voir la section [Traitement des articles à assembler pour commande dans les prélèvements inventaire](#handling-assemble-to-order-items-with-inventory-picks).  

## <a name="to-record-the-inventory-picks"></a>Pour enregistrer les prélèvements stock

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvement inventaire**, puis sélectionnez le lien associé.  
2. Dans le champ **Code de zone** sur les lignes prélèvement, la zone à partir de laquelle les articles doivent être prélevés est proposée sur la base d'une zone par défaut de l'article. Vous pouvez modifier la zone sur cette page, si nécessaire.  
3. Exécutez le prélèvement et saisissez les informations pour la quantité effectivement rangée dans le champ **Quantité à traiter**.

    S'il s'avère nécessaire de prélever les articles d'une ligne dans plusieurs zones, notamment parce qu'ils ne sont pas disponibles dans la zone indiquée, alors utilisez la fonction **Éclater ligne** sur le raccourci **Lignes**. Pour plus d'informations sur l'éclatement des lignes, voir [Répartir des lignes activité entrepôt](warehouse-how-to-split-warehouse-activity-lines.md).  
4. Une fois le prélèvement exécuté, choisissez l'action **Reporter**.  

Le processus de report reporte la livraison des lignes du document source qui ont été prélevées, ou la consommation dans le cas de bons de production. Si l'emplacement utilise des zones, le report crée également des écritures entrepôt pour reporter les modifications apportées aux quantités de la zone.  

## <a name="to-delete-inventory-pick-lines"></a>Pour supprimer des lignes prélèvement inventaire

Si les articles du prélèvement inventaire ne sont pas disponibles, vous pouvez supprimer ces lignes prélèvement inventaire après report, puis supprimer le document prélèvement inventaire. Le document source, par exemple un document de vente ou un bon de production, aura d'autres articles à prélever qui peuvent être obtenus via un nouveau prélèvement inventaire ultérieurement lorsque les articles sont disponibles.  

> [!WARNING]  
> Ce traitement n'est pas possible si des numéros de série/lot sont spécifiés dans le document origine. Par exemple, si une ligne document de vente contient un numéro de série/lot, cette spécification traçabilité sera supprimée si une ligne prélèvement inventaire du numéro de série/lot est supprimée.  
>
> Si des numéros de série/lot de lignes prélèvement inventaire ne sont pas disponibles, vous ne devez pas supprimer les lignes concernées. Au lieu de cela, vous devez remettre le champ **Qté à gérer** à zéro, reporter les prélèvements réels, puis supprimer le document prélèvement inventaire. De cette manière, vous pourrez recréer les lignes prélèvement inventaire de ces numéros de série/lot à partir du document de vente ultérieurement.  

## <a name="handling-assemble-to-order-items-with-inventory-picks"></a>Traitement des articles à assembler pour commande dans les prélèvements stock

La page **Prélèvement inventaire** est également utilisée pour prélever et livrer les ventes lorsque les articles doivent être assemblés avant de pouvoir être livrés. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).

Les articles à livrer ne sont pas physiquement présents dans une zone tant qu'ils ne sont pas assemblés et reportés comme production dans une zone de la zone d'assemblage. Cela signifie que le prélèvement des articles à assembler pour commande en vue d'une livraison est effectué suivant un flux spécial. Depuis une zone, les employés d'entrepôt déposent des éléments d'assemblage sur le quai de livraison, puis reportent le prélèvement inventaire. Le prélèvement inventaire reporté reporte ensuite les résultats d'assemblage, la consommation de composantes et la livraison vente.

Vous pouvez configurer [!INCLUDE[d365fin](includes/d365fin_md.md)] pour créer automatiquement un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage. Pour cela, vous devez sélectionner le champ **Créer des mouvements automatiquement** sur la page **Configuration d'assemblage**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Les lignes prélèvement inventaire pour les articles vente sont créées de différentes manières, selon qu'aucune, certaines ou toutes les quantités des lignes vente sont assemblées pour commande.

Dans les ventes courantes où vous utilisez des prélèvements inventaire pour reporter la livraison des quantités de l'inventaire, une ligne prélèvement inventaire, ou plusieurs si l'article se trouve dans différentes zones, sont créées pour chaque ligne document de vente. Cette ligne prélèvement est basée sur la quantité indiquée dans le champ **Qté à livrer**.

Dans les ventes assembler pour commande où la quantité totale de la ligne document de vente est assemblée pour commande, une ligne prélèvement inventaire est créée pour cette quantité. Cela signifie que la valeur du champ Quantité à assembler correspond à la valeur du champ **Qté à livrer**. Le champ **Assembler pour commande** est sélectionné sur la ligne.

Si un flux de résultats d'assemblage est configuré pour l'emplacement, la valeur du champ **Code de zone livr. ass. pr comm.** ou du champ **Code de zone depuis assemblage**, de cette commande, est insérée dans le champ **Code de zone** de la ligne prélèvement inventaire.

Si aucun code de zone n'est spécifié sur la ligne document de vente et qu'aucun flux résultats d'assemblage n'est configuré pour l'emplacement, le champ **Code de zone** de la ligne prélèvement inventaire est vide. L'employé d'entrepôt doit ouvrir la page **Contenus de la zone** et sélectionner la zone où les articles d'assemblage sont assemblés.

Dans les scénarios de combinaison, où une partie de la quantité doit d'abord être assemblée et l'autre doit être prélevée à partir de l'inventaire, un minimum de deux lignes prélèvement inventaire sont créées. Une ligne prélèvement est calculée pour la quantité à assembler pour commande. L'autre ligne prélèvement dépend de quelles zones peuvent satisfaire à la quantité restante en inventaire. Les codes de zone sur les deux lignes sont renseignés de différentes manières comme indiqué pour les deux types de vente différents respectivement. Pour plus d'informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et Assembler pour stock](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="see-also"></a>Voir aussi

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base](walkthrough-picking-and-shipping-in-basic-warehousing.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
