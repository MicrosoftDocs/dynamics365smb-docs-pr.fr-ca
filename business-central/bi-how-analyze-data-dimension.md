---
title: Analyser des données par dimensions
description: Cet article décrit comment analyser les données d’entreprise par dimensions pour mieux comprendre votre activité.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '545, 555, 556, 557, 558, 9372, 9370, 9371'
ms.date: 04/19/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Analyser des données par dimensions

En analyse financière, une dimension correspond à des données que vous ajoutez à une écriture comme une sorte de marqueur pour grouper les écritures similaires. Par exemple, les dimensions regroupent souvent les entrées pour les clients, les régions, les produits et les représentants. Les groupes vous permettent de récupérer facilement des données les concernant pour les analyser. Vous pouvez utiliser les dimensions sur des écritures de journaux, de documents et de budgets.

Chaque dimension décrit l’objet de l’analyse. Une analyse à deux axes, par exemple, est une analyse des ventes par zone. En utilisant plus de deux dimensions lors de la création d’une entrée, vous pouvez effectuer une analyse plus complexe. Un exemple d’analyse complexe consiste à explorer les ventes par promotion de vente, par groupe de clients et par zone. Cela vous permet d’obtenir un meilleur aperçu de votre activité commerciale, comme la mesure du bon fonctionnement de votre société, les domaines dans lesquels elle prospère ou non, et ceux dans lesquels il est nécessaire d’affecter davantage de ressources. Ces informations vous aident à prendre des décisions commerciales plus éclairées. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

> [!TIP]
> Pour analyser rapidement les données transactionnelles par axe, vous pouvez filtrer les totaux du plan comptable (COA) et les écritures de toutes les pages **Écritures** par dimensions. Recherchez l'action **Définir le filtre dimension**.

> [!NOTE]
> Si vous découvrez qu’une valeur de dimension incorrecte a été utilisée sur les écritures du grand livre reportées, vous pouvez la corriger et mettre à jour vos vues d’analyse. Pour en savoir plus, consultez [Dépannage et correction des dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting).

## Configurer une vue d’analyse

Les analyses par dimensions utilisent une combinaison sélectionnée de dimensions. Vous stockez, récupérez et mettez à jour cet ensemble de dimensions en créant une fiche **Vue d’analyse**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.  
2. Sur la page **Liste des vues d'analyse**, cliquez sur l'action **Nouveau**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Pour ajouter des codes dimension aux quatre codes du raccourci **Dimensions**, cliquez sur l’action **Filtre**, renseignez les champs, puis cliquez sur **OK**.  
5. Pour mettre à jour la vue, choisissez l'action **Mettre à jour**.

## Analyse par dimensions

Utilisez les vues d’analyse que vous avez déjà configurées avec la matrice **Analyse par dimensions** pour afficher les montants de votre grand livre.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.  
2. Sélectionnez la vue d’analyse appropriée et choisissez l’action **Analyse par dimensions**.
3. Sur la page **Analyse par dimensions**, renseignez les champs pour définir les données affichées et leur présentation.
4. Choisissez l’action **Afficher matrice** pour ouvrir la page matricielle de la vue d’analyse.
5. Pour accéder au détail d’un montant dans la page matrice, choisissez le montant.  

- Les colonnes à gauche contiennent des informations basées sur l’option sélectionnée dans le champ **Afficher lignes** de l’en-tête.  
- Les colonnes à droite contiennent des informations basées sur l’option sélectionnée dans le champ **Afficher colonnes** de l’en-tête.

> [!IMPORTANT]  
> Vous ne pouvez pas sélectionner une période plus courte que celle indiquée en tant que compression date sur la fiche **Vue d’analyse**. Les actions **Jeu suivant** et **Jeu précédent** ne sont pas disponibles si vous avez sélectionné **Période** dans le champ **Afficher lignes** ou les champs **Afficher colonnes**.  

> [!NOTE]  
> Vous pouvez utiliser l'état **Axes analytiques - Détail** pour répertorier de manière détaillée les différentes utilisations des axes analytiques sur les écritures au cours d'une période. Vous pouvez utiliser le rapport **Dimensions - Total** pour afficher uniquement les montants totaux.  

> [!TIP]  
> Vous pouvez également modifier la vue en changeant la valeur des champs **Afficher lignes** et **Afficher colonnes**. Pour contrepasser un paramètre de vue, choisissez l'action **Inverser lignes et colonnes**.

## Mettre à jour une vue d’analyse

Les montants sur la page **Analyse par dimensions** offrent une image de l’état de la compagnie au moment de la dernière mise à jour. Pour obtenir l’état actuel, exécutez l’action de mise à jour pour mettre à jour la vue d’analyse.

Suivez la procédure suivante pour mettre à jour une vue d’analyse à partir de la page **Analyse par dimensions**. Les étapes sont similaires à celles de la mise à jour des pages **Fiche vue d’analyse** et **Liste des vues d’analyse**.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Vues d’analyse**, puis sélectionnez le lien associé.
2. Sélectionnez la vue d’analyse appropriée et choisissez l’action **Analyse par dimensions**.
3. Sur la page **Analyse par dimensions**, sélectionnez le champ **Code vue d'analyse**.  
4. Sélectionnez la ligne contenant la vue d'analyse appropriée.  
5. Sur la page **Vues d’analyse**, sélectionnez la vue d’analyse, puis l’action **Mettre à jour**.  

> [!TIP]  
> Si vous activez la case à cocher **Mise à jour lors du report** sur une fiche vue d’analyse, la vue est automatiquement mise à jour lorsqu’une transaction associée est reportée.

> [!NOTE]  
> Pour mettre à jour tout ou partie des vues d’analyse en même temps, utilisez le traitement en lot **Mise à jour vues d’analyse**.  

## Voir aussi .

[Business Intelligence financière](bi.md)  
[Finances](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Utiliser des dimensions](finance-dimensions.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
