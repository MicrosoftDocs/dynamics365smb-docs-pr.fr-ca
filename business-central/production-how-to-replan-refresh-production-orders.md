---
title: Procédure de replanification ou d'actualisation directe des ordres de fabrication | Microsoft Docs
description: Les lignes bon de production affichent les articles à produire à l'aide du bon de production.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: e3e1fa5535637f204c942aa8d3589dfff0392333
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5787812"
---
# <a name="replan-or-refresh-production-orders-directly"></a>Replanifier ou actualiser directement des ordres de fabrication
La fonction **Replanifier** des bons de production est généralement utilisée après avoir ajouté ou modifié des composantes constituant des bons de production sous-jacents. La fonction calcule les modifications apportées aux composantes et aux lignes itinéraires. Elle inclut les articles situés à des niveaux de nomenclatures de production inférieurs, pour lesquels elle peut générer de nouveaux bons de production.  

Sur la base des modifications apportées aux composants et aux lignes gamme, la fonction Replanifier calcule et planifie toutes les nouvelles demandes de l'ordre de fabrication.  

La fonction **Actualiser** des ordres de fabrication est généralement utilisée après avoir effectué une des opérations suivantes :

- Créé un en-tête d'un bon de production manuellement pour calculer et créer des données de ligne pour la première fois.
- Apporté des modifications à un en-tête d'un bon de production pour recalculer toutes les données de ligne.

La fonction Actualiser calcule les modifications apportées à un en-tête d'ordre de fabrication et ne prend pas en compte les niveaux nomenclature de production. La fonction a pour rôle de calculer et d'initier les valeurs des lignes composante et des lignes itinéraire en fonction des données de base définies dans la nomenclature de production et l'itinéraire affectés, selon la quantité commande et la date d'échéance de l'en-tête du bon de production.

Vous pouvez soit insérer les lignes bon de production manuellement, soit utiliser la fonction de calcul de ces lignes à partir de l'en-tête.  

> [!NOTE]
> Si vous utilisez la fonction Actualiser pour recalculer des lignes O.F., les anciennes lignes O.F. sont supprimées et de nouvelles lignes sont calculées.  

## <a name="to-replan-a-production-order"></a>Pour replanifier un bon de production  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de production planifiés fermes**, puis sélectionnez le lien associé.  
2.  Ouvrez l'ordre de fabrication à replanifier.  
3.  Sur le raccourci **Lignes**, choisissez l'action **Lignes**, puis choisissez l'action **Composantes**.  
4.  Ajoutez une composante qui soit un article produit ou un sous-ensemble.  
5.  Dans l'ordre de fabrication, choisissez l'action **Replanifier**.  

    Sur la page **Replanifier O.F.**, définissez la procédure et les éléments à replanifier.  
6.  Dans le champ **Direction**, sélectionnez l'une des options suivantes.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Retour**|Calcule la séquence d'opérations en amont, de la date fin la plus proche possible, définie par la date d'échéance et/ou d'autres commandes programmées, à la date début la plus éloignée possible. **Note :** cette option par défaut convient à la majorité des cas.|  
    |**Aval**|Calcule la séquence d'opérations en aval, de la date début la plus éloignée possible, définie par la date d'échéance et/ou d'autres commandes programmées, à la date fin la plus proche possible. **Note :** cette option n'est utile que pour les commandes urgentes.|  

7.  Dans le champ **Planifier**, choisissez l'option correspondant au mode de calcul des exigences de production des articles produits sur la nomenclature, comme suit.  

    |Option|Description|  
    |----------------------------------|---------------------------------------|  
    |**Aucun niveau**|Ne prenez pas en compte la production de plus bas niveau. Cette option met uniquement à jour le calendrier de l'article, comme l'actualisation.|  
    |**Un niveau**|Planifie une demande fabrication pour le premier niveau. Des ordres de fabrication de premier niveau peuvent être créés.|  
    |**Tous niveaux**|Planifie une demande fabrication pour tous les niveaux. Des ordres de fabrication multi-niveaux peuvent être créés.|  

8.  Sélectionnez **Un niveau**, puis choisissez le bouton **OK** pour replanifier l'ordre de fabrication, et calculer et créer un ordre de fabrication sous-jacent pour le nouveau sous-ensemble, s'il n'est pas totalement disponible.  

> [!NOTE]  
>  Les modifications mises en œuvre via la fonction **Replanifier** risquent fortement de modifier la capacité nécessaire de l'ordre de fabrication et de vous obliger à effectuer par la suite une replanification des opérations.  

## <a name="to-refresh-a-production-order"></a>Pour actualiser un bon de production  
Si vous avez modifié des lignes bon de production, des composantes ou des lignes itinéraire, vous devez aussi actualiser les informations du bon de production. Dans la procédure qui suit, les composantes d'un bon de production planifié ferme sont calculées. La procédure est identique pour les lignes itinéraire.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bon de production planifié ferme**, puis sélectionnez le lien associé.  
2.  Sélectionnez l'action **Nouveau**. Pour plus d'informations, voir [Créer des ordres de fabrication](production-how-to-create-production-orders.md).  
3.  Sélectionnez l'action **Actualiser**.
4. Sur la page **Actualiser O.F.**, sélectionnez l'une des options suivantes :

    |Option|Description|  
    |----------------------------------|---------------|---------------------------------------|  
    |**Direction inscrite**|**Aval**|La programmation commence à la date début et se poursuit jusqu'à la date fin. Vous devez renseigner la date début pour pouvoir utiliser cette option.|  
    ||**Amont**|La programmation commence à la date fin et remonte jusqu'à la date début.|  
    |**Calculer**|**Lignes**|Sélectionnez ce champ pour calculer les lignes bon de production|  
    ||**Gammes**|Ce champ n'affecte pas le calcul des lignes fabrication.|  
    ||**Besoin composant**|Ce champ n'affecte pas le calcul des lignes fabrication.|  
    |**Entrepôt**|**Créer demande d'enlogement**|Ce champ n'affecte pas le calcul des lignes fabrication.|  

5. Cliquez sur le bouton **OK** pour confirmer votre choix. Les lignes bon de production sont calculées.

> [!NOTE]  
>  Le calcul des composantes bon de production supprime les modifications précédentes des composantes.

## <a name="see-also"></a>Voir aussi  
[Planification](production-planning.md)  
[Paramétrage de la production](production-configure-production-processes.md)  
[Production](production-manage-manufacturing.md)    
[Stock](inventory-manage-inventory.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Détails de conception : planification de l'approvisionnement](design-details-supply-planning.md)   
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]