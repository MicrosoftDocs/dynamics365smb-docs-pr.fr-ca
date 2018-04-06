---
title: "Procédure : créer des zones | Microsoft Docs"
description: "La méthode la plus efficace pour créer les zones de votre entrepôt consiste à générer des groupes de zones identiques dans la feuille de création de zones, mais vous pouvez également créer vos zones séparément."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 09/07/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: d7fb34e1c9428a64c71ff47be8bcff174649c00d
ms.openlocfilehash: 2e7388bb03ce47f3ef7fe232c5c5d8e7b43c23d1
ms.contentlocale: fr-ca
ms.lasthandoff: 03/22/2018

---
# <a name="create-bins"></a>Créer zones
La méthode la plus efficace pour créer les zones de votre entrepôt consiste à générer des groupes de zones identiques dans la feuille de création de zones, mais vous pouvez également créer vos zones séparément à partir de la fiche emplacement. Vous pouvez également utiliser une fonction de la fenêtre **Feuille création zone** pour créer des zones automatiquement.  

## <a name="to-create-a-bin-from-the-location-card"></a>Pour créer une zone à partir de la fiche emplacement  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Emplacements**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'emplacement à partir duquel vous souhaitez créer une zone, puis choisissez l'action **Zones**.  
3. Sélectionnez l'action **Nouveau**.
4. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-create-bins-individually-in-the-bin-creation-worksheet"></a>Pour créer séparément des zones dans la feuille de création de zones  
1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille création zone**, puis sélectionnez le lien associé.  
2.  Sur chaque ligne, renseignez les champs requis pour nommer et caractériser les emplacements que vous créez.  
3.  Choisissez l'action **Créer zones**.  

## <a name="to-make-bins-automatically-in-the-bin-creation-worksheet"></a>Pour créer des zones automatiquement dans la feuille de création de zones  
Avant de commencer à créer automatiquement des zones, déterminez les types de zone essentiels à vos opérations, ainsi que la circulation des articles la plus pratique dans la structure physique de votre entrepôt.  

> [!NOTE]  
>  Dès que vous utilisez une zone, vous ne pouvez pas la supprimer sauf si elle est vide. En revanche, si vous souhaitez utiliser un autre système d'attribution de nom de zone, vous pouvez utiliser le journal reclassement pour déplacer effectivement vos articles vers un nouveau système de zones. Cependant, ce processus est manuel et prend du temps ; il est donc préférable de configurer correctement vos emplacements dès le début.  

Pour travailler avec la fenêtre **Feuille création emplacement**, vous devez être défini comme magasinier à l'endroit où les emplacements existent. Pour plus d'informations, voir [Configurer des employés d'entrepôt](warehouse-how-to-set-up-warehouse-employees.md).    

1.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Feuille création zone**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Calculer zones**.
3. Dans la fenêtre **Calculer zones**, sous **Code modèle zone**, sélectionnez le modèle de zone à utiliser comme modèle pour les zones que vous créez.
4.  Saisissez une description pour les emplacements que vous êtes en train de créer.  
5.  Pour créer des codes d'emplacement, renseignez les champs **Du n°** et **Au n°** dans les trois catégories indiquées ci\-dessous : **Travée**, **Section** et **Niveau**. Le code de zone peut contenir au maximum 20 caractères.  

    > [!NOTE]  
    >  Le nombre de caractères saisis dans les champs des trois catégories \(par exemple, les caractères saisis dans les trois champs **Du n°**\), auxquels s'ajoutent les éventuels séparateurs de champs, doit être inférieur ou égal à 20.  

     Vous pouvez utiliser des lettres dans le code, mais la lettre utilisée doit être identique dans les champs **Du n°** et **Au n°** . Par exemple, vous pouvez définir la partie Travée du code de la manière suivante : **Du n° A01** et **Au n° A10**. Le programme n'est pas configuré pour générer des codes comprenant des suites de lettres (par exemple, de A01 à F05).  

6.  Si vous souhaitez qu'un caractère (par exemple, un trait d'union) sépare les champs des catégories que vous avez définis comme faisant partie du code emplacement, renseignez le champ **Séparateur de champs** avec ce caractère.  
7.  Pour que le programme ne crée pas de ligne pour un emplacement si elle existe déjà, sélectionnez le champ **Vérifier existence emplacement**.  
8. Une fois le remplissage de toutes les lignes terminé, sélectionnez le bouton **OK**.

    Le programme crée dans la feuille une ligne pour chaque zone. Vous pouvez maintenant supprimer certains emplacements, par exemple si vous avez un casier qui vous permet d'accéder aux deux premiers niveaux de deux sections.  

9. Lorsque vous avez supprimé toutes les zones inutiles, choisissez l'action **Créer zones** pour que le programme crée des zones pour chaque ligne de la feuille.  

Répétez l'opération pour un autre ensemble d'emplacements jusqu'à ce que vous ayez créé tous les emplacements de votre entrepôt.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

