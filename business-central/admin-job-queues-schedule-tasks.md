---
title: Programmer des projets à exécuter automatiquement
description: Découvrez comment utiliser les entrées de la file d’attente des tâches pour exécuter des rapports et des codeunits.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 07/16/2024
ms.custom: bap-template
ms.search.form: '672, 673, 674, 671'
ms.service: dynamics-365-business-central
---
# <a name="use-job-queues-to-schedule-tasks"></a>Utiliser des files d’attente de projets pour programmer des tâches

Utiliser la page **Écritures file d’attente des travaux** permet aux utilisateurs de programmer et d’exécuter des rapports et codeunits spécifiques. Vous pouvez définir des projets à exécuter une fois, ou sur une base récurrente. Par exemple, vous souhaiterez peut-être exécuter le rapport **Statistiques vente * représentant** sur une base hebdomadaire, pour suivre les ventes par représentant chaque semaine, ou exécuter le codeunit **Déléguer les demandes d’approbation** quotidiennement, pour empêcher les documents de s’empiler ou de bloquer le flux de travail.

La page **Écritures file d'attente des travaux** répertorie tous les projets existants. Si vous ajoutez une écriture file d’attente des projets qui s’exécute selon un calendrier, vous devez fournir certaines informations. Par exemple :

* Le type d’objet à exécuter, tel qu’un rapport ou une codeunit. Vous devez être autorisé à exécuter le rapport ou la codeunit.
* Le nom et le code objet de l’objet.
* Les paramètres pour spécifier le comportement de la file d’attente des travaux. Par exemple, vous pouvez ajouter un paramètre pour envoyer uniquement des documents de vente reportés.
* Calendrier définissant le moment et la fréquence d’exécution de l’écriture file d’attente des projets.

> [!IMPORTANT]  
> Si vous bénéficiez de l’ensemble d’autorisations SUPER qui est fourni avec [!INCLUDE[prod_short](includes/prod_short.md)], vous disposez des autorisations pour exécuter tous les objets inclus dans votre licence. Si vous disposez du rôle Administrateur délégué, vous pouvez créer et programmer des écritures file d’attente des projets, mais seuls les administrateurs et les utilisateurs possédant une licence peuvent les exécuter.

Après la fin réussie d'un projet, [!INCLUDE [prod_short](includes/prod_short.md)] le supprime de la liste d’écritures file d’attente des projets, sauf s'il s'agit d'un projet récurrent. Pour les travaux récurrents, le champ **Heure de début (au plus tôt)** est ajusté pour afficher la prochaine heure d’exécution du projet.

## <a name="important-for-scheduling-recurring-jobs"></a>Important pour planifier des tâches récurrentes

> [!IMPORTANT]  
> Les files d’attente des travaux récurrents peuvent affecter les performances, vous ne devez donc pas les exécuter trop fréquemment. Lorsque vous configurez la fréquence d’exécution d’une tâche récurrente, essayez de définir l’intervalle de temps le plus grand possible. Par exemple, si vous êtes sur le point de définir une récurrence de cinq minutes, demandez-vous si elle peut être de 15 minutes, ou même d’une fois par heure. Lors de la planification de files d’attente des travaux récurrents, réfléchissez quels domaines de l’application seront concernés par le travail. Est-ce un domaine où travaillent de nombreux utilisateurs et qui sera impacté par une forte activité ? Tenez compte de la durée d’une seule exécution de tâche et des motivations commerciales pour exécuter des tâches à une cadence donnée.

## <a name="the-earliest-start-date"></a>Date début au plus tôt

La valeur du champ **Date/heure de début au plus tôt** sur la page **Fiche écriture file d’attente des projets** indique la prochaine fois que le projet sera exécuté. Plusieurs facteurs peuvent affecter l’exécution réelle d’une écriture file d’attente des projets à ce moment-là.

Les facteurs les plus courants sont le nombre d’écritures file d’attente des projets dans un environnement et le nombre total de tâches programmées. Pour protéger les niveaux de performances, il existe des limites opérationnelles. Si vous avez beaucoup d’écritures et, par exemple, l’une d’entre elles échoue ou prend plus de temps que prévu, la tâche suivante risque de ne pas démarrer à l’heure prévue. Si vous disposez de codeunits qui génèrent 100 000 tâches programmées ou plus, vous devez déterminer si vous avez réellement besoin de toutes ces tâches. Vous pouvez accéder à la liste de toutes les tâches programmées sur la page **Tâches programmées**.

Pour en savoir plus sur la surveillance de l’état des écritures file d’attente des projets, reportez-vous à [Pour afficher l’état d’un projet](#to-view-status-for-any-job). Pour en savoir plus sur les limites opérationnelles, accédez à [Limites des tâches asynchrones](/dynamics365/business-central/dev-itpro/administration/operational-limits-online#Task).

## <a name="monitor-status-or-errors-in-the-job-queue"></a>Surveiller l’état ou les erreurs dans la file d’attente des travaux

Les données générées par la file d’attente des travaux sont stockées, de sorte que vous pouvez résoudre les erreurs.  

Pour chaque entrée de file d'attente des travaux, vous pouvez afficher et modifier l’état. Lorsque vous créez une écriture file d'attente des travaux, son état est défini sur **En attente**. Vous pouvez définir l'état sur **Prêt** et revenir à **En attente**, par exemple. Sinon, les informations d'état sont mises à jour automatiquement.

Le tableau suivant décrit les valeurs du champ **État**.

| état | Désignation |
|--|--|
| Prêt | L’écriture file d’attente des travaux est prête à être exécutée. |
| En cours | L’écriture file d’attente des travaux est en cours. Ce champ est mis à jour lors de l’exécution de la file d’attente des travaux. |
| En attente | L'état par défaut de l’écriture file d’attente des projets lorsque vous la créez. Choisissez **Attribuer l'état Prêt** pour modifier l'état sur **Prêt**. Choisissez l’action **Définir sur Suspendu** pour rétablir l’état sur **En attente**. Pour en savoir plus, accédez à [À propos de l’attente](#about-on-hold).|
| Suspendu en raison d'une inactivité | Utilisé principalement pour les écritures file d’attente des projets qui programment la synchronisation entre [!INCLUDE [prod_short](includes/prod_short.md)] et une autre application, telle que [!INCLUDE [cds_long_md](includes/cds_long_md.md)]. Pour en savoir plus sur cer état, consultez [À propos des délais d’inactivité](/dynamics365/business-central/admin-scheduled-synchronization-using-the-synchronization-job-queue-entries#about-inactivity-timeouts). |
|En attente | Uniquement pertinent pour les écritures file d’attente des projets auxquelles un code de catégorie est affecté. Indique que le projet est programmé, mais que la tâche programmée sous-jacente n’est pas active. Après la fin de l’écriture file d’attente des projets en cours d’exécution et dans la même catégorie, l'état du projet suivant dans la catégorie avec l'état En attente devient Prêt. |
| Erreur | Un problème est survenu. Choisissez **Afficher erreur** pour afficher le message d’erreur. |
| PROD FINIS | L’écriture file d’attente des travaux est complète. |

 > [!TIP]  
> Les écriture de la file d’attente des tâches cessent de s’exécuter en cas d’erreur. Par exemple, cela peut être un problème lorsqu'une entrée se connecte à un service externe, tel qu'un flux bancaire. Si le service est temporairement indisponible et que l’entrée de la file d’attente des travaux ne peut pas se connecter, l’entrée affichera une erreur et cessera de s’exécuter. Vous devrez redémarrer manuellement l’entrée de la file d’attente des travaux. Cependant, les champs **Nombre maximal de tentatives** et **Délai de réexécution (sec.)** peuvent vous aider à éviter cette situation. Le champ **Nombre maximal de tentatives** vous permet de spécifier combien de fois l’entrée de la file d’attente des travaux peut échouer avant qu’elle n’arrête d’essayer de s’exécuter. Le champ **Délai de réexécution (sec.)** vous permet de spécifier la durée, en secondes, entre les tentatives. La combinaison de ces deux champs peut maintenir l’entrée de la file d’attente des travaux en cours d’exécution jusqu’à ce que le service externe soit disponible.

### <a name="about-on-hold"></a>À propos de l’attente

La définition d’une écriture file d’attente des projets sur **En attente** n’affecte pas un projet déjà en cours d’exécution. Après le démarrage d'un projet, il continue à s’exécuter jusqu’à son terme, quelles que soient les modifications apportées ultérieurement à l’écriture file d’attente des projets, par exemple sa mise en attente.<br><br>L'état **En attente** est généralement utilisé pour empêcher un projet de démarrer automatiquement lorsqu’il atteint l’heure de début programmée. Il permet d’interrompre temporairement un projet avant qu’il ne commence à être traité. <br><br>Si vous devez arrêter ou annuler une tâche en cours d’exécution, vous pouvez intervenir manuellement dans le processus. Par exemple, vous pouvez arrêter la session ou le processus correspondant.

### <a name="to-view-status-for-any-job"></a>Pour visualiser l'état de tous les travaux

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures file d’attente des travaux**, puis sélectionnez le lien associé.
2. Sur la page **Écritures file d'attente des travaux**, sélectionnez une écriture file d'attente des travaux, puis sélectionnez l'action **Écritures journal**.  

> [!TIP]
> Pour une analyse plus approfondie basée sur la télémétrie, utilisez Application Insights dans Microsoft Azure pour voir l’état des écritures file d’attente. Pour en savoir plus sur la télémétrie, accédez à [Surveillance et analyse de la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) et [Analyse de la télémétrie de la trace du cycle de vie des files d’attente de travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

## <a name="view-scheduled-tasks"></a>Afficher les tâches programmées

La page **Tâches programmées** dans [!INCLUDE [prod_short](includes/prod_short.md)] indique quelles tâches sont prêtes à être exécutées dans la file d'attente des travaux. La page affiche également des informations sur la compagnie dans laquelle chaque tâche est configurée pour s’exécuter. Cependant, seules les tâches marquées comme appartenant à l’environnement actuel peuvent s’exécuter.  

Par exemple, toutes les tâches programmées s’arrêtent si la compagnie se trouve dans un environnement qui est une copie d’un autre environnement. Utilisez la page **Tâches programmées** pour définir les tâches comme prêtes à être exécutées dans la file d'attente des travaux.  

> [!NOTE]
> Les administrateurs internes et les utilisateurs sous licence peuvent programmer l’exécution des tâches. Les administrateurs délégués peuvent configurer et programmer des tâches à exécuter, mais seuls les utilisateurs sous licence peuvent les exécuter.

## <a name="the-my-job-queue-part"></a>Composant Ma file d’attente des travaux

Le composant **Ma file d’attente des projets** sur votre Tableau de bord répertorie les écritures file d’attente des projets que vous avez commencées, mais qui ne sont pas terminées. Par défaut, le composant n’est pas affiché, mais vous pouvez l’ajouter à votre tableau de bord. Pour plus d’informations sur la personnalisation, consultez [Personnaliser votre espace de travail](ui-personalization-user.md).  

Le composant affiche les informations suivantes :

* Quels documents ayant votre code dans le champ **Code utilisateur affecté** sont en cours de traitement ou en attente, y compris ceux reportés à l’arrière-plan. 
* S’il y a eu une erreur lors du report d’un document ou dans l’entrée de la file d’attente des travaux. 

Le composant Ma file d’attente des travaux permet également d’annuler une report de document.

### <a name="to-view-an-error-from-the-my-job-queue-part"></a>Pour afficher une erreur dans le composant Ma file d'attente des travaux

1. Sur une écriture ayant l'état **Erreur**, sélectionnez l'action **Afficher erreur**.
2. Examinez le message d’erreur et résolvez le problème.

## <a name="examples-of-what-you-can-schedule-using-job-queue-entries"></a>Exemples de ce que vous pouvez programmer à l’aide des écritures de la file d’attente des travaux

### <a name="schedule-reports"></a>Programmer des rapports

Vous pouvez programmer un rapport ou un traitement en lot pour qu'il s'exécute à une date et une heure spécifiques. Les rapports ou les traitements en lot programmés sont entrés dans la file d'attente des travaux et traités au moment programmé, comme les autres projets. Vous devez choisir l’option **Calendrier** après avoir choisi l’action **Envoyer à**, puis vous devez entrer des informations telles que l’imprimante, l’heure, la date et la récurrence.  

Pour en savoir plus sur la planification, accédez à [Planifier l’exécution d’un rapport](ui-work-report.md#ScheduleReport)

### <a name="schedule-synchronization-between--and-includeprod_short"></a>Programmer la synchronisation entre [!INCLUDE[prod_short](includes/prod_short.md)] et [!INCLUDE[prod_short](includes/cds_long_md.md)]

Si vous intégrez [!INCLUDE[prod_short](includes/prod_short.md)] à [!INCLUDE[prod_short](includes/cds_long_md.md)], la file d’attente des projets vous permet de programmer à quel moment synchroniser les données. Selon la direction et les règles que vous définissez, l’écriture file d’attente des projets peut créer des enregistrements dans une application pour établir une correspondance avec des enregistrements dans l’autre. Un bon exemple est lorsque vous enregistrez un contact dans [!INCLUDE[crm_md](includes/crm_md.md)], l’entrée de la file d’attente peut configurer ce contact pour vous dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour en savoir plus sur la planification, voir [Planification d’une synchronisation entre Business Central et Dynamics 365 Sales](admin-scheduled-synchronization-using-the-synchronization-job-queue-entries.md).

### <a name="schedule-when-to-post-sales-and-purchase-orders"></a>Programmer le moment de report des commande vente et des bons de commande

Vous pouvez utiliser les entrées de la file d’attente des travaux pour programmer l’exécution des processus métier en arrière-plan. Par exemple, les tâches en arrière-plan sont utiles quand plusieurs utilisateurs valident des documents de vente en même temps, mais qu’une seule commande peut être traitée à la fois. Pour en savoir plus sur la publication en arrière-plan, accédez à [Pour configurer la publication en arrière-plan avec des files d’attente de travaux](ui-batch-posting.md#to-set-up-background-posting-with-job-queues).

## <a name="handle-job-queue-entry-issues"></a>Gérer les problèmes d’écritures dans la file d’attente des tâches

Si une écriture de la file d’attente des travaux affiche une erreur, votre première option pour résoudre le problème consiste à redémarrer l’entrée de la file d’attente des travaux. Vous pouvez définir l’état de l’entrée de la file d’attente des travaux sur **En attente**, puis sur **Prêt**, ou simplement la redémarrer.

Si un redémarrage n’aide pas, le problème peut être dans le code. Vous pouvez trouver le propriétaire (également appelé *éditeur*) du code dans la trace de la pile AL dans le journal de la file d’attente des travaux. Si l’erreur provient d’une application/extension, contactez votre partenaire Microsoft. Si l’erreur provient d’une application Microsoft, ouvrez une demande de support auprès de Microsoft.

Si vous contactez votre partenaire Microsoft ou Microsoft pour obtenir de l’aide, fournissez les informations suivantes :

* L’ID de l’entrée de la file d’attente de tâches s’exécute là où l’erreur s’est produite
* L’horodatage du moment où l’erreur s’est produite
* Votre fuseau horaire

> [!TIP]
> Selon que votre [!INCLUDE [prod_short](includes/prod_short.md)] est antérieur ou ultérieur à la version 22.1, rassemblez les informations de la manière suivante :
>
> * Pour les versions antérieures, fournissez une capture d’écran de la page **Écritures journal file d’attente des travaux**.
> * Pour les versions ultérieures, utilisez l’action **Copier les détails** sur la page Écritures journal file d’attente des travaux pour copier les informations (Code de la file d’attente des travaux, horodatage et votre fuseau horaire).

## <a name="monitor-the-job-queue-with-telemetry"></a>Surveiller la file d’attente des travaux avec la télémétrie

Les administrateurs peuvent utiliser [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) pour recueillir et analyser la télémétrie qui vous permet d’identifier les problèmes. Pour en savoir plus sur la télémétrie, accédez à [Surveillance et analyse de la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-overview) et [Analyse de la télémétrie de la trace du cycle de vie des files d’attente de travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace).

La télémétrie permet aux administrateurs de configurer des alertes sur les problèmes de file d’attente des tâches qui envoient un SMS, un courriel ou un message dans Teams si quelque chose ne va pas. Pour en savoir plus sur ces alertes, accédez à [Alerte sur la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-alert).

## <a name="see-also"></a>Voir aussi .

[Administration](admin-setup-and-administration.md)  
[Configuration de Business Central](setup.md)  
[Modification des paramètres de base](ui-change-basic-settings.md)  
[Analyse de la télémétrie de suivi du cycle de vie de la file d'attente des travaux](/dynamics365/business-central/dev-itpro/administration/telemetry-job-queue-lifecycle-trace)  
[Alerte sur la télémétrie](/dynamics365/business-central/dev-itpro/administration/telemetry-alert)

[!INCLUDE[footer-include](includes/footer-banner.md)]
