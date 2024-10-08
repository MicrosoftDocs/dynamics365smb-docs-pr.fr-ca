---
title: Comment configurer des unités de stock
description: Utilisez des unités de stock pour enregistrer des informations relatives à vos articles pour un emplacement ou une variante spécifique.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 06/10/2024
ms.custom: bap-template
ms.search.forms: '5704, 5700, 5702, 5701'
ms.service: dynamics-365-business-central
---

# <a name="set-up-stock-keeping-units"></a>Configuration des unités de gestion de stock

Utilisez des unités de stock pour enregistrer des informations relatives aux articles pour un emplacement ou une variante spécifique. Ils vous permettent d’ajouter différentes informations sur un article pour un emplacement spécifique, par exemple :

* Un entrepôt ou un centre de distribution
* Des variantes, par exemple différents numéros de tablette et différentes informations de réapprovisionnement, pour un même article  

## <a name="to-set-up-a-sku"></a>Pour configurer une unité de stock

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Centres de stock**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. Les champs suivants sont nécessaires : **N° article**, **Code d'emplacement** et/ou **Code variante**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

Après avoir configuré la première unité de stock pour un article, la case **L'unité de stock existe** sur la fiche **Article** est cochée.  

Pour créer plusieurs unités de stock pour un article, utilisez le traitement en lot **Créer unité de stock**. Pour en savoir plus sur les traitement en lot, consultez [Utiliser les files d’attente de travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

> [!NOTE]  
> Les informations de la fiche **Point de stock** sont prioritaires par rapport à celles de la fiche **Article**.

> [!Warning]
> Si l’unité de stock est expédiée à la fabrication, le champ **Coût standard** n’est pas utilisé lors de la facturation et de l’ajustement du coût réel de l’article fabriqué. À la place, [!INCLUDE [prod_short](includes/prod_short.md)] utilise la valeur du champ **Coût standard** de la fiche article et les écarts sont calculés par rapport aux coûts totaux de cet article.<br><br>
> Bien que vous puissiez affecter les nomenclatures de production et les itinéraires aux points de stock, le calcul du coût unitaire et le calcul lié des coûts totaux ne sont pas disponibles dans les points de stock. Pour en savoir plus sur les coûts standard, consultez [À propos du calcul du coût standard](finance-about-calculating-standard-cost.md)

## <a name="see-also"></a>Voir aussi .

[Enregistrement des nouveaux articles](inventory-how-register-new-items.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Gestion d'assemblage](assembly-assemble-items.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
