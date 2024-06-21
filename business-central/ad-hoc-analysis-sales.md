---
title: Analyse ad hoc des données de ventes
description: Découvrez comment utiliser le mode d’analyse des données pour analyser les données ventes.
author: brentholtorf
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '516, 9300, 5119, 9301, 9305'
ms.date: 04/28/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="ad-hoc-analysis-of-sales-data"></a>Analyse ad hoc des données de ventes

Cet article vous apprenez à utiliser fonction **analyse les données** pour analyser des pages de vente directement de liste de pages et requêtes. Vous n’avez pas besoin d’exécuter un rapport ou de changer d'application, comme Excel. La fonction fournit un moyen interactif et polyvalent de calculer, résumer et examiner les données. Plutôt que d’exécuter des rapports à l’aide d’options et de filtres, vous pouvez ajouter plusieurs onglets qui représentent différentes tâches ou vues sur les données. Quelques exemples sont "Mes clients" ou "Statistiques vente", ou toute autre vue que vous pouvez imaginer. Pour en savoir plus sur l’utilisation de la fonctionnalité **Analyse des données** , accédez à [Analyser la liste et interroger les données avec le mode d’analyse](analysis-mode.md).

Utilisez les pages de liste suivantes pour une analyse ad hoc des processus de vente :

- [Commandes vente](https://businesscentral.dynamics.com/?page=9305)
- Écritures comptables
- [Écritures comptables client](https://businesscentral.dynamics.com/?page=25)
- Écritures article
- Factures vente enregistrées
- Retours vente

## <a name="sales-ad-hoc-analysis-scenarios"></a>Scénarios d’analyse ad hoc des ventes

Utilisez la fonctionnalité **Analyse des données** pour une vérification rapide des faits et une analyse ad hoc :

- Si vous ne souhaitez pas générer de rapport.
- S’il n’existe pas de rapport correspondant à votre besoin spécifique.
- Si vous souhaitez effectuer une itération rapide pour avoir une bonne vue d’ensemble sur une partie de votre entreprise.

Les sections suivantes fournissent des exemples de scénarios de vente dans [!INCLUDE [prod_short](includes/prod_short.md)].

| Aire | Pour... | Ouvrir cette page en mode analyse | Utiliser ces champs |
| ---- | ----- | ------------------------------- |------------------- |
| [Ventes (volume de ventes prévu)](#example-sales-expected-sales-volume) | Analysez votre volume de ventes attendu. | [Commandes vente](https://businesscentral.dynamics.com/?page=9305) | **Nom du client débiteur**, **Numéro du client débiteur**, **N°** , **Montant**, **Année du document**, et **Document Date Mois**. |
| [Ventes (ventes clients en volume)](#example-sales-customer-sales-by-volume) | Bref aperçu des clients qui achètent le plus et de ceux qui doivent le plus d'argent | [Écritures comptables client](https://businesscentral.dynamics.com/?page=25) | **Nom du client**, **N° de document**, **Montant**, et **Montant restant**. |
| [Finance (Comptabilités client)](#example-finance-accounts-receivables) | Voyez par exemple ce que vos clients vous doivent, décomposé en intervalles de temps pendant lesquels les montants sont dus. | [Écritures comptables client](https://businesscentral.dynamics.com/?page=25) | **Nom du client**, **Date d’échéance** et **Montant restant**. |

## <a name="example-sales-expected-sales-volume"></a>Exemples : Ventes (volume de ventes prévu)

Pour analyser votre volume de ventes prévu et les montants des ventes pour les commandes non expédiées pour chaque client par année ou par mois, procédez comme suit :

1. Ouvrez la liste des [documents de vente](https://businesscentral.dynamics.com/?page=9305) et activez le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Allumer **Pivot** mode (situé directement au-dessus du **Recherche** champ).
1. Faites glisser les champs **Nom du client débiteur**, **Numéro de client débiteur**, et **N°** Champs vers le **Groupes de lignes** zone. Faites glisser les champs dans cet ordre.
1. Faites glisser le champ **Montant** champ vers le **Valeurs** zone.
1. Faites glisser le **Année du document** et **Document Date Mois** champs vers le **Étiquettes de colonnes** zone. Faites glisser les champs dans cet ordre.
1. Pour effectuer l’analyse pour une année ou un trimestre donné, appliquez un filtre dans le menu **Filtres supplémentaires**. Le menu se trouve à droite de la page, juste en dessous du **Colonnes** menu.
1. Renommez votre onglet d’analyse en **Volume vente prévu** ou quelque chose qui décrit cette analyse pour vous.

## <a name="example-sales-customer-sales-by-volume"></a>Exemple : Ventes (ventes clients en volume)

Bref aperçu des clients qui achètent le plus et de ceux qui doivent le plus d'argent, comme suit :

1. Ouvrez la liste [Écritures client](https://businesscentral.dynamics.com/?page=25) et activez le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Faites glisser le **Nom du client** champ vers le **Groupes de lignes** zone, et le **Numéro de document** champ en dessous.
1. Choisir la **Montant** et **Montant restant** des champs.
1. Pour effectuer l’analyse pour une année ou un trimestre donné, appliquez un filtre dans le menu **Filtres supplémentaires**. Le menu se trouve à droite de la page, juste en dessous du **Colonnes** menu.
1. Renommez votre onglet d’analyse en **Clients par Volume vente** ou quelque chose qui décrit cette analyse pour vous.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source="media/data-analysis-customer-ledger-entries.png" alt-text="Exemple de procédure pour effectuer une analyse des données Écritures client" lightbox="media/data-analysis-customer-ledger-entries.png":::

## <a name="example-finance-accounts-receivables"></a>Exemple : Finance (Comptabilités client)

Pour voir ce que vos clients vous doivent, décomposé en intervalles de temps pendant lesquels les montants sont dus, comme suit :

1. Ouvrez la liste [Écritures client](https://businesscentral.dynamics.com/?page=25) et activez le mode d’analyse.
1. À la **Colonnes** menu, supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Allumer **Pivot** mode (situé directement au-dessus du **Recherche** champ).
1. Faites glisser le **Nom du client** champ vers le **Groupes de lignes** zone et faites glisser le champ **Montant restant** au **Valeurs** zone.
1. Faites glisser le champ **Mois de la date d’échéance** vers la zone **Étiquettes de colonnes**.
1. Pour effectuer l’analyse pour une année ou un trimestre donné, appliquez un filtre dans le menu **Filtres supplémentaires**. Le menu se trouve à droite de la page, juste en dessous du **Colonnes** menu.
1. Renommez votre onglet d’analyse en **Comptes classés chronologiquement par mois** ou quelque chose qui décrit cette analyse pour vous.

## <a name="data-foundation-for-ad-hoc-analysis-on-sales"></a>Base de données pour une analyse ad hoc des ventes

Après entré les informations sur un document de vente et ajouté toutes lignes document de vente, vous pouvez reporter la commande. Le report crée une livraison et une facture. [!INCLUDE [prod_short](includes/prod_short.md)] met à jour le compte du client, le grand livrer et les écritures article :

- Pour chaque document de vente, une écriture vente est créée sur la table **Écriture GL**. Une écriture est également créée dans le compte client de la table **Écriture comptable client** et une écriture comptable est créée dans le compte client approprié. De plus, le report de la commande peut avoir pour résultat la création d’une écriture TVA et d’une écriture pour le montant de l’escompte.
- Pour chaque ligne document de vente, une écriture article est créée dans la table **Écriture article** (si les lignes vente contiennent des numéros d'article) ou une écriture GL est créée dans la table **Écriture GL** (si les lignes vente contiennent un compte GL). En outre, les documents de vente sont toujours enregistrés dans les tables **En-tête livraison vente** et **En-tête facture vente**.

Pour en savoir plus sur le report des ventes, voir [Report des ventes](ui-post-sales.md).

## <a name="see-also"></a>Voir aussi .

[Report des ventes](ui-post-sales.md)  
[Analyse des données de liste et de requête avec le mode d’analyse](analysis-mode.md)  
[Présentation des analyses ventes](sales-analytics-overview.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)  
[Vue d’ensemble des ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]
