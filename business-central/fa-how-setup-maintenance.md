---
title: Configurer l'entretien des immobilisations| Microsoft Docs
description: Pour gérer les réparations et l'entretien des immobilisations, spécifiez les informations générales d'entretien, les codes du type de travail, ainsi qu'un compte de report pour les coûts.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: repair, service
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 60080b0a8982420ff2f3a6654d496395733bc425
ms.sourcegitcommit: 2e7307fbe1eb3b34d0ad9356226a19409054a402
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 12/17/2020
ms.locfileid: "4749228"
---
# <a name="set-up-fixed-asset-maintenance"></a>Configurer l'entretien d'une immobilisation
Pour gérer l'entretien des immobilisations, vous devez configurer tout d'abord certaines informations générales d'entretien, un compte de report pour les coûts d'entretien et les codes d'entretien pour les types de travaux, tels que le service de routine ou la réparation.

## <a name="to-set-up-general-maintenance-information"></a>Pour configurer les informations générales d'entretien
Si vous configurez les champs pour l'entretien, vous pouvez reporter des dépenses d'entretien à partir du journal immobilisation.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Immobilisations**, puis sélectionnez le lien associé.
2. Sélectionnez l'immobilisation pour laquelle vous souhaitez définir la couverture d'assurance, puis sélectionnez l'action **Modifier**.
3. Sur le raccourci **Maintenance**, complétez les champs, comme nécessaire. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

## <a name="to-set-up-maintenance-codes"></a>Pour configurer des codes entretien
Lorsque vous validez des coûts de maintenance à partir d'une feuille comptabilité, vous renseignez le champ **Code maintenance** pour enregistrer le type de maintenance effectuée, telle qu'un service de routine ou une réparation.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Entretien**, puis sélectionnez le lien associé.
2. Sur la page **Entretien**, configurez les codes pour les différents types de travaux d'entretien.

## <a name="to-set-up-maintenance-expense-accounts"></a>Pour configurer des comptes frais d'entretien
Pour reporter les coûts d'entretien, vous devez tout d'abord saisir un numéro de compte sur la page **Groupes report immo.**.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report immo.**, puis sélectionnez le lien associé.
2. Renseignez le champ **Compte frais maintenance** pour chaque groupe comptabilisation.

> [!NOTE]  
>   Pour définir que les coûts d'entretien sont affectés aux départements ou projets, configurez une clé d'affectation. Pour en savoir plus, voir [Configurer des fonctionnalités d'immobilisations](fa-how-setup-general.md).

## <a name="see-also"></a>Voir aussi
[Paramétrage d'immobilisations](fa-setup.md)  
[Immobilisations](fa-manage.md)  
[Finance](finance.md)  
[Mise en route](product-get-started.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)
