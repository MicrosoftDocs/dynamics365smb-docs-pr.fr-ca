---
title: Consolider les données de plusieurs compagnies
description: Cette rubrique explique comment vous pouvez consolider les écritures d’au moins deux compagnies séparées (filiales) dans une compagnie consolidée.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'consolidation, subsidiaries, consolidate'
ms.search.form: '1826, 1827'
ms.date: 06/16/2021
ms.author: edupont
---

# <a name="consolidating-financial-data-from-multiple-companies"></a>Consolidation des données financières de plusieurs compagnies

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui doivent rendre compte aux organisations mères. Dans les deux cas, les comptables utilisent des outils intégrés pour aider à consolider les données financières.  

Vous pouvez consolider les écritures d’au moins deux compagnies séparées (filiales) dans une compagnie consolidée. Chaque compagnie individuelle impliquée dans une consolidation est appelée unité fonctionnelle. La compagnie résultant de la combinaison est appelée compagnie consolidée.  

Vous pouvez importer des données dans la compagnie consolidée à partir d’autres compagnies du même abonné [!INCLUDE [prod_short](includes/prod_short.md)], à partir d'abonnés ou à partir de fichiers.  

Si les états financiers d’une unité fonctionnelle sont dans une devise différente de celle de la compagnie consolidée, vous devez configurer les taux de change pour la consolidation.  

Vous pouvez consolider :  

* entre compagnies ayant plusieurs plans comptables ;  
* des compagnies qui utilisent plusieurs exercices financiers et devises ;  
* la totalité ou un pourcentage des informations financières d'une compagnie ;
* Utilisation de plusieurs taux de change dans des comptes du grand livre individuels
* Compagnies dans d’autres programmes de gestion comptable et d’entreprise

Vous configurez la compagnie consolidée de la même manière que vous configurez d'autres compagnies. Le plan comptable est indépendant du plan comptable des autres unités fonctionnelles et le plan comptable des unités fonctionnelles individuelles peut varier. Vous configurez une liste de compagnies à consolider, vérifiez les données comptables avant leur consolidation, importez des fichiers ou des bases de données et générez des rapports de consolidation. Pour plus d’informations, voir [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md).  

> [!TIP]
> La consolidation des données financières peut être particulièrement appropriée en association avec des processus intersociétés. Pour plus d'informations, voir [Gestion des transactions intersociétés](intercompany-manage.md).

## <a name="trial-balance"></a>Balance de vérification

Si vous avez plusieurs compagnies dans [!INCLUDE[prod_short](includes/prod_short.md)], le rapport **Balance de vérification consolidée** peut vous donner un aperçu de leur santé financière dans leur ensemble.  

Le rapport regroupe les écritures de chacune de vos compagnies dans une nouvelle compagnie que vous créez pour stocker les données consolidées. Cette compagnie est généralement appelée « compagnie consolidée ». La compagnie consolidée est un simple conteneur pour les données consolidées, et ne contient pas de données métier en temps réel. Les compagnies que vous incluez dans la compagnie consolidée deviennent des **Unités fonctionnelles** dans le rapport. Pour plus d’informations, voir [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md).  

## <a name="consolidate-data"></a>Consolider les données

Le processus de transfert des chiffres des unités fonctionnelles vers la compagnie consolidée est la *consolidation* à proprement parler. Avant de réaliser cette opération, il peut être intéressant de rechercher les éventuelles différences entre les informations de base dans les unités fonctionnelles et dans la compagnie consolidée. Il existe deux rapports que vous pouvez utiliser pour tester la base de données et le fichier.

### <a name="to-test-the-data-before-you-consolidate"></a>Pour tester les données avant la consolidation

Vous pouvez tester vos données avant de les transférer vers la compagnie consolidée. [!INCLUDE[prod_short](includes/prod_short.md)] recherche des différences dans les informations des unités fonctionnelles et de la compagnie consolidée. Par exemple, si les numéros de compte ou les codes axe sont différents. Vous devez corriger les erreurs avant d'exécuter le rapport. Vous pouvez tester la base de données ou, si vous importez des données à partir d'un fichier XML, vous pouvez tester le fichier.  

1. Ouvrez la compagnie consolidée.  
2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unités fonctionnelles**, puis choisissez le lien associé.  
3. Exécutez l'une des opérations suivantes :  

    * Pour tester un fichier, choisissez l'action **Tester fichier**, entrez le nom du fichier à tester, puis choisissez **Imprimer**.  
    * Pour tester la base de données, choisissez **Tester base de données**.  

### <a name="run-the-consolidation"></a>Exécuter la consolidation

Une fois les données testées, vous pouvez les transférer vers la compagnie consolidée.  

1. Connectez-vous à la compagnie consolidée.  
2. Dans le **Tableau de bord Comptable**, choisissez l'action **Exécuter la consolidation**.  
3. Renseignez les champs requis.  
4. Dans la section Filtre, définissez un filtre pour l'unité fonctionnelle ou le nom de la compagnie concerné.  
5. programmez éventuellement le rapport à exécuter à une heure spécifique.  

## <a name="eliminate-repeated-transactions"></a>Éliminer les transactions répétées

Après que vous avez consolidé toutes les compagnies, vous devez rechercher toutes les transactions enregistrées plusieurs fois dans des compagnies, puis reporter les écritures élimination pour les supprimer.

Le traitement d'éliminations de consolidation est un processus manuel.  

Pour éliminer les transactions répétées :

1. Recherchez des transactions qui doivent peut-être être ajustées et entrez les lignes journal général pour les éliminer.
2. Exécutez le rapport **Éliminations consolidation GL** pour évaluer l'effet des lignes journal général avant le report.
3. Reportez les transactions d'ajustement.

Le rapport **Éliminations consolidation GL** affiche une tentative de balance de vérification où vous pouvez simuler les conséquences de l'élimination des écritures en comparant les écritures de la compagnie consolidée avec les éliminations entrées dans le journal général.

Pour qu'une unité fonctionnelle puisse être incluse dans le rapport, elle doit être configurée sur la page **Unités fonctionnelles** et le champ **Consolider** doit être sélectionné.

Chaque compte s'affiche individuellement sur une ligne, selon la structure du plan comptable. Un compte n'est pas affiché si tous les montants de la ligne sont égaux à 0. Les informations suivantes sont données pour chaque compte :

* Numéro de compte
* Nom du compte.
* Si vous avez sélectionné un ou plusieurs codes unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total excluant les éliminations et les unités fonctionnelles sélectionnées est affiché pour la compagnie consolidée. Si le champ **Code unité fonctionnelle** n'est pas renseigné, un total excluant les éliminations est affiché pour la compagnie consolidée.
* Si vous avez sélectionné un code unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total est affiché pour les écritures importées à partir de l'unité fonctionnelle. Si le champ **Code unité fonctionnelle** n'est pas renseigné, un total est affiché pour les éliminations reportées dans la compagnie consolidée.
* Le total de la compagnie consolidée, avec toutes les unités fonctionnelles et toutes les éliminations reportées.
* Les éliminations à effectuer dans la compagnie consolidée, c'est-à-dire les écritures du journal général sélectionné sur la page de demande.
* Le texte de report copié à partir du journal général.
* Le total de la compagnie consolidée après les éliminations, si elles sont reportées.

## <a name="export-and-import-consolidated-data-between-databases"></a>Exporter et importer des données consolidées entre des bases de données

Si les données d'une unité fonctionnelle se trouvent dans une autre base de données, vous devez exporter les données dans un fichier avant de les inclure dans la consolidation. Chaque compagnie doit être exportée séparément. À cette fin, utilisez le traitement par lots **Exporter fichier consolidation**.  

> [!TIP]
> Utilisez le même processus pour exporter les données consolidées qui doivent être soumises à Dynamics 365 Finance, par exemple si l'unité fonctionnelle actuelle est une filiale et que la compagnie mère utilise Dynamics 365 Finance.

Après l'exécution du traitement en lot, toutes les écritures des comptes GL sont traitées. Pour chaque combinaison d'axe principal et date sélectionnés, la valeur des champs **Montant** des écritures est totalisée et exportée. La combinaison d'axe principal et date sélectionnés suivante qui a le même numéro de compte est traitée, puis les combinaisons ayant le numéro de compte suivant sont traitées, etc.  

Les écritures exportées contiennent les champs suivants : **N° compte**, **Date comptabilisation** et **Montant**. Si des informations de dimensions ont également été exportées, des codes de dimension et des valeurs de dimension sont également inclus.  

1. Pour chaque ligne exportée, si le total des champs **Montant** est un débit, le numéro de compte configuré dans le champ **Compte débit consolidation** de l'unité fonctionnelle est exporté vers la ligne. Si le total est un crédit, le numéro correspondant dans le champ **Compte crédit consolidation** est exporté vers la ligne.  
2. La date utilisée pour chaque ligne exportée est la date de fin de la période ou, si le transfert est opéré chaque jour, la date du calcul.  
3. La section analytique exportée pour la saisie est celle de la société consolidée configurée dans le champ **Code consolidation** pour cette section analytique. Si aucune section analytique de société consolidée n'a été entrée dans le champ **Code consolidé** à cette fin, la section analytique proprement dite est exportée vers la ligne.  
4. Les fichiers XML contiennent également les taux de change devise correspondant à la période de consolidation. Ces taux sont inclus dans une section distincte au début du fichier.  

## <a name="see-also"></a>Voir aussi

[Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]