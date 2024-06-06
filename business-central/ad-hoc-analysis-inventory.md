---
title: Analyse ad hoc des données d’inventaire
description: Découvrez comment utiliser le mode d’analyse des données pour analyser les données d’inventaire.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '516, 9300, 5119, 9301, 9305'
ms.date: 05/03/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="ad-hoc-analysis-of-inventory-data"></a>Analyse ad hoc des données d’inventaire

Cet article explique comment utiliser la fonction **Analyse des données** pour analyser des données d’inventaire directement à partir des pages de liste et des requêtes. Vous n’avez pas besoin d’exécuter un rapport ou de changer d'application, comme Excel. La fonction fournit un moyen interactif et polyvalent de calculer, résumer et examiner les données. Plutôt que d’exécuter des rapports à l’aide d’options et de filtres, vous pouvez ajouter plusieurs onglets qui représentent différentes tâches ou vues sur les données. Quelques exemples sont "stock expiration" ou "meilleures vente", ou toute autre vue que vous pouvez imaginer. Pour en savoir plus sur l’utilisation de la fonctionnalité **Analyse des données** , accédez à [Analyser la liste et interroger les données avec le mode d’analyse](analysis-mode.md).

Utilisez les pages de liste suivantes pour une analyse ad hoc des processus d’inventaire :

- [Écritures article](https://businesscentral.dynamics.com/?page=38)

## <a name="inventory-ad-hoc-analysis-scenarios"></a>Scénarios d’analyse ad hoc de l’inventaire

Utilisez la fonctionnalité **Analyse des données** pour une vérification rapide des faits et une analyse ad hoc :

- Si vous ne souhaitez pas générer de rapport.
- S’il n’existe pas de rapport correspondant à votre besoin spécifique.
- Si vous souhaitez effectuer une itération rapide pour avoir une bonne vue d’ensemble sur une partie de votre entreprise.

Les sections suivantes fournissent des exemples de scénarios d’inventaire dans [!INCLUDE [prod_short](includes/prod_short.md)].

| Aire | Pour... | Ouvrir cette page en mode analyse | Utiliser ces champs |
| ---- | ----- | ------------------------------- |------------------- |
| [Inventaire disponible](#example-inventory-on-hand) | Obtenez un aperçu des articles disponibles dans votre inventaire. | [Écritures article](https://businesscentral.dynamics.com/?page=38) | **N° article**, **Quantité restante** |
|[Exemple : suivre les stocks expirés ou anciens](#example-track-expiring-or-old-stock) | Obtenez un aperçu des articles de votre inventaire qui sont en stock depuis longtemps et qui ne se vendent pas bien. | [Écritures article](https://businesscentral.dynamics.com/?page=38) | **Année de la date de report**, **Mois de la date de report**, **N° d’article**, **Date de report**, **Type d’écriture**, **Quantité** et **Quantité restante**. |
| [Articles retournés par motif de retour](#example-returned-items-by-return-reason) | Obtenez un aperçu des marchandises que les clients retournent, classées par motif de retour. Utilisez-le pour l’analyse pour le contrôle qualité. | [Écritures article](https://businesscentral.dynamics.com/?page=38) | **Code de motif de retour**, **Mois de la date de report**, **Quantité** , **Montant du coût**, **Date de report**, **Type de document**, **N° d'article** et  **N° de document**. |
| Débit d’inventaire | Obtenez un aperçu des achats et des ventes dans votre inventaire par mois ou trimestre. | [Écritures article](https://businesscentral.dynamics.com/?page=38) | **Année de la date de report**, **Mois de la date de report**, **N° d’article**, **Quantité**, **Montant des ventes**, **Montant du coût (réel)** et **Mois de la date de report** |
| [Mouvements d'inventaire] | Obtenez un aperçu de la façon dont les marchandises de votre inventaire se déplacent entre les emplacements. | [Écritures article](https://businesscentral.dynamics.com/?page=38) | **Code d’emplacement**, **Quantité**, **Date de report**, **N° d’article** |

## <a name="example-inventory-on-hand"></a>Exemple : inventaire disponible

Pour analyser des articles de votre inventaire qui sont en stock, procédez comme suit :

1. Ouvrez la liste [Écritures article](https://businesscentral.dynamics.com/?page=38) et choisissez :::image type="content" source="media/analysis-mode-icon.png" alt-text="Entrer en mode d’analyse":::. pour activer le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Faites glisser le champ **N° article** champ vers le **Groupes lignes** zone. Faites glisser les champs dans cet ordre.
1. Faites glisser le champ **Quantité restante** champ vers le **Valeurs** zone.
1. Définir un **Inégal** filtrer pour **0** sur **Quantité restante**. Si vous n’autorisez pas les niveaux de stock négatifs, définissez un **Plus grand que** filtrer pour **0**.
1. Vous pouvez éventuellement ajouter d’autres champs à l’analyse et peut-être pivoter sur l’emplacement ou sur d’autres champs.
1. Renommez votre onglet d’analyse en **Inventaire disponible** ou quelque chose qui décrit cette analyse.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source="media/data-analysis-inventory-on-hand.png" alt-text="Exemple de comment effectuer une analyse des données disponibles d’inventaire." lightbox="media/data-analysis-inventory-on-hand.png":::

## <a name="example-track-expiring-or-old-stock"></a>Exemple : suivre les stocks expirés ou anciens

Pour analyse des articles de votre inventaire qui sont en stock depuis longtemps et qui ne se vendent pas bien, procédez comme suit :

1. Ouvrez la liste [Écritures article](https://businesscentral.dynamics.com/?page=38) et choisissez :::image type="content" source="media/analysis-mode-icon.png" alt-text="Entrer en mode d’analyse":::. pour activer le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Faites glisser les champs **Année de la date de report**, **Mois de la date de report** et **N° d’article** vers la zone **Groupes de lignes**. Faites glisser les champs dans cet ordre.
1. Dans la zone **Colonnes**, choisissez les champs **Date de report**, **Type d’écriture**, **Quantité** et **Quantité restante**.
1. Définissez un filtre **Inférieur à** pour la **Date de report** pour définir ce que vous entendez par « ancien ».
1. Renommez votre onglet d’analyse en **Stock ancien** ou quelque chose qui décrit cette analyse.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source="media/data-analysis-inventory-dead-stock.png" alt-text="Exemple de procédure pour effectuer une analyse des données de stock mort sur la page Écritures article" lightbox="media/data-analysis-inventory-dead-stock.png":::

## <a name="example-returned-items-by-return-reason"></a>Exemple : articles retournés par motif de retour

Pour analyser les articles retournés triés par motif de retour, procédez comme suit :

1. Ouvrez la liste [Écritures article](https://businesscentral.dynamics.com/?page=38).
1. Pour personnalisant la page, ajouter champ **code motif retour**. Dans le menu **Paramètres** , choisissez **Personnaliser**.
1. Quittez le mode personnalisation.
1. Choisir :::image type="content" source="media/analysis-mode-icon.png" alt-text="Entrer en mode d’analyse."::: pour activer le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Faites glisser les champs **Code de motif de retour** et **Mois de la date de report** vers la zone **Groupes de lignes**. Faites glisser les champs dans cet ordre.
1. Faites glisser les champs **Quantité** et **Montant du coût** vers la zone **Valeurs**.
1. Ajoutez tous les autres champs de votre choix dans l’analyse et activez-les dans la zone **Colonnes**. Par exemple, vous pouvez ajouter les champs **Date de report**, **Type de document**, **N° d’article** et **N° du document**.
1. Renommez votre onglet d’analyse en **Articles retournés par motif de retour** ou quelque chose qui décrit cette analyse.  

## <a name="example-inventory-throughput"></a>Exemple : Débit d’inventaire

1. Ouvrez la liste [Écritures article](https://businesscentral.dynamics.com/?page=38) et choisissez :::image type="content" source="media/analysis-mode-icon.png" alt-text="Entrer en mode d’analyse":::. pour activer le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Allumer **Pivot mode** (situé directement au-dessus du **Recherche** champ droite).
1. Faites glisser les champs **Année de la date de report**, **Mois de la date de report** et **N° d’article** vers la zone **Groupes de lignes**.
1. Faites glisser les champs **Quantité**, **Montant vente** et **Montant du coût (réel)** vers la zone **Valeurs**.
1. Faites glisser le champ **Mois de la date de report** vers la zone **Groupes de colonnes**.
1. Renommez votre onglet d’analyse en **Débit d’inventaire par mois** ou quelque chose qui décrit cette analyse.  

## <a name="inventory-movements"></a>Mouvements d’inventaire

Pour suivre les mouvements d'inventaire entre les emplacements, procédez comme suit :

1. Ouvrez la liste [Écritures article](https://businesscentral.dynamics.com/?page=38) et choisissez :::image type="content" source="media/analysis-mode-icon.png" alt-text="Entrer en mode d’analyse":::. pour activer le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Faites glisser le champ **Code d’emplacement** vers la zone **Groupes de lignes**.
1. Faites glisser le champ **Quantité** vers le **Valeurs** zone.
1. Ajoutez tous les autres champs de votre choix dans l’analyse et activez-les dans la zone **Colonnes**. Par exemple, vous pouvez ajouter le champ **Numéro d’article** .
1. Renommez votre onglet d’analyse en **Mouvements d'inventaire** ou quelque chose qui décrit cette analyse.  

   > [!TIP]
   > Si vous ajoutez le champ Date de report, vous pouvez également suivre les mouvements au fil du temps.

## <a name="data-foundation-for-ad-hoc-analysis-on-inventory"></a>Base de données pour l’analyse ad hoc de l’inventaire

Lorsque vous reportez un document de vente, [!INCLUDE [prod_short](includes/prod_short.md)] met à jour le compte du client, le grand livre et les écritures article.

- Pour chaque ligne document de vente, une écriture article est créée dans la table **Écriture article** (si les lignes vente contiennent des numéros d’articles). En outre, les documents de vente sont toujours enregistrés dans les tables **En-tête livraison vente** et **En-tête facture vente**. Pour en savoir plus sur le report des ventes, voir [Report des ventes](ui-post-sales.md).

Lorsque vous reportez un document achat, [!INCLUDE [prod_short](includes/prod_short.md)] met à jour le compte du fournisseur, le grand livre (GL), les écritures article et les écritures ressource.

- Pour chaque ligne achat, le cas échéant, des écritures sont créées dans la table **Écriture article** (si la ligne achat est de type Article). En outre, les documents achat sont toujours enregistrés dans les tables **En-tête réception achat** et **En-tête facture achat**. Pour en savoir plus, voir [Report des achats](purchasing-how-record-purchases.md#posting-purchases).

## <a name="see-also"></a>Voir aussi .

[Analyse des données de liste et de requête avec le mode d’analyse](analysis-mode.md)  
[Vue d’ensemble de l’analyse de l’inventaire](inventory-analytics-overview.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)  
[Vue d’ensemble de l’inventaire](inventory-manage-inventory.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
