---
title: Créer le contenus de la zone
description: Une fois que vous avez configuré vos zones, vous pouvez spécifier les articles à y stocker et configurer des règles qui contrôlent la fréquence de remplissage des zones.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 9cd37ecbadda34238d9fb7e74ef26f1bb218073a
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3923155"
---
# <a name="create-bin-contents"></a>Créer le contenus de la zone

Une fois la configuration des emplacements terminée, vous pouvez configurer leur contenu. En d'autres termes, vous pouvez configurer les articles à stocker dans une zone donnée et définir les règles qui régissent le remplissage de la zone avec un article spécifique. Vous pouvez effectuer cette opération manuellement sur la page **Contenu de la zone** ou automatiquement sur la page **Créer feuille contenu de la zone** .

## <a name="to-create-bin-content-manually"></a>Pour créer le contenu de la zone manuellement

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Emplacements** , puis sélectionnez le lien associé.  
2. Sélectionnez l'emplacement à partir duquel vous souhaitez créer des contenus de la zone, puis choisissez l'action **Zones** .  
3. Sélectionnez la zone à partir de laquelle vous souhaitez configurer un contenu, puis choisissez l'action **Contenus** .  
4. Pour chaque article que vous souhaitez stocker dans la zone, renseignez une ligne de la page **Contenus de la zone** avec les informations appropriées. Certains champs sont déjà renseignés avec des informations relatives à la zone.  
5. Renseignez d'abord le champ **N° article** , puis, si vous utilisez un prélèvement et un rangement suggérés, renseignez les autres champs tels que **Code unité de mesure** , **Qté max** et **Qté min** .  

Sélectionnez le champ **Fixe** si nécessaire. Si l'emplacement doit être utilisé comme emplacement par défaut pour l'article, sélectionnez le champ **Emplacement par défaut** .  

Si vous utilisez un prélèvement et un rangement suggérés et que vous avez saisi, via la fiche article, les dimensions exactes des unités de mesure de chaque article, la quantité maximale que vous avez saisie sur la page **Contenus de la zone** est comparée aux capacités physiques de la zone. Les quantités minimales et maximales sont alors utilisées lors du calcul du réapprovisionnement de la zone et des rangements proposés.  

Si vous sélectionnez le champ **Fixe** , vous associez l'article à l'emplacement de manière statique, ce qui signifie que [!INCLUDE[d365fin](includes/d365fin_md.md)] essaie de placer cet article dans l'emplacement si l'espace libre est suffisant et conserve l'enregistrement qui associe l'article de manière statique à l'emplacement, même lorsque la quantité à l'emplacement est égale à 0. Il est possible de placer d'autres articles dans la zone, même si un article a été associé à cette zone.  

> [!NOTE]  
> Vous pouvez configurer simultanément plusieurs contenus de la zone sur la page **Feuille création contenu de la zone** .  

## <a name="to-create-bin-content-with-a-worksheet"></a>Pour créer le contenu de la zone avec une feuille

Lorsque vous avez créé vos zones, vous pouvez créer le contenu de chaque zone dans la feuille de création de contenu de la zone.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Feuille de création du contenu de la zone** , puis sélectionnez le lien associé.  
2. Dans l'en-tête feuille, cliquez dans le champ **Nom** et sélectionnez la feuille du magasin où vous souhaitez créer le contenu d'un emplacement.  
3. Dans le champ **Code emplacement** , sélectionnez le code de l'emplacement dont vous souhaitez définir le contenu.  

    En cas d'utilisation d'un prélèvement et d'un rangement suggérés dans cet emplacement, les champs liés à la zone en question ( **Type zone** , **Code classe entrepôt** et **Classement de zone** ) seront renseignés automatiquement. Vous devez prendre en compte ces informations lors de la définition du contenu de la zone.  
4. Sélectionnez l'article à affecter à la zone et renseignez les champs relatifs au contenu de la zone. Pour pouvoir utiliser la fonction **Calculer réappro. zone** dans le cadre d'un prélèvement et d'un rangement suggérés, renseignez les champs **Qté max.** et **Qté min.**  

    Pour définir cette zone comme zone préférée pour l'article, même si la quantité zone est égale à **0** et que tous les autres critères de rangement sont égaux, sélectionnez le champ **Fixe** .  
5. Répétez les étapes 3 à 4 pour chaque article à affecter à une zone.  
6. Choisissez l'action **Imprimer** pour afficher un aperçu du contenu de la zone que vous avez entré dans la feuille et l'imprimer. Modifiez le contenu de la zone jusqu'à ce qu'il vous convienne.  
7. Lorsque vous êtes prêt, choisissez l'action **Créer contenu de la zone** .  

Dans cette feuille, vous pouvez utiliser des lignes contenu de la zone pour plusieurs zones, afin d'obtenir un aperçu convenable des articles que vous placez dans différents zones d'une zone, d'une allée, ou d'un casier donné.  

## <a name="see-also"></a>Voir aussi

[Calculer le réapprovisionnement de la zone](warehouse-how-to-calculate-bin-replenishment.md)  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Détails de conception : Configuration de l'entrepôt](design-details-warehouse-setup.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
