---
title: Procédure d'archivage des documents vente et achat | Microsoft Docs
description: Vous pouvez archiver des documents de vente et des bons de commande, des devis, des retours et des commandes permanentes, et vous pouvez utiliser le document archivé pour recréer le document d'origine.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 209ef492bf5620921ce371a17227653576dcae8a
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5775907"
---
# <a name="archive-documents"></a>Archiver des documents
Vous pouvez archiver des bons de commande, des documents de vente, des devis, des retours et des commandes permanentes, par exemple parce que vous voulez enregistrer une copie d'un document pour la réutiliser plus tard. Vous pouvez archiver des documents vente ou achat plusieurs fois, en enregistrant une version archivée différente chaque fois.

Pour les documents archivés où l'original existe et n'est pas reporté, vous pouvez utiliser la fonction **Restaurer** pour remplacer l'original par la version archivée du document. Ceci est pratique si vous devez restaurer le contenu d'un document à un état antérieur.

Pour les documents archivés où l'original est désactivé, vous pouvez réutiliser le contenu uniquement en copiant les données, par exemple avec la fonction **Copier à partir du document**.   

## <a name="to-set-up-automatic-document-archiving"></a>Pour configurer l'archivage automatique des documents  
Vous pouvez configurer l'archivage automatique des documents de vente, des bons de commande, des devis, des commandes permanentes et des retours, avant de supprimer des documents.

La procédure suivante décrit comment configurer l'archivage automatique des documents vente. La procédure est identique pour les documents achat.
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes et à recevoir**, renseignez les champs comme suit.

|Champ|Description|
|-----|-----------|
|**Archivage des devis**|**Jamais** pour ne jamais archiver les devis lorsqu'ils sont supprimés. **Question** pour demander à l'utilisateur s'il souhaite archiver les devis lorsqu'ils sont supprimés. **Toujours** pour archiver automatiquement les devis lorsqu'ils sont supprimés.|
|**Archivage des commandes permanentes ventes**|Permet d'archiver automatiquement les commandes permanentes ventes chaque fois qu'elles sont supprimées.|
|**Arch. commandes et retours**|Permet d'archiver automatiquement les documents de vente chaque fois qu'ils sont supprimés.|

## <a name="to-archive-a-sales-order"></a>Pour archiver un document de vente
La procédure suivante décrit comment archiver un document de vente. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Ouvrez un document de vente que vous souhaitez archiver.  
3.  Sélectionnez l'action **Archiver document**.

Le document de vente est archivé. Vous pouvez l'afficher sur la page **Documents de vente archivés**.

## <a name="to-restore-a-non-posted-sales-order-from-the-archive"></a>Pour restaurer une document de vente non reporté depuis les archives
La procédure suivante décrit comment insérer le contenu d'un document de vente archivé dans le document de vente d'origine. Cela n'est possible que lorsque le document source n'a pas été reporté. La procédure est identique pour l'ensemble des commandes, commandes permanentes, retours et devis.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Documents de vente archivés**, puis sélectionnez le lien associé.
2. Sélectionnez le document de vente archivé, ou une version de celui-ci, que vous voulez restaurer, puis sélectionnez l'action **Restaurer**.  

Le contenu du document de vente d'origine est remplacé par celui de la version archivée sélectionnée.

## <a name="to-delete-archived-sales-orders"></a>Pour supprimer des documents de vente archivés
La procédure suivante décrit comment supprimer des documents de vente archivés. La procédure est identique pour les autres documents achat et vente archivés.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Supprimer les versions de documents de vente archivées**, puis sélectionnez le lien associé.  
2.  Sur la page **Supprimer les versions documents de vente archivées**, sélectionnez les filtres appropriés.  
3.  Cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi
[Suivre des lignes document](across-how-to-track-document-lines.md)  
[Vente](sales-manage-sales.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]