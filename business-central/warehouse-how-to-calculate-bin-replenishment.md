---
title: Calculer le réapprovisionnement de la zone
description: Lorsque l'emplacement est configuré pour utiliser le prélèvement et le rangement suggérés, les priorités du modèle de rangement de l'emplacement sont prises en compte lors du rangement des réceptions.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.search.form: 7315, 7351
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 0f2653087df90ca6801f0d2e972f142e1f65b889
ms.sourcegitcommit: 3acadf94fa34ca57fc137cb2296e644fbabc1a60
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/19/2022
ms.locfileid: "9530822"
---
# <a name="calculate-bin-replenishment"></a>Calculer le réapprovisionnement de la zone

Lorsque l'emplacement est configuré pour utiliser le prélèvement et le rangement suggérés, les priorités du modèle de rangement de l'emplacement sont prises en compte lors du rangement des réceptions. Les priorités incluent les quantités minimale et maximale du contenu de la zone qui ont été définies pour une zone particulière, ainsi que les classements de zone. Par conséquent, si des articles arrivent régulièrement, les zones prélèvement les plus utilisées sont remplies dès qu'elles sont vides.  

Cependant, les articles en inventaire n'arrivent pas toujours de manière régulière. Parfois, votre compagnie achète des articles en grande quantité afin d'obtenir un escompte de paiement ou votre unité de mesure de production fabrique un article en grande quantité afin de réduire le coût unitaire. L'entrepôt ne reçoit aucun article pendant un certain temps et doit périodiquement déplacer des articles de zones de stockage en vrac vers des emplacements prélèvement.  

Il se peut aussi que l'entrepôt attende l'arrivée imminente d'un nouveau stock et veuille vider la zone de stockage en vrac des articles avant l'arrivée de la nouvelle marchandise.  

Enfin, si vous avez défini vos zones stockage en vrac avec une action de type de zone **Rangement** uniquement c'est à dire que l'action **Prélèvement** n'est pas sélectionnée pour le type de zone, vos zones prélèvement doivent toujours être réapprovisionnées, étant donné que les zones de type Rangement ne sont pas proposées pour un prélèvement d'inventaire.  

## <a name="to-replenish-pick-bins"></a>Pour réapprovisionner des emplacements prélèvement

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Feuille mouvement**, puis choisissez le lien associé.  
2.  Choisissez l'action **Calculer réappro. zone** pour ouvrir la page de demande de rapport.  
3.  Renseignez la page de demande de traitement en lot pour limiter la portée des propositions de réapprovisionnement qui sera calculée. Par exemple, vous pouvez vous intéresser à des articles, des zones ou des emplacements particuliers.  
4.  Cliquez sur le bouton **OK**. Des lignes sont créées pour les mouvements réapprovisionnement devant être effectués en fonction des règles configurées pour les emplacements et leur contenu, c'est à dire des articles.  
5.  Pour effectuer tous les réapprovisionnements proposés, choisissez l'action **Créer mouvement**. Les employés peuvent maintenant consulter les instructions à partir de l'élément de menu **Mouvements**, puis les exécuter et les enregistrer.  
6.  Si vous ne souhaitez exécuter que certaines propositions, supprimez les lignes moins importantes, puis créez un mouvement.  

Lorsque vous calculez un nouvel approvisionnement zone, les propositions supprimées seront recréées si elles sont toujours valides.  

> [!NOTE]  
>  Si un article répond aux conditions suivantes :  
>   
>  -   l'article a une date d'expiration et  
> -   Le champ **Prélèvement selon FEFO** sur la fiche magasin doit être sélectionné, et  
> -   Vous utilisez la fonction **Calculer réappro. emplacement**,  
>   
>  alors les champs **De zone** et **D'emplacement** sont vides, car l'algorithme qui permet de calculer d'où déplacer les articles est déclenché uniquement lorsque vous activez la fonction **Créer mouvement**.  

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/move-items/) associée

## <a name="see-also"></a>Voir aussi .

[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Prélèvement par FEFO](warehouse-picking-by-fefo.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
