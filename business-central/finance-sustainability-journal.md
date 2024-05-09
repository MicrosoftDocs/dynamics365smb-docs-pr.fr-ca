---
title: Comment enregistrer les entrées de durabilité
description: Apprenez à enregistrer les émissions de GES (gaz à effet de serre).
author: altotovi
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'Sustainability, ESG, emission, GHG, CSRD, journal'
ms.search.form: '6216, 6219, 6220'
ms.date: 05/02/2024
ms.author: altotovi
ms.service: dynamics-365-business-central
---

# <a name="record-sustainability-entries"></a>Comment enregistrer les entrées de durabilité

À l’heure actuelle, la seule façon d’enregistrer les émissions de GES dans le **Compta. de durabilité** est d’utiliser les **Journaux de durabilité**.   

## <a name="sustainability-journals"></a>Journal durabilité

**Les journaux de durabilité** sont conçus pour suivre et enregistrer les activités liées au développement durable en utilisant la même expérience utilisateur que les autres journaux de Business Central. Dans le journal, les utilisateurs ont la possibilité de saisir manuellement les émissions s’ils possèdent les informations nécessaires. Alternativement, s’ils ne disposent pas de ces données, ils peuvent utiliser des formules intégrées pour calculer avec précision les émissions sur la base de paramètres connus spécifiques correspondant à différents types de sources et de comptes. 

Les informations que vous saisissez dans un journal sont temporaires et peuvent être modifiées tant qu’elles sont dans le journal. Lorsque vous reportez le journal, les informations sont transférées vers des **écritures durabilité** sur des **Comptes durabilité** individuels, où elles ne peuvent pas être modifiées. Vous pouvez toutefois reporter des écritures d’inversion ou de correction.  

### <a name="use-journal-templates-and-batches"></a>Utiliser des lots et des modèles journal

Il existe deux **Modèles de journaux de durabilité** par défaut : le modèle standard et le modèle récurrent. Pour chaque modèle journal, vous pouvez configurer votre propre journal personnel sous forme de lot de journal. Pour ce faire, vous devez choisir l’action **Lots** sur la page **Modèles de journaux de durabilité** et créer le nouveau **Lot journal durabilité** sur la nouvelle page. Par exemple, vous pouvez définir votre propre lot journal pour chaque étendue d’émission, à l’aide de l’option **Étendue de l’émission** qui vous permet de choisir entre trois étendues existantes. Vous pouvez également ajouter ou modifier le **Code source** et **Code motif** pour chacun des lots. 

>[!TIP]
>Vous pouvez avoir un lot journal pour chacun des types d’émissions, si vous avez plusieurs lignes, car cela peut réduire le risque d’erreurs, mais vous pouvez également utiliser le lot commun pour tous les types d’émissions.   

### <a name="validate-sustainability-journals"></a>Validation de journaux durabilité

Vous pouvez activer une vérification en arrière-plan sur la page **Configuration durabilité** qui aidera à éviter les retards lors du report. Le contrôle vous informe en cas d’erreur pendant l’utilisation du **Journal durabilité** et vous empêche de reporter le journal.  

Lorsque vous activez la validation, le Récapitulatif **Vérification de journal** affiche les problèmes de la ligne actuelle et du lot entier. La validation se produit lorsque vous chargez un lot journal et lorsque vous choisissez une autre ligne journal. La vignette **Nombre total d’erreurs** du Récapitulatif montre le nombre total de problèmes que [!INCLUDE [prod_short](includes/prod_short.md)] a trouvées, et vous pouvez le choisir pour ouvrir un aperçu des problèmes. 

### <a name="work-with-sustainability-journals"></a>Utiliser des journaux durabilité

Pour commencer à travailler avec les **Journaux durabilité**, suivez les étapes :   

1. Sélectionnez l’icône ![Ampoule qui ouvre la fenêtre de recherche 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal durabilité**, puis sélectionnez le lien associé. 
2. Sur la page **Journal durabilité** , vous pouvez saisir autant de lignes que vous prévoyez de reporter avec le même lot.  
3. En tant que **Type de document**, vous pouvez conserver une option vide ou choisir d’utiliser **Facture** ou **Note de crédit**.  
4. Dans le champ **N° de compte** , vous pouvez uniquement choisir **Comptes de durabilité** si vous sélectionnez **Report direct**, **Report** en tant que **Type de comptabilité** et compte non bloqué. En outre, les comptes doivent être configurés avec une catégorie et une sous-catégorie.  

>[!NOTE]
>Si vous utilisez le lot dans lequel le périmètre d’émission est configuré, le **portée d’émission** dans le **compte de durabilité** doit être égal au **Scope émission** dans le lot utilisé.  

5. Vous avez deux options : soit reporter manuellement les montants, soit utiliser des formules.   

    1. Si vous disposez d’informations précises sur l’émission et que vous souhaitez la reporter (c’est-à-dire qu’elle figure sur la facture reçue), vous devez sélectionner le champ **Saisie manuelle** pour spécifier que les montants seront saisis manuellement. Dans ce cas, vous ne pouvez pas renseigner vos données dans les champs **Carburant/Électricité**, **Distance**, **Montant personnalisé**, **Multiplicateur d’installation** et **Facteur de temps** , car ils ne seront pas modifiables pour ce choix. Mais les **émissions de CO2**, **émissions de CH4** et **émissions de N2O** les champs seront modifiables et vous pourrez y remplir vos données directement. 
    2. Si vous ne connaissez pas votre émission avec précision, vous devez la calculer, et vous ne devez pas avoir sélectionné le champ **Saisie manuelle** , et dans ce cas le **Émission CO2**, **Émission CH4** et **Émission N2O** champs ne sera pas modifiable, mais vous pouvez saisir les détails de votre calcul en fonction de la formule que vous utilisez. Vous pouvez en savoir plus sur les formules utilisées et définies dans la **Catégorie de comptes de durabilité** ici dans le [Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md#account-categories).
    
7. Pour valider la feuille, sélectionnez l'action **Valider**. Lorsque vous reportez dans un **journal durabilité**, les écritures sont générées dans le **Grand livre durabilité**. 

Dans le cas où votre formule est basée sur l’option **Calculer à partir du grand livre** dans la **Catégorie de compte de durabilité**, vous devez utiliser l’action **Recueillir le montant des écritures GL** action avant de reporter le journal pour calculer les émissions en fonction de cette source de données. De plus, si vous avez apporté des modifications aux facteurs d’émission après avoir renseigné les lignes de journal, vous devez choisir le **Recalculer** action pour obtenir le montant approprié dans le journal.  

### <a name="recurring-journals"></a>Journaux récurrents

Un journal récurrent est un **journal durabilité** contenant des champs spécifiques pour la gestion des transactions que vous reportez fréquemment avec peu ou pas de modifications. Par exemple, les transactions durables telles que l’électricité, le chauffage ou d’autres transactions similaires. L’utilisation de journaux récurrents vous permet de reporter des montants fixes et variables. Avec un journal récurrent, vous ne créez les écritures qui sont régulièrement reportées qu’une fois. Par exemple, les comptes, dimensions, valeurs de dimension, etc. restent dans le journal après report. Si des modifications sont nécessaires, vous pouvez les apporter à chaque report. 

Le champ **Mode récurrent** est important. Il détermine la manière dont le montant de la ligne journal est traité après report. Par exemple, si vous utilisez le même montant à chaque fois que vous reportez la ligne, vous pouvez conserver le montant, et dans ce cas, vous devez utiliser l’option **F Fixe**. Si vous utilisez les mêmes comptes et le même texte pour la ligne, mais que le montant varie chaque fois que vous reportez, vous pouvez choisir de supprimer le montant après report, et dans ce cas, l’option **Variable V**. 

Vous devez également configurer le champ **Fréquence de la récurrence**, car ce champ de formule de date détermine la fréquence de report de l’écriture sur la ligne journal et il doit être rempli. En savoir plus sur [Utiliser des formules de date](ui-enter-date-ranges.md#use-date-formulas).  

Le champ **Date expiration** détermine la date à laquelle la ligne est reportée pour la dernière fois. La ligne n’est plus reportée après cette date. L’avantage d’utiliser le champ **Date d’expiration** est que la ligne n’est pas supprimée immédiatement du journal. Vous pouvez entrer une date ultérieure afin de pouvoir utiliser la ligne à l’avenir. Si le champ est vide, la ligne est reportée à chaque fois, jusqu’à ce qu’elle soit supprimée du journal.  

## <a name="see-also"></a>Voir aussi .
[Finances](finance.md)    
[Vue d’ensemble de la gestion de la durabilité](finance-manage-sustainability.md)   
[Configuration de durabilité](finance-sustainability-setup.md)   
[Graphique des comptes de durabilité et de comptabilité](finance-sustainability-accounts-ledger.md)   
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)   

[!INCLUDE[footer-include](includes/footer-banner.md)]
