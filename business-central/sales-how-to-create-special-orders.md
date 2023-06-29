---
title: "Procédure\_: créer des commandes spéciales"
description: Découvrez comment créer une commande spéciale pour un article de catalogue spécifique à livrer à un client particulier.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: null
ms.date: 06/23/2021
ms.author: edupont
---
# <a name="create-special-orders"></a><a name="create-special-orders"></a>Créer des commandes spéciales

Vous pouvez créer une commande spéciale pour un article de catalogue spécifique à livrer à un client particulier. Le fournisseur livre l'article à votre entrepôt et vous pouvez ensuite le livrer à votre client seul ou avec d'autres articles issus d'autres commandes.  

Dans le cadre d'une commande spéciale, le bon de commande et le document de vente sont liés pour s'assurer que l'article de catalogue spécifique est prélevé et livré au client.  

Pour pouvoir utiliser cette fonction, vous devez d'abord configurer les fiches client, fournisseur, et article nécessaires à la commande.  

## <a name="to-create-a-special-order"></a><a name="to-create-a-special-order"></a>Pour créer une commande spéciale

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Document de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**. Créez et renseignez un document de vente pour l'article. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
3.  Sous le raccourci **Lignes**, renseignez la ligne vente. Dans le champ **Procédure achat**, sélectionnez une procédure achat dont le champ **Commande spéciale** est sélectionné.

    Vous devez maintenant créer un bon de commande à partir d'une feuille de réquisition.  
4. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille de réquisition**, puis sélectionnez le lien associé.  
5. Choisissez l'action **Commande spéciale**, puis choisissez l'action **Extraire documents de vente**.  
6.  Sur la page **Extraire documents de vente**, affichez les résultats dans lesquels le **N° document** correspond au numéro de document de vente. Cliquez sur le bouton **OK**. Une ligne de feuille de réquisition est créée pour l'article.  
7.  Dans la ligne demande achat, sélectionnez **Nouveau** dans le champ **Message d'action**.  
8.  Sur la page **Demande achat**, sélectionnez l'action **Traiter messages d'action**. La page **Traiter messages d'action - Demande** s'affiche. Cliquez sur le bouton **OK**.  

    Le message qui s'affiche indique que les commandes achat ont été créées. Cliquez sur le bouton **OK**.  

Un bon de commande créé comme commande spécial pour un document de vente est respecté par le système de planification lorsqu'il équilibre l'offre et la demande. Ainsi, le bon de commande (approvisionnement) reste lié au document de vente (demande), même si ce bon de commande pourrait approvisionner une autre demande antérieure. Pour plus d'informations, voir [Détails de conception : méthodes de réapprovisionnement](design-details-reservation-order-tracking-and-action-messaging.md).  

> [!NOTE]  
>  Vous ne pouvez pas utiliser la fonctionnalité de commande spéciale si l'élément est déjà réservé. Par conséquent, pour les articles qui sont vendus en commandes spéciales, assurez\-vous que le champ **Réserver** sur la fiche article n'est pas défini sur **Toujours**.  

## <a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/create-sales-documents-dynamics-365-business-central/) associée

## <a name="see-also"></a><a name="see-also"></a>Voir aussi .

[Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md)  
[Ventes](sales-manage-sales.md)  
[Effectuer des livraisons directes](sales-how-drop-shipment.md)   
[Détails de conception : méthodes de réapprovisionnement](design-details-reservation-order-tracking-and-action-messaging.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
