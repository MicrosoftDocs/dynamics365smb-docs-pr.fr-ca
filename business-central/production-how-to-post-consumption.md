---
title: Reporter en lot la consommation
description: Si la méthode consommation est définie sur Manuel, vous devez reporter les composantes manuellement à l’aide d’un journal consommation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 99000846, 99000850
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 4f110f6f6ada70ab739749d7dcc3522987c3a1d4
ms.sourcegitcommit: 2ab6709741be16ca8029e2afadf19d28cf00fbc7
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 01/14/2022
ms.locfileid: "7973865"
---
# <a name="batch-post-production-consumption"></a>Reporter en lot la consommation de la production

Si le champ Méthode consommation indique **Manuelle**, vous devez valider les composants manuellement à l'aide d'une feuille consommation.  

>[!NOTE]
> Si vous avez activé le champ **Prélèvement requis** sur la fiche emplacement pour indiquer que l'emplacement requiert un traitement de prélèvement inventaire, vous ne devez pas utiliser ce traitement en lot. [!INCLUDE[prod_short](includes/prod_short.md)] gérera la consommation lorsque vous reporterez le prélèvement inventaire. Pour plus d’informations, voir [Prélever pour la fabrication dans les configurations d′entrepôt de base](warehouse-how-to-pick-for-production.md#pick-for-production-in-basic-warehouse-configurations).  

Vous pouvez également configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour reporter automatiquement (*consommer*) les composantes lorsque vous lancez ou terminez des bons de production. Pour plus d'informations, voir [Activer la consommation des composantes en fonction de la sortie réalisée](production-how-to-flush-components-according-to-operation-output.md).

## <a name="to-post-consumption-for-one-or-more-production-order-lines"></a>Pour reporter la consommation pour une ou plusieurs lignes bon de production

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal consommation**, puis choisissez le lien associé.  
2. Renseignez les champs en indiquant les données relatives au bon de production et à la consommation. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Utilisez l'action **Calculer consommation** pour générer les lignes journal des bons de production basés sur la production réelle (quantité de produits finis figurant dans le rapport) ou sur la production prévue (quantité de produits finis que vous prévoyez de fabriquer).

    > [!NOTE]
    > Si vous avez configuré la fiche emplacement pour exiger le traitement des prélèvements en entrepôt, seules les quantités déjà prélevées via une activité entrepôt peuvent être saisies dans le champ **Quantité** de la page **Journal consommation**, pas la quantité calculée. Pour plus d’informations, consultez [Prélever pour la production ou l’assemblage dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md)

3. Choisissez l'action **Reporter** pour reporter la consommation. Les stocks associés sont réduits.

## <a name="see-also"></a>Voir aussi

[Production](production-manage-manufacturing.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
