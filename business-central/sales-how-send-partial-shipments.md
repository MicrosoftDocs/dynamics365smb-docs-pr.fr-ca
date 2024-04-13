---
title: Traiter les livraisons partielles
description: Les livraisons des documents de vente peuvent être traitées dans Business Central avec des livraisons partielles à l’aide des champs Avis de livraison et Quantité à livrer.
author: brentholtorf
ms.service: dynamics-365-business-central
ms.topic: conceptual
ms.search.keywords: 'shipping advice, partial shipments, partial deliveries, trade, customer sales order'
ms.date: 02/14/2024
ms.author: bholtorf
---
# <a name="process-partial-shipments"></a>Traiter les livraisons partielles

Dans une livraison partielle, une commande n’est pas livrée en une seule fois. Par exemple, pour une commande de 100 unités, vous en livrez 40 immédiatement et 60 ultérieurement. Il n’y a aucune limite quant au nombre de livraisons pouvant être effectuées pour une commande.

Cependant, avant de pouvoir utiliser des livraisons partielles dans [!INCLUDE [prod_short](includes/prod_short.md)], vous devez spécifier que le client accepte les livraisons partielles en définissant le champ **Avis d’expédition** sur la page **Fiche client**. Sinon, si le client n’accepte que des expéditions complètes, mais demande ensuite ou accepte une expédition partielle pour un document de vente spécifique, vous pouvez modifier le champ **Avis d’expédition** avant report.

Par défaut, [!INCLUDE [prod_short](includes/prod_short.md)] définit le champ dans la page **Fiche client** comme **Partiel**, ce qui permet des livraisons partielles. Toutefois, si le champ est défini pour spécifier **Complet**, le champ **Qté à expédier** apparaît bloqué dans les documents de vente pour ce client.

[!INCLUDE [order-ship-invoice_md](includes/order-ship-invoice.md)]

## <a name="see-also"></a>Voir aussi .

[Vente de produits avec un document de vente client](sales-how-sell-products.md)  
[Livrer des articles](warehouse-how-ship-items.md)  
[Effectuer des livraisons directes](sales-how-drop-shipment.md)  
[Ventes](sales-manage-sales.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
