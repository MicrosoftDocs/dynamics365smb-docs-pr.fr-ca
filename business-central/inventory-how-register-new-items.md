---
title: Créer des fiches article pour des biens ou des services (contient une vidéo)
description: Vous créez des fiches article pour les services que vous vendez en heures et pour les produits physiques. Les exemples incluent les éléments d’assemblage et les produits finis que vous vendez à partir de votre inventaire.
author: SorenGP
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'item, finished good, component, raw material, assembly item, item substitution'
ms.search.form: '30, 5717, 31, 32, 346, 9091, 5718, 5716, 5720, 1384, 1383, 35, 5404, 1378, 5719'
ms.date: 09/26/2022
ms.author: edupont
---
# Enregistrer de nouveaux articles

Les articles, entre autres produits, sont la base de votre activité, les biens ou les services que vous commercialisez. Chaque article doit être enregistré en tant que fiche article.

Les fiches article contiennent les informations nécessaires à l'achat, le stockage, la vente, la livraison et la comptabilisation des articles.

La fiche article peut être de type **Inventaire**, **Service** ou **Hors inventaire** pour spécifier si l’article est une unité d'inventaire physique, une unité de temps de travail ou une unité physique qui n’est pas suivie dans l'inventaire. Pour plus d'informations sur les types, voir [À propos des types d'articles](inventory-about-item-types.md).

Un article peut être structuré comme article parent avec les éléments enfants sous-jacents dans une nomenclature. En savoir plus sur les nomenclatures d’assemblage et les nomenclatures de production dans la section [Utiliser les nomenclatures](inventory-how-work-BOMs.md).

Si vous achetez le même article chez plusieurs fournisseurs, vous pouvez lier ces fournisseurs à la fiche article. Les fournisseurs s'affichent alors sur la page **Catalogue fournisseur articles**, de sorte que vous pouvez facilement sélectionner un autre fournisseur.

Les *Articles de catalogue* sont des articles que vous offrez à vos clients, mais que vous ne souhaitez pas gérer dans votre système tant que vous ne les commercialisez pas. Les articles de catalogue ne sont pas des articles normaux de type **Hors inventaire**. En savoir plus sur [Utiliser des éléments de catalogue](inventory-how-work-nonstock-items.md).  

> [!NOTE]  
> Si des modèles article existent pour différents types d'articles, une page s'affiche automatiquement lorsque vous créez une nouvelle fiche article à partir de laquelle vous pouvez sélectionner un modèle article approprié. Si un seul modèle article existe, les nouvelles fiches article utiliseront toujours ce modèle.

La procédure suivante explique comment créer une fiche article à partir de zéro. Vous pouvez également créer de nouvelles fiches d'objets en copiant celles existantes. Pour plus d'informations, voir [Copier des articles existants pour créer de nouveaux articles](inventory-how-copy-items.md).  

<br />

> [!Video https://www.microsoft.com/videoplayer/embed/RE47eLx?rel=0]

## Pour créer une fiche article

[!INCLUDE[create_new_item](includes/create_new_item.md)]

> [!NOTE]
> Dans le champ **Mode évaluation coût**, vous configurez la façon dont le coût unitaire de l'article est calculé en estimant le flux d'articles physiques dans votre compagnie. Il existe cinq modes évaluation stock disponibles, selon le type d'article. Pour plus d'informations, [Détails de conception : modes évaluation stock](design-details-costing-methods.md).
>
> Si vous sélectionnez **Moyenne**, le coût unitaire de l'article est calculé comme le coût unitaire moyen à chaque moment après un achat. L'inventaire est évalué en supposant que tous les inventaires sont vendus simultanément. Avec ce paramètre, vous pouvez choisir le champ **Coût unitaire**, sur la page **Aperçu calc. coût moyen** de la fiche article pour afficher l'historique des transactions à partir duquel est calculé le coût moyen

Vous pouvez afficher ou modifier les prix ou escomptes spéciaux que vous accordez, ou que votre fournisseur vous accorde, pour l'article si certains critères sont réunis, par exemple le client, la quantité minimale de commande ou la date de fin. Pour ce faire, choisissez les actions **Définir des prix spéciaux** ou **Définir des escomptes spéciaux**. Chaque ligne de la page **Prix de vente**, par exemple, représente un prix spécial. Chaque colonne représente un critère qui doit s'appliquer pour accorder à un client le prix spécial que vous entrez dans le champ **Prix unitaire** de la page **Prix de vente**. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md) ou [Enregistrer des prix d'achat et des escomptes spéciaux](purchasing-how-record-purchase-price-discount-payment-agreements.md).

L'article est désormais enregistré, et la fiche article est prête à être utilisée sur les documents d'achat et de vente.

Si vous souhaitez utiliser cette fiche article comme modèle lorsque vous créez de nouvelles fiches article, enregistrez-la comme modèle. Pour plus d'informations, reportez-vous à la section suivantes.  

### Pour enregistrer la fiche article en tant que modèle

1. Sur la page **Fiche article**, sélectionnez l'action **Sauvegarder comme modèle**. La page **Modèle article** s'ouvre et affiche la fiche article comme modèle.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour réutiliser les axes analytiques dans les modèles, sélectionnez l'action **Axes analytiques**. La page **Modèles dimension** s'ouvre et affiche tous les codes dimension qui sont configurés pour l'article.
4. Modifiez ou entrez les codes dimension s'appliquant aux nouvelles fiches article créées à l'aide du modèle.
5. Lorsque vous avez terminé le nouveau modèle article, cliquez sur le bouton **OK**.

Le modèle article est ajouté à la liste des modèles article. Vous pouvez ainsi l'utiliser pour créer des fiches article.

### Articles utilisés dans les bons de production

Si vous souhaitez enregistrer des articles qui sont ensuite utilisés dans des bons de production, vous spécifiez le système réappro. comme *Bon de production* sur le raccourci **Réapprovisionnement**. Pour plus d'informations, voir [À propos des bons de production](production-about-production-orders.md).  

## Pour configurer plusieurs fournisseurs pour un article

Si vous achetez le même article chez plusieurs fournisseurs, vous devez saisir, pour chacun des fournisseurs de cet article des informations concernant, par exemple, ses prix, ses délais, ses escomptes, etc.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2. Sélectionnez l'article concerné, puis cliquez sur l'action **Modifier**.  
3. Sélectionnez l'action **Fournisseurs**.  
4. Cliquez sur le champ **N° fournisseur**, puis sélectionnez le fournisseur à paramétrer pour l'article.  
5. De manière facultative, renseignez les autres champs.  
6. Répétez les étapes 2 à 5 pour chaque fournisseur auprès de qui vous souhaitez acheter l'article.

Les fournisseurs s'affichent maintenant sur la page **Catalogue fournisseur articles** (que vous ouvrez à partir de la fiche article), de sorte que vous pouvez facilement sélectionner un autre fournisseur.

## Configuration de substitutions d'articles

Vous pouvez configurer des articles pour qu’ils aient des substituts, tels que d’autres articles pouvant être utilisés à la place de l’article d’origine.

### Pour créer une substitution d'articles

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2. Recherchez l’article concerné, puis cliquez sur le **N° article** pour ouvrir la fiche article.  
3. Choisissez l’action **Association**, puis sélectionnez **Article**, puis **Substitutions** pour ouvrir la page **Saisie de substitution d’article**.  
4. Sélectionnez le champ **N° substitut**, puis sélectionnez l’article de substitution dans la liste.
5. Renseignez ou modifiez les autres champs de la page selon vos besoins.

Lorsque la quantité demandée dépasse la quantité disponible en inventaire, un message apparaît pour vous informer que des articles de substitution sont disponibles.

> [!NOTE]  
> Sachez que les substitutions d'articles n’entraîneront pas automatiquement le remplacement d’un article par un autre, par exemple lors de la création d’un document de vente ou dans une nomenclature. Au lieu de cela, vous serez alerté du fait qu’un substitut est disponible pour vous.

## Catégories, attributs et variantes

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

En savoir plus sur les variantes dans la section [Gérer les variantes de produits](inventory-item-variants.md).  

## Suppression de fiches article

Si vous avez reporté une transaction pour un article, vous ne pouvez pas supprimer la carte, car les écritures peuvent être nécessaires pour l’évaluation de l’inventaire ou l’audit. Pour supprimer des fiches article avec des écritures, contactez le partenaire Microsoft pour le faire par code.  

## Gérer l'inventaire des entrepôts

Lorsque vous enregistrez un nouvel article, vous verrez des champs liés à la gestion de l’entrepôt, en particulier sur le raccourci **Entrepôt**. Si votre organisation n’utilise pas les fonctionnalités de gestion d’entrepôt dans [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez alors ignorer ces champs.  

Si votre organisation configure ultérieurement la gestion des entrepôts, nous vous recommandons de vous assurer que chaque article existant possède les bonnes informations dans les différents champs. De cette façon, les processus d’entrepôt peuvent s’exécuter comme prévu. Ces informations peuvent inclure des champs, tels que **Code classe entrepôt** ou **Code modèle rangement**. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

## Planific.

Lorsque votre compagnie utilise les processus de planification des approvisionnements dans [!INCLUDE [prod_short](includes/prod_short.md)], vous devez remplir les champs correspondants sur le raccourci **Planification**. Pour une introduction à la zone de planification, voir [Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md).  

Pour des exemples d’utilisation des champs du raccourci **Planification**, voir [Configurer des recommandations : configuration de planification](setup-best-practices-planning-parameters.md).  

## Voir la [formation Microsoft](/training/modules/create-items/) associée

## Voir aussi .

[Stock](inventory-manage-inventory.md)  
[Configuration d'unités de mesure](inventory-how-setup-units-of-measure.md)  
[Gérer les variantes de produits](inventory-item-variants.md)  
[Paramétrer les rapports Intrastat](finance-how-setup-report-intrastat.md#other-intrastat-configurations)  
[Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Création des séries de numéros](ui-create-number-series.md)  
[Configuration de groupes de report](finance-posting-groups.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Vente](sales-manage-sales.md)  
[À propos de la fonctionnalité Planification](production-about-planning-functionality.md)  
[Pratiques de configuration recommandées : Paramètres de planification](setup-best-practices-planning-parameters.md)  
[Configurer des recommandations : planification de l'approvisionnement](setup-best-practices-supply-planning.md)  
[Détails de conception : concepts centraux du système de planification](design-details-central-concepts-of-the-planning-system.md)  
[Détails de conception : équilibrage de la demande et de l'approvisionnement](design-details-balancing-demand-and-supply.md)  
[Détails de conception : paramètres de planification](design-details-planning-parameters.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
