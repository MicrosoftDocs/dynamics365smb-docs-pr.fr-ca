---
title: Utiliser les clés d'affectation dans les journaux généraux | Microsoft Docs
description: En savoir plus sur l'utilisation des clés de ventilation dans les feuilles.
services: project-madeira
documentationcenter: ''
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: cost accounting
ms.date: 04/01/2019
ms.author: edupont
ms.openlocfilehash: aa2e553b28825338dadd758f48c5ff43a0494cf4
ms.sourcegitcommit: bd78a5d990c9e83174da1409076c22df8b35eafd
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/31/2019
ms.locfileid: "913835"
---
# <a name="use-allocation-keys-in-general-journals"></a>Utiliser les clés d'affectation dans les journaux généraux
Vous pouvez ventiler une écriture dans un journal général dans différents comptes lorsque vous reportez le journal. L'affectation peut être effectuée par quantité, pourcentage ou montant.

## <a name="to-set-up-allocation-keys"></a>Pour définir des clés de ventilation
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal général récurrent**, puis sélectionnez le lien associé.
2. Sélectionnez le champ **Nom du lot** pour ouvrir la page **Lots journal général**.
3. Vous pouvez soit modifier les ventilations sur un lot existant dans la liste ou créer un lot avec des ventilations.
   * Pour créer un lot, sélectionnez l'action **Nouveau**, et passez à l'étape suivante.
   * Pour modifier les affectations à partir d'un journal existant, sélectionnez le journal et passez à l'étape 7.    
4. Dans le champ **Nom**, saisissez le nom du lot, par exemple NETTOYAGE. Dans le champ **Description**, saisissez une description, par exemple Feuille frais de nettoyage.
5. Fermez la page lorsque vous avez terminé. Un nouveau journal récurrent vide s'ouvre.
6. Renseignez les champs de la ligne.
7. Sélectionnez l'action **Ventilations**.
8. Ajoutez une ligne pour chaque affectation. Vous devez renseigner le champ **% ventilation**, **Quantité imputée** ou **Montant**. Vous devez également renseigner le champ **N° compte** et, si vous affectez la transaction à des dimensions principales, les champs de ces dimensions principales.
9. Si vous saisissez un pourcentage dans une ligne, le montant du champ **Montant** est calculé automatiquement. Ces montants sont dotés du signe opposé à celui du montant total figurant dans le champ **Montant** de la feuille récurrente.
10. Après avoir saisi les lignes d'affectations, cliquez sur **OK** pour revenir à la page **Journal général récurrent**. Le champ **Montant imputé DS** est renseigné et correspond au champ **Montant**.
11. Reportez le journal.

## <a name="to-change-an-allocation-key-that-has-already-been-set-up"></a>Pour modifier une clé d'affectation déjà configurée
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Journal général récurrent**, puis sélectionnez le lien associé.
2. Sur la page **Journal général récurrent**, sélectionnez le journal contenant l'affectation.
3. Sélectionnez la ligne de la ventilation, puis sélectionnez l'action **Ventilations**.
4. Modifiez les champs appropriés, puis cliquez sur le bouton **OK**.

## <a name="see-also"></a>Voir aussi
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)  
[Validation des documents et des feuilles](ui-post-documents-journals.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
