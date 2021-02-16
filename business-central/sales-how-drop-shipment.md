---
title: Lier un document de vente à un bon de commande pour une livraison directe | Microsoft Docs
description: Décrit comment créer un document de vente liée à un bon de commande pour permettre la livraison directe du fournisseur au client.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: c6b84d3622b4261c1f88880ba1257bf00f83e346
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4748453"
---
# <a name="make-drop-shipments"></a>Effectuer des livraisons directes

Lors d'une livraison directe, un ou plusieurs articles de l'un de vos fournisseurs sont livrés directement chez l'un de vos clients.

Lorsqu'un document de vente est marqué pour livraison directe, et lorsque vous créez un bon de commande précisant le client dans le champ **Destinataire**, **Adresse client**, vous pouvez associer les deux documents pour demander au fournisseur de faire directement la livraison au client.
<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4mOyM?rel=0]

## <a name="to-create-a-sales-order-for-drop-shipment"></a>Pour créer un document de vente pour des livraisons directes

Pour préparer une livraison directe, vous créez un document de vente pour un article et indiquer sur la ligne vente que la vente exige la livraison directe.

1. Créez un document de vente pour un article. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
2. Sur la ligne commande vente pour l'article envoyé, cochez la case **Livraison directe**. Utilisez la fonction **Choisir les colonnes** si le champ n'est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

## <a name="to-create-the-purchase-order-for-drop-shipment"></a>Pour créer le bon de commande pour livraison directe

Pour préparer une livraison directe, vous indiquez sur le bon de commande qu'elle doit être livrée à votre client, et non à vous-même.

1. Créez un bon de commande. Ne remplissez pas les champs sur les lignes. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).
2. Dans le champ **Destinataire**, sélectionnez **Adresse client**.
3. Dans le champ **Client**, sélectionnez le client auquel vous souhaitez vendre l'article en question.
4. Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire document de vente**.
5. Sur la page **Liste des ventes**, sélectionnez le document de vente que vous avez préparée dans la section [Créer un document de vente pour livraison directe](sales-how-drop-shipment.md#to-create-a-sales-order-for-drop-shipment).
6. Choisissez le bouton **OK**.

Les informations de ligne du document de vente sont insérées sur la/les ligne(s) bon de commande.

Vous pouvez maintenant informer le fournisseur quant à la livraison des articles à votre client, par exemple en envoyant le bon de commande au format PDF.     

## <a name="to-create-multiple-purchase-orders-for-drop-shipments"></a>Pour créer plusieurs bons de commande pour des livraisons directes

Vous pouvez également utiliser la feuille de réquisition pour créer le bon de commande du fournisseur. L'avantage d'utiliser la feuille de réquisition est qu'elle permet de créer des bons de commande pour toutes les livraisons directes en attente, il n'est donc pas nécessaire de créer chacun d'eux individuellement.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Demandes achat**, puis choisissez le lien associé.
2. Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire document de vente**.
3. Choisissez le bouton **OK**.
4. Passez en revue les lignes bon de commande et, dans le champ **N° fournisseur**, sélectionnez le fournisseur qui fournit les marchandises requises. 
5. Choisissez l’action **Traiter messages d’action** pour convertir les lignes révisées en bon de commande.

## <a name="to-view-the-linked-purchase-order-from-the-sales-order"></a>Pour afficher le bon de commande associé à partir du document de vente

* Sélectionnez la ligne commande vente livraison directe, choisissez l'action **Commande**, puis l'action **Livraison directe** et enfin l'action **Commande achat**.

## <a name="to-post-a-drop-shipment"></a>Pour reporter une livraison directe

Lorsque le fournisseur a livré les articles, vous pouvez reporter le document de vente comme envoyé. Vous pouvez également valider la commande achat, mais uniquement avec l'option **Réceptionner** jusqu'à ce que la commande vente ait été facturée.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez le document de vente que vous avez créé dans [Pour créer un document de vente pour une livraison directe](#to-create-a-sales-order-for-drop-shipment).
3. Dans le champ **Qté à livrer**, spécifiez quelle quantité de la commande livrer : la quantité totale ou partielle.
4. Sélectionnez l'action **Valider** ou **Valider et envoyer**.
5. Sélectionnez l'option **Livrer** pour facturer ultérieurement ou l'option **Livrer et facturer** pour facturer immédiatement.

## <a name="see-also"></a>Voir aussi

[Créer des commandes spéciales](sales-how-to-create-special-orders.md)  
[Acheter des articles pour une vente](purchasing-how-purchase-products-sale.md)  
[Vendre des produits](sales-how-sell-products.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Vente](sales-manage-sales.md)  
[Inventaire](inventory-manage-inventory.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
