---
title: Enregistrer les achats avec les factures achat (contient une vidéo)
description: 'Décrit comment acheter des inventaires, des articles hors inventaire ou des ressources en créant et en reportant des factures ou commandes achat.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: procurement
ms.search.form: '50 ,51, 53, 56, 146, 147, 9307, 9309, 9306, 9308, 9310'
ms.date: 09/01/2022
ms.author: bholtorf
---
# <a name="record-purchases-with-purchase-invoices-and-orders"></a>Enregistrer les achats avec les factures achat et les commandes

Vous créez une facture achat ou un bon de commande pour enregistrer le coût d'achats et suivre les créances. Les factures achat et les bons de commande sont également utilisés pour mettre à jour de manière dynamique les niveaux d'inventaire afin que vous puissiez réduire vos coûts d'inventaire et fournir un meilleur service au client. Le prix d’achat, notamment les frais de service, et les valeurs d’inventaire qui résultent du report des factures achat ou des commandes contribuent aux chiffres du profit et à d’autres KPI financiers sur votre Tableau de bord.

## <a name="record-purchases-with-purchase-invoices"></a>Enregistrer les achats avec les factures achat

Lorsque vous réceptionnez des articles de l’inventaire ou lorsque le service acheté est terminé, vous reportez la facture achat pour mettre à jour l’inventaire et les enregistrements financiers, et activer le paiement au fournisseur selon les modalités de paiement. [Effectuer des paiements](payables-make-payments.md).

> [!CAUTION]  
> Ne reportez pas une facture achat pour des articles physiques tant que vous n’avez pas reçu les articles et que vous ne connaissez pas le coût total de l’achat, frais supplémentaires compris. Sinon, la valeur de l'inventaire et les chiffres de profit peuvent être biaisés.

### <a name="create-a-and-post-purchase-invoice"></a>Créer et reporter une facture achat

Ce qui suit décrit comment créer une facture achat. La procédure est identique pour un bon de commande. La principale différence est que les bons de commande ont des champs et des actions supplémentaires pour la manutention des articles.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Dans le champ **Fournisseur**, entrez le nom d'un fournisseur existant.

    D’autres champs de la page **Facture achat** sont désormais renseignés avec les informations standard sur le fournisseur sélectionné. Si le fournisseur n’est pas enregistré, procédez comme suit :

    1. Dans le champ **Fournisseur**, entrez le nom du nouveau fournisseur.
    2. Dans la boîte de dialogue d’enregistrement du nouveau fournisseur, cliquez sur le bouton **Oui**.
    3. Pour en savoir plus sur la façon de remplir la carte du fournisseur, consultez [Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md).  
    4. Une fois que vous avez terminé la fiche fournisseur, cliquez sur le bouton **OK** pour revenir à la page **Facture achat**.

3. Renseignez les champs restants de la page **Facture achat**, selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    Vous êtes maintenant prêt à renseigner les lignes facture achat avec les articles ou ressources que vous avez achetés au fournisseur.

    > [!NOTE]  
    > Si vous avez défini des lignes achat récurrentes pour le fournisseur, par exemple un ordre de réapprovisionnement mensuel, vous pouvez insérer ces lignes sur la facture par l'intermédiaire de l'action **Extraire les lignes achat récurrentes**.
4. Dans le raccourci **Lignes**, dans le champ **N° article**, entrez le numéro d’un article d'inventaire ou d’un service.
5. Dans le champ **Quantité**, indiquez le nombre d'articles à acheter.

    Le champ **Montant ligne** est mis à jour pour indiquer la valeur du champ **Coût unitaire direct** multipliée par la valeur du champ **Quantité**.

    Le prix et le montant ligne sont affichés avec ou sans la taxe de vente en fonction de ce que vous avez sélectionné dans le champ **Prix incluant les taxes** sur la fiche fournisseur.

    Les champs totaux sous les lignes sont automatiquement mis à jour lorsque vous créez ou modifiez des lignes pour afficher les montants qui seront reportés dans les livres.

6. Dans le champ **Montant d'escompte de la facture**, entrez un montant qui doit être déduit de la valeur indiquée dans le champ **Total TTC** au bas de la facture.

    > [!NOTE]  
    > Si vous avez défini des escomptes facture pour le fournisseur, le pourcentage spécifié est automatiquement inséré dans le champ **% escompte facture fournisseur** si les critères sont réunis. Le montant correspondant est alors inséré dans le champ **Montant d’escompte de la facture**.
7. Lorsque vous recevez les articles ou services achetés, sélectionnez **Valider**.

L'achat est désormais visible dans l'inventaire, les livres ressource et les enregistrements financiers, et le paiement fournisseur est activé. La facture achat est supprimée de la liste des factures achat et remplacée par un nouveau document dans la liste des factures achat reportées.  Pour plus d’informations sur ce qui se passe lorsque vous reportez des documents achat, consultez [Reporter des achats](purchasing-how-record-purchases.md#posting-purchases).

> [!NOTE]
> Dans de rares cas, les montants reportés peuvent différer de ce qui est affiché dans les champs des totaux. Cela est généralement dû aux calculs d’arrondissement par rapport à la TVA ou à la taxe de vente.
>
> Pour vérifier les montants qui seront réellement reportés, utilisez la page **Statistiques**, qui tient compte des calculs d’arrondissement. Aussi, si vous choisissez l'action **Libérer**, les champs de totaux seront mis à jour pour inclure les calculs d’arrondissement.

## <a name="posted-invoices"></a>Factures reportées

[!INCLUDE [posted-invoices](includes/posted-invoices.md)]

Vous pouvez facilement corriger ou annuler une facture achat reportée avant de payer le fournisseur. Cela est utile si vous souhaitez corriger une erreur de saisie, ou si vous souhaitez modifier l’achat assez tôt dans le processus de commande. En savoir plus, [Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md) Si vous avez déjà payé des articles ou services sur la facture achat reportée, vous devez créer une note de crédit achat pour inverser l’achat. En savoir plus, [Traiter les retours ou annulations d’achats](purchasing-how-process-purchase-returns-cancellations.md)

[Ouvrir la liste des **factures achat reportées**](https://businesscentral.dynamics.com/?page=146) dans [!INCLUDE [prod_short](includes/prod_short.md)].


## <a name="purchasing-non-inventory-items"></a>Achat d'articles hors inventaire

Les lignes d’une facture d’achat peuvent être de type **Ressource** ou **Article**. Les fiches article peuvent être classées comme étant de type **Inventaire**, **Service** ou **Hors inventaire** pour spécifier si l’article est une unité d'inventaire physique, une unité de temps de travail (applicable pour les ressources) ou une unité physique qui n’est pas conservée dans l'inventaire. En savoir plus sur [Enregistrer de nouveaux articles](inventory-how-register-new-items.md). Le processus de facture achat est identique pour tous les types mentionnés.

> [!NOTE]
> Avec le type de ligne achat **Ressource**, vous pouvez également acheter des ressources externes, par exemple pour facturer un fournisseur pour le travail livré. En savoir plus sur [Configurer les ressources](projects-how-setup-resources.md).
>
> Pour utiliser une ressource achetée, vous devrez peut-être définir la capacité de la ressource et l'affecter manuellement à un projet. L’achat d’une ressource crée une écriture ressource. Cependant, les écritures ressource ne sont pas suivies pour la quantité et la valeur comme le sont les articles, par exemple. Si le suivi de la quantité et de la valeur est requis, envisagez d'utiliser d'autres types d'élément de ligne.

## <a name="when-to-use-purchase-orders"></a>Quand utiliser les bons de commande

Vous devez utiliser les bons de commande si votre processus d'achat exige que vous enregistriez des réceptions partielles d’une quantité de commande, par exemple, si la quantité totale n’était pas disponible auprès du fournisseur. Si vous livrez des articles vendus directement de votre fournisseur à votre client en tant que livraison directe , vous devez également utiliser les bons de commande. En savoir plus sur [Créer des livraisons directes](sales-how-drop-shipment.md).

Pour tous les autres aspects, les bons de commande fonctionnent de la même manière que les factures achat. La procédure suivante se base sur une facture achat. La procédure est identique pour un bon de commande.

<br><br>

> [!Video https://www.microsoft.com/videoplayer/embed/RE4b3tt?rel=0]

## <a name="receive-items-with-a-purchase-order"></a>Pour réceptionner des articles avec un bon de commande

La section suivante décrit comment recevoir des articles avec un bon de commande. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de commande**, puis choisissez le lien associé.
2. Ouvrez un bon de commande existant, ou créez-en un nouveau.
3. Dans le champ **Qté à recevoir**, indiquez la quantité reçue.

   > [!NOTE]
   > Si la quantité reçue est supérieure à la quantité du bon de commande, et que le fournisseur a été configuré pour autoriser les sur-réceptions, utilisez le champ **Sur-réception** pour gérer la quantité excédentaire. Pour en savoir plus, consultez la section [Pour réceptionner plus d’articles que commandés](purchasing-how-record-purchases.md#receive-more-items-than-ordered).
4. Sélectionnez l'action **Valider**.

  La valeur du champ **Qté reçue** est mise à jour en conséquence. Si c’est une réception partielle, la valeur est inférieure à la valeur dans le champ **Quantité**.

> [!NOTE]
> Si vous utilisez un traitement entrepôt, vous ne pouvez pas utiliser l’action **Reporter** sur le bon de commande pour enregistrer la réception. La raison est qu’un employé d'entrepôt a déjà reporté la quantité du bon de commande telle que reçue. Learn more at [Détails de conception : flux d’enlogement](design-details-inbound-warehouse-flow.md).

## <a name="receive-more-items-than-ordered"></a>Réceptionner plus d’articles que commandés

Lorsque vous recevez plus de produits que commandés, vous pouvez les réceptionner au lieu d’annuler la réception. Par exemple, il peut être moins coûteux de conserver des articles dans l’inventaire que de les retourner, ou votre fournisseur peut vous proposer un rabais pour les conserver.

<!--move the over-receipt setup info to an article about purchasing. Keep the concept info here and link to the steps-->
### <a name="set-up-over-receipts"></a>Configurer des sur-réceptions

Créez des codes de sur-réception pour définir un pourcentage par lequel une quantité reçue peut dépasser la quantité commandée. Spécifiez le pourcentage dans le champ **% de tolérance de sur-réception**. Vous affectez ensuite le code sur les pages Fiche article ou Fiche fournisseur pour les articles et les fournisseurs.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Codes sur-réception.**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

### <a name="assign-the-over-receipt-code-to-an-item"></a>Attribuer le code de sur-réception à un article

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Ouvrez la page **Fiche article** pour l’article.
3. Dans le champ **Code de sur-réception**, choisissez le code qui contient le pourcentage que vous souhaitez autoriser pour les sur-réceptions.

Le code de sur-réception est affecté à l'article. Les bons de commande ou les réceptions entrepôt pour l’article vous permettent désormais de réceptionner une quantité supérieure à celle commandée, à hauteur du pourcentage de tolérance de sur-réception indiqué.

> [!NOTE]
> Vous pouvez configurer un flux de travail approbation pour exiger l’approbation des sur-réceptions avant leur traitement. Cochez la case **Approbation requise** sur la page **Codes de sur-réception**. En savoir plus sur [Créer des flux de projet](across-how-to-create-workflows.md).

### <a name="over-receive-an-order"></a>Sur-réception d’une commande

Sur les lignes achat et les lignes réception entrepôt, le champ **Quantité de sur-réception** permet d’enregistrer les quantités excédentaires reçues, c’est-à-dire les quantités dépassant la valeur dans le champ **Quantité**, la quantité commandée.

Lorsque vous traitez une sur-réception, vous pouvez augmenter la valeur dans le champ **Qté à recevoir** pour la faire correspondre à la quantité réellement reçue. Le champ **Quantité de sur-réception** se met à jour pour afficher la quantité excédentaire. Vous pouvez également saisir la quantité excédentaire dans le champ **Quantité de sur-réception**. Le champ **Qté à recevoir** se met à jour pour afficher la quantité commandée augmentée de la quantité excédentaire. La procédure suivante décrit comment renseigner le champ **Qté à recevoir**.  

1. Sur un bon de commande ou un document réception entrepôt où la quantité reçue est supérieure à celle commandée, saisissez la quantité réellement reçue dans le champ **Qté à recevoir**.

    Si l’augmentation est inférieure ou égale à la tolérance indiquée par le code de sur-réception attribué, le champ **Quantité de sur-réception** est mis à jour pour afficher la quantité de dépassement de la valeur dans le champ **Quantité**.

    Si l’augmentation est supérieure à la tolérance, la sur-réception n’est pas autorisée. Vérifiez si un autre code de sur-réception le permettra. Sinon, seule la quantité commandée peut être réceptionnée et la quantité excédentaire doit être traitée autrement, par exemple en la renvoyant au fournisseur.

2. Reportez la réception comme vous le feriez pour toute autre réception.

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] ne gère pas automatiquement les aspects financiers des sur-réceptions. Vous devez gérer cela manuellement en accord avec le fournisseur, qui peut par exemple vous envoyer une facture nouvelle ou mise à jour.

## <a name="external-document-number"></a>Numéro de document externe

[!INCLUDE [ext-doc-no-purch](includes/ext-doc-no-purch.md)]

## <a name="posting-purchases"></a>Report des achats

Sur un document achat, vous pouvez faire votre choix parmi les actions de report suivantes :

* **Reporter**
* **Aperçu report**
* **Valider et Imprimer**
<!--* **Test Report**-->
* **Valider par lot**

Lorsqu’un document achat est reporté, le compte du fournisseur, le grand livre, les écritures article et les écritures ressource sont mis à jour.

Pour chaque document achat, une écriture achat est créée dans la table **Écriture**. Une écriture est également créée dans le compte fournisseur de la table **Ecriture fournisseur** et une autre dans le compte fournisseur approprié. De plus, le report de l’achat peut entraîner la création d’une écriture TVA et d’une écriture pour le montant de l'escompte. Le report d'une écriture pour l'escompte dépend de la valeur du champ **Report escompte** de la table **Configuration des achats et des comptes à payer**.

Pour chaque ligne achat, les écritures suivantes sont créées :

* la table **Écriture article** si la ligne achat est de type **Article**.
* la table **Écriture** si la ligne achat est de type **Compte du grand livre**.
* la table **Écriture ressource** si la ligne achat est de type **Ressource**.

En outre, les documents achat sont toujours enregistrés dans les tables **En-tête réception achat** et **En-tête facture achat**.

Vous pouvez toujours consulter les différentes écritures qui seront créées à la suite des reports. Choisissez **Aperçu report** pour valider le document et inspecter les écritures attendues.


> [!IMPORTANT]  
> Lorsque vous reportez un bon de commande pour des articles, vous pouvez créer une réception et une facture. Celles-ci peuvent être faites simultanément ou séparément. Vous pouvez également créer une réception partielle et une facture partielle en renseignant les champs **Qté à recevoir** et **Qté à facturer** sur chaque ligne commande achat avant la validation. Notez que vous ne pouvez pas créer de facture d’achat à partir d’un bon de commande pour des produits ou des services qui n’ont pas été reçus. C'est-à-dire que, avant de pouvoir facturer, vous devez avoir validé une réception, ou vous devez choisir de réceptionner et de facturer en même temps.

Vous pouvez soit reporter, soit reporter et imprimer. Si vous choisissez de reporter et d’imprimer, un rapport est imprimé lorsque la commande est reportée. Vous pouvez aussi choisir l’action **Reporter par lot**, qui vous permet de reporter plusieurs commandes en même temps. Pour plus d'informations, voir [Reporter plusieurs documents en même temps](ui-batch-posting.md).

## <a name="viewing-ledger-entries"></a>Affichage des écritures

Lorsque le report est terminé, les lignes achat reportées sont supprimées de la commande. Un message vous indique lorsque le report est terminé. Vous pouvez ensuite afficher les écritures reportées dans les diverses pages qui contiennent les écritures reportées, comme les pages **Écritures fournisseur**, **Écritures**, **Écritures article**, **Écritures ressource**, **Réceptions achat** et **Factures achat reportées**.

Dans la plupart des cas, vous pouvez ouvrir des écritures à partir de la fiche ou du document concerné. Par exemple, sur la page **Fiche fournisseur**, sélectionnez l'action **Écritures**.

## <a name="editing-ledger-entries"></a>Modification des écritures

Vous pouvez modifier certains champs sur les documents achat reportés, tels que le champ **Référence de paiement**. Pour plus d'informations, voir [Modifier les documents reportés](across-edit-posted-document.md). Pour les champs plus critiques qui concernent la piste d'audit, vous devez inverser ou annuler le report. Pour plus d'informations, voir [Inverser des reports journal et annuler des réceptions/livraisons](finance-how-reverse-journal-posting.md).

## <a name="see-also"></a>Voir aussi .

[Demande de devis](purchasing-how-request-quotes.md)  
[Achat des articles pour une vente](purchasing-how-purchase-products-sale.md)  
[Préparer des livraisons directes](sales-how-drop-shipment.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Définition des achats](purchasing-setup-purchasing.md)  
[Paramétrer des ressources](projects-how-setup-resources.md)  
[Enregistrer de nouveaux fournisseurs](purchasing-how-register-new-vendors.md)  
[Modifier les documents reportés](across-edit-posted-document.md)  
[Reporter plusieurs documents en même temps](ui-batch-posting.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Validation des documents et des feuilles](ui-post-documents-journals.md)  
[Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
