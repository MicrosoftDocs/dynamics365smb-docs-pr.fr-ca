---
title: Archiver les documents vente et les documents achat
description: 'Vous pouvez archiver des bons de commande et des documents de vente, des devis, des retours et des commandes permanentes, et restaurer les documents originaux si nécessaire.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 06/02/2023
ms.custom: bap-template
ms.search.form: '42, 49, 50, 459, 460, 5159, 5162, 5164, 5167, 6627, 6630, 6644, 9305, 9306, 9346, 9347, 9348, 9349'
---
# <a name="archive-documents" />Archiver des documents

Vous pouvez archiver des bons de commande et des documents de vente, des devis, des retours et des commandes permanentes. L’archivage des documents vous permet de restaurer les documents originaux, si nécessaire. Vous pouvez archiver des documents vente ou achat plusieurs fois, en enregistrant une version archivée différente chaque fois.

Pour les documents de vente archivés où l’original existe toujours et n’est pas reporté, vous pouvez utiliser l’action **Restaurer** pour remplacer le document actuel par une version archivée.

Pour les documents archivés où l’original est désactivé, vous pouvez réutiliser le contenu uniquement en copiant les données, par exemple en utilisant l’action **Copier à partir du document**.  

## <a name="to-set-up-automatic-document-archiving" />Pour configurer l'archivage automatique des documents

Vous pouvez configurer l’archivage automatique des bons de commande et des documents de vente, des devis, des commandes permanentes et des retours. Lorsque l’archivage automatique est activé, une nouvelle version du document archivé est créée lorsque quelqu’un effectue les actions suivantes :

* Modifie ou supprime un document.
* Imprime, télécharge ou envoie un document par courriel.
* Convertit un devis en commande ou en facture.
* Publie une commande.

La procédure suivante décrit comment configurer l'archivage automatique des documents vente. La procédure est identique pour les documents achat.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.
2. Sur le raccourci **Archivage**, spécifiez s’il faut activer l’archivage automatique pour les différents types de documents de vente. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]

Le tableau suivant décrit les options disponibles pour le champ **Archiver devis**.

|Option|Désignation|
|------|-----------|
|**Jamais**| N’archivez pas les devis lorsqu’ils sont supprimés.|
|**Question**|Invitez l’utilisateur à archiver ou non les devis lorsqu’ils sont supprimés.|
|**Toujours**|Archivez automatiquement les devis lorsqu’ils sont supprimés.|

## <a name="to-manually-archive-a-sales-order" />Pour archiver manuellement un document de vente

La procédure suivante décrit comment archiver manuellement un document de vente. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez un document de vente que vous souhaitez archiver.  
3. Sélectionnez l'action **Archiver document**.

Le document de vente est archivé. Vous pouvez l'afficher sur la page **Documents de vente archivés**.

## <a name="to-restore-a-non-posted-sales-order-from-the-archive" />Pour restaurer une document de vente non reporté depuis les archives

La procédure suivante décrit comment restaurer un document de vente archivé dans le document de vente d’origine. Il n'est possible de restaurer un document que si le document d’origine n’a pas été reporté. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Archives documents de vente**, puis sélectionnez le lien associé.
2. Sélectionnez le document de vente archivé, ou une version de celui-ci, que vous voulez restaurer, puis sélectionnez l'action **Restaurer**.  

Le contenu du document de vente d’origine est remplacé par celui de la version archivée.

## <a name="to-delete-archived-sales-orders" />Pour supprimer des documents de vente archivés

Utilisez une stratégie de rétention pour nettoyer les documents archivés dont vous n’avez plus besoin. Les stratégies de rétention permettent aux administrateurs de définir la durée de stockage des données. Par exemple, ils peuvent configurer une stratégie qui supprime les données après une date d’expiration. Pour plus d’informations, voir [Définir les stratégies de rétention](admin-data-retention-policies.md).

Il y a quelques points à noter concernant la création de stratégies de rétention pour les documents archivés :

* *Si le document d’origine n’a pas été supprimé, Business Central ne supprime pas les versions archivées. Les versions archivées n’expirent pas tant que l’original existe.
* Lorsque vous configurez la stratégie de rétention, vous pouvez spécifier que vous souhaitez que la stratégie supprime toutes les versions archivées d’un document, à l’exception de la plus récente. Par exemple, vous pouvez avoir 10 versions d’un document et vouloir conserver une copie de la dernière. 
* Business Central calcule la date d’expiration des documents en fonction de la date de la version archivée la plus récente.

## <a name="see-also" />Voir aussi

[Suivi des lignes document](across-how-to-track-document-lines.md)  
[Ventes](sales-manage-sales.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
