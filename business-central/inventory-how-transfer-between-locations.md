---
title: Transfert d'articles entre des magasins entrepôt| Microsoft Docs
description: Décrit comment déplacer un inventaire d'un emplacement ou d'un entrepôt vers un autre soit avec le journal reclassement soit à l'aide d'ordres de transfert.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: move, warehouse
ms.date: 04/01/2019
ms.author: SorenGP
ms.openlocfilehash: 95ce328595bccaff230699c56e603ba55f9375b7
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "916861"
---
# <a name="transfer-inventory-between-locations"></a>Transfert d'inventaire entre des emplacements
Vous pouvez transférer des articles en inventaire entre des emplacements en créant des ordres de transfert. Vous pouvez également utiliser le journal reclassement article.

Avec des ordres de transfert, vous pouvez livrer un transfert sortant à partir d'un emplacement et recevoir un transfert entrant à l'autre emplacement. Cela vous permet de gérer les activités entrepôt impliquées et garantit que les quantités en inventaire sont mises à jour correctement.

Avec la feuille reclassement, il vous suffit de renseigner les champs **Code magasin** et **Nouveau code magasin**. Lorsque vous reportez le journal, les écritures article sont ajustées dans les emplacements en question. Avec cette méthode, les activités entrepôt ne sont pas traitées.

> [!NOTE]  
>   Si vous avez des articles enregistrés dans votre inventaire sans code d'emplacement, par exemple datant d'une période où vous n'aviez qu'un seul entrepôt, vous ne pouvez pas transférer ces articles en utilisant des ordres de transfert. Au lieu de cela, vous devez utiliser le journal reclassement pour reclasser les articles à partir d'un code d'emplacement vide vers un code d'emplacement réel.  Pour plus d'informations, voir l'étape 3 dans [Pour transférer des articles avec le journal reclassement article](inventory-how-transfer-between-locations.md#to-transfer-items-with-the-item-reclassification-journal).

Pour transférer des articles, des acheminements transfert et des emplacements doivent être créés. Pour plus d'informations, voir [Configurer des emplacements](inventory-how-setup-locations.md).

## <a name="to-transfer-items-with-a-transfer-order"></a>Pour transférer des articles avec un ordre de transfert
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Ordres de transfert**, puis sélectionnez le lien associé.
2. Sur la page **Ordre de transfer**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]  
    >   Si vous avez renseigné les champs **Code transit**, **Code agent de livraison**, et **Service agent de livraison** sur la page **Spéc. acheminement transfert** lors de la configuration de l'acheminement transfert ; ensuite les champs correspondants sur l'ordre de transfert sont renseignés automatiquement.

    Lorsque vous renseignez le champ **Code prestation transporteur**, le programme calcule la date de réception au magasin de destination en ajoutant le délai d'expédition de la prestation transporteur à la date d'expédition.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à livrer les articles.
3. Cliquez sur **Valider**, choisissez l'option **Expédition**, puis cliquez sur le bouton **OK**.

    Les articles sont à présent en transit entre les magasins spécifiés, selon l'acheminement transfert spécifié.

    En tant que magasinier dans l'emplacement provenance transfert, continuez à recevoir les articles.
4. Cliquez sur **Valider**, choisissez l'option **Réception**, puis cliquez sur le bouton **OK**.

## <a name="to-transfer-items-with-the-item-reclassification-journal"></a>Pour transférer des articles avec le journal reclassement article
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux reclassement article**, puis sélectionnez le lien associé.
2. Sur la page **Journal reclassement article**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Dans le champ **Code magasin**, entrez le magasin où les articles sont actuellement stockés.

    > [!NOTE]  
    >   Pour transférer les articles qui n'ont aucun code magasin, laissez le champ **Code magasin** vide.
4. Dans le champ **Nouveau Code magasin**, indiquez le magasin vers lequel vous souhaitez transférer les articles.
5. Sélectionnez l'action **Valider**.

## <a name="see-also"></a>Voir aussi
[Gestion du stock](inventory-manage-inventory.md)  
[Configurer des emplacements](inventory-how-setup-locations.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Modification des fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)
