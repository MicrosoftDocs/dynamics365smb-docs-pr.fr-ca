---
title: Comment planifier des prélèvements dans des feuilles | Microsoft Docs
description: Lorsque l'entrepôt est configuré pour exiger un traitement des prélèvements et des livraisons, le fonctionnement de l'entrepôt peut être établi de telle sorte que les lignes des documents livraison ne soient pas automatiquement transformées en instructions de prélèvement, mais soient plutôt activées sur le journal prélèvement.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: a340c06dab26f0f1426efea95ec5bfc614417825
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3192949"
---
# <a name="plan-picks-in-worksheets"></a>Planifier des prélèvements dans la feuille
Lorsque l'entrepôt est configuré pour exiger un traitement des prélèvements et des livraisons, le fonctionnement de l'entrepôt peut être établi de telle sorte que les lignes des documents livraison ne soient pas automatiquement transformées en instructions de prélèvement, mais soient plutôt activées sur le journal prélèvement.  

> [!NOTE]  
>  Si des instructions de prélèvement entrepôt ont déjà été créées et que vous souhaitez les combiner pour former une instruction de prélèvement plus efficace, supprimez les prélèvements entrepôt individuels. Les lignes à prélever sont alors listées dans la feuille.  

Dans la feuille prélèvement, vous pouvez définir des listes de prélèvement pour les employés de manière à réduire au minimum leurs déplacements lors du prélèvement des articles dans l'entrepôt. Les champs contiennent des informations concernant les quantités d'articles disponibles dans les zones de transbordement. En cas de transbordement, ces champs vous permettent de planifier l'affectation des tâches, car l'application propose toujours en priorité de prélever un article dans une zone de transbordement avant de le prélever dans une autre zone, quelle que soit l'unité de mesure de l'article. Les lignes de la feuille peuvent provenir d'un certain nombre de documents sources et être triées par article, numéro tablette, document source, date d'échéance ou adresse de livraison.  

Si vous triez par date d'échéance, vous pouvez choisir d'effacer de la feuille toutes les lignes à l'exception de celles nécessitant un traitement immédiat. Les lignes moins urgentes ne sont pas effacées mais renvoyées à la feuille **sélection prélèvement**. Lorsque vous créez le prélèvement, les lignes sont déjà triées par date d'échéance et vous pouvez choisir d'affecter le prélèvement à un employé donné.  

> [!NOTE]  
>  Le prélèvement pour la livraison entrepôt des articles assemblés au document de vente en cours de livraison suit les mêmes étapes que les prélèvements entrepôt ordinaires pour la livraison, comme décrit dans cette rubrique. Cependant, le nombre de lignes prélèvement par quantité à livrer peut varier considérablement, car ce sont les composantes qui sont prélevées et non l'élément d'assemblage.  
>   
>  Les lignes prélèvement entrepôt sont créées suivant la valeur du champ **Quantité restante** sur les lignes de l'ordre d'assemblage associé à la ligne document de vente en cours de livraison. Ceci garantit le prélèvement de toutes les composantes en une seule tâche.  
>   
>  Pour plus d’informations, reportez-vous à la section « Traitement des articles à assembler pour commande dans les livraisons entrepôt » dans Livraison entrepôt.  
>   
>  Pour plus d'informations sur le prélèvement de composantes pour les ordres d'assemblage en général, notamment les situations où l'élément d'assemblage n'est pas dû dans une livraison vente, voir [Prélever pour l'assemblage ou la production dans les configurations de stockage avancées.](warehouse-how-to-pick-for-internal-operations-in-advanced-warehousing.md).  

## <a name="to-plan-picks-in-the-worksheet"></a>Pour planifier des prélèvements dans la feuille  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Feuille prélèvement**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Extraire documents entrepôt**.  
3.  Sélectionnez les livraisons pour lesquelles vous souhaitez préparer un prélèvement. Vous pouvez à présent opérer un tri ponctuel, qui ne suivra pas l'instruction globale de prélèvement. Vous pouvez aussi supprimer certaines lignes pour rendre le prélèvement plus efficace. Par exemple, si un certain nombre de lignes comporte des articles situés dans des zones de transbordement, vous pouvez créer un prélèvement pour toutes les lignes associées à ces lignes. Les articles transbordés seront livrés, avec les autres articles des livraisons, et les zones de transbordement pourront à nouveau recevoir d'autres articles entrants.  
4.  Choisissez l'action **Créer prélèvement**, puis remplissez la page de demande **Créer prélèvement**. Le tri que vous demandez ici organisera les lignes prélèvement que vous créez. Par exemple, vous pouvez créer un prélèvement pour chaque zone et trier les lignes selon le classement de zone au sein de chaque prélèvement.  
5.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Prélèvements**, puis sélectionnez le lien associé. La page **Prélèvements** s'ouvre.  
6.  Vous pouvez à présent trouver le prélèvement affecté que vous venez de créer en sélectionnant le prélèvement doté du numéro le plus élevé.  
7.  Dans ce prélèvement, vous pouvez toujours au besoin modifier le code utilisateur de la personne à qui ce prélèvement est affecté, ainsi que le mode de tri des lignes.  
8.  Choisissez l'action **Imprimer** pour imprimer les instructions relatives au prélèvement.  
9. Une fois le prélèvement exécuté, choisissez l'action **Enregistrer**.  

Si la numérotation des zones reflète la disposition de l'entrepôt, les lignes triées par code de zone permettent à la personne qui réalise le prélèvement de prélever les articles nécessaires à plusieurs livraisons en ne réalisant qu'un tour dans l'entrepôt. L'employé prélève dans chaque zone le nombre d'articles requis pour chaque ligne livraison et les place avec les autres articles en les organisant par livraison. L'employé gagne ainsi un temps considérable en prélevant en une fois dans une zone donnée les articles nécessaires à plusieurs livraisons.  

Le classement de zone constitue une autre méthode de tri efficace, si l'entrepôt est organisé en fonction du classement de zone plutôt que du code de zone.  

Dans la feuille prélèvement, vous pouvez aussi trier par adresse de livraison, ce qui vous permet d'assembler, puis de livrer en premier les commandes destinées aux clients lointains.  

## <a name="see-also"></a>Voir aussi
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
