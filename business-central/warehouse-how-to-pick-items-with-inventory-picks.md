---
title: Comment prélever des articles avec les prélèvements inventaire
description: Découvrez comment utiliser les prélèvements inventaire pour enregistrer et reporter les informations de prélèvement et d’expédition pour les documents source.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 01/25/2023
ms.custom: bap-template
ms.search.forms: '931, 7377'
---
# <a name="pick-items-with-inventory-picks" />Prélever des articles avec les prélèvements stock

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous prélevez et livrez des articles en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus sortant|Prélèvement requis|Livraison requise|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report du prélèvement et de la livraison à partir d’un document prélèvement inventaire|Activé||De base : commande par commande.|  
|C|Report du prélèvement et de la livraison à partir d’un document livraison entrepôt||Activé|De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report du prélèvement à partir d’un document prélèvement entrepôt, et report de la livraison à partir d’un document livraison entrepôt|Activé|Activé|Avancé|  

Learn more at [Flux de désenlogement](design-details-outbound-warehouse-flow.md).

Cet article fait référence à la méthode B dans le tableau.

Lorsque votre emplacement est défini pour exiger un traitement des prélèvements mais pas un traitement des livraisons, utilisez la page **Prélèvement inventaire** pour enregistrer et reporter les informations de prélèvement et de livraison pour vos documents source. Les documents source sortants peuvent être des documents de vente, des retours achat et des ordres de transfert sortant.

> [!NOTE]
> Les besoins en composantes des ordres de fabrication et d’assemblage représentent également des documents source sortants. Pour en savoir plus sur la gestion des ordres de production et d’assemblage pour les processus internes, consultez [Détails de conception : Flux d’entrepôt internes](design-details-internal-warehouse-flows.md).
>
> Bien que les commandes de service soient également des documents origine sortants, elles ne prennent pas en charge le niveau de complexité commande par commande de base.
>
> En cas de prélèvement et d’expédition de quantités de lignes vente assemblées pour commande, vous devez suivre certaines règles lorsque vous créez les lignes prélèvement inventaire. Pour en savoir plus, voir [Traitement des articles à assembler pour commande dans les prélèvements inventaire](#handling-assemble-to-order-items-with-inventory-picks).  

Vous pouvez créer un prélèvement inventaire de trois manières :

* Créez le prélèvement inventaire directement à partir du document source.  
* Créez des prélèvements inventaire pour plusieurs documents source simultanément en utilisant un traitement en lot.
* Demandez le prélèvement en deux étapes en émettant d’abord le document origine, qui signale à l’entrepôt que le document origine est prêt pour le prélèvement.

Le prélèvement inventaire peut ensuite être créé à partir de la page **Prélèvement inventaire** sur la base du document source.  

## <a name="to-create-an-inventory-pick-from-the-source-document" />Pour créer un prélèvement inventaire à partir du document source

1. Dans le document source, qui peut être un document de vente, un retour achat ou un transfert sortant, choisissez l’action **Créer prélèv./rangement inventaire**.
2. Activez la case à cocher **Créer prélèvement inventaire**.  
3. Cliquez sur le bouton **OK**. Un nouveau prélèvement inventaire sera créé.

## <a name="to-create-multiple-inventory-picks-with-a-batch-job" />Pour créer plusieurs prélèvements inventaire avec un traitement en lot

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Créer rangement/prélèvement/mouvement d’inventaire**, puis choisissez le lien associé.  
2. Sur le raccourci **Demande entrepôt**, utilisez les champs **Document origine** et **N° origine** pour opérer un filtrage sur certains types de documents ou des plages de numéros de document. Par exemple, vous pouvez créer des prélèvements uniquement pour des documents de vente.  
3. Dans le raccourci **Options**, cochez la case **Créer prélèvement inventaire**.
4. Choisissez le bouton **OK**.

## <a name="to-create-the-pick-in-two-steps" />Pour créer le prélèvement en deux étapes

### <a name="to-request-an-inventory-pick-by-releasing-the-source-document" />Pour demander un prélèvement inventaire en libérant le document source

Pour les documents de vente, les retours achat et les ordres de transfert sortants, vous créez la demande entrepôt en libérant l'ordre. Le lancement de la commande rend les articles disponibles pour le prélèvement.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Sélectionnez le document de vente que vous voulez libérer, puis sélectionnez l'action **Libérer**.

### <a name="to-create-an-inventory-pick-based-on-the-source-document" />Pour créer un prélèvement inventaire en fonction du document source

Après avoir lancé une commande, l'employé d'entrepôt peut créer un prélèvement inventaire.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements inventaire**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Document origine**, sélectionnez le type de document origine relatif au prélèvement.  
4. Dans le champ **N° origine**, sélectionnez le document origine.  
5. Sinon, choisissez l’action **Extraire document source** pour créer une liste de tous les documents source sortants prêts pour le prélèvement dans l’emplacement.  
6. Sélectionnez le bouton **OK** pour renseigner les lignes prélèvement en fonction des documents origine sélectionnés.  

## <a name="to-record-inventory-picks" />Pour enregistrer les prélèvements inventaire

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvement inventaire**, puis choisissez le lien associé.  
2. Dans le champ **Code de zone** sur les lignes prélèvement, la zone à partir de laquelle les articles doivent être prélevés est proposée sur la base d'une zone par défaut de l'article. Vous pouvez modifier la zone sur cette page, si nécessaire.  
3. Exécutez le prélèvement, puis saisissez la quantité prélevée dans le champ **Quantité à traiter**.

    Si vous devez prélever les articles d’une ligne à partir de plusieurs zones, par exemple parce que la quantité totale n’est pas dans la zone, utilisez l’action **Fractionner la ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.

4. Sélectionnez l'action **Reporter**.  

    * Reportez la livraison des lignes du document source qui ont été prélevées.
    * Si l’emplacement utilise des zones, le report crée également des écritures entrepôt pour reporter les modifications apportées aux quantités zone.  

## <a name="handling-assemble-to-order-items-with-inventory-picks" />Traitement des articles à assembler pour commande dans les prélèvements inventaire

Vous pouvez également utiliser la page **Prélèvement inventaire** pour prélever et livrer les ventes lorsque les articles doivent être assemblés avant de pouvoir être livrés. Learn more at [Vente d’articles à assembler pour commande](assembly-how-to-sell-items-assembled-to-order.md).

Les articles à assembler pour commande ne se trouvent pas physiquement dans une zone tant qu’ils n’ont pas été assemblés et reportés comme sortie vers une zone. Le prélèvement des articles à assembler pour commande à partir d’une zone en vue de la livraison suit un flux spécial.

1. Depuis une zone, les employés d'entrepôt déposent des éléments d'assemblage sur le quai de livraison, puis reportent le prélèvement inventaire.
2. Le prélèvement inventaire reporté reporte le résultat d’assemblage, la consommation de composantes et la livraison vente.

Vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour créer automatiquement un mouvement d'inventaire lors de la création du prélèvement inventaire pour l'élément d'assemblage. Sélectionnez le champ **Créer des mouvements automatiquement** sur la page **Configuration d’assemblage**. Learn more at [Configurer des entrepôts de base avec les zones d’opérations](warehouse-how-to-set-up-basic-warehouses-with-operations-areas.md).

Les lignes prélèvement inventaire pour les articles vente sont créées de différentes manières, selon qu’aucune, certaines ou toutes les quantités des lignes vente sont assemblées pour commande. Dans les scénarios où une partie de la quantité est assemblée et une autre est prélevée dans l’inventaire, un minimum de deux lignes prélèvement sont créées.

Pour les ventes où la quantité totale de la ligne document de vente est assemblée pour commande, une ligne prélèvement inventaire est créée pour cette quantité. La valeur du champ **Quantité à assembler** correspond à la valeur du champ **Qté à livrer**. Le champ **Assembler pour commande** est sélectionné sur la ligne.

Si un flux de résultat d’assemblage est configuré pour la zone, le champ **Code de zone** sur la ligne de prélèvement inventaire contient la valeur des champs suivants, dans l’ordre suivant.

* ***Code empl. exp. ass. pr comm.** <!-- not applicable for inv pick-->
* **Code empl. depuis assemblage**

Si aucun code de zone n’est spécifié sur la ligne document de vente et qu’aucun flux de résultat d’assemblage n’est configuré pour l'emplacement, le champ **Code de zone** de la ligne prélèvement inventaire est vide. L'employé d'entrepôt doit ouvrir la page **Contenus de la zone** et sélectionner la zone où les articles d'assemblage sont assemblés.

Dans les scénarios où une partie de la quantité est assemblée et l’autre doit être prélevée, un minimum de deux lignes prélèvement stock sont créées.

* Une ligne prélèvement pour la quantité à assembler pour commande. [!INCLUDE [prod_short](includes/prod_short.md)] utilise les champs suivants, dans cet ordre, pour déterminer le code de zone : **Code de zone**, **Code de zone livr. ass. pr comm.**, puis **Code de zone post-assemblage**. Si ces champs sont vides, l'employé d'entrepôt doit ouvrir la page **Contenu zone** et choisir la zone dans laquelle les articles sont assemblés.  
* L’autre ligne prélèvement dépend des zones qui peuvent satisfaire la quantité restante. Si l’article est conservé dans plusieurs zones, plusieurs lignes seront créées. La ligne Prendre est basée sur la quantité indiquée dans le champ **Qté à livrer**.

> [!NOTE]  
> Si les articles sont assemblés pour commande, le prélèvement inventaire pour le document de vente lié crée un mouvement d’inventaire pour toutes les composantes d’assemblage.  

## <a name="see-related-microsoft-training" />Voir la [formation Microsoft](/training/paths/pick-ship-items-business-central/) associée

## <a name="see-also" />Voir aussi

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Procédure pas à pas : Prélèvement et expédition dans les configurations de stockage de base](walkthrough-picking-and-shipping-in-basic-warehousing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
