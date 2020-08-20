---
title: Paramétrage d'états à imprimer sur des imprimantes spécifiques | Microsoft Docs
description: En savoir plus sur la configuration d'une imprimante pour un rapport et l'utilisation de la page Sélections d'imprimantes.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: online printing
ms.date: 04/17/2020
ms.author: sgroespe
ms.openlocfilehash: dc92c499aa201278abc0c8cdc351eeb1406b1cca
ms.sourcegitcommit: 99cecd005f8ede70e9a3d163a457fcb9aadb6843
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/10/2020
ms.locfileid: "3549877"
---
# <a name="set-up-printers"></a>Paramétrage imprimantes
Comme [!INCLUDE[prodshort](includes/prodshort.md)] est un service nuage, il ne peut pas atteindre les imprimantes locales connectées aux machines des utilisateurs. Cependant, il peut se connecter aux imprimantes nuage. Dans la version générique de [!INCLUDE[prodshort](includes/prodshort.md)], une imprimante nuage nommée **Imprimante par courriel** est installée en tant qu'extension et prête à l'emploi après la configuration initiale.

Si aucune imprimante nuage n'est installée et configurée ou si une imprimante installée échoue, l'impression reprend par défaut les options d'impression du navigateur. Ceci est indiqué par cette valeur dans le champ **Imprimante** sur la page de demande de rapport : *(aucune, gestion par le navigateur)*.

Sur la page **Gestion des imprimantes**, vous pouvez voir les imprimantes configurées. Après avoir configuré une ou plusieurs imprimantes, vous pouvez ouvrir la page **Sélections d'imprimantes** pour configurer les rapports spécifiques à imprimer avec l'imprimante de votre choix pour votre compte utilisateur.

Lorsqu'une imprimante est configurée et affectée à des rapports spécifiques, vous imprimez un rapport en cliquant sur le bouton **Imprimer** sur la page de demande de rapport. Pour en savoir plus, consultez [Impression d'un rapport](ui-work-report.md#PrintReport).

### <a name="sizing-print-jobs"></a>Dimensionnement des travaux d'impression
L'impression dans le nuage est conçue pour des documents de taille raisonnable. La plupart des services en nuage, y compris PrintNode et HP ePrint, ont une limite de 10 Mo par tâche. Si vous devez imprimer des rapports plus volumineux, vous devrez peut-être les diviser en plusieurs impressions.

## <a name="to-set-up-a-printer"></a>Pour configurer une imprimante
Sur la page **Gestion des imprimantes**, vous pouvez voir les imprimantes configurées et accéder à la page **Configuration** pour chaque imprimante, afin de modifier une configuration existante ou de configurer une nouvelle imprimante.

La procédure suivante décrit comment configurer l'imprimante existante **Imprimante par courriel**, qui est une extension préinstallée.

> [!NOTE]
> Pour utiliser l'impression par courriel, la fonctionnalité de messagerie doit être configurée. Pour plus d'informations, voir [Configurer la messagerie](admin-how-setup-email.md).

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Gestion des imprimantes**, puis sélectionnez le lien associé.
2. Sélectionnez la ligne pour l'imprimante **Imprimante par courriel**, puis l'action **Modifier les paramètres de l'imprimante**.
3. Sur la page **Paramètres**, renseignez les champs nécessaires. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

    > [!NOTE]
    > Vous devez sélectionner manuellement le format de papier approprié pour une imprimante, car aucune imprimante locale ni aucun paramètre utilisateur ne peuvent être stockés.
    >
    > Sachez que l'extension Imprimante par courriel est définie par défaut sur le format de papier **A4**, qui n'est pas adapté en Amérique du Nord, par exemple.
4. Pour faire d'une imprimante votre imprimante par défaut, choisissez l'action **Définir comme imprimante par défaut** sur la page **Gestion des imprimantes**.

### <a name="privacy-notice"></a>Déclaration de confidentialité
Si vous utilisez l'extension Imprimante par courriel, tout ou partie des travaux d'impression sont envoyés à l'adresse de courriel que vous avez fournie lors de la configuration de l'imprimante. Nous vous recommandons vivement d'associer un code courriel unique à un périphérique d'impression en utilisant uniquement les services officiels fournis par le fabricant du matériel, tels que HP ePrint, KonicaMinolta EveryonePrint ou Epson Email Print.

Vous devez prendre toutes les précautions de confidentialité nécessaires, notamment en veillant à configurer correctement les autorisations, les paramètres de confidentialité et les stratégies de conservation de la solution d'impression de courriels. Il est de votre responsabilité de fournir une adresse de courriel correcte, vérifiée et opérationnelle. Pour en savoir plus, consultez [Déclaration de confidentialité Microsoft](https://privacy.microsoft.com/en-us/privacystatement).

## <a name="to-select-which-printers-print-which-reports"></a>Pour sélectionner les imprimantes imprimant des rapports spécifiques

Sur la page **Sélections d'imprimantes**, vous pouvez configurer les rapports à imprimer sur des imprimantes spécifiques. Ceci est utile si vous utilisez différents rapports nécessitant différentes imprimantes en raison de leur placement dans la compagnie ou de leurs capacités d'impression.

> [!IMPORTANT]
> Pour [!INCLUDE[prodshort](includes/prodshort.md)] sur site, la page **Sélections d'imprimantes** ne peut être utilisée que pour les imprimantes définies par les extensions d'imprimante. Elle ne peut pas être utilisée pour les imprimantes locales.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Sélections d'imprimantes**, puis sélectionnez le lien associé. Sinon, sur la page **Gestion des imprimantes**, sélectionnez une imprimante, puis l'action **Sélections d'imprimantes**.
2. Choisissez l'action **Nouveau** pour ajouter une sélection d'imprimante pour un rapport spécifique.
3. Renseignez les champs selon vos besoins.

Le rapport spécifié est désormais configuré pour être imprimé sur l'imprimante sélectionnée par défaut.

> [!NOTE]
> Lorsque vous imprimez le rapport en question, vous pouvez remplacer cette configuration en sélectionnant une autre imprimante sur la page de demande **Configuration d'impression**.

> [!NOTE]
> Si vous ne configurez pas un rapport pour une imprimante spécifique sur la page **Sélections d'imprimantes**, il est imprimé sur l'imprimante par défaut de la compagnie, comme défini sur la page **Gestion des imprimantes**.

Vous ou l'administrateur pouvez également utiliser la page **Sélections d'imprimantes** pour définir d'autres variantes d'impression pour les utilisateurs et les rapports. Le tableau suivant décrit les combinaisons de valeurs nécessaires pour spécifier une autre configuration d'impression pour un rapport.

|Pour                                                 |Définir les valeurs suivantes                                             |
|---------------------------------------------------|---------------------------------------------------------------------|
|Imprimer un rapport sur une imprimante spécifique pour tous les utilisateurs |Spécifiez une valeur dans les champs **Code rapport** et **Nom de l'imprimante** et ne renseignez pas le champ **Code utilisateur**.|
|Imprimer tous les rapports sur une imprimante spécifique pour un utilisateur spécifique|Spécifiez une valeur dans les champs **Code utilisateur** et **Nom de l'imprimante** et ne renseignez pas le champ **Code rapport**.|
|Définir l'imprimante par défaut pour tous les rapports|Spécifiez une valeur dans le champ **Nom de l'imprimante** et ne renseignez pas les champs **Code utilisateur** et **Code rapport**.|
|Imprimer un rapport spécifique sur l'imprimante par défaut de l'utilisateur|Spécifiez une valeur dans le champ **Code rapport** et ne renseignez pas les champs **Nom de l'imprimante** et **Code utilisateur**.|
|Imprimer un rapport spécifique sur une imprimante spécifique pour un utilisateur spécifique|Spécifiez une valeur dans les trois champs.|

> [!NOTE]
> Des sélections d'imprimantes plus spécifiques prévalent sur des sélections d'imprimantes plus générales. Par exemple, une sélection d'imprimante ayant des valeurs dans les champs **Code utilisateur**, **Code rapport** et **Nom de l'imprimante** prévaut sur une sélection d’imprimante ayant des entrées vides dans le champ **Code utilisateur** ou **Code rapport**.

## <a name="see-also"></a>Voir aussi
[Impression d'un rapport](ui-work-report.md#PrintReport)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
[Exécuter des traitements en lot](ui-how-run-batch-jobs.md)  
[Envoyer des documents par courriel](ui-how-send-documents-email.md)  
