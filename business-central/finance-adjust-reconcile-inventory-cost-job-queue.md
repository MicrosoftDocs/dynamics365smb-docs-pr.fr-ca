---
title: Ajuster et rapprocher le coût avec le grand livre à l’aide de la file d’attente des travaux
description: Découvrez comment vous pouvez utiliser la file d’attente des travaux pour déplacer les tâches d’ajustement du coût de l’inventaire ou de rapprochement avec le grand livre en arrière-plan. Par exemple, si votre compagnie exécute de nombreuses tâches ou traite de nombreuses transactions.
author: AndreiPanko
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.reviewer: edupont
ms.date: 07/28/2021
ms.author: andreipa
ms.openlocfilehash: e44936d9d9ec39d9232285d7293c152c57ab0a56
ms.sourcegitcommit: 769d20d299155cba30c35636d02b2ef021e4ecc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/29/2021
ms.locfileid: "6688473"
---
# <a name="adjust-and-reconcile-inventory-cost-with-general-ledger-with-job-queue"></a>Ajuster et rapprocher le coût de l’inventaire avec le grand livre avec la file d’attente des travaux

Pour optimiser l’expérience, l’ajustement automatique des coûts et le report dans le grand livre sont activés par défaut. Cependant, à mesure que les données s’accumulent au fil du temps, cela peut affecter les performances. Pour réduire la charge de l’application, il est souvent utile d’utiliser les écritures file d’attente des travaux pour déplacer les tâches à exécuter en arrière-plan.

## <a name="move-the-task-of-adjusting-item-costs-to-the-background-with-the-help-of-assisted-setup"></a>Déplacez la tâche d’ajustement des coûts article en arrière-plan à l’aide de la configuration assistée

La création des écritures file d’attente des travaux peut être compliquée, même pour un consultant expérimenté; par conséquent, nous avons un guide de configuration assistée pour faciliter le processus d’ajustement des coûts article. 

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration inventaire**, puis sélectionnez le lien associé.  
2. Dans la page **Configuration inventaire**, activez le champ **Report coûts automatique** ou spécifiez **Jamais** dans le champ **Ajustement automatique des coûts**.  
3. Dans la notification qui s’affiche maintenant en haut de la page, choisissez le lien **Programmer écriture file d’attente des travaux**.
4. Spécifiez la tâche que vous souhaitez programmer.  

  > [!NOTE]
  > Vous ne pouvez pas créer une nouvelle écriture file d’attente des travaux si une écriture file d’attente des travaux pour la tâche spécifiée existe déjà. 
5. Sélectionnez le champ **Afficher les écritures file d’attente des travaux quand vous avez terminé** pour réviser et ajuster les paramètres. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

## <a name="to-create-a-job-queue-entry-for-adjusting-and-reconciling-inventory-cost-manually"></a>Pour créer une écriture file d’attente des travaux pour ajuster et rapprocher manuellement le coût de l’inventaire

Vous pouvez également créer des écritures file d’attente des travaux manuellement. La procédure suivante montre comment définir le traitement en lot **Ajuster coût écritures article** pour s’exécuter automatiquement chaque jour, mais les mêmes étapes s’appliquent au traitement en lot **Reporter le coût de l’inventaire au grand livre**. 

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Écritures file d'attente des travaux**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Type objet à exécuter**, choisissez *Rapport*.  
4. Dans le champ **Code objet à exécuter**, choisissez *795*, **Ajuster coût écritures article**.  
5. Dans le champ **Formule de la date de la prochaine exécution**, entrez *1D*.
6. Dans le champ **Heure début**, entrez *14h00*.
7. Choisissez l'action **Attribuer l'état Prêt**.

Maintenant, le coût de l’inventaire sera mis à jour toutes les nuits.  

Pour programmer une tâche de rapprochement de l’inventaire avec le grand livre, choisissez Codeunit 2846 **Reporter le coût de l’inventaire au grand livre**.


> [!NOTE]
> Pour éviter le verrouillage, ne programmez pas de tâches pour le traitement en lot **Ajuster coût écritures article**, le codeunit **Reporter le coût de l’inventaire au grand livre** et les tâches de report des transactions de vente ou d’achat en même temps, et assurez-vous qu’ils utilisent la même catégorie de file d’attente des travaux.

## <a name="see-also"></a>Voir aussi

[Ajuster coûts et prix article](inventory-how-adjust-item-costs.md)  
[Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
