---
title: Configurer des employés d'entrepôt
description: 'Chaque utilisateur exerçant des activités entrepôt doit être configuré en tant qu''employé d''entrepôt affecté à un emplacement par défaut, et éventuellement à d''autres emplacements.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.date: 03/09/2023
ms.custom: bap-template
ms.search.form: '7328, 7348'
---
# <a name="set-up-warehouse-employees" />Configurer des employés d'entrepôt

Chaque utilisateur qui exécute des activités entrepôt doit être configuré en tant qu’employé d’entrepôt et attribué à un emplacement par défaut. [!INCLUDE [prod_short](includes/prod_short.md)] filtre les activités de l’entrepôt à l’emplacement par défaut de l’employé. Ils ne peuvent effectuer les activités d’entrepôt qu’à l’emplacement. Vous pouvez aussi affecter un utilisateur à d’autres emplacements. Ils peuvent accéder, mais pas effectuer des activités à ces emplacements.

## <a name="to-set-up-warehouse-employees" />Pour configurer des employés d'entrepôt

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Employés entrepôt**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Sélectionnez le champ **Code utilisateur**, puis sélectionnez l'utilisateur à ajouter comme magasinier. Cliquez sur le bouton **OK**.  
4. Dans le champ **Code magasin**, entrez le code du magasin dans lequel va travailler l'utilisateur.  
5. Activez le bouton à bascule **Par défaut** pour définir l’emplacement comme seul emplacement pour les activités entrepôt de l’employé.  
6. Répétez ces étapes pour affecter d’autres employés à des emplacements ou affecter d’autres emplacements à des employés d’entrepôt existants.  

## <a name="see-related-microsoft-trainingtrainingmodulesget-started-warehouse-management" />Voir la [formation Microsoft](/training/modules/get-started-warehouse-management/) associée

## <a name="see-also" />Voir aussi

[Vue d’ensemble de Warehouse Management](design-details-warehouse-management.md)
[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Définir une stratégie de report des factures pour les utilisateurs](admin-setup-invoice-posting-policy.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
