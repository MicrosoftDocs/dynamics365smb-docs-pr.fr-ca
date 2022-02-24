---
title: Comment reporter plusieurs documents en même temps | Microsoft Docs
description: Au lieu de reporter des documents individuels un par un, vous pouvez sélectionner plusieurs documents non reportés dans une liste afin de les reporter en lot, soit pour un report immédiat, soit pour un report programmé, par exemple, à la fin de la journée.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 32998248de254facdb225d60a0c8b55066b2707c
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3192109"
---
# <a name="post-multiple-documents-at-the-same-time"></a>Reporter plusieurs documents en même temps
Au lieu de reporter des documents individuels un par un, vous pouvez sélectionner plusieurs documents non reportés dans une liste pour un report immédiat ou un report en lot, conformément à une programmation, à la fin de la journée, par exemple. Cela peut être utile si seul un superviseur peut reporter des documents créés par d'autres utilisateurs ou pour éviter des problèmes de performance du système liés au report pendant les heures de travail.

## <a name="to-post-multiple-purchase-orders-immediately"></a>Pour reporter plusieurs bons de commande immédiatement
La procédure suivante explique comment reporter immédiatement plusieurs bons de commande. Les étapes sont similaires pour tous les documents achat et vente.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.
2. Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :
3. Dans le champ **N°**, choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.
4. Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.
5. Choisissez l'action **Report**, puis sélectionnez l'action **Reporter**.
6. Choisissez le bouton **Oui** dans le message de confirmation.

## <a name="to-batch-post-multiple-purchase-orders"></a>Pour exécuter en lot plusieurs bons de commande
La procédure suivante explique comment exécuter en lot plusieurs bons de commande. Les étapes sont similaires pour tous les documents achat et vente où l'action **Exécuter en lot** est disponible.

> [!NOTE]
> Le report en lot de documents s'effectue en arrière-plan, comme défini par une entrée de file d'attente des travaux, qui doit d'abord être configurée. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Bons de commande**, puis sélectionnez le lien associé.  
2. Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :
3. Dans le champ **N°**, choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.
4. Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.
5. Choisissez l'action **Report**, puis sélectionnez l'action **Reporter en lot**.
6. Sur la page **Exécuter en lot les bons de commande**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > Pour imprimer des rapports associés lors du report, tels que le rapport **Confirmation de commande** pour les documents de vente, sélectionnez la case à cocher **Imprimer**.<br /><br /> Dans le champ **Type sortie rapport** sur la page **Configuration ventes** ou **Configuration achats**, définissez si le rapport sera imprimé ou émis au format PDF.<br /><br /> Notez également que l'impression directe sur une imprimante sélectionnée n'est possible que dans les installations locales uniquement.

7. Choisissez le bouton **OK**.
8. Pour afficher les problèmes potentiels survenus lors du report en lot de documents, ouvrez la page **Registre des messages d'erreur**.

Les bons de commande seront désormais ajoutés à une entrée de file d'attente des travaux dédiée, qui définit le moment où les documents sont reportés. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

Si vous sélectionnez **PDF** dans le champ **Type sortie rapport**, les bons de commande reportés avec succès seront disponibles dans la partie **boîte de réception rapport** de votre tableau de bord.

## <a name="see-also"></a>Voir aussi
[Validation des documents et des feuilles](ui-post-documents-journals.md)  
[Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md)  
[Modifier les documents reportés](across-edit-posted-document.md)  
[Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
