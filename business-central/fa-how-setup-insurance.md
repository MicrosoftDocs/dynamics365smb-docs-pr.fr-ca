---
title: Paramétrer l'assurance immo.| Microsoft Docs
description: Configurez certaines informations générales d'assurance ainsi qu'une fiche assurance par police pour gérer la couverture d'assurance des immobilisations.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: policy, coverage
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 1acb95e72ded81520272b250138005d36759d634
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813343"
---
# <a name="set-up-fixed-asset-insurance"></a>Configurer une assurance immobilisation
Pour gérer la couverture d'assurance des immobilisations, vous devez tout d'abord configurer certaines informations générales d'assurance ainsi qu'une fiche assurance par police.

## <a name="to-set-up-general-insurance-information"></a>Pour définir des informations générales relatives aux assurances
Pour utiliser les fonctions d'assurance dans [!INCLUDE[d365fin](includes/d365fin_md.md)], vous devez définir certaines informations générales relatives aux assurances.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Paramètres immobilisations**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]  

## <a name="to-set-up-insurance-types"></a>Pour définir des types d'assurance
Vous pouvez regrouper vos polices d'assurance en catégories (assurances contre le vol, assurances incendie, etc.). Les types d'assurance sont utilisés sur la fiche assurance.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Types assurance**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-cards"></a>Pour définir des fiches assurance
Vous pouvez rassembler des informations sur chaque police d'assurance dans la fiche assurance.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Assurance**, puis sélectionnez le lien associé.  
2. Sur la page **Assurance**, sélectionnez l'action **Nouveau** pour créer une fiche assurance.  
3. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-journal-templates"></a>Pour configurer des modèles journal assurance
[!INCLUDE[d365fin](includes/d365fin_md.md)] crée automatiquement un modèle journal assurance la première fois que vous ouvrez la page **Journal assurance**. Vous pouvez cependant configurer d'autres modèles journal. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles de journaux d'assurance**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins.

## <a name="to-set-up-insurance-journal-batches"></a>Pour définir des lots journal assurance
Vous pouvez configurer des lots dans un modèle journal assurance. Les valeurs du lot journal servent de valeurs par défaut si les champs ne sont pas renseignés sur les lignes journal. Pour en savoir plus, voir [Utiliser des feuilles comptabilité](ui-work-general-journals.md)  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Modèles de journaux d'assurance**, puis sélectionnez le lien associé.  
2. Sélectionnez un modèle feuille assurance, puis l'action **Lots**.
3. Sur la page **Lots journal assurance**, renseignez les champs selon vos besoins.

> [!NOTE]  
>   Les numéros remplissent une fonction spéciale dans les noms de journal. Si un nom de journal ou de modèle journal indique un numéro, ce numéro est incrémenté automatiquement de 1 chaque fois que le journal est reporté. Par exemple, si vous saisissez HH1 dans le champ **Nom**, la feuille prend le nom HH2 après validation de la feuille HH1.

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Immobilisations](fa-manage.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
