---
title: Plan comptable et comptabilité de durabilité
description: 'Découvrez comment gérer le tableau des comptes, catégories et sous-catégories de développement durable ainsi que les détails sur les écritures du grand livre de développement durable.'
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, CoA, Chart, Account, Ledger'
ms.search.form: '6210, 6213, 6214, 6220'
ms.date: 05/07/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# Plan comptable et comptabilité de durabilité

## Graphique des comptes de durabilité

Le Graphique des comptes de durabilité (CoSA) constitue la liste structurée fondamentale utilisée pour enregistrer toutes les données sur les émissions. Il fonctionne comme un cadre qui catégorise et organise les comptes de durabilité en fonction de leurs attributs, tels que la portée ou d’autres regroupements. Chaque compte se voit généralement attribuer un code ou un numéro unique pour faciliter la référence et le suivi. Il a la même structure qu’un plan comptable traditionnel, mais est personnalisé spécifiquement pour surveiller les données et les mesures liées au développement durable dans une organisation.

Les utilisateurs peuvent ajouter des catégories de comptes de développement durable et des sous-catégories de comptes de développement durable pour définir le comportement du système. De cette manière, ils peuvent sélectionner des émissions dédiées à suivre, des facteurs d’émission, des formules et des configurations similaires.

> [!NOTE]
> Selon les normes GES (Gaz à Effet de Serre), il existe trois champs d’émissions :
>
> - **Émissions de champ 1** incluent les émissions émises par la combustion de produits stationnaires et mobiles, ainsi que par les émissions fugitives accidentelles.
> - **Les émissions de champ 2** incluent les émissions indirectes provenant de la production d’énergie achetée auprès de fournisseurs d’électricité.
> - **Émissions de champ 3** incluent un large spectre d’émissions, provenant des biens et services achetés et des biens d’équipement, des activités liées aux carburants et à l’énergie, aux transports en amont et en aval, aux déchets générés, aux voyages d’affaires et aux déplacements domicile-travail des employés, etc.

À partir du Graphique des comptes de durabilité (CoSA), vous pouvez faire les choses suivantes :

- Affichez les rapports qui affichent les écritures durabilité et les soldes.
- Ouvrir Fiche de compte de durabilité pour ajouter ou modifier des paramètres.
- Afficher la catégorie et la sous-catégorie du compte. 
- Consulter les soldes distincts pour chacune des émissions d’un seul compte.
- Ajouter une ou plusieurs dimensions à chacun des comptes et définir des filtres de dimension.

Vous pouvez ajouter, modifier ou supprimer des comptes de durabilité. Toutefois, pour éviter les écarts, vous ne pouvez pas supprimer un compte de durabilité si une ou plusieurs écritures lui sont associées.

### Ajouter ou modifier les comptes

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Graphique des comptes de durabilité**, puis choisissez le lien associé.
2. Sur **Graphique des comptes de durabilité**, vous pouvez ouvrir chaque compte de durabilité et ajouter ou modifier des paramètres. Positionnez le curseur sur un champ pour lire une brève description.

Pour les comptes de type **Total**, vous devez définir le champ **Totalisation**.

Pour les comptes de type **Fin total**, la fonction Décaler définit automatiquement le champ **Totalisation**. Après avoir configuré tous les comptes, sélectionnez l’action **Décaler plan comptable de durabilité** pour exécuter la fonction Décaler et définissez le champ **Totalisation**.

> [!IMPORTANT]
> La fonction Décaler écrase la valeur de tous les champs des comptes **Fin total**. Ainsi, si vous avez saisi des définitions dans le champ **Totalisation** pour les comptes **Fin total** avant d’exécuter la fonction Décaler, vous devez les saisir à nouveau après l'exécution.

### Supprimer les comptes

Vous pouvez supprimer un comptes de durabilité. Cependant, vous devez d’abord vous assurer qu’aucune écriture n’y est associée. Business Central vous évite de supprimer un compte de durabilité si une ou plusieurs écritures y sont associées.

## Catégories de compte

Les utilisateurs doivent ajouter une catégorie de compte de durabilité à chaque compte de durabilité pour définir le comportement du système. Ils peuvent sélectionner des champs d’émissions, des émissions dédiées à suivre, des formules et des configurations similaires.

Pour examiner les catégories de compte de durabilité, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Catégories des comptes de durabilité**, puis choisissez le lien associé.
2. Sur la page **Catégories de comptes de durabilité**, vous pouvez modifier la liste existante ou créer une nouvelle catégorie. Pour créer une nouvelle catégorie, sélectionnez l’action **Nouveau**.
3. Définissez les champs **Code** et **Description**.
4. Dans le champ **Champ de l’émission**, sélectionnant une des options de champ.
5. Sélectionnez les émissions de gaz que vous souhaitez suivre. Actuellement, les options suivantes sont disponibles : **CO2**, **CH4** et **N2O**. Vous pouvez sélectionner n’importe quelle combinaison que vous souhaitez suivre, mais vous devez sélectionner au moins une émission.
6. Dans le champ **Base de calcul**, vous pouvez sélectionner la base de calcul (formule) à utiliser pour les calculs d’émissions si vous ne connaissez pas la quantité précise d’émission. Vous pouvez sélectionner l’une des options suivantes : **Carburant/Électricité**, **Distance**, **Installation** ou **Personnalisée**.

    > [!NOTE]
    > Si l’ensemble de formules disponibles dans le champ **Fondation de calcul** n’est pas suffisant, vous pouvez étendre le champ et ajouter d’autres calculs au système à utiliser dans le journaux de durabilité.

7. Si vous avez sélectionné **Personnalisé** dans le champ **Fondation de calcul**, vous pouvez configurer une description personnalisée dans le champ **Valeur personnalisée**.

Si vous définissez le champ **Fondation de calcul**, le tableau suivant explique comment le système calcule les émissions en fonction de l’option que vous avez sélectionnée. (Dans cette table, *FE* représente la valeur **Facteur d’émission** que vous pouvez configurer sur la page **Sous-catégorie de compte de durabilité**.)

| Type d'émissions | Base de calcul | Formule | Commentaires |
|---------------|------------------------|---------|---------|
| **Étendue 1** | | | |
| Combustion stationnaire | Carburant/électricité | *Émissions* = *Carburant* &times; *EF* | *Carburant* = Quantité de carburant dépensée pour les chaudières, les appareils de chauffage, les oxydants thermiques, etc. |
| Combustion mobile | Carburant/électricité | *Émissions* = *Carburant* &times; *EF* | *Carburant* = Quantité de carburant dépensée pour les véhicules routiers ou non routiers, ferroviaires, etc. |
| | | *Émissions* = *Distance* &times; *EF* | *Distance* = Kilométrage des véhicules routiers ou non routiers, ferroviaires, etc. |
| Émissions fugitives | Installation | *Émissions* = *Multiplicateur d’installation* &times; *Montant personnalisé* &divide; 100 &times; *Facteur temps* | *Montant personnalisé* = pertes d’assemblage, taux de fuite annuel, etc. |
| **Étendue 2** | | | |
| Fournisseurs de services publics | Carburant/électricité | *Émissions* = *Électricité* &times; *FE* | *Carburant/Électricité* = quantité d’électricité, quantité de vapeur, unité de chauffage, etc. |
| | Personnalisé | *Émissions* = *Montant personnalisé* &times; *EF* | *Montant personnalisé* = Unité thermique, tonne-heure, etc. |
| **Étendue 3** | | | |
| Biens et services achetés et biens d’équipement | Personnalisé | *Émissions* = *Montant personnalisé* &times; *EF* | *Montant personnalisé* = Coût (GL), etc. |
| Transport et distribution en amont | Distance | *Émissions* = *Distance* &times; *EF* | |
| | Distance | *Émissions* = *Distance* &times; *Multiplicateur* &times; *EF* | *Multiplicateur* = Tonnes de fret |
| Transport et distribution en aval | Distance | *Émissions* = *Distance* &times; *EF* | |
| | Distance | *Émissions* = *Distance* &times; *Multiplicateur* &times; *EF* | *Multiplicateur* = Tonnes de fret |
| Déchets générés lors des opérations et traitement de fin de vie des produits vendus | Personnalisé | *Émissions* = *Montant personnalisé* &times; *EF* | *Montant personnalisé* = Déchets |
| Voyages d’affaires et déplacements domicile-travail des employés | Distance | *Émissions* = *Distance* &times; *EF* | *Distance* = Kilométrage de la voiture de fonction utilisée, de la voiture de location, du train, de l’avion, etc. |
| | Personnalisé | *Émissions* = *Montant personnalisé* &times; *EF* | *Montant personnalisé* = Séjours à l’hôtel |
| | Carburant/électricité | *Émissions* = *Carburant* &times; *EF* | *Carburant* = Quantité de carburant dépensée dans la voiture de fonction, la voiture de location, etc. |

## Sous-catégories du compte

Les utilisateurs doivent ajouter une sous-catégorie de compte de durabilité à chaque compte de durabilité. Cette sous-catégorie définit les facteurs d’émission utilisés dans les formules, en fonction du choix de suivi des émissions dans la catégorie du compte de durabilité.

Pour examiner les sous-catégories de comptes de durabilité, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sous-catégories des comptes de durabilité**, puis choisissez le lien associé. 
2. Sur la page **Sous-catégories de comptes de durabilité**, vous pouvez modifier la liste existante ou créer une nouvelle catégorie. Pour créer une nouvelle catégorie, sélectionnez l’action **Nouveau**.
3. Définissez les champs **Code** et **Description**.
4. En fonction des émissions de gaz que vous souhaitez suivre dans le Catégorie de compte de durabilité, et connectez cette sous-catégorie avec, vous pouvez également définir un ou plusieurs facteurs d’émission : 

    - **Facteur d’émission CO2** : le facteur d’émission des émissions de dioxyde de carbone (CO<sub>2</sub>).
    - **Facteur d’émission CH4** : le facteur d’émission pour les émissions de méthane (CH<sub>4</sub>).
    - **Facteur d’émission N2O** : le facteur d’émission des émissions d’oxyde d’azote (N<sub>2</sub>O).

5. Si la sous-catégorie est liée aux énergies renouvelables, sélectionnez le champ **Énergie renouvelable**.

> [!NOTE]
> Les champs **Importer des données** et **Importer à partir de** sont prévus pour une intégration potentielle avec des systèmes externes utilisés pour recueillir les facteurs d’émission. Cependant, dans la **1re vague de lancement 2024**, ces champs ne peuvent pas être utilisés comme fonctionnalité par défaut.

## Écritures durabilité

Le grand livre durabilité stocke l’historique de toutes les transactions de durabilité reportées, et organise toutes les données d’émission selon le plan des comptes de durabilité (CoSA). Lorsqu’un utilisateur effectue un report dans le journal durabilité, toutes les données cruciales y sont enregistrées. Tous les rapports actifs sont générés en fonction des écritures comptable de durabilité.

Pour ouvrir ce grand livre pour un compte spécifique, utilisez l’action **Écritures** sur la page **Graphique des comptes de durabilité**. Pour ouvrir toutes les écritures, sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures durabilité**, puis sélectionnez le lien associé. Positionnez le curseur sur un champ pour lire une brève description.

> [!IMPORTANT]
> Une fois que vous avez reporté vos données dans le grand livre durabilité, vous ne pouvez pas les supprimer. Si vous avez commis une erreur, vous pouvez reporter une transaction inversée utilisant les mêmes détails, mais utilisant le signe négatif pour le montant.

## Voir aussi .

[Finances](finance.md)  
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)  
[Configuration de durabilité](finance-sustainability-setup.md)  
[Procédure pour enregistrer des émissions](finance-sustainability-journal.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
