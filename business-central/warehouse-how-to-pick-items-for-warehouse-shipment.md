---
title: Prélever des articles pour une livraison entrepôt
description: Découvrez comment utiliser les documents de prélèvement entrepôt pour créer et traiter les informations de prélèvement avant de reporter une livraison entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 09/11/2023
ms.custom: bap-template
ms.search.forms: '7335, 7339, 7345,'
---
# Prélever des articles pour une livraison entrepôt

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous prélevez et livrez des articles en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus sortant|Prélèvement requis|Livraison requise|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------|----------------|-----|---------|-------------------------------------------------------------------------------------|  
|A|Report du prélèvement et de la livraison à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report du prélèvement et de la livraison à partir d’un document prélèvement inventaire|Activé||De base : commande par commande.|  
|C|Report du prélèvement et de la livraison à partir d’un document livraison entrepôt||Activé|De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report du prélèvement à partir d’un document prélèvement entrepôt, et report de la livraison à partir d’un document livraison entrepôt|Activé|Activé|Avancé|  

Learn more at [Flux de désenlogement](design-details-outbound-warehouse-flow.md).

Cet article fait référence à la méthode D dans le tableau. Pour en savoir plus sur l’expédition d’articles, consultez [Expédier des articles](warehouse-how-ship-items.md).

Lorsqu’un emplacement est configuré pour appeler un traitement de prélèvement entrepôt et un traitement de livraison entrepôt, vous pouvez utiliser les documents prélèvement entrepôt pour créer et traiter les informations de prélèvement avant de reporter la livraison entrepôt.  

Vous ne pouvez pas créer un document de prélèvement en entrepôt à partir de rien. Les prélèvements font partie d’un flux de travail où la personne qui traite une commande les crée de manière « push », ou l'employé d'entrepôt les crée de manière « pull » :

- En mode « push », où vous utilisez l’action **Créer prélèvement** sur la page **Livraison entrepôt**. Sélectionnez les lignes à prélever et préparez les prélèvements en spécifiant, par exemple, à partir de quelles zones les prendre, à quelles zones les placer, et le nombre d’unités à traiter. Les zones peuvent être prédéfinies pour l’emplacement d’entrepôt ou la ressource.
- En mode « pull », où vous utilisez l’action **Libérer** dans la page **Livraison entrepôt** pour rendre les articles disponibles pour le prélèvement. Ensuite, sur la page **Feuille prélèvement**, les employés de l’entrepôt peuvent utiliser l’action **Extraire documents entrepôt** pour retirer les prélèvements qui leur sont assignés.

> [!NOTE]  
> Le prélèvement pour une livraison entrepôt des articles assemblés pour un document de vente suit les mêmes étapes que les prélèvements entrepôt ordinaires pour les livraisons, comme décrit dans cet article. Cependant, le nombre de lignes prélèvement pour la quantité à livrer peut grandement varier, car le prélèvement entrepôt concerne les composantes et non l’article assemblé.  
>
> Les lignes prélèvement entrepôt sont créées suivant la valeur du champ **Quantité restante** sur les lignes de l’ordre d’assemblage associé à la ligne document de vente en cours de livraison. Toutes les composantes sont prélevées en une seule action. Pour en savoir plus, voir [Traitement des articles à assembler pour commande dans les livraisons entrepôt](warehouse-how-ship-items.md#handling-assemble-to-order-items-in-warehouse-shipments).  
>  
> Pour en savoir plus sur le prélèvement de composantes pour les ordres d’assemblage, notamment les situations où les éléments d’assemblage ne sont pas associés à une livraison vente, voir [Prélever pour la fabrication, l’assemblage ou les tâches dans les configurations de stockage avancées](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## Vérifier si les articles sont disponibles pour le prélèvement

[!INCLUDE [inventory-availability-overview](includes/inventory-availability-overview.md)]

## Pour créer des documents de prélèvement en bloc avec la feuille prélèvement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille prélèvement**, puis choisissez le lien associé.  

2. Choisissez l'action **Extraire documents entrepôt**.  

    La liste comprendra toutes les livraisons qui ont été libérées pour le prélèvement, y compris celles pour lesquelles des instructions de prélèvement ont déjà été créées. Les documents dont les lignes prélèvement ont été entièrement prélevées et enregistrées n’apparaissent pas dans cette liste.  
3. Sélectionnez les livraisons pour lesquelles vous souhaitez préparer un prélèvement.

    > [!NOTE]  
    >  Si vous essayez de sélectionner un document de livraison ou de prélèvement interne pour lequel vous avez déjà créé des instructions pour toutes ses lignes, vous recevrez un message indiquant qu’il n’y a rien à gérer. Pour combiner des instructions de prélèvement entrepôt que vous avez déjà créées en une seule instruction de prélèvement, vous devez d’abord supprimer les prélèvements entrepôt individuels.

4. Renseignez le champ **Méthode de tri** pour trier les lignes.  

    > [!NOTE]  
    >  La façon dont les lignes sont triées dans la feuille ne se répercute pas automatiquement sur l’instruction de prélèvement. Cependant, les mêmes possibilités de tri et de classement des opportunités existent. Vous pouvez facilement recréer l’ordre des lignes planifié dans la feuille lorsque vous créez ou triez les instructions de prélèvement.

5. Remplissez le champ **Qté à traiter**, soit manuellement, soit en utilisant l’action **Remplir qté à traiter**.  

    La page affiche les quantités disponibles dans les zones de transbordement. Cette information est utile pour planifier les affectations de travail dans les situations de transbordement. [!INCLUDE[prod_short](includes/prod_short.md)] proposera toujours en premier un prélèvement dans une zone de transbordement.
6. Si nécessaire, modifiez les lignes. Vous pouvez aussi supprimer des lignes pour rendre le prélèvement plus efficace. Par exemple, si plusieurs lignes comportent des articles situés dans des zones de transbordement, vous pouvez créer un prélèvement pour toutes les lignes. Les articles transbordés seront livrés avec les autres articles de la livraison, et les zones de transbordement pourront à nouveau recevoir d’autres articles entrants.  

    > [!NOTE]  
    >  Si vous supprimez des lignes, elles sont supprimées de la feuille. Elles ne sont pas supprimées de la liste de sélection de prélèvement.  

7. Choisissez l'action **Créer prélèvement**. La page **Créer prélèvement** s’ouvre, où vous pouvez ajouter plus d’informations au prélèvement que vous créez. Spécifiez la façon de combiner les lignes prélèvement dans les documents prélèvement en sélectionnant l’une des options suivantes.  

    |Option|Désignation|
    |-|-|
    |Par entrepôt Document|Crée des documents prélèvement distincts pour les lignes feuille avec le même document d’origine entrepôt.|
    |Par client/fourn./mag.|Créez des documents prélèvement distincts pour chaque client (documents de vente), fournisseur (retours achat) et emplacement (ordres de transfert).|
    |Par article|Créez des documents prélèvement distincts pour chaque article sur la feuille prélèvement.|
    |Par zone origine|Créez des documents prélèvement distincts pour chaque zone où vous prendrez les articles.|
    |Par zone|Créez des documents prélèvement distincts pour chaque zone où vous prendrez les articles.|
    |Par date d'échéance|Créez des documents prélèvement distincts pour les documents source qui ont la même date d’échéance.|

    Indiquez la façon dont les documents prélèvement sont créés en sélectionnant l’une des options suivantes.

    |Option|Désignation|
    |-|-|
    |Montant Non. de lignes prélèvement|Crée des documents prélèvement qui n’ont pas plus que le nombre de lignes spécifié dans chaque document.|
    |Montant Non. de docs origine prélèvement|Crée des documents prélèvement qui chacun couvre pas plus que le nombre spécifié de documents origine.|
    |Code utilisateur affecté|Crée des documents prélèvement uniquement pour les lignes qui sont affectées à l'employé d'entrepôt sélectionné.|
    |Méthode de tri|Choisissez parmi les options disponibles pour trier les lignes du document prélèvement créé.|
    |Régler le filtre de rupture de charge|Masque les lignes prélèvement déconditionnement intermédiaires lorsqu’une plus grande unité de mesure est convertie en une unité de mesure inférieure et est prélevée dans son intégralité.|
    |Ne pas remplir qté à traiter|Laisse le champ Qté à traiter vide sur les lignes prélèvement créées.|
    |Imprimer prélèvement|Imprime les documents prélèvement lors de leur création. Vous pouvez également imprimer à partir des documents prélèvement créés.|

8. Cliquez sur **OK**. [!INCLUDE [prod_short](includes/prod_short.md)] créera le prélèvement en fonction de vos sélections.  

## Pour prélever des articles pour une livraison entrepôt

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements entrepôt**, puis choisissez le lien associé.  

    Si vous souhaitez travailler à un prélèvement particulier, sélectionnez-le dans la liste ou filtrez cette dernière afin de trouver les prélèvements qui vous ont été spécifiquement affectés. Ouvrez la fiche prélèvement.  
2. Si le champ **Code utilisateur affecté** est vide, entrez votre code pour vous identifier, si nécessaire.  
3. Prélevez les articles.  

    Si la zone de stockage est configurée pour utiliser des zones, les zones par défaut des articles sont utilisées pour suggérer où prendre les articles. Les instructions contiennent au moins deux lignes distinctes pour les actions Prendre et Placer.  

    Si l’entrepôt est configuré pour utiliser le rangement et le prélèvement dirigés, la priorité zone est utilisée pour calculer les meilleures zones pour le prélèvement. Ces zones sont suggérées sur les lignes prélèvement. Les instructions contiennent au moins deux lignes distinctes pour les actions Prendre et Placer.  

    * La première ligne, avec **Prendre** dans le champ **Type d’action**, indique l’endroit où se trouvent les articles dans la zone de prélèvement. Si vous livrez un grand nombre d’articles sur une seule ligne de livraison, vous devrez peut-être prélever les articles dans plusieurs zones; il y a donc une ligne Prendre pour chaque zone.
    * La ligne suivante, avec **Placer** dans le champ **Type d’action**, indique l’endroit où vous devez placer les articles dans l’entrepôt. Vous ne pouvez pas modifier la zone de cette ligne.

    > [!NOTE]
    > Si vous devez prélever ou placer les articles d’une ligne dans plusieurs zones, notamment parce que la zone indiquée est pleine, utilisez l’action **Éclater ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.

4. Après avoir prélevé et placé les articles dans la zone ou la zone d’expédition, choisissez l’action **Enregistrer prélèvement**.  

Vous pouvez alors apporter les articles au quai de chargement et reporter la livraison, dont le document source lié, sur la page **Livraison entrepôt**. Pour en savoir plus, voir [Livrer des articles](warehouse-how-ship-items.md).

## Voir aussi .

- [Vue d’ensemble de la gestion d’entrepôt](design-details-warehouse-management.md)
- [Gestion du stock](inventory-manage-inventory.md)  
- [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
- [Gestion d'assemblage](assembly-assemble-items.md)    
- [Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
