---
title: Graphique des comptes de durabilité et de comptabilité
description: 'Découvrez comment gérer le tableau des comptes, catégories et sous-catégories de développement durable ainsi que les détails sur les écritures du grand livre de développement durable.'
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, CoA, Chart, Account, Ledger'
ms.search.form: '6210, 6213, 6214, 6220'
ms.date: 04/02/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# <a name="chart-of-sustainability-accounts-and-ledger"></a>Graphique des comptes de durabilité et de comptabilité

## <a name="chart-of-sustainability-accounts"></a>Graphique des comptes de durabilité

Le **Graphique des comptes de durabilité** (CoSA) constitue la liste structurée fondamentale utilisée pour enregistrer toutes les données sur les émissions. Il fonctionne comme un cadre qui catégorise et organise les comptes de durabilité en fonction de leurs attributs, tels que la portée ou d’autres regroupements. Chaque compte se voit généralement attribuer un code ou un numéro unique pour faciliter la référence et le suivi, suivant la même structure qu’un **plan comptable traditionnel** mais personnalisé spécifiquement pour le suivi des données et des données liées au développement durable. indicateurs au sein d’une organisation. 
 
Les utilisateurs peuvent ajouter des **catégories de compte** et **sous-catégories** pour définir le comportement du système, en sélectionnant les émissions dédiées au suivi et les facteurs d’émission, formules et configurations similaires.  

>[!NOTE]
>Pour se familiariser avec les scopes, basés sur les normes GES (Gaz à Effet de Serre), il existe trois scopes d’émissions :  
>- **Émissions de portée 1** : incluent les émissions émises par la combustion de produits fixes et mobiles, ainsi que par les émissions fugitives accidentelles. 
>- **Les émissions de scope 2** : incluent les émissions indirectes provenant de la production d’énergie achetée auprès de fournisseurs d’électricité. 
>- **Émissions de portée 3** : incluent un large spectre d’émissions, provenant des biens et services achetés et des biens d’équipement, des activités liées aux carburants et à l’énergie, aux transports en amont et en aval, aux déchets générés, aux voyages d’affaires et aux déplacements domicile-travail des employés, etc. 

Vous pouvez effectuer les opérations suivantes à partir du **Graphique des comptes de durabilité** (CoSA) :  

-   Affichez les rapports qui affichent les écritures durabilité et les soldes. 
-   Ouvrir **Fiche de compte de durabilité** pour ajouter ou modifier des paramètres.  
-   Consultez la catégorie et la sous-catégorie de ce compte.   
-   Consultez les soldes distincts pour chacune des émissions d’un seul compte. 
-   Ajoutez une ou plusieurs **dimensions** à chacun des comptes et définissez un filtre de dimension. 
    
Vous pouvez ajouter, modifier ou supprimer **Fiche de compte de durabilité**. Toutefois, pour éviter les écarts, vous ne pouvez pas supprimer un **Compte durabilité** s’il existe une ou plusieurs écritures associées à ce compte.  

### <a name="add-or-change-accounts"></a>Ajouter ou modifier les comptes

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Graphique des comptes de durabilité**, puis choisissez le lien associé. 
2. Sur **Graphique des comptes de durabilité** (CoSA), vous pouvez ouvrir chaque **comptes de durabilité** et ajouter ou modifier des paramètres. Positionnez le curseur sur un champ pour lire une brève description. 

Pour les comptes de type **Total**, vous devez renseigner le champ **Totalisation**. Pour les comptes de type **Fin total**, ce champ est renseigné automatiquement par la fonction Décaler. Après avoir configuré tous les comptes, choisissez l’action **Décaler graphique des comptes de durabilité** pour ce faire.  

>[!IMPORTANT]
>Si vous avez entré des définitions dans les champs **Totalisation** pour les comptes de type **Fin total** avant d’exécuter la fonction de décalage, vous devez les entrer à nouveau car cette fonction remplace les valeurs de tous les champs **Fin total**.  

### <a name="delete-accounts"></a>Supprimer les comptes

Vous pouvez supprimer un **comptes de durabilité**. Toutefois, avant de le supprimer, vous devez vous assurer qu’il existe une ou plusieurs écritures associées à ce compte, car Business Central vous empêchera de supprimer un **compte durabilité** dans ce cas.  

## <a name="account-categories"></a>Catégories de compte

Les utilisateurs doivent ajouter la **Catégorie de compte de durabilité** à chacun des **Comptes de durabilité** pour définir le comportement du système, en sélectionnant périmètres d’émission, émissions dédiées pour le suivi, formules et configurations similaires.  

Pour examiner les **catégories de comptes de durabilité**, procédez comme suit : 

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Catégories des comptes de durabilité**, puis choisissez le lien associé. 
2.  Sur la page **Catégories de comptes de durabilité**, vous pouvez modifier la liste existante ou créer une nouvelle catégorie. Pour créer une nouvelle catégorie, sélectionnez l’action **Nouveau** .  
3.  Renseignez les champs **Code** et **Désignation**.   
4.  Configurez le champ **Portée des émissions** en choisissant l’une des options de portée.  
5.  Sélectionnez les émissions de gaz que vous souhaitez suivre. Actuellement, vous pouvez utiliser l’une des options : **CO2**, **CH4** ou **N2O**. Vous pouvez choisir n’importe quelle combinaison que vous souhaitez suivre, mais vous devez avoir au moins une émission pour le suivi.  
6.  Dans le champ **Fondation de calcul** , vous pouvez choisir l’une des formules que vous souhaitez utiliser, au cas où vous ne connaissez pas la quantité exacte d’émission. Ici, vous pouvez spécifier la base du calcul (formule) des émissions. Vous pouvez choisir l’une des options suivantes : **Carburant/Électricité**, **Distance**, **Installation** ou **Personnalisée**. 
7.  Si vous choisissez la formule **Personnalisée** , vous pouvez configurer une description personnalisée dans le champ **Valeur personnalisée** .  

>[!NOTE]
>Si cet ensemble de formules proposées dans le champ **Fondation de calcul** n’est pas suffisant, vous pouvez étendre ce champ et ajouter d’autres calculs au système à utiliser dans le **Journaux de durabilité**.  

Si vous utilisez le **Fondation de calcul** (formules), il y a une explication sur la façon dont le système calculera en fonction de l’option que vous avez choisie (**EF** est le **Facteur d’émission** que vous pouvez configurer dans le **Sous-catégorie de compte de durabilité** page) : 

|  Type d'émissions  |  Base de calcul  |  Formule         | Commentaires      |
|------------|--------------|------------------------------|---------------------------------|
| **Étendue 1**  |
| Combustion stationnaire | Carburant/électricité | Émissions = Carburant * EF | _c’est-à-dire, Carburant = Quantité de carburant dépensée pour les chaudières, les appareils de chauffage, les oxydants thermiques..._ |
| Combustion mobile | Carburant/électricité | Émissions = Carburant * EF | _c’est-à-dire Carburant = Quantité de carburant dépensée pour les véhicules routiers ou non routiers, ferroviaires..._ |
|  |  |  Émissions = Distance * EF | _c’est-à-dire Distance = kilométrage des véhicules routiers ou non routiers, ferroviaires..._ |
| Émissions fugitives | Installation | Émission = Multiplicateur d’installation * Montant personnalisé / 100 * Facteur temps | _c’est-à-dire, montant personnalisé = pertes d’assemblage, taux de fuite annuel..._ |
| **Étendue 2**  |
| Fournisseurs de services publics | Carburant/électricité | Émissions = Électricité * FE | _c’est-à-dire, Combustible/Électricité = quantité d’électricité, quantité de vapeur, unité de chauffage..._ |
|  | Personnalisé | Émission = Montant personnalisé * EF | _c’est-à-dire, montant personnalisé = unité thermique, tonne-heure..._ |
| **Étendue 3**  |
| Biens et services achetés et biens d’équipement | Personnalisé | Émission = Montant personnalisé * EF | _c’est-à-dire, Montant personnalisé = Coût (GL)..._ |
| Transport et distribution en amont | Distance | Émissions = Distance * EF |  |
|  | Distance | Émissions = Distance * Multiplicateur * EF | _Multiplicateur = Tonnes de fret_ |
| Transport et distribution en aval | Distance | Émissions = Distance * EF |  |
|  | Distance | Émissions = Distance * Multiplicateur * EF | _Multiplicateur = Tonnes de fret_ |
| Déchets générés lors des opérations et traitement de fin de vie des produits vendus | Personnalisé | Émission = Montant personnalisé * EF | _c’est-à-dire, Montant personnalisé = Déchets..._ |
| Voyages d’affaires et déplacements domicile-travail des employés | Distance | Émissions = Distance * EF | _c’est-à-dire Distance = Kilométrage de la voiture de fonction utilisée, de la voiture de location, du train, de l’avion..._ |
|  | Personnalisé | Émission = Montant personnalisé * EF | _c’est-à-dire, Montant personnalisé = Séjours à l’hôtel..._ |
|  | Carburant/électricité | Émissions = Carburant * EF | _c’est-à-dire Carburant = Quantité de carburant dépensée dans la voiture de fonction, la voiture de location..._ |

## <a name="account-subcategories"></a>Sous-catégories du compte

Les utilisateurs doivent ajouter le **Sous-catégorie de compte de durabilité** à chacun de **Comptes de durabilité** pour définir les facteurs d’émission qui seront utilisés dans les formules, mais cela repose sur le choix de suivi des émissions dans le **Catégorie de compte de durabilité**.  

Pour examiner les **sous-catégories de comptes de durabilité**, procédez comme suit :  

1.  Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Sous-catégories des comptes de durabilité**, puis choisissez le lien associé. 
2.  Sur la page **Sous-catégories de comptes de durabilité**, vous pouvez modifier la liste existante ou créer une nouvelle catégorie. Pour créer une nouvelle catégorie, sélectionnez l’action **Nouveau** .  
3.  Renseignez les champs **Code** et **Désignation**.   
4.  En fonction des émissions de gaz que vous souhaitez suivre dans le **Catégorie de compte de durabilité**, et connectez cette sous-catégorie avec, vous pouvez également renseigner un ou plusieurs facteurs d’émission : 

   - **facteur d'émission CO2** : Spécifie le facteur d’émission pour les émissions de CO2.  
   - **facteur d'émission CH4** : Spécifie le facteur d’émission pour les émissions de CH4. 
   - **facteur d'émission N2O** : Spécifie le facteur d’émission pour les émissions de N2O.  

5.  Si cette sous-catégorie est liée aux énergies renouvelables, sélectionnez la **Énergie renouvelable** champ.   

>[!NOTE]
>Les champs **Importer des données** et **Importer de** sont destinés à une intégration potentielle avec des systèmes externes utilisés pour collecter des facteurs d’émission, mais dans la **1re vague de lancement 2024**, ils ne peuvent pas être utilisés comme fonctionnalité par défaut.  

## <a name="sustainability-ledger-entries"></a>Écritures durabilité

Le **Grand livre durabilité** stocke l’historique de toutes les transactions durabilité reportées, en organisant toutes les données d’émission selon le **Plan des comptes durabilité**. Lorsqu’un utilisateur publie le **Journal de durabilité**, toutes les données cruciales y seront enregistrées. Tous les rapports actifs sont générés en fonction du **Écritures comptable de durabilité**.   

L’utilisateur peut ouvrir ce grand livre pour un compte spécifique à l’aide de l’action **Écriture comptable** de la page **Graphique des comptes de durabilité** ou, pour ouvrir toutes les écritures du grand livre, sélectionnez l’ampoule ![qui ouvre la fonctionnalité La fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Écritures durabilité**, puis sélectionnez le lien associé. Positionnez le curseur sur un champ pour lire une brève description.  

>[!IMPORTANT]
>Une fois que vous avez reporté vos données dans le Grand livre durabilité, vous ne pouvez pas les supprimer. Si vous avez commis une erreur, vous pouvez reporter la transaction inversée en utilisant les mêmes détails, mais en utilisant le signe négatif pour le montant.  

## <a name="see-also"></a>Voir aussi .
[Finances](finance.md)    
[Présentation de la gestion du développement durable](finance-manage-sustainability.md)
[Configuration du développement durable](finance-sustainability-setup.md)
[Comment enregistrer les émissions](finance-sustainability-journal.md)
[Travailler avec [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
