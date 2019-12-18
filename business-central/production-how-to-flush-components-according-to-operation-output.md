---
title: 'Procédure : consommer des composantes en fonction de la sortie réalisée | Microsoft Docs'
description: Pour les articles créés avec la méthode de consommation en amont le comportement par défaut est de calculer et de valider la consommation de composants lorsque vous affectez à l'ordre de fabrication lancé le statut **Terminé**. Pour plus d'informations, voir Méthode consommation.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2019
ms.author: sgroespe
ms.openlocfilehash: 09534c7a859f7e0a5ba7bf861718e060d5e56c3e
ms.sourcegitcommit: cfc92eefa8b06fb426482f54e393f0e6e222f712
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/03/2019
ms.locfileid: "2883272"
---
# <a name="flush-components-according-to-operation-output"></a>Consommer en aval des composantes en fonction de la production réalisée
Pour les articles créés avec la méthode de consommation en amont le comportement par défaut est de calculer et de valider la consommation de composants lorsque vous affectez à l'ordre de fabrication lancé le statut **Terminé**.  

Si vous définissez également les codes lien itinéraire, le calcul et le report ont lieu lorsque chaque opération est terminée et que la quantité effectivement consommée au cours de l'opération est reportée. Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).  

Par exemple, si un bon de production de 800 mètres nécessite pour son exécution 8 kilogrammes d'une composante, lorsque vous reportez 200 mètres de production, 2 kilogrammes sont automatiquement reportés comme étant consommés.  

Cette fonctionnalité est utile pour les motifs suivants :  

-   **Évaluation de l'inventaire** - Des écritures valeur pour la sortie et la consommation sont créées parallèlement à la progression du bon de production. Sans les codes lien itinéraire, la valeur de l'inventaire augmente lorsque la production est reportée, puis réduite ultérieurement lorsque la valeur de la consommation des composantes est reportée en même temps que le bon de production terminé.  
-   **Disponibilité de l'inventaire** - Avec un report progressif de la consommation, la disponibilité des articles composante est mieux actualisée, ce qui est important pour conserver l'équilibre interne entre l'offre et la demande. Sans les codes lien itinéraire, les autres demandeurs de la composante peuvent croire qu'elle est disponible tant que le report de sa consommation reste en attente.  
-   **Just-in-Time** - Si vous pouvez personnaliser les produits en fonction des demandes client, vous pouvez réduire les rebuts en vous organisant pour que les procédures de travail et les systèmes ne soient modifiés que lorsque c'est nécessaire.  

La procédure suivante montre comment combiner la consommation en amont et les codes lien itinéraire pour que la quantité consommée par chaque opération soit proportionnelle à la production réelle de cette opération terminée.  

## <a name="to-flush-components-according-to-operation-output"></a>Pour consommer en aval des composants en fonction de la production réalisée  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2.  Choisissez l'action **Modifier**.  
3.  Sur le raccourci **Réapprovisionnement**, dans le champ **Méthode consommation**, sélectionnez **En aval**.  

    > [!NOTE]  
    >  Sélectionnez **Prélèvement + Aval** si la composante est utilisée dans un emplacement configuré pour un prélèvement et un rangement suggérés.  

4.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Itinéraires**, puis sélectionnez le lien associé.  
5.  Définir les codes lien itinéraire pour chaque opération qui consomme la composante. Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).  
6.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Nomenclature production**, puis sélectionnez le lien associé.  
7.  Associe aux codes lien itinéraire de chaque instance de la composante l'opération dans laquelle elle est consommée.

    > [!IMPORTANT]  
    >  La composante doit avoir un lien itinéraire l'associant à la dernière opération de l'itinéraire.  

## <a name="see-also"></a>Voir aussi  
[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Planification](production-planning.md)   
[Inventaire](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
