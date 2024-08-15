---
title: Comment bloquer les ventes aux clients
description: 'Si nécessaire, vous pouvez empêcher qu''un client soit ajouté aux documents de vente et d''autres transactions de vente.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: null
ms.date: 07/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="block-customers"></a>Bloquer les clients
Vous pouvez bloquer un client, par exemple en raison d’une insolvabilité, afin que le client ne puisse pas être ajouté aux documents de vente ou qu’aucune transaction ne puisse être enregistrée pour le client.

En plus de bloquer un client, vous pouvez définir que des transactions à recevoir pour le client soient en attente au niveau des rappels. Pour plus d'informations, voir [Collecte des soldes restants](receivables-collect-outstanding-balances.md).   

Le tableau suivant décrit les options pour bloquer des clients.  

|Option|Description|  
|--------------------|------------|  
|**Vide**|Les transactions sont autorisés pour ce client.|
|**Livraison**|De nouvelles commandes et de nouvelles expéditions ne peuvent pas être créées pour ce client. Les livraisons existantes qui ne sont pas encore facturées peuvent être facturées.|  
|**Facture**|De nouvelles commandes, de nouvelles expéditions et de nouvelles factures ne peuvent pas être créées pour ce client. Les expéditions existantes non encore facturées ne peuvent pas être facturées. Vous pouvez toujours envoyer des rappels et des notes de frais financiers au client.|  
|**Tous**|Ce client n'est autorisé à effectuer aucune transaction, pas même un paiement.|  

## <a name="to-block-a-customer"></a>Pour bloquer un client
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Clients**, puis choisissez le lien associé.
2. Sélectionnez un client, puis cliquez sur l'action **Modifier**.
3. Dans le champ **Bloqué**, choisissez ce que vous souhaitez bloquer, comme décrit dans le tableau ci-dessus.

## <a name="see-also"></a>Voir aussi .
[Enregistrement de nouveaux clients](sales-how-register-new-customers.md)  
[Collecte des soldes restants](receivables-collect-outstanding-balances.md)  
[Gestion des comptes client](receivables-manage-receivables.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
