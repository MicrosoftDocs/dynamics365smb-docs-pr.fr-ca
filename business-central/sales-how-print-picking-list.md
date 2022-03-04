---
title: Imprimer la liste des prélèvements inventaire à partir d’un document de vente
description: Vous pouvez imprimer une liste des prélèvements inventaire directement à partir d'un document de vente, des ventes, de la facture et d'autres documents vente sortants.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: e42008912079eafeaa037f7759a50a2c76393edb
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8130108"
---
# <a name="print-the-picking-list"></a>Imprimer la liste des prélèvements

Vous pouvez imprimer une liste des prélèvements inventaire directement à partir d’un document de vente ou d’autres documents qui déclenchent la livraison des articles.

Ce rapport est généralement utilisé dans les compagnies sans fonctionnalité dédiée à la gestion des entrepôts, de sorte qu'un préposé à l'inventaire peut simplement afficher ou imprimer la liste des prélèvements à partir du document vente associé. Dans les compagnies avec un volume plus élevé ou des processus plus complexes, le prélèvement est planifié et effectué dans des documents entrepôt dédiés. Pour plus d'informations, voir [Prélèvement d'articles](warehouse-pick-items.md).

## <a name="to-print-a-picking-list-from-a-sales-order"></a>Pour imprimer une liste des prélèvements à partir d'un document de vente

La procédure suivante se base sur un document de vente. Les étapes sont similaires pour tous les autres documents pouvant être utilisés pour lancer la livraison d’articles, par exemple un ordre transfert.

1. Choisissez l’icône ![Page ou rapport pour la recherche.](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez le document de vente pour lequel vous souhaitez prélever des articles.  
3. Choisir l'action **Rapport**, puis choisissez l'action **Liste de prélèvement par ordre**.  
4. Sélectionnez le bouton **Imprimer** pour imprimer la liste de prélèvements, ou le bouton **Aperçu** pour l'afficher à l'écran.

Vous pouvez également enregistrer la liste des prélèvements en tant que document, par exemple, pour l'envoyer à quelqu'un ou pour l'ajouter en tant que pièce jointe au document de vente. Pour plus d'informations, voir [Gérer les pièces jointes, les liens et les notes sur les fiches et les documents](ui-how-add-link-to-record.md).

> [!NOTE]
> Si vous avez utilisé la fonction **Éclater nomenclature** sur le document de vente, seuls les composantes de l'élément d'assemblage associé sont affichées dans le rapport. Pour plus d'informations, reportez-vous à [Utiliser les nomenclatures](inventory-how-work-BOMs.md).

## <a name="see-also"></a>Voir aussi

[Inventaire](inventory-manage-inventory.md)  
[Prélèvement d'articles](warehouse-pick-items.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]