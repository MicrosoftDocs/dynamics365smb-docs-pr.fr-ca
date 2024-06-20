---
title: Rapport sur les pratiques de paiement
description: Découvrez comment créer facilement le rapport sur les pratiques de paiement pour les fournisseurs et les clients.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'payment, practices, vendor, customer, report'
ms.search.form: '686, 687, 689'
ms.date: 04/23/2024
ms.author: altotovi
ms.reviewer: bholtorf
--- 

# <a name="payment-practices-report"></a>Rapport sur les pratiques de paiement

Certains pays/régions exigent que les compagnies déclarent les délais de paiement de leurs fournisseurs tels que définis par les autorités locales. Ces rapports peuvent être basés sur différentes sources et peuvent trier les fournisseurs en fonction de leur taille ou de leurs modalités de paiement définies, fournissant ainsi des rapports aux fournisseurs sur les éléments suivants, comme l’exigent les autorités locales :  

- Période de paiement convenue moyenne.  
- Période de paiement réelle moyenne.   
- La proportion de factures payées après la fin du délai de paiement convenu. 

Les utilisateurs peuvent sélectionner la période pour laquelle ils souhaitent exécuter un calcul et rechercher des détails en fonction d’un regroupement que vous choisissez. Pour chacun de ces regroupements, vous pouvez trouver des entrées sourcées. 

> [!NOTE]
> Cette déclaration est jusqu’à présent requise dans certains pays, mais il s’agit d’une fonctionnalité mondiale qui peut être utilisée partout. Actuellement, chaque année, les compagnies suédoises de 250 employés et plus doivent déclarer au Bureau suédois d’enregistrement des compagnies les délais de paiement dont elles disposent pour les achats auprès de compagnies plus petites qu’elles. Des lois similaires existent au Royaume-Uni, en Australie et en Nouvelle-Zélande.  

## <a name="generate-the-report"></a>Générer le rapport

Pour exécuter le rapport **Pratiques de paiement** , procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Pratique paiement**, puis Sélectionner le lien associé. 
2. Sélectionnez **Nouveau**.
3. Entrer valeurs les champs suivant sur le raccourci **Général** :

   | Champ | Désignation |
   |---------|-----------------------------------|
   | N° | Spécifiez le numéro de l’entrée ou de l’enregistrement du rapport. |
   | Type agrégation | Spécifiez la manière dont les données sont agrégées. Si vous choisissez l’option **Période**, le rapport sera basé sur différentes périodes, mais si vous choisissez l’option **Taille de la compagnie**, le rapport est créé en fonction de la taille des compagnies configurée dans le champ **Code taille compagnie** de la fiche **Fournisseur**. |
   | Type d’en-tête | Spécifie la source des entrées dans la pratique de paiement et vous pouvez choisir Fournisseurs, Clients ou les deux. |
   | Date début | Spécifie la date début de la pratique de paiement. |
   | Date de fin | Indique la date de fin de la pratique de paiement. |

> [!NOTE]
> Si vous décidez d’utiliser l’option **Taille de la compagnie**, vous devez d’abord créer des écritures sur la page **Tailles de la compagnie** et les ajouter à tous les fournisseurs que vous souhaitez suivre par cette méthode.

4. Une fois que vous avez rempli tous les champs de l’en-tête, vous devez exécuter l’action **Générer** pour générer des données dans les lignes et des statistiques pour le type de rapport sélectionné.
5. En fonction du **type d’agrégation** , vous obtiendrez différentes lignes. Vous pouvez modifier certaines valeurs manuellement, mais dans ce cas, chacune des lignes modifiées et l’ensemble du rapport seront marqués comme **Modifié manuellement**.
6. À partir de tous les champs calculés, vous pouvez approfondir la façon dont ce résultat a été calculé en ouvrant la page **Liste des données sur les pratiques de paiement** .
7. Si vous souhaitez imprimer le document, vous pouvez le faire en exécutant l’action **Imprimer** .

## <a name="see-also"></a>Voir aussi .

[Rapports financiers](finance-reports.md)  
[Analyse des états financiers dans Microsoft Excel](finance-analyze-excel.md)  
[Rapports Comptabilité client et analyse](receivables-reports.md)  
[Rapports Comptabilité fournisseur et analyse](payables-reports.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Finances](finance.md)  
[Vue d’ensemble des fonctionnalités locales](about-localization.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
