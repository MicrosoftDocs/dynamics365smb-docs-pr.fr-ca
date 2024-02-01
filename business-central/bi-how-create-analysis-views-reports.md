---
title: Créer des rapports d'analyse
description: 'Décrit comment créer de nouveaux rapports d''analyse pour les ventes, les achats et l''inventaire, et configurer des modèles d''analyse.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '555, 556, 557, 558, 9372, 9370, 9371'
ms.date: 09/22/2022
ms.author: bholtorf
ms.service: dynamics-365-business-central
---
# Créer des rapports d'analyse

Les directeurs des ventes doivent analyser de manière régulière les rotations, le profit bénéficiaire brut et d’autres indicateurs de performance des ventes clés. Les acheteurs, eux, s’intéressent plutôt à la dynamique des volumes d’achat, des performances des fournisseurs et des prix d’achat. Par ailleurs, les gestionnaires des inventaires et directeurs de la logistique ont besoin d'informations sur la rotation des inventaires, d'une analyse des mouvements d'inventaire et de statistiques sur la valeur d'inventaire. Il n’y a donc pas de rapport d’analyse qui convienne à toutes les situations.

Vous pouvez personnaliser les rapports d’analyse basés sur les enregistrements de vos transactions reportées, comme les ventes, les achats, les transferts et les ajustements inventaire. Dans les rapports personnalisés, les données source, provenant du grand livre article (comportant des écritures valeur associées), peuvent être combinées, comparées et présentées de plusieurs manières, conformément aux souhaits de l’utilisateur. En ce sens, les rapports d'analyse sont très proches des rapports de tableau croisé dynamique de Microsoft Excel.  

Ainsi, par exemple, vous pouvez créer un rapport personnalisé qui se concentre sur vos comptes principaux en termes de chiffre d’affaires total des produits en montants et quantités vendus, de profit brut et de pourcentage de profit brut au cours du mois en cours. Ensuite, vous pouvez lui demander de comparer ces chiffres avec les résultats des mois précédents ou du même mois l’année dernière, et de calculer les écarts. Vous pouvez effectuer toutes ces opérations dans une seule et même vue, ce qui vous permet d’accéder à la cause des zones problématiques identifiées, et même de sélectionner le menu déroulant pour détailler au maximum les transactions individuelles.  

Les rapports d’analyse sont constitués des objets à analyser (par exemple, les clients, les groupes de clients, les vendeurs, etc.), représentés sous forme de lignes, et des paramètres d’analyse, qui déterminent la manière dont vous souhaitez analyser les objets, (par exemple, calculs de profit, comparaisons périodiques des volumes et des montants vente, ou comparaisons périodiques des chiffres réels et budgétés, représentés sous forme de colonnes). 

Outre les rapports d’analyse, vous pouvez créer et afficher des informations similaires dans des vues d’analyse (basées sur des dimensions). Pour en savoir plus, voir [Analyse des données par dimensions](bi-how-analyze-data-dimension.md).

## Exemple :

Vous pouvez configurer ces lignes (objets que vous souhaitez analyser) :  

- Ordinateurs  
- Ecrans  
- Pièces de rechange  

Ensuite, vous pouvez configurer ces colonnes (comment vous voulez que les objets soient analysés) :  

- Ventes mois en cours  
- Ventes mois précédent  
- Ventes mois précédent (en %)  

## Configuration des dispositions de ligne et de colonne

Sur la page **Rapport d’analyse**, vous pouvez afficher différentes présentations de ligne et de colonne, à définir sur :

* la page **Modèles de ligne d’analyse** où vous définissez le nom du rapport et les objets à inclure dans les lignes du rapport, et
* la page **Modèles de colonne d’analyse** où vous définissez le nom du modèle de colonne et les paramètres d’analyse à inclure dans le rapport sous forme de colonnes. Chaque ligne de cette page représente une colonne du rapport. 

Les lignes et les colonnes d'analyse sont indépendantes les unes des autres.  

Selon les lignes et les colonnes configurées, [!INCLUDE[prod_short](includes/prod_short.md)] agrège le résultat du rapport sur la page **Rapport d’analyse**, comme indiqué dans la table suivante.  

|- |Ventes mois en cours|Ventes mois précédent|Ventes mois précédent (en %)|  
|-|-|-|-|  
|Ordinateurs| | | |  
|Ecrans| | | |  
|Pièces de rechange| | | |  
|Total| | | |  

Vous pouvez, par exemple, définir un groupe de lignes et plusieurs groupes de dispositions de colonne afin d’afficher respectivement les rapports mensuel et annuel.

## Configurer des modèles de colonne d’analyse

La procédure suivante se base sur des vues d’analyse des ventes. Les étapes sont similaires aux vues d'analyse d'achat et d'inventaire.

Un modèle de colonne d’analyse contient un ensemble de lignes, chacune représentant une colonne d’analyse souhaitée dans le rapport d’analyse. Pour définir une colonne, attribuez un code type analyse à une ligne. Ce code type analyse détermine le type de données origine dans les écritures du grand livre d'articles sur lequel l'analyse est basée. Les données source peuvent inclure les coûts, le montant vente ou la quantité et leurs écritures valeur associées. Vous pouvez configurer autant de modèles de colonne que nécessaire, puis les utiliser pour créer des rapports d’analyse.    

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles de colonne Vente**, puis sélectionnez le lien associé.  
2. Sélectionnez la première ligne vide, puis renseignez les champs selon vos besoins.
3. Sélectionnez l'action **Colonnes**.  
4. Sur la page **Colonnes d’analyse**, renseignez les champs afin d’indiquer les colonnes à inclure dans le rapport d’analyse.  

    > [!NOTE]  
    > Pour définir une colonne, renseignez le champ **Code type analyse** de tous les types de colonne sauf **Formule**. Configurez les codes type analyse sur la page **Types d'analyse**.  
    
    En outre, si vous sélectionnez **Écritures article** dans le champ **Type écriture**, les chiffres réels issus de l'écriture article sont copiés. Si vous sélectionnez **Ecritures budget article**, les chiffres budgétés à partir du budget sont copiés.  
5. Sélectionnez **OK** pour enregistrer vos modifications.  

## Configurer des modèles de ligne d’analyse

La procédure suivante se base sur des rapports d'analyse des ventes. Les étapes sont similaires aux rapports d'analyse d'achat et d'inventaire.

Un modèle de colonne d’analyse contient un ensemble de lignes, chacune représentant une ligne d’analyse souhaitée dans le rapport d’analyse. Une ligne peut indiquer un ou plusieurs articles, clients, fournisseurs ou groupes. Vous pouvez également créer dans une ligne une formule totalisant les autres lignes. Vous pouvez configurer autant de modèles de ligne que nécessaire, puis les utiliser pour créer des rapports d’analyse.   

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Modèles de ligne Vente**, puis sélectionnez le lien associé.  
2. Sélectionnez la première ligne vide, puis renseignez les champs selon vos besoins.
3. Sélectionnez l'option **Lignes**.  
4. Sur la page **Ligne d'analyse**, créez des lignes pour les articles, clients, fournisseurs ou représentants dont vous voulez voir les chiffres dans votre rapport d'analyse. Vous devez renseigner les champs **Type**, **Plage** et **Désignation**.  

> [!NOTE]  
> Autrement, pour créer plusieurs lignes distinctes pour chaque article, client, etc., vous pouvez également sélectionner l’option d’insertion appropriée pour renseigner tous les champs pertinents de la ligne. Si vous le souhaitez, vous pouvez alors modifier les lignes manuellement. Pour insérer des lignes, choisissez l’action **Insérer des articles** ou **Insérer des groupes articles**.  

## Créer un rapport d’analyse vente

La procédure suivante se base sur des rapports d'analyse des ventes. Les étapes sont similaires aux rapports d'analyse d'achat et d'inventaire.

Avec les rapports d’analyse, vous pouvez analyser la dynamique de vos ventes en fonction d’indicateurs de performances clés des ventes, par exemple le volume des ventes en termes de montant et de quantité, la marge contributive ou l’évolution des ventes réelles par rapport au budget. Ils peuvent également servir à analyser vos prix de vente moyens et à évaluer les performances de vos commerciaux.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports d’analyse Vente**, puis sélectionnez le lien associé.  
2. Sur la page **Rapports d'analyse vente**, cliquez sur l'action **Nouveau**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Choisissez l'action **Modifier le rapport d'analyse**.
5. Sur la page **Rapport d'analyse des ventes**, cliquez sur l'action **Afficher matrice**.  

> [!NOTE]  
> Si vous le souhaitez, vous pouvez mettre au point des combinaisons de modèles de ligne et de colonne pour créer des états et leur affecter des noms uniques. Dans ce cas, vous n’aurez pas à sélectionner des modèles de ligne et de colonne sur la page **Rapport d’analyse vente**. Une fois que vous avez choisi un nom de rapport, vous pouvez changer individuellement les modèles de ligne et de colonne et ensuite sélectionner une nouvelle fois le nom du rapport afin de restaurer la combinaison d'origine.

## Voir aussi .

[Décisionnel pour le secteur de la finance](bi.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
