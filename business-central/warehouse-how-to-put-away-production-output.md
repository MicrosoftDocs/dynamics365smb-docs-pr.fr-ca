---
title: Ranger la production
description: Cet article décrit comment ranger la sortie de la production.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 12/20/2022
ms.custom: bap-template
ms.search.forms: '9326, 99000831, 9315, 7375'
---
# <a name="put-away-production-or-assembly-output"></a>Rangement du résultat de fabrication ou d'assemblage

Le mode de rangement de la production dépend du mode de configuration de l'entrepôt en tant qu'emplacement. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

Dans les configurations entrepôt de base où l’emplacement appelle un traitement de rangement, vous utilisez le document **Rangement inventaire** pour reporter la production et enregistrer son rangement.  

> [!NOTE]  
> Les processus d’assemblage ne prennent pas en charge le rangement inventaire. Vous reportez un ordre d’assemblage pour enregistrer le résultat. Si vous utilisez des zones, vous pouvez déplacer des éléments d’un emplacement à un autre ultérieurement. Learn more at [Déplacement des articles ad hoc dans les configurations entrepôt de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).  

Dans les configurations de stockage avancées où un emplacement nécessite un traitement à la fois de rangement et de réception, vous pouvez créer soit un document rangement interne soit un document mouvement pour ranger la production.  

## <a name="to-put-away-production-output-with-an-inventory-put-away"></a>Pour ranger la production avec un rangement inventaire

La première étape du rangement de la production consiste à créer la demande enlogement entrante. Cette demande indique à l'entrepôt que la production de l'O.F ou de l'assemblage est prête à être rangée.

### <a name="to-create-the-inbound-warehouse-request"></a>Pour créer la demande d'enlogement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bon de production libéré**, puis sélectionnez le lien associé.  
2. Choisissez le bon de production qui est prêt pour rangement, puis choisissez l’action **Créer requête entrepôt entrante**.  

> [!NOTE]  
> Vous pouvez également créer la demande d’enlogement entrepôt en choisissant le champ **Créer demande d’enlogement** lors de l’actualisation du bon de production. Pour en savoir pus, voir [Actualiser ou replanifier des bons de production](production-how-to-replan-refresh-production-orders.md).  

### <a name="to-put-output-away-with-an-inventory-put-away"></a>Pour ranger la production avec un rangement inventaire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangement inventaire**, puis choisissez le lien associé.  
2. Créez un rangement inventaire. Pour en savoir plus, voir [Ranger des articles avec le rangement inventaire](warehouse-how-to-put-items-away-with-inventory-put-aways.md).
3. Pour accéder aux composantes du bon de production, choisissez l'action **Extraire documents sources**, puis sélectionnez le bon de production libéré.  
4. Renseignez les lignes rangement en fonction des besoins.
5. Lorsque les lignes sont prêtes à être reportées, choisissez l'action **Reporter**. Les écritures entrepôt nécessaires sont alors créées et la production des articles est validée.  

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

Vous pouvez également créer un **rangement inventaire** directement à partir du bon de production libéré. Pour en savoir plus, voir [Ranger des articles avec le rangement inventaire](warehouse-how-to-put-items-away-with-inventory-put-aways.md).  

Lorsque vous reportez un rangement inventaire, il est supposé que toutes les opérations sont reportées selon l’itinéraire standard. C’est-à-dire que la quantité produite est reportée conformément à la dernière opération. Vous pouvez utiliser le journal production pour reporter les écarts de quantité produite et les temps d’exécution et de préparation. Si vous devez effectuer un report partiel après la création d’un rangement inventaire, vous pouvez le faire au niveau des temps de préparation et des quantités pour toutes les opérations, à l’exception de la dernière. La dernière opération est contrôlée par le rangement inventaire.  

Si vous devez juste reporter le temps d’exécution ou de préparation de la dernière opération, définissez la quantité produite de la dernière opération sur 0. Vous pouvez également choisir de ne pas reporter la dernière ligne en la supprimant.

## <a name="to-put-assembly-and-production-output-away-in-advanced-warehouse-configurations"></a>Pour ranger l’assemblage et la production dans les configurations de stockage avancées

Lorsque vous reportez l’ordre de fabrication ou d’assemblage dans un entrepôt qui utilise le prélèvement et le rangement dirigés, la production est placée dans la zone définie dans l’ordre de fabrication ou d’assemblage. Pour en savoir plus sur les différentes manières de déplacer des articles dans l’entrepôt avec des configurations avancées, consultez [Déplacer des articles dans les configurations de stockage avancées](warehouse-how-to-move-items-in-advanced-warehousing.md#to-move-items-with-the-warehouse-movement-worksheet).

> [!NOTE]  
> Vous ne pouvez pas saisir le numéro document source, tel que le numéro de bon de production, dans les documents de rangement interne, rangement ou mouvement pour les processus de sortie de la production ou de l’assemblage.  

## <a name="see-also"></a>Voir aussi

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
