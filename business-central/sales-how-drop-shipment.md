---
title: Réalisation de livraisons directes
description: Décrit comment créer un document de vente liée à un bon de commande pour permettre la livraison directe du fournisseur au client.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: direct shipment
ms.date: 05/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="make-drop-shipments"></a>Réalisation de livraisons directes

Lors d'une livraison directe, un ou plusieurs articles de l'un de vos fournisseurs sont livrés directement chez l'un de vos clients.

Lorsqu'un document de vente est marqué pour livraison directe, et lorsque vous créez un bon de commande précisant le client dans le champ **Destinataire**, **Adresse client**, vous pouvez associer les deux documents pour demander au fournisseur de faire directement la livraison au client.
<br><br>  
  
> [!Video https://www.microsoft.com/en-us/videoplayer/embed/RE4mOyM?rel=0]

## <a name="to-create-a-sales-order-for-drop-shipment"></a>Pour créer un document de vente pour des livraisons directes

Pour préparer une livraison directe, vous créez un document de vente pour un article et indiquer sur la ligne vente que la vente exige la livraison directe.

1. Créez un document de vente pour un article. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
2. Sur la ligne document de vente pour la livraison directe, cochez la case **Livraison directe**. Sinon, dans le champ **Code achat**, sélectionnez un code achat dont le champ **Livraison directe** est sélectionné.

> [!TIP]
> Par défaut, la case à cocher Livraison directe et le champ Code achat n’est pas disponible sur les lignes. Si ce n’est pas le cas, vous pouvez les ajouter en personnalisant la section de page qui contient les lignes. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

## <a name="to-create-the-purchase-order-for-drop-shipment"></a>Pour créer le bon de commande pour livraison directe

Pour préparer une livraison directe, vous indiquez sur le bon de commande qu'elle doit être livrée à votre client, et non à vous-même.

1. Créez un bon de commande. Ne remplissez aucun champ sur les lignes. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).
2. Dans le champ **Destinataire**, sélectionnez **Adresse client**.
3. Dans le champ **Client**, sélectionnez le client auquel vous vendez l’article.
4. Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire commande vente**.
5. Sur la page **Liste des ventes**, sélectionnez le document de vente que vous avez préparé dans [Créer un document de vente pour livraison directe](#to-create-a-sales-order-for-drop-shipment).
6. Choisissez le bouton **OK**.

Les informations de ligne du document de vente sont insérées sur la/les ligne(s) bon de commande.

Vous pouvez maintenant demander à votre fournisseur de livrer les articles directement au client. Par exemple, vous pouvez lui envoyer la commande par courriel.

Si votre fournisseur vous communique des Informations supplémentaires, comme un numéro de suivi, vous pouvez ajouter ces informations comme Commentaire sur une ligne bon de commande. Pour ajouter un commentaire sur une ligne, dans le champ **Type** , choisissez **Commentaire**, puis saisissez les informations dans le champ **Description** .  

## <a name="to-create-multiple-purchase-orders-for-drop-shipments"></a>Pour créer plusieurs bons de commande pour des livraisons directes

Vous pouvez également utiliser la feuille de réquisition pour créer des bons de commande. L’avantage d’utiliser la feuille de réquisition est qu’elle peut créer des bons de commande pour toutes les livraisons directes en attente. Cela signifie que vous n’avez pas à créer chaque ordre individuellement.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , saisissez **Feuilles de réquisition**, puis choisissez le lien associé.
2. Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire commande vente**.
3. Si nécessaire, saisissez des critères de filtrage pour les commandes que vous souhaitez obtenir, puis cliquez sur le bouton **OK** .
4. Passez en revue les lignes bon de commande et, dans le champ **N° fournisseur**, sélectionnez le fournisseur qui fournit les marchandises.
5. Choisissez l’action **Traiter message d’action** pour convertir les lignes en bon de commande.

## <a name="to-view-the-linked-purchase-order-from-the-sales-order"></a>Pour afficher le bon de commande associé à partir du document de vente

Sélectionnez la ligne commande vente livraison directe, choisissez l'action **Commande**, puis l'action **Livraison directe** et enfin l'action **Commande achat**.

## <a name="to-post-a-drop-shipment"></a>Pour reporter une livraison directe

Lorsque le fournisseur a livré les articles, vous pouvez reporter le document de vente comme envoyé. Vous pouvez également valider la commande achat, mais uniquement avec l'option **Réceptionner** jusqu'à ce que la commande vente ait été facturée.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez le document de vente que vous avez créé dans [Pour créer un document de vente pour une livraison directe](#to-create-a-sales-order-for-drop-shipment).
3. Dans le champ **Qté à livrer**, spécifiez quelle quantité de la commande livrer : la quantité totale ou partielle.
4. Sélectionnez l'action **Valider** ou **Valider et envoyer**.
5. Sélectionnez l'option **Livrer** pour facturer ultérieurement ou l'option **Livrer et facturer** pour facturer immédiatement.

> [!TIP]
> N’oubliez pas que vous devez reporter la facture du bon de commande.

## <a name="see-also"></a>Voir aussi .

[Création des commandes spéciales](sales-how-to-create-special-orders.md)  
[Achat des articles pour une vente](purchasing-how-purchase-products-sale.md)  
[Vente des produits](sales-how-sell-products.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Vente](sales-manage-sales.md)  
[Inventaire](inventory-manage-inventory.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
