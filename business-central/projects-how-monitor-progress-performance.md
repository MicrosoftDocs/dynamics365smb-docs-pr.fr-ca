---
title: "Définir une méthode TEC et surveiller la progression du projet | Microsoft Docs"
description: "Décrit la manière dont vous pouvez créer une méthode de travaux en cours (TEC) et calculer les TEC pour estimer la valeur financière des projets lorsqu'ils sont en cours."
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: project management, KPI, work in process, work in progress
ms.date: 10/01/2018
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: 9dbd92409ba02281f008246194f3ce0c53e4e001
ms.openlocfilehash: 065f6cc5dc11af1a9cddf2b3eed2b20e99912960
ms.contentlocale: fr-ca
ms.lasthandoff: 09/28/2018

---
# <a name="monitor-job-progress-and-performance"></a>Surveiller la progression et les performances
Au fur et à mesure de la progression du projet, les matières, ressources et autres frais sont consommés et doivent être reportés dans le projet. La fonctionnalité Travaux en cours (TEC) permet d'estimer la valeur financière des projets dans le grand livre au cours des projets. Dans de nombreux cas, vous pouvez reporter les frais pour un projet avant de le facturer. Lorsque seuls les frais sont reportés, l'état financier est incorrect. Pour en savoir plus, reportez-vous à [Comprendre les méthodes TEC](projects-understanding-wip.md).

Pour effectuer le suivi de la valeur dans le grand livre, vous pouvez calculer les TEC et reporter la valeur dans le grand livre.

Vous pouvez calculer les TEC sur la base des éléments suivants :

* Valeur de coût
* Valeur des ventes
* Coût identifiable
* Pourcentage d'achèvement
* Contrat complété

Pour afficher le résultat avec une autre méthode, vous pouvez modifier la méthode et calculer les TEC de nouveau. Le calcul des TEC peut être exécuté un nombre illimité de fois. Le TEC est uniquement calculé, il n'est pas reporté dans le grand livre. Une fois les TEC calculés, vous pouvez effectuer un report dans le grand livre.

## <a name="to-create-a-job-wip-method"></a>Pour créer une méthode TEC projet
Vous pouvez créer une méthode TEC projet qui reflète les besoins de votre organisation. Après l'avoir créée, vous pouvez la configurer comme méthode par défaut de calcul TEC projet qui sera utilisée dans votre organisation.  

> [!NOTE]
> Après avoir utilisé la nouvelle méthode pour créer des écritures TEC, vous ne pouvez pas supprimer la méthode ou la modifier.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Méthodes TEC projet**, puis choisissez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  
3. Fermez la fenêtre.   
4. Pour que cette nouvelle méthode devienne celle par défaut, choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration projets**, puis sélectionnez le lien associé.  
5. Dans le champ **Méthode TEC par défaut**, choisissez la méthode de la liste.

## <a name="to-define-a-wip-method-for-a-job"></a>Pour définir une méthode TEC pour un projet
Lorsque vous créez un projet, vous devez spécifier la méthode TEC projet qui s'applique. Dans certains cas, quelle méthode TEC projet utilisable a été paramétrée pour vous par défaut.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projets**, puis sélectionnez le lien associé.
2. Sélectionnez l'action **Nouveau**. Pour plus d'informations, voir [Créer des projets](projects-how-create-jobs.md).  
3. Dans la fenêtre **Fiche projet**, dans le champ **Méthode TEC**, sélectionnez une méthode TEC dans la liste. Si une méthode par défaut a été définie, vous pouvez sélectionner une autre option si nécessaire.  

## <a name="to-calculate-wip"></a>Pour calculer les TEC :
Vous pouvez déterminer le montant TEC devant être reporté dans les comptes de bilan pour la génération de rapports de fin d'exercice. Pour ce faire, utilisez le traitement par lots **Projet Calculer TEC**.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projet Calculer TEC**, puis choisissez le lien associé.  
2. Cliquez sur **Calculer TEC**.
3. Dans la fenêtre **Projet Calculer TEC**, renseignez les champs comme nécessaire.
4. Cliquez sur le bouton **OK**.  

> [!NOTE]  
>   Le traitement en lot calcule uniquement les TEC. Il n'est pas reporté dans le grand livre. Pour ce faire, exécutez le traitement par lots **Valider TEC en compta.** à l'issue du calcul. Pour plus d'informations, voir la procédure suivante.

## <a name="to-post-wip"></a>Pour reporter les TEC
Quand vous avez calculé les TEC, vous pouvez les reporter pour équilibrer les comptes bilan pour le rapport de fin de période. Pour ce faire, utilisez le traitement par lots **Projet Valider TEC en comptabilité**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Projet - Reporter TEC au GL**, puis sélectionnez le lien associé.  
2. Dans la fenêtre **Projet Valider TEC en comptabilité**, renseignez les champs selon vos besoins.  
3. Cliquez sur le bouton **OK**.

## <a name="to-view-job-usage-estimates-and-post-updates"></a>Pour visualiser les estimations projet et reporter les mises à jour
Vous pouvez visualiser les utilisations projet jusqu'à leur achèvement en une étape. Pour ce faire, utilisez le traitement par lots **Projet Calc. activité restante** pour toutes les tâches jusqu'à la fin du projet.  

Cela vous permet de suivre vos estimations initiales, de les comparer aux résultats réels, ainsi que d'apporter des modifications et d'ajouter de nouvelles écritures, selon les besoins. Par exemple, alors que vous aviez estimé qu'un projet nécessitait 10 heures de travail, vous en avez effectué 15. Vous pouvez ajouter les cinq heures supplémentaires à la ligne journal existante ou créer une ligne journal pour les déclarer en tant qu'heures supplémentaires, ce qui constitue un autre type de tâche. Le coût et le prix appropriés sont calculés. Vous pouvez les reporter dans le journal.  

> [!NOTE]  
>   Les écritures article créent des écritures article et diminuent la quantité de l'inventaire. Le traitement par lots **Valider coûts ajustés** permet de transférer le coût du stock à la comptabilité. Les écritures ressource créent des écritures ressource.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journaux projet**, puis sélectionnez le lien associé.  
2. Sélectionnez une feuille projet appropriée, puis cliquez sur l'action **Calc. activité restante**.  
3. Dans la fenêtre **Projet Calc. activité restante**, entrez le numéro et la date de comptabilisation du document devant être insérés dans la feuille, puis sélectionnez le bouton **OK**.  
4. Mettez à jour le journal avec toutes les modifications qui peuvent être nécessaires.  
5. Sélectionnez l'action **Valider**.

## <a name="to-view-job-ledger-entries"></a>Pour visualiser des écritures projet
Toutes les écritures liées à des projets sont enregistrées dans des historiques des transactions projet et sont numérotées de manière séquentielle à partir de 1. Le registre de projet permet d'obtenir un aperçu de toutes les écritures projet.    

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Registres de projet**, puis sélectionnez le lien associé.
2. Sélectionnez un historique approprié, puis cliquez sur **Écritures projet**

Dans la fenêtre **Écritures comptables projet** vous pouvez passer en revue les écritures associées à un projet.  

## <a name="see-also"></a>Voir aussi
[Gestion des projets](projects-manage-projects.md)
[Gestion de l'évaluation stock](finance-manage-inventory-costs.md)   
[Finance](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)         
[Vente](sales-manage-sales.md)      
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  

