---
title: Livrer des articles
description: Cet article décrit comment livrer des articles depuis votre entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 02/22/2023
ms.custom: bap-template
ms.search.form: '7335, 7337, 7339, 7340, 7341, 7362, 9008'
---

# <a name="ship-items-with-a-warehouse-shipment"></a>Livrer des articles avec une livraison entrepôt

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous prélevez et livrez des articles en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus sortant|Prélèvement requis|Livraison requise|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report du prélèvement et de la livraison à partir d’un document prélèvement inventaire|Activé||De base : commande par commande.|  
|C|Report du prélèvement et de la livraison à partir d’un document livraison entrepôt||Activé|De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report du prélèvement à partir d’un document prélèvement entrepôt, et report de la livraison à partir d’un document livraison entrepôt|Activé|Activé|Avancé|  

Pour en savoir plus sur l’expédition d’articles, consultez [Flux de désenlogement](design-details-outbound-warehouse-flow.md).

Cet article fait référence aux méthodes C et D dans le tableau. Dans les deux méthodes, vous commencez par créer un document de livraison à partir d’un document source commercial. Puis, vous prélevez les articles spécifiés pour la livraison.

Lorsqu’un emplacement nécessite des livraisons entrepôt, vous pouvez livrer des articles en fonction des documents source qui ont été émis dans l’entrepôt. L’émission des documents origine rend les articles qu’ils contiennent prêts à être manipulés dans l’entrepôt. Voici des exemples de documents origine :

* Documents de vente
* Retours achat
* Ordres de transfert
* Commandes service

Vous pouvez créer une livraison entrepôt de deux manières :

* En mode « push », lorsque le travail est effectué commande par commande. Choisissez l’action **Créer livraison entrepôt** dans le document source pour créer une livraison entrepôt pour le document.
* En mode « pull », où vous utilisez l’action **Libérer** dans le document source pour le libérer dans l’entrepôt. Un employé d'entrepôt crée une **Livraison entrepôt** pour un ou plusieurs documents source libérés. La procédure suivante décrit comment créer une livraison entrepôt en mode « pull ».

## <a name="to-ship-items-using-a-warehouse-shipment-document"></a>Pour livrer des articles avec un document de livraison entrepôt

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Livraisons entrepôt**, puis sélectionnez le lien associé.  
2. Choisissez **Nouveau**.  
3. Dans le champ **N°**, choisissez la série de numéros à utiliser pour créer un identifiant pour la livraison.  
4. Dans le champ **Code emplacement**, choisissez l’emplacement à partir duquel vous expédiez. 

    Lorsque vous récupérez des lignes document source, certaines des informations de l’emplacement sont copiées dans chaque ligne.  
5. Si l’emplacement nécessite des zones, remplissez le champ **Code de zone**. Selon votre configuration, [!INCLUDE[prod_short](includes/prod_short.md)]] peut ajouter le code de zone pour vous. Pour en savoir plus, voir [Zone et codes de zone](warehouse-how-ship-items.md#zone-and-bin-codes).  
6. Vous pouvez obtenir le document origine de deux manières :

    * Choisissez l'action **Extraire documents origine**. La page **Documents origine - Sortants** s’ouvre. Ici, vous pouvez sélectionner un ou plusieurs documents source libérés dans l’entrepôt qui nécessitent une livraison.
    * Choisissez l'action **Filtrer pour extr. doc. orig.**. La page **Filtres pour extr. doc. orig.** s’ouvre. Vous pouvez sélectionner le filtre de document source et l’appliquer. Toutes les lignes du document source libéré qui répondent aux critères de filtre sont ajoutées sur la page **Livraison entrepôt**. Learn more at [Procédure : utiliser des filtres afin d’obtenir des documents origine](warehouse-how-ship-items.md#how-to-use-filters-to-get-source-documents).

    > [!NOTE]
    > Si votre emplacement utilise le transbordement, et dispose de zones pour chaque ligne, vous pouvez examiner la quantité d’articles placés dans les zones transbordement. [!INCLUDE [prod_short](includes/prod_short.md)] calcule les quantités chaque fois que les champs de la livraison sont mis à jour. S’il s’agit des articles correspondant à la livraison que vous préparez, vous pouvez créer un prélèvement pour tous les articles, puis terminer la livraison. En savoir plus sur [ Transborder des articles](warehouse-how-to-cross-dock-items.md).

7. Créez un prélèvement entrepôt. Si l’emplacement nécessite un prélèvement, vous pouvez créer des activités de prélèvement pour les livraisons d’entrepôt de l’une des deux manières suivantes :

    * En mode « push », où vous utilisez l’action **Créer prélèvement**. Sélectionnez les lignes à prélever et spécifiez les informations sur les prélèvements. Par exemple, dans quelles zones prendre et placer, et combien d’unités manipuler. Les zones peuvent être prédéfinies pour l’emplacement d’entrepôt ou la ressource.
    * En mode « pull », où vous utilisez l’action **Libérer**. Sur la page **Feuille prélèvement**, utilisez l’action **Extraire documents entrepôt** pour récupérer les prélèvements qui vous ont été attribués. Lorsque les prélèvements entrepôt sont entièrement enregistrés, les lignes dans la **Feuille prélèvement** sont supprimées. Pour en savoir plus, voir [Prélever des articles pour la livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md).

    > [!TIP]
    > Pour un emplacement qui ne nécessite pas de prélèvement, vous pouvez imprimer la livraison entrepôt et l’utiliser comme liste de prélèvement.

8. Spécifiez la quantité à livrer.  

    Pour un emplacement nécessitant le prélèvement, le champ **Qté à livrer** est mis à jour automatiquement lorsque le prélèvement est enregistré. Sinon, le champ **Qté à livrer** est rempli avec la quantité restante pour chaque ligne lorsque la ligne de livraison entrepôt est créée.

    Vous pouvez modifier la quantité, mais vous ne pouvez pas livrer plus d’articles que le nombre indiqué dans le champ **Qté restante** sur la ligne du document source ou le champ **Qté prélevée** si le prélèvement est requis.

    Pour définir la valeur dans le champ **Qté à livrer** sur toutes les lignes à zéro, choisissez l’action **Supprimer qté à livrer**. Par exemple, définir les quantités sur zéro est utile si vous utilisez un lecteur de code-barres pour mettre à jour les quantités d’expédition. Pour ajouter la quantité disponible pour la livraison, choisissez l’action **Remplir qté à livrer**.

9. Reportez la livraison.

    [!INCLUDE [preview-posting-shipment](includes/preview-posting-shipment.md)]

## <a name="how-to-use-filters-to-get-source-documents"></a>Procédure : utiliser des filtres afin d’obtenir des documents origine

À partir d’une livraison entrepôt, vous pouvez utiliser la page **Filtres pour extr. doc. orig.** afin d’extraire les lignes du document source libéré qui définissent les articles à recevoir ou à livrer.

1. Dans la livraison entrepôt, choisissez l’action **Filtrer pour extr. doc. orig.**. 
2. Pour configurer un nouveau filtre, entrez un code descriptif dans le champ **Code**, puis choisissez l’action **Modifier**.

    La page **Fiche filtre document origine - Sortants** s’ouvre.

3. Utilisez les filtres pour définir le type de lignes du document origine à récupérer. Par exemple, vous pouvez sélectionner des types de documents origine, tels que des commande vente ou des ordres de transfert.
4. Choisir **Exécuter**.  

Toutes les lignes du document source libéré qui répondent aux critères de filtre sont ajoutées sur la page **Livraison entrepôt** sur laquelle vous avez défini les filtres.

Le nombre de combinaisons de filtres est illimité. Les filtres sont enregistrés sur la page **Filtres pour extr. doc. orig.** et seront disponibles la prochaine fois que vous en aurez besoin. Vous pouvez modifier les critères à tout moment en choisissant l'action **Modifier**.

## <a name="zone-and-bin-codes"></a>Zone et codes de zone

Si les zones sont obligatoires dans l’emplacement, [!INCLUDE [prod_short](includes/prod_short.md)] suggère une zone et un code de zone sur le document de livraison entrepôt.

* Pour les configurations avancées dans lesquelles un emplacement utilise le rangement et le prélèvement dirigés, [!INCLUDE [prod_short](includes/prod_short.md)] utilise la zone spécifiée dans le champ **Code de zone livraison** sur la **Fiche emplacement**. Si aucun **Code de zone livraison** n’est spécifié, le champ est vide. Si l’article et la zone de livraison ne correspondent pas, [!INCLUDE [prod_short](includes/prod_short.md)] laisse la zone de livraison vide.
* Dans les autres cas, [!INCLUDE [prod_short](includes/prod_short.md)] utilise toujours en premier la zone spécifiée dans le champ **Code de zone livraison** sur la **Fiche emplacement**. Si aucun code de zone de livraison n’est spécifié, [!INCLUDE [prod_short](includes/prod_short.md)] utilise le code de zone du document source.

## <a name="handling-assemble-to-order-items-in-warehouse-shipments"></a>Traitement des articles à assembler pour commande dans les livraisons entrepôt

Dans des scénarios d’assemblage pour commande, utilisez le champ **Qté à livrer** sur les lignes livraison entrepôt pour enregistrer le nombre d’unités assemblées. La quantité est reportée comme résultat d’assemblage lorsque vous reportez la livraison entrepôt. Pour d’autres lignes livraison entrepôt, la valeur du champ **Qté à livrer** est zéro.

Lorsque les ouvriers ont fini d’assembler une partie ou la totalité de la quantité à assembler pour commande, enregistrez la quantité dans le champ **Qté à livrer** sur la ligne de livraison entrepôt. Sélectionnez ensuite l’action **Reporter livraison**. Le résultat d’assemblage est reporté, y compris la consommation des composantes. Une livraison vente pour la quantité est reportée pour le document de vente.

À partir de l'ordre d'assemblage, vous pouvez choisir **Ligne livraison entrepôt Assembler pour commande** pour accéder à la ligne livraison entrepôt.

Une fois la livraison entrepôt validée, divers champs de la ligne document de vente sont mis à jour pour afficher la progression dans l’entrepôt. Les champs suivants sont également mis à jour pour afficher le nombre de quantités à assembler pour commande qui restent à assembler et livrer :

* **Qté restante entrepôt ATO**
* **Qté restante entrepôt ATO (base)**

> [!NOTE]
> Dans les scénarios de combinaison, où une partie de la quantité doit être assemblée et l’autre doit être livrée à partir des inventaires, deux lignes livraison entrepôt sont créées. L'une est pour la quantité à assembler pour commande et l'autre est destinée à la quantité en inventaire.
>
> La quantité assemblée pour commande est gérée comme décrit dans cet article. La quantité provenant de l’inventaire est traitée comme une ligne de livraison entrepôt standard. Pour plus d’informations sur les scénarios de combinaison, consultez [Description des processus Assembler pour commande et Assembler pour inventaire](assembly-assemble-to-order-or-assemble-to-stock.md).

## <a name="see-also"></a>Voir aussi .

[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
