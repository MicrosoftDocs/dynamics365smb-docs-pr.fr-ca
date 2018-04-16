---
title: "Transfert d'articles entre des magasins entrepôt| Microsoft Docs"
description: "Décrit comment déplacer un inventaire d'un emplacement ou d'un entrepôt vers un autre soit avec le journal reclassement soit à l'aide d'ordres de transfert."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.date: 01/25/2018
ms.author: SorenGP
ms.translationtype: HT
ms.sourcegitcommit: b34f276a764f0e828fbc1f015429df9852242a4c
ms.openlocfilehash: 8ee703865f86c0edcc5bff77d8bd04cc2bd107be
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="transfer-inventory-between-locations"></a>Transfert d'inventaire entre des emplacements
Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert. Vous pouvez également utiliser le journal reclassement article.

Avec des ordres de transfert, vous pouvez livrer un transfert sortant à partir d'un emplacement et recevoir un transfert entrant à l'autre emplacement. Cela vous permet de gérer les activités entrepôt impliquées et garantit que les quantités en inventaire sont mises à jour correctement.

Avec la feuille reclassement, il vous suffit de renseigner les champs **Code magasin** et **Nouveau code magasin**. Lorsque vous reportez le journal, les écritures article sont ajustées dans les emplacements en question. Avec cette méthode, les activités entrepôt ne sont pas traitées.

> [!NOTE]  
>   Si vous avez des articles enregistrés dans votre inventaire sans code d'emplacement, par exemple datant d'une période où vous n'aviez qu'un seul entrepôt, vous ne pouvez pas transférer ces articles en utilisant des ordres de transfert. Au lieu de cela, vous devez utiliser le journal reclassement pour reclasser les articles à partir d'un code emplacement vide vers un code d'emplacement réel.  Pour plus d'informations, voir l'étape 3 dans la section « Pour transférer des articles avec le journal reclassement article ».

Pour transférer des articles, des acheminements transfert et magasins doivent être créés. Pour plus d'informations, voir [Configurer des emplacements](inventory-how-setup-locations.md).

## <a name="to-transfer-items-with-a-transfer-order"></a>Pour transférer des articles avec un ordre de transfert
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Ordres de transfert**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Ordre de transfer**, renseignez les champs comme nécessaire. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
   >   Si vous avez renseigné les champs **Code transit**, **Code agent de livraison**, et **Prestation agent de livraison** dans la fenêtre **Spéc. acheminement transfert** lors de la configuration de l'acheminement transfert, les champs correspondants sur l'ordre de transfert sont renseignés automatiquement.

    Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à livrer les articles.
3. Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.

    Les articles sont à présent en transit entre les magasins spécifiés, selon l'acheminement transfert spécifié.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles.
4. Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.

## <a name="to-transfer-items-with-the-item-reclassification-journal"></a>Pour transférer des articles avec le journal reclassement article
1. Sélectionnez l'icône ![Page ou état pour la recherche](media/ui-search/search_small.png "Page ou état pour la recherche"), entrez **Feuilles reclassement article**, puis sélectionnez le lien connexe.
2. Dans la fenêtre **Feuilles reclassement article**, renseignez les champs selon vos besoins. [!INCLUDE [tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.

    > [!NOTE]  
   >   Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.
4. Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.
5. Sélectionnez l'action **Valider**.

## <a name="see-also"></a>Voir aussi
[Gestion du stock](inventory-manage-inventory.md)  
[Configurer des emplacements](inventory-how-setup-locations.md)  

[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Personnalisation de votre expérience [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)

