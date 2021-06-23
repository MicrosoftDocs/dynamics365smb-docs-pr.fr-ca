---
title: Configurer une fiche emplacement et définir des acheminements transfert
description: Vous créez une fiche emplacement pour chaque emplacement où vous stockez des articles d'inventaire, par exemple, un entrepôt ou un centre de distribution, et configurez des acheminements pour le transfert d'articles entre emplacements.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: warehouse, distribution center
ms.date: 06/01/2021
ms.author: edupont
ms.openlocfilehash: 0319f0c64dd46610aa82705257091bd9478ac14f
ms.sourcegitcommit: 1aab52477956bf1aa7376fc7fb984644bc398c61
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 06/04/2021
ms.locfileid: "6184334"
---
# <a name="set-up-locations"></a>Configurer des emplacements

Si vous achetez, enregistrez, ou vendez des articles à plusieurs emplacements ou entrepôts, vous devez configurer chaque emplacement avec une fiche emplacement et définir des acheminements transfert. [!INCLUDE [prod_short](includes/prod_short.md)] utilise des emplacements pour aider à suivre l'inventaire dans les cas les plus simples et dans les processus d’entrepôt plus complexes.

Vous pouvez ensuite créer des lignes document pour un emplacement spécifique, voir la disponibilité par emplacement, et transférer l'inventaire entre emplacements. Pour plus d'informations, reportez-vous à [Gestion du stock](inventory-manage-inventory.md).
<br><br>  
  
> [!Video https://www.microsoft.com/videoplayer/embed/RE4aQvq?rel=0]

## <a name="location-cards"></a>Fiches emplacement

La fiche emplacement spécifie des informations sur un emplacement, par exemple un entrepôt ou un centre de distribution. Affectez un nom et un code représentatifs à chaque emplacement. Il vous suffit ensuite de saisir le code d'emplacement dans d’autres parties du programme lorsque vous souhaitez enregistrer les transactions d’un emplacement en particulier.  

Vous pouvez entrer des informations sur les zones et les règles entrepôt pour chaque emplacement. En fonction des règles entrepôt sélectionnées, vous pouvez utiliser les options du raccourci **Zones** pour définir les zones utilisées par défaut lorsque vous effectuez des transactions. Si vous utilisez les prélèvement et rangement suggérés, vous pouvez utiliser la plupart des options du raccourci **Politiques de zones** pour définir la façon dont vous souhaitez utiliser les différentes fonctions d’entrepôt avancées.  

Certains champs d’option sont grisés et désactivés par d’autres paramètres dans la page **Fiche emplacement** pour limiter les combinaisons de configuration non prises en charge.  

Choisissez les actions **Zones** ou **Zones** pour visualiser des informations sur les zones et les zones qui peuvent être définies pour l'emplacement.

### <a name="to-create-a-location-card"></a>Pour créer une fiche emplacement

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacements**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**.
3. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Répétez les étapes 2 et 3 pour chaque emplacement dans lequel vous souhaitez conserver un inventaire.

> [!NOTE]  
> De nombreux champs de la fiche emplacement se rapportent à la gestion des articles dans les processus enlogement et désenlogement. Les champs ne sont pas pertinents pour les compagnies qui n’ont pas besoin des fonctionnalités d’entrepôt plus complexes. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Vous pouvez modifier la configuration d’un emplacement ultérieurement, mais vous ne pouvez pas modifier la configuration des emplacements qui ont des écritures article.  

Ensuite, si vous avez plusieurs emplacements, vous pouvez définir des acheminements transfert entre les emplacements.  

### <a name="to-create-a-transfer-route"></a>Pour créer un acheminement transfert

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Acheminements transfert**, puis sélectionnez le lien associé.
2. Sinon, à partir de n'importe quelle page **Fiche emplacement**, cliquez sur **Acheminements transfert**.
3. Sélectionnez l'action **Nouveau**.
4. Sur la page **Fiche emplacement**, renseignez les champs comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

Vous pouvez à présent transférer des articles en inventaire entre deux emplacements. Pour plus d'informations, voir [Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md).    

## <a name="bins"></a>Zones

Les emplacements représentent la structure d'entrepôt de base et sont utilisés pour faire des propositions relatives à l'emplacement des articles. Lorsque vous avez créé vos zones, vous pouvez définir précisément le contenu que vous souhaitez placer dans chacune d'elles, ou bien la zone peut être utilisée en tant que zone dynamique sans contenu spécifié. Les zones sont principalement utilisées dans les opérations d’entrepôt de base et avancées. Si vous gérez l'inventaire dans une configuration plus simple, vous n’avez probablement pas besoin de zones.

Pour utiliser la fonctionnalité de zone liée à un emplacement, vous devez d’abord activer la fonctionnalité sur la fiche **Emplacement** en sélectionnant le champ **Zones obligatoires** sur le raccourci **Entrepôt**. Ensuite, vous définissez la circulation des articles dans l'emplacement en spécifiant les codes de zones dans les champs de configuration qui représentent les différents flux.

> [!NOTE]
> Avant de pouvoir spécifier les codes de zones sur la fiche emplacement, il convient de les créer.

Pour plus d'informations, voir [Créer des zones](warehouse-how-to-create-individual-bins.md) et [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).  

## <a name="zones"></a>Zones

Si vous souhaitez structurer vos zones en zones, vous pouvez le faire dans la page **Zones**.

[!INCLUDE [prod_short](includes/prod_short.md)] copie les champs que vous définissez pour une zone donnée dans les zones qui s’y trouvent. Cela signifie que vous pouvez affecter une zone à une zone ou à un modèle de zone (filtre de création de zone) et que plusieurs autres champs sont ensuite renseignés automatiquement.

Toutefois, vous pouvez choisir de configurer une seule zone et d’organiser votre entrepôt uniquement en fonction des zones. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

## <a name="see-also"></a>Voir aussi

[Gestion du stock](inventory-manage-inventory.md)  
[Transfert de l'inventaire entre des emplacements](inventory-how-transfer-between-locations.md)  
[Créer zones](warehouse-how-to-create-individual-bins.md)  
[Configurer des types de zone](warehouse-how-to-set-up-bin-types.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  
[Fonctionnalités marché](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]