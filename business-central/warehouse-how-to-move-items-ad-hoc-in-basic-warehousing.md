---
title: Déplacer des articles non planifiés dans les configurations de stockage de base
description: Cet article explique les mouvements internes non planifiés entre zones sans demande d’un document source.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/16/2022
ms.custom: bap-template
ms.search.form: '393, 7382'
---
# <a name="move-items-internally-in-basic-warehouse-configurations"></a>Déplacer des articles en interne dans les configurations de stockage de base

Vous souhaiterez peut-être déplacer des articles entre zones sans demande d’un document source. Par exemple, dans le cadre des activités suivantes :

* Réorganiser votre entrepôt.
* Apporter des articles à une zone d’inspection.
* Déplacer des articles supplémentaires vers et depuis une zone de production. 

Le mode de prélèvement des articles dépend de la configuration de l’entrepôt en tant qu’emplacement. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Dans les configurations d’entrepôt où le bouton à bascule de configuration **Zone obligatoire** est activé, mais pas **Prélèvement et rangement dirigés**, vous pouvez enregistrer des mouvements non planifiés sur les pages suivantes :  

* Sur la page **Mouvement interne**.
* Sur la page **Journal reclassement article**.  

## <a name="internal-movements"></a>Mouvements internes

La page **Mouvements internes** vous permet de spécifier des lignes Prendre et Placer lorsqu’il n’y a pas de demande d’un document origine. La page Mouvement interne est comme une feuille de travail pour organiser les choses. Vous ne pouvez pas traiter le mouvement réel directement à partir de celle-ci. Lorsqu’une ligne est remplie, utilisez l’action **Créer un mouvement d’inventaire** pour envoyer la ligne à la page **Mouvement d’inventaire**, où vous traitez et enregistrez le mouvement.

### <a name="to-move-items-as-an-internal-movement"></a>Pour déplacer des articles en tant que mouvement interne

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Mouvements internes**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**. Assurez-vous que le champ **N°** du raccourci **Général** est rempli.
3. Dans le champ **Code magasin**, entrez le magasin où le mouvement a lieu.  

    Si l’emplacement est votre emplacement par défaut en tant qu'employé d'entrepôt, le code emplacement est inséré automatiquement.  
4. Dans le champ **Code de zone de destination**, entrez le code de la zone vers laquelle vous souhaitez déplacer les articles.

    Par exemple, en production, la zone peut être la zone d'atelier ouvert définie sur la fiche emplacement ou dans l’atelier.  
5. Dans le champ **Date d’échéance**, entrez la date à laquelle terminer le mouvement.  
6. Sur chaque ligne, renseignez les champs selon vos besoins. Les documents de mouvement interne comportent une ligne par mouvement. La ligne contient à la fois les actions prendre et placer.
7. Choisissez le champ **N° article** pour ouvrir la page **Liste des contenus zone**. Sélectionnez l’article à déplacer en fonction de sa disponibilité dans les zones. Vous pouvez également choisir l’action **Extraire contenu zone** pour remplir les lignes de mouvements internes en fonction de vos filtres.  

    Après avoir sélectionné l’article, le champ **Code de zone de provenance** est automatiquement renseigné en fonction du contenu de la zone sélectionné. Vous pouvez choisir n’importe quelle zone où l’article est disponible. Les champs **N° article** et **Code de zone de provenance** sont liés. La modification de la valeur d’un champ peut modifier la valeur de l’autre.  

    Le champ **Code de zone de destination** est rempli avec la valeur que vous avez saisie dans l’en-tête. Vous pouvez la changer sur la ligne pour toute autre code de zone qui n’est pas bloqué ou dédié à des fins particulières. Learn more at [Le champ Réservé](warehouse-how-to-create-individual-bins.md#the-dedicated-field).  

8. Après avoir défini les zones depuis ou vers lesquelles que vous souhaitez déplacer les articles, entrez la quantité à déplacer dans le champ **Quantité**.  

    > [!NOTE]  
    > La quantité doit être disponible dans la zone spécifiée dans le champ **Code de zone de provenance**.  

9. Lorsque vous êtes prêt à traiter le mouvement, choisissez l’action **Créer mouvement d’inventaire**.  

    > [!NOTE]  
    >  Après avoir créé le mouvement, les lignes de mouvement internes sont supprimées.  

Exécutez le reste du mouvement non planifié sur la page **Mouvement d’inventaire** de la même manière que pour un mouvement basé sur des documents source.

### <a name="to-record-the-inventory-movement"></a>Pour enregistrer le mouvement d’inventaire

1. Sur la page **Mouvement d’inventaire**, ouvrez le document pour lequel enregistrer le mouvement.  
2. Dans le champ **Code de zone** sur les lignes mouvement, la zone à partir de laquelle les articles doivent être prélevés est celui où les articles sont disponibles. Si nécessaire, vous pouvez modifier la zone.
3. Exécutez le mouvement et saisissez les informations pour la quantité déplacée dans le champ **Quantité à traiter**. La valeur sur les lignes prélèvement et emplacement doit être la même. Sinon, vous ne pouvez pas enregistrer le mouvement.

    Si vous devez prélever les articles d’une ligne à partir de plusieurs zones, par exemple parce que la quantité totale n’est pas dans la zone, utilisez l’action **Fractionner la ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.  
4. Sélectionnez l’action **Enregistrer mouvement d’inventaire**.  

Voici ce qui se passe pendant le processus de report :

* Les écritures emplacement indiquent que la quantité est transférée des zones « prendre » vers les zones « placer ».

## <a name="to-move-items-with-the-item-reclassification-journal"></a>Pour déplacer des articles à l'aide du journal reclassement article

Au lieu d’utiliser des documents de mouvement, vous pouvez enregistrer des mouvements en reclassant les codes de zone sur les articles. Pour en savoir plus, voir [Comptabiliser, ajuster et reclasser l’inventaire avec les journaux](inventory-how-count-adjust-reclassify.md).

> [!NOTE]  
> Les mouvements reportés avec des journaux de reclassement ne rendent pas les documents de mouvement prêts pour le déplacement.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal reclassement article**, puis choisissez le lien associé.  
2. Sur chaque ligne journal, définissez les zones depuis et vers lesquelles déplacer les articles en renseignant les champs **Code de zone** et **Nouveau code de zone**.  

    1. Pour déplacer tout le contenu d'une zone vers une autre, choisissez l'action **Extraire contenu de la zone**.  
    2. Utilisez les filtres pour trouver la zone qui contient les éléments que vous souhaitez déplacer, puis choisissez **OK**. Les lignes journal sont renseignées avec le contenu de la zone.  
3. Renseignez les champs restants de chaque ligne journal.
4. Reportez le journal reclassement.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="see-also"></a>Voir aussi .

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
