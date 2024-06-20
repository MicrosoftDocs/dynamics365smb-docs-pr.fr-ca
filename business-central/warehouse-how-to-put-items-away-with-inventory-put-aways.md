---
title: Comment ranger des articles avec le rangement inventaire
description: Découvrez comment utiliser les documents de rangement inventaire pour enregistrer et reporter les informations de rangement et de réception.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 09/19/2023
ms.custom: bap-template
ms.search.forms: '7375,'
---
# <a name="put-items-away-with-inventory-put-aways"></a>Ranger des articles avec le rangement stock

Dans [!INCLUDE[prod_short](includes/prod_short.md)], vous recevez des articles et les rangez en utilisant l’une des quatre méthodes décrites dans le tableau suivant.

|Méthode|Processus entrant|Réceptions requises|Rangements requis|Niveau de complexité (pour plus d’informations, consultez [Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md))|  
|------------|---------------------|--------------|----------------|------------|  
|A|Report de la réception et du rangement à partir de la ligne commande|||Aucune activité entrepôt dédiée.|  
|B|Report de la réception et du rangement à partir d'un document de rangement inventaire||Activé|De base : commande par commande.|  
|C|Report de la réception et du rangement à partir d'un document réception entrepôt|Activé||De base : envoi/réception regroupés pour plusieurs commandes.|  
|J|Report de la réception d'un document réception entrepôt et report du rangement à partir d'un document de rangement entrepôt|Activé|Activé|Avancé|  

Learn more at [Flux d’enlogement](design-details-inbound-warehouse-flow.md).

Cet article fait référence à la méthode B dans le tableau.

Lorsque votre emplacement est configuré pour exiger un traitement des rangements, mais qu’il ne l’est pas pour un traitement des réceptions, utilisez un document **Rangement inventaire** pour enregistrer et reporter les informations de rangement et de réception pour vos documents origine. Les documents source entrants peuvent être des bons de commande, des retours vente et des ordres de transfert entrant.

> [!NOTE]
> Les sorties de la production et de l’assemblage représentent également des documents origine entrants. Pour en savoir plus sur la gestion des sorties de la production et de l’assemblage pour les processus internes, consultez [Détails de conception : Flux d’entrepôt internes](design-details-internal-warehouse-flows.md).

Vous pouvez créer un rangement inventaire de trois manières :  

* Créez le rangement inventaire directement à partir du document source proprement dit.  
* Créez des rangements inventaire pour plusieurs documents source simultanément en utilisant un traitement en lot.  
* Créez le rangement en deux étapes en publiant d’abord le document origine pour rendre les articles disponibles pour le rangement. Vous pouvez créer le rangement inventaire sur la base du document source en utilisant la page **Rangement inventaire**.  

## <a name="to-create-an-inventory-put-away-from-the-source-document"></a>Pour créer un rangement inventaire à partir du document source

1. Dans le document source, qui peut être un bon de commande, un retour vente ou un ordre de transfert entrant, choisissez l’action **Créer prélèv./rangement inventaire**.  
2. Activez la case à cocher **Créer prélèv./rangement inventaire**.
3. Cliquez sur le bouton **OK**. Un nouveau rangement inventaire est créé.

## <a name="to-create-multiple-inventory-put-aways-with-a-batch-job"></a>Pour créer plusieurs rangements inventaire avec un traitement en lot

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Créer rangement/prélèvement/mouvement d’inventaire**, puis choisissez le lien associé. 
2. Sur le raccourci **Demande entrepôt**, utilisez les champs **Document origine** et **N° origine** pour opérer un filtrage sur certains types de documents ou des plages de numéros de document. Par exemple, vous pouvez créer des rangements uniquement pour les bons de commande.
3. Sur le raccourci **Options**, cochez la case **Créer rangement inventaire**.
4. Choisissez le bouton **OK**. Les rangements stock spécifiés sont créés.

## <a name="to-create-the-put-away-in-two-steps"></a>Pour créer le rangement en deux étapes

### <a name="to-request-an-inventory-put-away-by-releasing-the-source-document"></a>Pour demander un rangement inventaire en libérant le document d'source

Lorsque vous libérez des bons de commande, des retours vente et des ordres de transfert entrants, les articles des commandes deviennent disponibles pour être rangés. Les étapes suivantes décrivent comment rendre les articles d’un bon de commande prêts à être rangés.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Bons de commande**, puis sélectionnez le lien associé.
2. Sélectionnez le bon de commande que vous voulez libérer, puis sélectionnez l'action **Libérer**.  

### <a name="to-create-an-inventory-put-away-based-on-the-source-document"></a>Pour créer un rangement inventaire sur la base du document source

Un employé d'entrepôt peut créer un nouveau rangement inventaire basé sur le document source émis.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangement inventaire**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Document origine**, sélectionnez le type de document origine que vous rangez.  
4. Dans le champ **N° origine**, sélectionnez le document origine.  
5. Sinon, choisissez l'action **Extraire document source** pour sélectionner le document à partir de la liste des documents sources entrants prêts pour le rangement dans l'emplacement.  
6. Choisissez le bouton **OK** pour renseigner les lignes rangement en fonction du document origine sélectionné.  

## <a name="to-record-the-inventory-put-away"></a>Pour enregistrer les rangements inventaire

1. Sur la page **Rangements inventaire**, ouvrez un document de rangement créé au préalable.  
2. Dans le champ **Code de zone** sur les lignes rangement, les zones où les articles doivent être rangés sont proposées sur la base de la zone par défaut de l’article. Si nécessaire, vous pouvez modifier la zone.  
3. Exécutez le rangement, puis saisissez la quantité effectivement rangée dans le champ **Quantité à traiter**.

    Si vous devez placer les articles d’une ligne dans plusieurs zones, notamment parce que la zone indiquée est pleine, utilisez l’action **Éclater ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.  
4. Après avoir rangé les articles, choisissez l’action **Reporter**.  

    * Reporter la réception des lignes du document source qui ont été rangées
    * Si l’emplacement utilise des zones, le report crée également des écritures entrepôt pour reporter les modifications apportées aux quantités zone.

    [!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

## <a name="see-also"></a>Voir aussi .

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
