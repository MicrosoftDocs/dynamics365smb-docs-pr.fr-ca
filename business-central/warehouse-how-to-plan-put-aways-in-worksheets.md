---
title: Comment planifier des rangements dans la feuille
description: Configurez votre entrepôt de sorte que les lignes de réception soient disponibles dans la feuille de calcul de rangement lorsque vous souhaitez planifier les instructions de rangement pour les réceptions.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 06/25/2021
ms.author: edupont
ms.openlocfilehash: 109ebfef1650c365cb383aac56cf51ab9ee8231b
ms.sourcegitcommit: 8a12074b170a14d98ab7ffdad77d66aed64e5783
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2022
ms.locfileid: "8518557"
---
# <a name="plan-put-aways-in-worksheets"></a>Planifier des rangements dans la feuille
Lorsque l'emplacement nécessite un traitement à la fois de rangement et de réception et que vous souhaitez planifier des instructions de rangement pour plusieurs réceptions, vous pouvez utiliser la feuille rangement (dans ce cas, les employés n'ont pas à suivre les instructions créées par l'application pour différentes réceptions reportées).  

Pour configurer votre entrepôt afin que les lignes réception soient disponibles dans la feuille rangement dès leur report, sélectionnez le champ **Utiliser feuille rangement** sur le raccourci **Entrepôt** de la fiche emplacement. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

Si vous ne sélectionnez pas ce champ, l'application crée automatiquement des instructions rangement pour les réceptions dès leur report.  

> [!NOTE]  
>  Quel que soit l'état du champ **Utiliser feuille rangement** de la fiche emplacement, vous pouvez toujours obtenir des lignes instruction rangement, c'est à dire des lignes réception reportées, dans la feuille rangement en procédant comme suit :  
>   
>  1.  Sur la page **Rangement entrepôt**, appuyez sur Ctrl+D pour supprimer l'instruction rangement, ou sélectionnez les lignes à traiter dans la feuille et supprimez-les.  
> 2.  Poursuivez l'opération dans tous les rangements concernés jusqu'à ce que vous ayez supprimé les lignes que vous souhaitez utiliser dans la feuille. Sélectionnez maintenant **Rangement** et continuez la planification.  

## <a name="to-plan-instructions-in-the-put-away-worksheet"></a>Pour planifier des instructions dans la feuille rangement  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille rangement**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Extraire documents entrepôt**. La page **Sélection rangement** s'ouvre.  

    Vous pouvez visualiser toutes les réceptions reportées et tous les rangements internes enregistrés qui ont été envoyés vers la fonction rangement, y compris ceux pour lesquels des instructions rangement ont déjà été créées. Les documents dont les lignes rangement ont été entièrement rangées et enregistrées n'apparaissent pas dans cette liste.  

3. Sélectionnez les documents que vous souhaitez utiliser dans la feuille. Vous pouvez utiliser simultanément des lignes de plusieurs documents.  

    > [!NOTE]  
    >  Si vous essayez de sélectionner un document réception ou rangement interne dont toutes les lignes disposent déjà d'instructions, l'application vous indique qu'il n'y a rien à gérer.  

4. Renseignez le champ **Méthode de tri** pour trier les lignes à votre convenance.  

    > [!NOTE]  
    >  Le mode de tri des lignes de la feuille ne conduit pas automatiquement à l'instruction rangement, mais les mêmes possibilités de tri existent avec le classement de zone. L'ordre des lignes planifié dans la feuille est donc facilement recréé lorsque vous créez ou triez les instructions rangement.  

5.  Renseignez le champ **Quantité à traiter**. Choisissez l'action **Remplir qté à traiter**, ou renseignez les champs manuellement.  
6.  Si nécessaire, modifiez les lignes manuellement. Vous pouvez supprimer des lignes (par exemple, si certains articles doivent être rangés dans une zone éloignée des zones des autres articles).  

    > [!NOTE]  
    >  s: Les lignes supprimées sont uniquement supprimées dans cette feuille ; elles ne sont pas supprimées de la liste de sélection des rangements.  

7.  Choisissez l'action **Créer rangement**. La page **Créer document** s'ouvre, où vous pouvez ajouter des informations supplémentaires au rangement que vous créez, telles que :  

    -   Vous pouvez affecter le rangement à un employé donné.  
    -   Vous pouvez trier les lignes instruction rangement comme dans la feuille ou par classement de zone. Lorsque vous effectuez un tri sur la base du classement de zone, les lignes Prélever apparaissent d'abord, étant donné que la plupart des zones réception sont classées au niveau 0, et les lignes zone apparaissent ensuite, en commençant par les zones les moins bien classées. Si vous avez structuré votre entrepôt de façon à ce que les zones de même classement soient les unes à côté des autres et si vous utilisez cette méthode de tri, les magasiniers éviteront un certain nombre d'étapes.  
    -   Vous pouvez choisir de ne pas afficher les lignes intermédiaires créées lorsque l'application divise une unité de mesure en unités de mesure plus petites, en sélectionnant le champ **Configurer filtre déconditionnement**. Pour en savoir plus, voir [Activer la rupture de charge automatique avec prélèvement et rangement dirigé](warehouse-enable-automatic-breaking-bulk-with-directed-put-away-and-pick.md).  
    -   Vous pouvez faire en sorte que le champ **Quantité à traiter** des instructions rangement ne soit pas renseigné automatiquement.  
    -   Vous pouvez imprimer immédiatement le document.  

8.  Sélectionnez le bouton **OK** pour que l'application crée le rangement en fonction de vos exigences.  

## <a name="see-also"></a>Voir aussi  
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]