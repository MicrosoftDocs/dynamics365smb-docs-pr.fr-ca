---
title: Enregistrer les entrées de durabilité
description: Apprenez à enregistrer les émissions de GES (gaz à effet de serre).
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, journal'
ms.search.form: '6216, 6219, 6220'
ms.date: 05/07/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---

# <a name="record-sustainability-entries"></a>Enregistrer les entrées de durabilité

À l’heure actuelle, la seule façon d’enregistrer les émissions de gaz à effet de serre (GES) dans le grand livre durabilité est d’utiliser des journaux durabilité.

## <a name="sustainability-journals"></a>Journaux durabilité

Les journaux durabilité sont conçus pour suivre et enregistrer les activités liées au développement durable en utilisant la même expérience utilisateur que les autres journaux de Business Central. Les utilisateurs disposant des informations nécessaires peuvent saisir manuellement les émissions dans un journal. Alternativement, s’ils ne disposent pas de ces informations, ils peuvent utiliser des formules intégrées pour calculer avec précision les émissions sur la base de paramètres connus spécifiques correspondant à différents types de sources et de comptes.

Les informations que vous saisissez dans un journal sont temporaires et peuvent être modifiées tant qu’elles sont dans ce journal. Lorsque vous reportez le journal, les informations sont transférées vers des écritures durabilité sur des comptes durabilité individuels, où elles ne peuvent pas être modifiées. Vous pouvez toutefois reporter des écritures d'inversion ou de correction.

### <a name="use-journal-templates-and-batches"></a>Utiliser des lots et des modèles journal

Par défaut, il existe deux modèles de journal durabilité par défaut : le modèle standard et le modèle récurrent.

Pour chaque modèle journal, vous pouvez configurer votre propre journal personnel sous forme de lot de journal. Pour ce faire, sélectionnez l’action **Lots** sur la page **Modèles de journaux durabilité**, puis créez le **nouveau lot journal durabilité** sur la nouvelle page. Par exemple, vous pouvez définir votre propre lot journal pour chaque étendue d’émission, à l’aide de l’option **Étendue de l’émission** qui vous permet de choisir entre trois étendues existantes. Pour chaque lot, vous pouvez également ajouter ou modifier les valeurs **Code source** et **Code motif**.

> [!TIP]
> Si vous disposez de plusieurs lignes, vous pouvez contribuer à réduire le risque d’erreurs en créant un lot journal pour chaque type d’émission. Vous pouvez également utiliser le lot commun pour tous les types d’émissions.

### <a name="validate-sustainability-journals"></a>Valider les journaux durabilité

Sur la page **Configuration durabilité**, vous pouvez activer une vérification en arrière-plan pour aider à éviter les retards de report. Si une erreur survient lorsque vous travaillez dans le journal durabilité, la validation vous informe et vous empêche de reporter le journal.

Lorsque vous activez la validation, le Récapitulatif **Vérification de journal** affiche les problèmes de la ligne actuelle et du lot entier. La validation se produit lorsque vous chargez un lot journal et lorsque vous sélectionnez une autre ligne journal. La vignette **Problèmes totaux** du récapitulatif indique le nombre total de problèmes [!INCLUDE [prod_short](includes/prod_short.md)] trouvés. Vous pouvez sélectionner la vignette pour ouvrir une vue d’ensemble des problèmes.

### <a name="work-with-sustainability-journals"></a>Utiliser des journaux durabilité

Pour commencer à travailler avec les journaux durabilité, suivez ces étapes :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal durabilité**, puis sélectionnez le lien associé.
2. Sur la page **Journal durabilité** , saisissez autant de lignes que vous prévoyez de reporter dans le même lot.
3. Vous pouvez laisser le champ **Type de document** vide ou sélectionner **Facture** ou **Note de crédit**.
4. Dans le champ **N° de compte**, vous pouvez sélectionner uniquement les comptes de durabilité non bloqués pour lesquels le champ **Report direct** est sélectionné et le champ **Type de comptabilité** est défini sur **Report**. Les comptes doivent être également configurés avec une catégorie et une sous-catégorie.

    > [!NOTE]
    > Si vous utilisez le lot dans lequel le périmètre d’émission est configuré, la valeur **Champ d’émission** dans le compte de durabilité doit être égal à la valeur **Champ de l’émission** dans le lot.

5. Vous pouvez soit reporter manuellement les montants, soit utiliser des formules.

    - Si vous disposez d’informations précises sur l’émission et que vous souhaitez les reporter (c’est-à-dire que vous avez des informations sur la facture reçue), sélectionnez le champ **Saisie manuelle** pour spécifier que vous allez saisir les montants manuellement. Dans ce cas, vous ne pouvez pas renseigner vos données dans les champs **Carburant/Électricité**, **Distance**, **Montant personnalisé**, **Multiplicateur d’installation** et **Facteur de temps** , car ils ne seront pas modifiables pour ce choix. Mais les champs **émissions de CO2**, **émissions de CH4** et **émissions de N2O** seront modifiables et vous pourrez y remplir vos données directement.
    - Si vous n’avez pas une connaissance précise de l’émission et devez la calculer, ne sélectionnez pas le champ **Saisie manuelle**. Dans ce cas, les champs **émissions de CO2**, **émissions de CH4** et **émissions de N2O** ne sont plus modifiables. Cependant, vous pouvez saisir les détails de votre calcul en fonction de la formule que vous utilisez. Vous pouvez en savoir plus sur les formules utilisées et définies dans la **Catégorie de comptes de durabilité** ici dans le [Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md#account-categories).

6. Pour reporter le journal, sélectionnez l’action **Reporter**. Lors du report dans un journal durabilité, les écritures sont générées dans le grand livre durabilité.

Si votre formule est basée sur l’option **Calculer à partir du grand livre** dans la catégorie de compte de durabilité, vous devez utiliser l’action **Recueillir le montant des écritures GL** avant de reporter le journal pour calculer les émissions en fonction de cette source de données. De plus, si vous avez apporté des modifications aux facteurs d’émission après avoir renseigné les lignes journal, vous devez choisir l’action **Recalculer** pour obtenir le montant approprié dans le journal.

### <a name="recurring-journals"></a>Journaux récurrents

Un journal récurrent est un journal durabilité contenant des champs spécifiques pour la gestion des transactions que vous reportez fréquemment avec peu ou pas de modifications. Par exemple, les transactions durables telles que l’électricité, le chauffage ou d’autres transactions similaires. Vous pouvez utiliser les journaux récurrents pour reporter des montants fixes et variables.

Lorsque vous utilisez un journal récurrent, les écritures qui sont régulièrement reportées ne doivent être créées qu’une fois. Des informations telles que les comptes, dimensions et valeurs de dimension, restent dans le journal après le report. À chaque report, vous pouvez apporter toutes les modifications requises.

Le champ **Mode récurrent** est important. Il détermine la manière dont le montant de la ligne journal est traité après report. Par exemple, si vous utilisez le même montant à chaque fois que vous reportez la ligne, vous pouvez sélectionner l’option **F Fixe** pour que le montant reste au-delà du report. Si vous utilisez les mêmes comptes et le même texte sur la ligne, mais que le montant varie à chaque report, vous pouvez choisir de supprimer le montant après le report, dans ce cas, l’option **Variable V**.

Le champ **Fréquence récurrente** est également important et doit être défini. Ce champ de formule de date détermine la fréquence de report de l’écriture sur la ligne journal. En savoir plus dans [Utiliser des formules de date](ui-enter-date-ranges.md#use-date-formulas).

Le champ **Date expiration** détermine la date à laquelle la ligne est reportée pour la dernière fois. La ligne n’est plus reportée après cette date. L’avantage d’utiliser le champ **Date d’expiration** est que la ligne n’est pas supprimée immédiatement du journal. Vous pouvez entrer une date ultérieure afin de pouvoir utiliser la ligne à l’avenir. Si le champ est blanc, la ligne est reportée à chaque fois, jusqu’à ce qu’elle soit supprimée du journal.

## <a name="see-also"></a>Voir aussi .

[Finances](finance.md)  
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)  
[Configuration de durabilité](finance-sustainability-setup.md)  
[Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
