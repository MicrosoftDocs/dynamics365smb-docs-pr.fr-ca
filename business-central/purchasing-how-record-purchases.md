---
title: Enregistrer les achats avec les factures achat (contient une vidéo)
description: Décrit comment acheter des inventaires, des articles hors inventaire ou des ressources en créant et en reportant des factures ou commandes achat.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: procurement
ms.search.form: 50 ,51, 53, 56, 146, 147, 9307, 9309, 9306, 9308, 9310
ms.date: 09/07/2021
ms.author: edupont
ms.openlocfilehash: 55cc80b6f03d93dd2a4b92a32260831b52a1176c
ms.sourcegitcommit: 5a02f8527faecdffcc54f9c5c70cefe8c4b3b3f4
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/04/2022
ms.locfileid: "8383173"
---
# <a name="record-purchases-with-purchase-invoices"></a>Enregistrer les achats avec les factures achat

Vous créez une facture achat ou un bon de commande pour enregistrer le coût d'achats et suivre les créances. Si vous devez contrôler un inventaire, les factures achat et les bons de commande sont également utilisés pour mettre à jour les niveaux d'inventaire de manière dynamique afin que vous puissiez réduire vos coûts d'inventaire et fournir un meilleur service au client. Le prix d'achat, notamment les frais de service, et les valeurs d'inventaire qui résultent du report des factures achat ou des commandes contribuent aux chiffres du profit et à d'autres KPI financiers sur votre Tableau de bord.

## <a name="create-purchase-invoices"></a>Créer des factures achat

Outre l'achat d'articles physiques (type d'article **Inventaire**) qui affectent l'évaluation de l'inventaire, vous pouvez acheter des services représentés par des unités de temps. Vous pouvez le faire avec le type d'article **Service** ou le type de ligne **Ressource**.

Lorsque vous réceptionnez des articles d'inventaire ou lorsque le service acheté est terminé, vous reportez la facture ou commande achat pour mettre à jour l'inventaire et les enregistrements financiers et activer le paiement au fournisseur selon les modalités de paiement. Pour en savoir plus, consultez [Report des achats](ui-post-purchases.md) et [Effectuer des paiements](payables-make-payments.md).

> [!CAUTION]  
> Ne reportez pas une facture achat pour des articles physiques tant que vous n’avez pas reçu les articles et que vous ne connaissez pas le coût total de l’achat, frais supplémentaires compris. Sinon, la valeur de l'inventaire et les chiffres de profit peuvent être biaisés.

### <a name="to-create-a-purchase-invoice"></a>Pour créer une facture achat

Ce qui suit décrit comment créer une facture achat. La procédure est identique pour un bon de commande. La principale différence est que les bons de commande ont des champs et des actions supplémentaires pour la manutention des articles.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Dans le champ **Fournisseur**, entrez le nom d'un fournisseur existant.

    D'autres champs de la page **Facture achat** sont désormais renseignés avec les informations standard sur le fournisseur sélectionné. Si le fournisseur n'est pas enregistré, procédez comme suit :

    1. Dans le champ **Fournisseur**, entrez le nom du nouveau fournisseur.
    2. Dans la boîte de dialogue d'enregistrement du nouveau fournisseur, cliquez sur le bouton **Oui**.
    3. Pour en savoir plus sur la façon de remplir la carte du fournisseur, consultez [Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md).  
    4. Une fois que vous avez terminé la fiche fournisseur, cliquez sur le bouton **OK** pour revenir à la page **Facture achat**.

3. Renseignez les champs restants de la page **Facture achat**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    Vous êtes maintenant prêt à renseigner les lignes facture achat avec les articles ou ressources que vous avez achetés au fournisseur.

    > [!NOTE]  
    > Si vous avez défini des lignes achat récurrentes pour le fournisseur, par exemple un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la facture par l'intermédiaire de l'action **Extraire les lignes achat récurrentes**.
4. Dans le raccourci **Lignes**, dans le champ **N° article**, entrez le numéro d'un article en inventaire ou d'un service.
5. Dans le champ **Quantité**, indiquez le nombre d'articles à acheter.

    Le champ **Montant ligne** est mis à jour pour indiquer la valeur du champ **Coût unitaire direct** multipliée par la valeur du champ **Quantité**.

    Le prix et le montant ligne sont affichés avec ou sans la taxe de vente en fonction de ce que vous avez sélectionné dans le champ **Prix incluant les taxes** sur la fiche fournisseur.

    Les champs totaux sous les lignes sont automatiquement mis à jour lorsque vous créez ou modifiez des lignes pour afficher les montants qui seront reportés dans les livres.

6. Dans le champ **Montant d'escompte de la facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC** au bas de la facture.

    > [!NOTE]  
    > Si vous avez défini des remises facture pour le fournisseur, le pourcentage spécifié est automatiquement inséré dans le champ **% remise facture fournisseur** si les critères sont réunis, et le montant associé est inséré dans le champ **Montant remise facture**.
7. Lorsque vous recevez les articles ou services achetés, sélectionnez **Valider**.

L'achat est désormais visible dans l'inventaire, les livres ressource et les enregistrements financiers, et le paiement fournisseur est activé. La facture achat est supprimée de la liste des factures achat et remplacée par un nouveau document dans la liste des factures achat reportées.  

> [!NOTE]
> Dans de rares cas, les montants reportés peuvent différer de ce qui est affiché dans les champs des totaux. Cela est généralement dû aux calculs d'arrondissement par rapport à la TVA ou à la taxe de vente.
>
> Pour vérifier les montants qui seront réellement reportés, vous pouvez utiliser la page **Statistiques**, qui tient compte des calculs d'arrondissement. Aussi, si vous choisissez l'action **Libérer**, les champs de totaux seront mis à jour pour inclure les calculs d’arrondissement.

## <a name="when-to-use-purchase-orders"></a>Quand utiliser les bons de commande

Vous devez utiliser les commandes achat si votre processus de vente exige que vous enregistriez des réceptions partielles d'une quantité de commande, par exemple, si la quantité totale n'était pas disponible auprès du fournisseur. Si vous commercialisez des articles en les livrant directement depuis votre fournisseur auprès de votre client, vous devez également utiliser les bons de commande. Pour plus d'informations, voir [Effectuer des livraisons directes](sales-how-drop-shipment.md). Pour tous les autres aspects, les commandes achat fonctionnent de la même manière que les factures achat. La procédure suivante se base sur une facture achat. La procédure est identique pour un bon de commande.

<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4b3tt?rel=0]

## <a name="selling-non-inventory-items"></a>Vente d'articles hors inventaire

Les articles sur une facture achat peuvent être de type **Inventaire**, **Service**, **Ressource** et **Hors inventaire** pour spécifier si l’article est une unité d'inventaire physique, une unité de temps de travail ou une unité physique qui n’est pas conservée dans l'inventaire. Pour plus d'informations, voir [Enregistrer de nouveaux articles](inventory-how-register-new-items.md). Le processus de facture achat est identique pour les trois types d'article.

> [!NOTE]
> Avec le type de ligne achat **Ressource**, vous pouvez également acheter des ressources externes, par exemple pour facturer un fournisseur pour le travail livré. Pour plus d'informations, reportez-vous à [Configuration de ressources](projects-how-setup-resources.md).
>
> Pour utiliser une ressource achetée, vous devrez peut-être définir la capacité de la ressource et l'affecter manuellement à un projet. L'achat d'une ressource crée une écriture ressource. Cependant, les écritures ressource ne sont pas suivies pour la quantité et la valeur comme le sont les articles, par exemple. Si le suivi de la quantité et de la valeur est requis, envisagez d'utiliser d'autres types d'élément de ligne.

## <a name="posted-invoices"></a>Factures reportées

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

Vous pouvez facilement corriger ou annuler une facture achat reportée avant de payer le fournisseur. Cela est utile si vous souhaitez corriger une erreur de saisie ou si vous souhaitez modifier l'achat assez tôt dans le processus de commande. Pour plus d'informations, voir [Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md). Si vous avez déjà payé des articles ou services sur la facture achat reportée, vous devez créer une note de crédit achat pour inverser l'achat. Pour plus d'informations, reportez-vous à [Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md).

[Ouvrir la liste des **factures achat reportées**](https://businesscentral.dynamics.com/?page=146) dans [!INCLUDE [prod_short](includes/prod_short.md)].

## <a name="external-document-number"></a>Numéro de document externe

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/processing-invoices-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Procédure d'achat](purchasing-manage-purchasing.md)  
[Définition des achats](purchasing-setup-purchasing.md)  
[Paramétrer des ressources](projects-how-setup-resources.md)  
[Report des achats](ui-post-purchases.md)  
[Demander des devis](purchasing-how-request-quotes.md)  
[Acheter des articles pour une vente](purchasing-how-purchase-products-sale.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Préparer des livraisons directes](sales-how-drop-shipment.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]