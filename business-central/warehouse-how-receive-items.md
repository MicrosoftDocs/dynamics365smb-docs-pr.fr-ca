---
title: Comment recevoir des articles | Microsoft Docs
description: Lorsque les articles arrivent dans un entrepôt configuré pour appeler un traitement de réception entrepôt, vous devez extraire les lignes du document origine libéré ayant déclenché leur réception.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 5bf683be6e6d0976464240d08e0546639a46362a
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5771914"
---
# <a name="receive-items"></a>Réceptionner des articles

Lorsque les articles arrivent dans un entrepôt qui n'est pas configuré pour un traitement de réception entrepôt, enregistrez simplement la réception du document d'entreprise associé, comme un bon de commande, un retour vente ou un ordre de transfert entrant.

Lorsque les articles arrivent dans un entrepôt configuré pour appeler un traitement de réception entrepôt, vous devez extraire les lignes du document origine libéré ayant déclenché leur réception. En présence de zones, vous pouvez soit accepter la zone par défaut qui est renseignée, soit renseigner la zone de rangement de l'article concerné si cet article n'a jamais été utilisé dans l'entrepôt. Vous devez ensuite renseigner les quantités d'articles reçus et reporter la réception.  

## <a name="to-receive-items-with-a-purchase-order"></a>Pour recevoir des articles avec un bon de commande

La section suivante décrit comment recevoir des articles avec un bon de commande. Les étapes sont similaires pour les retours vente et les ordres de transfert.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.
2. Ouvrez un bon de commande existant, ou créez-en un nouveau. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).
3. Dans le champ **Qté à recevoir**, indiquez la quantité reçue.

  > [!NOTE]
  > Si la quantité reçue est supérieure à celle commandée sur le bon de commande, selon le champ **Quantité**, et que le fournisseur a été configuré pour autoriser les sur-réceptions, utilisez le champ **Sur-réception** pour gérer la quantité excédentaire. Pour en savoir plus, consultez [Pour réceptionner plus d'articles que commandés](warehouse-how-receive-items.md#to-receive-more-items-than-ordered).

4. Sélectionnez l'action **Reporter**.

  La valeur du champ **Qté reçue** est mise à jour en conséquence. Si c'est une réception partielle, la valeur est inférieure à la valeur dans le champ **Quantité**.

> [!NOTE]
> Si vous utilisez un document entrepôt pour reporter la réception, vous ne pouvez pas utiliser l'action **Reporter** sur le bon de commande. Au lieu de cela, un magasinier a déjà reporté la quantité de la bon de commande telle qu'elle a été reçue. Pour en savoir plus, consultez [Pour réceptionner des articles avec une réception entrepôt](warehouse-how-receive-items.md#to-receive-items-with-a-warehouse-receipt).

## <a name="to-receive-items-with-a-warehouse-receipt"></a>Pour recevoir des articles avec une réception entrepôt

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Réceptions entrepôt**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  

    Renseignez les champs du raccourci **Général**. Lorsque vous récupérez des lignes document origine,certaines des informations de l'en-tête sont copiées dans chaque ligne.  

    Pour une configuration entrepôt avec un prélèvement et un rangement suggérés : Si l'emplacement possède des zones par défaut pour les réceptions, les champs **Code de zone** et **Code de zone** seront renseignés automatiquement, mais vous pouvez les modifier selon vos besoins.  

    > [!NOTE]  
    > Pour recevoir des articles portant des codes classe entrepôt différents du code classe de l'emplacement indiqué dans le champ **Code emplacement** de l'en-tête du document, vous devez supprimer la valeur du champ **Code emplacement** de l'en-tête avant d'extraire les lignes des documents origine des articles.  
3. Choisissez l'action **Extraire documents origine**. La page **Documents origine** s'ouvre.

    À partir d'une réception entrepôt nouvelle ou ouverte, vous pouvez utiliser la page **Filtres pour extr. doc. orig.** afin d'extraire les lignes du document origine libéré qui définissent les articles à recevoir ou à livrer.

    1. Choisissez l'action **Filtrer pour extr. doc. orig.**.  
    2. Pour configurer un nouveau filtre, entrez un code descriptif dans le champ **Code**, puis choisissez l'action **Modifier**.  
    3. Définissez le type de ligne document origine que vous souhaitez extraire en renseignant les champs de filtre appropriés.  
    4. Sélectionnez l'action **Exécuter**.  

    Toutes les lignes du document origine libéré qui correspondent aux critères du filtre sont à présent insérées sur la page **Réception entrepôt** à partir de laquelle vous avez activé la fonction filtre.  

    Les combinaisons de filtres que vous définissez sont stockées sur la page **Filtres pour extr. doc. orig.** jusqu'à la prochaine utilisation. Le nombre de combinaisons de filtres est illimité. Vous pouvez modifier les critères à tout moment en choisissant l'action **Modifier**.

4. Sélectionnez le document origine pour lequel vous souhaitez réceptionner des articles, puis sélectionnez le bouton **OK**.  

    Les lignes des documents origine s'affichent sur la page **Réception entrepôt**. Le champ **Qté à recevoir** est renseigné avec la quantité restante pour chaque ligne, mais vous pouvez modifier cette quantité selon vos besoins. Si vous avez supprimé la valeur du champ **Code emplacement** du raccourci **Général** avant d'accéder aux lignes, vous devez alors renseigner un code emplacement approprié sur chaque ligne réception.  

    > [!NOTE]  
    >  Pour renseigner le champ **Qté à recevoir** sur toutes les lignes à zéro, choisissez l'action **Supprimer qté à recevoir**. Pour y insérer à nouveau la quantité restante, choisissez l'action **Remplir qté à recevoir**.  

    > [!NOTE]  
    >  Vous ne pouvez pas recevoir un nombre d'articles supérieur au nombre figurant dans le champ **Qté ouverte** de la ligne document origine. Pour recevoir des articles supplémentaires, récupérez un autre document origine contenant une ligne pour l'article concerné en utilisant la fonction filtre afin d'obtenir les documents origine où figure cet article.  

5. Reportez la réception entrepôt. Les champs relatifs à la quantité dans les documents origine sont mis à jour et les articles enregistrés dans le cadre de l'inventaire de la compagnie.  

En cas d'utilisation d'un rangement entrepôt, les lignes réception sont transmises à la fonction de rangement entrepôt. Les articles, bien que réceptionnés, ne peuvent pas être prélevés avant d'avoir été rangés. Les articles réceptionnés sont identifiés en tant qu'inventaire disponible une fois le rangement enregistré uniquement.  

En cas de non-utilisation d'un rangement entrepôt et d'utilisation de zones, le rangement des articles est enregistré dans la zone spécifiée sur la ligne document source.  

> [!NOTE]  
> En utilisant la fonction **Reporter et Imprimer**, vous effectuez à la fois le report de la réception et l'impression d'une instruction de rangement qui indique où ranger les articles dans le stock.  
>
> En cas d'utilisation d'un prélèvement et d'un rangement suggérés, les modèles rangement sont utilisés pour procéder au calcul du meilleur emplacement de rangement des articles. Il est ensuite imprimé sur l'instruction de rangement.

## <a name="to-receive-more-items-than-ordered"></a>Pour réceptionner plus d'articles que commandés

Lorsque vous recevez plus de produits que commandés, vous pouvez les réceptionner au lieu d'annuler la réception. Par exemple, il peut être moins coûteux de conserver les inventaires excédentaires que de les retourner, ou votre fournisseur peut vous proposer un escompte pour les conserver.

### <a name="to-set-up-over-receipts"></a>Pour configurer des sur-réceptions

Vous devez définir un pourcentage de dépassement autorisé de la quantité commandée lors de la réception. Vous le définissez sous un code de sur-réception, qui contient le pourcentage dans le champ **% de tolérance de sur-réception**. Vous affectez ensuite le code aux fiches des articles et/ou fournisseurs concernés.  

Ce qui suit décrit comment configurer un code de sur-réception et l'attribuer à un article. La procédure est identique pour un fournisseur.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.
2. Ouvrez la fiche pour un article que vous soupçonnez parfois d'être livré avec une quantité supérieure à celle commandée.
3. Cliquez sur le bouton de recherche dans le champ **Code de sur-réception**.
4. Sélectionnez l'action **Nouveau**.
5. Sur la page **Codes de sur-réception**, créez une ou plusieurs lignes définissant différentes stratégies de sur-réception. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
6. Sélectionnez une ligne, puis cliquez sur le bouton **OK**.

Le code de sur-réception est affecté à l'article. Tout bon de commande ou toute réception entrepôt pour l'article permet désormais de réceptionner une quantité supérieure à celle commandée selon le pourcentage de tolérance de sur-réception indiqué.

> [!NOTE]
> Vous pouvez configurer un flux de travail approbation pour exiger l'approbation des sur-réceptions avant leur traitement. Dans ce cas, vous devez sélectionner le champ **Approbation requise** sur la page **Codes de sur-réception**. Pour plus d'informations, voir [Créer des flux de travail](across-how-to-create-workflows.md).

### <a name="to-perform-an-over-receipt"></a>Pour effectuer une sur-réception

Sur les lignes achat et les lignes réception entrepôt, le champ **Quantité de sur-réception** permet d'enregistrer les quantités excédentaires reçues, c'est-à-dire les quantités dépassant la valeur dans le champ **Quantité**, la quantité commandée.

Lorsque vous traitez une sur-réception, vous pouvez augmenter la valeur dans le champ **Qté à recevoir** pour la faire correspondre à la quantité réellement reçue. Le champ **Quantité de sur-réception** est ensuite mis à jour pour afficher la quantité excédentaire. Vous pouvez également saisir la quantité excédentaire dans le champ **Quantité de sur-réception**. Le champ **Qté à recevoir** est ensuite mis à jour pour afficher la quantité commandée augmentée de la quantité excédentaire. La procédure suivante décrit comment renseigner le champ **Qté à recevoir**.  

1. Sur un bon de commande ou un document réception entrepôt où la quantité reçue est supérieure à celle commandée, saisissez la quantité réellement reçue dans le champ **Qté à recevoir**.

    Si l'augmentation est inférieure ou égale à la tolérance indiquée par le code de sur-réception attribué, le champ **Quantité de sur-réception** est mis à jour pour afficher la quantité de dépassement de la valeur dans le champ **Quantité**.

    Si l'augmentation est supérieure à la tolérance indiquée, la sur-réception n'est pas autorisée. Dans ce cas, vous pouvez rechercher s'il existe un autre code de sur-réception qui l'autorisera. Sinon, seule la quantité commandée peut être réceptionnée et la quantité excédentaire doit être traitée autrement, par exemple en la renvoyant au fournisseur.

2. Reportez la réception comme vous le feriez pour toute autre réception.

> [!NOTE]
> [!INCLUDE[prod_short](includes/prod_short.md)] n'inclut pas de fonctionnalité permettant d'initier automatiquement l'administration financière des sur-réceptions. Vous devez gérer cela manuellement en accord avec le fournisseur, qui peut par exemple vous envoyer une facture nouvelle ou mise à jour.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/receive-invoice-dynamics-d365-business-central/index)

## <a name="see-also"></a>Voir aussi

[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]