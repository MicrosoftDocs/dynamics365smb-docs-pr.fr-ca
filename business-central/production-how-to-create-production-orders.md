---
title: Créer des en-têtes O.F.
description: Vous pouvez créer manuellement un bon de production. Pour cela, la première étape est de créer un en-tête bon de production
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 9325, 99000815, 99000829, 9900083
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: b47525b8f552cb4446497a0edafa7661aa25f17b
ms.sourcegitcommit: 00a8acc82cdc90e0d0db9d1a4f98a908944fd50a
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/29/2022
ms.locfileid: "9074718"
---
# <a name="create-production-order-headers"></a>Créer des en-têtes O.F.

Vous pouvez créer manuellement un bon de production. Pour cela, la première étape est de créer un en-tête bon de production

Les ordres de fabrication sont généralement créés automatiquement par une fonction de planification pour répondre à une demande connue. Pour plus d'informations, voir [Planification](production-planning.md).  

La procédure suivante se base sur un bon de production planifié ferme. Vous pouvez aussi créer des bons de production dotés d'un autre état.  

## <a name="to-create-a-production-order-header"></a>Pour créer un en-tête bon de production

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de production planifiés fermes**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **N°**, insérez le numéro suivant de la souche.  
4. Dans le champ **Type origine**, sélectionnez la source de l'ordre de fabrication.

    Vous pouvez choisir de produire une famille d'articles. Pour plus d'informations, voir [Utiliser les familles de production](production-how-work-family.md).
5. Dans le champ **N° origine**, sélectionnez le numéro d'article, la famille, ou l'en-tête vente pour lequel l'ordre de fabrication doit être créé.  
6. Renseignez les champs **Quantité** et **Délai** en fonction de vos spécifications.  

Lorsque les exigences de production évoluent, comme les composantes ou les opérations, vous pouvez replanifier rapidement le bon de production. Pour plus d'informations, voir [Replanifier ou actualiser directement des ordres de fabrication](production-how-to-replan-refresh-production-orders.md).  

## <a name="see-also"></a>Voir aussi

[Production](production-manage-manufacturing.md)
[Paramétrage de la production](production-configure-production-processes.md)  
[Planification](production-planning.md)  
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]