---
title: Définitions de ligne dans les rapports financiers
description: Décrit le fonctionnement des définitions de ligne dans les rapports financiers.
author: kennieNP
ms.author: kepontop
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: 'bi, power BI, analysis, KPI, account schedule, financial report'
ms.search.form: '103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766'
ms.service: dynamics-365-business-central
---

# Définitions de ligne dans les rapports financiers

Les définitions de ligne dans les rapports financiers fournissent un emplacement pour les calculs qui ne peuvent pas être effectués directement dans le plan comptable. Par exemple, vous pouvez créer des sous-totaux pour des groupes de comptes, puis inclure ce total dans d'autres totaux. Vous pouvez également calculer des étapes intermédiaires qui ne sont pas affichées dans le rapport final.

## Créer ou modifier une définition de ligne

Pour créer ou modifier une définition de ligne, procédez comme suit :

1. Sur la page **Rapports financiers**, sélectionnez le rapport financier souhaité, puis sélectionnez l’action **Modifier la définition de ligne**.
1. Choisissez les actions **Insérer des comptes GL**, **Insérer des comptes CF**, et **Insérer des types de coût** pour créer une ligne pour chaque élément financier que vous souhaitez analyser. Par exemple, vous pouvez avoir une ligne pour les actifs à court terme et une autre ligne pour les immobilisations. Pour avoir de l’inspiration, explorez les rapports financiers de la compagnie de démonstration CRONUS.

    > [!NOTE]
    > Le champ **N° ligne** affiche les 10 premiers caractères d’un identificateur, par exemple, un numéro de compte. Si vous ajoutez des éléments avec des identificateurs qui commencent par les mêmes 10 caractères, vous aurez des doublons dans le champ **N° ligne** . Si nécessaire, vous pouvez modifier manuellement les identificateurs après avoir inséré les éléments. Les identificateurs complets sont affichés dans le champ **Totalisation**.

> [!NOTE]
> Les colonnes que vous définissez sur chaque ligne de la définition de ligne représentent les colonnes 3 et supérieures de la page **Rapport financier**. Les deux premières colonnes, **N° ligne** et **Description**, sont fixes.  

## Définitions de ligne intégrées

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des exemples de définitions de lignes qui peuvent vous aider à démarrer rapidement la configuration de rapports financiers adaptés à vos besoins.

<!-- update this when we release the new templates in 24.1
| Row definition code | Description | How to use this row definition | 
| ------------------- | ----------- | ------------------------------ | 
| TBA 1 | TBA 1 | TBA 1 |
| TBA 2 | TBA 2 | TBA 2 |
| TBA 3 | TBA 3 | TBA 3 |
| TBA 4 | TBA 4 | TBA 4 | 
-->

> [!NOTE]
> Les exemples de rapports financiers présentés dans [!INCLUDE[prod_short](includes/prod_short.md)] ne sont pas prêt à être utilisés directement. En fonction de la façon dont vous configurez vos comptes du grand livre, vos dimensions, vos catégories de comptes du grand livre et vos budgets, ajustez les exemples de définitions de lignes et de colonnes ainsi que les rapports financiers qui les utilisent pour correspondre à votre configuration.

## Utiliser les catégories de compte du grand livre pour modifier la présentation de vos états financiers

Vous pouvez utiliser les catégories de compte du grand livre pour modifier la présentation de vos relevés financiers. Par exemple, après avoir configuré vos catégories de compte sur la page **Catégories de compte du grand livre**, vous pouvez choisir l’action **Générer les rapports financiers**, et mettre à jour les rapports financiers sous-jacents pour les rapports financiers de base. La prochaine fois que vous exécuterez l’un de ces rapports, par exemple le rapport **Relevé de solde**, de nouveaux totaux et des sous-entrées seront ajoutés.

Un autre avantage de l’utilisation des catégories de comptes du grand livre par rapport aux comptes du grand livre bruts dans vos définitions de lignes est qu’une modification dans la structure de votre plan comptable n’affecte pas vos rapports financiers.

> [!NOTE]
> Les catégories de compte de niveau supérieur, telles que le nœud **Passif**, sont fixes et vous ne pouvez pas ajouter les vôtres. Cependant, vous pouvez supprimer et ajouter des catégories de compte à des niveaux inférieurs et définir la façon dont le rapport financier associé apparaît dans les rapports.
>
> Vous devez créer et structurer vos propres catégories de compte GL de niveau inférieur à partir de zéro, dans une hiérarchie si nécessaire, plutôt que d’essayer de réorganiser les catégories existantes. Par exemple, vous pouvez restructurer le nœud **Passif** pour contenir un nouveau nœud **Équité** suivi des nœuds **Passif à court terme** et **Passif à long terme**. Pour en savoir plus, voir [Mappage des comptes GL aux catégories de comptes](finance-general-ledger.md#account-categories).

## Meilleures pratiques pour utiliser les définitions de lignes

Les définitions de lignes ne sont pas versionnées. Lorsque vous modifiez une définition de ligne, l’ancienne version est remplacée lorsque votre modification est enregistrée dans la base de données. La liste suivante contient quelques bonnes pratiques pour utiliser les définitions de lignes :

- Si vous ajoutez des définitions de ligne, choisissez un bon code et remplissez le champ de description avec un texte significatif tout en sachant à quoi vous utilisez la définition de ligne. Ces informations aident vos collègues (et votre futur moi) à travailler avec les rapports financiers et peut-être à modifier la définition de ligne.
- Avant de modifier une définition de ligne, envisagez d’en faire une copie comme sauvegarde, au cas où votre modification ne fonctionnerait pas comme prévu. Vous pouvez soit simplement copier la définition (lui donner un bon nom), soit l’exporter. Pour en savoir plus, voir [importer ou exporter des définitions de lignes](#import-or-export-financial-reporting-row-definitions).
- Si vous avez besoin d’une nouvelle copie d’une définition fournie par [!INCLUDE[prod_short](includes/prod_short.md)], un moyen simple d’en obtenir une consiste à créer une nouvelle compagnie contenant uniquement des données de configuration. Ensuite, exportez la définition et importez-la dans la compagnie où la définition doit être actualisée.

## Importer ou exporter des définitions de ligne dans des rapports financiers

Vous pouvez importer et exporter des définition de lignes comme des packages de configuration RapidStart. Par exemple, les packages de configuration s’avèrent utiles pour le partage d’informations avec d’autres compagnies. Le package est créé dans un fichier .rapidstart, qui compresse le contenu.

> [!NOTE]
> Lorsque vous importez des définitions de ligne dans des rapports financiers, les enregistrements existants portant les mêmes noms que ceux que vous importez sont remplacés par les nouvelles définitions. Le package de configuration d’une définition de rapport n’écrasera aucune définition de ligne ou de colonne existante utilisée dans la définition de rapport.

Pour importer ou exporter des définitions de lignes de rapports financiers, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Définitions de ligne**, puis sélectionnez le lien associé.
1. Choisissez la définition de ligne, puis choisissez l’action **Importer définition de ligne** ou **Exporter définition de ligne**, selon ce que vous voulez faire.

## Voir aussi .

[Définitions de colonne dans les rapports financiers](bi-column-definitions.md)  
[Préparer des rapports financiers](bi-how-work-account-schedule.md)  
[Business Intelligence financière](bi.md)  
[Finances](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
