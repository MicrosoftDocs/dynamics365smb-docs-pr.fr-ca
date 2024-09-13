---
title: Durabilité gestion des états financiers
description: Décrit comment utiliser les rapports financiers pour créer différentes vues et rapports permettant d’analyser les données de performance en matière de développement durable.
author: altotovi
ms.topic: conceptual
ms.search.keywords: reporting
ms.search.form: '104, 108, 490'
ms.date: 08/22/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# Analyse des écritures de durabilité avec les rapports financiers 

La fonctionnalité  *Rapports financiers* vous donne un aperçu des données financières affichées sur votre plan comptable (COA). Vous pouvez configurer les rapports financiers pour analyser les chiffres dans les comptes du grand livre (GL) et comparer les écritures GL et les écritures budget. Mais vous pouvez également analyser les données statistiques et de durabilité avec la même fonctionnalité, et même combiner les trois types de données.  

## Conditions préalables aux rapports financiers  

La création de rapports financiers nécessite une compréhension de la structure des données que vous souhaitez analyser. Il y a quelques concepts clés auxquels vous devez probablement prêter attention avant de concevoir vos rapports financiers : 

1. Concernant le plan comptable : 
   1. Mappez les comptes de report du grand livre aux catégories de comptes du grand livre. 
   2. Concevez la façon dont vous utilisez les dimensions.
   3. Configurer les budgets GL  
2. En rapport avec la durabilité :   
   1. Configurez vos comptes de développement durable. 
   2. Configurez vos frais carbone et CO2e dans les frais d’émission **.**
   3. Concevez la façon dont vous utilisez les dimensions.  
3. En rapport avec les comptes statistiques : 
   1. Paramétrez vos comptes statistiques. 
   2. Concevez la façon dont vous utilisez les dimensions.  

> [!NOTE]
> Les rapports financiers ne fonctionnent pas directement avec les émissions de CO2, CH4 ou N2O. Au lieu de cela, il utilise le modèle d’équivalent CO2 et cela signifie que vous devez d’abord configurer **CO2e** (équivalent dioxyde de carbone) sur la page **Frais d’émission** .  

> [!NOTE]
> Vous trouverez plus de détails sur l’utilisation des rapports financiers avec des données financières et un plan comptable ici [Créer des rapports financiers à l’aide de données financières et de catégories de comptes](bi-how-work-account-schedule.md).   

## Créer un rapport financier  

Pour créer rapidement vos propres rapports financiers, commencez par en copier un existant, tel que décrit à l’étape 3 ci-dessous. 

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.  
2. Sur la page **Rapports financiers**, choisissez l’action **Nouveau** pour créer un nom de rapport financier.  
3. Remplissez le nom court du rapport dans le champ  **Nom** (vous ne pourrez pas modifier le nom ultérieurement) et entrez  **Description**.  
4. Choisissez une définition de ligne et une définition de colonne.   
5. Choisissez l’action  **Modifier définition de rapport** pour accéder à plus de propriétés sur le rapport financier.  
6. Dans l’onglet rapide **Options**, vous pouvez modifier la description du rapport, modifier les définitions de ligne et de colonne et définir comment afficher les dates. Vous pouvez afficher les dates par jour, semaine, mois, trimestre, année ou périodes comptables. Pour en savoir plus, accédez à [Comparaison de périodes comptables à l’aide de formules de période](bi-column-definitions.md#comparing-accounting-periods-using-period-formulas). 
7. Dans l’onglet rapide **Dimensions** , vous pouvez définir des filtres de dimension pour le rapport.  
8. Vous pouvez prévisualiser le rapport dans la zone située sous l’onglet rapide **Dimensions** .   

Si vous souhaitez analyser vos données de durabilité ou statistiques, vous pouvez y parvenir en configurant le **définition de ligne**.  

Pour créer ou modifier un définition de ligne, suivre, procédez comme suit :

1. Sur la page **Rapports financiers**, sélectionnez le rapport financier souhaité, puis sélectionnez l’action **Modifier la définition de ligne**. 
2. Configurez les lignes comme dans les étapes suivantes.  

> [!NOTE]
> Le champ **N° ligne** affiche les 10 premiers caractères d’un identificateur, par exemple, un numéro de compte. Si vous ajoutez des éléments avec des identificateurs qui commencent par les mêmes 10 caractères, vous aurez des doublons dans le champ **N° ligne** . Si nécessaire, vous pouvez modifier manuellement les identificateurs après avoir inséré les éléments. Les identificateurs complets sont affichés dans le champ **Totalisation**.

> [!NOTE]
> Vous pouvez combiner tous les **types de totalisation**, c’est-à-dire les comptes de comptabilisation, les comptes de sout. Comptes, Compte statistique.

> [!NOTE]
> Les définitions de lignes ne sont pas versionnées. Lorsque vous modifiez un définition de ligne, l’ancienne version est remplacée et vos modifications seront enregistrées dans la base de données. 

### Analyse des données sur la durabilité  

1. Saisissez le numéro de ligne. **·** Pour identifier votre brut et ajouter **Description** comme texte qui apparaîtra sur la ligne du rapport financier. 
2. Dans la colonne Type de totalisation, choisissez l’option  **Comptes de suivi** .   
3. Dans le champ Totalisation, choisissez un ou plusieurs comptes de durabilité en utilisant tous les filtres applicables. 
4. Dans le **Type de montant** choisissez l’une des options :   
   1. **CO2e** si vous souhaitez signaler la valeur équivalente CO2 du champ **Émission de CO2e** dans les **Écritures du grand livre de développement durable**. 
   2. **taxe carbone** si vous souhaitez signaler l’équivalent financier (taxe carbone) à partir du **taxe carbone** champ des **écritures du grand livre de développement durable**. 
5. Si vous choisissez **Formule** comme **Type de totalisation**, vous pouvez utiliser des formules mathématiques dans la colonne **Totalisation** .  

### Analyser les données statistiques

1. Saisissez le numéro de ligne. **·** Pour identifier votre ligne et ajouter **Description** comme texte qui apparaîtra sur la ligne du rapport financier. 
2. Dans la colonne **Type de totalisation**, choisissez l’option **Comptes statistiques** .   
3. Dans le champ **Total**, choisissez un ou plusieurs comptes de durabilité en utilisant tous les filtres applicables. 
4. Si vous choisissez **Formule** comme **Type de totalisation**, vous pouvez utiliser des formules mathématiques dans la colonne **Totalisation** .  

## Voir aussi .

[Présentation de la gestion de la durabilité](finance-manage-sustainability.md)    
[Rapports de durabilité et analyses dans Business Central](sustainability-reports.md)   
[API de durabilité](/dynamics365/business-central/dev-itpro/api-sustainability/sustainability-api?toc=/dynamics365/business-central/toc.json)    
[Préparez gestion des états financiers](bi-how-work-account-schedule.md)    
[définition de ligne dans gestion des états financiers](bi-row-definitions.md)    
[définition de colonne dans le gestion des états financiers](bi-column-definitions.md)    
[Finances](finance.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)    

[!INCLUDE[footer-include](includes/footer-banner.md)]
