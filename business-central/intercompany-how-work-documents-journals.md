---
title: Reporter des documents et journaux intercompagnies
description: Cette rubrique explique comment vous pouvez utiliser les documents ou les journaux intersociétés pour reporter les transactions effectuées avec vos partenaires intercompagnies.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'IC, group, consolidation, affiliate, subsidiary'
ms.search.form: '600, 610'
ms.date: 03/09/2022
ms.author: edupont
---
# <a name="work-with-intercompany-documents-and-journals"></a><a name="work-with-intercompany-documents-and-journals"></a><a name="work-with-intercompany-documents-and-journals"></a>Utiliser les documents et les journaux intersociétés
Les documents ou journaux intercompagnies permettent de reporter les transactions effectuées avec vos partenaires intercompagnies. Lorsque vous reportez un document ou une ligne journal intercompagnie dans votre compagnie, le programme crée le document ou la ligne journal correspondante dans votre boîte d'envoi intercompagnie : vous pouvez le transmettre au partenaire concerné. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

Pour les documents achat et vente, le code partenaire intercompagnie du client ou du fournisseur concerné garantit que toutes les commandes et factures générées en relation avec les transactions avec ces compagnies produisent des documents correspondants dans la compagnie partenaire. Il en résulte un équilibrage correct des comptes.

Dans le cas des lignes journal général intercompagnies, vous ne devez pas spécifier les comptes pour un ensemble de livres particulier, mais simplement fournir l'identification de la compagnie concernée. Les lignes journal général intercompagnie correspondantes sont alors créées dans la compagnie partenaire, ce qui entraîne l'équilibrage des livres des deux compagnies impliquées dans une transaction.

## <a name="fill-in-and-send-an-intercompany-sales-order"></a><a name="fill-in-and-send-an-intercompany-sales-order"></a><a name="fill-in-and-send-an-intercompany-sales-order"></a>Pour renseigner et envoyer un document de vente intercompagnie
Vous pouvez envoyer les documents de vente et les bons de commande, ainsi que les retours avant qu'ils soient reportés. En revanche, l'envoi des factures et notes de crédit est impossible tant qu'elles ne sont pas reportées.

La procédure suivante explique comment renseigner et envoyer un document de vente intercompagnie. La même procédure s'applique aux bons de commande intercompagnie et aux retours, ainsi qu'aux factures et notes de crédit intercompagnie reportés.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Sélectionnez **Nouveau** pour créer un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Vérifiez que le client est un partenaire intercompagnie.
5. Pour envoyer le document de vente avant de le reporter, choisissez l'action **Envoi document de vente IC**.

> [!NOTE]
> Si vous effectuez l'étape 4, le document de vente est déplacé vers votre boîte d'envoi intercompagnies, d'où vous pouvez l'envoyer ultérieurement. Pour plus d'informations, voir [Gérer la boîte de réception et la boîte d'envoi intersociétés](intercompany-how-manage-intercompany-inbox.md).

## <a name="fill-in-and-post-an-intercompany-journal"></a><a name="fill-in-and-post-an-intercompany-journal"></a><a name="fill-in-and-post-an-intercompany-journal"></a>Pour renseigner et reporter un journal intercompagnie

Lorsque vous reportez une ligne journal général intercompagnie dans votre compagnie, le programme crée une ligne journal correspondante dans votre boîte d'envoi intercompagnie : vous pouvez la transmettre au partenaire concerné. Avec la 1re vague de lancement 2022, vous pouvez également configurer la compagnie afin que soient créées automatiquement les transactions intercompagnies reçues des partenaires intercompagnies, reportées via le journal général intercompagnie. Celui-ci peut ensuite reporter la transaction correspondante dans sa compagnie sans avoir à entrer à nouveau les données.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux généraux intercompagnies**, puis sélectionnez le lien associé.  
2. Ouvrez le lot journal approprié. Pour plus d'informations, reportez-vous à [Utilisation des feuilles comptabilité](ui-work-general-journals.md).
3. Renseignez les champs selon vos besoins.
4. Dans le champ **N° compte G/L du partenaire IC**, saisissez le numéro du compte du grand livre intercompagnie sur lequel le montant sera reporté dans la compagnie de votre partenaire.

    > [!NOTE]
    > Ce champ doit être renseigné avec une ligne dont l'un des champs **N° compte** ou  **N° compte de solde** contient un compte bancaire ou un compte du grand livre.  
5. Sélectionnez l'action **Valider**.

Les écritures associées sont reportées dans votre compagnie et un journal avec les écritures correspondantes est créé dans votre boîte d'envoi intercompagnie ; vous pouvez l'envoyer à votre partenaire. Pour plus d'informations, voir [Gérer la boîte de réception et la boîte d'envoi intersociétés](intercompany-how-manage-intercompany-inbox.md).

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi

[Gestion des transactions intersociétés](intercompany-manage.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser des journaux généraux](ui-work-general-journals.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
