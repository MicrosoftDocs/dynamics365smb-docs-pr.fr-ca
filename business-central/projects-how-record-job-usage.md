---
title: Enregistrer la consommation ou l′utilisation des articles et des ressources du projet
description: Cet article décrit comment enregistrer la consommation ou l’utilisation des articles ou des ressources pour des projets dans la gestion de projets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 02/22/2024
ms.custom: bap-template
---
# <a name="record-consumption-or-usage-for-projects"></a>Enregistrer la consommation ou l′utilisation pour les projets

À partir de la page **Fiche projet**, vous pouvez ouvrir la page **Lignes planification projet** pour examiner et enregistrer l’utilisation sur diverses composantes de votre projet. Ces informations sont automatiquement mises à jour lorsque vous modifiez et transférez des informations entre projets et entre journaux projet et factures projet. Cela nécessite que vous activiez le bouton à bascule **Appliquer le lien d’utilisation par défaut** sur la page **Configuration projet**. En savoir plus sur [Configurer les projets](projects-how-setup-jobs.md).  

Par exemple, pour les lignes planification de type **Budget**, vous pouvez saisir la quantité d’une ressource, puis indiquer la quantité à transférer vers le journal projet. Si le type de la ligne planification est **Facturable**, vous pouvez saisir la quantité de la ressource, puis indiquer la quantité à transférer vers une facture. Pour en savoir plus sur la facturation du client, consultez [Facturation des projets](projects-how-invoice-jobs.md). En comparant la quantité d′origine, la quantité restante ou la quantité reportée, vous pouvez rapidement examiner les informations d′utilisation. Pour en savoir plus sur l’estimation des valeurs budgétées lors de la planification, consultez [Gérer les budgets de projets](projects-how-manage-budgets.md).  

Les procédures suivantes décrivent comment enregistrer les quantités (budgétées) et les coûts réels avec un journal projet. Sinon, vous pouvez utiliser les documents achat pour enregistrer les achats pour un projet. En savoir plus [Gérer les fournitures pour un projet](projects-how-manage-project-supplies.md).

## <a name="to-record-usage-for-a-project-planning-line-of-type-budget"></a>Pour enregistrer l’utilisation d’une ligne planification projet de type Budget

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **projets**, puis choisissez le lien associé.  
2. Sélectionnez le projet, puis choisissez l’action **Lignes planification projet**. 
3. Sélectionnez une ligne planification projet de type **Budget** ou **Budget et Facturable** pour laquelle vous voulez enregistrer une utilisation.   

    > [!NOTE]
    > Vous pouvez également enregistrer l’utilisation d′une ligne planification projet de type **Facturable**. En général, vous utilisez ces lignes pour créer des factures, mais vous pouvez également transférer les informations vers un journal. En savoir plus sur [Facturer des projet](projects-how-invoice-jobs.md) 

4. Dans le champ **Qté à transférer sur le journal**, entrez la quantité à transférer. La quantité par défaut est la même valeur que celle du champ **Quantité**.

    Le champ **Quantité restante** indique la quantité qui reste pour terminer le projet et à transférer au journal.
5. Choisissez l’action **Créer des lignes journal projet**.

    > [!TIP]
    > Si vous allez ajouter d’autres lignes planification projet pour ce projet, attendez avec cette étape jusqu’à ce que vous ayez ajouté toutes les lignes planification projet.
6. Sur la page **Projet Transférer la ligne planification projet**, renseignez les champs selon vos besoins, puis cliquez sur le bouton **OK**. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
7. Choisissez l’action **Ouvrir le journal projet**.  
8. Sur la page **Journal projet**, sélectionnez la ligne appropriée, puis choisissez l’action **Reporter**.

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

9. Sur la page **Lignes planification projet**, examinez l’utilisation enregistrée en observant les champs **Quantité**, **Quantité restante** et **Qté à transférer sur le journal**.  
10. Répétez les phases 3 à 8 pour enregistrer l'utilisation supplémentaire.  

## <a name="to-create-project-journal-lines-manually"></a>Pour créer des lignes journal projet manuellement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux projet**, puis choisissez le lien associé.  
2. Dans le champ **Nom du journal**, choisissez un nom de journal projet approprié.  
3. Dans une nouvelle ligne, entrez le numéro de document, le numéro de projet, le numéro tâche projet, le type et la quantité du type consommé.  
4. Lorsque les lignes journal projet sont renseignées, cliquez sur **Reporter**.  

    [!INCLUDE [preview-posting-inventory](includes/preview-posting-inventory.md)]

## <a name="to-view-project-usage-estimates-and-post-updates"></a>Pour visualiser les estimations projet et reporter les mises à jour

Vous pouvez visualiser l′utilisation projet jusqu’à son achèvement en une étape. Pour ce faire, utilisez le traitement en lot **Projet Calc. utilisation restante** pour toutes les tâches jusqu’à la fin d’un projet.  

Cela vous permet de suivre vos estimations initiales, de les comparer aux résultats réels, ainsi que d'apporter des modifications et d'ajouter de nouvelles écritures, selon les besoins. Par exemple, alors que vous aviez estimé qu’un projet nécessitait 10 heures de travail, vous en avez effectué 15. Vous pouvez ajouter les cinq heures supplémentaires à la ligne journal existante ou créer une ligne journal pour les déclarer en tant qu'heures supplémentaires, ce qui constitue un autre type de tâche. Le coût et le prix appropriés sont calculés. Vous pouvez les reporter dans le journal.  

> [!NOTE]  
> Les écritures article créent des écritures article et diminuent la quantité de l'inventaire. Le traitement par lots **Valider coûts ajustés** permet de transférer le coût du stock à la comptabilité. Les écritures ressource créent des écritures ressource.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux projet**, puis choisissez le lien associé.  
2. Sélectionnez un journal projet approprié, puis cliquez sur l’action **Calc. utilisation restante**.  
3. Sur la page **Projet Calc. utilisation restante**, entrez le numéro et la date de report du document devant être insérés dans le journal, puis sélectionnez le bouton **OK**.  
4. Mettez à jour le journal avec toutes les modifications qui peuvent être nécessaires.  
5. Sélectionnez l'action **Valider**.

## <a name="create-inventory-and-warehouse-pick-documents-for-a-project"></a>Créez des documents prélèvement entrepôt et inventaire pour un projet

Utilisez les actions **Créer un prélèvement inventaire** et **Créer un prélèvement entrepôt** sur la page **Fiche projet**. Pour créer ou enregistrer un document de prélèvement, utilisez les actions **Rangement/Lignes prélèvement/Lignes Mouvements** ou **Lignes prélèvement enregistrées**. En savoir plus [Flux pour la production, l’assemblage et les projets](design-details-internal-warehouse-flows.md).

Vous pouvez utiliser les actions dans les conditions suivantes :

* L’**état** du projet est **Ouvert**.
* Le **Type de ligne** de la ligne de planification du projet est **Budget** ou **Budget et Facturable**.
* Le **Type** de la ligne de planification du projet est **Article**.
* **Prélèvement requis** est activé pour l'emplacement associé.
* **Prélèv. et rangement dirigés** est désactivé.

> [!NOTE] 
> Bien que le paramètre s’appelle **Prélèvement requis**, vous pouvez toujours reporter la consommation directement à partir de la ligne du journal projet pour l’emplacement. Si votre emplacement est configuré pour exiger un traitement des prélèvements mais pas des livraisons, utilisez la page **Prélèvement inventaire** pour organiser et imprimer les informations de prélèvement. Vous utilisez également la page pour saisir et reporter le résultat du prélèvement, qui à son tour affiche la consommation des articles. 
> 
> Lorsque votre emplacement est configuré pour appeler un traitement de prélèvement et de livraison, ce qui implique que vous avez activé les champs **Prélèvement requis** et **Livraison requise** sur la page **Fiche emplacement**, utilisez le document **Prélèvement entrepôt** pour gérer le prélèvement. Les prélèvements entrepôt sont similaires aux prélèvements inventaire. La différence est qu'au lieu d'afficher les informations de prélèvement, vous enregistrez le prélèvement. Ce processus d’enregistrement ne reporte pas la consommation, il rend simplement les articles disponibles pour le report. En tant que responsable d’entrepôt, vous pouvez utiliser une feuille de calcul pour organiser les informations de prélèvement avant de créer les instructions de prélèvement d’entrepôt individuelles

## <a name="to-review-planning-lines-for-a-project-ledger-entry"></a>Pour consulter les lignes planification pour une écriture projet

Après avoir reporté les lignes journal projet, vous pouvez voir les lignes planification associées aux écritures journal projet qui ont été reportées.

> [!NOTE]  
> Cela nécessite que la case **Appliquer le lien d′utilisation** soit cochée pour le projet. Pour plus d’informations, voir [Configuration de projets](projects-how-setup-jobs.md).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux projet**, puis choisissez le lien associé.  
2. Sélectionnez un journal projet approprié, puis choisissez l’action **Écritures**.  
3. Sur la page **Écritures projet**, choisissez l’action **Afficher les lignes planification projet liées**.

## <a name="see-also"></a>Voir aussi .

[Gestion de projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
