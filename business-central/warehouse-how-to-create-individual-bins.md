---
title: Créer des zones
description: 'Générez des groupes de zones similaires dans la feuille de calcul prévue à cet effet, créez des zones individuellement sur la carte d’emplacement ou automatiquement sur la feuille de calcul de création des zones.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: '7368, 7369, 7370, 7371, 7372, 7373'
ms.date: 12/13/2023
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="create-bins"></a>Créer des zones

La méthode la plus efficace pour créer les zones de votre entrepôt consiste à générer des groupes de zones identiques dans la feuille de création de zones, mais vous pouvez également créer vos zones séparément à partir de la fiche emplacement. Vous pouvez également utiliser une fonction de la page **Feuille création zone** pour créer des zones automatiquement.  

## <a name="to-create-a-bin-from-the-location-card"></a>Pour créer une zone à partir de la fiche emplacement

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Emplacements**, puis choisissez le lien associé.  
2.  Sélectionnez l'emplacement à partir duquel vous souhaitez créer une zone, puis choisissez l'action **Zones**.  
3. Sélectionnez l'action **Nouveau**.
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### <a name="the-dedicated-field"></a>Le champ Réservé

Le champ **Réservé** sur la page **Zones** indique que les quantités de la zone sont protégées des prélèvements d’autres demandes. Toutefois, les quantités des zones réservées peuvent encore être réservées. Par conséquent, les quantités figurant dans des zones réservées sont incluses dans le champ **Quantité totale disponible** de la page **Réservation**.

La réservation d'une zone est, dans l'entreposage de base, une fonctionnalité similaire à l'utilisation des types de zone, uniquement disponible dans l'entreposage avancé. Pour plus d'informations, voir [Configurer des types de zone](warehouse-how-to-set-up-bin-types.md).

### <a name="example"></a>Exemple :

Un atelier est configuré avec un code de zone dans le champ **Code de zone avant production**. Les lignes composante bon de production présentant ce code de zone nécessitent que les composantes consommées en aval soient stockées à cet emplacement. Toutefois, jusqu’à la consommation des composantes de cette zone, d’autres demandes de composante peuvent y effectuer un prélèvement ou une consommation, car elles sont encore considérées comme du contenu zone disponible. Pour vous assurer que le contenu de la zone est uniquement disponible pour la demande de composantes qui utilise cette zone avant production, vous devez sélectionner le champ **Réservé** sur la ligne de ce code de zone.

> [!Caution]
> Des articles dans des zones réservées ne sont pas protégés lorsqu'ils sont prélevés et consommés comme composantes d'assemblage ou de production sur la page **Prélèvement inventaire**. Pour plus d'informations, consultez [Prélever pour la fabrication ou l'assemblage dans les configurations de stockage de base](warehouse-how-to-pick-for-production.md).

## <a name="to-create-bins-individually-in-the-bin-creation-worksheet"></a>Pour créer séparément des zones dans la feuille de création de zones

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille création zone**, et choisissez le lien associé.  
2.  Sur chaque ligne, renseignez les champs requis pour nommer et caractériser les zones que vous créez.  
3.  Choisissez l'action **Créer zones**.  

## <a name="to-make-bins-automatically-in-the-bin-creation-worksheet"></a>Pour créer des zones automatiquement dans la feuille de création de zones

Avant de commencer à créer automatiquement des zones, déterminez les types de zones essentielles à vos opérations, ainsi que la circulation des articles la plus pratique dans la structure physique de votre entrepôt.  

> [!NOTE]  
> Dès que vous utilisez une zone, vous ne pouvez pas la supprimer sauf si elle est vide. En revanche, si vous souhaitez utiliser un autre système d'attribution de nom de zone, vous pouvez utiliser le journal reclassement pour déplacer effectivement vos articles vers un nouveau système de zones. Cependant, ce processus est manuel et prend du temps ; il est donc préférable de configurer correctement vos emplacements dès le début.  

Pour travailler avec la page **Feuille création zone**, vous devez être configuré comme employé d'entrepôt à l'emplacement où les zones existent. Pour plus d'informations, voir [Configurer des employés d'entrepôt](warehouse-how-to-set-up-warehouse-employees.md).    

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille de création de zone**, et choisissez le lien associé.  
2.  Choisissez l'action **Calculer zones**.
3. Sur la page **Calculer zones**, sous **Code modèle zone**, sélectionnez le modèle zone à utiliser comme modèle pour les zones que vous créez.
4.  Saisissez une description pour les emplacements que vous êtes en train de créer.  
5.  Pour créer des codes d'emplacement, renseignez les champs **Du n°** et **Au n°** dans les trois catégories indiquées sur la page : **Travée**, **Section** et **Niveau**. Le code de zone peut contenir au maximum 20 caractères.  

    > [!NOTE]  
    >  Le nombre de caractères saisis dans les champs des trois catégories \(par exemple, les caractères saisis dans les trois champs **Du n°**\), auxquels s'ajoutent les éventuels séparateurs de champs, doit être inférieur ou égal à 20.  

     Vous pouvez utiliser des lettres dans le code, mais la lettre utilisée doit être identique dans les champs **Du n°** et **Au n°** . Par exemple, vous pouvez définir la partie Travée du code de la manière suivante : **Du n° A01** et **Au n° A10**. L’application n’est pas configurée pour générer des codes comprenant des suites de lettres (par exemple, de A01 à F05).  

6.  Si vous souhaitez qu'un caractère (par exemple, un trait d'union) sépare les champs des catégories que vous avez définis comme faisant partie du code emplacement, renseignez le champ **Séparateur de champs** avec ce caractère.  
7.  Pour que l'application ne crée pas de ligne pour une zone si elle existe déjà, sélectionnez le champ **Vérifier existence zone**.  
8. Une fois le remplissage de toutes les lignes terminé, sélectionnez le bouton **OK**.

    L'application crée une ligne pour chaque zone dans la feuille. Vous pouvez maintenant supprimer certains emplacements, par exemple si vous avez un casier qui vous permet d'accéder aux deux premiers niveaux de deux sections.  

9. Lorsque vous supprimez toutes les zones inutiles, choisissez l’action **Créer zones** pour que l’application crée des zones pour chaque ligne de la feuille.  

Répétez l’opération pour un autre ensemble de zones jusqu’à ce que vous ayez créé toutes les zones de votre entrepôt.  

## <a name="see-also"></a>Voir aussi .

[Vue d’ensemble de la gestion d’entrepôt](design-details-warehouse-management.md)  
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)    
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
