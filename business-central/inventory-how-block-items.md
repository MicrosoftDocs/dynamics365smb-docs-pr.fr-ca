---
title: Comment bloquer des articles pour la vente ou pour l'achat
description: Dans Business Central, un article peut être signalé comme bloqué pour la vente, bloqué pour l'achat ou bloqué dans tous les cas.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: c453a10f30d2a45f6d4641bda8b24ee3659b1a32
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3182310"
---
# <a name="block-items-from-sales-or-purchasing"></a>Bloquer des articles pour la vente ou pour l'achat
Vous pouvez bloquer un article pour empêcher sa saisie dans des lignes vente ou achat, et vous pouvez le bloquer pour empêcher son report dans n'importe quelle transaction.  

Le tableau suivant illustre ce qui se produit lorsque les articles sont bloqués.  

|Option|Description|  
|--------------------|------------|  
|**Bloqué à la vente**|Vous ne pouvez pas saisir l'article dans un document vente ou dans un journal article vente.|  
|**Bloqué à l'achat**|Vous ne pouvez pas saisir l'article dans un document achat, dans un journal article achat, ou dans les processus de planification achat.|  
|**Bloqué**|Vous ne pouvez pas utiliser l'article pour une transaction d'article.|  

> [!NOTE]
> Les articles bloqués peuvent être retournés. Cela signifie qu'aucun des paramètres ci-dessus ne s'applique lorsque l'article est utilisé sur des retours et des notes de crédit.

Lorsque vous utilisez la fonction **Copier à partir du document** pour créer des documents à partir de documents existants, vous êtes averti si des articles sur les lignes du document source sont bloqués. Les lignes de document bloquées sont exclues du nouveau document et une notification affiche une vue d'ensemble de toutes les lignes de document bloquées dans le document source.

## <a name="to-block-an-item-from-being-entered-on-sales-lines"></a>Pour bloquer un article pour la saisie sur des lignes vente  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à la vente**.  

Si vous essayez de saisir l'article sur un document vente ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.

## <a name="to-block-an-item-from-being-entered-on-purchase-lines"></a>Pour bloquer un article pour la saisie sur des lignes achat  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué à l'achat**.  

Si vous essayez de saisir l'article sur un document achat ou une ligne journal, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.

## <a name="to-block-an-item-from-being-posted"></a>Pour bloquer un article et empêcher son report
1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.
2. Sélectionnez l'article que vous souhaitez bloquer, puis sélectionnez la case à cocher **Bloqué**.

Si vous essayez de reporter tout type de transaction pour l'article, vous recevez désormais un message d'erreur indiquant que l'article est bloqué.

## <a name="see-also"></a>Voir aussi  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Inventaire](inventory-manage-inventory.md)  
