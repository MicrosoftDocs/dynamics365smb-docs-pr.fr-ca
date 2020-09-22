---
title: Créer des fiches article pour des biens ou des services| Microsoft Docs
description: Vous créez des fiches article pour les services que vous vendez en heures et pour les marchandises physiques, comme les éléments d'assemblage, les produits finis, les composantes ou les matières premières que vous vendez depuis votre inventaire.
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: item, finished good, component, raw material, assembly item
ms.date: 07/06/2020
ms.author: edupont
ms.openlocfilehash: 296e150eec01e3aee4ec8ccc32b4bf5299b86d3e
ms.sourcegitcommit: a80afd4e5075018716efad76d82a54e158f1392d
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/09/2020
ms.locfileid: "3782078"
---
# <a name="register-new-items"></a>Enregistrer de nouveaux articles

Les articles, entre autres produits, sont la base de votre activité, les biens ou les services que vous commercialisez. Chaque article doit être enregistré en tant que fiche article.

Les fiches article contiennent les informations nécessaires à l'achat, le stockage, la vente, la livraison et la comptabilisation des articles.

La fiche article peut être de type **Inventaire**, **Service** ou **Hors inventaire** pour spécifier si l'article est une unité d'inventaire physique, une unité de temps de travail ou une unité physique qui n'est pas suivie dans l'inventaire. Pour plus d'informations sur les types, voir [À propos des types d'articles](inventory-about-item-types.md).

Un article peut être structuré comme article parent avec les éléments enfants sous-jacents dans une nomenclature. Dans [!INCLUDE[d365fin](includes/d365fin_md.md)], une nomenclature peut être une nomenclature d'assemblage ou une nomenclature de production, selon son utilisation. Pour plus d'informations, reportez-vous à [Utiliser les nomenclatures](inventory-how-work-BOMs.md).

Si vous achetez le même article chez plusieurs fournisseurs, vous pouvez lier ces fournisseurs à la fiche article. Les fournisseurs s'affichent alors sur la page **Catalogue fournisseur articles**, de sorte que vous pouvez facilement sélectionner un autre fournisseur.

Les articles que vous offrez à vos clients mais que vous ne souhaitez pas gérer dans le système jusqu'à ce que vous commenciez à les vendre peuvent être définis comme des articles de catalogue. Les articles de catalogue ne doivent pas être confondus avec les articles normaux de type **Hors inventaire**. Pour en savoir plus, voir [Utiliser des articles de catalogue](inventory-how-work-nonstock-items.md).  

> [!NOTE]  
> Si des modèles article existent pour différents types d'articles, une page s'affiche automatiquement lorsque vous créez une nouvelle fiche article à partir de laquelle vous pouvez sélectionner un modèle article approprié. Si un seul modèle article existe, les nouvelles fiches article utiliseront toujours ce modèle.

La procédure suivante explique comment créer une fiche article à partir de zéro. Vous pouvez également créer de nouvelles fiches d'objets en copiant celles existantes. Pour plus d'informations, voir [Copier des articles existants pour créer de nouveaux articles](inventory-how-copy-items.md).  

> [!Video https://www.microsoft.com/videoplayer/embed/RE47eLx?rel=0]

## <a name="to-create-a-new-item-card"></a>Pour créer une fiche article

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2. Sur la page **Articles**, sélectionnez l'action **Nouveau**.

    Si un seul modèle article existe, une nouvelle fiche article avec certains champs renseignés à l'aide des informations provenant du modèle s'ouvre.
3. Sur la page **Sélectionnez un modèle pour un nouvel article**, sélectionnez le modèle que vous souhaitez utiliser pour la nouvelle fiche article.
4. Cliquez sur le bouton **OK**. Une nouvelle fiche article avec certains champs renseignés à l'aide des informations provenant du modèle s'ouvre.
5. Continuez à renseigner ou modifier les champs de la fiche article selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> Dans le champ **Mode évaluation coût**, vous configurez la façon dont le coût unitaire de l'article est calculé en estimant le flux d'articles physiques dans votre compagnie. Il existe cinq modes évaluation stock disponibles, selon le type d'article. Pour plus d'informations, [Détails de conception : modes évaluation stock](design-details-costing-methods.md).
>
> Si vous sélectionnez **Moyenne**, le coût unitaire de l'article est calculé comme le coût unitaire moyen à chaque moment après un achat. L'inventaire est évalué en supposant que tous les inventaires sont vendus simultanément. Avec ce paramètre, vous pouvez choisir le champ **Coût unitaire**, sur la page **Aperçu calc. coût moyen** de la fiche article pour afficher l'historique des transactions à partir duquel est calculé le coût moyen

Vous pouvez afficher ou modifier les prix ou escomptes spéciaux que vous accordez, ou que votre fournisseur vous accorde, pour l'article si certains critères sont réunis, par exemple le client, la quantité minimale de commande ou la date de fin. Pour ce faire, choisissez les actions **Définir des prix spéciaux** ou **Définir des escomptes spéciaux**. Chaque ligne de la page **Prix de vente**, par exemple, représente un prix spécial. Chaque colonne représente un critère qui doit s'appliquer pour accorder à un client le prix spécial que vous entrez dans le champ **Prix unitaire** de la page **Prix de vente**. Pour plus d'informations, voir [Enregistrement des prix de vente, des escomptes et des ententes sur les paiements](sales-how-record-sales-price-discount-payment-agreements.md) ou [Enregistrer des prix d'achat et des escomptes spéciaux](purchasing-how-record-purchase-price-discount-payment-agreements.md).

L'article est désormais enregistré, et la fiche article est prête à être utilisée sur les documents d'achat et de vente.

Si vous souhaitez utiliser cette fiche article comme modèle lorsque vous créez de nouvelles fiches article, enregistrez-la comme modèle. Pour plus d'informations, reportez-vous à la section suivantes.  

### <a name="to-save-the-item-card-as-a-template"></a>Pour enregistrer la fiche article en tant que modèle

1. Sur la page **Fiche article**, sélectionnez l'action **Sauvegarder comme modèle**. La page **Modèle article** s'ouvre et affiche la fiche article comme modèle.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Pour réutiliser les axes analytiques dans les modèles, sélectionnez l'action **Axes analytiques**. La page **Modèles dimension** s'ouvre et affiche tous les codes dimension qui sont configurés pour l'article.
4. Modifiez ou entrez les codes dimension s'appliquant aux nouvelles fiches article créées à l'aide du modèle.
5. Lorsque vous avez terminé le nouveau modèle article, cliquez sur le bouton **OK**.

Le modèle article est ajouté à la liste des modèles article. Vous pouvez ainsi l'utiliser pour créer des fiches article.

### <a name="items-used-in-production-orders"></a>Articles utilisés dans les bons de production

Si vous souhaitez enregistrer des articles qui sont ensuite utilisés dans des bons de production, vous spécifiez le système réappro. comme *Bon de production* sur le raccourci **Réapprovisionnement**. Pour plus d'informations, voir [À propos des bons de production](production-about-production-orders.md).  

## <a name="to-set-up-multiple-vendors-for-an-item"></a>Pour configurer plusieurs fournisseurs pour un article

Si vous achetez le même article chez plusieurs fournisseurs, vous devez saisir, pour chacun des fournisseurs de cet article des informations concernant, par exemple, ses prix, ses délais, ses escomptes, etc.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction de recherche](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Articles**, puis sélectionnez le lien associé.  
2. Sélectionnez l'article concerné, puis cliquez sur l'action **Modifier**.  
3. Sélectionnez l'action **Fournisseurs**.  
4. Cliquez sur le champ **N° fournisseur**, puis sélectionnez le fournisseur à paramétrer pour l'article.  
5. De manière facultative, renseignez les autres champs.  
6. Répétez les étapes 2 à 5 pour chaque fournisseur auprès de qui vous souhaitez acheter l'article.

Les fournisseurs s'affichent maintenant sur la page **Catalogue fournisseur articles** (que vous ouvrez à partir de la fiche article), de sorte que vous pouvez facilement sélectionner un autre fournisseur.

## <a name="categories-attributes-and-variants"></a>Catégories, attributs et variantes

[!INCLUDE[inventory_variant](includes/inventory_variant.md)]

## <a name="deleting-item-cards"></a>Suppression de fiches article

Si vous avez reporté une transaction pour un article, vous ne pouvez pas supprimer la fiche, car les écritures peuvent être nécessaires pour l'évaluation de l'inventaire ou l'audit. Pour supprimer des fiches article avec des écritures, contactez le partenaire Microsoft pour le faire par code.

## <a name="see-also"></a>Voir aussi

[Inventaire](inventory-manage-inventory.md)  
[Configuration d'unités de mesure](inventory-how-setup-units-of-measure.md)  
[Rapprocher les coûts de l'inventaire avec le grand livre](finance-how-to-post-inventory-costs-to-the-general-ledger.md)  
[Création des séries de numéros](ui-create-number-series.md)  
[Configuration de groupes de report](finance-posting-groups.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[d365fin](includes/d365fin_md.md)]](ui-work-product.md)  
