---
title: Programmation d'un rapport à exécuter à une date et une heure spécifiques | Microsoft Docs
description: En savoir plus sur l'intégration d'un rapport dans une file d'attente des travaux et la programmation de son traitement à une date et une heure spécifiques.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 2bafaa9f4bda392309a76470df5290857327e59c
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3189301"
---
# <a name="working-with-reports-batch-jobs-and-xmlports"></a>Utilisation des rapports, des traitements en lot et des objets XMLport
Un rapport regroupe des informations en fonction d'un ensemble de critères spécifié, et organise et présente les informations dans un format facilement lisible que vous pouvez imprimer ou enregistrer en tant que fichier. Il existe de nombreux rapports accessibles dans l'ensemble de l'application. Les rapports fournissent généralement des informations relatives au contexte de la page où vous vous trouvez. Par exemple, la page **Client** comprend des rapports pour les 10 principaux clients et les statistiques de vente, et plus encore.

Les traitements en lot et les objets XMLport sont plus ou moins identiques aux rapports mais ils ont pour objectif d'exécuter un processus ou d'exporter des données. Par exemple, le traitement en lot **Créer des rappels** crée des rappels pour les clients ayant des paiements échus.  

> [!NOTE]
> Cette rubrique fait référence surtout aux « rapports », mais des informations similaires s'appliquent aux traitements en lot et aux objets XMLport.

Vous pouvez rechercher des rapports dans l'onglet **Rapports** sur les pages sélectionnées ou utiliser la recherche ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") pour rechercher les rapports par nom.

## <a name="specifying-the-data-to-include-in-reports"></a>Définition des données à inclure dans les rapports
Lorsque vous ouvrez un rapport, un traitement en lot ou un XMLport, une page de demande s'affiche généralement pour vous permettre de définir plusieurs options et filtres qui déterminent les éléments à inclure dans le rapport.

Vous devez définir des filtres dans un rapport de la même manière que vous le faites sur des listes. Pour plus d'informations, reportez-vous à la rubrique [Filtrage](ui-enter-criteria-filters.md#filtering).

> [!Caution]
> La section **Filtrer la liste par** sur une page de demande fournit une capacité de filtrage générique pour les rapports. Ces filtres sont optionnels.<br /><br /> Certains rapports ignoreront ces filtres, ce qui signifie que quel que soit le filtre défini dans la section **Filtrer la liste par**, la sortie du rapport est identique. Il est impossible de fournir une liste des champs ignorés dans les rapports, vous devez donc expérimenter avec des filtres lorsque vous les utiliserez.<br /><br />
**Exemple** : Lorsque vous utilisez le traitement en lot **Créer rappels**, un filtre pour le champ **Écritures client** de **Niveau dernier rappel émis** sera ignoré, car les filtres sont fixes pour ce traitement en lot.

## <a name="using-saved-settings"></a><a name="SavedSettings"></a>Utilisation des paramètres enregistrés
La page de demande peut inclure la section **Paramètres enregistrés** qui contient une ou plusieurs entrées dans la zone **Utiliser les valeurs par défaut de**. Un paramètre enregistré est fondamentalement un groupe prédéfini d'options et de filtres que vous pouvez appliquer au rapport avant d'en afficher un aperçu ou de l'envoyer vers un fichier. L'écriture de paramètres enregistrés appelée **Options et filtres récemment utilisés** est toujours disponible. Cette écriture permet de faire en sorte que le rapport utilise les options et les filtres qui ont été utilisés la dernière fois que vous l'avez utilisé.

Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates. Après avoir défini la zone **Utiliser les valeurs par défaut de** sur une entrée de paramètres enregistrés, vous pouvez modifier les options et les filtres avant d'afficher un aperçu ou d'enregistrer le rapport. Vos modifications ne seront pas enregistrées dans l'entrée de paramètres enregistrés que vous avez sélectionnée, mais elles seront sauvegardées dans l'entrée **Options et filtres récemment utilisés**.

>[!NOTE]
>Si vous êtes un administrateur, vous pouvez créer et gérer les paramètres enregistrés des rapports pour tous les utilisateurs. Pour plus d'informations, voir [Gérer les paramètres enregistrés pour les rapports et les traitements en lot](reports-saving-reusing-settings.md).

## <a name="previewing-a-report"></a>Affichage de l'aperçu d'un rapport
Cliquez sur le bouton **Aperçu** pour afficher le rapport. Utilisez la barre de menus dans l'aperçu du rapport pour :

-   Naviguer entre les pages
-   Effectuer un zoom avant et arrière
-   Redimensionner à la taille de la page
-   Sélectionner du texte

    Vous pouvez copier le texte d'un rapport puis le coller ailleurs, comme dans une page de [!INCLUDE[d365fin](includes/d365fin_md.md)] ou Microsoft Word.  Avec la souris, par exemple, appuyez et maintenez la pression là où vous souhaitez démarrer, puis déplacez la souris pour sélectionner un ou plusieurs mots, phrases ou paragraphes. Vous pouvez ensuite appuyer sur le bouton droit de la souris et sélectionner **Copier**. Vous pouvez coller le texte sélectionné partout où vous le souhaitez.
-   Faire défiler le document

    Vous pouvez déplacer la zone visible du rapport dans n'importe quelle direction de manière voir d'autres zones ou le rapport. Ceci est utile si vous avez effectué un zoom pour observer les détails.  À l'aide de la souris, par exemple, appuyez et maintenez le bouton de la souris enfoncé n'importe où dans l'aperçu du rapport, puis déplacez la souris.

-   Téléchargez un fichier PDF sur votre ordinateur ou votre réseau.
-   Imprimer

## <a name="saving-a-report"></a>Enregistrement d'un rapport
Vous pouvez enregistrer un rapport dans un document PDF, un document Microsoft Word ou un document Microsoft Excel en sélectionnant le bouton **Envoyer à**, puis en effectuant votre sélection.

## <a name="scheduling-a-report-to-run"></a><a name="ScheduleReport"></a> Programmation d'un rapport à exécuter
Vous pouvez programmer ou traiter en lot un rapport à exécuter à une date et une heure spécifiques. Les rapports ou les traitements en lot programmés sont entrés dans la file d'attente des travaux et traités au moment programmé, comme les autres projets. Vous devez choisir l'option **Programmé** après avoir cliqué sur le bouton **Envoyer à**, puis vous devez entrer des informations telles que l’imprimante, l’heure et la date. Le rapport est alors ajouté à la file d'attente des travaux et sera exécuté au moment spécifié. Lorsque le rapport a été traité, l'article est supprimé de la file d'attente projets. Pour plus d'informations, voir [Utiliser des files d'attente des travaux pour programmer des tâches](admin-job-queues-schedule-tasks.md).

Vous pouvez choisir de sauvegarder le rapport traité dans un fichier, par exemple, Excel, Word ou PDF, de l'imprimer sur une imprimante sélectionnée ou de traiter le rapport uniquement. Si vous choisissez d'enregistrer le rapport dans un fichier, le rapport traité est envoyé à la zone **Boîte de réception rapport** sur votre tableau de bord, où vous pouvez l'afficher.

## <a name="printing-a-report"></a><a name="PrintReport"></a>Impression d'un rapport
Vous pouvez imprimer un rapport en cliquant sur le bouton **Impression** sur la page de demande de rapport ou dans la barre de menu sur la page **Aperçu**.

Comme [!INCLUDE[prodshort](includes/prodshort.md)] est un service nuage, il ne peut pas atteindre les imprimantes locales connectées aux machines des utilisateurs. Cependant, il peut se connecter aux imprimantes nuage. Dans la version générique de [!INCLUDE[prodshort](includes/prodshort.md)], une imprimante nuage nommée **Imprimante par courriel** est installée en tant qu'extension et prête à l'emploi après la configuration initiale.

Si aucune imprimante nuage n'est installée et configurée ou si une imprimante installée échoue, l'impression reprend par défaut les options d'impression du navigateur. Ceci est indiqué par cette valeur dans le champ **Imprimante** sur la page de demande de rapport : *(aucune, gestion par le navigateur)*.

Sur la page **Gestion des imprimantes**, vous pouvez voir les imprimantes configurées. Pour en savoir plus, consultez [Paramétrage imprimantes](ui-specify-printer-selection-reports.md).

> [!NOTE]
> Vous ne pouvez pas modifier le champ **Imprimante** sur la page de demande de rapport. Pour utiliser une autre imprimante, vous devez la sélectionner sur la page **Gestion des imprimantes**.

### <a name="printing-reports-in-thai"></a>Impression de rapports en thaïlandais
Spécifiquement pour la version thaïlandaise de [!INCLUDE[prodshort](includes/prodshort.md)], le bouton **Imprimer** ne peut pas imprimer correctement des rapports en raison des limitations du service qui génère le fichier PDF imprimable. À la place, vous pouvez ouvrir le rapport dans Word puis l'enregistrer en tant que fichier PDF imprimable.  

Sinon, vous pouvez demander à votre administrateur de créer une présentation rapport Word pour vos rapports les plus utilisés. Pour plus d'informations, voir [Gestion des présentations de rapport et de document](ui-manage-report-layouts.md).  

## <a name="changing-report-layouts"></a>Modification des présentations de rapport
Une présentation de rapport contrôle les éléments affichés sur un rapport, leur agencement et leur mise en forme. Si vous souhaitez changer de présentation, voir [Modifier la présentation actuelle du rapport](ui-how-change-layout-currently-used-report.md). Ou, si vous souhaitez personnaliser votre propre présentation de rapport, voir [Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md).

## <a name="see-also"></a>Voir aussi
[Paramétrage imprimantes](ui-specify-printer-selection-reports.md)  
[Utilisation de dates civiles et les heures](ui-enter-date-ranges.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
