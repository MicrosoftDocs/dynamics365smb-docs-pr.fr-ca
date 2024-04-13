---
title: Gestion des fournitures d'un projet
description: Décrit les différentes façons de gérer l’approvisionnement et l’achat de matériel et de services pour les projets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.search.keywords: 'project management, material, purchase'
ms.search.form: '98, 1020'
ms.date: 02/22/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---
# <a name="manage-project-supplies"></a>Gestion des fournitures d'un projet

Gérez des fournitures des projets relatifs à des articles, services et dépenses est l’un des aspects essentiels de tous projet. Vous pouvez utiliser les quantités en inventaire ou effectuer des achats spécifiques au projet en utilisant des bons de commande ou des factures achat. Par exemple, un projet de service sur un ordinateur requiert un nouveau disque. Vous devez donc créer une facture achat pour l’acheter et pour enregistrer le projet qui l'utilisé.

Si le processus d’achat ne requiert pas d’enregistrement séparé de la transaction physique, un achat peut être traité sur la page **Journal GL projet**. Pour plus d′informations, voir [Pour reporter des frais liés à un projet](projects-how-manage-project-supplies.md#to-post-a-project-related-expense).

## <a name="to-purchase-items-or-services-for-a-project"></a>Pour acheter des articles ou des services pour un projet

La procédure suivante indique comment utiliser une facture achat pour acheter des produits pour un projet. Les mêmes phases s'appliquent lors de l'utilisation d'un bon de commande.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Factures achat**, puis sélectionnez le lien associé.  
2. Sélectionnez l'action **Nouveau**, puis renseignez les champs selon vos besoins. Pour plus d'informations, voir [Enregistrer des achats](purchasing-how-record-purchases.md).
3. Dans le champ **N° projet** et les champs **N° tâche projet**, sélectionnez les informations du projet pour lequel vous souhaitez acheter des articles ou des services. Utilisez les outils de personnalisation si un champ n’est pas visible. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md).

    La valeur que vous sélectionnez dans le champ **Type ligne projet** définit si une ligne planification est créée lorsque vous reportez l’utilisation de l’article. Si le champ indique **Facturable**, les lignes planification projet prêtes pour facturation sont créées. Pour plus d’informations, reportez-vous à [Gestion des factures](projects-how-invoice-jobs.md).
4. Sélectionnez l'action **Valider**.

## <a name="to-view-the-value-of-purchases-for-a-project"></a>Pour afficher la valeur des achats pour un projet

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **projets**, puis choisissez le lien associé.
2. Ouvrez la fiche projet appropriée.

    Dans le raccourci **Tâches**, le champ **Commandes en suspens** affiche le montant total en suspens, en devise locale, des services et articles en inventaire sur les documents achat pour la ligne tâche projet.  

    Le champ **Montant reçu non facturé** affiche la valeur des articles livrés sur les documents achat mais non facturés.  
3. Choisissez l’un des champs pour ouvrir la page **Lignes achat** dans laquelle vous pouvez consulter des informations sur les lignes de document achat associées, incluant les articles ou les services réceptionnés.

## <a name="to-post-a-project-related-expense"></a>Pour reporter des frais liés à un projet

Si vous supportez les dépenses extraordinaires ou exceptionnelles du projet, vous pouvez utiliser la page **Journal GL projet** pour les reporter directement dans le compte projet approprié.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux GL projet**, puis choisissez le lien associé.  
2. Créez une ligne et renseignez les informations concernant les frais, notamment les informations des champs **N° projet** et **N° tâche projet**.  
3. Lorsque la feuille est renseignée, cliquez sur **Valider**.

## <a name="see-also"></a>Voir aussi .

[Gestion de projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser Business Central](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
