---
title: Analyses ponctuelles en achats
description: Découvrez comment utiliser le mode d’analyse des données dans les achats pour analyser les données.
author: kennienp
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'bi, power BI, analysis, KPI'
ms.search.form: '9306, 9307, 518, 29'
ms.date: 04/29/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Analyses ponctuelles en achats

Cet article explique à analyser les données d'achat des pages de liste et des requêtes à l’aide de fonctionnalité **Analyse des données**. La fonctionnalité vous permet d'analyser les données directement à partir de la page, sans avoir à exécuter un rapport ou à ouvrir une autre application comme Excel. L'analyse de données fournit un moyen interactif et polyvalent de calculer, résumer et examiner les données. Plutôt que d’exécuter des rapports à l’aide d’options et de filtres, vous pouvez ajouter plusieurs onglets qui représentent différentes tâches ou vues sur les données. Quelques exemples sont "Mes fournisseurs" ou "Statistiques achat", ou toute autre vue que vous pouvez imaginer. Pour en savoir plus sur l’utilisation de la fonctionnalité **Analyse des données** , accédez à [Analyser la liste et interroger les données avec le mode d’analyse](analysis-mode.md).

Utilisez les pages de liste suivantes pour une analyse ad hoc des processus d'achat :

- [Commandes achat](https://businesscentral.dynamics.com/?page=9307)
- [Lignes achat](https://businesscentral.dynamics.com/?page=518)
- [Factures achat reportées](https://businesscentral.dynamics.com/?page=146)
- [Écritures comptables fournisseur](https://businesscentral.dynamics.com/?page=29)
- [Écritures journal général](https://businesscentral.dynamics.com/?page=20)

## Scénarios d’analyse ad hoc pour les achats

Utilisez la fonctionnalité **Analyse des données** pour une vérification rapide des faits et une analyse ad hoc :

- Si vous ne souhaitez pas générer de rapport
- S’il n’existe pas de rapport correspondant à votre besoin spécifique
- Si vous souhaitez effectuer une itération rapide pour avoir une bonne vue d’ensemble sur une partie de votre entreprise.

Les sections suivantes fournissent des exemples de scénarios d'achat dans [!INCLUDE [prod_short](includes/prod_short.md)].

| Aire | Pour... | Ouvrir cette page en mode analyse | Utiliser ces champs |
| ---- | ----- | ------------------------------- |------------------- |
| [Vue d’ensemble de GRNI](#example-goods-received-not-invoiced-grni-overview) | Obtenez un aperçu des marchandises reçues, non facturées (GRNI) pour tous les fournisseurs. | **Tapez**, **Montant reçu non fact. $** (filtrer sur ces champs), **N° du fournisseur**, **N° du document**, **N°** et **Montant reçu non fact. $** <br> **REMARQUE :** Pour ajouter les champs vous devez personnaliser la page. Pour plus d’informations, consultez [Personnalisez votre espace de travail](ui-personalization-user.md). | 
| [Finances (comptabilité fournisseur)](#example-finance-accounts-payable) | Voyez ce que vous devez à vos fournisseurs décomposé en intervalles de temps pendant lesquels les montants sont dus. | [Écritures comptables fournisseur](https://businesscentral.dynamics.com/?page=29) | **Nom du fournisseur**, **Type de document**, **N° du document**, **Année de la date d’échéance**, **Mois de la date d’échéance** et **Montant restant**. |

## Exemple : aperçu des marchandises reçues, non facturées (GRNI)

Pour créer un aperçu des marchandises reçues, non facturées (GRNI) pour tous les fournisseurs, procédez comme suit :
 
1. Ouvrez la liste [Lignes achat](https://businesscentral.dynamics.com/?page=518) page.
1. Personnalisez la page pour ajouter le champ **Montant reçu non facturé** . Pour personnaliser la page, choisissez **Paramètres**, puis **Personnaliser**.
1. Activez le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Dans le menu **Filtres supplémentaires** (à droite de la page, juste en dessous du menu **Colonnes**) définir les filtres suivants :
    - **Type = article**
    - **Montant reçu non fact. $ > 0**. 
1. Faites glisser le **N° du fournisseur**, **N° du document** et **N°.** Champs vers le **Groupes de lignes** zone. Faites glisser les champs dans cet ordre.
1. Ajoutez le champ **Montant reçu non fact. $** pour l’inclure dans l’aperçu.
1. Pour effectuer l’analyse pour une année ou un trimestre donné, appliquez un filtre dans le menu **Filtres supplémentaires**. Le menu se trouve à droite de la page, juste en dessous du **Colonnes** menu.
1. Renommez votre onglet d’analyse en **marchandises ont été réceptionnées mais non encore facturées (GRNI)** ou quelque chose qui décrit cette analyse pour vous.

## Exemple : Finance (Comptabilités fournisseur)

Pour voir ce que vous devez fournisseur, décomposé en intervalles de temps pendant lesquels les montants sont dus, comme suit :

1. Ouvrez la page de liste [Écritures fournisseur](https://businesscentral.dynamics.com/?page=29) et activez le mode d’analyse.
1. Allez au **Colonnes** menu et supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ).
1. Allumer **Pivot** mode (situé directement au-dessus du **Recherche** champ).
1. Faites glisser le **Nom du fournisseur**, **Type de document**, et **Numéro de document** champs vers le **Groupes de lignes** zone, puis faites glisser le **Montant restant** champ vers le **Valeurs** zone.
1. Faites glisser les champs **Année de la date d'échéance** et **Mois de la date d'échéance** vers la zone **Étiquettes de colonnes**. Faites glisser les champs dans cet ordre.
1. Pour effectuer l’analyse pour une année ou un trimestre donné, appliquez un filtre dans le menu **Filtres supplémentaires** (à droite de la page, juste en dessous du menu **Colonnes**.)
1. Renommez votre onglet d’analyse en **Comptes fournisseurs classés chronologiquement par mois** ou quelque chose qui décrit cette analyse pour vous.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source="media/data-analysis-vendor-ledger-entries.png" alt-text="Exemple de procédure pour effectuer une analyse des données Écritures client" lightbox="media/data-analysis-vendor-ledger-entries.png":::

## Base de données pour une analyse ad hoc des achats

Lorsque vous reportez un document achat, [!INCLUDE [prod_short](includes/prod_short.md)] met à jour le compte du fournisseur, le grand livre (GL), les écritures article et les écritures ressource :

- Pour chaque document achat, une écriture achat est créée dans la table **Écriture**. Une écriture est également créée dans le compte fournisseur de la table **Écriture fournisseur** et une autre dans le compte fournisseur approprié. De plus, le report de l’achat peut entraîner la création d’une écriture TVA et d’une écriture GL pour le montant de l'escompte.
- Pour chaque ligne achat, les écritures suivantes sont créées :
  - La table **Écriture article** si la ligne achat est de type Article.
  - La table **Écriture GL** si la ligne achat est de type Compte GL.
  - La table **Écriture ressource** si la ligne achat est de type Ressource.
- En outre, les documents achat sont toujours enregistrés dans les tables **En-tête réception achat** et **En-tête facture achat**.

Pour en savoir plus, voir [Report des achats](purchasing-how-record-purchases.md#posting-purchases).

## Voir aussi .

[Report des achats](purchasing-how-record-purchases.md#posting-purchases)  
[Analyse des données de liste et de requête avec le mode d’analyse](analysis-mode.md)  
[Vue d’ensemble des achats](purchasing-manage-purchasing.md)  
[Vue d’ensemble Analyses, business intelligence et rapport](reports-bi-reporting.md)  
[Vue d’ensemble des achats](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

## [!INCLUDE[prod_short](includes/free_trial_md.md)]  

[!INCLUDE[footer-include](includes/footer-banner.md)]