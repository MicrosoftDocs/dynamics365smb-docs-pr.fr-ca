---
title: Créer des nouvelles écritures valeur pour des articles de l'inventaire Microsoft Docs
description: Décrit comment réévaluer ou amortir les entrées valeur d'un ou de plusieurs articles dans l'inventaire en reportant leur valeur actuelle calculée.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: costing, inventory cost, value entries
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 01710b23c56634b91b86f3f1c6e6c87415a787c6
ms.sourcegitcommit: a7cb0be8eae6ece95f5259d7de7a48b385c9cfeb
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/08/2021
ms.locfileid: "6435607"
---
# <a name="revalue-inventory"></a>Réévaluer l'inventaire
Pour réévaluer ou amortir un article ou une écriture article spécifique, vous devez utiliser le journal réévaluation.

## <a name="to-revalue-inventory"></a>Pour réévaluer l'inventaire
1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal réévaluation**, puis choisissez le lien associé.
2. Choisissez l'action **Calculer valeur stock**.
3. Sur la page **Calculer valeur inventaire**, renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Cliquez sur le bouton **OK**.
5. Sur chaque ligne de la page **Journal réévaluation**, indiquez le nouveau coût unitaire dans le champ **Coût unitaire (réévalué)**. Vous pouvez aussi indiquer le nouveau montant total dans le champ **Valeur stock (réévaluée)**.

    Les champs appropriés sont automatiquement mis à jour. Remarque : le champ **Montant** affiche la modification réelle de la valeur du stock pour l'écriture comptable article sélectionnée. Il calcule la différence entre les champs **Valeur stock (calculée)** et **Valeur stock (réévaluée)**.
6. Lorsque vous avez renseigné toutes les lignes de la feuille réévaluation, choisissez l'action **Valider**.

Les nouvelles écritures valeur sont alors créées pour refléter les appréciations que vous avez reportées. Vous pouvez visualiser les nouvelles valeurs dans les fiches article concernées.

## <a name="see-also"></a>Voir aussi
[Détails de conception : réévaluation](design-details-revaluation.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vente](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]