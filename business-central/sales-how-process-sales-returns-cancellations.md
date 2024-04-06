---
title: Traiter les retours ou annulations de ventes
description: 'Décrit comment créer une note de crédit vente pour traiter un retour, une annulation ou un remboursement pour les articles ou les services qui vous ont déjà été payés.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'undo, credit memo, return'
ms.search.form: '44, 134, 143, 6629, 6630, 6633, 6662, 9302, 9304, Report_6646'
ms.date: 09/27/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="process-sales-returns-or-cancellations"></a>Traiter les retours ou annulations de ventes

Si votre client souhaite retourner des articles ou obtenir un remboursement pour des articles, ou encore annuler des services, que vous lui avez vendus et pour lesquels vous avez reçu un paiement, vous devez créer et reporter une note de crédit vente qui indique la modification demandée. Pour inclure les informations correctes sur la facture vente, vous pouvez procéder comme suit :  

- Créer la note de crédit vente directement à partir de la facture vente reportée.
- Créer une note de crédit vente avec les informations copiées de la facture.

Si vous souhaitez davantage de contrôle sur le processus de retour vente, par exemple les documents entrepôt pour la manutention des articles, ou une meilleure vue d’ensemble lors de la réception d’articles à partir de plusieurs documents vente avec un retour vente, vous pouvez créer des retours vente. Un retour vente émet automatiquement la note de crédit vente associée et les autres documents relatifs au retour, comme un document de vente de remplacement, le cas échéant. Pour plus de détails, reportez-vous à la rubrique [Traiter les retours vente](sales-how-process-sales-returns-orders.md).

> [!NOTE]  
> Si une facture vente reportée n'a pas encore été payée, vous pouvez utiliser les fonctions **Corriger** ou **Annuler** sur la facture vente reportée pour inverser automatiquement les transactions associées. Ces fonctions ne fonctionnent que pour les factures impayées, elles ne prennent pas en charge des retours partiels ou les annulations. Pour plus d'informations, voir [Corriger ou annuler des factures vente impayées](sales-how-correct-cancel-sales-invoice.md).

Un retour ou un remboursement peut en effet se rapporter uniquement à certains des articles ou des services figurant sur la facture vente initiale. Dans ce cas, vous devez modifier les informations des lignes de la note de crédit vente ou du retour vente. Lors du report de la note de crédit vente ou du retour vente, les documents vente affectés par la modification sont inversés et un paiement de remboursement peut être créé pour le client. Pour plus d'informations, reportez-vous à [Effectuer des paiements](payables-make-payments.md).  

La report de la note de crédit rétablira également tous les frais annexes affectés au document reporté, afin que les écritures valeur de l'article soient identiques à celles précédant l'affectation des frais annexes.

> [!NOTE]
> Les aspects comptables des retours de ventes, tels que les paiements aux clients à titre de remboursement, sont considérés comme des travaux comptables et ne sont pas décrits ici. Pour plus d'informations, reportez-vous à [Gestion des comptes fournisseur](payables-manage-payables.md).

## <a name="to-create-a-sales-credit-memo-from-a-posted-sales-invoice"></a>Pour créer une note de crédit vente à partir d'une facture vente reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures vente reportées**, puis sélectionnez le lien associé.  
2. Sur la page **Factures vente reportées**, sélectionnez la facture vente reportée que vous souhaitez inverser, sélectionnez l’action **Annuler**, puis l’action **Créer une note de crédit corrective**.

    L'en-tête de la note de crédit vente affiche des informations sur la facture vente reportée. Vous pouvez les modifier, par exemple avec de nouvelles informations qui reflètent l'entente de retour.  
3. Modifiez les informations des lignes en fonction de l'entente, par exemple le nombre d'articles retournés ou le montant à rembourser.
4. Sélectionnez l’action **Préparer**, puis sélectionnez l’action **Affecter écritures**.
5. Sur la page **Affecter écritures client**, sélectionnez la ligne contenant le document vente reporté auquel vous souhaitez affecter la note de crédit vente, puis sélectionnez l'action **Code référence**.

    L'identifiant de l'avoir vente s'affiche dans le champ **ID lettrage**.
6. Dans le champ **Montant à lettrer**, entrez le montant à lettrer s'il est inférieur au montant initial.  

    Au bas de la page **Affecter écritures client**, vous pouvez afficher le montant total à affecter pour inverser toutes les écritures concernées, à savoir lorsque la valeur du champ **Solde** est égale à zéro.
7. Cliquez sur le bouton **OK**. Lors du report de la note de crédit vente, elle est affectée aux documents vente reportés.

    Après que vous avez créé ou modifié les lignes note de crédit vente et spécifié une ou plusieurs applications, vous pouvez procéder au report de la note de crédit vente.  
8. Choisissez l’action **Report**, puis sélectionnez l’action **Reporter et envoyer**.  

La boîte de dialogue **Valider et envoyer la confirmation** s'ouvre et indique le mode d'envoi par défaut du client. Vous pouvez modifier le mode d'envoi en cliquant sur le bouton de recherche pour le champ **Envoyer le document à**. Pour plus d'informations, reportez vous à [Configurer des profils d'envoi de documents](sales-how-setup-document-send-profiles.md).  

Les documents vente reportés auxquels vous avez affecté la note de crédit sont à présent inversés, et un remboursement peut être créé pour le client. La note de crédit vente est supprimée et remplacée par un nouveau document dans la liste des notes de crédit vente reportées.

## <a name="to-create-a-sales-credit-memo-by-copying-a-posted-sales-invoice"></a>Pour créer une note de crédit vente en copiant une facture vente reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit vente**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir vente vierge.
3. Dans le champ **Nom client**, entrez le nom d’un client existant.
4. Sélectionnez l’action **Préparer**, puis sélectionnez l’action **Copier document**.
5. Sur la page **Copier document vente**, dans le champ **Type document**, sélectionnez **Facture reportée**.
6. Sélectionnez le champ **N° document** pour ouvrir la page **Factures vente reportées**, puis sélectionnez l’enregistrement de facture vente reportée qui contient les lignes que vous souhaitez inverser.
7. Activez la case à cocher **Recalculer lignes** si vous souhaitez que les lignes facture vente validées copiées soient mises à jour avec les modifications apportées au prix article et au coût unitaire depuis la validation de la facture.
8. Cliquez sur le bouton **OK**. Les lignes facture copiées sont insérées dans la note de crédit vente.
9. Remplissez la note de crédit vente en vous reportant à la procédure [Pour créer une note de crédit vente à partir d'une facture vente reportée](sales-how-process-sales-returns-cancellations.md#to-create-a-sales-credit-memo-from-a-posted-sales-invoice).

## <a name="to-create-a-sales-allowance"></a>Pour créer des frais de vente
Vous pouvez envoyer une note de crédit à un client avec une réduction si le client a reçu des articles légèrement endommagés ou avec du retard.  
Vous pouvez reporter ce prix réduit en tant que frais annexes dans une note de crédit ou un retour et l'affecter à la livraison reportée. Ce qui suit décrit la procédure pour une note de crédit vente, mais la même procédure s'applique à un retour vente.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit vente**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir vente vierge.
3. Renseignez l'en-tête note de crédit avec les informations appropriées sur le client à qui vous accordez un rabais sur ventes.  
4. Dans le champ **Type** du raccourci **Lignes**, sélectionnez **Frais annexes**.  
5. Dans le champ **N°**, sélectionnez la valeur de frais annexes appropriée.  
     Vous pouvez créer un numéro frais annexes spécial pour couvrir les rabais sur ventes.  
6. Dans le champ **Quantité**, saisissez **1**.  
7. Dans le champ **Prix unitaire HT**, saisissez le montant du rabais sur ventes.  
8. Affectez les frais de vente en tant que frais annexes aux articles de la livraison reportée. Pour plus d'informations, voir [Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md). Une fois ce rabais affecté, revenez à la page **Note de crédit vente**.  

Lorsque vous reportez le retour vente, le rabais sur la vente est ajouté au montant de l'écriture vente appropriée. De cette manière, vous pouvez maintenir la précision de l'évaluation de l'inventaire.

## <a name="to-combine-return-receipts"></a>Pour regrouper des réceptions retour
Vous pouvez regrouper des réceptions retour si votre client retourne plusieurs articles couverts par différentes commandes retour vente.  

Lorsque vous recevez les articles dans votre entrepôt, reportez les retours vente concernés comme reçus. Cela crée des réceptions retour reportées.  

Lorsque vous êtes prêt à facturer ce client, au lieu de facturer chaque commande retour vente séparément, vous pouvez créer une note de crédit vente et copier automatiquement les lignes réception retour reportées dans ce document. Vous pouvez ensuite reporter la note de crédit et facturer facilement toutes les retours vente ouverts en même temps.  

Pour regrouper les réceptions retour, activez la case à cocher **Combiner les livraisons** sur la page **Fiche client**.  

### <a name="to-manually-combine-return-receipts"></a>Pour regrouper manuellement des réceptions retour

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit vente**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire.  
4. Choisissez l'action **Extraire lignes récept. retour**.  
5. Sélectionnez les lignes réception retour à inclure dans la note de crédit:  

    - Pour insérer toutes les lignes, sélectionnez-les toutes et sélectionnez le bouton **OK**.  

    - Pour insérer des lignes spécifiques, sélectionnez-les et sélectionnez le bouton **OK**.  
6.  Si une ligne livraison incorrecte a été sélectionnée ou si vous voulez recommencer, supprimez simplement les lignes de la note de crédit, puis exécutez de nouveau la fonction **Extraire lignes réception retour**.  
7.  Reportez la facture.  

### <a name="to-automatically-combine-return-receipts"></a>Pour regrouper automatiquement des réceptions retour

Vous pouvez regrouper automatiquement des réceptions retour et avez la possibilité de reporter automatiquement les notes de crédit à l'aide de la fonction **Regrouper réceptions retour**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Regrouper réceptions retour**, puis sélectionnez le lien associé.
2. Sur la page **Regrouper réceptions retour**, renseignez les champs pour choisir les réceptions retour appropriées.
3. Cochez la case **Reporter notes de crédit**. Sinon, vous devrez reporter manuellement les notes de crédit achat qui en résulteront.
4. Cliquez sur le bouton **OK**.  

### <a name="to-remove-a-received-and-invoiced-return-order"></a>Pour supprimer un retour reçu et facturé

Lorsque vous facturez des réceptions retour de cette manière, les commandes retour à partir desquelles les réceptions retour ont été reportées continuent à exister, même si elles ont été entièrement reçues et facturées.  

Lorsque des réceptions retour sont regroupées sur une note de crédit et reportées, une note de crédit reportée est créé pour les lignes créditées. Le champ **Quantité facturée** dans le retour vente d'origine est mis à jour sur la base de la quantité facturée.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Supprimer retours vente facturé**, puis sélectionnez le lien associé.  
2. Dans le champ de filtre **N°**, spécifiez les retours vente à supprimer.  
3. Cliquez sur le bouton **OK**.  

Vous pouvez également supprimer chacune des commandes retour vente manuellement.  

## <a name="inventory-costing"></a>Évaluation stock

Pour préserver l'évaluation correcte de l'inventaire, vous voudrez généralement remettre les articles retournés dans l'inventaire au coût unitaire auquel ils ont été vendus, et non à leur coût unitaire actuel. On appelle cela une inversion de même coût.

Vous pouvez affecter l’inversion de même coût automatiquement de deux façons :  

|Fonction.|Description|  
|------------------|---------------------------------------|  
|Fonction**Extraire des lignes document reportées à inverser** sur la page **Retour vente**|Copie les lignes d'un ou plusieurs documents reportés afin de les inverser dans le retour vente. Pour plus d’informations, voir la section [Créer un retour vente à partir d’un ou de plusieurs documents vente reportés](sales-how-process-sales-returns-orders.md#create-a-sales-return-order-based-on-one-or-more-posted-sales-documents).|  
|Fonction**Copier document** des pages **Note de crédit vente** et **Retour vente**|Copie l'en-tête et les lignes d'un document reporté à inverser.<br /><br /> Requiert que la case à cocher **Coût d'inversion exact obligatoire** soit sélectionnée sur la page **Configuration ventes & à recevoir**.|

Pour réaliser manuellement l'inversion exacte, sélectionnez **Écriture article à affecter** sur n'importe quelle ligne de document retour, puis sélectionnez le numéro de l'écriture vente initiale. Cela crée un lien entre la note de crédit vente ou le retour vente et l'écriture vente initiale, et garantit que l'article est évalué en fonction du coût unitaire initial.

Pour plus d'informations, voir [Détails de conception : Évaluation stock](design-details-inventory-costing.md).

## <a name="see-also"></a>Voir aussi

[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Envoi de documents par courriel](ui-how-send-documents-email.md)  
[Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
