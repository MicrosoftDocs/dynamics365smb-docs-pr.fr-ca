---
title: Configurer les processus de dépannage | Microsoft Docs
description: Découvrez comment configurer des processus qui aident les conseillers du service clientèle à identifier et à résoudre les problèmes liés aux articles de service.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: service, service item, troubleshoot, repairs, maintenance
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 2dfa02f0054cab20605281bb1cc580b522b893fd
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1251272"
---
# <a name="setting-up-troubleshooting-for-service-items"></a>Configuration du dépannage pour les articles de service
Vous pouvez configurer des instructions de dépannage qui aident les techniciens à résoudre les problèmes pendant la maintenance. Par exemple, les instructions peuvent être une liste d'étapes pour effectuer une réparation, ou une série de questions à poser sur les articles. Une fois que vous avez configuré les instructions de dépannage, vous pouvez les affecter à des groupes articles de service, des articles de service et des articles. Il existe une hiérarchie d'héritage pour les instructions. Si vous les affectez à un groupe articles de service, les articles inclus dans le groupe héritent des instructions sauf si vous les spécifiez pour les articles. De même, les articles de service héritent des instructions des articles.  

## <a name="to-set-up-troubleshooting-guidelines"></a>Pour configurer des instructions dépannage
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Dépannage**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-assign-troubleshooting-guidelines-to-items-service-items-or-service-item-groups"></a>Pour affecter des instructions de dépannage à des articles, des articles de service ou des groupes articles de service
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Articles**, **Articles de service** ou **Groupes articles de service**, puis sélectionnez le lien associé.  
2. Sélectionnez l'entité appropriée, puis l'action **Dépannage**.  

## <a name="see-also"></a>Voir aussi
[Gestion des services](service-service.md)