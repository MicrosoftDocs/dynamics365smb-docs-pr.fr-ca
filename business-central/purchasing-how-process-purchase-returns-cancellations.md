---
title: Traiter les retours ou annulations
description: Explique comment créer et reporter une note de crédit achat lorsque vous souhaitez retourner des articles à un fournisseur ou annuler des services achetés.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'cancel, undo, correct'
ms.search.form: '6640, 6643, 9307, 9309, 9308, 6652, 145, 147'
ms.date: 04/01/2021
ms.author: edupont
---
# <a name="process-purchase-returns-or-cancellations"></a><a name="process-purchase-returns-or-cancellations"></a><a name="process-purchase-returns-or-cancellations"></a>Traiter les retours ou annulations d'achats

Si vous souhaitez retourner des articles à votre fournisseur ou annuler des services que vous avez achetés, vous pouvez créer et reporter une note de crédit achat qui indique la modification demandée par rapport à la facture achat d'origine. Pour inclure les informations de facture achat correctes, vous pouvez créer la note de crédit achat à partir de la facture achat reportée ou vous pouvez créer une note de crédit achat avec les informations copiées de la facture.

Si vous souhaitez davantage de contrôle sur le processus de retour achat, par exemple les documents entrepôt pour la manutention des articles ou une meilleure vue d'ensemble lors de la réexpédition d'articles à partir de plusieurs documents achat avec un retour achat, vous pouvez créer des retours achat. Un retour achat émet automatiquement la note de crédit achat associée. Pour plus d'informations, voir [Pour créer un retour achat à partir d'un ou de plusieurs documents achat reportés](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

> [!NOTE]  
> Si une facture achat reportée n'a pas encore été payée, vous pouvez utiliser les fonctions **Corriger** ou **Annuler** sur la facture achat reportée pour inverser automatiquement les transactions associées. Ces fonctions ne fonctionnent que pour les factures impayées, elles ne prennent pas en charge des retours partiels ou les annulations. Vous ne pouvez pas non plus corriger ou annuler les factures achat qui ont été reportées avec les reçus de plusieurs bons de commande. Pour plus d'informations, voir [Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md).

Généralement, vous pouvez créer une note de crédit achat ou un retour achat en réaction à une note de crédit que vous a envoyée un fournisseur. La note de crédit achat ou le retour achat tient lieu de documentation interne du processus de note de crédit aux fins de comptabilité ou pour contrôler la livraison des articles concernés.

La modification peut concerner tous les produits figurant sur la facture achat d'origine, ou uniquement certains d'entre eux. Par conséquent, vous pouvez partiellement renvoyer les articles reçus ou demander le remboursement partiel des services reçus. Dans ce cas, vous devez modifier les informations sur la note de crédit achat ou le retour achat.

Outre la facture achat reportée d'origine, vous pouvez affecter la note de crédit achat ou le retour achat à d'autres documents achat, par exemple une autre facture achat reportée, parce que vous renvoyez également des articles livrés avec cette facture.

La report de la note de crédit rétablira également tous les frais annexes affectés au document reporté, afin que les écritures valeur de l'article soient identiques à celles précédant l'affectation des frais annexes.

## <a name="inventory-costing"></a><a name="inventory-costing"></a><a name="inventory-costing"></a>Évaluation stock
Pour préserver l'évaluation correcte de l'inventaire, vous voudrez généralement prélever les articles retournés dans l'inventaire au coût unitaire auquel ils ont été achetés, et non à leur coût unitaire actuel. On appelle cela une inversion de même coût.

Vous pouvez affecter l'inversion de même coût automatiquement de deux façons.  

|Fonction.|Description|  
|------------------|---------------------------------------|  
|Fonction **Afficher des lignes document reportées à inverser** sur la page **Retour commande achat**|Copie les lignes d'un ou de plusieurs documents reportés afin de les inverser dans le retour achat. Pour plus d'informations, voir la section [Pour créer un retour achat à partir d'un ou plusieurs documents achat reportés](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents).|  
|Fonction **Copier à partir du document** des pages **Note de crédit achat** et **Retour achat**|Copie l'en-tête et les lignes d'un document reporté à inverser.<br /><br /> Requiert que la case à cocher **Coût d'inversion exact obligatoire** soit sélectionnée sur la page **Configuration achats et à payer**.|

Pour réaliser manuellement l'inversion exacte, sélectionnez **Écriture article à affecter** sur n'importe quelle ligne de document retour, puis sélectionnez le numéro de l'écriture achat initiale. Cela crée un lien entre la note de crédit achat ou le retour achat et l'écriture achat initiale, et garantit que l'article est évalué en fonction du coût unitaire initial.

Pour plus d'informations, voir [Détails de conception : Évaluation stock](design-details-inventory-costing.md).

## <a name="to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice"></a><a name="to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice"></a><a name="to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice"></a>Pour créer une note de crédit achat à partir d'une facture achat reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat reportées**, puis sélectionnez le lien associé.  
2. Sur la page **Factures achat reportées**, sélectionnez la facture achat reportée que vous souhaitez inverser, puis sélectionnez l'action **Créer une note de crédit de correction**.

    La plupart des champs de l'en-tête de la note de crédit achat sont renseignés avec les informations de la facture achat reportée. Vous pouvez modifier tous les champs, par exemple avec de nouvelles informations qui reflètent l'entente de retour.
3. Modifiez les informations des lignes en fonction de l'entente, par exemple le nombre d'articles retournés ou le montant à rembourser.
4. Sélectionnez l'action **Lettrer écritures**.
5. Sur la page **Affecter écritures fournisseur**, sélectionnez la ligne contenant le document achat reporté auquel vous souhaitez affecter la note de crédit achat, puis sélectionnez l'action **Code référence**. Le numéro de l'avoir achat est inséré dans le champ **ID lettrage**.
6. Dans le champ **Montant à lettrer**, entrez le montant à lettrer s'il est inférieur au montant initial.

    Au bas de la page **Affecter écritures fournisseur**, vous pouvez afficher le montant total à affecter pour inverser toutes les écritures concernées, à savoir lorsque la valeur du champ **Solde** est égale à zéro.
7. Cliquez sur le bouton **OK**. Lorsque vous reportez la note de crédit achat, elle est affectée aux documents achat reportés spécifiés.

    Lorsque vous avez créé ou modifié les lignes note de crédit achat nécessaires et qu'une ou plusieurs applications sont spécifiées, vous pouvez procéder au report de la note de crédit achat.
8. Sélectionnez l'action **Valider**.

Les factures achat reportées auxquelles vous affectez la note de crédit sont à présent inversées. Si vous avez déjà payé la facture initiale, le fournisseur doit maintenant rembourser le paiement en votre faveur. Si la note de crédit est uniquement pour une partie du produit dans la facture initiale, vous pouvez payer uniquement le montant restant de la facture achat d'origine pour la fermer.

La note de crédit achat est supprimée et remplacée par un nouveau document dans la liste des notes de crédit achat reportées.

## <a name="to-create-a-purchase-credit-memo-by-copying-a-posted-purchase-invoice"></a><a name="to-create-a-purchase-credit-memo-by-copying-a-posted-purchase-invoice"></a><a name="to-create-a-purchase-credit-memo-by-copying-a-posted-purchase-invoice"></a>Pour créer une note de crédit achat en copiant une facture achat reportée

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit achat**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir achat vierge.
3. Dans le champ **Fournisseur**, entrez le nom d'un fournisseur existant.
4. Sélectionnez l'action **Copier à partir du document**.
5. Sur la page **Extraire document achat**, dans le champ **Type document**, sélectionnez **Facture reportée**.
6. Sélectionnez le champ **N° document** pour ouvrir la page **Factures achat reportées**, puis sélectionnez la facture achat reportée qui contient les lignes que vous souhaitez inverser.
7. Activez la case à cocher **Recalculer lignes** si vous souhaitez que les lignes facture achat validées copiées soient mises à jour avec les modifications apportées au prix article et au coût unitaire depuis la validation de la facture.
8. Cliquez sur le bouton **OK**. Les lignes facture copiées sont insérées dans la note de crédit achat.
9. Remplissez la note de crédit achat en vous reportant à la procédure [Pour créer une note de crédit achat à partir d'une facture achat reportée](purchasing-how-process-purchase-returns-cancellations.md#to-create-a-purchase-credit-memo-from-a-posted-purchase-invoice).

## <a name="to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents"></a><a name="to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents"></a><a name="to-create-a-purchase-return-order-based-on-one-or-more-posted-purchase-documents"></a>Pour créer un retour achat à partir d'un ou de plusieurs documents achat reportés

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Retours achat**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs dans le raccourci **Général** selon les besoins.
4. Dans le raccourci **Lignes**, renseignez les lignes manuellement, ou copiez des informations d'autres documents pour renseigner les lignes automatiquement :

    - Utilisez la fonction **Extraire les lignes de document reportées à inverser** pour copier une ou plusieurs lignes de document reportées à partir d'un ou de plusieurs documents reportés. Cette fonction inverse toujours exactement les coûts à partir de la ligne de document reportée. Cette fonction est décrite dans les étapes suivantes.    
    - Utilisez la fonction **Copier à partir du document** pour copier un document existant dans le retour. Cette fonction permet de copier l'ensemble du document. Il peut s'agir d'un document reporté ou d'un document non encore reporté. Cette fonction ne permet l'inversion de même coût que lorsque la case **Inversion de même coût obligatoire** est cochée sur la page **Config. ventes et à recevoir**.  

5. Sélectionnez l'action **Extraire les lignes de document reportées à inverser**.
6. Dans le haut de la page **Lignes document achat reportées**, cochez la case **Afficher uniquement lignes réversibles** si vous voulez n'afficher que les lignes contenant des quantités qui n'ont pas encore été retournées, ou s'il s'agit de lignes achat, vendues ou consommées. Par exemple, si une quantité de facture achat reportée a déjà été retournée, il se peut que vous ne vouliez pas intégrer cette quantité dans un nouveau document retour achat.

    > [!NOTE]  
    >  Ce champ ne fonctionne que pour les réceptions reportées et les lignes facture reportées, pas pour les lignes retour reportées ni les lignes note de crédit reportées.  

    Dans la partie gauche de la page, les différents types de document sont énumérés, et le nombre entre parenthèses est le nombre de documents disponibles de chaque type de document.

7. Dans le champ **Filtre de type de document**, sélectionnez le type de lignes document validées que vous souhaitez utiliser.  
8. Sélectionnez les lignes que vous voulez copier vers le nouveau document.  

    > [!NOTE]  
    >  Si vous utilisez <kbd>Ctrl</kbd>+<kbd>A</kbd> pour sélectionner toutes les lignes, toutes les lignes à l’intérieur du filtre que vous avez défini sont copiées mais le filtre **Afficher uniquement quantité réversible** n’est pas pris en considération. Par exemple, supposons que vous ayez filtré les lignes pour un numéro de document particulier comportant deux lignes, dont l'une a déjà été retournée. Même si le champ **Afficher uniquement quantité réversible** est sélectionné, si vous sélectionnez <kbd>Ctrl</kbd>+<kbd>A</kbd> pour copier toutes les lignes, deux lignes sont copiées au lieu de celle qui n’a pas encore été inversée.  

9. Sélectionnez le bouton **OK** pour copier les lignes dans le nouveau document.  

    Les traitements suivants se produisent :  

    - Pour les lignes document validées du type **Article**, une ligne document est créée qui est une copie de la ligne document validée, avec la quantité qui n'a pas encore été contrepassée. Le champ **Écr. article à affecter** est renseigné correctement avec le numéro de l'écriture article de la ligne document reportée.  

    - Pour les lignes document validées qui ne sont pas du type **Article** (telles que les frais annexes), une ligne document est créée qui est une copie de la ligne document validée originale.  

    - Calcule le champ **Coût unitaire $** sur la nouvelle ligne à partir des coûts des écritures article correspondantes.  

    - Si le document copié est une livraison reportée, une réception reportée, une réception retour reportée ou une livraison retour reportée, le prix unitaire est calculé automatiquement à partir de la fiche article.  

    - Si le document copié est une facture ou une note de crédit reportée, le prix unitaire, les escomptes de la facture et les escomptes de paiement ligne sont copiés à partir de la ligne document reportée.  

    - Si la ligne document reportée contient des lignes traçabilité, le champ **Écr. article à affecter** sur les lignes traçabilité est renseigné à l'aide des numéros d'écriture article appropriés des lignes traçabilité reportées.  

     Lors de la copie à partir d'une facture ou d'une note de crédit reportée, l'application copie les escomptes facture et les escomptes ligne adéquats comme valides au moment du report de ce document, de la ligne document reportée vers la nouvelle ligne document. Notez toutefois que si l'option **Calculer escompte facture** est activée sur la page **Configuration des achats et des comptes à payer**, l'escompte facture est de nouveau calculé lorsque vous reportez la nouvelle ligne document. Le montant ligne de la nouvelle ligne peut par conséquent être différent du montant ligne de la ligne document reportée, en fonction du nouveau calcul de l'escompte facture.  

    > [!NOTE]  
    >  Si une partie de la quantité de la ligne document reportée a déjà été inversée ou vendue ou consommée, une ligne n'est créée que pour la quantité restant en inventaire qui n'a pas encore été renvoyée. Si la quantité totale de la ligne document reportée a déjà été inversée, aucune ligne document n'est créée.  
    >
    >  Si le flux de biens dans le document reporté est identique au flux de biens dans le nouveau document, une copie de la ligne document reportée originale est simplement créée dans le nouveau document. Le champ **Écriture article à lettrer** n'est pas renseigné parce que, dans ce cas, l'inversion de même coût n'est pas possible. Par exemple, si vous utilisez la fonction **Extraire les lignes de document reportées à inverser** pour afficher une ligne note de crédit achat reportée pour une nouvelle note de crédit achat, seule la ligne note de crédit reportée originale est copiée sur la nouvelle note de crédit.  

10. Sur la page **Retour achat**, dans le champ **Code motif retour** de chaque ligne, sélectionnez le motif de ce retour.
11. Sélectionnez l'action **Valider**.

## <a name="to-create-a-replacement-purchase-order-from-a-purchase-return-order"></a><a name="to-create-a-replacement-purchase-order-from-a-purchase-return-order"></a><a name="to-create-a-replacement-purchase-order-from-a-purchase-return-order"></a>Pour créer une bon de commande de remplacement à partir d'un retour commande achat

Vous pouvez vous accorder avec le fournisseur pour qu'il compense l'achat d'un article en remplaçant cet article. L'article de remplacement peut être identique à l'article d'origine ou il peut être différent. Le fournisseur peut vous avoir livré par erreur le mauvais article.  

1.  Sur la page **Retour achat** pour un processus de retour actif, sur une ligne vide, entrez une écriture négative pour l'article de remplacement en insérant un montant négatif dans le champ **Quantité**.  
2. Sélectionnez l'action **Déplacer lignes négatives**.  
3. Sur la page **Déplacer lignes achat nég.**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**. La ligne négative est effacée du retour achat et un nouveau bon de commande est créé. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).  

## <a name="to-create-a-purchase-allowance"></a><a name="to-create-a-purchase-allowance"></a><a name="to-create-a-purchase-allowance"></a>Pour créer un rabais

Si vous recevez de votre fournisseur des articles que vous ne souhaitez pas, par exemple s'ils sont légèrement endommagés, ou s'ils ne sont pas de la bonne couleur ou de la bonne taille, le fournisseur peut vous proposer un rabais.  

Vous pouvez reporter ce coût d'achat réduit en tant que frais annexes sur une note de crédit ou un retour et le lier à la réception reportée. Ce qui suit décrit la procédure pour un retour achat, mais la même procédure s'applique à une note de crédit achat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit achat**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau** pour ouvrir un nouvel avoir achat vierge.  
3. Renseignez l'en-tête note de crédit à l'aide des informations relatives au fournisseur qui vous a envoyé le rabais.  
4. Dans le champ **Type** du raccourci **Lignes**, sélectionnez **Frais annexes**.  
5. Dans le champ **N°**, sélectionnez la valeur de frais annexes appropriée.  

    Vous pouvez créer un numéro de frais annexes spécial afin de couvrir les rabais.  
6. Dans le champ **Quantité**, saisissez **1**.  
7. Dans le champ **Coût unitaire direct**, saisissez le montant du rabais.  
8. Affectez le rabais en tant que frais annexes aux articles de la réception reportée. Pour plus d'informations, voir [Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md). Une fois ce rabais affecté, revenez à la page **Note de crédit achat**.

Lorsque vous reportez le retour achat, le rabais sur l'achat est ajouté au montant de l'écriture achat appropriée. De cette manière, vous pouvez maintenir la précision de l'évaluation de l'inventaire.  

## <a name="to-combine-return-shipments"></a><a name="to-combine-return-shipments"></a><a name="to-combine-return-shipments"></a>Pour regrouper les expéditions retour

Pour retourner des articles couverts par différents retours achat au même fournisseur, vous pouvez utiliser la fonction **Regrouper les expéditions retour**.  

Lorsque vous livrez ces articles, vous reportez les commandes retour achat associées comme étant livrées, ce qui crée des livraisons retour achat reportées.  

Lorsque vous êtes prêt à facturer ces articles, au lieu de facturer séparément chaque retour achat, vous pouvez créer une note de crédit achat et copier automatiquement dans ce document les lignes livraison retour achat reportées. Il vous suffit alors de reporter la note de crédit achat et de facturer en une fois tous les retours achat ouverts.  

Lorsque des livraisons retour sont regroupées sur une note de crédit et reportées, une note de crédit achat reportée est créé pour les lignes facturées. Le champ **Quantité facturée** sur le retour achat d'origine est mis à jour en fonction de la quantité facturée. Comme ce retour achat d'origine n'est toutefois pas supprimé, même s'il a été entièrement reçus et facturés, vous devez supprimer le retour achat manuellement.

> [!NOTE]  
> Dans la procédure suivante, on suppose qu'il existe plusieurs retours achat pour le fournisseur et qu'ils ont été reportés comme étant livrés.     

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Notes de crédit achat**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Sur le raccourci **Général**, complétez les champs, comme nécessaire.  
4. Choisissez l'action **Extraire les lignes de livraison de retour**.  
5. Sélectionnez plusieurs lignes livraison retour que vous souhaitez inclure dans la facture.  

    Si une ligne expédition retour incorrecte a été sélectionnée ou que vous souhaitez recommencer, il vous suffit de supprimer les lignes de l'avoir achat et de réutiliser la fonction **Extraire lignes expédition retour**.  
6. Sélectionnez l'action **Valider**.  

### <a name="to-remove-open-purchase-return-orders-after-combined-return-shipment-posting"></a><a name="to-remove-open-purchase-return-orders-after-combined-return-shipment-posting"></a><a name="to-remove-open-purchase-return-orders-after-combined-return-shipment-posting"></a>Pour supprimer des retours achat ouverts après le report de livraisons retour groupées

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Supprimer retours achat facturé**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.  
3. Vous pouvez également supprimer chacun des retours achat manuellement.

## <a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/return-items-dynamics-365-business-central/) associée

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Enregistrer des achats](purchasing-how-record-purchases.md)  
[Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
