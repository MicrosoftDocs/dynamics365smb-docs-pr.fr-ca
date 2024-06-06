---
title: Exécuter et imprimer des rapports
description: En savoir plus sur l'intégration d'un rapport dans une file d'attente des travaux et la programmation de son traitement à une date et une heure spécifiques.
author: jswymer
ms.author: jswymer
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'task, process, report, print, schedule, save, Excel, PDF, Word, dataset'
ms.search.form: null
ms.date: 09/04/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Exécuter et imprimer des rapports

Un rapport rassemble des informations en fonction d’un ensemble spécifié de critères. Il organise et présente les informations dans un format facile à lire que vous pouvez imprimer ou enregistrer sous forme de fichier. Il existe de nombreux rapports accessibles dans l'ensemble de l'application. Les rapports fournissent généralement des informations relatives au contexte de la page où vous vous trouvez. Par exemple, la page **Client** comprend des rapports pour les 10 principaux clients et les statistiques de vente, et plus encore.

> [!NOTE]
> Les traitements en lot et les ports XML sont plus ou moins identiques aux rapports mais ils ont pour objectif d’exécuter un processus ou d’exporter des données. Par exemple, le traitement en lot **Créer des rappels** crée des rappels à envoyer aux clients avec des paiements échus. Cet article fait référence surtout aux « rapports », mais des informations similaires s’appliquent aux traitements en lot et aux ports XML.

## Mise en route

Vous pouvez trouver les rapports sous l’onglet **Rapports** sur les pages, listes et fiches sélectionnées ou utiliser la recherche ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"). pour rechercher des rapports par nom. Pour un aperçu des rapports intégrés que vous pouvez utiliser dans [!INCLUDE[prod_short](includes/prod_short.md)], triés par catégories, voir [Rapports disponibles dans [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md).

Lorsque vous choisissez un rapport, une page de demande s’affiche généralement&mdash;avec un titre selon le nom du rapport&mdash;pour vous permettre de définir plusieurs options et filtres qui déterminent les éléments à inclure dans le rapport. Les sections suivantes expliquent comment utiliser la page de demande pour créer, afficher un aperçu et imprimer un rapport.

## <a name="SavedSettings"></a>Utilisation des valeurs par défaut – paramètres prédéfinis

La plupart des pages de demande de rapport incluent le champ **Utiliser les valeurs par défaut de**. Avec ce champ, vous pouvez sélectionner des paramètres prédéfinis pour le rapport, qui définissent automatiquement les options et les filtres. Sélectionnez une entrée dans la liste déroulante, et vous verrez les options et les filtres sur la page de demande de rapport se modifier en conséquence.

L’entrée appelée **Options et filtres récemment utilisés** est toujours disponible. Cette entrée configure le rapport pour qu'il utilise les options et les filtres que vous avez utilisés la dernière fois que vous l’avez exécuté.

Le champ **Utiliser les valeurs par défaut de** fournit un moyen rapide et fiable de générer de manière cohérente des rapports contenant les données correctes. Après avoir sélectionné une entrée, vous pouvez modifier les options et les filtres avant d’afficher un aperçu ou d’imprimer le rapport. Vos modifications ne seront pas enregistrées dans l’entrée de paramètres prédéfinis que vous avez sélectionnée, mais elles seront sauvegardées dans l’entrée **Options et filtres récemment utilisés**.

> [!NOTE]
> Les paramètres prédéfinis sont généralement configurés et gérés par un administrateur. Pour en savoir plus, voir [Gérer les paramètres enregistrés pour les rapports et les traitements en lot](reports-saving-reusing-settings.md).

## Définition des données à inclure dans un rapport

Utilisez les champs sous **Options** et **Filtres** pour modifier ou limiter les informations que vous souhaitez dans le rapport. Vous pouvez définir des filtres dans un rapport plus ou moins de la même manière que vous le faites sur des listes. Consultez la section [Filtrage](ui-enter-criteria-filters.md#filtering).

> [!CAUTION]
> Le raccourci **Filtrer** sur une page de demande de rapport fournit une fonctionnalité de filtrage générique pour les rapports. Ces filtres sont optionnels.
>
> Certains rapports ignorent ces filtres, ce qui signifie que quel que soit le filtre défini dans le raccourci **Filtre**, la sortie du rapport est identique. Il est impossible de fournir une liste des champs ignorés dans les rapports, vous devez expérimenter avec les filtres lorsque vous les utiliserez.
>
> **Exemple** : Lorsque vous utilisez le traitement en lot **Créer rappels**, un filtre pour le champ **Écritures client** de **Niveau dernier rappel émis** sera ignoré, car les filtres sont fixes pour ce traitement en lot.

## Affichage de l'aperçu d'un rapport

En affichant l’aperçu d’un rapport, vous pouvez voir à quoi il ressemblera avant de l’imprimer. L’aperçu n’est pas basé sur l’imprimante sélectionnée dans le champ **Imprimante** sur la page de demande. Il est contrôlé par le navigateur. Après l’aperçu, vous pouvez revenir à la page de la demande et apporter des modifications aux options et aux filtres si nécessaire.

Les choix d’aperçu sur la page **Demande de rapport** dépendent du rapport. Ainsi, pour certains rapports, vous pouvez choisir **Aperçu**, tandis que pour d’autres, le choix est **Aperçu et fermer**. Les deux choix ouvrent un aperçu du rapport. La différence est que l’**Aperçu** garde la page de demande ouverte afin que vous puissiez y revenir, apporter des modifications, afficher à nouveau un aperçu ou imprimer. Au contraire, avec **Aperçu et fermer**, la page de demande se ferme, vous devrez donc rouvrir le rapport pour apporter des modifications ou l’imprimer.

> [!NOTE]
> Si vous utilisez la 1re vague de lancement 2020 de Business Central ou une version antérieure, le seul choix est **Aperçu** qui ferme la page de demande lors de l’aperçu, comme décrit plus haut pour **Aperçu et fermer**.

### Utiliser l’aperçu

Dans l’Aperçu, utilisez la barre de menus dans l’aperçu du rapport pour :

- Naviguer entre les pages
- Effectuer un zoom avant et arrière
- Redimensionner à la taille de la page
- Sélectionner du texte

    Vous pouvez copier le texte d’un rapport puis le coller ailleurs, comme dans une page de [!INCLUDE[prod_short](includes/prod_short.md)] ou Microsoft Word. À l’aide d’une souris, par exemple, vous sélectionnez le bouton gauche de la souris et le maintenez enfoncé où vous voulez commencer. Faites glisser la souris pour sélectionner un ou plusieurs mots, phrases ou paragraphes. Puis sélectionnez le bouton droit de la souris et sélectionnez **Copier**. Vous pouvez maintenant coller le texte sélectionné partout où vous le souhaitez.
- Faire défiler le document

    Vous pouvez déplacer la zone visible du rapport dans n’importe quelle direction pour voir d’autres zones du rapport. Le défilement est utile si vous avez effectué un zoom pour observer les détails. Avec la souris, par exemple, sélectionnez et maintenez la pression n’importe où dans l’aperçu du rapport, puis déplacez la souris pour sélectionner une section du rapport.

- Téléchargez un fichier PDF sur votre ordinateur ou votre réseau.
- Imprimer

## Enregistrement d’un rapport dans un fichier

Vous pouvez enregistrer un rapport dans un document PDF, un document Microsoft Word, un classeur Microsoft Excel ou un document XML en sélectionnant **Envoyer à**, puis en effectuant votre sélection. Un fichier de présentation sera téléchargé sur votre appareil.

Si votre organisation a configuré OneDrive pour les fonctionnalités système, au lieu d’être téléchargés, les classeurs Excel et les documents Word sont ouverts dans votre navigateur à l’aide d’Excel ou de Word pour le Web.

> [!TIP]
> Les options **Document Microsoft Excel (données uniquement)** et **Document XML** concernent principalement le niveau avancé. Vous utiliserez généralement ces options pour effectuer une analyse détaillée des données. Pour en savoir plus, voir [Analyse des données de rapport avec Excel et XML](report-analyze-excel.md).
>
> Vous pouvez également utiliser l’option **Document Microsoft Excel (données uniquement)** pour créer des présentations Excel pour un rapport donné. En savoir plus sur [Utiliser les présentations Excel](ui-excel-report-layouts.md).  

## <a name="ScheduleReport"></a> Planification d’un rapport pour une exécution ultérieure ou périodique

Vous pouvez programmer un rapport unique ou récurrent à exécuter à une date et une heure spécifiques. Les rapports prévus sont entrés dans la file d'attente projets et traités au moment prévu, comme les autres projets. Choisissez l’option **Programmer** après avoir sélectionné **Envoyer à**, puis entrez des informations telles que l’imprimante, l’heure et la date. Le rapport est alors ajouté à la file d’attente des projets et sera exécuté au moment spécifié. Lorsque le rapport a été traité, l’article est supprimé de la file d’attente des travaux. Pour plus d’informations, voir [Utiliser des files d’attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

Lorsque vous programmez l’exécution d’un rapport, vous pouvez spécifier qu’il doit s’exécuter, par exemple, tous les jeudis en définissant le champ **Formule de date de la prochaine exécution** sur *D4*. Pour plus d’informations, voir [Utiliser des formules date](ui-enter-date-ranges.md#use-date-formulas).  

Vous pouvez choisir d'enregistrer le rapport dans un fichier (par exemple, Excel, Word ou PDF), de l’imprimer ou uniquement de générer le rapport. Si vous choisissez d’enregistrer le rapport dans un fichier, le rapport traité est envoyé à la page **Boîte de réception rapport** sur votre tableau de bord, dans laquelle vous pouvez l’afficher. Pour en savoir, voir [Partager et exporter des rapports avec la boîte de réception Rapport](ui-work-report-inbox.md)

### Gérer les rapports récurrents programmés

Les rapports programmés sont générés par des traitements en lot gérés sur la page **Écritures file d’attente des travaux**. Vous pouvez voir l’état et d’autres informations pour chaque rapport sur la page, interrompre/reprendre le traitement en lot du rapport et générer le rapport à la demande.

Depuis la page **Écritures file d’attente des travaux**, vous pouvez également modifier certains paramètres de rapport, tels que le type de fichier de sortie, la récurrence, la date d’exécution et les heures de début et de fin. Toutefois, avant de modifier un rapport programmé existant, il est nécessaire de mettre la file d’attente des travaux de rapport en attente :

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction de recherche 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures file d’attente des travaux**, puis sélectionnez le lien associé.  
2. Sur la page **Écritures file d’attente des travaux**, choisissez le rapport souhaité.
3. Choisissez l’action **Définir en attente**.
4. Ouvrez et modifiez le rapport programmé en sélectionnant son état (*En attente*).

Après avoir modifié les options du rapport, répétez les deux premières étapes, puis sélectionnez l’action **Définir l’état sur Prêt** pour reprendre la génération du rapport.

Pour en savoir plus sur la gestion des files d’attente des travaux, voir [Utiliser les files d’attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

## <a name="PrintReport"></a>Impression d’un rapport

Pour imprimer un rapport, sélectionnez **Imprimer** sur la page de demande de rapport ou dans la barre de menu de la page **Aperçu**.

Lorsqu’un rapport utilise une présentation Excel, le champ **Imprimante** et les boutons **Imprimer** ou **Aperçu** ne sont pas affichés. Au lieu de cela, il y a une option **Télécharger**. Pour imprimer, sélectionnez **Télécharger**, puis ouvrez le fichier téléchargé dans Excel et imprimez à partir de là.

### <a name="Printer"></a>Imprimante

Le champ **Imprimante** sur la page de demande affiche le nom de l’imprimante à laquelle le rapport est transmis. Pour changer d'imprimante, sélectionnez simplement l'imprimante dans la liste.

> [!NOTE]
> L’option **(Géré par le navigateur)** indique qu’il n’y a pas d’imprimante désignée pour le rapport. Dans ce cas, le navigateur gérera l’impression et affichera une expérience standard, où vous pourrez choisir une imprimante locale connectée à votre appareil. L’option **(Géré par le navigateur)** n’est pas disponible dans l’application mobile [!INCLUDE[prod_short](includes/prod_short.md)] ou application pour Microsoft Teams.

> [!TIP]
> L'imprimante sélectionnée pour vous par défaut est configurée sur la page **Sélections d'imprimantes**. En savoir plus sur la modification de l’imprimante par défaut dans la section [Configurer les imprimantes par défaut](ui-specify-printer-selection-reports.md#default).

### Impression de rapports en thaïlandais

Spécifiquement pour la version thaïlandaise de [!INCLUDE[prod_short](includes/prod_short.md)], le bouton **Imprimer** ne peut pas imprimer correctement des rapports du fait des limitations du service qui génère un fichier PDF imprimable. À la place, vous pouvez ouvrir le rapport dans Word puis l'enregistrer en tant que fichier PDF imprimable.  

Sinon, vous pouvez demander à votre administrateur de créer une présentation rapport Word pour vos rapports les plus utilisés. Pour en savoir plus, voir [Gestion des présentations de rapport et de document](ui-manage-report-layouts.md).  

## Modifier la présentation du rapport

Une présentation de rapport contrôle les éléments affichés sur un rapport, leur agencement et leur mise en forme. Il explique plusieurs méthodes pour modifier la présentation :

- Lorsque vous configurez l’exécution d’un rapport, vous voyez la présentation actuelle dans le champ **Présentation du rapport** sur la page de demande. Pour basculer temporairement vers une autre présentation, sélectionnez le champ **Présentation du rapport**, puis faites votre choix dans la liste des présentations disponibles pour le rapport.
- Pour modifier la présentation par défaut utilisée par un rapport, accédez aux pages **Présentations du rapport** ou **Sélection de la présentation du rapport**.

Pour en savoir plus, voir [Définir la présentation utilisée par un rapport](ui-set-report-layout.md). Ou, si vous voulez personnaliser votre propre présentation de rapport, voir [Bien démarrer avec la création de présentations](ui-get-started-layouts.md).

## Modifier la langue et le format des nombres, des dates et des heures

Par défaut, la langue du texte et le format des nombres, des dates et des heures dans un rapport sont basés sur vos paramètres de langue de travail et de région, qui sont définis sur la page **Mes paramètres**. Vous pouvez toutefois modifier la langue et la région de format au cas par cas lorsque vous prévisualisez, imprimez ou envoyez un rapport. Sur la page de demande, définissez les options **Langue** et **Région de format** selon vos préférences. Vous pouvez également spécifier le format de langue et de région à utiliser par défaut pour les clients et les fournisseurs sur les pages de leurs fiches.

Selon l’emplacement où vous avez spécifié les paramètres de langue et de format, [!INCLUDE [prod_short](includes/prod_short.md)] détermine les paramètres à utiliser dans l’ordre suivant :

1. Les paramètres que vous spécifiez lorsque vous générez un rapport.
2. Les paramètres spécifiés dans le document, qui proviennent des paramètres du client ou du fournisseur.
3. Les paramètres spécifiés dans l’objet Rapport AL.
4. Les paramètres définis dans Mes paramètres.

Pour plus d’informations sur la page **Mes paramètres**, accédez à [Modifier les paramètres de base](ui-change-basic-settings.md#region).

## Options avancées

Les champs sous le raccourci **Avancé** définissent des limites sur le rapport généré pour contrôler les ressources de l’imprimante. Vous n’aurez généralement pas à modifier ces paramètres, sauf si vous disposez d’un rapport volumineux. Si un rapport dépasse ces limites lorsque vous essayez d’afficher un aperçu ou d’imprimer, un message indiquera quelle limite vous avez dépassée. Vous pouvez ensuite modifier les paramètres en fonction de votre rapport. Cependant, chaque champ a une valeur maximale que vous devez connaître :

|Champ|Valeur maximale|
|-----|-------------|
|Durée maximale de l’affichage|12:00:00|
|Nombre maximal de lignes|1 000 000|
|Nombre maximal de documents|500|

> [!NOTE]
> Les valeurs maximales peuvent être différentes pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site et un administrateur peut les modifier. Pour plus d’informations, reportez-vous à la rubrique [Configuration de Business Central Server – Rapports](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#Reports). Pour un aperçu des limites des rapports dans [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, voir [Limites opérationnelles](/dynamics365/business-central/dev-itpro/administration/operational-limits-online).

## Voir aussi .

[Rapports disponibles dans [!INCLUDE[prod_short](includes/prod_short.md)]](reports-available-reports.md)  
[Utilisation des rapports dans le travail quotidien](reports-use-reports.md)  
[Vue d’ensemble de Business Intelligence et de la génération de rapports](reports-bi-reporting.md)  
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Exécuter des traitements en lot et des objets XMLport](ui-how-run-batch-jobs.md)  
[Utiliser les dates civiles et les heures](ui-enter-date-ranges.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Décisionnel pour le secteur de la finance](bi.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
