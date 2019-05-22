---
title: Configurer les documents entrants| Microsoft Docs
description: Utilisez la fonctionnalité Documents entrants pour créer des documents électroniques, gérer des tâches OCR, importer des factures, et convertir des fichiers images.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: electronic document, e-invoice, incoming document, OCR, ecommerce, document exchange, import invoice
ms.date: 04/01/2019
ms.author: sgroespe
ms.openlocfilehash: 7e99f4b33767a1bdea7b942d1b183edbacc829ac
ms.sourcegitcommit: 60b87e5eb32bb408dd65b9855c29159b1dfbfca8
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 04/29/2019
ms.locfileid: "1241518"
---
# <a name="set-up-incoming-documents"></a>Configurer des documents entrants
Si vous créez des lignes journal général à partir des enregistrements de documents entrants, vous devez spécifier sur la page **Configuration des documents entrants** quels modèle et lot de journal utiliser.

Si vous ne souhaitez pas que les utilisateurs créent des factures ou des lignes journal général à partir d'enregistrements de documents entrants, sauf si les documents ont été préalablement approuvés, vous devez configurer des approbateurs sur la page **Approbateurs de document entrant**.

Pour convertir les fichiers PDF et image en documents électroniques que vous pouvez convertir, par exemple, en factures achat dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez d'abord configurer la fonctionnalité OCR et activer le service.

Une fois que la fonctionnalité Documents entrants est configurée, vous pouvez utiliser différentes fonctions pour examiner les reçus de dépenses, gérer les tâches OCR et convertir les fichiers document entrant, manuellement ou automatiquement, en documents ou lignes journal appropriés. Les fichiers externes peuvent être joints à n'importe quelle étape du processus, notamment en ce qui concerne les documents reportés et les écritures fournisseur, client et grand livre résultantes. Pour plus d'informations, voir la section [Traitement des documents entrants](across-process-income-documents.md).

## <a name="to-set-up-the-incoming-documents-feature"></a>Configurer la fonctionnalité Documents entrants
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration document entrant**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-approvers-of-incoming-document-records"></a>Configurer des approbateurs d'enregistrements document entrant
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration document entrant**, puis sélectionnez le lien associé.  
2. Sur la page **Configuration des documents entrants**, sélectionnez l'action **Approbateurs**.

    La page **Approbateurs de document entrant** affiche tous les utilisateurs configurés dans [!INCLUDE[d365fin](includes/d365fin_md.md)].  
3. Sélectionnez un ou plusieurs utilisateurs pouvant approuver un document entrant avant de pouvoir créer un document ou une ligne journal correspondante.

Lorsque des approbateurs ont été configurés sur la page **Approbateurs de document entrant**, seuls ces utilisateurs peuvent approuver un document entrant si la case **Exiger une approbation pour créer** est cochée sur la page **Configuration des documents entrants**.

> [!NOTE]  
>   Cette configuration d'approbation n'est pas liée aux flux d'approbation. Pour plus d'informations, reportez-vous à [Utilisation des flux d'approbation](across-how-use-approval-workflows.md).

## <a name="to-set-up-an-ocr-service"></a>Configurer un service ROC
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration du service OCR**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]  
> Vos données d'ouverture de session sont automatiquement chiffrées.

## <a name="see-also"></a>Voir aussi
[Traiter les documents entrants](across-process-income-documents.md)  
[Documents entrants](across-income-documents.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
