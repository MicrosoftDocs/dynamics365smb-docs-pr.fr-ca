---
title: "Lier un document de vente à un bon de commande pour une livraison directe | Microsoft Docs"
description: "Décrit comment créer un document de vente liée à un bon de commande pour permettre la livraison directe du fournisseur au client."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: direct shipment
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 68af9892db003a2200bd0ceb9b9fa839952dce36
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="make-drop-shipments"></a>Effectuer des livraisons directes
Lors d'une livraison directe, un ou plusieurs articles de l'un de vos fournisseurs sont livrés directement chez l'un de vos clients.

Lorsqu'une commande vente est marquée pour livraison directe, et lorsque vous créez une commande achat spécifiant le client dans le champ **N° donneur d'ordre** , vous pouvez ensuite associer les deux documents et par conséquent informer le fournisseur de procéder directement à la livraison au client.

## <a name="to-create-a-sales-order-for-drop-shipment"></a>Pour créer un document de vente pour des livraisons directes
Pour préparer une livraison directe, vous créez un document de vente pour un article, sauf que vous devez indiquer sur la ligne vente que la vente exige la livraison directe.

1. Créez un document de vente pour un article. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
2. Sur la ligne commande vente pour l'article envoyé, cochez la case **Livraison directe**. Utilisez la fonction **Choisir les colonnes** si le champ n'est pas visible. Pour plus d'informations, voir [Personnalisation de votre espace de travail](ui-personalization-user.md).

## <a name="to-create-the-purchase-order-for-drop-shipment"></a>Pour créer le bon de commande pour livraison directe
Pour préparer une livraison directe pour l'article mis en vente, vous créez un bon de commande, comme à l'accoutumée, sauf que vous devez indiquer sur le bon de commande qu'il doit être envoyé à votre client et non pas à vous-même.

1. Créez un bon de commande. Ne remplissez pas les champs sur les lignes. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).
2. Dans le champ **N° donneur d'ordre** , sélectionnez le client auquel vous souhaitez vendre l'article en question.
3. Choisissez l'action **Livraisons directes**, puis choisissez l'option **Extraire commande vente**.
4. Sur la page **Liste des ventes**, sélectionnez le document de vente que vous avez préparé dans la section « Créer un document de vente pour livraison directe ».
5. Cliquez sur le bouton **OK**.

Les informations de ligne du document de vente sont insérées sur la/les ligne(s) bon de commande.

Vous pouvez maintenant informer le fournisseur quant à la livraison des articles à votre client, par exemple en envoyant le bon de commande au format PDF.     

## <a name="to-view-the-linked-purchase-order-from-the-sales-order"></a>Pour afficher le bon de commande associé à partir du document de vente
* Sélectionnez la ligne commande vente livraison directe, choisissez l'action **Commande**, puis l'action **Livraison directe** et enfin l'action **Commande achat**.

## <a name="to-post-a-drop-shipment"></a>Pour reporter une livraison directe
Lorsque le fournisseur a livré les articles, vous pouvez reporter le document de vente comme envoyé. Vous pouvez également valider la commande achat, mais uniquement avec l'option **Réceptionner** jusqu'à ce que la commande vente ait été facturée.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez le document de vente que vous avez créé dans la section « Pour créer un document de vente pour une livraison directe ».
3. Dans le champ **Qté à expédier**, spécifiez la quantité de commandes à envoyer, la quantité de commandes partielles ou totales.
4. Sélectionnez l'action **Valider** ou **Valider et envoyer**.
5. Sélectionnez l'option **Livrer** pour facturer ultérieurement ou l'option **Livrer et facturer** pour facturer immédiatement.

## <a name="see-also"></a>Voir aussi
[Créer des commandes spéciales](sales-how-to-create-special-orders.md)  
[Acheter des articles pour une vente](purchasing-how-purchase-products-sale.md)  
[Vendre des produits](sales-how-sell-products.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Ventes](sales-manage-sales.md)  
[Stock](inventory-manage-inventory.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

