---
title: Fermer des écritures article provenant de l’utilisation d’une affectation fixe
description: Découvrez comment vous pouvez créer une affectation fixe entre une transaction entrante et la transaction sortante initiale dans le journal article.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 01/14/2020
ms.author: edupont
ms.openlocfilehash: 9aa24653d4ae957ff741e85a99c13e0c9a8f7173
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5381966"
---
# <a name="close-open-item-ledger-entries-resulting-from-fixed-application-in-the-item-journal"></a>Fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal article

Vous pouvez utiliser le champ **Écriture affectée de** dans la fenêtre **Journal article** pour créer une affectation fixe entre une transaction entrante et la transaction sortante initiale. Par exemple, pour corriger la transaction sortante ou pour traiter un retour.  

> [!IMPORTANT]  
> Les affectations fixes exécutées de cette manière s'appliquent uniquement au coût et non à la quantité. Par conséquent, l'écriture du grand livre d'articles positive reportée ne ferme pas l'écriture sortante affectée et demeure ouverte elle-même. Cela s'applique également lorsque vous reportez une affectation fixe pour une écriture positive vers une écriture négative qui n'a pas été fermée par une écriture positive ordinaire ; les écritures négatives et positives restent ouvertes.  
>
> Cela signifie également que vous ne pouvez pas fermer une période d'inventaire si une telle écriture existe.  

Vous pouvez modifier et affecter à nouveau des écritures d'affectation dans certaines conditions à l’aide de la page **Feuille affectation**.  

La procédure suivante explique comment fermer des écritures de ce genre au cours de deux reports de correction dans le journal article.  

## <a name="to-close-open-item-ledger-entries-that-result-from-a-fixed-application-in-the-item-journal"></a>Pour fermer les écritures article ouvertes qui résultent d'une affectation fixe dans le journal d'articles  

1. Utilisez le champ **Écriture affectée de** pour reporter un ajustement positif avec la quantité correspondante. Cela permet de fermer l'écriture négative initiale par une affectation fixe.  

    Le champ **Écriture référence** spécifie le numéro de l’écriture article sortant dont le coût est transmis à l’écriture article entrant lorsque vous reportez une transaction entrante de type **Ajustement positif** ou **Achat** avec le journal article.  
2. Utilisez le champ **Écriture affectée à** pour reporter un ajustement négatif. Cela permet de fermer l'écriture positive de correction initiale par une affectation fixe.  

    Le champ **Écriture référence** spécifie si la quantité dans la ligne journal article doit être affectée à un document déjà reporté. Si c’est le cas, entrez le numéro de l’écriture article à laquelle la ligne journal article doit être affectée.

## <a name="see-also"></a>Voir aussi

[Supprimer et appliquer à nouveau des écritures article](finance-how-to-remove-and-reapply-item-entries.md)  
[Traiter les retours et annulations de ventes](sales-how-process-sales-returns-cancellations.md)  
[Configuration de l'évaluation de l'inventaire et des coûts](finance-set-up-inventory-valuation-and-costing.md)  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Détails de conception : modes évaluation stock](design-details-costing-methods.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]