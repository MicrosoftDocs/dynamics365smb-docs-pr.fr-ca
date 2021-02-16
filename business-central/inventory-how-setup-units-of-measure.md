---
title: Comment configurer des unités de mesure article | Microsoft Docs
description: Vous pouvez définir plusieurs unités de mesure pour un article afin de pouvoir affecter des unités de mesure à l'article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: UOM
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 5b10d8e8c8dd6142a4b9ed2c9604fd4e9c7e9c74
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4746276"
---
# <a name="set-up-units-of-measure"></a>Configuration d'unités de mesure

Dans le cadre de la configuration de votre [!INCLUDE [prod_short](includes/prod_short.md)], vous définissez des unités de mesure générales sur la page **Unités de mesure**. Ensuite, lorsque vous enregistrez de nouveaux articles, vous spécifiez l'unité de mesure de base sur la **Fiche article**. Mais vous pouvez également ajouter des unités de mesure ultérieurement.  

Vous pouvez configurer plusieurs unités de mesure pour un article afin que vous puissiez affecter des unités de mesure à l'article aux fins suivantes :

- Affectez une unité de mesure de base sur la fiche article de l'article pour définir la manière dont elle est stockée dans l'inventaire et pour servir de base de conversion aux autres unités de mesure.
- Affectez d'autres unités de mesure pour les documents d'achat, de production, ou de vente pour spécifier le nombre d'unités de mesure de base que vous gérez dans ces processus. Par exemple, vous pouvez acheter l'article en palettes et n'utiliser que des pièces individuelles en production.

Si un article est stocké dans une unité mais produit dans une autre, un ordre de fabrication utilisant une unité de lot de fabrication est créé pour calculer la quantité correcte des composants durant le traitement par lots **Actualiser O.F.**. Une situation dans laquelle un article fabriqué est stocké en pièces mais produit en tonnes est un exemple d'un calcul d'unité de mesure de lot de fabrication. Pour plus d'informations, voir [Utiliser les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md).  

## <a name="to-set-up-units-of-measure"></a>Pour configurer des unités de mesure

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Unités de mesure**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**. Une nouvelle ligne vide est insérée.  
3. Remplissez les champs. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  
4. Si vous savez que votre organisation vendra des articles avec cette unité de mesure à des clients dans d'autres pays, vous pouvez ajouter des traductions.  
    1. Sélectionnez le code pour lequel vous souhaitez définir des traductions, puis cliquez sur **Traductions**.
    2. Dans le champ **Code langue**, sélectionnez la flèche déroulante pour visualiser la liste des codes langue disponibles. Sélectionnez le code langue pour lequel vous souhaitez entrer une traduction, puis choisissez le bouton OK pour copier le code dans le champ.
    3. Dans le champ **Description**, saisissez le texte approprié.
5. Répétez les étapes précédentes pour toutes les unités de mesure supplémentaires que vous souhaitez ajouter.  

Lorsque vous enregistrez un nouvel article, vous pouvez choisir l'unité de mesure de base dans la liste des unités de mesure que vous avez maintenant configurée. Vous pouvez également configurer plusieurs unités de mesure pour un article.  

## <a name="to-set-up-multiple-item-units-of-measure"></a>Pour configurer plusieurs unités de mesure article

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.
2. Ouvrez la fiche article pour laquelle vous souhaitez configurer des unités de mesure de remplacement.
3. Choisissez l'action **Unités de mesure**. La page **Unités de mesure article** s'ouvre.
4. Si le champ **Unité de mesure de base** de la fiche article est renseigné, cette unité de mesure est déjà configurée.
5. Sélectionnez l'action **Nouveau**. Une nouvelle ligne vide est insérée.
6. Dans le champ **Code**, entrez le nom de l'unité de mesure. Sinon, sélectionnez le champ pour choisir parmi les codes unité de mesure figurant dans la base de données.
7. Dans le champ **Quantité par unité de mesure** entrez le nombre d'unités de l'unité de mesure de base que la nouvelle unité de mesure contient.
8. Éventuellement, dans les champs **Hauteur**, **Largeur**, **Longueur** et **Poids**, spécifiez des informations précises sur la taille des unités de mesure de manière à ce que [!INCLUDE [prod_short](includes/prod_short.md)] puisse calculer le nombre d'unités de mesure article pouvant être placées dans une zone donnée. Le champ **Cubage** est calculé automatiquement en fonction de la **Hauteur**, **Largeur** et **Longueur**.

    Si l'un de ces champs contient une valeur autre que 0, cette mesure est utilisée pendant tous les processus qui impliquent le placement d'articles dans une zone : rangement, mouvements, réceptions, livraisons, prélèvements et ajustements. [!INCLUDE [prod_short](includes/prod_short.md)] compare la somme de chaque mesure physique des articles rangés ajoutés à ceux qui se trouvent déjà dans la zone à la taille maximum ou à l'autre mesure qui peut être logée dans une zone, en fonction de la capacité de la zone sur la fiche emplacement pour cet article. En d'autres termes, vous devez utiliser la même mesure unitaire pour chaque dimension dans toutes les unités de mesure article; utilisez des kilogrammes ou des livres pour le poids, par exemple, mais soyez cohérent.
9. Répétez les étapes 5 à 7 pour configurer toutes les autres unités de mesure que vous souhaitez utiliser dans les différents processus de cet article.

    Dans le champ **Unité de mesure de base** situé au bas de la fenêtre, vous pouvez visualiser ou modifier l'unité de mesure de base de l'article. Vous pouvez également modifier l'unité de mesure de base dans le champ **Unité de mesure de base** de la fiche article. Sur la page **Unité de mesures article**, l'unité de mesure de base doit avoir la valeur **1** dans le champ **Qté par unité de mesure**.

Vous pouvez désormais utiliser les unités de mesure alternatives sur les documents d'achat, de production et de vente, comme décrit dans la section [Pour entrer un code unité de mesure par défaut pour des transactions de ventes et d'achat](#to-enter-a-default-unit-of-measure-code-for-sales-and-purchasing-transactions).  

## <a name="to-set-up-unit-of-measure-translations"></a>Pour configurer des traductions d'unités de mesure

Lorsque vous vendez des articles à des clients étrangers, vous pouvez être amené à indiquer l'unité de mesure dans leur langue. Pour cela, vous devez d'abord configurer les traductions d'unités de mesure nécessaires.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Unités de mesure**, puis sélectionnez le lien associé.
2. Sélectionnez le code pour lequel vous souhaitez définir des traductions, puis cliquez sur **Traductions**.
3. Dans le champ **Code langue**, sélectionnez la flèche déroulante pour visualiser la liste des codes langue disponibles. Sélectionnez le code langue pour lequel vous souhaitez entrer une traduction, puis choisissez le bouton OK pour copier le code dans le champ.
4. Dans le champ **Description**, saisissez le texte approprié.
5. Répétez les étapes 2 à 4 pour les langues et les codes unité de mesure pour lesquels vous souhaitez indiquer des traductions.

## <a name="to-enter-a-default-unit-of-measure-code-for-sales-and-purchasing-transactions"></a>Pour entrer un code unité de mesure par défaut pour des transactions de ventes et d'achat

Si vous utilisez habituellement d'autres unités de mesure que l'unité de mesure de base pour vos achats et vos ventes, vous pouvez indiquer des unités de mesure distinctes. Pour ce faire, vous devez configurer les unités de mesure sur la page **Unités de mesure article**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.
2. Ouvrez la fiche article appropriée pour laquelle vous souhaitez indiquer un code unité de mesure par défaut pour les achats et les ventes.
3. Pour les ventes, sur le raccourci **Facturation**, dans le champ **Unité de mesure vente**, ouvrez la page **Unités de mesure article**.
4. Pour les achats, sur le raccourci **Réapprovisionnement**, dans le champ **Unité de mesure achat**, ouvrez la page **Unités de mesure article**.
5. Sélectionnez le code que vous souhaitez configurer comme unité de mesure par défaut pour les ventes ou les achats respectivement, puis cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi

[Utiliser les unités de mesure de lot de fabrication](production-how-to-use-the-manufacturing-batch-unit-of-measure.md)  
[Enregistrer de nouveaux articles](inventory-how-register-new-items.md)  
[Gestion de l'inventaire](inventory-manage-inventory.md)  
[Gestion des achats](purchasing-manage-purchasing.md)  
[Gestion des ventes](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
