---
title: Configurer une fiche emplacement et définir des acheminements de transfert (contient une vidéo)
description: Si vous achetez, stockez ou commercialisez des articles à plusieurs endroits, vous pouvez configurer chaque lieu en tant qu’emplacement.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.search.forms: 5703, 15
ms.date: 07/05/2022
ms.author: bholtorf
ms.openlocfilehash: 882c7c0506439aba55d5b1c2d0cc23bd79db9d6e
ms.sourcegitcommit: 8ad79e0ec6e625796af298f756a142624f514cf3
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/30/2022
ms.locfileid: "9605817"
---
# <a name="set-up-locations"></a>Configurer des emplacements

Les emplacements sont des endroits tels que des entrepôts où vous achetez, stockez ou vendez des articles. [!INCLUDE [prod_short](includes/prod_short.md)] utilise des emplacements pour aider à suivre l'inventaire dans les processus d’entrepôt à la fois simples et complexes.

Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements. Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).
<br><br>  
  
> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## <a name="location-cards"></a>Fiches emplacement

Vous spécifiez des informations sur un emplacement, par exemple un entrepôt ou un centre de distribution sur la page **Fiche emplacement**. Affectez un nom et un code représentatifs à chaque emplacement. Il vous suffit ensuite de saisir le code d'emplacement dans d’autres parties du programme lorsque vous souhaitez enregistrer les transactions d’un emplacement en particulier.  

Vous pouvez entrer des informations sur les zones et les règles entrepôt pour chaque emplacement. En fonction de vos stratégies d’entrepôt, vous pouvez utiliser les options sur le raccourci **Zones** pour spécifier lesquelles utiliser par défaut pour les transactions. Si vous utilisez les prélèvements et rangements suggérés, vous pouvez utiliser la plupart des options du raccourci **Politiques de zones** pour définir la façon dont vous souhaitez utiliser les différentes fonctions d’entrepôt avancées.  

Certains champs d’option dépendent des paramètres dans la page **Fiche emplacement** pour limiter les combinaisons de configuration non prises en charge.  

Choisissez les actions **Zone** ou **Zones** pour visualiser des informations sur les zones qui sont définies pour l'emplacement.

### <a name="to-set-up-a-location"></a>Pour configurer un emplacement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") , entrez **Emplacements**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.

> [!NOTE]  
> De nombreux champs de la page Fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement. Ces champs ne sont pas pertinents pour les compagnies qui n’ont pas besoin des fonctionnalités d’entrepôt complexes. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Vous pouvez modifier la configuration d’un emplacement tant qu’il n’a pas d’écritures article.  

Si vous avez plusieurs emplacements, vous pouvez définir des acheminements transfert entre les emplacements. Pour plus d’informations, reportez-vous à [Créer des acheminement transfert ](inventory-how-setup-locations.md#to-create-a-transfer-route).

### <a name="to-create-a-transfer-route"></a>Pour créer un acheminement transfert

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Acheminements de transfert**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
4. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez à présent transférer des articles en inventaire entre deux emplacements. Pour plus d'informations, voir [Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).    

## <a name="bins"></a>Zones

Les zones représentent la structure de base de l’entrepôt et peuvent suggérer où placer les articles. Vos zones peuvent avoir du contenu ou être flottantes sans contenu spécifique. 

Pour utiliser la fonctionnalité de zone liée à l’emplacement, vous devez d’abord activer la fonctionnalité sur la page **Fiche emplacement** sur le raccourci **Entrepôt** en activant le bouton à bascule **Zone obligatoire**. Vous pouvez concevoir le flux d’articles à l’emplacement en spécifiant des codes de zone dans les champs des processus d’entrepôt sur les raccourcis **Zones** et **Stratégies de zone**.

> [!NOTE]
> Avant de pouvoir spécifier les codes zone sur un emplacement, vous devez les créer. Pour plus d'informations, voir [Créer des zones](warehouse-how-to-create-individual-bins.md) et [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).  

## <a name="zones"></a>Zones

Si vous souhaitez structurer vos zones en zones, vous pouvez le faire dans la page **Zones**. Lorsque vous affectez une zone à des zones, [!INCLUDE [prod_short](includes/prod_short.md)] copie les informations de la zone vers les zones. Vous pouvez également choisir de configurer une zone et d’utiliser des zones seules pour organiser votre entrepôt. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

## <a name="default-dimensions-for-locations"></a>Dimensions par défaut pour les emplacements

Pour définir les dimensions par défaut pour un emplacement, allez sur la page **Fiche emplacement** et choisissez **Dimensions**. Par la suite, les dimensions par défaut de l’emplacement sont attribuées aux documents lorsque vous choisissez l’emplacement sur une ligne. Au besoin, vous pouvez supprimer ou modifier les dimensions sur les lignes. Dans le champ **Contrôle report**, pouvez exiger que les personnes spécifient des dimensions pour des emplacements spécifiques avant de pouvoir reporter une écriture. Si vous souhaitez que les utilisateurs puissent choisir uniquement certaines valeurs de dimension, vous pouvez spécifier celles-ci dans le champ **Filtre valeurs autorisées**. Vous pouvez également inclure des valeurs de dimension d’emplacement sur la page **Affect. analytique prioritaire** et **Croisements analytiques** pour les combinaisons de règles de priorité et de dimension.

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/trade-set-up-dynamics-365-business-central/)

## <a name="see-also"></a>Voir aussi .

[Gestion du stock](inventory-manage-inventory.md)  
[Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)  
[Créer zones](warehouse-how-to-create-individual-bins.md)  
[Configurer des types de zone](warehouse-how-to-set-up-bin-types.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
