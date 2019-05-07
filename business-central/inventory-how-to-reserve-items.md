---
title: 'Procédure : réserver des articles | Microsoft Docs'
description: Vous pouvez réserver des articles pour les documents de vente, les bons de commande et les bons de production. Vous pouvez réserver des articles en inventaire ou entrants sur les lignes document ouvertes.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: bca330009730caf5d8f4d6d82eb6bedab5e762c0
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "932182"
---
# <a name="reserve-items"></a>Réserver des articles
Vous pouvez réserver des articles pour les documents de vente, les bons de commande, les commandes service, les ordres d'assemblage et les bons de production. Vous pouvez réserver des articles en inventaire ou entrants sur les lignes document ou journal ouvertes. Vous effectuez le travail sur la page **Réservation**.

Chaque ligne de la page **Réservation**, que vous ouvrez pour réserver des articles, donne des informations sur un type de ligne (vente, achat, journal) ou d'écriture d'inventaire. Les lignes décrivent le nombre d'articles disponibles pour réservation à partir de chaque type de ligne ou d'écriture.

## <a name="to-reserve-items-for-sales"></a>Pour réserver des articles pour des ventes
Ce qui suit décrit comment réserver des articles pour un document de vente. Les étapes sont similaires à celles des commandes achat, service et ordre d'assemblage.  
1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente**, puis sélectionnez le lien associé.  
2.  Dans un document de vente, sur le raccourci **Lignes**, sélectionnez l'action **Réserver**. La page **Réservation** s’affiche.  
3. sélectionnez la ligne à partir de laquelle vous souhaitez réserver des articles.  
4. Choisissez l'une des actions suivantes.  

    |**Fonction.**|**Description**|
    |------------------|---------------------|  
    |**Réservation automatique**|Permet de réserver automatiquement des articles sur la page **Réservation**.|  
    |**Réserver à partir de la ligne courante**|Permet de réserver des articles sur la ligne du document que vous avez sélectionnée.|  
    |**Annuler la réservation de la ligne courante**|Permet d'annuler la réservation d'articles sur la ligne du document que vous avez sélectionnée.|

> [!NOTE]  
>  Si des lignes traçabilité article existent pour le document de vente, le système de réservation vous fera suivre une procédure spéciale : Pour plus d'informations, voir [Pour réserver un numéro de série ou de lot particulier](inventory-how-to-reserve-items.md#to-reserve-a-specific-serial-or-lot-number).  

## <a name="to-reserve-an-item-for-a-production-order-line"></a>Pour réserver un article pour une ligne O.F.  
Vous pouvez réserver des articles pour des ordres de fabrication. Vous devez distinguer les lignes bon de production, correspondant à l'article parent, et les composantes bon de production.

La procédure suivante se base sur un bon de production planifié ferme.   
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **O.F. planifié ferme**, puis sélectionnez le lien associé.  
2. Ouvrez l'O.F. planifié ferme pour lequel vous souhaitez réserver des articles parents.  
3. Sélectionnez la ligne bon de production concernée.  
4. Sur le raccourci **Lignes**, choisissez l'action **Réserver**.
5. Sur la page **Réservation**, sélectionnez la ligne **Ligne vente, commande**, puis sélectionnez l'action **Réserver à partir de la ligne courante**.  

La quantité entrée dans la ligne bon de production planifié ferme est désormais réservée.

## <a name="to-reserve-items-for-production-order-components"></a>Pour réserver des articles pour des composantes bon de production  
Vous pouvez réserver des articles pour des ordres de fabrication. Vous devez distinguer les lignes bon de production, correspondant à l'article parent, et les composantes bon de production.

La procédure suivante se base sur un bon de production planifié ferme.    
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **O.F. planifié ferme**, puis sélectionnez le lien associé.  
2. Ouvrez le bon de production planifié ferme pour lequel vous souhaitez réserver des articles composante.  
3. Sélectionnez la ligne bon de production concernée.  
4. Sur le raccourci **Lignes**, choisissez **Ligne**, puis **Composantes**.  
5. Sélectionnez la ligne composante appropriée.  
6. Dans le raccourci **Lignes**, choisissez l'action **Réserver**.  
7. Sur la page **Réservation**, sélectionnez une ligne, puis sélectionnez l'action **Réserver à partir de la ligne courante**.  

La quantité entrée dans la ligne composante production planifié ferme est désormais réservée.

## <a name="to-change-a-reservation"></a>Pour modifier une réservation  
Vous pouvez être parfois amené à modifier une réservation d'article.   
1. À partir de la ligne document à partir de laquelle vous avez fait la réservation, dans le raccourci **Lignes**, choisissez l'action **Réserver**.  
2. Sur la page **Réservation**, choisissez l'action **Écritures réservation**.
3. Sur la page **Écritures réservation**, mettez à jour le champ **Quantité** de la ligne à modifier.
4. Confirmez le message qui suit en cliquant sur le bouton **OK**.

## <a name="to-cancel-a-reservation"></a>Pour annuler des réservations  
Vous pouvez parfois avoir à annuler une réservation d'article.   
1. À partir de la ligne document à partir de laquelle vous souhaitez annuler une réservation, dans le raccourci **Lignes**, choisissez l'action **Réserver**.  
2. Sur la page **Réservation**, choisissez l'action **Écritures réservation**.  
3.  Sur la page **Écritures réservation**, choisissez l'action **Annuler la réservation**.  
4.  Confirmez le message qui suit en cliquant sur le bouton **OK**.  

## <a name="to-reserve-a-specific-serial-or-lot-number"></a>Pour réserver un numéro de série ou de lot particulier  
À partir des documents sortants pour les articles suivis, comme des documents de vente ou des listes de composantes de production, vous pouvez réserver des numéros de série ou de lot spécifiques. Ceci peut s'avérer utile, par exemple, si vous avez besoin des composants de production d'un lot spécifique pour assurer une cohérence avec des lots de production précédents, ou parce qu'un client demande un numéro de série particulier. Pour plus d'informations, voir [Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md).

Il s'agit d'une réservation spécifique, parce que vous réservez à partir de la quantité de l'article X qui appartient au Lot X. Si vous réservez seulement à partir des quantités de l'article X, la réservation est normale, non spécifique. Pour plus d'informations, reportez-vous à [Détails de conception : traçabilité et réservations](design-details-item-tracking-and-reservations.md).

La procédure suivante se base sur un document de vente.    
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Documents de vente**, puis sélectionnez le lien associé.  
2. Créez une ligne document de vente d'un article suivi.  
3. Affectez des numéros de série et de lot à la ligne document de vente. Pour plus d'informations, voir [Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md).
4. Sur la ligne document de vente, sélectionnez l'action **Réserver**.  
5. Choisissez le bouton **Oui** pour réserver des numéros de série ou de lot spécifiques.  
6. Sur la page **Liste traçabilité**, sélectionnez la combinaison de numéros de série et de lot que vous venez d'affecter.  
7. Cliquez sur le bouton **OK** pour ouvrir une page **Réservation** affichant uniquement l'approvisionnement portant le numéro de traçabilité spécifié. S'il y a des réservations non spécifiques sur l'un des numéros traçabilité que vous avez spécifiés pour cette ligne, vous êtes informé que la quantité a déjà été réservée.  
8. Sélectionnez l'action **Réservation automatique** ou **Réserver à partir de la ligne courante** pour créer la réservation sur les numéros traçabilité spécifiques.

## <a name="see-also"></a>Voir aussi
[Stocks](inventory-manage-inventory.md)  
[Détails de conception : réservation, chaînage et message d'action](design-details-reservation-order-tracking-and-action-messaging.md)  
[Détails de conception : traçabilité et réservations](design-details-item-tracking-and-reservations.md)  
[Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
