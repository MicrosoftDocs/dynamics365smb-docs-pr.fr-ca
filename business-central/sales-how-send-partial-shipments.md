---
title: Traiter les livraisons partielles
description: Les livraisons des documents de vente peuvent être traitées dans Business Central avec des livraisons partielles à l’aide des champs Avis de livraison et Quantité à livrer.
author: rubenseishima
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.search.keywords: 'shipping advice, partial shipments, partial deliveries, trade, customer sales order'
ms.date: 08/12/2022
ms.author: a-reishima
---
# Traiter les livraisons partielles

Dans une livraison partielle, une commande n’est pas livrée en une seule fois. Par exemple, pour une commande de 100 unités, vous en livrez 40 immédiatement et 60 ultérieurement. Il n’y a aucune limite quant au nombre de livraisons pouvant être effectuées pour une commande.

Cependant, avant de pouvoir utiliser des livraisons partielles dans [!INCLUDE [prod_short](includes/prod_short.md)], vous devez spécifier que le client accepte les livraisons partielles en définissant le champ **Avis d’expédition** sur la page **Fiche client**. Sinon, si le client n’accepte généralement que des livraisons complètes, mais demande ensuite ou accepte une livraison partielle pour un document de vente spécifique, vous pouvez modifier le champ **Avis de livraison** avant report.

Par défaut, [!INCLUDE [prod_short](includes/prod_short.md)] définit le champ dans la page **Fiche client** comme **Partiel**, ce qui permet des livraisons partielles. Si, toutefois, le champ a été ajusté pour spécifier **Complet**, le champ **Qté à livrer** est bloqué dans les documents de vente pour ce client.

[!INCLUDE [order-ship-invoice_md](includes/order-ship-invoice.md)]

## Voir aussi .

[Vente de produits avec un document de vente client](sales-how-sell-products.md)  
[Livrer des articles](warehouse-how-ship-items.md)  
[Effectuer des livraisons directes](sales-how-drop-shipment.md)  
[Ventes](sales-manage-sales.md)  
[Préparation aux activités commerciales](ui-get-ready-business.md)  
[Administration](admin-setup-and-administration.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
