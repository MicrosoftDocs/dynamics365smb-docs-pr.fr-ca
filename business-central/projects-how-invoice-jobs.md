---
title: Créer une facture vente projet pour facturer un projet
description: Décrit comment facturer des clients pour les coûts au fur et à mesure de l’avancée du projet et des coûts accumulés.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.search.keywords: project invoice
ms.search.form: '1002, 1007,'
ms.date: 02/22/2024
ms.service: dynamics-365-business-central
---
# Facturation des projets

Au cours du projet, les coûts de projet provenant de l’utilisation de ressources, de matières, et d’achats associés au projet peuvent s’accumuler. Au fur et à mesure de la progression du projet, ces transactions sont reportées dans le journal projet. Il est important que tous les coûts soient enregistrés dans le journal projet avant de facturer le client.

> [!NOTE]
> Vous pouvez également acheter des ressources externes non liées à un projet, par exemple pour facturer un fournisseur pour le travail livré. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).

Vous pouvez facturer l’ensemble du projet à partir de la page **Lignes tâche projet** ou facturer uniquement les lignes facturables sélectionnées sur la page **Lignes planification projet**. La facturation peut avoir lieu une fois le projet terminé ou à certains intervalles au cours du projet sur la base d’une prévision de facture.

> [!NOTE]  
> Si vous sélectionnez **Facturable** dans le champ **Type ligne projet** dans les documents d’achat pour les achats associés au projet, les lignes planification projet prêtes pour facturation sont créées. Pour en savoir plus, voir [Gérer des fournitures d'un projet](projects-how-manage-project-supplies.md).

Vous pouvez également facturer une compagnie qui n’est pas le client final. Parfois, la partie à laquelle un projet est destiné est différente de celle qui paie la facture. Sur la page **Projets**, vous pouvez spécifier le client qui bénéficiera du projet dans les champs **Débiteur** et la partie à facturer dans les champs **Facturation**.

## Pour créer plusieurs factures vente projet

Vous pouvez créer une facture pour un projet ou pour une ou plusieurs tâches projet pour un client lorsque le travail à facturer est terminé ou lorsque la date de facturation dépendante d’un programme de facturation est atteinte.

La procédure suivante explique comment utiliser un traitement en lot pour facturer plusieurs projets.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Projet Créer facture vente**, puis sélectionnez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Définissez des filtres si vous souhaitez limiter le nombre de projets que le traitement en lot va traiter.
4. Pour créer les factures, cliquez sur le bouton **OK**.  

Vous pouvez examiner et reporter les factures créées dans la fenêtre **Factures vente**.

> [!NOTE]
> Sinon, facturez un client en sélectionnant le projet, puis en choisissant l’action **Créer une facture vente projet**. 

## Pour créer et reporter une facture vente projet à partir de lignes planification projet

Vous pouvez créer une facture à partir des lignes planification projet et indiquer à ce moment-là la quantité de l’article, la ressource ou le compte GL sur lequel vous souhaitez facturer.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **projets**, puis choisissez le lien associé.
2. Ouvrez le projet approprié.
3. Sélectionnez une tâche projet pour laquelle le champ **Type tâche projet** contient **Report**, puis choisissez l’action **Lignes planification projet**.  
4. Dans une ligne planification projet, dans le champ **Qté à transférer à facturer**, saisissez la quantité de l’article, la ressource et le type de compte GL sur lequel vous souhaitez facturer.  
5. Cliquez sur **Créer facture vente**.
6. Sur la page **Projet Transférer facture vente**, saisissez la date de report et si vous souhaitez créer une facture ou ajouter cette facture à une facture existante.
7. Cliquez sur le bouton **OK**.  
8. Sur la page **Lignes planification projet**, choisissez l’action **Notes de crédit/Factures vente**.

    La page **Facture vente** s'ouvre et affiche la quantité que vous avez transférée à la facture.
9. Apportez les modifications supplémentaires, puis cliquez sur **Valider**.

> [!NOTE]  
> La procédure ci-dessus permet également de créer, de consulter, puis de reporter une note de crédit vente associée à un projet.

## Voir aussi .

[Gestion des projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
