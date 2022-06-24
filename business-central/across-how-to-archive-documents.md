---
title: Archiver les documents vente et les documents achat
description: Vous pouvez archiver des bons de commande et des documents de vente, des devis, des retours et des commandes permanentes, et restaurer les documents originaux si nécessaire.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: 42, 49, 50, 459, 460, 5159, 5162, 5164, 5167, 6627, 6630, 6644, 9305, 9306, 9346, 9347, 9348, 9349
ms.date: 03/06/2022
ms.author: bholtorf
ms.openlocfilehash: c81248844f603f80304822c0ce089c666f9be9bc
ms.sourcegitcommit: 7b6d70798b4da283d1d3e38a05151df2209c2b72
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/12/2022
ms.locfileid: "8950339"
---
# <a name="archive-documents"></a>Archiver des documents
Vous pouvez archiver des bons de commande et des documents de vente, des devis, des retours et des commandes permanentes. L’archivage des documents vous permet de restaurer les documents originaux, si nécessaire. Vous pouvez archiver des documents vente ou achat plusieurs fois, en enregistrant une version archivée différente chaque fois.

Pour les documents de vente archivés où l’original existe toujours et n’est pas reporté, vous pouvez utiliser l’action **Restaurer** pour remplacer le document actuel par une version archivée. 

Pour les documents archivés où l’original est désactivé, vous pouvez réutiliser le contenu uniquement en copiant les données, par exemple en utilisant l’action **Copier à partir du document**.  

## <a name="to-set-up-automatic-document-archiving"></a>Pour configurer l'archivage automatique des documents

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

## <a name="to-archive-a-sales-order"></a>Pour archiver un document de vente

La procédure suivante décrit comment archiver un document de vente. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Documents de vente**, puis sélectionnez le lien associé.  
2. Ouvrez un document de vente que vous souhaitez archiver.  
3. Sélectionnez l'action **Archiver document**.

Le document de vente est archivé. Vous pouvez l'afficher sur la page **Documents de vente archivés**.

## <a name="to-restore-a-non-posted-sales-order-from-the-archive"></a>Pour restaurer une document de vente non reporté depuis les archives

La procédure suivante décrit comment restaurer un document de vente archivé dans le document de vente d’origine. Il n'est possible de restaurer un document que si le document d’origine n’a pas été reporté. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Archives documents de vente**, puis sélectionnez le lien associé.
2. Sélectionnez le document de vente archivé, ou une version de celui-ci, que vous voulez restaurer, puis sélectionnez l'action **Restaurer**.  

Le contenu du document de vente d’origine est remplacé par celui de la version archivée.

## <a name="to-delete-archived-sales-orders"></a>Pour supprimer des documents de vente archivés

La procédure suivante décrit comment supprimer des documents de vente archivés. La procédure est identique pour les autres documents achat et vente archivés.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Archives documents de vente**, puis sélectionnez le lien associé.  
2. Choisissez l’action **Supprimer les anciennes versions**, puis, sur la page **Supprimer les versions de documents de vente archivées**, sélectionnez les filtres appropriés.  
3. Cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi

[Suivre des lignes document](across-how-to-track-document-lines.md)  
[Vente](sales-manage-sales.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
