---
title: Comment livrer des articles | Microsoft Docs
description: En fonction de votre configuration d'entrepôt, vous pouvez enregistrer la livraison sur le document d'entreprise sortant associé, comme un document de vente, directement, ou vous pouvez utiliser les documents livraison entrepôt qui respectent un flux de travail et s'intègrent à différentes activités entrepôt.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: a2bde69033ee208082662fa771616ac0b124d73e
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2876785"
---
# <a name="ship-items"></a>Livrer des articles
Lorsque vous livrez des articles provenant d'un entrepôt qui n'est pas configuré pour un traitement de livraison entrepôt, enregistrez simplement la livraison du document d'entreprise associé, comme un document de vente, une commande service, un retour vente ou un ordre de transfert sortant.

Lorsque vous livrez des articles à partir d'un entrepôt qui est configuré pour un traitement de livraison entrepôt, vous ne pouvez livrer des articles que sur la base des documents sources que d'autres centres de la compagnie ont libérés et transmis à l'entrepôt en vue d'une action.

> [!NOTE]
> Si votre entrepôt utilise le transbordement et les zones, vous pouvez visualiser pour chaque ligne la quantité d'articles placés dans les zones transbordement. L'application calcule automatiquement ces quantités chaque fois que les champs de la livraison sont mis à jour. S'il s'agit des articles correspondant à la livraison que vous préparez, vous pouvez créer un prélèvement pour toutes les lignes, puis terminer la livraison. Pour plus d'informations, voir [Transborder des articles](warehouse-how-to-cross-dock-items.md).

## <a name="to-ship-items-with-a-sales-order"></a>Pour livrer des articles avec un document de vente
La section suivante décrit comment recevoir des articles avec un bon de commande. Les étapes sont similaires pour les retours achat, les commandes service et les ordres de transfert sortants.  
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.
2. Ouvrez un document de vente existant, ou créez-en un nouveau. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
3. Dans le champ **Qté à livrer**, indiquez la quantité reçue.

    La valeur du champ **Qté livrée** est mise à jour. Si c'est une livraison partielle, la valeur est inférieure celle dans le champ **Quantité**.
4. Sélectionnez l'action **Valider**.

## <a name="to-ship-items-with-a-warehouse-shipment"></a>Pour livrer des articles avec une livraison entrepôt
Premièrement, vous créez un document livraison à partir d'un document source d'entreprise. Puis, vous prélevez les articles spécifiés pour la livraison.

### <a name="to-create-a-warehouse-shipment"></a>Pour créer une livraison entrepôt
Généralement, l'employé chargé de la livraison crée une livraison entrepôt.
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons entrepôt**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**.  

    Renseignez les champs du raccourci **Général**. Lorsque vous récupérez des lignes document origine,certaines des informations de l'en-tête sont copiées dans chaque ligne.  

    Pour une configuration entrepôt avec un prélèvement et un rangement suggérés : Si l'emplacement possède des zones par défaut pour les livraisons, les champs **Code de zone** et **Code de zone** seront renseignés automatiquement, mais vous pouvez les modifier selon vos besoins.  

    > [!NOTE]  
    >  Pour livrer des articles portant des codes classe entrepôt différents du code classe de la zone indiqué dans le champ **Code de zone** de l'en-tête du document, vous devez supprimer le contenu du champ **Code de zone** de l'en-tête avant d'extraire les lignes des documents sources des articles.  
3.  Choisissez l'action **Extraire documents origine**. La page **Documents origine** s'ouvre.

    À partir d'une livraison entrepôt nouvelle ou ouverte, vous pouvez utiliser la page **Filtres pour extr. doc. orig.** afin d'extraire les lignes du document origine libéré qui définissent les articles à recevoir ou à livrer.

    1. Choisissez l'action **Filtrer pour extr. doc. orig.**.  
    2. Pour configurer un nouveau filtre, entrez un code descriptif dans le champ **Code**, puis choisissez l'action **Modifier**.  
    3. Définissez le type de ligne document origine que vous souhaitez extraire en renseignant les champs de filtre appropriés.  
    4. Sélectionnez l'action **Exécuter**.  

    Toutes les lignes du document origine libéré qui correspondent aux critères du filtre sont à présent insérées sur la page **Livraison entrepôt** à partir de laquelle vous avez activé la fonction filtre.  

    Les combinaisons de filtres que vous définissez sont stockées sur la page **Filtres pour extr. doc. orig.** jusqu'à la prochaine utilisation. Le nombre de combinaisons de filtres est illimité. Vous pouvez modifier les critères à tout moment en choisissant l'action **Modifier**.

4.  Sélectionnez les documents sources pour lesquels vous souhaitez livrer des articles, puis sélectionnez le bouton **OK**.  

Les lignes des documents origine s'affichent sur la page **Livraison entrepôt**. Le champ **Qté à livrer** est renseigné avec la quantité restante pour chaque ligne, mais vous pouvez modifier cette quantité selon vos besoins. Si vous avez supprimé le contenu du champ **Code de zone** du raccourci **Général** avant d'accéder aux lignes, vous devez alors renseigner un code de zone approprié sur chaque ligne livraison.  

> [!NOTE]  
>  Vous ne pouvez pas livrer un nombre d'articles supérieur au nombre figurant dans le champ **Qté résiduelle** de la ligne document source. Pour livrer des articles supplémentaires, récupérez un autre document source contenant une ligne pour l'article concerné en utilisant la fonction filtre afin d'obtenir les documents sources où figure cet article.  

Lorsque vous disposez des lignes à livrer, vous pouvez lancer le processus qui envoie les lignes pour prélèvement aux magasiniers.

### <a name="to-pick-and-ship"></a>Pour effectuer un prélèvement et une livraison
Généralement, un magasinier chargé du prélèvement crée un document prélèvement, ou ouvre un document prélèvement déjà créé.
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Livraisons entrepôt**, puis sélectionnez le lien associé.
2. Sélectionnez la livraison entrepôt que vous souhaitez prélever, puis sélectionnez l'action **Créer prélèvement**.
3. Renseignez les champs de la page de demande, puis cliquez sur le bouton **OK**. Le document prélèvement entrepôt spécifié est créé.

    Sinon, ouvrez un prélèvement entrepôt existant.
4. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvements**, puis sélectionnez le lien associé. Sélectionnez le prélèvement entrepôt que vous souhaitez utiliser.

    Si l'entrepôt est configuré pour utiliser des emplacements, alors les lignes prélèvement sont converties en lignes action Prélever et Ranger.

    Vous pouvez trier les lignes, affecter un employé au prélèvement, définir un filtre de déconditionnement (en cas d'utilisation d'un prélèvement et d'un rangement suggérés) et imprimer les instructions de prélèvement.

5. Réalisez le prélèvement effectif des articles et placez-les dans la zone livraison spécifiée, ou dans la zone livraison, si vous n'avez pas de zones.
6. Choisissez l'action **Enregistrer prélèvement**.

    Les champs **Qté à livrer** et **État document** de l'en-tête du document livraison sont mis à jour. Les articles prélevés ne peuvent plus être prélevés pour d'autres expéditions ou pour des opérations internes.
7. Imprimez les documents livraison, préparez les colis, puis reportez la livraison.

Pour plus d'informations sur le prélèvement pour les livraisons entrepôt, voir [Prélever des articles pour une livraison entrepôt](warehouse-how-to-pick-items-for-warehouse-shipment.md).

Vous pouvez également utiliser la feuille prélèvement pour regrouper plusieurs instructions de prélèvement en une seule instruction (pour plusieurs livraisons) et optimiser ainsi l'efficacité du prélèvement dans l'entrepôt. Pour plus d'informations, voir [Planifier un prélèvement dans des feuilles](warehouse-how-to-plan-picks-in-worksheets.md).

> [!NOTE]
> Lorsque vous attendez l'arrivée d'articles spécifiques dans l'entrepôt et que vous utilisez la fonctionnalité de transbordement, [!INCLUDE[d365fin](includes/d365fin_md.md)] calcule, pour chaque ligne journal prélèvement ou livraison, la quantité article figurant dans la zone de transbordement. Il met à jour ce champ chaque fois que vous fermez ou ouvrez la feuille ou le document de livraison. Pour plus d'informations, voir [Transborder des articles](warehouse-how-to-cross-dock-items.md).

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
