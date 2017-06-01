---
title: "Paramètres enregistrés dans les états"
description: "Décrit comment utiliser les paramètres enregistrés dans les rapports."
services: project-madeira
documentationcenter: 
author: jswymer
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customization, personalization
ms.date: 12/12/2016
ms.author: jswymer
ms.translationtype: Human Translation
ms.sourcegitcommit: a31be0f9d07e2abb591e26f6bae34c6f6e4dcda6
ms.openlocfilehash: 7afbd31e77a4f53ee99fbb192dd8a32a660f87eb
ms.contentlocale: fr-ca
ms.lasthandoff: 05/04/2017


---
# <a name="saved-settings-on-reports"></a>Paramètres enregistrés dans les états
En fonction du rapport exécuté, vous pouvez bénéficier d'une page qui vous laisse définir certaines options et certains filtres pour modifier les données incluses dans le rapport généré. Cette page est connue comme la page de demande du rapport. Un état peut inclure un ou plusieurs *paramètres enregistrés* que vous pouvez appliquer à l'état à partir de la page de demande. Les *Paramètres enregistrés* sont essentiellement des options et des filtres prédéfinis. Le fait d'utiliser les paramètres enregistrés est une façon rapide et fiable de générer de façon cohérente des états qui contiennent les données adéquates.

Vous pouvez voir les paramètres enregistrés qui sont à votre disposition pour un état dans la section **Paramètres enregistrés** de la page de demande de l'état.  

## <a name="to-apply-saved-settings-to-a-report"></a>Pour appliquer des paramètres enregistrés à un rapport
1. Ouvrez le rapport.

   La page de demande du rapport s'affiche.    
2. Dans la section **Paramètres enregistrés** de la page, définissez le champ **Nom** dans les paramètres enregistrés que vous souhaitez utiliser.

   La section **Paramètres enregistrés** apparaît uniquement si l'état a été exécuté avant ou s'il y a des écritures de paramètres enregistrées. L'écriture de paramètres enregistrés appelée **Options et filtres récemment utilisés** est toujours disponible. Ces paramètres sont les valeurs d'option et de filtre qui ont été utilisées la dernière fois que vous avez exécuté le rapport.

## <a name="administer-saved-report-settings-for-users"></a>Administrer les paramètres de rapport enregistrés pour les utilisateurs
Si vous avez les bonnes autorisations, vous pouvez visualiser, créer et modifier les paramètres enregistrés pour tous les rapports pour tous les utilisateurs de la compagnie. Vous pouvez attribuer les paramètres enregistrés d'un rapport à des utilisateurs en particulier ou à tous les utilisateurs de la compagnie.

Vous gérez les paramètres enregistrés à partir de la page 1506 **Paramètres des états**. Pour ouvrir cette page, dans le coin supérieur droit, sélectionnez l'icône **Page ou état pour la recherche** ![Page ou état pour la recherche](media/ui-search/search_small.png "Icône Page ou état pour la recherche"), entrez **Paramètres d'état**, puis sélectionnez le lien associé.

Sur la page **Paramètres d'état**, vous pouvez créer de nouveaux paramètres à partir de zéro ou vous pouvez effectuer une copier et modifier des paramètres existants. Pour modifier les options et les filtres pour un paramètre, sélectionnez l'action **Modifier**.

**Remarque :**

* la fonctionnalité des paramètres enregistrés des états n'est appropriée que lorsque la propriété SaveValues de la page de demande est définie sur Oui. La propriété SaveValues est définie dans l'environnement de développement.
* Si vous créez un article de paramètres enregistrés pour tous les utilisateurs, et qu'il porte le même nom que les paramètres enregistrés existants pour un utilisateur spécifique, alors cet utilisateur ne pourra pas utiliser les paramètres enregistrés affectés à tous.  Dans le champ Paramètres enregistrés de la page de demande de rapport, l'utilisateur verra deux options de paramètres enregistrées avec le même nom. Toutefois, peu importe l'option qu'il choisit, les paramètres enregistrés qui lui sont spécifiques seront utilisés.

## <a name="see-also"></a>Voir aussi
[Planifier un état à exécuter](ui-schedule-report.md)  

