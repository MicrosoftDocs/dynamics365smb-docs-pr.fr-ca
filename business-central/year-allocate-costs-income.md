---
title: Aperçu des tâches de ventilation des coûts et des revenus | Microsoft Docs
description: Décrit les tâches pour affecter une écriture dans un journal général dans différents comptes lorsque vous reportez le journal.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 10/01/2018
ms.author: sgroespe
ms.openlocfilehash: 0c761db3f76d1fff05dd75a08a586f52386b5b88
ms.sourcegitcommit: 1bcfaa99ea302e6b84b8361ca02730b135557fc1
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 03/08/2019
ms.locfileid: "813333"
---
# <a name="allocate-costs-and-income"></a>Répartition des coûts et du revenu
Vous pouvez ventiler une écriture dans un journal général dans différents comptes lorsque vous reportez le journal. L'affectation peut être effectuée de trois manières différentes :

* Quantité
* Pourcentage (%)
* Montant

Les fonctions d'affectation peuvent être utilisées avec les journaux généraux récurrents et dans les journaux immobilisations.
<!--You can also distribute the cost or revenue of a line to an intercompany partner when you post a sales or purchase document. When you post the document, a line will be posted in your general journal, and a corresponding line will be created in the intercompany outbox.-->

Les procédures suivantes décrivent comment se préparer à affecter des coûts dans un journal général récurrent en définissant des clés d'affectation. Lorsque des clés d'affectation sont définies, vous renseignez et reportez le journal comme tout autre journal général récurrent. Pour plus d'informations, voir [Utilisation des feuilles comptabilité](ui-work-general-journals.md).

## <a name="to-set-up-allocation-keys"></a>Pour définir des clés de ventilation
Vous pouvez affecter une écriture dans un journal général récurrent dans différents comptes lorsque vous reportez le journal. L'affectation peut être effectuée par quantité, pourcentage ou montant.
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
[Clôture des exercices et des périodes](year-close-years-periods.md)  
[Utilisation de feuilles comptabilité](ui-work-general-journals.md)    
[Validation des documents et des feuilles](ui-post-documents-journals.md)    
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)
