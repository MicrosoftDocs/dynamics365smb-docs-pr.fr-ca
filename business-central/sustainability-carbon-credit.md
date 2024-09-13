---
title: Travailler avec des crédits carbone
description: Apprenez comment configurer et acheter des crédits carbone.
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, carbon, credit, CO2'
ms.search.form: null
ms.date: 08/20/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: solsen
---

# Travailler avec le crédit carbone  

Lorsque les entreprises ne peuvent pas réduire leurs émissions pour diverses raisons, elles peuvent acheter des crédits carbone pour compenser leurs émissions. En achetant des crédits carbone, une entreprise peut toujours émettre la quantité équivalente de gaz tout en restant neutre en carbone. Ces crédits sont achetés auprès de fournisseurs spécialisés, incitant à la réduction des émissions.  

En général, les crédits carbone sont des permis qui permettent au propriétaire d’émettre une certaine quantité de dioxyde de carbone (CO₂) ou d’autres gaz à effet de serre (GES). Un crédit carbone représente généralement le droit d’émettre une tonne de CO₂ ou une quantité équivalente d’un autre GES. Il est donc important d’activer cette option pour certaines organisations.  

## Mettre en place le crédit carbone  

Le crédit carbone dans [!INCLUDE[prod_short](includes/prod_short.md)] peut être défini comme **élément**. Pour configurer l’élément comme crédit carbone, suivez les étapes suivantes : **·** 
  
1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis sélectionnez le lien associé. 
2. [Créez un nouvel élément comme expliqué](inventory-how-register-new-items.md).   
3. Une fois l’élément créé, Sélectionner le champ **Crédit GES** du raccourci **Durabilité**  et ajoutez la valeur du crédit carbone à l’aide du champ **Crédit carbone par UOM** .

> [!NOTE]
> **Le crédit carbone par UOM** représente la quantité de CO₂ dans l’unité de mesure configurée dans le **code d’unité de mesure d’émission** dans la **configuration de durabilité**. Cela signifie donc la valeur totale du crédit carbone en tant que quantité de CO₂ créditée par unité de mesure de base d’article utilisé. **·**   

> [!NOTE]
> Vous pouvez configurer n’importe quel type d’article, qu’il s’agisse d’un inventaire, d’un service ou d’un élément non inventaire, en tant que crédit carbone.  

## Pour acheter des crédits carbone 

### Documents achat 

Pour travailler avec des documents liés à l’achat, suivre les étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") Icône et :  
   1. Saisissez **Factures d’achat** si vous souhaitez une facture comme **type de document**, puis Sélectionner le lien associé.  
   2. Saisissez **Bons de commande** si vous souhaitez commander en tant que **type de document**, puis Sélectionner le lien associé.   
2. Remplissez l’en-tête du document en fonction des instructions suivantes [comment travailler avec les factures d’achat et les commandes](purchasing-how-record-purchases.md). 
3. Choisissez l’élément configurer comme crédit carbone dans le **Non.** Champ dans les lignes du document d’achat et ajoutez la **quantité** et le **coût unitaire direct** appropriés. 
4. Ajoutez le **numéro de compte de développement durable** que vous utiliseriez pour réduire votre valeur de dioxyde de carbone (CO₂). Le système remplira automatiquement la valeur dans le champ **Émission de CO2** en fonction de la valeur que vous avez configurée dans le champ **Crédit carbone par UOM** sur **l’élément** carte.
5. Validez le document.

> [!NOTE]
> Bien que le crédit carbone diminue la valeur des entrées, vous verrez une valeur positive dans les **émissions de CO2**. Mais une fois que vous aurez publié le document, vous verrez une valeur avec un logarithme négatif dans l’ **entrée du grand livre de développement durable** avec le **crédit GES** comme **type de document**.  

### Journaux durabilité 

Pour travailler avec **Sustainability Journal** suivre suivez les étapes :  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal durabilité**, puis sélectionnez le lien associé. 
2. Sur la page **Journal de développement durable**, saisissez autant de lignes que vous souhaitez publier dans le même lot.  
3. Choisissez le **Crédit GES** dans le champ **Type de document** .    
4. Dans le champ **N° de compte**, vous pouvez sélectionner uniquement les comptes de durabilité non bloqués pour lesquels le champ **Report direct** est sélectionné et le champ **Type de comptabilité** est défini sur **Report**. Les comptes doivent être également configurés avec une catégorie et une sous-catégorie. Choisissez le compte approprié pour publier des crédits carbone.
5. Sélectionner **Saisie manuelle** et entrez la valeur que vous souhaitez publier en tant que crédit carbone dans le champ **Émission CO2** .  
6. Reportez le journal.   

## Voir aussi .

[Finances](finance.md)    
[Enregistrer les entrées de durabilité](finance-sustainability-journal.md)    
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)    
[Configuration de durabilité](finance-sustainability-setup.md)   
[Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md)  
[Analyse ad hoc des données de durabilité](ad-hoc-analysis-sustainability.md)    
[Rapports et analyses sur la durabilité [!INCLUDE[prod_short](includes/prod_short.md)]](sustainability-reports.md)   
[API de durabilité](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
