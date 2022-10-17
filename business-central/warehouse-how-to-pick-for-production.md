---
title: Prélever pour la fabrication, l’assemblage ou les tâches dans l’entrepôt de base
description: Lorsque l’entrepôt exige un traitement des prélèvements sans livraisons, utilisez la page Prélèvement inventaire pour enregistrer les composantes prélevées.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 08/02/2022
ms.author: bholtorf
ms.openlocfilehash: 859c70ebc51f2649000d41817d173292ed5b0870
ms.sourcegitcommit: b4da421c19c3aa3031b0344ec2829d2038be6642
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/03/2022
ms.locfileid: "9617887"
---
# <a name="pick-for-production-assembly-or-jobs-in-basic-warehouse-configurations"></a>Prélever pour la fabrication, l’assemblage ou les tâches dans les configurations de stockage de base

Le mode de rangement de vos composantes de prélèvement pour les bons de production ou les ordres d'assemblage dépend de la configuration de l'entrepôt en tant qu'emplacement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

## <a name="pick-for-production-in-basic-warehouse-configurations"></a>Prélever pour la fabrication dans les configurations de stockage de base

Si un emplacement exige un traitement de prélèvement, mais pas un traitement de livraison, vous pouvez utiliser la page **Prélèvement inventaire**. La page **Prélèvement inventaire** vous permet d’organiser et d’enregistrer le prélèvement des articles dont le mode de consommation est défini sur **Manuel**. Lorsque vous enregistrez un prélèvement inventaire, la consommation des composantes prélevées est reportée. Vous pouvez également utiliser un **Mouvement d’inventaire** avec une référence à un document source pour assigner les composantes avec la méthode de consommation définie sur **Manuel**, **Prélèvement + Aval**, **Prélèvement + Amont** aux bons de production.

Lorsque la production est intégrée dans les processus entrepôt via des zones ou des prélèvements ou rangements suggérés, les composantes sont consommées par la zone sur la ligne bon de production. Toutes les composantes requises doivent être disponibles dans cette zone. Autrement, le report manuel ou par consommation de la composante est annulé.

> [!NOTE]  
> Les prélèvements inventaire, les mouvements inventaire et les prélèvements entrepôt présentent les grandes différences suivantes :  
>
> - Lorsque vous enregistrez un prélèvement inventaire pour une opération interne, telle que la production, la consommation des composantes prélevées est reportée en même temps. Lorsque vous enregistrez un mouvement d'inventaire ou un prélèvement en entrepôt pour une opération interne, vous enregistrez seulement le mouvement physique des composantes requises dans une zone de l'espace Opérations sans reporter la consommation.  
> - Lorsque vous utilisez des prélèvements stock, le champ **Code emplacement** sur une ligne composant d'ordre de fabrication. définit l'emplacement de *prélèvement* où les composants sont déduits lors de la validation de la consommation. Lorsque vous utilisez des mouvements d'inventaire ou un prélèvement en entrepôt, le champ **Code de zone** sur les lignes composante bon de production définit la zone *placement* dans l'espace Opérations où l’employé d'entrepôt doit placer les composantes.  

Pour prélever ou déplacer des composantes pour des documents sources, une demande d’entrepôt sortante doit notifier la zone d’entrepôt du besoin de composante. La demande d’entrepôt sortante est créée lorsque vous procédez comme suit :

- Remplacez l'état d’un bon de production par Libéré.
- Créez un bon de production libéré.  

Les méthodes de consommation affectent également le flux des composantes en production. Pour plus d’informations, voir [Consommer en aval des composantes en fonction de la production réalisée](production-how-to-flush-components-according-to-operation-output.md). **Mouvement d’inventaire** avec des références au document source et **Prélèvement en entrepôt** ne peuvent pas être utilisés pour sélectionner des composantes avec des méthodes de consommation *Amont* et *Aval*. **Prélèvement inventaire** ne peut pas être utilisé pour sélectionner des composantes avec une méthode de consommation autre que *Manuel*. Pour gérer les composantes restantes, utilisez **Mouvement d'inventaire** sans référence à un document source. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

Dans les configurations d'entrepôt avancées où les emplacements nécessitent à la fois des prélèvements et des livraisons, vous devez utiliser la page **Prélèvement en entrepôt** pour amener les composantes avec la méthode de consommation définie sur *Manuel*, *Prélever + Aval*, *Prélever + Amont* aux bons de production. Pour plus d'informations, consultez [Prélever pour la fabrication ou l'assemblage dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

## <a name="to-pick-components-for-production-and-jobs-in-basic-warehouse-configurations"></a>Pour prélever les composantes pour la production et les projets dans les configurations d'entrepôt de base

Dans les configurations d'entrepôt de base où l'emplacement est configuré pour utiliser uniquement le prélèvement, vous pouvez prélever des composantes pour les activités de production et les lignes planification projet sur la page **Prélèvement inventaire**. Pour plus d'informations, voir [Prélever des articles avec les prélèvements stock](warehouse-how-to-pick-items-with-inventory-picks.md).

> [!NOTE]
> La possibilité de prélever des composantes pour les lignes planification projet a été ajoutée à [!INCLUDE[d365fin](includes/d365fin_md.md)] dans la 2e vague de lancement 2022. Pour commencer à utiliser la fonctionnalité, un administrateur doit activer **Mise à jour des fonctionnalités : activer prélèvement inventaire et entrepôt à partir des projets** sur la page **Gestion des fonctionnalités**.
>
>[!INCLUDE[prod_short](includes/prod_short.md)] utilise la valeur dans le champ **Quantité restante** sur la ligne planification projet lorsqu’il crée des prélèvements inventaire. Pour utiliser les prélèvements d’inventaire pour les projets, vous devez activer le bouton à bascule **Appliquer le lien d’utilisation** sur la page **Fiche projet** pour le projet. Cela vous permet de suivre l’utilisation par rapport à votre forfait. Si vous n’activez pas le bouton à bascule, la quantité restante restera à **0** et le prélèvement de l'inventaire ne sera pas créé. Pour plus d’informations, voir [Configurer le suivi de l’utilisation des tâches](projects-how-setup-jobs.md?tabs=current-experience#to-set-up-job-usage-tracking).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements inventaire**, puis choisissez le lien associé.  
2. Pour accéder aux composantes du bon de production, choisissez l'action **Extraire documents sources**, puis sélectionnez le bon de production libéré.  
3. Prélevez la composante, puis enregistrez les informations sur le prélèvement dans le champ **Qté à traiter**.  
4. Lorsque les lignes sont prêtes à être reportées, choisissez l'action **Reporter**. Les écritures entrepôt nécessaires sont alors créées et la consommation des articles est reportée.  

Vous pouvez également créer un **Prélèvement de stock** directement à partir de la commande de fabrication lancée. Choisissez l’action **Créer rangement/prélèvement/mouvement d'inventaire**, cochez la case **Créer prélèvement inventaire**, puis choisissez le bouton **OK**.

Sinon, utilisez un **Mouvement d'inventaire** en référence au document source pour déplacer des articles entre les zones. Vous devrez enregistrer la consommation séparément. Pour plus d'informations, voir [Reporter en lot la consommation de la production](production-how-to-post-consumption.md)

## <a name="pick-for-assembly-in-basic-warehouse-configurations"></a>Prélever pour l'Assemblage dans les configurations de stockage de base

Utilisez les pages suivantes pour prélever des ordres d’assemblage :

- La page **Mouvement d’inventaire**.
- Si l’emplacement exige des prélèvements, mais pas de livraisons, utilisez la page **Prélèvement inventaire** pour prélever, assembler et livrer les documents de vente lorsque les articles doivent être assemblés avant de pouvoir être livrés. Pour plus d’informations, voir [Traitement des articles assembler pour commande dans les prélèvements inventaire](warehouse-how-to-pick-for-production.md#handling-assemble-to-order-items-with-inventory-picks).  

Dans les configurations d’entrepôt avancées où les emplacements requièrent des prélèvements et des livraisons, vous devez utiliser la page **Prélèvement entrepôt** pour ajouter des composantes aux ordres d'assemblage. Pour plus d'informations, consultez [Prélever pour la fabrication ou l'assemblage dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).

## <a name="handling-assemble-to-order-items-with-inventory-picks"></a>Traitement des articles à assembler pour commande dans les prélèvements stock

La page **Prélèvement inventaire** est également utilisée pour prélever et livrer les ventes lorsque les articles doivent être assemblés avant de pouvoir être livrés. Pour plus d'informations, reportez-vous à [Vente d'articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).

Les articles Assembler pour commande à livrer ne sont pas considérés présents dans une zone tant qu’ils ne sont pas assemblés et reportés comme production dans une zone de la zone d’assemblage. Par conséquent, le prélèvement de ces articles pour la livraison suit un flux spécial. Depuis une zone, les employés d'entrepôt déposent des éléments d'assemblage sur le quai de livraison, puis reportent le prélèvement inventaire. Le prélèvement inventaire reporté reporte ensuite les résultats d'assemblage, la consommation de composantes et la livraison vente.

Vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour créer automatiquement un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage. Pour créer automatiquement des mouvements, sélectionnez le champ **Créer des mouvements automatiquement** sur la page **Configuration d’assemblage**. Pour plus d'informations, voir [Déplacer les composantes vers une zone opérations dans le stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md).

[!INCLUDE[prod_short](includes/prod_short.md)] crée des lignes prélèvement inventaire pour les articles vente de différentes manières, selon qu’aucune, certaines ou toutes les quantités des lignes vente sont assemblées pour commande.

- Dans les ventes où vous utilisez des prélèvements inventaire pour reporter la livraison de inventaire, [!INCLUDE[prod_short](includes/prod_short.md)] crée une ligne prélèvement inventaire pour chaque ligne document de vente. Si l’article est placé dans différentes zones, plusieurs lignes seront créées. Les lignes prélèvement sont basées sur la quantité indiquée dans le champ **Qté à livrer**.
- Dans les ventes où la quantité totale de la ligne document de vente est assemblée pour commande, une ligne prélèvement inventaire est créée pour cette quantité. La valeur du champ Quantité à assembler correspond à la valeur du champ **Qté à livrer**. Le champ **Assembler pour commande** est sélectionné sur la ligne.

Si un flux de résultats d’assemblage est paramétré pour l'emplacement, la valeur du champ **Code de zone livr. ass. pr comm.** ou **Code de zone depuis assemblage**, de cette commande, est insérée dans le champ **Code de zone** de la ligne prélèvement inventaire.

Si aucun code de zone n'est spécifié sur la ligne document de vente et qu'aucun flux résultats d'assemblage n'est configuré pour l'emplacement, le champ **Code de zone** de la ligne prélèvement inventaire est vide. L'employé d'entrepôt doit ouvrir la page **Contenus de la zone** et sélectionner la zone où les articles d'assemblage sont assemblés.

Si une partie de la quantité doit d’abord être assemblée, et une autre prélevée de l'inventaire, [!INCLUDE[prod_short](includes/prod_short.md)] crée au minimum deux lignes prélèvement inventaire. Une ligne prélèvement est calculée pour la quantité à assembler pour commande. L'autre ligne prélèvement dépend de quelles zones peuvent satisfaire à la quantité restante en inventaire. Les codes de zone sur les deux lignes sont renseignés de différentes manières comme indiqué pour les deux types de vente différents respectivement. Pour plus d'informations, voir la section « Scénarios de combinaison » dans [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="filling-the-consumption-bin"></a>Renseigner la zone consommation

Ce graphique indique comment le champ **Code de zone** sur les lignes composante bon de production est renseigné en fonction de la configuration de votre emplacement.

![Organigramme Flux de zone.](media/binflow.png "BinFlow")

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/pick-ship-items-business-central/) associée

## <a name="see-also"></a>Voir aussi .

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
