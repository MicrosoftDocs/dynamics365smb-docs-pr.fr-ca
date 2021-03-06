---
title: "Procédure : configurer des emplacements pour qu'ils utilisent des zones | Microsoft Docs"
description: Les emplacements représentent la structure d'entrepôt de base et sont utilisés pour faire des propositions relatives à l'emplacement des articles. Lorsque vous avez créé vos zones, vous pouvez définir précisément le contenu que vous souhaitez placer dans chacune d'entre elles, ou la zone peut être utilisée en tant que zone dynamique sans contenu spécifié.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: e04ec3be3385b86cfdfb42bffadcdd9730244efc
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5771636"
---
# <a name="set-up-locations-to-use-bins"></a>Configurer des emplacements de sorte qu'ils utilisent des zones
Les emplacements représentent la structure d'entrepôt de base et sont utilisés pour faire des propositions relatives à l'emplacement des articles. Lorsque vous avez créé vos zones, vous pouvez définir précisément le contenu que vous souhaitez placer dans chacune d'entre elles, ou la zone peut être utilisée en tant que zone dynamique sans contenu spécifié.  

Pour utiliser la fonctionnalité liée au magasin, vous devez d'abord l'activer dans la fiche **magasin**. Ensuite, vous définissez la circulation des articles dans l'emplacement en spécifiant les codes de zones dans les champs de configuration qui représentent les différents flux.  

> [!NOTE]  
>  Avant de pouvoir spécifier les codes de zones sur la fiche emplacement, il convient de les créer. Pour plus d'informations, voir [Créer zones](warehouse-how-to-create-individual-bins.md).  

## <a name="to-set-up-a-location-to-use-bins"></a>Pour configurer un emplacement de sorte qu'il utilise des zones  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacements**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'emplacement dans lequel vous souhaitez utiliser des zones.  
3.  Choisissez l'action **Modifier**.  
4.  Sur le raccourci **Entrepôt**, cochez la case **Zone obligatoire**.  
5.  Si vous n'avez pas recours à un prélèvement et à un rangement suggérés dans l'emplacement, renseignez le champ **Sélection zone par déf.** en y indiquant la méthode d'attribution d'une zone par défaut à un article que le système doit utiliser.  
6.  Ouvrez la fiche de l'emplacement pour lequel vous souhaitez configurer des zones.
7.  Sur le raccourci **Zones**, sélectionnez les zones que vous voulez utiliser par défaut pour les réceptions, les livraisons, les enlogements et les désenlogements, ainsi que pour les zones d'atelier ouvert.  
8.  Les codes emplacement que vous indiquez ici s'affichent automatiquement dans les en-têtes et sur les lignes de différents documents entrepôt. Les emplacements par défaut définissent tous les placements de début ou de fin des articles dans l'entrepôt.  
9.  En cas d'utilisation d'un prélèvement et d'un rangement suggérés, sélectionnez une zone pour les ajustements entrepôt. Le code emplacement dans le champ **Code empl. ajustement** définit l'emplacement virtuel dans lequel enregistrer les différences de stock lorsque vous enregistrez soit les différences observées dans la feuille article entrepôt, soit les différences calculées lorsque vous enregistrez un inventaire entrepôt.  
10. Renseignez les champs du raccourci **Config. emplacement** s'ils sont appropriés à votre entrepôt. Les champs les plus importants sont les suivants : **Politique capacité zone**, **Autoriser déconditionnement** et **Code modèle rangement**.  
11. Sur les champs **Entrepôt**, renseignez les champs **Délai désenlogement**, **Délai enlogement** et **Code calendrier principal**. Pour plus d'informations, voir [Configurer des calendriers principaux](across-how-to-assign-base-calendars.md).

## <a name="filling-the-consumption-bin"></a>Renseignement de la zone consommation
Ce graphique indique comment le champ **Code de zone** sur les lignes composante bon de production est renseigné en fonction de la configuration de votre emplacement.

![Organigramme Flux de zone](media/binflow.png "BinFlow")  

## <a name="see-also"></a>Voir aussi
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]