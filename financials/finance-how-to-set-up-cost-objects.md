---
title: "Procédure : configurer des objets de coûts | Microsoft Docs"
description: "Découvrez comment configurer des objets de coûts, qui sont similaires aux dimensions pour le grand livre."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 07/01/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 3f371a772f710576a70bac4808b15be091a61d66
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="set-up-cost-objects"></a>Configurer les objets de coûts
Les objets de coûts sont les projets, les biens ou les services d'une compagnie. Le plan des objets de coûts est semblable aux informations sur la dimension pour le grand livre. Vous pouvez configurer le plan des coûts associés comme suit :  

* Transférez des valeurs de dimension du grand livre vers le plan des objets de coûts. Vous pouvez effectuer tous les ajustements nécessaires après le transfert.  
* Créez un nouveau plan des objets de coûts, qui est indépendant du grand livre ou ajoutez un nouvel objet de coûts à un plan des objets de coûts existant. Vous devez créer chaque objet de coût individuellement.  

## <a name="to-transfer-dimension-values-from-the-general-ledger-to-the-chart-of-cost-objects"></a>Pour transférer des valeurs de dimension du grand livre vers le plan des objets de coûts  
1.  Définissez un axe analytique pour être celui des coûts associés dans la fenêtre **Actualiser axes analytiques CA**. Seules les valeurs de cette dimension sont transférées.  
2.  Choisissez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "icône Page ou rapport pour la recherche"), entrez **Plan comptable des objets de coûts**, puis sélectionnez le lien associé.  
3.  Choisissez l'action **Extraire les objets de coûts de la dimension** pour transférer des valeurs de dimension vers le plan comptable des objets de coûts. La fonction transfère les axes analytiques que vous avez définis dans l'étape 1.  

    > [!NOTE]  
    >  Vous pouvez configurer le champ **Aligner dimension objet de coûts** pour définir une synchronisation unidirectionnelle des valeurs de dimension à partir du grand livre vers le plan des objets de coûts. Vous ne pouvez pas définir une synchronisation du plan des objets de coûts avec les valeurs de dimension issues du grand livre.  

Le plan des objets de coûts comprend désormais toutes les valeurs de dimension spécifiées provenant du grand livre. Il inclut les titres et les sous-totaux.  

## <a name="to-create-new-cost-objects-in-the-chart-of-cost-objects-window"></a>Pour créer de nouveaux coûts associés dans la fenêtre Plan comptable des coûts associés  
Vous pouvez configurer et gérer les coûts associés, soit dans la fenêtre **Fiche coûts associés**, soit dans la fenêtre **Plan comptable des coûts associés**. Dans cette procédure, vous configurez de nouveaux coûts associés dans la fenêtre **Plan comptable des coûts associés**.  

1.  Ouvrez la fenêtre **Plan comptable des coûts associés** en mode édition.  
2.  Dans le champ **Code**, entrez le code coût associé. Tous les coûts associés doivent avoir un code.  
3.  Dans le champ **Nom**, saisissez le nom du coût associé.  
4.  Sélectionnez la flèche déroulante dans le champ **Type ligne** pour spécifier l'objectif de l'objet de coûts.  

    * Pour les objets de coûts de type de ligne **Total**, renseignez le champ **Total De/À**. Utilisez l'opérateur **or**, qui est une ligne verticale (**&#124;**), pour définir les plages des coûts associés.  
    * Pour les objets de coûts de type de ligne **Fin total**, ce champ est renseigné automatiquement lorsque vous utilisez la fonction de décalage.  
5.  Renseignez le champ **Ordre de tri**.  
6.  Choisissez la ligne vide suivante pour créer un nouvel objet de coûts, puis répétez les phases 2 à 5.  
7.  Après avoir défini tous les objets de coûts, choisissez l'action **Décaler les objets de coûts**. Cliquez sur le bouton **Oui**.  

> [!IMPORTANT]  
>  Si vous avez saisi des définitions dans les champs **Total De/À** pour les objets de coûts **Fin total** avant d'exécuter la fonction de décalage, vous devez les saisir à nouveau. La fonction remplace les valeurs dans tous les champs **Fin total**.  

## <a name="see-also"></a>Voir aussi  
[Comptabilité pour les coûts](finance-manage-cost-accounting.md)  
[Définition des centres de coûts et des coûts associés pour le plan comptable](finance-defining-cost-centers-and-cost-objects-for-chart-of-accounts.md)   
[Soldes entre le type de coût, un centre de coûts et les coûts associés](finance-balances-between-cost-type-cost-center-and-cost-object.md)   
[Paramétrage du contrôle de gestion](finance-set-up-cost-accounting.md)   
[Terminologie en comptabilité analytique](finance-terminology-in-cost-accounting.md)   
[À propos de la comptabilité analytique](finance-about-cost-accounting.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)

