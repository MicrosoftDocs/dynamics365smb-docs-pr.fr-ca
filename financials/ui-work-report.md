---
title: "Programmation d'un rapport à exécuter à une date et une heure spécifiques | Microsoft Docs"
description: "En savoir plus sur l'entrée d'un rapport dans une file d'attente de projets et la programmation de son traitement à une date et une heure spécifiques."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: task, process, report
ms.date: 07/06/2017
ms.author: jswymer
ms.translationtype: HT
ms.sourcegitcommit: ba26b354d235981bd7291f9ac6402779f554ac7a
ms.openlocfilehash: 16c9c8c896e3517f08a7326eef88ebc646834b1a
ms.contentlocale: fr-ca
ms.lasthandoff: 11/10/2017

---
# <a name="working-with-reports"></a>Utilisation des rapports
Un rapport regroupe des informations en fonction d'un ensemble de critères spécifié, et organise et présente les informations dans un format imprimable et facilement lisible. Il existe de nombreux rapports accessibles dans l'ensemble de l'application. Les rapports fournissent généralement des informations relatives au contexte de la page où vous vous trouvez. Par exemple, la page **Client** comprend des rapports pour les 10 principaux clients et les statistiques de vente, et plus encore.

Vous pouvez rechercher des rapports dans l'onglet **Rapports** des pages sélectionnées, ou vous pouvez utiliser la recherche pour rechercher des rapports par leur nom. Lorsque vous ouvrez un rapport, vous voyez d'abord une page qui vous permet de spécifier des informations (des options et des filtres) qui déterminent ce que vous souhaitez inclure dans le rapport. Par exemple, selon le rapport, vous pouvez spécifier une plage de dates, un enregistrement particulier tel qu'un client, ou effectuer un tri. Voici un exemple :

![Options de rapport](media/report_options.png "Options de rapport")

## <a name="previewing-a-report"></a>Affichage de l'aperçu d'un rapport
Sélectionnez **Aperçu** pour visualiser le rapport dans le navigateur Internet. Pointez un zone du rapport pour afficher la barre de menus.  

![Barre d'outils Aperçu du rapport](media/report_viewer.png "Barre d'outils Aperçu du rapport")

Utilisez la barre de menus pour :

-   Naviguer entre les pages
-   Effectuer un zoom avant et arrière
-   Redimensionner à la taille de la fenêtre
-   Sélectionner du texte

    Vous pouvez copier le texte d'un rapport puis le coller ailleurs, comme dans une page de [!INCLUDE[d365fin](includes/d365fin_md.md)] ou Microsoft Word.  Avec la souris, par exemple, appuyez et maintenez la pression là où vous souhaitez démarrer, puis déplacez la souris pour sélectionner un ou plusieurs mots, phrases ou paragraphes. Vous pouvez ensuite appuyer sur le bouton droit de la souris et sélectionner **Copier**. Vous pouvez coller le texte sélectionné partout où vous le souhaitez.
-   Faire défiler le document

    Vous pouvez déplacer la zone visible du rapport dans n'importe quelle direction de manière voir d'autres zones ou le rapport. Ceci est utile si vous avez effectué un zoom pour observer les détails.  À l'aide de la souris, par exemple, appuyez et maintenez le bouton de la souris enfoncé n'importe où dans l'aperçu du rapport, puis déplacez la souris.

-   Téléchargez un fichier PDF sur votre ordinateur ou votre réseau.
-   Imprimer


## <a name="saving-a-report"></a>Enregistrement d'un rapport
Vous pouvez enregistrer un rapport dans un document PDF, un document Microsoft Word ou un document Microsoft Excel en sélectionnant **Envoyer à**, puis en effectuant votre sélection.

## <a name="ScheduleReport"></a> Programmation d'un rapport à exécuter
Vous pouvez programmer un rapport à exécuter à une date et une heure spécifiques. Les rapports prévus sont entrés dans la file d'attente projets et traités au moment prévu, comme les autres projets. Vous pouvez choisir de sauvegarder le rapport traité dans un fichier, par exemple, Excel, Word ou PDF, de l'imprimer sur une imprimante sélectionnée ou de traiter le rapport uniquement. Si vous choisissez d'enregistrer l'état dans un fichier, alors l'état traité est envoyé à la **Boîte de réception état** de votre page d'accueil, dans laquelle vous pouvez l'afficher.

Vous pouvez programmer un rapport lorsque vous l'ouvrez. Vous devez sélectionner **Planifier** et entrer des informations telles que l'imprimante, ainsi que la date et l'heure. Le rapport est alors ajouté à la file d'attente des travaux et sera exécuté au moment spécifié. Lorsque le rapport a été traité, l'article est supprimé de la file d'attente projets. Si vous avez enregistré l'état traité dans un fichier, il est disponible dans la **Boîte de réception état**.

## <a name="PrintReport"></a>Impression d'un rapport
Vous pouvez imprimer un rapport à l'aide du bouton **Imprimer** sur la page d'options qui s'affiche lorsque vous ouvrez le rapport ou dans la barre de menu dans l'aperçu.

## <a name="using-saved-settings"></a>Utilisation des paramètres enregistrés
Un rapport peut inclure une ou plusieurs écritures dans la zone **Paramètres enregistrés**. Les *Paramètres enregistrés* sont fondamentalement un groupe prédéfini d'options et de filtres que vous pouvez appliquer au rapport avant d'en afficher un aperçu ou de l'envoyer vers un fichier. Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates.

L'écriture de paramètres enregistrés appelée **Options et filtres récemment utilisés** est toujours disponible. Cette écriture permet de faire en sorte que le rapport réutilise les options et les filtres utilisés la dernière fois que vous l'avez consulté.

>[!NOTE]
>En tant qu'administrateur, vous pouvez créer et gérer les paramètres enregistrés pour les rapports pour tous les utilisateurs. Pour plus d'informations, voir [Gestion des paramètres enregistrés dans les rapports](reports-saving-reusing-settings.md).

## <a name="changing-the-layout-and-look-of-a-report"></a>Modification de la présentation et de l'apparence d'un rapport
Une présentation de rapport contrôle les éléments affichés sur un rapport, leur agencement et leur mise en forme. Si vous souhaitez changer de présentation, voir [Procédure : modification de la présentation actuellement utilisée sur un rapport](ui-how-change-layout-currently-used-report.md). Ou, si vous souhaitez personnaliser votre propre présentation de rapport, voir [Procédure : créer et modifier une présentation de rapport personnalisée](ui-how-create-custom-report-layout.md).

## <a name="see-also"></a>Voir aussi
[Spécifier la sélection de l'imprimante pour les états](ui-specify-printer-selection-reports.md)  
[Gestion des présentations de rapport et de document](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[d365fin_long](includes/d365fin_long_md.md)]](ui-work-product.md)

