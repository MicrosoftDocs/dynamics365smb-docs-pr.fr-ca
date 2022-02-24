---
title: Affecter et modifier les paramètres enregistrés dans des rapports | Microsoft Docs
description: Décrit l'utilisation d'options et filtre prédéfinis pour personnaliser un rapport et pour générer les données exactes.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 04/01/2020
ms.author: sgroespe
ms.openlocfilehash: 4c43429e4436400dc9e3b991b9ccca59a439372a
ms.sourcegitcommit: 88e4b30eaf6fa32af0c1452ce2f85ff1111c75e2
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/01/2020
ms.locfileid: "3191893"
---
# <a name="manage-saved-settings-for-reports-and-batch-jobs"></a>Gérer les paramètres enregistrés pour les rapports et les traitements en lot
Lors de l'exécution d'un rapport, les utilisateurs voient généralement une page qui leur permet de sélectionner des options et de définir des filtres pour modifier les données incluses dans le rapport généré. Cette page est appelée la page de demande. Un rapport peut inclure un ou plusieurs *paramètres enregistrés* que les utilisateurs peuvent appliquer au rapport à partir de la page de demande. Les *Paramètres enregistrés* sont essentiellement des options et des filtres prédéfinis. Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates. Pour plus d'informations, voir [Utilisation des paramètres enregistrés](ui-work-report.md#SavedSettings).

> [!NOTE]
> Cette rubrique fait principalement référence aux « rapports », mais des informations similaires s'appliquent aux traitements en lot.

Si vous avez les bonnes autorisations, vous pouvez visualiser, créer et modifier les paramètres enregistrés pour tous les rapports pour tous les utilisateurs d'une compagnie. Vous pouvez attribuer les paramètres enregistrés d'un rapport à des utilisateurs en particulier ou à tous les utilisateurs de la compagnie.

<!--
## Apply saved settings to a report
1. Open the report.

   The request page appears.    
2. In the **Saved Settings** section of the page, set the **Name** field  to the saved settings that you want to use.

   The **Saved Settings** section only appears if the report has been run before or if there are existing saved settings entries. The saved settings entry called **Last used options and filters** is always available. These settings are the option and filter values that were used the last time you ran the report.

-->

## <a name="to-create-and-modify-saved-settings-for-all-users"></a>Pour créer et modifier les paramètres enregistrés pour tous les utilisateurs
Vous devez gérer les paramètres enregistrés à partir de la page **Paramètres des rapports**. Deux méthodes sont disponibles pour ouvrir cette page :
-   Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Paramètres des rapports**, puis sélectionnez le lien associé.
-   Ouvrez un rapport, sélectionnez la fonction de recherche dans le champ **Utiliser les valeurs par défaut de**, puis choisissez l'action **Sélectionner dans la liste complète**.

La page affiche toutes les entrées de paramètres enregistrés existants pour tous les utilisateurs. Si un nom d'utilisateur est indiqué dans le champ **Affecté à**, seul cet utilisateur peut utiliser les paramètres enregistrés pour le rapport associé. Si le champ **Partager avec tous les utilisateurs** est coché, tous les utilisateurs peuvent utiliser les paramètres enregistrés pour le rapport.

Dans la page **Paramètres du rapport**, vous pouvez :
-   Sélectionner l'action **Nouveau** pour créer une nouvelle entrée de paramètres enregistrés.
-   Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir l'action **Copier** pour créer une copie.
-   Sélectionner une entrée de paramètres enregistrés dans la liste, puis choisir l'action **Modifier** pour la modifier.

> [!Important]
> Définir le nom que vous souhaitez affecter à une entrée de paramètres enregistrés. Si vous créez une entrée de paramètres enregistrés pour tous les utilisateurs et vous lui donnez le même nom que l'entrée de paramètres enregistrés existants qui est affectée à un utilisateur spécifique, alors cet utilisateur ne pourra pas utiliser l'entrée de paramètres enregistrés qui est affectée à tous.  Dans la section **Paramètres enregistrés** dans la page de demande de l'état, l'utilisateur verra deux entrées de paramètres enregistrés avec le même nom. Toutefois, peu importe l'option qu'il choisit, l'entrée de paramètres enregistrés qui lui est spécifique sera utilisée.

> [!NOTE]
> La fonctionnalité Paramètres enregistrés n'est disponible que pour les rapports où la propriété [SaveValues](/dynamics365/business-central/dev-itpro/developer/properties/devenv-savevalues-property) de la page de demande du rapport est définie sur **Oui**. La propriété **SaveValues** est définie dans l'environnement de développement.  

## <a name="see-also"></a>Voir aussi
[Utilisation des rapports, des traitements en lot et des objets XMLport](ui-work-report.md)  
