---
title: Reporter des documents et journaux intercompagnies
description: Cette rubrique explique comment vous pouvez utiliser les documents ou les journaux intersociétés pour reporter les transactions effectuées avec vos partenaires intercompagnies.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 02/06/2023
ms.custom: bap-template
ms.search.keywords: 'IC, group, consolidation, affiliate, subsidiary, bank-to-bank'
ms.search.form: '600, 610'
ms.service: dynamics-365-business-central
---
# Utiliser les documents et les journaux intersociétés

Les documents ou journaux intercompagnies permettent de reporter les transactions effectuées avec vos partenaires intercompagnies. Vous pouvez publier des transactions sur des comptes du grand livre et, si vous avez configuré des comptes bancaires intercompagnies, vous pouvez également publier des transactions de banque à banque. Pour en savoir plus sur la configuration des comptes bancaires intercompagnies, accédez à [Spécifier les comptes bancaires à utiliser pour les partenaires intercompagnies](intercompany-how-setup.md#specify-the-bank-accounts-to-use-for-intercompany-partners).  

Lorsque vous reportez un document ou une ligne journal intercompagnie dans votre compagnie, le programme crée le document ou la ligne journal correspondant dans votre boîte d’envoi intercompagnie. Vous transférez la ligne de votre boîte d’envoi à votre partenaire. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

Pour les documents achat et vente, le code partenaire intercompagnie du client ou du fournisseur concerné garantit que toutes les commandes et factures générées en relation avec les transactions entre les partenaires produisent des documents correspondants dans les compagnies partenaires. Les comptes de la compagnie s’équilibrent correctement.

Il en est de même pour les lignes journal général intercompagnies. Vous n’avez pas besoin de spécifier de comptes, il vous suffit de choisir l’entreprise partenaire. Les lignes journal général intercompagnies correspondantes sont ensuite créées dans la compagnie partenaire.

## Renseigner et envoyer un document de vente intercompagnie

Vous pouvez envoyer les documents de vente et les bons de commande, ainsi que les retours avant qu'ils soient reportés. En revanche, l’envoi des factures et notes de crédit est impossible tant qu’ils ne sont pas reportés.

La procédure suivante explique comment renseigner et envoyer un document de vente intercompagnie. La même procédure s'applique aux bons de commande intercompagnie et aux retours, ainsi qu'aux factures et notes de crédit intercompagnie reportés.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez **Nouveau** pour créer un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Vérifiez que le client est un partenaire intercompagnie.
5. Pour envoyer le document de vente avant de le reporter, choisissez l'action **Envoi document de vente IC**.

> [!NOTE]
> Si vous effectuez l’étape 5, le document de vente est déplacé vers votre boîte d’envoi intercompagnie, d’où vous pouvez l’envoyer ultérieurement. Pour en savoir plus sur la boîte de réception et la boîte d’envoi intersociétés, accédez à [Gérer la boîte de réception et la boîte d’envoi intersociétés](intercompany-how-manage-intercompany-inbox.md).

## Renseigner et reporter un journal intercompagnie

Lorsque vous reportez une ligne journal général intercompagnie dans votre compagnie, le programme crée une ligne journal correspondante dans votre boîte d'envoi intercompagnie : vous pouvez la transmettre au partenaire concerné. Avec la 1re vague de lancement 2022, vous pouvez également configurer la compagnie afin que soient créées automatiquement les transactions intercompagnies reçues des partenaires intercompagnies, reportées via les journaux généraux intercompagnies. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux intercompagnies**, puis sélectionnez le lien associé.  
2. Ouvrez le journal. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](../archive/invoicing/includes/tooltip-inline-tip_md.md)]
4. Dans le champ **N° compte G/L du partenaire IC**, saisissez le numéro du compte du grand livre intercompagnie sur lequel le montant sera reporté dans la compagnie de votre partenaire.

    > [!NOTE]
    > Ce champ doit être renseigné avec une ligne dont l'un des champs **N° compte** ou  **N° compte de solde** contient un compte bancaire ou un compte du grand livre.  
5. Sélectionnez l'action **Reporter**.

Les écritures sont reportées dans votre compagnie et un journal avec les écritures correspondantes est créé dans votre boîte d’envoi intercompagnie; vous pouvez l’envoyer à votre partenaire.

## Voir aussi

[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]