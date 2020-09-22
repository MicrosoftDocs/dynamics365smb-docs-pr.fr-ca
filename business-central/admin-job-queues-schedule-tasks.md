---
title: Programmer des projets à exécuter automatiquement | Microsoft Docs
description: Les tâches programmées sont gérées par la file d'attente des travaux. Ces projets exécutent des rapports et des codeunits. Vous pouvez définir des projets à exécuter une fois, ou sur une base récurrente.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 09/09/2020
ms.author: edupont
ms.openlocfilehash: 6816ba11203e697ff833b9ea96aa85139fbcffe9
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3783611"
---
# <a name="use-job-queues-to-schedule-tasks"></a>Utiliser des files d'attente des travaux pour programmer des tâches

Des files d'attente des travaux dans [!INCLUDE[d365fin](includes/d365fin_md.md)] permettent aux utilisateurs de planifier et d'exécuter des états et codeunits spécifiques. Vous pouvez définir des projets à exécuter une fois, ou sur une base récurrente. Par exemple, vous souhaiterez peut-être exécuter le rapport **Statistiques * vente représentant** sur une base hebdomadaire, pour suivre les ventes par représentant chaque semaine, ou exécuter le codeunit **Déléguer les demandes d’approbation** quotidiennement, pour empêcher les documents de s’empiler ou de bloquer le flux de travail.

La page **Écritures file d'attente des travaux** répertorie tous les projets existants. Si vous ajoutez une nouvelle écriture file d'attente des travaux que vous voulez programmer, vous devez spécifier des informations sur le type d'objet à exécuter, par exemple un rapport ou un codeunit, ainsi que le nom et le code de l'objet que vous voulez exécuter. Vous pouvez également ajouter des paramètres pour spécifier le comportement de la file d'attente des travaux. Par exemple, vous pouvez ajouter un paramètre pour envoyer uniquement des documents de vente reportés. Vous devez être autorisé à exécuter le rapport ou le codeunit spécifié, sans quoi une erreur est renvoyée lors de l'exécution de la file d'attente des travaux.  

Une file d'attente des travaux peut comporter plusieurs écritures correspondant aux projets que la file d'attente gère et exécute. Les informations contenues dans les écritures spécifient le codeunit ou le rapport exécuté, la date et le nombre d'exécutions d'une écriture, la catégorie dans laquelle le projet s'exécute et comment il s'exécute.  

## <a name="to-set-up-background-posting-with-job-queues"></a>Pour configurer le report en arrière-plan avec les files d'attente des travaux

Les files d'attente des travaux sont un outil efficace pour programmer l'exécution des processus d'entreprises en arrière-plan, par exemple lorsque plusieurs utilisateurs essaient de reporter des documents de vente, mais uniquement une commande à la fois.  

La procédure suivante explique comment configurer le report en arrière-plan des documents de vente. La procédure est identique pour les achats.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration ventes & à recevoir**, puis sélectionnez le lien associé.
2. Sur la page **Configuration ventes & à recevoir**, activez la case à cocher **Reporter avec la file d'attente des travaux**.
3. Choisissez le champ **Code catégorie de la file d'attente des travaux**, puis spécifiez le code **SALESPOST**.

    > [!NOTE]
    > Certains travaux modifient les données identiques et ne doivent pas s'exécuter en simultané, car cela peut provoquer des conflits. Par exemple, les travaux d'arrière-plan des documents de vente tentent de modifier les données identiques en simultané. Les catégories de file d'attente des travaux permettent d'éviter ces types de conflits en garantissant que lorsqu'un travail est en cours d'exécution, un autre travail appartenant à la même catégorie de file d'attente ne s'exécutera pas avant sa fin. Par exemple, un travail relevant d'une catégorie de file d'attente des travaux de vente attendra que tous les autres travaux liés aux ventes soient terminés. Vous spécifiez une catégorie de file d'attente des travaux sur le raccourci **Report en arrière-plan** sur la page **Configuration ventes & à recevoir**.
    >
    > [!INCLUDE[d365fin](includes/d365fin_md.md)] fournit des catégories de file d'attente des travaux pour les reports au grand livre, les ventes et les achats. Nous recommandons que l'une d'entre elles, ou celle que vous créez, soit toujours spécifiée. Si vous rencontrez des échecs en raison de conflits, pensez à configurer une catégorie pour l'ensemble des reports comptables en arrière-plan, des ventes et des achats.

    Si vous souhaitez également que des documents vente soient imprimés lorsqu'ils sont reportés, sélectionnez la case à cocher **Reporter et imprimer avec la file d'attente des travaux** sur la page **Configuration ventes & à recevoir**.  

    > [!IMPORTANT]  
    > Si vous configurez un projet qui reporte et imprime des documents et que l'imprimante affiche une boîte de dialogue, par exemple une demande d'informations d'identification ou un avertissement à propos de la quantité faible d'encre, votre document est reporté mais non imprimé. L'écriture file d'attente de travaux correspondante expire et la valeur du champ **Statut** devient **Erreur**. Par conséquent, nous vous recommandons de ne pas utiliser une configuration d'imprimante nécessitant une interaction avec les boîtes de dialogue de l'imprimante relatives au report en arrière-plan.

    La prochaine fois que vous reportez des documents de vente, [!INCLUDE [prodshort](includes/prodshort.md)] crée automatiquement une entrée de file d'attente des travaux pour chaque document et exécute les travaux en arrière-plan, un par un.

4. Pour vérifier que la file d'attente des travaux fonctionne comme prévu, reportez un document de vente. Pour en savoir plus, voir [Vendre des produits](sales-how-sell-products.md).

5. Vérifiez sur la page **Écritures journal file d'attente des travaux** si le document de vente a été reporté avec succès. Pour plus d'informations, voir [Pour afficher l'état ou les erreurs dans la file d'attente](admin-job-queues-schedule-tasks.md#to-view-status-or-errors-in-the-job-queue).

## <a name="to-create-a-job-queue-entry-for-batch-posting-of-sales-orders"></a>Pour créer une écriture file d'attente des travaux pour le report en lot des documents de vente

Sinon, vous pouvez reporter les reports à des heures pratiques pour votre organisation. Par exemple, il peut sembler raisonnable dans votre activité d’exécuter certaines routines lorsque la plupart de la saisie de données de la journée est achevée. Vous pouvez effectuer cette opération en configurant la file d'attente des travaux pour exécuter différents rapports de report en lot, par exemple, **Reporter en lot documents de vente**, **Reporter en lot factures vente** et des rapports similaires. [!INCLUDE[d365fin](includes/d365fin_md.md)] prend en charge le report en arrière-plan de tous les documents de types ventes, achats et service.

La procédure suivante décrit comment définir le rapport **Reporter en lot documents de vente** pour un report automatique des documents de vente lancés à 16 h 00 les jours de semaine.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Écritures file d'attente des travaux**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Type objet à exécuter**, sélectionnez **Rapport**.  
4. Dans le champ **Code objet à exécuter**, sélectionnez 296, **Reporter en lot des documents de vente**.

   Vous pouvez également utiliser les rapports suivants :
  
   * 900 **Reporter en lot ordres d’assemblage**
   * 497 **Reporter en lot factures achat**
   * 496 **Reporter en lot bons de commande**
   * 498 **Reporter en lot notes de crédit achat**
   * 6665 **Reporter en lot retours achat**
   * 298 **Reporter en lot notes de crédit vente**
   * 297 **Reporter en lot factures vente**
   * 296 **Reporter en lot documents de vente**
   * 6655 **Reporter en lot retours vente**
   * 6005 **Reporter en lot notes de crédit service**
   * 6004 **Reporter en lot factures service**
   * 6001 **Reporter en lot Commandes service**

5. Activez la case à cocher **Page requête rapport**.
6. Dans la page de demande **Reporter en lot des documents de vente**, définissez ce qu'il faut inclure lors du report automatique des documents de vente, puis sélectionnez le bouton **OK**.

    > [!IMPORTANT]
    > N’oubliez pas de définir des filtres stricts ; sinon, [!INCLUDE [prodshort](includes/prodshort.md)] affichera tous les documents, même s’ils ne sont pas prêts. Pensez à définir un filtre sur le champ **État** pour la valeur *Libéré*, et un filtre sur le champ **Date de report** pour la valeur *..aujourd’hui*. Pour plus d’informations, voir [Tri, recherche et filtrage](ui-enter-criteria-filters.md).
7. Activez toutes les cases à cocher de **Exécuter le lundi** à **Exécuter le vendredi**.
8. Dans le champ **Heure début**, entrez 16 h 00.
9. Choisissez l'action **Attribuer l'état Prêt**.

Les documents de vente dans les filtres définis sont à présent reportés chaque jour de la semaine à 16 h 00.

> [!NOTE]
> Si la file d'attente des travaux ne peut pas reporter le document de vente, l'état passe à **Erreur**, et le document de vente est ajouté à la liste des documents de vente que l'utilisateur doit traiter. Pour plus d'informations, voir [Pour afficher l'état ou les erreurs dans la file d'attente](admin-job-queues-schedule-tasks.md#to-view-status-or-errors-in-the-job-queue).

Une fois les files d'attente des travaux configurées et en cours d'exécution, l'état peut être modifié comme suit au cours de chaque période récurrente :

* **En attente**  
* **Prêt**  
* **En cours**  
* **Erreur**  
* **Terminé**  

Une fois qu'un projet s'est terminé correctement, il est supprimé de la liste des écritures file d'attente des travaux, sauf en cas de projet récurrent. S'il s'agit d'un projet récurrent, le champ **Heure de début (au plus tôt)** est ajusté pour afficher la prochaine heure d'exécution planifiée pour le projet.  

## <a name="to-view-status-or-errors-in-the-job-queue"></a>Pour visualiser l'état ou les erreurs dans la file d'attente des travaux
Les données qui sont générées lors de l'exécution d'une file d'attente des travaux sont stockées dans la base de données, de sorte que vous puissiez résoudre les erreurs de la file d'attente des travaux.

### <a name="to-view-status-for-any-job"></a>Pour visualiser l'état de tous les travaux
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Écritures file d'attente des travaux**, puis sélectionnez le lien associé.
2. Sur la page **Écritures file d'attente des travaux**, sélectionnez une écriture file d'attente des travaux, puis sélectionnez l'action **Écritures journal**.  

### <a name="to-view-status-from-a-sales-or-purchase-document"></a>Pour afficher l'état à partir d'un document vente ou achat
1. Dans le document que vous avez essayé de reporter avec le report en arrière-plan, choisissez le champ **État de la file d'attente des travaux**, qui contient **Erreur**.
2. Examinez le message d’erreur et résolvez le problème.

## <a name="the-my-job-queue-part"></a>Composant Ma file d'attente des travaux
Le composant **Ma file d'attente des travaux** sur votre Tableau de bord répertorie les écritures files d'attente des travaux que vous avez commencées, mais qui ne sont pas encore terminées. Par défaut, le composant n'est pas visible et vous devez donc l'ajouter à votre tableau de bord. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).  

Le composant indique les documents avec votre code dans le champ **Code utilisateur affecté** qui sont en cours de traitement ou en attente, y compris ceux associés au report en arrière-plan. La composante peut vous indiquer rapidement s’il y a eu une erreur lors du report d’un document ou s’il existe des erreurs dans une écriture de file d'attente projet. Elle vous permet également d'annuler un report de document en cas de non-exécution.

### <a name="to-view-an-error-from-the-my-job-queue-part"></a>Pour afficher une erreur dans le composant Ma file d'attente des travaux
1. Sur une écriture ayant l'état **Erreur**, sélectionnez l'action **Afficher erreur**.
2. Examinez le message d’erreur et résolvez le problème.

## <a name="security"></a>Sécurité  
Les écritures file d'attente des travaux s'exécutent sur la base d'autorisations. Ces autorisations doivent permettre l'exécution du rapport ou du codeunit.  

Lorsqu'une file d'attente des travaux est activée manuellement, elle s'exécute avec les informations d'identification de l'utilisateur. Lorsqu'une file d'attente des travaux est activée en tant que tâche programmée, elle s'exécute avec les informations d'identification de l'instance du serveur. Un projet s'exécute avec les informations d'identification de la file d'attente des travaux qui l'active. L'utilisateur qui a créé cette écriture file d'attente des travaux doit toutefois disposer d'autorisations. Lorsqu’un projet est « exécuté dans la session utilisateur » (par exemple, durant le report en arrière-plan), il est exécuté avec les informations d’identification de l’utilisateur qui a créé ce projet.  

> [!IMPORTANT]  
> Si vous utilisez l'ensemble d'autorisations SUPER qui est fourni avec [!INCLUDE[d365fin](includes/d365fin_md.md)], les utilisateurs et vous-même disposez des autorisations pour exécuter tous les objets. Dans ce cas, l'accès accordé à chaque utilisateur est uniquement limité par les autorisations relatives aux données.  

## <a name="using-job-queues-effectively"></a>Utilisation efficace des files d'attente des travaux  
L'enregistrement des écritures file d'attente des travaux possède plusieurs champs dont l'objectif est d'exécuter des paramètres dans un codeunit que vous avez indiqué comme devant être exécuté avec une file d'attente des travaux. Cela signifie également que les codeunits devant être exécutés via la file d'attente des travaux doivent être indiqués avec l'enregistrement des écritures file d'attente des travaux en tant que paramètre dans le déclencheur **OnRun**. Un niveau de sécurité supplémentaire est ainsi assuré, car les utilisateurs ne peuvent pas exécuter de codeunits aléatoires via la file d'attente des travaux. Si l'utilisateur doit transmettre des paramètres à un rapport, il n'a d'autre choix que celui d'inclure l'exécution du rapport dans un codeunit, lequel analyse ensuite les paramètres d'entrée et les intègre dans le rapport avant de l'exécuter.  

## <a name="scheduling-synchronization-between-d365fin-and-d365fin"></a>Planification de la synchronisation entre [!INCLUDE[d365fin](includes/d365fin_md.md)] et [!INCLUDE[d365fin](includes/cds_long_md.md)]

Si vous avez intégré [!INCLUDE[d365fin](includes/d365fin_md.md)] à [!INCLUDE[d365fin](includes/cds_long_md.md)], vous pouvez utiliser la file d'attente des travaux pour programmer à quel moment vous souhaitez synchroniser les données des enregistrements que vous avez couplés dans les deux applications métier. Selon la direction et les règles que vous avez définies pour l’intégration, les tâches de synchronisation peuvent également créer des enregistrements dans l’application de destination pour correspondre à ceux de la source. Par exemple, si un représentant crée un contact dans [!INCLUDE[crm_md](includes/crm_md.md)], la tâche de synchronisation peut créer ce contact pour le représentant couplé dans [!INCLUDE[d365fin](includes/d365fin_md.md)]. Pour plus d’informations, voir [Planification d’une synchronisation entre Business Central et Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

## <a name="see-also"></a>Voir aussi

[Administration](admin-setup-and-administration.md)  
[Configuration de Business Central](setup.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
