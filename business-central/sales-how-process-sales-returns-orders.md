---
title: Traitement des ordres de retour vente
description: 'Décrit comment créer un retour vente pour traiter un retour, une annulation, ou un remboursement pour les articles ou les services qui vous ont déjà été payés.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'undo, credit memo, return, order'
ms.search.form: '44, 134, 144, 6629, 6630, 6633, 6662, 9302, 9304, Report_6646'
ms.date: 03/05/2024
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Traitement des ordres de retour vente  

Si vous souhaitez davantage de contrôle sur le processus de retour vente, par exemple les documents entrepôt pour la manutention des articles, ou une meilleure vue d’ensemble lors de la réception d’articles à partir de plusieurs documents vente avec un retour vente, vous pouvez créer des retours vente. Un retour vente émet automatiquement la note de crédit vente associée et les autres documents relatifs au retour, comme un document de vente de remplacement, le cas échéant.

Outre la facture vente reportée d'origine, vous pouvez affecter la note de crédit vente ou le retour vente à d'autres documents vente, par exemple une autre facture vente reportée, parce que le client renvoie également des articles livrés avec cette facture.

## Créer un retour vente à partir d’un ou de plusieurs documents vente reportés  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Retours vente**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs dans le raccourci **Général** selon les besoins.
4. Dans le raccourci **Lignes**, renseignez les lignes manuellement, ou copiez des informations d'autres documents pour renseigner les lignes automatiquement :

    - Utilisez la fonction **Extraire les lignes de document reportées à inverser** pour copier une ou plusieurs lignes de document reportées à partir d'un ou de plusieurs documents reportés. Cette fonction inverse toujours exactement les coûts à partir de la ligne de document reportée. Cette fonction est décrite dans les étapes suivantes.    
    - Utilisez la fonction **Copier à partir du document** pour copier un document existant dans le retour. Cette fonction permet de copier l'ensemble du document. Il peut s’agir d’un document reporté ou d’un document non encore reporté. Cette fonction ne permet l’inversion de coût exacte que si la case **Inversion coût exacte obligatoire** est cochée sur la page **Configuration ventes**.  

5. Choisissez l’action **Traiter**, puis choisissez l’action **Afficher des lignes document reportées à inverser**.
6. Dans le haut de la page **Lignes document vente reportées**, cochez la case **Afficher uniquement lignes réversibles** si vous voulez n’afficher que les lignes contenant des quantités qui n’ont pas encore été retournées. Par exemple, si une quantité de facture vente reportée a déjà été retournée, il se peut que vous ne vouliez pas retourner cette quantité sur un nouveau document retour vente.

    > [!NOTE]  
    >  Ce champ ne fonctionne que pour les livraisons reportées et les lignes facture reportées, pas pour les lignes retour reportées ni les lignes note de crédit reportées.

    Dans la partie gauche de la page, les différents types de document sont énumérés, et le nombre entre parenthèses est le nombre de documents disponibles de chaque type de document.

7. Dans le champ **Filtre de type de document**, sélectionnez le type de lignes document validées que vous souhaitez utiliser.  
8. Sélectionnez les lignes que vous voulez copier vers le nouveau document.  

    > [!NOTE]  
    >  Si vous utilisez <kbd>Ctrl</kbd>+<kbd>A</kbd> pour sélectionner toutes les lignes, toutes les lignes à l’intérieur du filtre que vous avez défini sont copiées mais le filtre **Afficher uniquement quantité réversible** n’est pas pris en considération. Par exemple, supposons que vous ayez filtré les lignes pour un numéro de document particulier comportant deux lignes, dont l'une a déjà été retournée. Même si le champ **Afficher uniquement quantité réversible** est sélectionné, si vous sélectionnez <kbd>Ctrl</kbd>+<kbd>A</kbd> pour copier toutes les lignes, deux lignes sont copiées au lieu de celle qui n’a pas encore été inversée.  

9. Sélectionnez le bouton **OK** pour copier les lignes dans le nouveau document.  

    Les traitements suivants se produisent :  

    -   Pour les lignes document reportées du type **Article**, une ligne document est créée qui est une copie de la ligne document reportée, avec la quantité qui n’a pas encore été inversée. Le champ **Écriture article à affecter** est renseigné correctement avec le numéro de l'écriture du grand livre d'articles de la ligne document reportée.  

    -   Pour les lignes document reportées qui ne sont pas du type **Article** (telles que les frais annexes), une ligne document est créée qui est une copie de la ligne document reportée originale.  

    -   Calcule le champ **Coût unitaire $** sur la nouvelle ligne à partir des coûts des écritures article correspondantes.  

    -   Si le document copié est une livraison reportée, une réception reportée, une réception retour reportée ou une livraison retour reportée, le prix unitaire est calculé automatiquement à partir de la fiche article.  

    -   Si le document copié est une facture ou une note de crédit reportée, le prix unitaire, les escomptes de la facture et les escomptes de paiement ligne sont copiés à partir de la ligne document reportée.  

    -   Si la ligne document reportée contient des lignes traçabilité, le champ **Écriture article à affecter** sur les lignes traçabilité est renseigné à l'aide des numéros d'écriture du grand livre d'articles appropriés des lignes traçabilité reportées.  

     Lors de la copie à partir d'une facture ou d'une note de crédit reportée, l'application copie les escomptes facture et les escomptes ligne adéquats comme valides au moment du report de ce document, de la ligne document reportée vers la nouvelle ligne document. Notez toutefois que si l'option **Calculer escompte facture** est activée sur la page **Configuration des ventes et des comptes à recevoir**, l'escompte facture est de nouveau calculé lorsque vous reportez la nouvelle ligne document. Le montant ligne de la nouvelle ligne peut par conséquent être différent du montant ligne de la ligne document reportée, en fonction du nouveau calcul de l’escompte facture.  

     > [!NOTE]  
     >  Si une partie de la quantité de la ligne document reportée a déjà été inversée ou vendue ou consommée, une ligne n'est créée que pour la quantité restant en inventaire qui n'a pas encore été renvoyée. Si la quantité totale de la ligne document reportée a déjà été inversée, aucune ligne document n'est créée.  
     >   
     >  Si le flux de biens dans le document reporté est identique au flux de biens dans le nouveau document, une copie de la ligne document reportée originale est simplement créée dans le nouveau document. Le champ **Écriture article à lettrer** n'est pas renseigné parce que, dans ce cas, l'inversion de même coût n'est pas possible. Par exemple, si vous utilisez la fonction **Afficher des lignes document validées à contrepasser** pour afficher une ligne avoir vente validée pour un nouvel avoir vente, seule la ligne avoir vente validée originale est copiée dans le nouvel avoir.  

10. Sur la page **Retour vente**, dans le champ **Code motif retour** de chaque ligne, sélectionnez le motif de ce retour.
11. Sélectionnez l'action **valider**.

## Pour créer un document de vente de remplacement à partir d'un retour vente
Vous pouvez décider de compenser la vente d’un article au client en remplaçant cet article. Vous pouvez le remplacer par le même article ou par un autre. Cette situation survient, par exemple, si vous avez par erreur livré un mauvais article au client.  

1. Sur la page **Retour vente** pour un processus de retour actif, sur une ligne vide, entrez une écriture négative pour l'article de remplacement en insérant un montant négatif dans le champ **Quantité**.  
2. Sélectionnez l'action **Déplacer lignes négatives**.
3. Sur la page **Déplacer lignes vente nég.**, renseignez les champs selon vos besoins.
4. Cliquez sur le bouton **OK**. La ligne négative pour l'article de remplacement est supprimée de la commande retour vente et insérée sur une nouvelle page **Document de vente**. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).

## Pour créer des documents associés au retour depuis un retour vente
Vous pouvez faire en sorte de créer automatiquement tous les documents de vente, retours achat et bons de commande de remplacement au cours du processus de retour vente. Cela est utile, par exemple, dans les situations où vous voulez gérer des articles bénéficiant des garanties fournies par les fournisseurs.

1. Sur la page **Retour vente** pour un processus de retour actif, choisissez l'action **Créer documents associés retour**.
2. Dans le champ **N° fournisseur**, saisissez le numéro d'un fournisseur si vous souhaitez créer les documents du fournisseur automatiquement.
3. Si vous devez retourner un article retourné au fournisseur, activez la case à cocher **Créer retour achat**.
4. Si vous devez commander un article retourné au fournisseur, activez la case à cocher **Créer bon de commande**.
5. Si vous devez créer un document de vente de remplacement, activez la case à cocher **Créer un document de vente**.

## Pour créer des frais de déstockage
Vous pouvez facturer à votre client les frais de restockage pour couvrir les coûts de manutention physique occasionnés par le retour d’un article. Cela peut arriver si, par exemple, le client commande par erreur le mauvais article ou change d'avis après réception de l'article.

Vous pouvez reporter ce prix augmenté en tant que frais annexes dans une note de crédit ou un retour et l'affecter à la livraison reportée. Les sections suivantes décrivent cette procédure pour un retour vente, mais la même procédure s’applique à une note de crédit vente.

1. Ouvrez la page **Retour vente** pour un processus de retour actif.
2. Sur une nouvelle ligne, dans le champ **Type**, sélectionnez **Frais annexes**.  
3. Renseignez les champs comme pour n'importe quelle ligne frais annexes. Pour plus d'informations, voir [Utiliser Frais annexes pour comptabiliser les coûts commerciaux supplémentaires](payables-how-assign-item-charges.md).  

Lorsque vous reportez la commande retour vente, les frais de restockage sont ajoutés au montant de l'écriture vente appropriée. De cette manière, vous pouvez maintenir la précision de l'évaluation de l'inventaire.  

## Voir aussi .

[Ventes](sales-manage-sales.md)  
[Définition des ventes](sales-setup-sales.md)  
[Gestion des comptes fournisseur](payables-manage-payables.md)  
[Envoi de documents par courriel](ui-how-send-documents-email.md)  
[Traiter les retours ou annulations d'achats](purchasing-how-process-purchase-returns-cancellations.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
