---
title: Ajouter un signet à un lien vers une page ou un rapport sur votre tableau de bord | Microsoft Docs
description: Découvrez comment ajouter un lien à votre tableau de bord.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 1bcbd23658ff2a74ae0ab88b6020e1d859f37355
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4747728"
---
# <a name="bookmark-a-page-or-report-on-your-role-center"></a>Ajouter un signet vers une page ou un rapport sur votre tableau de bord
À l'aide de l'icône de signet, vous pouvez ajouter une action qui ouvre une page ou un rapport à partir du menu de navigation de votre tableau de bord. Cela vous permet d'accéder rapidement à votre contenu préféré ou à vos tâches professionnelles. Vous devez ajouter le signet à partir de la page ou du rapport cible, c'est-à-dire l'écran sur lequel vous souhaitez que le lien du tableau de bord s'ouvre.

L'icône de signet est affichée dans le coin supérieur droit d'une page et également dans la fenêtre **Tell Me** où vous pouvez marquer plusieurs pages ou rapports efficacement. Si un signet existe déjà pour la page, l'icône est sombre et l'info-bulle indique « Mis en favori ».

## <a name="to-bookmark-the-target-page"></a>Pour ajouter un signet à la page cible
1. Ouvrez n'importe quelle page pour laquelle vous souhaitez un lien sur votre tableau de bord.
2. Choisissez l'icône ![Signet](media/ui_bookmark_icon.png "Signet").

Un nom d'action après la page est maintenant ajouté au menu de navigation de votre tableau de bord.

## <a name="to-bookmark-the-target-report"></a>Pour ajouter un signet au rapport cible
1. Ouvrez n'importe quelle page de demande de rapport pour laquelle vous souhaitez un lien sur votre tableau de bord.
2. Choisissez l'icône ![Signet](media/ui_bookmark_icon.png "Signet").

Un nom d'action après le rapport est maintenant ajouté au menu de navigation de votre tableau de bord.

## <a name="to-bookmark-a-page-or-report-from-the-tell-me-window"></a>Pour ajouter un signet à une page ou à un rapport à partir de la fenêtre Tell me
1. Ouvrez la fenêtre **Tell Me** et entrez, par exemple, **Documents de vente**.
2. Passez votre souris sur le résultat de la recherche pour la page ou le rapport **Documents de vente**, puis choisissez l'icône ![Signet](media/ui_bookmark_icon.png "Signet").

Un nom d'action après la page ou le rapport est maintenant ajouté au menu de navigation de votre tableau de bord.


## <a name="frequently-asked-questions"></a>Forum Aux Questions  

- **Puis-je réorganiser mes signets ?**  
Oui. Vous pouvez personnaliser votre tableau de bord et déplacer les actions dans un ordre plus optimal ou les déplacer dans des groupes ou sous-groupes existants.  
Découvrez comment [Personnaliser votre espace de travail](ui-personalization-user.md).

- **Comment supprimer un signet ?**  
Sur la page ou le rapport cible, choisissez à nouveau l'icône de signet pour supprimer l'action impliquée de votre tableau de bord. Vous pouvez également personnaliser votre tableau de bord et masquer temporairement les actions sans les supprimer complètement.

- **Où puis-je trouver mes signets ?**  
Lors de l'ajout d'un signet à une page ou à un rapport, la nouvelle action est ajoutée au menu de navigation supérieur de votre écran d'accueil actuel (tableau de bord). Si vous avez de nombreuses actions, vous devrez peut-être activer le bouton **Plus** pour les afficher toutes, car la nouvelle action est toujours ajoutée à la fin de ces actions.
<!-- Should we add a screenshot here? -->

- **Je n'ai pas d'icône de signet. Qu'est-ce qui ne va pas ?**  
La possibilité d'ajouter un signet à une page ou à un rapport est l'une des nombreuses fonctionnalités de personnalisation de l'utilisateur dans Business Central. Si l'icône de signet ne s'affiche pas, il est probable que votre administrateur ait désactivé la personnalisation.

- **Pourquoi ne puis-je pas ajouter un signet à certaines pages ou à certains rapports?**  
Toutes les pages et tous les rapports ne peuvent pas être mis en signet. Lorsqu'une page ou un rapport est exécuté dans un contexte spécial régi par l'application métier, l'icône de signet ne s'affiche pas. Par exemple, les pages qui sont introuvables dans la fenêtre **Rechercher**, mais qui sont lancées depuis un autre emplacement, n’afficheront pas d’icône de signet. De même, les pages de demande de rapport utilisées uniquement pour collecter des filtres sans exécuter le rapport n'afficheront pas d'icône de signet.

Voir les détails techniques sur [RunRequestPage](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/methods-auto/report/reportinstance-runrequestpage-method) et [FilterPageBuilder](https://docs.microsoft.com/dynamics365/business-central/dev-itpro/developer/methods-auto/filterpagebuilder/filterpagebuilder-data-type).

- **Lors de la suppression de ma personnalisation, mes signets seront-ils également supprimés ?**  
Oui. Les signets résident dans le menu de navigation. Si vous effacez les modifications apportées au menu de navigation à partir de n'importe quelle page, ou si vous supprimez toute personnalisation dans le tableau de bord, toutes vos nouvelles actions seront définitivement supprimées.

- **Pourquoi l'icône de signet continue-t-elle d'indiquer qu'elle n'est toujours pas signée ?**  
Lorsque vous ajoutez un signet, la nouvelle action est ajoutée au menu de navigation du tableau de bord et les visites suivantes sur la page ou le rapport affichent une icône de signet foncée. Si vous personnalisez votre tableau de bord et réorganisez vos actions en les déplaçant en groupes, l'icône de signet ne sera plus foncée et vous pourrez ajouter un autre signet à cette même page ou à ce même rapport. Cela vous permet d'ajouter plusieurs actions à la même page ou au même rapport et de les classer en différents groupes.

- **Pourquoi mon lien vers un rapport affiche-t-il un rapport différent?**  
Certains rapports peuvent être remplacés par d'autres rapports après avoir appliqué une extension à Business Central. En cas de substitution, le texte de la nouvelle action n'est pas mis à jour et continuera d'afficher le nom du rapport d'origine, mais accèdera au rapport le plus récent. Pour corriger le texte de la nouvelle action, vous pouvez supprimer la nouvelle action et l'ajouter à nouveau.
<!-- For more information on report substitution, see this link UNAVAILABLE AT THIS TIME -->

- **Le signet est-il disponible pour XMLports ?**  
Non. Pour le moment, l'ajout d'actions pour ouvrir XMLports n'est pas possible à partir de l'interface utilisateur.

- **Mes signets seront-ils traduits lorsque je changerai ma langue dans Business Central ?**  
Lorsqu'une nouvelle action est ajoutée, tout texte traduit qui était disponible à ce moment est également mis en signet. Si un nouveau texte traduit est ajouté ultérieurement, la nouvelle action n'inclura pas les traductions les plus récentes.


## <a name="see-also"></a>Voir aussi
[Personnaliser votre espace de travail](ui-personalization-user.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Modifier les paramètres de base](ui-change-basic-settings.md)  
[Modifier les fonctionnalités affichées](ui-experiences.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]