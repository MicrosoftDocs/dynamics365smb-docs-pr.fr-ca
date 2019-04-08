---
title: "Procédure : annuler le report d'assemblage | Microsoft Docs"
description: Vous pouvez parfois être amené à annuler un ordre d'assemblage reporté, par exemple, si la commande a été reportée avec des erreurs qui doivent être corrigées, ou parce qu'il n'aurait pas dû être reporté en premier et doit être annulé.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: kit, kitting
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 83545421ec7539b214788d08d4f4b33c4bdb71d7
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813785"
---
# <a name="undo-assembly-posting"></a>Annuler le report d'assemblage
Vous pouvez parfois être amené à annuler un ordre d'assemblage reporté, par exemple, si la commande a été reportée avec des erreurs qui doivent être corrigées, ou parce qu'il n'aurait pas dû être reporté en premier et doit être annulé.

Lorsque vous annulez un ordre d'assemblage reporté, un ensemble d'écritures du grand livre d'articles de correction est créé pour inverser les écritures d'origine. Chaque écriture production positive pour l'élément d'assemblage est inversée par une écriture production négative. Chaque écriture production négative pour une composante d'assemblage est inversée par une écriture production positive. L'affectation des coûts fixes est créée automatiquement entre les écritures de correction et les écritures d'origine afin de garantir l'exactitude de l'inversion de coût.  

Lorsque vous annulez un ordre d'assemblage entièrement reporté, vous pouvez choisir de recréer l'ordre d'assemblage à son état d'origine, par exemple, pour apporter des corrections avant un nouveau report. Sinon, vous pouvez choisir de ne pas recréer l'ordre d'assemblage.  

Lorsque vous annulez un ordre d'assemblage partiellement validé, tous les champs de quantité concernés, notamment les champs **Quantité assemblée**, **Quantité consommée** et **Quantité restante**, sont restaurés avec leur valeur précédant la validation en question.  

Pour recréer ou restaurer des ordres d'assemblage, il faut que l'élément d'assemblage qui résultait du report initial respecte les conditions suivantes :  

-   L'article doit toujours être en inventaire. En d'autres termes, il ne doit pas avoir été vendu ou consommé dans le cadre de transactions sortantes.  
-   Il ne doit pas être réservé.  
-   Il doit exister dans la zone dans laquelle il a été produit.  

De plus, les ordres d'assemblage existants ne peuvent être restaurés que si le nombre de lignes et la séquence de lignes de l'ordre de assemblage initial ne sont pas modifiés.  

> [!TIP]  
>  Pour résoudre les conflits dus à des modifications de ligne, vous pouvez rétablir manuellement les modifications sur les lignes en question avant d'annuler l'ordre d'assemblage reporté associé. Sinon, vous pouvez reporter l'ordre d'assemblage entièrement et choisir de le recréer lorsque vous annulez le report.  

La procédure suivante décrit comment annuler les ordres d'assemblage reportés dans lesquels les articles ont été assemblés pour stock. Si vous souhaitez annuler les ordres d'assemblage validés pour lesquels les articles ont été assemblés pour une commande vente, vous devez exécuter la fonction **Annuler expédition** sur l'expédition validée qui se rapporte à l'ordre d'assemblage validé. Pour plus d'informations, voir [Inverser des reports](finance-how-reverse-journal-posting.md). L'annulation de l'ordre d'assemblage reporté se produit alors automatiquement de la même manière que décrit dans cette rubrique.  

## <a name="to-undo-posting-of-an-assembly-order"></a>Pour annuler le report d'un ordre d'assemblage  
1.  Pour annuler un ordre d'assemblage entièrement ou partiellement reporté, choisissez l'icone ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Ordres d'assemblage reportés**, puis sélectionnez le lien associé.  

    La page **Ordres d'assemblage reportés** s'ouvre avec un ou plusieurs ordres d'assemblage qui ont été reportés à partir de l'ordre d'assemblage en question. Chaque report partiel crée un ordre d'assemblage reporté distinct.  
2.  Ouvrez l'ordre d'assemblage reporté que vous souhaitez annuler, puis choisissez **Annuler l'assemblage**.  

    Si l'ordre d'assemblage reporté que vous souhaitez annuler est lié à un ordre d'assemblage entièrement reporté qui est maintenant supprimé, vous avez la possibilité de le recréer, généralement parce que vous voulez le retraiter.  
3.  Si vous souhaitez recréer l'ordre d'assemblage, cliquez sur le bouton **oui**. Pour annuler la validation sans recréer l'ordre d'assemblage associée, cliquez sur le bouton **Non**.  

Le champ **Contrepassé** de l'en\-tête d'ordre d'assemblage prend la valeur **Oui**. Le report de l'ordre d'assemblage est désormais inversé. Vous pouvez traiter l'ordre d'assemblage dans son intégralité si vous avez choisi de le recréer, ou l'ordre d'assemblage ouvert que vous avez restauré à son état d'origine.  

> [!NOTE]  
>  Pour restaurer les quantités de plusieurs reports partiels dans un ordre d'assemblage, vous devez annuler tous les ordres d'assemblage reportés concernés en suivant les étapes 1 à 3 ci-dessus pour chaque ordre d'assemblage reporté.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Inverser des reports](finance-how-reverse-journal-posting.md)  
[Traiter les retours ou annulations de ventes](sales-how-process-sales-returns-cancellations.md)    
[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  
[Stock](inventory-manage-inventory.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
