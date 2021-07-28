---
title: Comment configurer des employés d'entrepôt | Microsoft Docs
description: Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu'employé d'entrepôt affecté à un emplacement par défaut, et éventuellement à d'autres emplacements.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: ''
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 1c7b37e11cab073fa6fda5492bec679363703e51
ms.sourcegitcommit: a7cb0be8eae6ece95f5259d7de7a48b385c9cfeb
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 07/08/2021
ms.locfileid: "6439270"
---
# <a name="set-up-warehouse-employees"></a>Configurer des employés d'entrepôt
Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu'employé d'entrepôt affecté à un emplacement par défaut, et éventuellement à d'autres emplacements. Cette configuration d'utilisateur filtre toutes les utilisations entrepôt dans la base de donnée pour l'emplacement de l'employé, de sorte que l'employé peut uniquement effectuer les activités entrepôt à l'emplacement par défaut. Un utilisateur peut être affecté à d'autres emplacements que ceux par défaut pour lesquels il peut consulter les lignes activité sans pour autant exécuter les activités.

## <a name="to-set-up-warehouse-employees"></a>Pour configurer des employés d'entrepôt  
1.  Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Sélectionnez le champ **Code utilisateur**, puis sélectionnez l'utilisateur à ajouter comme magasinier. Cliquez sur le bouton **OK**.  
6.  Dans le champ **Code magasin**, entrez le code du magasin dans lequel va travailler l'utilisateur.  
7.  Activez la case à cocher **Par défaut** pour définir le magasin comme seul emplacement pour les activités entrepôt de l'employé.  
8.  Répétez ces étapes pour affecter d'autres employés à des emplacements ou affecter d'autres emplacements à des employés d'entrepôt existants.  

## <a name="see-also"></a>Voir aussi  
[Gestion d'entrepôt](warehouse-manage-warehouse.md)  
[Stock](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)     
[Gestion d'assemblage](assembly-assemble-items.md)    
[Détails de conception : gestion d'entrepôt](design-details-warehouse-management.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]