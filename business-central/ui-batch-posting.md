---
title: Reporter plusieurs documents en même temps
description: Découvrez comment sélectionner plusieurs documents non reportés dans une liste pour un report par lots immédiat ou programmé dans Business Central.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: null
ms.reviewer: bholtorf
ms.date: 06/25/2021
ms.author: bholtorf
---
# Reporter plusieurs documents en même temps

Au lieu de reporter des documents individuels un par un, vous pouvez sélectionner plusieurs documents non reportés dans une liste pour un report immédiat ou un report en lot, conformément à une programmation, à la fin de la journée, par exemple. Cela peut être utile si seul un superviseur peut reporter des documents créés par d'autres utilisateurs ou pour éviter des problèmes de performance du système liés au report pendant les heures de travail.

## Pour reporter plusieurs bons de commande immédiatement

La procédure suivante explique comment reporter immédiatement plusieurs bons de commande. Les étapes sont similaires pour tous les documents achat et vente.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de commande**, puis choisissez le lien associé.
2. Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :
3. Dans le champ **N°**, choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.
4. Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.
5. Choisissez l'action **Report**, puis sélectionnez l'action **Reporter**.
6. Choisissez le bouton **Oui** dans le message de confirmation.

## Pour reporter en lot plusieurs bons de commande

La procédure suivante explique comment reporter en lot des bons de commande. Les étapes sont similaires pour tous les documents achat et vente où l’action **Reporter en lot** est disponible.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Bons de commande**, puis choisissez le lien associé.  
2. Sur la page **Bons de commande**, sélectionnez toutes les commandes à reporter :
3. Dans le champ **N°**, choisissez les trois points verticaux pour ouvrir le menu contextuel, puis choisissez l'action **Sélectionner davantage**.
4. Cochez la case pour toutes les lignes représentant les commandes que vous souhaitez reporter en même temps.
5. Choisissez l'action **Report**, puis sélectionnez l'action **Reporter en lot**.
6. Sur la page **Reporter en lot les bons de commande**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choisissez le bouton **OK**.
8. Pour afficher les problèmes potentiels survenus lors du report en lot de documents, ouvrez la page **Registre des messages d'erreur**.

> [!NOTE]
> Le report de plusieurs documents peut prendre un certain temps et bloquer d’autres utilisateurs. Envisagez d’activer le report en arrière-plan. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## Pour configurer le report en arrière-plan avec les files d'attente des travaux
Les files d'attente des travaux sont un outil efficace pour programmer l'exécution des processus d'entreprises en arrière-plan, par exemple lorsque plusieurs utilisateurs essaient de reporter des documents de vente, mais uniquement une commande à la fois.  

La procédure suivante explique comment configurer le report en arrière-plan des documents de vente. La procédure est identique pour les achats.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Configuration ventes & à recevoir**, puis choisissez le lien associé.
2. Sur la page **Configuration ventes & à recevoir**, activez la case à cocher **Reporter avec la file d'attente des travaux**.
3. Choisissez le champ **Code catégorie de la file d'attente des travaux**, puis spécifiez le code **SALESPOST**.

    > [!NOTE]
    > Certains travaux modifient les données identiques et ne doivent pas s'exécuter en simultané, car cela peut provoquer des conflits. Par exemple, les travaux d'arrière-plan des documents de vente tentent de modifier les données identiques en simultané. Les catégories de file d'attente des travaux permettent d'éviter ces types de conflits en garantissant que lorsqu'un travail est en cours d'exécution, un autre travail appartenant à la même catégorie de file d'attente ne s'exécutera pas avant sa fin. Par exemple, un travail relevant d'une catégorie de file d'attente des travaux de vente attendra que tous les autres travaux liés aux ventes soient terminés. Vous spécifiez une catégorie de file d'attente des travaux sur le raccourci **Report en arrière-plan** sur la page **Configuration ventes & à recevoir**.
    >
    > [!INCLUDE[prod_short](includes/prod_short.md)] fournit des catégories de file d'attente des travaux pour les reports au grand livre, les ventes et les achats. Nous recommandons que l'une d'entre elles, ou celle que vous créez, soit toujours spécifiée. Si vous rencontrez des échecs en raison de conflits, pensez à configurer une catégorie pour l'ensemble des reports comptables en arrière-plan, des ventes et des achats.

    Si vous souhaitez également que des documents vente soient imprimés lorsqu'ils sont reportés, sélectionnez la case à cocher **Reporter et imprimer avec la file d'attente des travaux** sur la page **Configuration ventes & à recevoir**.  
    Si vous sélectionnez **PDF** dans le champ **Type sortie rapport**, les bons de commande reportés avec succès seront disponibles dans la partie **boîte de réception rapport** de votre tableau de bord.

    > [!IMPORTANT]  
    > Si vous configurez un projet qui reporte et imprime des documents et que l'imprimante affiche une boîte de dialogue, par exemple une demande d'informations d'identification ou un avertissement à propos de la quantité faible d'encre, votre document est reporté mais non imprimé. L'écriture file d'attente de travaux correspondante expire et la valeur du champ **Statut** devient **Erreur**. Par conséquent, nous vous recommandons de ne pas utiliser une configuration d'imprimante nécessitant une interaction avec les boîtes de dialogue de l'imprimante relatives au report en arrière-plan.

    La prochaine fois que vous reportez des documents de vente, [!INCLUDE [prod_short](includes/prod_short.md)] crée automatiquement une entrée de file d'attente des travaux pour chaque document et exécute les travaux en arrière-plan, un par un.

4. Pour vérifier que la file d'attente des travaux fonctionne comme prévu, reportez un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).
    Les documents de vente seront désormais ajoutés à une entrée file d'attente des travaux dédiée, qui définit le moment où les documents sont reportés. 

### Pour afficher l'état à partir d'un document vente ou achat
Si la file d'attente des travaux ne peut pas reporter le document de vente, l'état passe à **Erreur**, et le document de vente est ajouté à la liste des documents de vente que l'utilisateur doit traiter.
1. Dans le document que vous avez essayé de reporter avec le report en arrière-plan, choisissez le champ **État de la file d'attente des travaux**, qui contient **Erreur**.
2. Examinez le message d’erreur et résolvez le problème.

Sinon, vous pouvez vérifier sur la page **Écritures journal file d’attente des travaux** si le document de vente a été reporté avec succès. Pour plus d’informations, consultez la section [Surveiller la file d’attente des travaux](#monitor-the-job-queue).

## Pour créer une écriture file d'attente des travaux pour le report en lot des documents de vente

Sinon, vous pouvez reporter les reports à des heures pratiques pour votre organisation. Par exemple, il peut sembler raisonnable dans votre activité d’exécuter certaines routines lorsque la plupart de la saisie de données de la journée est achevée. Vous pouvez effectuer cette opération en configurant la file d'attente des travaux pour exécuter différents rapports de report en lot, par exemple, **Reporter en lot documents de vente**, **Reporter en lot factures vente** et des rapports similaires. [!INCLUDE[prod_short](includes/prod_short.md)] prend en charge le report en arrière-plan de tous les documents de types ventes, achats et service.

La procédure suivante décrit comment définir le rapport **Reporter en lot des documents de vente** pour un report automatique des documents de vente lancés à 16 h 00 les jours de semaine.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures file d’attente des travaux**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Type objet à exécuter**, sélectionnez **Rapport**.  
4. Dans le champ **Code objet à exécuter**, sélectionnez 296, **Reporter en lot des documents de vente**.

   Vous pouvez également utiliser les rapports suivants :
  
   * 900 **Reporter en lot des ordres d’assemblage**
   * 497 **Reporter en lot des factures achat**
   * 496 **Reporter en lot des bons de commande**
   * 498 **Reporter en lot des notes de crédit achat**
   * 6665 **Reporter en lot des retours achat**
   * 298 **Reporter en lot des notes de crédit vente**
   * 297 **Reporter en lot des factures vente**
   * 296 **Reporter en lot des documents de vente**
   * 6655 **Reporter en lot des retours vente**
   * 6005 **Reporter en lot des notes de crédit service**
   * 6004 **Reporter en lot des factures service**
   * 6001 **Reporter en lot des commandes service**

5. Activez la case à cocher **Page requête rapport**.
6. Dans la page de demande **Reporter en lot des documents de vente**, définissez ce qu’il faut inclure lors du report automatique des documents de vente, puis sélectionnez le bouton **OK**.

    > [!IMPORTANT]
    > N’oubliez pas de définir des filtres stricts ; sinon, [!INCLUDE [prod_short](includes/prod_short.md)] affichera tous les documents, même s’ils ne sont pas prêts. Pensez à définir un filtre sur le champ **État** pour la valeur *Libéré*, et un filtre sur le champ **Date de report** pour la valeur *..aujourd’hui*. Pour plus d’informations, voir [Tri, recherche et filtrage](ui-enter-criteria-filters.md).
7. Activez toutes les cases à cocher de **Exécuter le lundi** à **Exécuter le vendredi**.
8. Dans le champ **Heure début**, entrez 16 h 00.
9. Choisissez l'action **Attribuer l'état Prêt**.

Les documents de vente dans les filtres définis sont à présent reportés chaque jour de la semaine à 16 h 00.

## Surveiller la file d’attente des travaux

Si vous configurez le report en arrière-plan avec les files d’attente des travaux, convertissez-le en une tâche périodique pour surveiller la file d’attente des travaux et détecter les éventuels problèmes. Vous pouvez suivre l’état dans la page **Écritures file d’attente des travaux**. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

En tant qu’administrateur, vous pouvez utiliser [Application Insights](/azure/azure-monitor/app/app-insights-overview) pour recueillir et analyser la télémétrie que vous pouvez utiliser pour identifier les problèmes. Pour plus d’informations, consultez [Surveillance et analyse de la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) dans le contenu pour développeurs et administrateurs.  

## Voir aussi

[Validation des documents et des feuilles](ui-post-documents-journals.md)  
[Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md)  
[Modifier les documents reportés](across-edit-posted-document.md)  
[Corriger ou annuler des factures achat impayées](purchasing-how-correct-cancel-unpaid-purchase-invoices.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]