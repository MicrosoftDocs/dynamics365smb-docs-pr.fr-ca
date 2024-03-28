---
title: Créer une Fiche projet pour un projet et spécifier des tâches
description: 'Pour un nouveau projet, vous créez une fiche projet qui contient les tâches projet et les lignes planification, pour vous aider à gérer la progression et les budgets.'
author: brentholtorf
ms.topic: conceptual
ms.search.keywords: 'project management, task'
ms.search.form: '88, 275, 276, 1001, 1002, 1003, 1004, 1005, 1006, 1007, 1020'
ms.date: 08/03/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# <a name="create-jobs"></a>Créer des projets

Lorsque vous démarrez un nouveau projet, vous devez créer une fiche projet avec des tâches intégrées et des lignes planification structurées en deux couches.  

La première couche inclut les tâches du projet. Vous devez créer au moins une tâche par projet car tous les reports font référence à une tâche de projet. Cela permet de configurer les lignes planification projet et de reporter la consommation dans le projet.

La seconde couche inclut les lignes planification projet, qui spécifient l'utilisation détaillée des ressources, articles et diverses dépenses du grand livre.

La structure de couche permet de séparer le projet en tâches plus petites et ainsi d'utiliser des détails plus spécifiques dans l'établissement du budget, les devis et l'enregistrement. En outre, elle vous donne un aperçu de la progression d'un projet. Par exemple, vous pouvez rechercher si vous respectez les étapes importantes fixées ou si vous êtes en passe de satisfaire les attentes budgétaires.

> [!TIP]
> Choisissez l'action **Nouveau projet** du tableau de bord **Chef de projet** pour lancer un guide de configuration assistée qui vous dirige à travers les étapes de création d'un projet avec des tâches intégrées et des lignes planification. La procédure suivante décrit comment exécuter les étapes manuellement. Pour obtenir un exemple de la procédure pour créer manuellement un projet, reportez-vous à la rubrique [Vidéo : Créer un projet dans Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw).

Parfois, la partie qui reçoit un service est différente de celle qui paie la facture. Sur la page **Projets**, vous pouvez spécifier le client qui bénéficiera du projet dans les champs **Débiteur** et la partie à facturer dans les champs **Facturation**. Vous pouvez également fournir les informations suivantes : 

* Où le travail aura lieu en sélectionnant parmi une liste d'adresses de livraison pour le client.
* Ajouter des informations sur les références externes pour simplifier la communication sur le projet.
* Remplacer les conditions financières standard du projet.

## <a name="to-create-a-job-card"></a>Pour créer une fiche projet

Vous devez créer une fiche projet, puis créez des Lignes tâche projet et des lignes planification projet pour ce projet.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Projets**, puis choisissez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour spécifier le projet avec les informations d'autres projets, cliquez sur **Copier projet**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

> [!NOTE]  
> Si vous utilisez des feuilles de temps dans le projet, vous devez également indiquer une personne responsable. Cette personne peut approuver les feuilles de temps pour les tâches des employés associées à ce projet. Pour plus d'informations, voir [Paramétrer des feuilles de temps](projects-how-setup-time-sheets.md).

Si vous le souhaitez, marquez les actions sur le projet comme bloquées à l’aide du champ **Bloqué**. Le tableau suivant décrit l'effet de ces options sur ce champ.

|Option  |Désignation  |
|---------|---------|
|Vide |Toutes les actions sont autorisées.|
|Report     |Vous pouvez utiliser des lignes planification, mais le report du projet est bloqué. Choisir cette option implique que vous ne pouvez pas reporter d'utilisation ni de vente sur le projet.|
|Tout  |Toutes les actions sont bloquées.|

## <a name="to-create-tasks-for-a-job"></a>Pour créer une tâche pour un projet

L'une des clés de la création d'un projet consiste à spécifier les différentes tâches impliquées dans le projet. Spécifiez les tâches en créant une ligne par tâche sur le raccourci **Tâches** de la page **Fiche projet**. Chaque projet doit avoir au minimum une tâche.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Projets**, puis choisissez le lien associé.
2. Ouvrez la fiche projet pour un projet concerné.
3. Sur le raccourci **Tâches**, renseignez les champs, le cas échéant sur une ligne.
4. Pour indenter des tâches et créer une hiérarchie, cliquez sur **Tâches**, puis sur **Indenter tâches projet**.
5. Répétez les étapes 3 et 4 pour toutes les tâches dont vous avez besoin pour le projet.
6. Pour spécifier les tâches du projet avec les informations d'autres tâches de projet, cliquez sur **Copier les tâches projet de**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**.

## <a name="to-create-planning-lines-for-a-job"></a>Pour créer des lignes planification pour un projet

Vous pouvez redéfinir vos nouvelles tâches projet sur les lignes planification projet. Une ligne planification peut extraire les information que vous souhaitez suivre pour un projet. Par exemple, vous pouvez suivre les ressources requises par le travail ou les éléments nécessaires. Par exemple, vous avez pour tâche d'amener un client à approuver un travail. Vous associez la tâche à des lignes planification article, comme un rendez-vous avec le client et l’affectation d’une ressource.  

Une ligne planification projet peut avoir l'un des types suivants :  

| Type | Description |
| --- | --- |
| **Budget** |Permet d'obtenir les utilisations et coûts prévus pour le projet, généralement dans le cadre d'un projet de régie. Les lignes planification de ce type ne peuvent pas être facturées. |
| **Facturable** |Permet de fournir un devis au client, généralement utilisé dans le cadre d'un projet à prix fixe. |
| **Budget et Facturable** |Permet de faire correspondre l'utilisation budgétée au montant que vous souhaitez facturer. |

> [!NOTE]
> Tandis que vous ajoutez des informations sur les lignes planification projet, le coût est automatiquement mis à jour. Par exemple, le coût, le prix et l'escompte relatifs aux ressources et aux articles sont calculés sur la base des informations de la ressource et de l’article. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Projets**, puis choisissez le lien associé.
2. Ouvrez la fiche projet appropriée.
3. Sélectionnez une tâche projet pour laquelle le champ **Type tâche projet** contient **Validation** puis, cliquez sur **Lignes planning projet**.  
4. Sur la page **Lignes planification projet**, renseignez les champs, le cas échéant sur une nouvelle ligne.
5. Répétez les phases 3 et 4 pour toutes les lignes planification dont vous avez besoin pour la tâche projet.

## <a name="see-also"></a>Voir aussi .

[Gestion de projets](projects-manage-projects.md)  
[Vidéo : Créer un projet dans Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Finances](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Vente](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
