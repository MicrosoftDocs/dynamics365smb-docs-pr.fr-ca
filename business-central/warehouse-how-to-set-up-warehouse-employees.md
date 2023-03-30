---
title: Configurer des employés d'entrepôt
description: 'Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu''employé d''entrepôt affecté à un emplacement par défaut, et éventuellement à d''autres emplacements.'
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.form: '7328, 7348'
ms.date: 04/01/2021
ms.author: edupont
---
# Configurer des employés d'entrepôt

Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu'employé d'entrepôt affecté à un emplacement par défaut, et éventuellement à d'autres emplacements. Cette configuration d'utilisateur filtre toutes les utilisations entrepôt dans la base de donnée pour l'emplacement de l'employé, de sorte que l'employé peut uniquement effectuer les activités entrepôt à l'emplacement par défaut. Un utilisateur peut être affecté à d'autres emplacements que ceux par défaut pour lesquels il peut consulter les lignes activité sans pour autant exécuter les activités.

## Pour configurer des employés d'entrepôt  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Sélectionnez le champ **Code utilisateur**, puis sélectionnez l'utilisateur à ajouter comme magasinier. Cliquez sur le bouton **OK**.  
4. Dans le champ **Code magasin**, entrez le code du magasin dans lequel va travailler l'utilisateur.  
5. Activez la case à cocher **Par défaut** pour définir le magasin comme seul emplacement pour les activités entrepôt de l'employé.  
6. Répétez ces étapes pour affecter d'autres employés à des emplacements ou affecter d'autres emplacements à des employés d'entrepôt existants.  

## Voir la [formation Microsoft](/training/modules/get-started-warehouse-management/) associée

## Voir aussi

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
