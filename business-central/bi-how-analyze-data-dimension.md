---
title: Analyse des données par axe analytique
description: Cet article décrit comment analyser les données d’entreprise par dimensions pour mieux comprendre votre activité.
author: edupont
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '545, 555, 556, 557, 558, 9372, 9370, 9371'
ms.date: 09/22/2022
ms.author: edupont
---
# <a name="analyze-data-by-dimensions" />Analyse des données par axe analytique

En analyse financière, une dimension correspond à des données que vous ajoutez à une écriture comme une sorte de marqueur. Ces données permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les régions, les produits et les représentants, et de récupérer facilement ces groupes à des fins d'analyse. Les axes peuvent être utilisés sur des écritures de feuilles, de documents et de budgets. 

Chaque « dimension » décrit l’objet de l’analyse. Une analyse à deux axes, par exemple, est une analyse des ventes par zone. Si vous utilisez plus de deux dimensions lors de la création d’une écriture, vous pouvez mener une analyse plus complexe, telle que des ventes par promotion de vente, par groupe client et par zone. Cela vous permet d’obtenir un meilleur aperçu de votre activité commerciale, comme la mesure du bon fonctionnement de votre société, les domaines dans lesquels elle prospère ou non, et ceux dans lesquels il est nécessaire d’affecter davantage de ressources. Vous pouvez ainsi prendre de meilleures décisions pour mieux progresser. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

> [!TIP]
> Pour analyser rapidement les données transactionnelles par axe, vous pouvez filtrer les totaux du plan comptable (COA) et les écritures de toutes les pages **Écritures** par dimensions. Recherchez l'action **Définir le filtre dimension**.

> [!NOTE]
> Si vous découvrez qu’une valeur de dimension incorrecte a été utilisée sur les écritures reportées, vous pouvez la corriger et mettre à jour vos vues d’analyse. Pour plus d’informations, consultez la section [Dépannage et correction des dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting).

## <a name="set-up-an-analysis-view" />Configurer une vue d’analyse

Les analyses par dimensions utilisent une combinaison sélectionnée de dimensions. Vous stockez, récupérez et mettez à jour cet ensemble de dimensions en créant une fiche **Vue d’analyse**. 

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.  
2. Sur la page **Liste des vues d'analyse**, cliquez sur l'action **Nouveau**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Pour ajouter des codes dimension aux quatre codes du raccourci **Dimensions**, cliquez sur l’action **Filtre**, renseignez les champs, puis cliquez sur **OK**.  
5. Pour mettre à jour la vue, choisissez l'action **Mettre à jour**.

## <a name="analyze-by-dimensions" />Analyse par dimensions

Utilisez les vues d’analyse que vous avez déjà configurées avec la matrice **Analyse par dimensions** pour afficher les montants de votre grand livre.   

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.  
2. Sélectionnez la vue d’analyse appropriée et choisissez l’action **Analyse par dimensions**.
3. Sur la page **Analyse par dimensions**, renseignez les champs pour définir les données affichées et leur présentation.
4. Choisissez l'action **Afficher matrice** pour ouvrir la page matricielle respective de la vue d'analyse définie.
5. Pour visualiser la spécification d'un montant affiché sur la page matricielle, sélectionnez le montant à explorer.  

- Les colonnes les plus à gauche contiennent des informations basées sur l’option sélectionnée dans le champ **Afficher lignes** de l’en-tête.  
- Les colonnes les plus à droite contiennent des informations basées sur l’option sélectionnée dans le champ **Afficher colonnes** de l’en-tête.

> [!IMPORTANT]  
> Vous ne pouvez pas sélectionner une période plus courte que celle indiquée en tant que compression date sur la fiche **Vue d'analyse**. Les commandes **Jeu suivant** et **Jeu précédent** sont inactives si vous avez sélectionné **Période** dans le champ **Afficher lignes** ou le champ **Afficher colonnes**.  

> [!NOTE]  
> Vous pouvez utiliser l'état **Axes analytiques - Détail** pour répertorier de manière détaillée les différentes utilisations des axes analytiques sur les écritures au cours d'une période. Vous pouvez utiliser le rapport **Dimensions - Total** pour afficher uniquement les montants totaux.  

> [!TIP]  
> Vous pouvez également modifier la vue en changeant la valeur des champs **Afficher lignes** et **Afficher colonnes**. Pour contrepasser un paramètre de vue, choisissez l'action **Inverser lignes et colonnes**.

## <a name="update-an-analysis-view" />Mettre à jour une vue d’analyse

Les montants affichés sur la page **Analyse par dimensions** offrent une image de l’état de la compagnie au moment de la dernière mise à jour. Pour obtenir un aperçu de l'état actuel, vous devez actualiser la vue d'analyse en exécutant l'option de mise à jour.

Suivez la procédure suivante pour mettre à jour une vue d’analyse à partir de la page **Analyse par dimensions**. Les étapes sont similaires à celles de la mise à jour des pages **Fiche vue d’analyse** et **Liste des vues d’analyse**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.
2. Sélectionnez la vue d’analyse appropriée et choisissez l’action **Analyse par dimensions**.
3. Sur la page **Analyse par dimensions**, sélectionnez le champ **Code vue d'analyse**.  
4. Sélectionnez la ligne contenant la vue d'analyse appropriée.  
5. Sur la page **Vues d’analyse**, sélectionnez la vue d’analyse, puis l’action **Mettre à jour**.  

> [!TIP]  
> Si vous activez la case à cocher **Mise à jour au report** sur la fiche vue d’analyse, la vue est automatiquement mise à jour lorsqu’une transaction associée est reportée.

> [!NOTE]  
> Pour mettre à jour tout ou partie des vues d'analyse en même temps, vous devez utiliser le traitement par lots **Mise à jour vues d'analyse**.  

## <a name="see-related-training-at-microsoft-learnlearnmodulesdimensions-financial-reports-dynamics--business-centralindex" />Voir la formation associée sur [Microsoft Learn](/learn/modules/dimensions-financial-reports-dynamics-365-business-central/index).

## <a name="see-also" />Voir aussi .

[Décisionnel pour le secteur de la finance](bi.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Utiliser des dimensions](finance-dimensions.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
