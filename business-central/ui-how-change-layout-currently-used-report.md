---
title: Modifier l'aspect d'un rapport en sélectionnant une présentation différente | Microsoft Docs
description: Vous pouvez utiliser différentes présentations d'un rapport, et passer d'une présentation à l'autre pour modifier l'aspect d'un rapport.
services: project-madeira
documentationcenter: ''
author: jswymer
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 10/01/2018
ms.author: jswymer
ms.openlocfilehash: a68c26e94aa4adda7c1f546e57331a741dcfe94b
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "814227"
---
# <a name="change-which-layout-is-currently-used-on-a-report"></a>Modification de la présentation actuellement utilisée sur un rapport
Un rapport peut être créé avec plus d'une présentation de rapport, que vous pouvez ensuite changer au besoin.

Selon les présentations qui sont disponibles pour un rapport, vous pouvez choisir d'utiliser une présentation de rapport RDLC intégrée, une présentation de rapport Word, ou une présentation personnalisée. Pour plus d'informations sur les présentations de rapport RDLC et Word, les présentations intégrées et personnalisées, et plus encore, reportez-vous à [Gérer la présentation des états](ui-manage-report-layouts.md).

## <a name="to-change-the-layout-that-is-used-on-a-report"></a>Pour modifier la présentation qui est utilisée dans un rapport
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Sélection présentation rapport**, puis sélectionnez le lien associé.  
   La page **Sélection présentation rapport** répertorie tous les rapports disponibles pour la compagnie spécifiée dans le champ Compagnie en haut de la page. Le champ Présentation sélectionnée spécifie la présentation qui est actuellement utilisée sur le rapport.
2. Définissez le champ **Compagnie** en haut de la page sur la compagnie qui inclut le rapport.
3. Pour modifier la présentation utilisée par un état, sur la ligne correspondant à l'état dans la liste, définissez le champ **Présentation sélectionnée** sur l'une des options suivantes :
   * RDLC (intégré), utilise la présentation de rapport RDLC intégrée sur le rapport.
   * Word (intégré), utilise la présentation de rapport Word intégrée sur le rapport.
   * Personnalisée, utilise une présentation personnalisée sur le rapport.  
     Il est possible de savoir quelles sont les présentations personnalisées disponibles pour le rapport dans le récapitulatif Partie présentations rapport. S'il n'existe aucune présentation personnalisée pour le rapport, alors vous devez d'abord en créer une. Si vous choisissez cette option, rendez-vous à la procédure suivante pour spécifier la présentation personnalisée que vous souhaitez utiliser.

    > [!NOTE]  
    >   Si vous choisissez **RDLC (intégré)** ou **Word (intégré)** et si vous recevez un message d'erreur indiquant que le rapport n'a pas de présentation du type spécifié, alors vous devez choisir une autre option de présentation ou créer une présentation de rapport personnalisée du type que vous souhaitez utiliser.

Si vous avez sélectionné une présentation de rapport RDLC ou Word intégrée, aucune action supplémentaire n'est requise et la présentation sera utilisée la prochaine fois que le rapport sera exécuté.

## <a name="to-specify-a-custom-layout-on-a-report"></a>Pour spécifier une présentation personnalisé sur un rapport
1. Vous spécifiez la présentation personnalisée à utiliser dans le rapport à partir de la page **Présentations rapport personnalisées**. Si la page **Présentations rapport personnalisées** n'est pas ouverte, cliquez sur le bouton de consultation du champ **Description présentation rapport**.
2. Sur la page **Présentations rapport personnalisées**, sélectionnez la ligne de la présentation personnalisée que vous souhaitez utiliser, puis fermez la page.

La page **Sélection présentation rapport** s'affiche à nouveau. Le nom de la présentation personnalisée sélectionnée s'affiche dans le champ **Description présentation personnalisée**. La présentation personnalisée sera utilisée la prochaine fois que vous exécuterez le rapport.

## <a name="see-also"></a>Voir aussi
[Gestion des présentations de rapport](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
