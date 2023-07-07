---
title: 'Prélever ou déplacer des articles pour la fabrication, l’assemblage ou les tâches dans les configurations de stockage de base'
description: 'Lorsque l’entrepôt exige un traitement des prélèvements sans livraisons, utilisez la page Prélèvement inventaire pour enregistrer les composantes prélevées.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.date: 12/16/2022
ms.custom: bap-template
ms.search.forms: '9330, 931, 990008, 89, 900, 902'
---
# <a name="pick-for-production-assembly-or-jobs-in-basic-warehouse-configurations"></a>Prélever pour la fabrication, l’assemblage ou les tâches dans les configurations de stockage de base

Le mode de prélèvement de vos composantes pour les ordres de fabrication, d’assemblage ou les tâches dépend de la configuration de l’entrepôt en tant qu’emplacement. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).

Dans une configuration d’entrepôt de base pour le flux sortant (prélèvement), sur la page **Fiche emplacement** du site, activez le bouton à bascule **Prélèvement requis** mais désactivez le bouton à bascule **Livraison requise**.

Utilisez les documents suivants pour les opérations internes :

* Article en inventaire à prélever
* Mouvement d'inventaire

## <a name="inventory-picks"></a>Prélèvements inventaire

* Lorsque vous enregistrez un prélèvement inventaire pour une opération interne, telle que la production ou une tâche, la consommation des composantes sélectionnées est reportée en même temps.
* Le bouton à bascule **Zone obligatoire** sur la page **Fiche emplacement** est facultatif.
* Lorsque vous utilisez les prélèvements inventaire, le champ **Code de zone** sur une ligne de composante de bon de production ou les lignes planification d’une tâche définit la zone *prendre*. Les composantes sont diminuées dans le bac « prendre » lorsque vous reportez la consommation.

## <a name="inventory-movements"></a>Mouvements d’inventaire

* Les mouvements d’inventaire nécessitent que vous activiez le bouton à bascule **Zone obligatoire** sur la page **Fiche emplacement** pour l’emplacement.
* Les mouvements d’inventaire ne fonctionnent qu’avec les lignes de composantes de bon de production et les lignes d’ordre d’assemblage.
* Lorsque vous enregistrez un mouvement d’inventaire pour une opération interne, vous enregistrez seulement le mouvement physique des composantes dans une zone de la zone d’opération. Vous ne reportez pas la consommation.
* Lorsque vous utilisez les mouvements d’inventaire, le champ **Code de zone** sur une ligne de composante de bon de production définit la zone *placer* dans la zone d’opération. La zone « placer » est l’endroit où les employés d'entrepôt doivent placer les composantes.
* Enregistrez séparément la consommation des composantes prélevées en reportant un journal consommation ou un ordre d’assemblage.

>[!NOTE]
> Même si le bouton à bascule **Prélèvement requis** est désactivé, vous pouvez utiliser un document **Prélèvement entrepôt**. Les documents de prélèvement entrepôt sont similaires aux documents **Prélèvement inventaire**. Ceci est utile si vous souhaitez utiliser les prélèvements dans les opérations et livrer dans les flux sortants de l’entrepôt.

### <a name="production"></a>Fabrication

Utilisez les documents **Prélèvement inventaire** pour prélever des composantes de production dans le flux vers la production.

Pour un emplacement qui utilise des zones, vous pouvez étendre le flux jusqu’à la production en utilisant les documents **Mouvement d’inventaire**. Les mouvements d’inventaire sont particulièrement utiles pour la consommation des composantes. Pour en savoir plus sur la façon dont la consommation de composantes passe des zones avant production aux zones d'atelier ouvert, voir [Consommer les composantes pour la production dans une configuration d’entrepôt de base](#flushing-production-components-in-a-basic-warehouse-configuration).

### <a name="assembly"></a>Assemblage

Utilisez les documents **Mouvement d’inventaire** pour déplacer les composantes d’assemblage vers la zone d’assemblage.

> [!NOTE]
> Les documents **Mouvement d’inventaire** nécessitent des zones.

[!INCLUDE [prod_short](includes/prod_short.md)] prend en charge les types de flux d’assemblage Assembler pour stock et Assembler pour commande. Pour en savoir plus sur l’assemblage pour commande dans le flux d’entrepôt sortant, accédez à [Traitement des articles à assembler pour commande dans des prélèvements inventaire](warehouse-how-to-pick-items-with-inventory-picks.md#handling-assemble-to-order-items-with-inventory-picks).

### <a name="project-management"></a>Gestion de projets

Utilisez les documents **Prélèvement inventaire** pour sélectionner les composantes de la tâche dans le flux vers la gestion de projet.

Pour les emplacements qui utilisent des zones, vous pouvez étendre le flux jusqu’aux projets en utilisant les documents **Mouvement d’inventaire**.

> [!NOTE]
> La possibilité de prélever des composantes pour les lignes planification projet a été ajoutée à [!INCLUDE[d365fin](includes/d365fin_md.md)] dans la 2e vague de lancement 2022. Pour commencer à utiliser la fonctionnalité, un administrateur doit activer **Mise à jour des fonctionnalités : activer prélèvement inventaire et entrepôt à partir des projets** sur la page **Gestion des fonctionnalités**.
>
> [!INCLUDE[prod_short](includes/prod_short.md)] utilise la valeur dans le champ **Quantité restante** sur la ligne planification projet lorsqu’il crée des prélèvements inventaire. Pour utiliser les prélèvements d’inventaire pour les projets, vous devez activer le bouton à bascule **Appliquer le lien d’utilisation** sur la page **Fiche projet** pour le projet. Cela vous permet de suivre l’utilisation par rapport à votre forfait. Si vous n’activez pas le bouton à bascule, la quantité restante restera à **0** et le prélèvement de l'inventaire ne sera pas créé. Learn more at [Pour configurer un suivi d’utilisation de projet](projects-how-setup-jobs.md?tabs=current-experience#to-set-up-job-usage-tracking).

## <a name="pick-or-move-for-production-assembly-and-jobs-in-a-basic-warehouse-configuration"></a>Prélever ou déplacer pour la production, l’assemblage ou les projets dans les configurations de stockage de base

Vous pouvez créer un prélèvement inventaire ou un mouvement d’inventaire de trois manières :  

* À partir du document origine lui-même.  
* Pour plusieurs documents source en même temps en utilisant un traitement en lot.  
* En deux étapes. Libérez le document source pour qu’il soit prêt pour le prélèvement. Créez le prélèvement ou le mouvement d’inventaire à partir des documents **Prélèvement inventaire** ou **Mouvement d’inventaire**. Le prélèvement ou le mouvement d’inventaire est basé sur le document source.  

### <a name="to-create-an-inventory-pick-from-the-source-document"></a>Pour créer un prélèvement inventaire à partir du document source

1. Sur le document source, qui peut être un bon de production ou un projet, choisissez l’action **Créer prélèv./rangement inventaire**.  
2. Activez la case à cocher **Créer prélèvement inventaire**.
3. Choisissez le bouton **OK**.

### <a name="to-create-an-inventory-movement-from-the-source-document"></a>Pour créer un mouvement d’inventaire à partir du document source

1. Sur le document source, qui peut être un bon de production, un ordre d’assemblage ou un projet, choisissez l’action **Créer prélèv./rangement inventaire**.  
2. Activez la case à cocher **Créer mouvement d’inventaire**.
3. Choisissez le bouton **OK**.

### <a name="to-create-multiple-inventory-picks-or-movements-with-a-batch-job"></a>Pour créer plusieurs prélèvements ou mouvements d’inventaire avec un traitement en lot

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Créer rangement/prélèvement/mouvement d’inventaire**, puis choisissez le lien associé.  
2. Sur le raccourci **Demande entrepôt**, utilisez les champs **Document origine** et **N° origine** pour opérer un filtrage sur les types de documents ou des plages de numéros de document. Par exemple, vous pouvez créer des prélèvements uniquement pour des ordres de fabrication.
3. Dans le raccourci **Options**, activez les boutons à bascule **Créer prélèvement inventaire** ou **Créer mouvement d’inventaire**.
4. Choisissez le bouton **OK**.

### <a name="to-create-inventory-picks-or-movements-in-two-steps"></a>Pour créer des prélèvements ou des mouvements d’inventaire en deux étapes

Pour prélever ou déplacer des composantes pour des documents source en deux étapes, vous devez libérer le document source pour qu’il soit prêt pour le prélèvement. Libérez les documents origine des opérations internes en procédant comme suit.  

|Document origine|Méthode de libération|  
|---------------------|--------------------|  
|Bon de production|Sur la page **Bon de production planifié**, changez l’état d’une commande en **Libéré** ou utilisez la page **Bon de production libéré**pour créer un bon de production libéré.|  
|Ordre d’assemblage|Modifiez l’état d’un ordre d’assemblage en **Libéré**.|
|Projets | Changez l’état d’un projet en **Ouvert** ou créez un projet avec l’état Ouvert immédiatement.|  

Un employé d'entrepôt affecté au prélèvement d’articles peut créer un document de rangement d’inventaire pour le document source.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Prélèvements inventaire** ou **Mouvement d’inventaire**, puis choisissez le lien associé.  
2. Sélectionnez l'action **Nouveau**.  
3. Dans le champ **Document origine**, sélectionnez le type de document origine que concerne le rangement.

    > [!NOTE]
    > Vous ne pouvez pas utiliser les documents **Prélèvement inventaire** pour prélever des composantes d’assemblage.
4. Dans le champ **N° origine**, sélectionnez le document origine.  
5. Sinon, choisissez l’action **Extraire document source** pour sélectionner le document à partir de la liste des documents source entrants prêts pour le prélèvement dans l’emplacement.  
6. Cliquez sur le bouton **OK** pour renseigner les lignes prélèvement ou mouvement en fonction du document origine sélectionné.  

## <a name="to-record-the-inventory-pick"></a>Pour enregistrer le prélèvement inventaire

1. Sur la page **Prélèvement inventaire**, ouvrez le document pour lequel enregistrer un prélèvement.  
2. Dans le champ **Code de zone** sur les lignes prélèvement, la zone à partir de laquelle les articles doivent être prélevés à partir de la zone où l’article est disponible. Si nécessaire, vous pouvez modifier la zone.
3. Exécutez le prélèvement, puis saisissez la quantité prélevée dans le champ **Quantité à traiter**.

    Si vous devez prélever les articles d’une ligne à partir de plusieurs zones, par exemple parce qu’une zone ne contient pas la quantité totale, utilisez l’action**Fractionner la ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.  
4. Sélectionnez l'action **Reporter**.  

Voici ce qui se passe pendant le processus de report :

* Report de la consommation des lignes du document source qui ont été prélevées.
* Si l’emplacement utilise des zones, le report crée également des écritures entrepôt pour reporter les modifications de la quantité zone.

[!INCLUDE [preview-posting-warehouse](includes/preview-posting-warehouse.md)]

## <a name="to-record-the-inventory-movement"></a>Pour enregistrer le mouvement d’inventaire

1. Sur la page **Mouvement d’inventaire**, ouvrez le document pour lequel enregistrer le mouvement.  
2. Dans le champ **Code de zone** sur les lignes de mouvement, la zone à prélever est suggérée en fonction de la zone par défaut et de la disponibilité de l’article. Si nécessaire, vous pouvez modifier la zone.  
3. Exécutez le mouvement, puis saisissez la quantité déplacée dans le champ **Quantité à traiter**. La valeur sur les lignes prélèvement et emplacement doit être la même. Sinon, vous ne pouvez pas enregistrer le mouvement.

    Si vous devez prendre les articles d’une ligne dans plusieurs zones, par exemple parce qu’une zone ne contient pas la quantité totale, utilisez l’action **Fractionner la ligne** sur le raccourci **Lignes**. L’action crée une ligne pour la quantité restante à gérer.  
4. Sélectionnez l’action **Enregistrer mouvement d’inventaire**.  

Voici ce qui se passe pendant le processus de report :

* Les écritures entrepôt indiquent maintenant que les composantes se trouvent dans les zones spécifiées sur les lignes d’ordre d’assemblage du document source. Par exemple, la ligne d’ordre d’assemblage, de composante de production ou de planification projet.

>[!NOTE]
> Contrairement au déplacement de composantes à l’aide de prélèvements inventaire, la consommation n’est pas reportée lorsque vous enregistrez un mouvement d’inventaire. Vous enregistrez la consommation dans une étape distincte en reportant le document source.

## <a name="flushing-production-components-in-a-basic-warehouse-configuration"></a>Consommer les composantes pour la production dans une configuration d’entrepôt de base

Les modes de consommation affectent le flux des composantes en production. Pour en savoir plus, voir [Consommer des composantes en fonction de la production réalisée](production-how-to-flush-components-according-to-operation-output.md). En fonction de la méthode de consommation sélectionnée, vous pouvez prélever des composantes pour la production des manières suivantes :

* Utilisez un document **Prélèvement inventaire** pour enregistrer le prélèvement des articles qui utilisent la méthode de consommation **manuelle**. Lorsque vous enregistrez un prélèvement inventaire, la consommation des composantes prélevées est reportée. 
* Utilisez un document **Mouvement d’inventaire** avec une référence à un document source pour enregistrer les prélèvements pour les composantes qui utilisent la méthode de consommation **Manuelle**. Vous devrez enregistrer la consommation séparément. Pour en savoir plus, voir [Reporter en lot la consommation de la production](production-how-to-post-consumption.md). 
* Utilisez un document **Mouvement d’inventaire** avec une référence à un document source pour enregistrer les prélèvements pour les composantes qui utilisent la méthode de consommation **Prélèvement + Aval**, **Prélèvement + Amont**. La consommation des composantes se produira automatiquement, soit lorsque vous modifiez l’état du bon de production, soit en démarrant ou en terminant une opération. Toutes les composantes requises doivent être disponibles. Autrement, le report de la consommation de la composante est arrêté.
* Utilisez un document **Mouvement d’inventaire** sans référence à un document source ou d’autres moyens d’enregistrer le mouvement des composantes qui utilisent la méthode de consommation **Aval** ou **Amont**. La consommation des composantes se produira automatiquement, soit lorsque vous modifiez l’état du bon de production, soit lorsque vous démarrez ou terminez une opération. Toutes les composantes requises doivent être disponibles. Autrement, le report de la consommation s’arrête pour cette composante. Learn more at [Déplacement des articles en interne dans les configurations entrepôt de base](warehouse-how-to-move-items-ad-hoc-in-basic-warehousing.md).

### <a name="example"></a>Exemple :

Vous avez un bon de production pour 15 pièces de l’article SP-SCM1004. Certains articles sur la liste des composantes doivent être consommés manuellement dans un journal consommation et d’autres articles peuvent être prélevés et consommés automatiquement à l’aide de la méthode de consommation **Prélèvement + Amont**.  

Les étapes suivantes illustrent les actions prises par divers utilisateurs et les réponses associées :  

1. Le chef atelier lance l'ordre de fabrication. Les articles utilisant la méthode de consommation **Aval** et aucun lien itinéraire n’est déduit de la zone d'atelier ouvert.  
2. Le chef d’atelier choisit l’action **Créer prélèv./rangement inventaire** sur le bon de production et active les boutons à bascule **Créer prélèvement inventaire** et **Créer mouvement d’inventaire**. Un document de prélèvement inventaire est créé pour les articles avec la méthode de consommation **manuelle**, et un mouvement d’inventaire est créé pour les articles avec les méthodes de consommation **Prélèvement + Amont** et **Prélèvement + Aval**.
3. Le gestionnaire d’entrepôt affecte les prélèvements et les mouvements à un employé d'entrepôt.
4. L'employé d'entrepôt prélève les articles dans les zones appropriées et les place dans la zone avant production ou dans la zone spécifiée sur le mouvement d’inventaire. La zone peut être une zone de poste de travail ou d’unité de production.  
5. L'employé d'entrepôt reporte le prélèvement. La quantité est déduite des zones.
6. L'employé d'entrepôt reporte le mouvement. La quantité est déduite des zones prélèvement et ajoutée à la zone de consommation. Le champ **Qté prélevée** sur la liste des composantes de tous les articles prélevés est mis à jour.  
7. L'opérateur indique au gestionnaire de production que les articles finis sont terminés.  
8. Le chef d’atelier utilise le journal production pour reporter la sortie. La quantité des composantes qui utilisent les méthodes de consommation **Prélèvement + Aval** ou **Prélèvement + Amont** avec des liens itinéraires est déduite de la zone avant production.
9. Le gestionnaire de production modifie l’état du bon de production en **Terminé**. La quantité de composantes qui utilisent la méthode de consommation **Amont** est déduite de la zone d'atelier ouvert, et la quantité de composantes qui utilisent la méthode de consommation **Prélèvement + Amont** et pas de lien itinéraire est déduite de la zone avant production.  

 La figure ci-après indique la date à laquelle le champ **Code de zone** de la liste des composantes est renseigné en fonction de la configuration de votre emplacement ou unité de production/atelier.  

:::image type="content" source="media/binflow.png" alt-text="Aperçu de quand et comment le champ Code de zone est renseigné.":::

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/paths/pick-ship-items-business-central/) associée

## <a name="see-also"></a>Voir aussi

[Inventaire](inventory-manage-inventory.md)  
[Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md)  
[Gestion d'assemblage](assembly-assemble-items.md)  
[Vue d’ensemble de la gestion des entrepôts](design-details-warehouse-management.md)
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
