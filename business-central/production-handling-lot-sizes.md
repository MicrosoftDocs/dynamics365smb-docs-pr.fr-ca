---
title: Gestion des tailles de lot
description: Cette rubrique décrit différentes manières de gérer les tailles de lot.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: null
ms.date: 04/01/2021
ms.author: bholtorf
---

# <a name="handling-lot-sizes-in-production"></a><a name="handling-lot-sizes-in-production"></a><a name="handling-lot-sizes-in-production"></a>Gestion des tailles de lot en production
En termes de quantité, le nombre d’articles que vous produisez lors d’une opération de production peut ne pas être corrélé à la manière dont ils les vendent. Par exemple, vous pouvez produire des centaines d’articles en un seul lot, mais vendre chaque article individuellement. Lorsque vous configurez vos itinéraires de production et vos nomenclatures, vous devez tenir compte de quelques nuances en ce qui concerne les tailles de lot. Cette rubrique décrit l’impact des tailles de lot sur les calculs des coûts et la planification des ressources.

## <a name="units-of-measure-in-production-bill-of-materials"></a><a name="units-of-measure-in-production-bill-of-materials"></a><a name="units-of-measure-in-production-bill-of-materials"></a>Unités de mesure dans la nomenclature de production
Bien que vous spécifiez l’unité de mesure de base (UdM) d’un article, votre nomenclature peut utiliser une UdM différente pour le produit fini. Par exemple, l’UdM de base d’un article peut être PCS, mais votre nomenclature peut appeler une palette ou une tonne. Ceci est pratique lorsque vos machines ou composantes brutes dictent le volume. Par exemple, vous ne voudriez probablement pas cuire un seul muffin, car il est difficile d’utiliser une portion d’œuf. Au lieu de cela, vous faites cuire un lot de muffins pour réduire le gaspillage. Pour plus d'informations, reportez-vous à [Créer des nomenclatures de production](production-how-to-create-production-boms.md).

## <a name="lot-size-on-routing-lines"></a><a name="lot-size-on-routing-lines"></a><a name="lot-size-on-routing-lines"></a>Taille de lot sur les lignes itinéraire
Du point de vue de l'itinéraire, vous pouvez spécifier une taille de lot sur les lignes itinéraire pour correspondre à la capacité des machines qui produisent les articles. Le temps d’exécution sur les lignes itinéraire est réduit proportionnellement à la taille de lot. 

Cela fonctionne bien lorsque la quantité sur un bon de production est un facteur de la taille du lot sur l'itinéraire. Par exemple, si votre plaque à pâtisserie peut contenir 10 muffins, vous devez en cuire 10, 20, 30 et ainsi de suite, et non 5 ni 15.  C’est beaucoup moins un problème si vous traitez de grandes quantités.

La taille de lot est également populaire dans les environnements de fabrication où la production est mesurée en tant que quantité que vous pouvez produire pendant une durée déterminée. Par exemple, si le volume par équipe de 9 heures est de 25 000 pieds cubes, vous pouvez définir la durée d’exécution sur 9 heures et la taille du lot sur 25 000.
La quantité du bon de production devient moins importante, car sur le bon de production, le temps d’exécution est calculé comme durée d’exécution/taille du lot pour obtenir le temps d’exécution par pièce.
 
> [!NOTE]
> La valeur définie dans Taille lot n’a pas d’impact sur le temps spécifié dans le champ **Temps de configuration** de la ligne itinéraire. La configuration ne se produira qu’une seule fois, même s’il y a plusieurs lots. Par exemple, pour ne pas avoir besoin de réchauffer le four pour le deuxième lot de muffins. Pour plus d'informations, voir [Créer des itinéraires](production-how-to-create-routings.md).

## <a name="lot-sizes-for-items-and-stockkeeping-units"></a><a name="lot-sizes-for-items-and-stockkeeping-units"></a><a name="lot-sizes-for-items-and-stockkeeping-units"></a>Tailles de lot pour les articles et les unités de stock
Les tailles de lot définies pour les itinéraires ne sont pas les mêmes que les tailles de lot pour les articles ou les unités de stock. Ces valeurs sont utilisées à des fins différentes et n’affectent pas la capacité de production. 

## <a name="lot-size-on-item-and-stockkeeping-units"></a><a name="lot-size-on-item-and-stockkeeping-units"></a><a name="lot-size-on-item-and-stockkeeping-units"></a>Taille de lot pour les articles et les unités de stock
Pour les articles et les unités de stock, les tailles de lot ont les effets suivants sur le calcul des coûts et la planification des approvisionnements :

* Pour le calcul des coûts standard, si vous activez **Coût avec configuration** sur la page **Configuration de la fabrication**, le coût de la configuration est ajouté au coût standard. Si vous spécifiez une taille de lot, le coût de configuration de l’opération d'itinéraire sera réduit en fonction d’une taille de lot. Par exemple, si la taille de votre lot définie sur la fiche article est de 10 et que le chauffage du four prend 15 minutes, le coût du carburant sera affecté aux 10 muffins en environ 1,5 minute. 

> [!NOTE]
> Les coûts de configuration sont traités différemment d'un point de vue de coût standard et d'affectation de capacité. Si la quantité produite ne correspond pas à la taille du lot définie dans la fiche article, cela entraînera une variation. Pour plus d’informations, reportez-vous à [Gestion des coûts de l'inventaire](finance-manage-inventory-costs.md). <!--not sure that I got this part right seems to repeat the first example.-->

Pour la planification des approvisionnements, le paramètre de taille de lot sur les articles fonctionne avec le champ **Tampon par défaut (%)** sur la page **Configuration de la fabrication**. [!INCLUDE[prod_short](includes/prod_short.md)] ignorera les changements de demande inférieurs au pourcentage de l’amortisseur et ne créera pas de suggestions de planification. Par exemple, 15 est spécifié dans le champ Tampon par défaut (%), et nous avons un bon de production de 20 muffins pour nourrir 20 invités, mais un invité ne peut pas y assister. [!INCLUDE[prod_short](includes/prod_short.md)] ignorera le seul invité manquant, car il ne représente que 10 % de la taille de lot 10 définie sur l’article. Cependant, si deux invités ne peuvent pas le faire, [!INCLUDE[prod_short](includes/prod_short.md)] suggérera que nous réduisions la quantité commandée, car deux correspond à 20 % de la taille de lot. Pour plus d’informations concernant la planification, voir [Planification](production-planning.md).

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi
[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Utiliser avec les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)
[Créer des itinéraires](production-how-to-create-routings.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
