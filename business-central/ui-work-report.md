---
title: Programmation d'un rapport à exécuter à une date et une heure spécifiques | Microsoft Docs
description: En savoir plus sur l'intégration d'un rapport dans une file d'attente des travaux et la programmation de son traitement à une date et une heure spécifiques.
author: jswymer
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report
ms.date: 04/01/2021
ms.author: jswymer
ms.openlocfilehash: 81df1625531b3b4c5bf1a55a9e09d37af8b6f7fe
ms.sourcegitcommit: 766e2840fd16efb901d211d7fa64d96766ac99d9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2021
ms.locfileid: "5782994"
---
# <a name="working-with-reports-batch-jobs-and-xmlports"></a>Utilisation des rapports, des traitements en lot et des objets XMLport

Un rapport regroupe des informations en fonction d'un ensemble de critères spécifié, et organise et présente les informations dans un format facilement lisible que vous pouvez imprimer ou enregistrer en tant que fichier. Il existe de nombreux rapports accessibles dans l'ensemble de l'application. Les rapports fournissent généralement des informations relatives au contexte de la page sur laquelle vous vous trouvez. Par exemple, la page **Client** comprend des rapports pour les 10 principaux clients et les statistiques de vente, et plus encore.

Les traitements en lot et les objets XMLport sont plus ou moins identiques aux rapports mais ils ont pour objectif d'exécuter un processus ou d'exporter des données. Par exemple, le traitement en lot **Créer des rappels** crée des rappels pour les clients ayant des paiements échus.  

> [!NOTE]
> Cette rubrique fait référence surtout aux « rapports », mais des informations similaires s'appliquent aux traitements en lot et aux objets XMLport.

## <a name="getting-started"></a>Mise en route

Vous pouvez trouver les rapports sous l’onglet **Rapports** sur les pages sélectionnées ou utiliser la recherche ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") pour rechercher les rapports par nom.

Lorsque vous ouvrez un rapport, un traitement en lot ou un XMLport, une page de demande s’affiche généralement pour vous permettre de définir plusieurs options et filtres qui déterminent les éléments à inclure dans le rapport. Les sections suivantes expliquent comment utiliser la page de demande pour créer, afficher un aperçu et imprimer un rapport.

## <a name="using-default-values---predefined-settings"></a><a name="SavedSettings"></a>Utilisation des valeurs par défaut – paramètres prédéfinis 

La plupart des pages de demande incluent le champ **Utiliser les valeurs par défaut de**. Ce champ vous permet de sélectionner des paramètres prédéfinis pour le rapport, qui définissent automatiquement les options et les filtres du rapport. Sélectionnez une entrée dans la liste déroulante, et vous verrez les options et les filtres sur la page de demande se modifier en conséquence.

L’entrée appelée **Options et filtres récemment utilisés** est toujours disponible. Cette entrée permet de faire en sorte que le rapport utilise les options et les filtres qui ont été utilisés la dernière fois que vous l’avez exécuté.

Le champ **Utiliser les valeurs par défaut de** fournit un moyen rapide et fiable de générer de manière cohérente des rapports contenant les données correctes. Après avoir sélectionné une entrée, vous pouvez modifier les options et les filtres avant d’afficher un aperçu ou d’imprimer le rapport. Vos modifications ne seront pas enregistrées dans l’entrée de paramètres prédéfinis que vous avez sélectionnée, mais elles seront sauvegardées dans l’entrée **Options et filtres récemment utilisés**.

>[!NOTE]
> Les paramètres prédéfinis sont généralement configurés et gérés par un administrateur. Pour en savoir plus, voir [Gérer les paramètres enregistrés pour les rapports et les traitements en lot](reports-saving-reusing-settings.md).

## <a name="specifying-the-data-to-include-in-reports"></a>Définition des données à inclure dans les rapports

Utilisez les champs sous **Options** et **Filtres** pour modifier ou limiter les informations que vous souhaitez dans le rapport. Vous devez définir des filtres dans un rapport de la même manière que vous le faites sur des listes. Pour plus d'informations, reportez-vous à la rubrique [Filtrage](ui-enter-criteria-filters.md#filtering).

> [!CAUTION]
> La section **Filtrer la liste par** sur une page de demande fournit une capacité de filtrage générique pour les rapports. Ces filtres sont optionnels.
>
> Certains rapports ignoreront ces filtres, ce qui signifie que quel que soit le filtre défini dans la section **Filtrer la liste par**, la sortie du rapport est identique. Il est impossible de fournir une liste des champs ignorés dans les rapports, vous devrez expérimenter avec les filtres lorsque vous les utiliserez.
>
> **Exemple** : Lorsque vous utilisez le traitement en lot **Créer rappels**, un filtre pour le champ **Écritures client** de **Niveau dernier rappel émis** sera ignoré, car les filtres sont fixes pour ce traitement en lot.

## <a name="previewing-a-report"></a>Affichage de l'aperçu d'un rapport

L’aperçu d’un rapport vous permet de voir à quoi il ressemblera avant de l’imprimer. L'aperçu n'est pas basé sur le champ **Imprimante** de l'imprimante sélectionnée sur la page de demande. Il est contrôlé par le navigateur. Après l’aperçu, vous pouvez revenir à la page de la demande et apporter des modifications aux options et aux filtres si nécessaire.

Pour afficher l’aperçu d’un rapport, choisissez le bouton **Aperçu** ou **Aperçu et fermer** sur la page de demande de rapport. Le bouton qui s’affiche dépend du rapport, certains rapports ont un bouton **Aperçu**, tandis que d’autres ont un bouton **Aperçu et fermer**. Les deux boutons ouvriront un aperçu du rapport. La différence est que l’**Aperçu** garde la page de demande ouverte afin que vous puissiez y revenir, apporter des modifications, afficher à nouveau un aperçu ou imprimer. Avec **Aperçu et fermer**, la page de demande se ferme, vous devrez donc rouvrir le rapport pour apporter des modifications ou l’imprimer.

> [!NOTE]
> Si vous utilisez la vague de lancement 1 de 2020 de Business Central ou antérieure, il n’y a qu’un bouton **Aperçu** qui ferme la page de demande lors de l’aperçu, comme décrit pour **Aperçu et fermer**.

### <a name="working-with-the-preview"></a>Utilisation de l’aperçu

Dans l’Aperçu, utilisez la barre de menus dans l’aperçu du rapport pour :

- Naviguer entre les pages
- Effectuer un zoom avant et arrière
- Redimensionner à la taille de la page
- Sélectionner du texte

    Vous pouvez copier le texte d'un rapport puis le coller ailleurs, comme dans une page de [!INCLUDE[prod_short](includes/prod_short.md)] ou Microsoft Word.  Avec la souris, par exemple, appuyez et maintenez la pression là où vous souhaitez démarrer, puis déplacez la souris pour sélectionner un ou plusieurs mots, phrases ou paragraphes. Appuyez sur le bouton droit de la souris et sélectionnez **Copier**. Ensuite, collez le texte sélectionné partout où vous le souhaitez.
- Faire défiler le document

    Vous pouvez déplacer la zone visible du rapport dans n'importe quelle direction de manière voir d'autres zones ou le rapport. Le défilement est utile si vous avez effectué un zoom pour observer les détails.  À l'aide de la souris, par exemple, appuyez et maintenez le bouton de la souris enfoncé n'importe où dans l'aperçu du rapport, puis déplacez la souris.

- Téléchargez un fichier PDF sur votre ordinateur ou votre réseau.
- Imprimer

## <a name="saving-a-report"></a>Enregistrement d'un rapport

Vous pouvez enregistrer un rapport dans un document PDF, un document Microsoft Word ou un document Microsoft Excel en sélectionnant le bouton **Envoyer à**, puis en effectuant votre sélection.

## <a name="scheduling-a-report-to-run"></a><a name="ScheduleReport"></a> Programmation d'un rapport à exécuter

Vous pouvez programmer ou traiter en lot un rapport à exécuter à une date et une heure spécifiques. Les rapports ou les traitements en lot programmés sont entrés dans la file d'attente des travaux et traités au moment programmé, comme les autres projets. Vous devez choisir l'option **Programmé** après avoir cliqué sur le bouton **Envoyer à**, puis vous devez entrer des informations telles que l’imprimante, l’heure et la date. Le rapport est alors ajouté à la file d'attente des travaux et sera exécuté au moment spécifié. Lorsque le rapport a été traité, l'article est supprimé de la file d'attente projets. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).  

Lorsque vous programmez l'exécution d'un rapport, vous pouvez spécifier qu'il doit s'exécuter tous les jeudis en définissant le champ **Formule de la date de la prochaine exécution** sur *D4*, par exemple. Pour plus d'informations, voir [Utilisation de formules date](ui-enter-date-ranges.md#using-date-formulas).  

Vous pouvez choisir de sauvegarder le rapport dans un fichier, par exemple, Excel, Word ou PDF, de l’imprimer sur une imprimante sélectionnée ou uniquement de générer le rapport. Si vous choisissez d'enregistrer le rapport dans un fichier, le rapport traité est envoyé à la zone **Boîte de réception rapport** sur votre tableau de bord, où vous pouvez l'afficher.  

## <a name="printing-a-report"></a><a name="PrintReport"></a>Impression d'un rapport

Pour imprimer un rapport, cliquez sur le bouton **Imprimer** sur la page de demande de rapport ou dans la barre de menu de la page **Aperçu**.

### <a name="printer"></a><a name="Printer"></a>Imprimante

Le champ **Imprimante** de la page de demande de rapport affiche le nom de l’imprimante à laquelle le rapport sera transmis. Pour changer d'imprimante, sélectionnez simplement l'imprimante dans la liste.

> [!NOTE]
> **(Géré par le navigateur)** indique qu’il n’y a pas d’imprimante désignée pour le rapport. Dans ce cas, le navigateur gérera l’impression et affichera une expérience standard, où vous pourrez choisir une imprimante locale connectée à votre appareil. **(Géré par le navigateur)** n'est pas disponible dans l'application mobile [!INCLUDE[prod_short](includes/prod_short.md)] ou application pour Microsoft Teams.

> [!TIP]
> L'imprimante sélectionnée pour vous par défaut est configurée sur la page **Sélections d'imprimantes**. Pour plus d'informations sur la modification de l'imprimante par défaut, reportez-vous à [Sélectionner quelles imprimantes impriment quels rapports](ui-specify-printer-selection-reports.md#default).

### <a name="printing-reports-in-thai"></a>Impression de rapports en thaïlandais

Spécifiquement pour la version thaïlandaise de [!INCLUDE[prod_short](includes/prod_short.md)], le bouton **Imprimer** ne peut pas imprimer correctement des rapports du fait des limitations du service qui génère un fichier PDF imprimable. À la place, vous pouvez ouvrir le rapport dans Word puis l'enregistrer en tant que fichier PDF imprimable.  

Sinon, vous pouvez demander à votre administrateur de créer une présentation rapport Word pour vos rapports les plus utilisés. Pour plus d'informations, voir [Gestion des présentations de rapport et de document](ui-manage-report-layouts.md).  

## <a name="changing-report-layouts"></a>Modification des présentations de rapport

Une présentation de rapport contrôle les éléments affichés sur un rapport, leur agencement et leur mise en forme. Si vous souhaitez changer de présentation, voir [Modifier la présentation actuelle du rapport](ui-how-change-layout-currently-used-report.md). Ou, si vous souhaitez personnaliser votre propre présentation de rapport, voir [Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md).

## <a name="advanced-options"></a>Options avancées

Les champs sous **Avancé** définissent des limites sur le rapport généré pour contrôler les ressources de l’imprimante. Vous n’aurez généralement pas à modifier ces paramètres, sauf si vous disposez d’un rapport volumineux. Si un rapport dépasse ces limites lorsque vous essayez d’afficher un aperçu ou d’imprimer, un message apparaît vous indiquant quelle limite a été dépassée. Vous pouvez ensuite modifier les paramètres en fonction de votre rapport. Cependant, chaque champ a une valeur maximale que vous devez connaître :

|Champ|Valeur maximale|
|-----|-------------|
|Durée maximale de l’affichage|12:00:00|
|Nombre maximal de lignes|1 000 000|
|Nombre maximal de documents|500|

> [!NOTE]
> Les valeurs maximales peuvent être différentes pour [!INCLUDE[prod_short](includes/prod_short.md)] sur site et un administrateur peut les modifier. Pour plus d’informations, reportez-vous à la rubrique [Configuration de Business Central Server – Rapports](/dynamics365/business-central/dev-itpro/administration/configure-server-instance#Reports). Pour un aperçu des limites des rapports [!INCLUDE[prod_short](includes/prod_short.md)] en ligne, voir [Limites opérationnelles](/dynamics365/business-central/dev-itpro/administration/operational-limits-online).

## <a name="see-also"></a>Voir aussi

[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Utilisation de dates civiles et les heures](ui-enter-date-ranges.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]