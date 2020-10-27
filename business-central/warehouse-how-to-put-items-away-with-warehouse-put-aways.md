---
title: Comment ranger des articles avec le rangement entrepôt | Microsoft Docs
description: Lorsque votre emplacement est configuré pour exiger un traitement des rangements entrepôt et un traitement des réceptions entrepôt, vous pouvez utiliser la fonction documents rangement entrepôt pour contrôler le rangement des articles.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: f158499f0c93e1a991b1f092676f653cf067a46e
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3910040"
---
# <a name="put-items-away-with-warehouse-put-aways"></a>Ranger des articles avec le rangement entrepôt
Lorsque votre emplacement est configuré pour exiger un traitement des rangements entrepôt et un traitement des réceptions entrepôt, vous pouvez utiliser la fonction documents rangement entrepôt pour contrôler le rangement des articles.  

Lorsque vous reportez une réception entrepôt, les documents sources, tels que bons de commande, ordres de transfert entrants ou retours vente sont mis à jour, la quantité reçue est reportée dans le grand livre article et les lignes relatives aux articles reçus sont envoyées à la fonction de rangement de l'entrepôt. En cas de rangement et de prélèvement internes, des lignes rangement peuvent également être créées dans le cadre du rangement interne.  

En fonction de la configuration de l'entrepôt, ces lignes sont mises à disposition de la feuille rangement ou utilisées pour créer immédiatement des instructions de rangement. Pour plus d'informations, voir [Planifier des rangements dans la feuille](warehouse-how-to-plan-put-aways-in-worksheets.md).  

Outre les méthodes standard pour créer les rangements entrepôt qui sont décrits dans cette rubrique, vous pouvez créer le rangement à partir de la réception entrepôt reportée associée. Cela est utile si vous avez supprimé des lignes rangement ou si vous utilisez le prélèvement et le rangement suggérés et avez décidé de ne pas utiliser la feuille rangement, car vous pouvez créer ou recréer des instructions de rangement à partir des lignes réception reportées.  

## <a name="to-put-items-away-without-directed-put-away-and-pick"></a>Rangement d'articles en l'absence de prélèvement et de rangement suggérés  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rangements** , puis sélectionnez le lien associé.  
2.  Ouvrez le rangement entrepôt qui est prêt à être traité.  

    Vous pouvez trier les lignes de rangement en fonction de critères divers, tels que par article, numéro de tablette ou date d'échéance et optimiser ainsi le processus de rangement.  
3.  Sur chaque ligne, dans le champ **Quantité à traiter** , entrez la quantité à ranger.  
4.  Une fois le rangement des articles terminé, choisissez l'action **Enregistrer rangement** pour enregistrer la finalisation de l'activité et rendre les articles disponibles pour le prélèvement.  

## <a name="to-put-items-away-with-directed-put-away-and-pick"></a>Rangement d'articles dans le cadre d'un prélèvement et d'un rangement suggérés  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Rangements** , puis sélectionnez le lien associé.
    Si des instructions de rangement ont été créées, un rangement entrepôt apparaît.  
2.  Ouvrez le rangement entrepôt que vous souhaitez utiliser.  
3.  Entrez votre code utilisateur sur le raccourci **Général** lorsque vous commencez à travailler sur un rangement particulier.  
4.  Effectuez les actions de prélèvement et de placement indiquées sur les lignes dans le champ **Type action** .  

    Notez que chaque ligne réception donne lieu à deux lignes au moins dans le rangement entrepôt :  

    -   la première ligne, correspondant au champ **Type action** **Prélèvement** , indique l'endroit où se trouvent les articles dans la zone de réception. Vous ne pouvez pas modifier le champ de la zone de cette ligne.  
    -   La ligne suivante, avec **Emplacement** dans le champ **Type d'action** , indique l'endroit où vous devez placer les articles dans le stockage en entrepôt. Si l'entrepôt a reçu un grand nombre d'articles sur une ligne réception, ils peuvent devoir être rangés dans plusieurs emplacements, pour qu'il y ait une ligne Emplacement pour chaque emplacement.  

        Si les lignes prélèvement et emplacement de chaque ligne réception ne se suivent pas directement et que vous souhaitez qu'elles se suivent, vous pouvez trier ces lignes en sélectionnant **Article** dans le champ **Méthode de tri** du raccourci **Général** .  

        Si l'organisation de l'entrepôt reflète le classement de zone, vous pouvez utiliser la méthode de tri **Classement de zone** pour préparer une opération de rangement en réduisant au minimum vos déplacements dans l'entrepôt.  

5.  Après avoir placé tous les articles dans des zones selon les instructions, choisissez l'action **Enregistrer rangement** .  

Dans les emplacements qui sont configurés pour utiliser le prélèvement et le rangement suggérés, les paramètres suivants sont des conditions préalables à la procédure ci-dessus :  

- Un modèle de rangement est configuré. Pour plus d'informations, voir [Configurer des modèles rangement](warehouse-how-to-set-up-put-away-templates.md).  
- Le poids, le cubage et les exigences particulières de stockage de l'article ou de l'unité de stock sont définis. Pour plus d'informations, voir Poids brut.  
- La capacité, le type de zone et le classement des zones. Pour plus d'informations, voir Classement de zone.  

Le classement de zone est pris en compte lorsque plusieurs zones correspondent aux critères du modèle de rangement. Si les critères du modèle de rangement et le classement de zone coïncident pour plusieurs zones, la zone dont le numéro est le plus élevé est alors sélectionnée.

## <a name="to-create-a-put-away-from-a-posted-receipt"></a>Pour créer un rangement à partir d'une réception reportée  
 Si votre emplacement utilise à la fois le traitement des rangements et des réceptions et que vous avez supprimé des lignes rangement, ou si vous utilisez le prélèvement et le rangement suggérés et avez décidé de ne pas utiliser la feuille rangement, vous pouvez créer ou recréer des instructions de rangement pour les lignes réception reportées.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Réceptions entrepôt reportées** , puis sélectionnez le lien associé.  
2.  Sélectionnez une réception reportée pouvant nécessiter un rangement.  
3.  Sélectionnez l'action **Fiche** .  

    Si le champ **Statut document** est blanc, la réception n'a pas été rangée. Sinon, le champ indique que la réception est partiellement rangée ou entièrement rangée.  

4.  Si la réception est partiellement rangée ou n'est pas rangée du tout, choisissez l'action **Créer rangement** .  
5.  Renseignez la page de demande de traitement en lot pour créer le rangement comme vous le souhaitez, puis sélectionnez le bouton **OK** .   

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
