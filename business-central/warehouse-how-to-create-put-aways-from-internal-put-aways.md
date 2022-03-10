---
title: Créer un rangement à partir du rangement interne
description: Cette rubrique explique comment prélever et ranger sans document source, à la fois comment créer un prélèvement interne et comment créer un rangement interne.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/24/2021
ms.author: edupont
ms.openlocfilehash: 609564faa1e0d5b1e7c364360315ca71b9ba3d06
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8140095"
---
# <a name="pick-and-put-away-without-a-source-document"></a>Prélever et ranger sans document origine
Une fois les articles rangés et avant qu'ils ne soient prélevés pour répondre aux besoins d'un bon de production ou d'une livraison, ils sont stockés dans l'entrepôt comme faisant partie de l'inventaire disponible.  

Vous pouvez être amené à sortir temporairement des articles des emplacements prélèvement entrepôt, par exemple pour les présenter au cours d'une argumentation. Ces articles appartiennent toujours à la compagnie et font partie de l'inventaire ; par contre, ils ne peuvent pas être prélevés. Ils sont enregistrés dans une zone spécial que vous créez à cet effet ; techniquement, les articles se trouvent dans l'entrepôt, mais physiquement, ils peuvent se trouver dans une salle de conférences ou d'exposition.  

Il peut également arriver que l'unité de fabrication ait inopinément besoin de quelques pièces pour un processus. Vous pouvez prélever des articles pour les emplacements fabrication à l'aide du prélèvement interne. Une fois le processus terminé et la production réalisée, vous reportez la consommation des articles et videz la zone production, ce qui a pour effet de réduire la quantité de l'article dans votre emplacement.  

De même, des articles peuvent être retournés à l'entrepôt pour être rangés. Il est possible que les articles aient été prélevés dans l'inventaire disponible pour répondre à un bon de production, mais sans être utilisés du tout. Pour qu'ils fassent de nouveau partie de l'inventaire disponible, ils doivent faire l'objet d'un rangement dans la zone.  

Les **rangements internes** vous permettent d'effectuer des rangements sans avoir à vous référer à un document origine spécifique. Vous pouvez facilement configurer toutes les informations nécessaires pour créer une instruction entrepôt de rangement.  

> [!NOTE]  
>  Lorsque vous n'utilisez pas de prélèvements ni de rangements internes, vous pouvez effectuer ces ajustements en déplaçant les articles d'une zone vers une autre ou en reportant les ajustements des quantités d'une zone.  
>   
>  Lorsque l'emplacement utilise le prélèvement et le rangement suggérés et, par conséquent, utilise des types de zone, vous ne pouvez pas déplacer manuellement des articles vers ou depuis une zone de type RÉCEPTIONNER, car les articles dans ce type de zone doivent être enregistrés comme étant rangés avant de faire partie de l'inventaire disponible.  

## <a name="to-create-an-internal-pick"></a>Pour créer un prélèvement interne  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvement interne entrepôt**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.
3. Renseignez le champ **N°** le champ **Code d'emplacement** et le champ **Du code de zone** du raccourci **Général**. Le champ **Du code de zone** indique où placer les articles prélevés. Pour des raisons de production, cette zone représente la zone enlogement ou la zone d'atelier ouvert. Pour d’autres applications, vous devez choisir un code de zone d’un type zone qui n’est pas utilisé pour le prélèvement (par exemple, une zone affectation, livraison ou une zone spéciale).  
4.  Sélectionnez un article dans le champ **N° article**, puis renseignez les quantités à prélever.  
5. Choisissez l'action **Créer prélèvement**. Une instruction prélèvement entrepôt est maintenant créée pour un magasinier. Vous pouvez également choisir l’action **Libérer** et créer des prélèvements entrepôt à l’aide de la **Feuille prélèvements**. Pour plus d’informations, voir [Planifier des prélèvements dans des feuilles](warehouse-how-to-plan-picks-in-worksheets.md)

## <a name="to-create-an-internal-put-away"></a>Pour créer un rangement interne  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rangement interne entrepôt**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.
3. Renseignez l’en-tête d’un nouveau rangement interne en y indiquant au moins le **N°** et le **Code d’emplacement**.
4. Renseignez une ligne pour chaque article à déplacer vers l'entrepôt. Vous ne devez renseigner que les champs **N° article** et **Quantité**.

  > [!NOTE]  
  > Lorsque vous sélectionnez le champ **N° article**, la **liste des contenus de la zone** s’ouvre à la place de la **liste des articles**. En effet, vous souhaitez ranger un article qui se trouve dans une zone particulière, le *contenu de la zone* et pas uniquement un article, et vous connaissez déjà la zone dans laquelle l’article doit être prélevé.  <!--If you filled in **From Bin Code** in the header, the bin content will be filtered by value defined in the **From Bin Code**.-->
5. Pour compléter les lignes en y indiquant l’ensemble du contenu de la zone ou le contenu de la zone filtré des zones de l’emplacement, choisissez l’action **Extraire contenu de la zone**.  
6. Choisissez l'action **Créer rangement**. Une instruction rangement entrepôt est maintenant créée pour un employé d'entrepôt. Vous pouvez également choisir l’action **Libérer** et créer des rangements entrepôt à l’aide de la **Feuille rangement**. Pour plus d’informations, voir [Planifier des rangements dans la feuille](warehouse-how-to-plan-put-aways-in-worksheets.md)

## <a name="see-also"></a>Voir aussi  
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
