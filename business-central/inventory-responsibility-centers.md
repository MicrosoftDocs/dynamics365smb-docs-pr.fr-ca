---
title: Procédure d'utilisation des centres de gestion | Microsoft Docs
description: Les centres de gestion permettent de gérer les centres administratifs. Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: e552378625325710b50989c513d303acd9c480af
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5774799"
---
# <a name="work-with-responsibility-centers"></a>Utiliser les centres de gestion

Les centres de gestion permettent de gérer les centres administratifs. Un centre de gestion peut être un centre de coûts, un centre de profit, un centre d'investissement ou tout autre centre administratif défini par la compagnie. Un bureau de vente, un département d'achat pour plusieurs emplacements, un bureau de planification d'usine, etc. sont des exemples de centres de gestion. Par exemple, cette fonctionnalité permet aux compagnies de configurer des vues spécifiques à l'utilisateur des documents vente et achat associés exclusivement à un centre de gestion particulier.  

L'utilisation de plusieurs emplacements avec des centres de gestion permet de gérer les activités commerciales de façon flexible et optimale.

Des emplacements multiples permettent aux compagnies de gérer leur inventaire dans plusieurs emplacements au moyen d'une seule base de données. Deux concepts, des magasins et des points de stock, sont les pierres angulaires du granule. Un emplacement est défini comme un lieu qui gère l'emplacement physique et la quantité des articles. Le concept est assez étendu pour inclure des magasins tels que les usines ou les unités de fabrication et les centres de distribution, les entrepôts, les magasins d'exposition et les véhicules de service. Une unité de stock est définie comme un article à un emplacement spécifique et/ou comme une variante. Grâce aux unités de stock, les compagnies utilisant plusieurs emplacements peuvent ajouter des informations de réapprovisionnement, des adresses de livraison et des informations financières de report au niveau de l'emplacement. Elles peuvent ainsi réapprovisionner les variantes du même article pour chaque emplacement et commander des articles pour chaque emplacement d'après les informations de réapprovisionnement spécifiques de l'emplacement.  

## <a name="to-set-up-a-responsibility-center"></a>Pour configurer un centre de gestion

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Centres de gestion**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

    Si vous utilisez des centres de gestion pour administrer votre compagnie, il peut être utile de définir un centre de gestion par défaut pour votre compagnie.
4. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Informations compagnie**, puis sélectionnez le lien associé.
5. Dans le champ **Centre de gestion**, entrez un code centre de gestion.

Ce code est utilisé sur tous les documents achat, vente ou service si l'utilisateur, le client ou le fournisseur n'a pas de centre de gestion par défaut. Sur un document vente, achat ou service, vous pouvez saisir un autre centre de gestion à la place de la valeur par défaut.

> [!NOTE]  
> Lorsque vous saisissez un code centre de gestion sur un document, le programme affecte l'adresse, les axes et les prix indiqués sur le document.  

## <a name="to-assign-responsibility-centers-to-users"></a>Pour affecter des centres de gestion à des utilisateurs

Vous pouvez configurer des utilisateurs de sorte que, dans leurs routines quotidiennes, l'application récupère uniquement les documents propres à leur activité. Les utilisateurs sont généralement associés à un centre de gestion et utilisent uniquement les documents propres à des modules spécifiques de ce centre.  

Pour configurer cela, vous devez affecter des centres de gestion à des utilisateurs dans trois modules : Achats, Ventes et Gestion des services.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration utilisateur**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration des utilisateurs**, sélectionnez l'utilisateur auquel vous souhaitez affecter un centre de gestion. Si l'utilisateur ne figure pas dans la liste, saisissez un code utilisateur dans le champ **Code utilisateur**.  
3. Dans le champ **Filtre centre gestion vente**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux ventes.  
4. Dans le champ **Filtre centre gestion achat**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées aux achats.  
5. Dans le champ **Filtre centre gestion service**, indiquez le centre de gestion dans lequel l'utilisateur aura des tâches liées à la gestion des services.  

> [!NOTE]  
> Les utilisateurs peuvent afficher uniquement les documents reportés liés à leur propre centre de responsabilité. Cependant, ils peuvent afficher toutes les écritures et accéder à d’autres documents reportés à partir des écritures.

## <a name="see-also"></a>Voir aussi

[Configuration de l'inventaire](inventory-setup-inventory.md)  
[Configuration de la gestion d'entrepôt](warehouse-setup-warehouse.md)
[Inventaire](inventory-manage-inventory.md)[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Gestion d’entrepôt](warehouse-manage-warehouse.md)  
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]