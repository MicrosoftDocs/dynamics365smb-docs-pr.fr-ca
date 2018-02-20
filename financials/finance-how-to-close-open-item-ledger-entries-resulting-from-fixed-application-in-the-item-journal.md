---
title: "Procédure : fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article | Microsoft Docs"
description: "Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale. Par exemple, pour corriger la transaction sortante ou pour traiter un retour."
services: project-madeira
documentationcenter: 
author: SorenGP
ms.service: dynamics365-financials
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 
ms.date: 08/09/2017
ms.author: sgroespe
ms.translationtype: HT
ms.sourcegitcommit: bec0619be0a65e3625759e13d2866ac615d7513c
ms.openlocfilehash: 1553b5f85cd9f00f9de15b59bcf258fba412967b
ms.contentlocale: fr-ca
ms.lasthandoff: 01/30/2018

---
# <a name="close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal"></a>Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article
Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale. Par exemple, pour corriger la transaction sortante ou pour traiter un retour. Pour plus d'informations, voir Lettrage à partir écriture.  

> [!IMPORTANT]  
>  Les affectations fixes exécutées de cette manière s'appliquent uniquement au coût et non à la quantité. Par conséquent, l'écriture du grand livre d'articles positive reportée ne ferme pas l'écriture sortante affectée et demeure ouverte elle-même. Cela s'applique également lorsque vous reportez une affectation fixe pour une écriture positive vers une écriture négative qui n'a pas été fermée par une écriture positive ordinaire ; les écritures négatives et positives restent ouvertes.  
>   
>  Cela signifie également que vous ne pouvez pas fermer une période d'inventaire si une telle écriture existe.  

La procédure suivante explique comment fermer des écritures de ce genre au cours de deux reports de correction dans le journal article.  

## <a name="to-close-open-item-ledger-entries-that-result-from-a-fixed-application-in-the-item-journal"></a>Pour fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal d'articles  

1.  Utilisez le champ **Écriture affectée de** pour reporter un ajustement positif avec la quantité correspondante. Cela permet de fermer l'écriture négative initiale par une affectation fixe.  
2.  Utilisez le champ **Écriture affectée à** pour reporter un ajustement négatif. Cela permet de fermer l'écriture positive de correction initiale par une affectation fixe.  

## <a name="see-also"></a>Voir aussi  
[ Supprimer et appliquer à nouveau des écritures article](finance-how-to-remove-and-reapply-item-entries.md)  
 [Traiter les retours et annulations de ventes](sales-how-process-sales-returns-cancellations.md)   
 [Configuration de l'évaluation de l'inventaire et des coûts](finance-set-up-inventory-valuation-and-costing.md)   
 [Gestion des coûts ajustés](finance-manage-inventory-costs.md)   
 [Détails de conception : modes évaluation stock](design-details-costing-methods.md)

