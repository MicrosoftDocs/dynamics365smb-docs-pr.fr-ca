---
title: Exporter vos données Business Central vers Excel
description: 'Vous pouvez exporter vos rapports financiers et vos données de veille économique de Business Central vers Excel, ou ouvrir vos données dans Excel.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'analysis, reporting, financial report, business intelligence, BI, Excel'
ms.search.form: '9901,'
ms.date: 05/24/2024
ms.service: dynamics-365-business-central
---
# <a name="export-your-business-data-to-excel"></a>Exportation des données métier vers Excel

Excel est un outil puissant à utiliser avec les données. À partir de [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez ouvrir n’importe quelle liste dans Excel. Vous pouvez même modifier les données dans Excel, puis les renvoyer vers [!INCLUDE [prod_short](includes/prod_short.md)]. La même capacité vous permet d’emporter facilement vos données avec vous si vous décidez d’annuler votre abonnement.

## <a name="opening-lists-in-excel"></a>Ouverture de listes dans Excel

Vous pouvez ouvrir des données dans Excel à partir de n'importe quel journal, liste ou feuille de calcul. Il vous suffit d'ouvrir la page que vous souhaitez, puis de cliquer sur **Ouvrir dans Excel**. Par exemple, ouvrez la liste des clients (recherchez **Clients**), puis sélectionnez **Ouvrir dans Excel**. Votre navigateur vous invite à ouvrir ou à enregistrer le classeur Excel généré.  

> [!NOTE]
> Utilisez cette option si vous ne souhaitez pas republier vos modifications dans [!INCLUDE[prod_short](includes/prod_short.md)].  

Chaque liste inclut des colonnes. L'exportation vers Excel inclut toutes les colonnes qui se trouvent dans votre vue actuelle. Modifiez les colonnes en ouvrant le menu contextuel d’une colonne, puis en spécifiant les colonnes que vous souhaitez voir. La liste des colonnes est différente pour la plupart des listes. Les colonnes reflètent la structure de la base de données qui stocke vos données. Si vous n’êtes pas sûr du type de données que contient une certaine colonne, ajoutez-la à votre vue. Vous pouvez toujours la supprimer à nouveau.  

### <a name="edit-data-in-excel"></a>Modifier des données dans Excel

Votre expérience [!INCLUDE[prod_short](includes/prod_short.md)] inclut un complément pour Excel vous permettant de modifier des données dans Excel. Pour plus d'informations, voir [Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md).  

## <a name="exporting-data-to-other-finance-systems"></a>Exportation de données vers d’autres systèmes financiers

Si vous décidez d'annuler votre abonnement à [!INCLUDE[prod_short](includes/prod_short.md)], vous pouvez exporter vos données vers Excel et les transférer ensuite dans votre système financier suivant.  

Vous pouvez exporter toutes les pages, mais il peut y en avoir trop. Envisagez d’exporter les principales pages suivantes, et penser à ajouter toutes les colonnes :  

* Plan comptable  
* Clients  
* Fournisseurs  
* Banques  
* Articles  

Si vous souhaitez exporter toutes vos transactions financières, le volume de données est alors très important et l’exportation prend souvent plusieurs minutes. Les transactions financières sont affichées sur la page **Écritures**.  

Nous recommandons également d'exporter des données à partir des pages suivantes :  

* Écritures client  
* Détails écritures fournisseur  
* Écritures du grand livre de compte bancaire  
* Écritures article  
* Config. paramètres report  
* Groupes de report du client  
* Groupes de report du fournisseur  
* Groupes comptabilisation stock  
* Groupe de report banque  
* Budgets GL  
* Écritures budget  
* Devis  
* Factures vente  
* Factures achat  
* Contacts  
* Représentants  

> [!NOTE]  
> Si vous avez défini plusieurs sociétés dans [!INCLUDE[prod_short](includes/prod_short.md)], vous devez exporter les données appropriées de chaque société.

> [!NOTE]
> Vous devez disposer d'au moins l'une des autorisations suivantes pour ouvrir ou modifier des données dans Excel :
>
> * Ensemble d'autorisations *Action Exportation Excel D365*  
> * Autorisation système 6110 *Autoriser l'action Exporter vers Excel*.  

Pour plus d’informations, voir [Afficher ou modifier les autorisations d’un utilisateur](ui-define-granular-permissions.md#get-an-overview-of-a-users-permissions).

## <a name="see-also"></a>Voir aussi .

[Annuler pour votre abonnement [!INCLUDE[prod_short](includes/prod_short.md)]](admin-cancel.md)  
[Importation des données métier à partir d'autres systèmes financiers](across-import-data-configuration-packages.md)  
[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Finance](finance.md)  
[Fonctionnalités marché](ui-across-business-areas.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
