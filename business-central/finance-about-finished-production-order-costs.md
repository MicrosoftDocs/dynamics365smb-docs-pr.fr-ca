---
title: À propos des coûts des bons de production achevés
description: La finition du bon de production est essentielle pour terminer le cycle de vie des coûts d’un article de production. Les coûts finaux sont calculés dans le traitement en lot Ajuster coût écritures article.
author: SorenGP
ms.topic: conceptual
ms.search.form: 99000867
ms.date: 06/16/2021
ms.author: edupont
ms.openlocfilehash: dd9010e055e5e24cafb87846b8eed98f54d83474
ms.sourcegitcommit: ef80c461713fff1a75998766e7a4ed3a7c6121d0
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2022
ms.locfileid: "8147840"
---
# <a name="about-finished-production-order-costs"></a>À propos des coûts des bons de production achevés

L'achèvement du bon de production est une tâche importante dans l'évaluation du cycle de vie de l'article en cours de production. Les coûts finaux, notamment les écarts dans un environnement de coût standard, les valeurs réelles dans un environnement de coût FIFO, Moyenne ou LIFO, sont calculés à l'aide du traitement en lot **Ajuster coûts - Écr. article** qui permet d'opérer un rapprochement financier des coûts de production d'un article. Pour qu'un ordre de fabrication soit pris en considération pour un ajustement de coût, son statut doit être **Produit fini**. Il est donc essentiel qu'au moment de son achèvement, le statut d'un ordre de fabrication soit modifié en **Produit fini**.  

## <a name="example"></a>Exemple :

Dans un environnement de coût standard, lorsque vous consommez des matières pour produire un article, le coût de l'article, celui de la main-d'œuvre et celui des frais généraux sont répertoriés dans le TEC, pour définir simplement les choses. Lorsque l'article est produit, son coût standard est retranché du TEC. Généralement, le résultat de l'opération n'est pas égal à zéro. Pour que le résultat obtenu soit égal à zéro, vous devez exécuter le traitement en lot **Ajuster coûts - Écr. article** en sachant que seuls les bons de production dont l'état est **Fini** seront pris en considération pour l'ajustement.  

## <a name="see-also"></a>Voir aussi

[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Production](production-manage-manufacturing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]