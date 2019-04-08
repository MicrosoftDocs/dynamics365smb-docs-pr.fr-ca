---
title: Programmation d'un rapport à exécuter à une date et une heure spécifiques | Microsoft Docs
description: En savoir plus sur l'intégration d'un rapport dans une file d'attente des travaux et la programmation de son traitement à une date et une heure spécifiques.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report
ms.date: 10/01/2018
ms.author: jswymer
ms.openlocfilehash: 98d51b10d3ca415a463b58405cb3c4f2449b75ad
ms.sourcegitcommit: d09f5ee0e164c7716f4ccb2ed71e2f9732a1f4f9
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/19/2019
ms.locfileid: "852434"
---
# <a name="working-with-reports-and-batch-jobs"></a>Utilisation des rapports et des traitements en lot
Un rapport regroupe des informations en fonction d'un ensemble de critères spécifié, et organise et présente les informations dans un format imprimable et facilement lisible. Il existe de nombreux rapports accessibles dans l'ensemble de l'application. Les rapports fournissent généralement des informations relatives au contexte de la page où vous vous trouvez. Par exemple, la page **Client** comprend des rapports pour les 10 principaux clients et les statistiques de vente, et plus encore.

Les traitements en lot sont plus ou moins identiques aux rapports mais ils ont pour objectif d'exécuter un processus. Par exemple, le traitement en lot **Créer des rappels** crée des rappels pour les clients ayant des paiements échus.  

> [!NOTE]
> Cette rubrique fait principalement référence aux « rapports », mais des informations similaires s'appliquent aux traitements en lot.

Vous pouvez rechercher des rapports dans l'onglet **Rapports** sur les pages sélectionnées, ou utiliser la recherche ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") pour rechercher les rapports par nom.


## <a name="specifying-the-data-to-include-in-the-report"></a>Définition des données à inclure dans le rapport
Lorsque vous ouvrez un rapport, une page s'affiche généralement pour vous permettre de définir plusieurs options et filtres qui déterminent les éléments à inclure dans le rapport. Cette page est appelée la page de demande du rapport. Par exemple, la page de demande du rapport vous permet de créer un rapport pour un client spécifique, une plage de dates spécifique, ou encore de définir l'ordre des informations dans le rapport. Voici un exemple de page de demande du rapport :

![Options de rapport](media/report_options.png "Options de rapport")

> [!Caution]
> La section **Afficher résultats** sur une page de demande propose une fonctionnalité de filtrage générique pour les rapports. Ces filtres sont optionnels.<br /><br /> Certains rapports ignoreront ces filtres, ce qui signifie que quel que soit le filtre défini dans la section **Afficher résultats**, la sortie du rapport est identique. Il est impossible de fournir une liste des champs ignorés dans les rapports, vous devez donc expérimenter avec des filtres lorsque vous les utiliserez.<br /><br />
**Exemple** : Lorsque vous utilisez le traitement en lot **Créer rappels**, un filtre pour le champ **Écritures client** de **Niveau dernier rappel émis** sera ignoré, car les filtres sont fixes pour ce traitement en lot.

### <a name="SavedSettings"></a>Utilisation des paramètres enregistrés
Avec certains rapports, selon la manière dont ils sont conçus, la page de rapport peut inclure la section **Paramètres enregistrés** qui contient une ou plusieurs entrées dans la zone **Utiliser les valeurs par défaut de**. Les entrées de cette zone sont appelées *paramètres enregistrés*. Un paramètre enregistré est fondamentalement un groupe prédéfini d'options et de filtres que vous pouvez appliquer au rapport avant d'en afficher un aperçu ou de l'envoyer vers un fichier. L'écriture de paramètres enregistrés appelée **Options et filtres récemment utilisés** est toujours disponible. Cette écriture permet de faire en sorte que le rapport réutilise les options et les filtres utilisés la dernière fois que vous l'avez consulté.

Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates. Après avoir défini la zone **Utiliser les valeurs par défaut de** sur une entrée de paramètres enregistrés, vous pouvez modifier les options et les filtres avant d'afficher un aperçu ou d'enregistrer le rapport. Vos modifications ne seront pas enregistrées dans l'entrée de paramètres enregistrés que vous avez sélectionnée, mais elles seront sauvegardées dans la zone **Options et filtres récemment utilisés**.

>[!NOTE]
>Si vous êtes un administrateur, vous pouvez créer et gérer les paramètres enregistrés des rapports pour tous les utilisateurs. Pour plus d'informations, voir [Gestion des paramètres enregistrés dans les rapports](reports-saving-reusing-settings.md).

### <a name="setting-options-and-filters"></a>Définition des options et des filtres
Si vous souhaitez limiter davantage ou localiser les données incluses dans un rapport, vous pouvez définir des options et des filtres supplémentaires.

Les filtres vous permettent d'afficher les données selon des critères spécifiques. Les filtres sont regroupés selon l'entité à laquelle ils appartiennent, par exemple **Client** dans l'illustration ci-dessus. Vous spécifiez un filtre en définissant la zone **Où** sur le champ de filtre, puis en ajoutant les critères dans la zone **est :**. Par exemple, dans l'illustration ci-dessus, un filtre unique crée un rapport pour le client dont le **N°** est égal à **01121212**.

Vous pouvez ajouter d'autres filtres en définissant les zones **Ajouter**. Lorsque vous avez défini plusieurs filtres, seuls les résultats qui répondent aux critères de tous les filtres seront inclus dans le rapport.

Selon le champ de type que vous filtrez, vous pouvez spécifier les critères de filtre pour rechercher une correspondance exacte, une correspondance partielle, une plage de valeurs, etc. Pour obtenir de l'aide sur la configuration des filtres, voir :
-   [filtres](ui-enter-criteria-filters.md#FilterCriteria) ;
-   [Utilisation de dates civiles et les heures](ui-enter-date-ranges.md)

## <a name="previewing-a-report"></a>Affichage de l'aperçu d'un rapport
Sélectionnez **Aperçu** pour visualiser le rapport dans le navigateur Internet. Pointez un zone du rapport pour afficher la barre de menus.  

![Barre d'outils Aperçu du rapport](media/report_viewer.png "Barre d'outils Aperçu du rapport")

Utilisez la barre de menus pour :

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
Vous pouvez enregistrer un rapport dans un document PDF, un document Microsoft Word ou un document Microsoft Excel en sélectionnant **Envoyer à**, puis en effectuant votre sélection.

## <a name="ScheduleReport"></a> Programmation d'un rapport à exécuter
Vous pouvez programmer un rapport à exécuter à une date et une heure spécifiques. Les rapports prévus sont entrés dans la file d'attente projets et traités au moment prévu, comme les autres projets. Vous pouvez choisir de sauvegarder le rapport traité dans un fichier, par exemple, Excel, Word ou PDF, de l'imprimer sur une imprimante sélectionnée ou de traiter le rapport uniquement. Si vous choisissez d'enregistrer le rapport dans un fichier, le rapport traité est envoyé à la zone **Boîte de réception rapport** sur votre tableau de bord, où vous pouvez l'afficher.

Vous pouvez programmer un rapport lorsque vous l'ouvrez. Vous devez sélectionner **Planifier** et entrer des informations telles que l'imprimante, ainsi que la date et l'heure. Le rapport est alors ajouté à la file d'attente des travaux et sera exécuté au moment spécifié. Lorsque le rapport a été traité, l'article est supprimé de la file d'attente projets. Si vous avez enregistré l'état traité dans un fichier, il est disponible dans la **Boîte de réception état**.

## <a name="PrintReport"></a>Impression d'un rapport
Vous pouvez imprimer un rapport à l'aide du bouton **Imprimer** sur la page d'options qui s'affiche lorsque vous ouvrez le rapport ou dans la barre de menu dans l'aperçu.

## <a name="changing-the-layout-and-look-of-a-report"></a>Modification de la présentation et de l'apparence d'un rapport
Une présentation de rapport contrôle les éléments affichés sur un rapport, leur agencement et leur mise en forme. Si vous souhaitez changer de présentation, voir [Modification de la présentation actuellement utilisée sur un rapport](ui-how-change-layout-currently-used-report.md). Ou, si vous souhaitez personnaliser votre propre présentation de rapport, voir [Créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md).

## <a name="see-also"></a>Voir aussi
[Spécifier la sélection de l'imprimante pour les états](ui-specify-printer-selection-reports.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
