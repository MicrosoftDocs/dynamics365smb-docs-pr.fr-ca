---
title: Consolider les données de plusieurs compagnies
description: Cet article explique comment vous pouvez consolider les écritures d’au moins deux compagnies séparées (filiales) dans une compagnie consolidée.
author: brentholtorf
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: 'consolidation, subsidiaries, consolidate'
ms.search.form: '1826, 1827'
ms.date: 09/29/2022
ms.author: bholtorf
---

# Consolidation des données financières de plusieurs compagnies

Certaines organisations utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans plusieurs unités fonctionnelles ou entités juridiques. D’autres utilisent [!INCLUDE [prod_short](includes/prod_short.md)] dans les filiales qui doivent rendre compte aux organisations mères. Dans les deux cas, les comptables utilisent des outils intégrés pour aider à consolider les données financières.  

Vous pouvez consolider les écritures d’au moins deux compagnies séparées (filiales) dans une compagnie consolidée. Chaque compagnie individuelle impliquée dans une consolidation est appelée unité fonctionnelle. La compagnie résultant de la combinaison est appelée compagnie consolidée.  

Vous pouvez importer des données dans la compagnie consolidée à partir d’autres compagnies du même abonné [!INCLUDE [prod_short](includes/prod_short.md)], des abonnés ou des fichiers.  

Si les états financiers d’une unité fonctionnelle sont dans une devise différente de celle utilisée dans la compagnie consolidée, vous devez configurer les taux de change pour la consolidation.  

Vous pouvez consolider :  

* entre compagnies ayant plusieurs plans comptables ;  
* des compagnies qui utilisent plusieurs exercices financiers et devises ;  
* la totalité ou un pourcentage des informations financières d'une compagnie ;
* Utilisation de plusieurs taux de change dans des comptes du grand livre individuels
* Compagnies dans d’autres programmes de gestion comptable et d’entreprise

Vous configurez la compagnie consolidée de la même manière que vous configurez d'autres compagnies. Le plan comptable est indépendant des plans comptables des unités fonctionnelles. Le plan comptable des unités fonctionnelles peut différer des autres. Vous configurez une liste de compagnies à consolider, vérifiez les données comptables avant leur consolidation, importez des fichiers ou des bases de données et générez des rapports de consolidation. Pour plus d’informations, voir [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md).  

> [!TIP]
> La consolidation des données financières peut être particulièrement appropriée en association avec des processus intersociétés. Pour plus d'informations, voir [Gestion des transactions intersociétés](intercompany-manage.md).

## Utiliser le rapport Balance de vérification consolidée

Le rapport **Balance de vérification consolidée** peut vous donner un aperçu de leur santé financière dans leur ensemble. Le rapport regroupe les écritures de chacune de vos compagnies dans une nouvelle compagnie créée pour les données consolidées. Cette compagnie est généralement appelée *compagnie consolidée*. La compagnie consolidée est un conteneur pour les données consolidées, et ne contient pas de données métier en temps réel. Les compagnies que vous incluez dans la compagnie consolidée deviennent des **Unités fonctionnelles** dans le rapport. Pour plus d’informations, voir [Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md). Avec quatre unités fonctionnelles maximum, vous pouvez utiliser le rapport **Balance de vérification consolidée (4)**.  

Le rapport affiche une ligne pour chaque compte et suit la structure du plan comptable. Un compte n’est pas affiché si tous les montants de la ligne sont égaux à 0. Le rapport affiche les informations suivantes pour chaque compte :

* Le numéro de compte et le nom du compte.
* Les totaux pour la compagnie consolidée et pour chaque unité fonctionnelle. Les totaux peuvent s’afficher comme solde période ou solde à ce jour.
* Les éliminations effectuées dans la compagnie consolidée. Elles sont toujours affichées pour une période correspondant à l’exercice financier comptable de la compagnie consolidée.
* Le total de la compagnie consolidée après les éliminations, affiché comme solde période ou solde à ce jour.

## Consolider les données

Le processus de transfert des chiffres des unités fonctionnelles vers la compagnie consolidée est la *consolidation* à proprement parler. Avant de réaliser la consolidation, il peut être intéressant de rechercher les éventuelles différences entre les informations de base dans les unités fonctionnelles et dans la compagnie consolidée. Il existe deux rapports que vous pouvez utiliser pour tester la base de données et le fichier.

### Pour tester les données avant la consolidation

Testez vos données avant de les transférer vers la compagnie consolidée. [!INCLUDE[prod_short](includes/prod_short.md)] recherche des différences dans les informations des unités fonctionnelles et de la compagnie consolidée. Par exemple, si les numéros de compte ou les codes axe sont différents. Vous devez corriger les erreurs avant d'exécuter le rapport. Vous pouvez tester la base de données ou, si vous importez des données à partir d’un fichier XML, vous pouvez tester le fichier.  

1. Ouvrez la compagnie consolidée.  
2. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Unités fonctionnelles**, puis choisissez le lien associé.  
3. Testez le fichier et la base de données, comme suit :  

    * Pour tester un fichier, choisissez l'action **Tester fichier**, entrez le nom du fichier à tester, puis choisissez **Imprimer**.  
    * Pour tester la base de données, choisissez **Tester base de données**.  

### Exécuter la consolidation

Une fois les données testées, vous pouvez les transférer vers la compagnie consolidée.  

1. Connectez-vous à la compagnie consolidée.  
2. Dans le **Tableau de bord Comptable**, choisissez l'action **Exécuter la consolidation**.  
3. Renseignez les champs requis.  
4. Dans la section Filtre, définissez un filtre pour l'unité fonctionnelle ou le nom de la compagnie concerné.  
5. programmez éventuellement le rapport à exécuter à une heure spécifique.  

## Éliminer les transactions répétées

Après que vous avez consolidé toutes les compagnies, vous devez rechercher toutes les transactions enregistrées dans plusieurs compagnies, puis valider les écritures d’élimination pour les supprimer. Le traitement d'éliminations de consolidation est un processus manuel.  

Pour éliminer les transactions répétées :

1. Recherchez des transactions qui doivent être ajustées potentiellement et entrez les lignes journal général pour les éliminer.
2. Exécutez le rapport **Éliminations consolidation GL** pour évaluer l'effet des lignes journal général avant le report.
3. Reportez les transactions d'ajustement.

Le rapport **Éliminations consolidation GL**affiche une balance de vérification provisoire dans laquelle vous pouvez simuler les conséquences de l’élimination des écritures. Le rapport compare les écritures dans la compagnie consolidée avec les éliminations inscrites au journal général.

Pour qu’une unité fonctionnelle puisse être incluse dans un rapport, elle doit être définie sur la page **Unités fonctionnelles**. Le champ **Consolider** doit être sélectionné.

Une ligne est créée pour chaque compte s’affiche, selon la structure du plan comptable. Un compte n’est pas affiché si tous les montants de la ligne sont égaux à 0. Les informations suivantes sont données pour chaque compte :

* Numéro de compte.
* Nom du compte.
* Si vous avez sélectionné un ou plusieurs codes unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total excluant les éliminations et les unités fonctionnelles sélectionnées est affiché pour la compagnie consolidée. Si le champ **Code unité fonctionnelle** n’est pas renseigné, un total excluant les éliminations est affiché pour la compagnie consolidée.
* Si vous avez sélectionné un code unité fonctionnelle dans le champ **Code unité fonctionnelle** de la page de demande, un total est affiché pour les écritures importées à partir de l’unité fonctionnelle. Si le champ **Code unité fonctionnelle** n’est pas renseigné, un total est affiché pour les éliminations reportées dans la compagnie consolidée.
* Le total de la compagnie consolidée, avec toutes les unités fonctionnelles et toutes les éliminations reportées.
* Les éliminations effectuées dans la compagnie consolidée. C’est-à-dire les écritures du journal général sélectionnées sur la page de demande.
* Le texte de report copié à partir du journal général.
* Le total de la compagnie consolidée après les éliminations, si elles sont reportées.

## Exporter et importer des données consolidées entre des bases de données

Si les données d'une unité fonctionnelle se trouvent dans une autre base de données, vous devez exporter les données dans un fichier avant de les inclure dans la consolidation. Chaque compagnie doit être exportée séparément. À cette fin, utilisez le traitement par lots **Exporter fichier consolidation**.  

> [!TIP]
> Utilisez le même processus pour exporter les données consolidées qui doivent être soumises à Dynamics 365 Finance, par exemple si l’unité fonctionnelle actuel est une filiale et que la compagnie mère utilise Dynamics 365 Finance.

Après l'exécution du traitement en lot, toutes les écritures des comptes GL sont traitées. Pour chaque combinaison d'axe principal et date sélectionnés, la valeur des champs **Montant** des écritures est totalisée et exportée. La combinaison suivante des dimensions et de la date sélectionnées avec le même numéro de compte est traitée. Ensuite, les combinaisons du numéro de compte suivant sont traitées, et ainsi de suite.  

Les écritures exportées contiennent les champs suivants : **N° compte**, **Date comptabilisation** et **Montant**. Si des informations de dimensions ont également été exportées, des codes de dimension et des valeurs de dimension sont également inclus.  

1. Pour chaque ligne exportée, si le total des champs **Montant** est un débit, le numéro de compte configuré dans le champ **Compte débit consolidation** de l'unité fonctionnelle est exporté vers la ligne. Si le total est un crédit, le numéro correspondant dans le champ **Compte crédit consolidation** est exporté vers la ligne.  
2. La date utilisée pour chaque ligne exportée est la date de fin de la période ou, si le transfert est opéré chaque jour, la date du calcul.  
3. La valeur de dimension exportée pour la saisie est celle de la compagnie consolidée configurée dans le champ **Code consolidation** pour cette valeur de dimension. Si aucune valeur de dimension de compagnie consolidée n’a été entrée dans le champ **Code consolidé** à cette fin, la valeur de dimension proprement dite est exportée vers la ligne.  
4. Les fichiers XML contiennent également les taux de change devise correspondant à la période de consolidation. Ces taux sont inclus dans une section distincte au début du fichier.  

## Voir aussi

[Configurer la consolidation de la compagnie](finance-consolidated-company-reporting-setup.md)  
[Gestion des transactions intersociétés](intercompany-manage.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Exportation de vos données métier vers Excel](about-export-data.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]