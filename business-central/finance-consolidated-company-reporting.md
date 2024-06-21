---
title: Consolider les données de plusieurs compagnies
description: Cet article explique comment vous pouvez consolider les écritures d’au moins deux compagnies séparées (filiales) dans une compagnie consolidée.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.date: 06/27/2023
ms.custom: bap-template
ms.search.keywords: 'consolidation, subsidiaries, consolidate'
ms.search.form: '1826, 1827'
ms.service: dynamics-365-business-central
---

# <a name="consolidating-financial-data-from-multiple-companies"></a>Consolidation des données financières de plusieurs compagnies

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui doivent rendre compte aux organisations mères. [!INCLUDE [prod_short](includes/prod_short.md)] fournit aux comptables des outils qui les aident à transférer les écritures de deux ou plusieurs compagnies (filiales) dans une compagnie consolidée.  

Chaque compagnie impliquée dans une consolidation est appelée unité fonctionnelle. La compagnie dans laquelle vous combinez les données est appelée compagnie consolidée.  

Vous pouvez transférer les données financières des filiales vers la compagnie consolidée, même si les filiales utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans différents environnements. Pour en savoir plus sur la façon de vous connecter à d’autres environnements, consultez [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md#busunit).

Si les états financiers d’une unité fonctionnelle utilisent une devise différente de celle de la compagnie consolidée, vous devez configurer les taux de change pour la consolidation. Pour en savoir plus sur les taux de change pour les consolidations, consultez [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md#exchrates).  

Vous pouvez consolider :  

* entre compagnies ayant plusieurs plans comptables ;  
* des compagnies qui utilisent plusieurs exercices financiers et devises ;  
* la totalité ou un pourcentage des informations financières d’une compagnie ;
* Utilisation de plusieurs taux de change dans des comptes du grand livre individuels.
* Compagnies dans d’autres programmes de gestion comptable et d’entreprise.
* Compagnies dans des environnements [!INCLUDE [prod_short](includes/prod_short.md)] différents.

Vous configurez la compagnie consolidée de la même manière que vous configurez d'autres compagnies. Le plan comptable est indépendant des plans comptables des unités fonctionnelles. Le plan comptable des unités fonctionnelles peut différer des autres. Pour en savoir plus sur la configuration d’une consolidation, consultez [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md).  

> [!TIP]
> La consolidation des données financières peut être particulièrement appropriée pour les processus intersociétés. Pour en savoir plus sur les fonctionnalités intersociétés, consultez [Gestion des transactions intersociétés](intercompany-manage.md).

## <a name="consolidate-data"></a>Consolider les données

Avant de procéder à une consolidation, il est recommandé de tester vos données avant de les transférer vers la compagnie consolidée. [!INCLUDE[prod_short](includes/prod_short.md)] recherche des différences dans les informations des unités fonctionnelles et de la compagnie consolidée. Par exemple, si les numéros de compte ou les codes axe sont différents. Corrigez les erreurs trouvées avant d’exécuter le rapport. Vous pouvez tester la base de données ou, si vous importez des données à partir d’un fichier XML, le fichier.

### <a name="test-the-data-before-you-consolidate"></a>Tester les données avant la consolidation

1. Ouvrez la compagnie consolidée.  
2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unités fonctionnelles**, puis choisissez le lien associé.  
3. Testez le fichier et la base de données, comme suit :  

    * Pour tester un fichier, choisissez l'action **Tester fichier**, entrez le nom du fichier à tester, puis choisissez **Imprimer**.  
    * Pour tester la base de données, choisissez **Tester base de données**.  

### <a name="run-the-consolidation"></a>Exécuter la consolidation

Une fois les données testées, vous pouvez les transférer vers la compagnie consolidée. Un guide de configuration assistée vous aide tout au long du processus.

> [!NOTE]
> Lorsque vous exécutez la consolidation, vous pouvez choisir les compagnies à inclure. Si votre compagnie consolidée n’a pas accès à une ou plusieurs filiales, le guide vous en accorde l’accès.

1. Connectez-vous à la compagnie consolidée.  
2. Sur la page **Unités fonctionnelles**, choisissez l’action **Consolider**.  
3. Renseignez les champs requis.  

## <a name="use-the-consolidated-trial-balance-report"></a>Utiliser le rapport Balance de vérification consolidée

Le rapport **Balance de vérification consolidée** peut vous donner un aperçu de leur santé financière dans leur ensemble. Le rapport regroupe les écritures de chacune de vos compagnies dans une nouvelle compagnie créée pour les données consolidées. La compagnie consolidée est un conteneur pour les données consolidées, et ne contient pas de données métier en temps réel. Les compagnies que vous incluez dans la compagnie consolidée deviennent des **Unités fonctionnelles** dans le rapport. Avec quatre unités fonctionnelles maximum, vous pouvez utiliser le rapport **Balance de vérification consolidée (4)**.  

Le rapport affiche une ligne pour chaque compte et suit la structure du plan comptable. Un compte n’est pas affiché si tous les montants de la ligne sont égaux à 0. Le rapport affiche les informations suivantes pour chaque compte :

* Le numéro de compte et le nom du compte.
* Les totaux pour la compagnie consolidée et pour chaque unité fonctionnelle. Les totaux peuvent s’afficher comme solde période ou solde à ce jour.
* Les éliminations effectuées dans la compagnie consolidée. Elles sont toujours affichées pour une période correspondant à l’exercice financier comptable de la compagnie consolidée.
* Le total de la compagnie consolidée après les éliminations, affiché comme solde période ou solde à ce jour.

## <a name="eliminate-repeated-transactions"></a>Éliminer les transactions répétées

Après que vous avez consolidé toutes les compagnies, vous devez rechercher toutes les transactions enregistrées dans plusieurs compagnies, puis valider les écritures d’élimination pour les supprimer. Le traitement d'éliminations de consolidation est un processus manuel.  

Pour éliminer les transactions répétées :

1. Recherchez des transactions qui doivent être ajustées potentiellement et entrez les lignes journal général pour les éliminer.
2. Exécutez le rapport **Éliminations consolidation GL** pour évaluer l'effet des lignes journal général avant le report.
3. Reportez les transactions d'ajustement.

Le rapport **Éliminations consolidation GL**affiche une balance de vérification provisoire dans laquelle vous pouvez simuler les conséquences de l’élimination des écritures. Le rapport compare les écritures dans la compagnie consolidée avec les éliminations inscrites au journal général.

Pour que vous puissiez inclure une unité fonctionnelle dans le rapport, vous devez la configurer sur la page **Unités fonctionnelles**. Assurez-vous d’activer le bouton bascule **Consolider**.

Une ligne est créée pour chaque compte s’affiche, selon la structure du plan comptable. Un compte n’est pas affiché si tous les montants de la ligne sont égaux à 0. Le rapport affiche les informations suivantes pour chaque compte :

* Numéro de compte.
* Nom du compte.
* Si vous avez sélectionné un ou plusieurs codes unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total excluant les éliminations et les unités fonctionnelles sélectionnées est affiché pour la compagnie consolidée. Si le champ **Code unité fonctionnelle** n’est pas renseigné, un total excluant les éliminations est affiché pour la compagnie consolidée.
* Si vous avez sélectionné un code unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total est affiché pour les écritures importées à partir de l’unité fonctionnelle. Si le champ **Code unité fonctionnelle** n’est pas renseigné, un total est affiché pour les éliminations reportées dans la compagnie consolidée.
* Le total de la compagnie consolidée, avec toutes les unités fonctionnelles et toutes les éliminations reportées.
* Les éliminations effectuées dans la compagnie consolidée. C’est-à-dire les écritures du journal général sélectionnées sur la page de demande.
* Le texte de report copié à partir du journal général.
* Le total de la compagnie consolidée après les éliminations, si elles sont reportées.

## <a name="export-and-import-consolidated-data-between-databases"></a>Exporter et importer des données consolidées entre des bases de données

Si les données d’une unité fonctionnelle se trouvent dans une autre base de données, vous pouvez effectuer un transfert manuel basé sur un fichier ou automatiser le processus à l’aide d’une API. Pour en savoir plus sur l’API, consultez [Utiliser notre API pour partager automatiquement des données entre les environnements](#use-our-api-to-automatically-share-data-across-environments).

Cette section décrit le processus manuel basé sur un fichier.

Vous exportez les données vers un fichier avant de les inclure dans la consolidation. Exportez chaque compagnie séparément en utilisant le traitement en lot **Exporter fichier consolidation**.  

> [!TIP]
> Utilisez le même processus pour exporter les données consolidées que vous devez envoyer à Dynamics 365 Finance. Par exemple, si l'unité fonctionnelle est une filiale et que la compagnie mère utilise Dynamics 365 Finance.

Après l'exécution du traitement en lot, toutes les écritures des comptes GL sont traitées. Pour chaque combinaison d'axe principal et date sélectionnés, la valeur des champs **Montant** des écritures est totalisée et exportée. La combinaison suivante des dimensions et de la date sélectionnées avec le même numéro de compte est traitée. Ensuite, les combinaisons du numéro de compte suivant sont traitées, et ainsi de suite.  

Les écritures exportées contiennent les champs suivants : **N° compte**, **Date comptabilisation** et **Montant**. Si des informations de dimensions ont également été exportées, des codes de dimension et des valeurs de dimension sont également inclus.  

1. Pour chaque ligne exportée, si le total des champs **Montant** est un débit, le numéro de compte configuré dans le champ **Compte débit consolidation** de l'unité fonctionnelle est exporté vers la ligne. Si le total est un crédit, le numéro correspondant dans le champ **Compte crédit consolidation** est exporté vers la ligne.  
2. La date utilisée pour chaque ligne exportée est la date de fin de la période ou, si le transfert est opéré chaque jour, la date du calcul.  
3. La valeur de dimension exportée pour la saisie est celle de la compagnie consolidée configurée dans le champ **Code consolidation** pour cette valeur de dimension. Si aucune valeur de dimension de compagnie consolidée n’a été entrée dans le champ **Code consolidé** à cette fin, la valeur de dimension proprement dite est exportée vers la ligne.  
4. Les fichiers XML contiennent également les taux de change devise correspondant à la période de consolidation. Ces taux sont inclus dans une section distincte au début du fichier.  

## <a name="use-our-api-to-automatically-share-data-across-environments"></a>Utiliser notre API pour partager automatiquement des données entre les environnements

[!INCLUDE [prod_short](includes/prod_short.md)] fournit une API qui vous permet d’automatiser le processus de partage des données financières entre les unités fonctionnelles et la compagnie consolidée. L’API est gratuite à utiliser et facile à configurer. Elle vous permet même de partager des données entre différents environnements [!INCLUDE [prod_short](includes/prod_short.md)]. Par exemple, vous devrez peut-être partager des données entre différents environnements lorsque les unités fonctionnelles ne se trouvent pas dans les mêmes zones géographiques Azure. Pour en savoir plus sur l’utilisation de l’API pour automatiser le processus de consolidation, consultez [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md#busunit).

## <a name="see-also"></a>Voir aussi

[Configuration de la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
