---
title: Comment déplacer des articles ad hoc dans les configurations de stockage de base | Microsoft Docs
description: Vous pouvez être amené à déplacer des articles d'une zone interne vers une autre (et non vers des zones de réception ou de livraison) sans demande spécifique issue d'un document source. Vous pouvez exécuter ces mouvements ad hoc, par exemple, pour réorganiser l'entrepôt, pour acheminer des articles vers une zone d'inspection, ou pour déplacer des articles supplémentaires vers et depuis une zone de production sans qu'il existe une relation système avec le document origine du bon de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 926d7076ba8b9ae78f718afcab434d012d885233
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4756227"
---
# <a name="move-items-ad-hoc-in-basic-warehouse-configurations"></a>Déplacer des articles ad hoc dans les configurations de stockage de base
Vous pouvez être amené à déplacer des articles d'une zone interne vers une autre (et non vers des zones de réception ou de livraison) sans demande spécifique issue d'un document source. Vous pouvez exécuter ces mouvements ad hoc, par exemple, pour réorganiser l'entrepôt, pour acheminer des articles vers une zone d'inspection, ou pour déplacer des articles supplémentaires vers et depuis une zone de production sans qu'il existe une relation système avec le document origine du bon de production.  

Dans les configurations d'entrepôt de base, où les emplacements utilisent le champ de configuration **Zone obligatoire** et éventuellement les champs **Prélèvement requis** et **Rangement requis**, vous pouvez enregistrer des mouvements ad hoc sans les documents sources en procédant comme suit :  

- À l'aide de la page **Mouvement interne**.  
- Avec la page **Journal reclassement article**.  

> [!NOTE]  
>  Dans les configurations d'entrepôt avancées, où les emplacements utilisent le champ de configuration **Prélèv. et rangement suggérés**, vous utilisez la page **Feuille mouvement** ou les pages **Prélèvement interne entrepôt** ou **Rangement interne entrepôt** pour déplacer des articles ad hoc entre différentes zones.  

## <a name="to-move-items-as-an-internal-movement"></a>Pour déplacer des articles en tant que mouvement interne  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Mouvement interne**, puis choisissez le lien associé.  
2.  Sur le raccourci **Général**, renseignez le champ **N°**. en le laissant tel quel ou en cliquant sur le bouton **AssistEdit** pour effectuer une sélection parmi la souche de numéros.  
3.  Dans le champ **Code magasin**, entrez le magasin où le mouvement a lieu.  

    Si l'emplacement est configuré comme votre emplacement par défaut en tant que magasinier, le code d'emplacement est inséré automatiquement.  
4.  Dans le champ **Vers code emplacement**, entrez le code de l'emplacement vers lequel vous souhaitez déplacer l'article. Pour la production, il peut s’agir du code de zone d'atelier ouvert, par exemple, tel qu’il est défini sur la fiche emplacement ou dans l'atelier.  
5.  Dans le champ **Date d'échéance**, entrez la date à laquelle le mouvement doit être terminé.  
6.  Sur le raccourci **Lignes**, cliquez sur le champ **N° article** pour ouvrir la page **Liste contenus de la zone**, puis sélectionnez l’article à déplacer sur la base de sa disponibilité dans les zones. Vous pouvez également choisir l'action **Extraire contenu de la zone** pour renseigner les lignes mouvement internes sur la base des filtres. Pour plus d'informations, voir l'info-bulles pour l'action **Extraire contenu de la zone**.   

    Lorsque vous avez sélectionné l'article, le champ **Du code emplacement** est renseigné automatiquement en fonction du contenu d'emplacement sélectionné, mais vous pouvez le remplacer par un autre emplacement dans lequel l'article est disponible.  

    > [!NOTE]  
    >  Étant donné que le champ **N° article** et le champ **Du code de zone** sont liés, leur valeur peut changer de manière interdépendante lorsque vous modifiez l'un ou l'autre de ces champs.  

    Le champ **Vers code emplacement** est renseigné avec la valeur que vous avez entrée dans l'en-tête, mais vous pouvez la remplacer sur la ligne par n'importe quel autre code emplacement qui n'est pas bloqué ou dédié à des cas particuliers. Pour plus d'informations sur la création d'emplacements dédiés, reportez\-vous à Dédié.  
7.  Lorsque vous avez défini les emplacements depuis/vers lesquels que vous souhaitez déplacer l'article, entrez la quantité à déplacer dans le champ **Quantité**.  

    > [!NOTE]  
    >  La quantité doit être disponible dans le champ Du code de zone.  

8.  Lorsque vous êtes prêt à traiter le mouvement interne, choisissez l'action **Créer mouvement d'inventaire**.  

    > [!NOTE]  
    >  Lorsque vous avez créé le mouvement d'inventaire, les lignes mouvement interne sont supprimées.  

    Vous effectuez le reste du mouvement ad hoc sur la page **Mouvement d'inventaire** de la même manière que pour un mouvement basé sur des documents origine. Pour plus d'informations, voir par exemple [Déplacer les composantes vers une zone opérations dans les configurations de stockage de base](warehouse-how-to-move-components-to-an-operation-area-in-basic-warehousing.md)  

## <a name="to-move-items-with-the-item-reclassification-journal"></a>Pour déplacer des articles à l'aide du journal reclassement article
Au lieu d'utiliser des documents mouvement entrepôt, vous pouvez enregistrer le déplacement d'articles en reclassant leurs codes de zone. Pour plus d'informations, voir [Inventaire, ajustement et reclassement de l'inventaire avec les journaux](inventory-how-count-adjust-reclassify.md).   
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal reclassement article**, puis sélectionnez le lien associé.  
2.  Sur chaque ligne feuille, définissez les emplacements depuis et vers lesquels vous souhaitez déplacer des articles en renseignant les champs **Code emplacement** et **Nouveau code emplacement**.  

    1.  Pour déplacer tout le contenu d'une zone vers une autre, choisissez l'action **Extraire contenu de la zone**.  
    2.  Renseignez les filtres pour rechercher l'emplacement dont vous souhaitez déplacer le contenu, puis sélectionnez le bouton **OK**. Les lignes journal sont renseignées avec le contenu de la zone.  
3.  Renseignez les champs restants de chaque ligne journal.   
4.  Reportez le journal reclassement.  

    > [!NOTE]  
    >  Contrairement aux documents mouvement, un mouvement reporté avec le journal reclassement ne crée pas de demande entrepôt pour effectuer la tâche physique.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
