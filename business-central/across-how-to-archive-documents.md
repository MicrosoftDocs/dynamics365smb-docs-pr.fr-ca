---
title: "Procédure d'archivage des documents vente et achat | Microsoft Docs"
description: "Vous pouvez archiver des documents de vente et des bons de commande, des devis, des retours et des commandes permanentes, et vous pouvez utiliser le document archivé pour recréer le document d'origine."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 33b900f1ac9e295921e7f3d6ea72cc93939d8a1b
ms.openlocfilehash: 4827e25d97127faf691b96df9868320bb47dee39
ms.contentlocale: fr-ca
ms.lasthandoff: 11/26/2018

---
# <a name="archive-documents"></a>Archiver des documents
Vous pouvez archiver des documents de vente et des bons de commande, des devis, des retours et des commandes permanentes, et vous pouvez utiliser le document archivé pour recréer le document d'origine.

## <a name="to-set-up-automatic-document-archiving"></a>Pour configurer l'archivage automatique des documents  
Vous pouvez configurer l'archivage automatique des documents de vente, des bons de commande, des devis, des commandes permanentes et des retours, avant de supprimer des documents.

La procédure suivante décrit comment configurer l'archivage automatique des documents vente. La procédure est identique pour les documents achat.
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration ventes et à recevoir**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes et à recevoir**, renseignez les champs comme suit.

|Champ|Description|
|-----|-----------|
|**Archivage des devis**|**Jamais** pour ne jamais archiver les devis lorsqu'ils sont supprimés. **Question** pour demander à l'utilisateur s'il souhaite archiver les devis lorsqu'ils sont supprimés. **Toujours** pour archiver automatiquement les devis lorsqu'ils sont supprimés.|
|**Archivage des commandes permanentes ventes**|Permet d'archiver automatiquement les commandes permanentes ventes chaque fois qu'elles sont supprimées.|
|**Arch. commandes et retours**|Permet d'archiver automatiquement les documents de vente chaque fois qu'ils sont supprimés.|

## <a name="to-archive-a-sales-order"></a>Pour archiver un document de vente
La procédure suivante décrit comment archiver un document de vente. La procédure est identique pour les commandes, les commandes ouvertes, les retours et les devis.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Ouvrez un document de vente que vous souhaitez archiver.  
3.  Sélectionnez l'action **Archiver document**.

Le document de vente est archivé. Vous pouvez l'afficher sur la page **Documents de vente archivés**. À partir d'ici, vous pouvez également l'utiliser pour recréer le document de vente d'origine.

## <a name="to-recreate-a-sales-order-from-the-archive"></a>Pour recréer un document de vente à partir de l'archive
La procédure suivante décrit comment recréer un document de vente. La procédure est identique pour les commandes, les commandes ouvertes, les retours et les devis.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente archivés**, puis sélectionnez le lien associé.
2.  Sélectionnez le document de vente archivé que vous voulez recréer, puis sélectionnez l'action **Restaurer**.  

Le document de vente est créé et ajouté à la page **Documents de vente**.

## <a name="to-delete-archived-sales-orders"></a>Pour supprimer des documents de vente archivés
La procédure suivante décrit comment supprimer des documents de vente archivés. La procédure est identique pour les autres documents achat et vente archivés.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Supprimer versions document de vente archivées**, puis sélectionnez le lien associé.  
2.  Sur la page **Supprimer les versions documents de vente archivées**, sélectionnez les filtres appropriés.  
3.  Cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi
[Suivre des lignes document](across-how-to-track-document-lines.md)  
[Ventes](sales-manage-sales.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

