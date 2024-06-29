---
title: Réception des articles
description: Cet article est un aperçu des différentes manières de recevoir des articles dans un entrepôt avec une réception entrepôt.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 06/06/2024
ms.search.form: '5768, 7330, 7332, 7333, 7342, 7363, 8510, 9008'
ms.service: dynamics-365-business-central
---
# <a name="receive-items-with-warehouse-receipts"></a>Réceptionner des articles avec une réception entrepôt

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous recevez des articles et les rangez en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus entrant|Réceptions requises|Rangements requis|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire||Activé|De base : commande par commande.|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt|Activé||De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt|Activé|Activé|Avancé|  

Pour en savoir plus sur la gestion des articles entrants, consultez [Flux d’enlogement](design-details-inbound-warehouse-flow.md).

L’article suivant fait référence aux méthodes C et D dans le tableau précédent.

## <a name="receive-items-with-a-warehouse-receipt"></a>Réceptionner des articles avec une réception entrepôt

Lorsque les articles arrivent dans un entrepôt configuré pour traiter les réceptions entrepôt, vous devez extraire les lignes du document source libéré ayant déclenché la réception. Si vous utilisez des zones, vous pouvez soit accepter la zone par défaut, soit spécifier la zone dans lequel placer les articles. Ce dernier peut être nécessaire lorsque vous recevez un article pour la première fois. Alors, renseignez les quantités d’articles reçus et reportez la réception.  

Vous pouvez créer une réception entrepôt de deux manières :

* En mode « push », lorsque le travail est effectué commande par commande. Sélectionnez l’action **Créer réception entrepôt** dans le document source, tel qu’un bon de commande, un retour vente ou un ordre de transfert pour créer une réception entrepôt pour un document source.
* En mode « pull », où vous utilisez l’action **Libérer** du document origine, tel qu’une bon de commande, un retour vente ou un ordre de transfert pour libérer le document dans l’entrepôt. Un employé d'entrepôt crée une **Réception entrepôt** pour un ou plusieurs documents source libérés. La procédure suivante décrit comment créer une réception entrepôt en mode « push ». La procédure suivante décrit comment créer une réception entrepôt en mode « pull ».

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Réceptions entrepôt**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  

    Renseignez le champ **Code emplacement** dans le raccourci **Général**. Lorsque vous récupérez des lignes document origine,certaines des informations de l'en-tête sont copiées dans chaque ligne.

    Pour un emplacement qui nécessite des zones, remplissez le champ **Code de zone**. Selon votre configuration, [!INCLUDE[prod_short](includes/prod_short.md)] peut ajouter le code de zone pour vous. Pour en savoir plus, voir [Zone et codes de zone](warehouse-how-receive-items.md#zone-and-bin-codes).  

3. Vous pouvez obtenir le document origine de deux manières :

    1. Choisissez l'action **Extraire documents origine**. La page **Documents origine - Entrant** s’ouvre. Ici, vous pouvez sélectionner un ou plusieurs documents source libérés dans l’entrepôt qui nécessitent une réception.
    2. Choisissez l'action **Filtrer pour extr. doc. orig.**. La page **Filtres pour extr. doc. orig. - Entrants** s’ouvre. Ici, vous pouvez sélectionner le filtre de document origine et l’exécuter. Toutes les lignes du document source libéré qui répondent aux critères de filtre sont ajoutées sur la page **Réception entrepôt**. Learn more at [Procédure : utiliser des filtres afin d’obtenir des documents origine](warehouse-how-receive-items.md#how-to-use-filters-to-get-source-documents).

4. Définissez la quantité à recevoir.

    Le champ **Qté à recevoir** contient la quantité restante pour chaque ligne, mais vous pouvez modifier cette quantité selon vos besoins. 

    Pour définir la valeur dans le champ **Qté à recevoir** sur toutes les lignes à zéro, choisissez l’action **Supprimer qté à recevoir**. Par exemple, définir les quantités sur zéro est utile si vous utilisez un lecteur de code-barres pour mettre à jour les quantités reçues. Pour ajouter à nouveau les quantités restantes à partir du document origine, choisissez l’action **Remplir qté à recevoir**.  

    Sur un document réception entrepôt où la quantité reçue est supérieure à celle commandée, saisissez la quantité réellement reçue dans le champ **Qté à recevoir**. Si l’augmentation est inférieure ou égale à la tolérance indiquée par le code de sur-réception attribué, le champ **Quantité de sur-réception** est mis à jour pour afficher la quantité de dépassement de la valeur dans le champ **Quantité**. Si l’augmentation est supérieure à la tolérance, la sur-réception n’est pas autorisée.

5. Reportez la réception entrepôt. Les champs relatifs à la quantité dans les documents source sont mis à jour et les articles sont ajoutés à l’inventaire.  

    [!INCLUDE [preview-posting-shipment](includes/preview-posting-shipment.md)]

    > [!TIP]
    > Si vous utilisez le rangement entrepôt, qui fait référence à la méthode D du tableau au début de cet article, les articles sont reçus mais ne peuvent pas être prélevés tant qu’ils n’ont pas été rangés. Pour en savoir plus sur le rangement d’articles, consultez [Ranger des articles avec le rangement entrepôt](warehouse-how-to-put-items-away-with-warehouse-put-aways.md).
    >
    > Sinon, envisagez d’utiliser l’action **Reporter et imprimer**. L’action reportera la réception et l’imprimera en tant qu’instruction de rangement indiquant où placer l’article.

    > [!NOTE]  
    > Si votre entrepôt utilise le transbordement, vous pouvez vérifier si vous pouvez transborder des articles sans les ranger. Pour en savoir plus sur le transbordement, consultez [Transborder des articles](warehouse-how-to-cross-dock-items.md).

## <a name="how-to-use-filters-to-get-source-documents"></a>Procédure : utiliser des filtres afin d’obtenir des documents origine

À partir d’une réception entrepôt, vous pouvez utiliser la page **Filtres pour extr. doc. orig.** afin d’extraire les lignes du document source libéré qui indiquent les articles à recevoir.

1. Dans la réception entrepôt, choisissez l’action **Filtrer pour extr. doc. orig.**.
2. Pour configurer un nouveau filtre, entrez un code descriptif dans le champ **Code**, puis choisissez l’action **Modifier**.

    La page **Fiche filtre document origine - Entrants** s’ouvre.

3. Utilisez les filtres pour définir le type de lignes du document origine à récupérer. Par exemple, vous pouvez sélectionner des types de documents origine, tels que des commande achat ou des ordres de transfert.
4. Choisir **Exécuter**.  

Toutes les lignes du document source libéré qui répondent aux critères de filtre sont ajoutées sur la page **Réception entrepôt** sur laquelle vous avez activé les filtres.

Le nombre de combinaisons de filtres est illimité. Les filtres sont enregistrés sur la page **Filtres pour extr. doc. orig.** et seront disponibles la prochaine fois que vous en aurez besoin. Vous pouvez modifier les critères à tout moment en choisissant l'action **Modifier**.

## <a name="zone-and-bin-codes"></a>Zone et codes de zone

Pour réceptionner des articles portant des codes classe entrepôt différents du code classe de la zone indiquée dans le champ **Code de zone** de l’en-tête du document, effacez la valeur du champ **Code de zone** de l’en-tête avant d’extraire les lignes des documents source des articles.  
<!-- TBD, table with comparison of various options-->

Si des zones sont obligatoires pour un emplacement, les codes de zone et zone sont ajoutés aux documents de réception entrepôt comme suit :

* Pour les configurations avancées qui utilisent le rangement et le prélèvement dirigés, [!INCLUDE [prod_short](includes/prod_short.md)] utilise le code de zone réception de la page **Fiche emplacement** de l’emplacement. Si aucun code de zone réception n’est spécifié, aucune zone n’est spécifiée. Si l’article et les zones de réception ne correspondent pas, le code de zone réception est vide.
* Dans d’autres configurations, si aucun code de zone réception n’est spécifié, [!INCLUDE [prod_short](includes/prod_short.md)] utilise le code de zone du document source.

## <a name="see-also"></a>Voir aussi .

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
