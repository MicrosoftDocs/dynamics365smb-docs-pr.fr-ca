---
title: Modifier l'aspect d'un rapport en sélectionnant une présentation différente | Microsoft Docs
description: Vous pouvez utiliser différentes présentations d'un rapport, et passer d'une présentation à l'autre pour modifier l'aspect d'un rapport.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: customized report, document layout, logo, personalize
ms.date: 04/01/2020
ms.author: edupont
ms.openlocfilehash: 9dc74627139ceed4f475686d57b64737e7e42b47
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3789360"
---
# <a name="change-the-current-report-layout"></a>Modifier la présentation actuelle du rapport
Un rapport peut être créé avec plus d'une présentation de rapport, que vous pouvez ensuite changer au besoin.

Selon les présentations qui sont disponibles pour un rapport, vous pouvez choisir d'utiliser une présentation de rapport RDLC intégrée, une présentation de rapport Word, ou une présentation personnalisée. Pour plus d'informations sur les présentations de rapport RDLC et Word, les présentations intégrées et personnalisées, et plus encore, reportez-vous à [Gérer la présentation des états](ui-manage-report-layouts.md).

Lorsque des présentations de rapport personnalisées sont définies, vous pouvez les sélectionner à partir des fiches client et fournisseur pour spécifier que les présentations sélectionnées sont utilisées pour les documents que vous créez pour le client ou le fournisseur en question. Pour plus d'informations, voir [Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md).

> [!TIP]  
> Les rapports de document (pas les listes) qui utilisent une mise en page de rapport Word sont généralement plus rapides que ceux qui utilisent une mise en page de rapport RDLC. Ainsi, si vous avez la possibilité de choisir entre une mise en page de rapport Word ou RDLC pour un rapport de document, utilisez la mise en page de rapport Word pour de meilleures performances.

## <a name="to-change-which-report-layout-to-use-for-a-report-or-document"></a>Pour modifier la présentation de rapport à utiliser pour un rapport ou un document
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Sélection de présentation de rapport**, puis sélectionnez le lien associé.  
   La page **Sélection de présentation de rapport** répertorie tous les rapports disponibles pour la compagnie spécifiée dans le champ **Compagnie** en haut de la page. Le champ **Présentation sélectionnée** spécifie la présentation qui est actuellement utilisée sur le rapport.
2. Définissez le champ **Compagnie** en haut de la page sur la compagnie qui inclut le rapport.
3. Pour modifier la présentation utilisée par un rapport, sur la ligne correspondant au rapport, définissez le champ **Présentation sélectionnée** sur l'une des options suivantes :
   * **RDLC (intégré)**, utilise la présentation de rapport RDLC intégrée sur le rapport.
   * **Word (intégré)**, utilise la présentation de rapport Word intégrée sur le rapport.
   * **Personnalisée**, utilise une présentation personnalisée sur le rapport.  

> [!NOTE]
> Si vous choisissez une présentation de rapport de type **RDLC (intégré)** ou **Word (intégré)** et si vous recevez un message d'erreur indiquant que le rapport n'a pas de présentation du type spécifié, alors vous devez choisir une autre option de présentation ou créer une présentation de rapport personnalisée du type que vous souhaitez utiliser. Consultez la procédure suivante.

Si vous avez sélectionné une présentation de rapport RDLC ou Word intégrée, aucune action supplémentaire n'est requise, et la présentation sera utilisée la prochaine fois que le rapport sera exécuté.

## <a name="to-change-the-custom-layout-to-use-for-a-report-layout"></a>Pour modifier la présentation personnalisée à utiliser pour une présentation de rapport
Vous pouvez également modifier la présentation personnalisée actuellement utilisée. Pour plus d'informations, voir [Créer et modifier des présentations de rapport personnalisées](ui-how-create-custom-report-layout.md).

Toutes les présentations de rapport personnalisées qui existent pour les présentations de rapport dans une compagnie sont répertoriées sur la page **Présentations de rapport personnalisées**. Sur la page **Sélection de présentation de rapport**, il est possible de savoir quelles présentations personnalisées sont disponibles pour chaque rapport dans le récapitulatif **Présentations personnalisées**.

1. Sur la page **Sélection de présentation de rapport**, sur la ligne de la présentation de rapport que vous souhaitez modifier, cliquez sur le bouton de recherche dans le champ **Description présentation personnalisée**.
2. Sur la page **Présentations de rapport personnalisées**, sélectionnez la ligne de la présentation personnalisée que vous souhaitez utiliser, puis cliquez sur le bouton **OK**.

Le nom de la présentation personnalisée sélectionnée s'affiche maintenant dans le champ **Description présentation personnalisée**, et sera utilisé la prochaine fois que le rapport ou le document sera prévisualisé, imprimé ou envoyé.

Vous pouvez maintenant accéder à vos fiches client et fournisseur pour spécifier les présentations à utiliser pour différents documents que vous créez pour le client ou le fournisseur en question, comme les confirmations de commande ou les rappels de paiement. Pour plus d'informations, voir [Définir des présentations de document pour les clients et les fournisseurs](ui-define-customer-vendor-document-layouts.md).

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/change-documents-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Gestion des présentations de rapport](ui-manage-report-layouts.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
