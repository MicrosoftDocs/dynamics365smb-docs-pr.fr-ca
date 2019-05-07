---
title: Comment bloquer les ventes aux articles clients depuis les ventes ou les achats
description: Dans Business Central, un article peut être signalé comme bloqué pour la vente, bloqué pour l'achat ou bloqué dans tous les cas.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: a2dee70270df135bc61ddef38e661758431b02a9
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "924174"
---
# <a name="block-customers"></a>Bloquer des clients
Vous pouvez bloquer un client, par exemple à cause de son insolvabilité, afin qu'il ne puisse pas être ajouté à des documents vente ou afin d'empêcher que d'autres transactions soient reportées pour ce client.

En plus de bloquer un client, vous pouvez définir que des transactions à recevoir pour le client soient en attente au niveau des rappels. Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).   

Le tableau suivant décrit les différentes options de blocage.  

|Option|Description|  
|--------------------|------------|  
|**Vide**|Les transactions sont autorisés pour ce client.|
|**Livraison**|Vous ne pouvez pas créer de commandes ni de livraisons pour ce client. Les livraisons existantes qui ne sont pas encore facturées peuvent être facturées.|  
|**Facture**|Vous ne pouvez pas créer de commandes, de livraisons ni de factures pour ce client. Les livraisons existantes qui ne sont pas encore facturées ne peuvent pas être facturées.|  
|**Tout**|Ce client n'est autorisé à effectuer aucune transaction, pas même un paiement.|  

## <a name="to-block-a-customer"></a>Pour bloquer un client  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Clients**, puis sélectionnez le lien associé.
2. Sélectionnez un client, puis cliquez sur l'action **Modifier**.
3. Renseignez le champ **Bloqué** avec l'une des options décrites ci-dessus.

## <a name="see-also"></a>Voir aussi  
[Enregistrer de nouveaux clients](sales-how-register-new-customers.md)  
[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  
