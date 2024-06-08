---
title: Comprendre le plan comptable
description: 'Décrit le plan comptable, comment le configurer et comment l’utiliser.'
author: kennienp
ms.topic: conceptual
ms.search.keywords: 'analysis, history, track'
ms.search.form: '18, 20, 37, 65, 99, 312, 314, 313, 395, 552, 569, 570, 634, 790, 791, 1158'
ms.date: 04/17/2024
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
---

# <a name="understanding-the-chart-of-accounts"></a>Comprendre le plan comptable

Un plan comptable (COA) sert de répertoire complet des comptes financiers et de leurs numéros de référence correspondants. Un COA comprend généralement deux catégories principales de comptes :

- Comptes de bilan : ces comptes suivent les actifs, les dettes et la valeur nette de votre compagnie.
- Comptes d'état de résultat : ces comptes enregistrent les revenus provenant de diverses sources et suivent également les dépenses.

Les comptes de bilan sont en outre classés en trois groupes :

1. Comptes d’actifs : ces comptes suivent toutes les ressources précieuses appartenant à votre compagnie.
1. Comptes de passif : ils enregistrent les dettes de votre compagnie.
1. Comptes de capitaux propres : représentent la valeur résiduelle de l’entreprise après soustraction des passifs des actifs.

Les comptes de revenus sont divisés en deux groupes :

1. Comptes de revenus : ces comptes capturent les revenus de votre compagnie provenant de diverses sources.
1. Comptes de dépenses : ces comptes capturent toutes les dépenses de votre compagnie.

Utilisez le COA pour enregistrer les transactions dans le grand livre général de votre organisation. Chaque compte possède généralement un identificateur (numéro de compte) et une légende ou un en-tête descriptif, et ils sont systématiquement codés en fonction de leur type de compte.

[!INCLUDE[prod_short](includes/prod_short.md)] inclut un plan comptable standard prêt à prendre en charge votre société.

La composition du plan comptable de votre compagnie est une décision stratégique prise par votre direction (ou par la réglementation propre à chaque pays). Cela varie en fonction du secteur d’activité, du modèle commercial et de la structure financière de votre compagnie. Par exemple, en fonction de votre secteur d’activité, vous pouvez disposer de comptes d’actifs spécifiques adaptés aux opérations et aux besoins uniques de votre compagnie :

* Une entreprise de vente au détail peut mettre l’accent sur l'inventaire et les comptes clients.
* Une compagnie technologique peut se concentrer sur des actifs incorporels tels que des brevets et des logiciels.
* Une usine de fabrication suivrait les immobilisations et les fournitures.

## <a name="the-chart-of-accounts-page"></a>Page Plan comptable

Le plan comptable affiche tous les comptes généraux. Vous pouvez effectuer les opérations suivantes à partir du plan comptable :  

* Afficher les rapports qui affichent les écritures et les soldes.  
* Fermez votre état des résultats.  
* Ouvrez la fiche Compte GL où vous pouvez ajouter ou modifier des paramètres.  
* Consulter la liste des groupes de report pour ce compte.
* Afficher les soldes débit et crédit d’un seul compte.

Vous pouvez ajouter, modifier ou supprimer des comptes généraux. Toutefois, pour éviter les différences, vous ne pouvez pas supprimer un compte GL si ses données sont utilisées dans le plan comptable. Pour éviter aussi la suppression accidentelle des comptes en périodes sensibles. Pour en savoir plus sur la protection des comptes contre la suppression, accédez à [Supprimer des comptes](finance-setup-chart-accounts.md#delete-accounts).  

## <a name="the-code-hierarchy-in-gl-accounts"></a>La hiérarchie des codes dans les comptes GL

Les entreprises créent généralement une structure hiérarchique dans les codes de comptes GL pour refléter leur place dans le plan comptable. Par exemple, dans certaines implémentations, les codes de compte GL commençant par **1** désignent les comptes d’actifs, tandis que les codes de compte GL commençant par 3 désignent les comptes de capitaux propres. Dans certaines régions, il existe des réglementations locales concernant l’utilisation d’un plan comptable standard. Pour aider les utilisateurs à comprendre cette hiérarchie sans avoir besoin de connaître la structure du code interne, vous pouvez définir des en-têtes et des sous-totaux dans votre plan comptable qui encapsulent ces structures internes.

## <a name="designing-your-chart-of-accounts"></a>Concevoir votre plan comptable

Chaque ligne du plan comptable est un compte GL de l'un des types suivants :

* Report (les journaux peuvent reporter des lignes sur ces comptes)
* En-tête (définit une rubrique globale dans le plan comptable)
* Total (définit une formule pour un sous-total dans le plan comptable)
* Début Total (définit un en-tête de début pour un sous-total dans le plan comptable. Toutes les lignes suivantes jusqu’à une ligne Fin-Total sont en décalées)
* Total final (définit un en-tête de fin pour un sous-total et la formule correspondante dans le plan comptable. Toutes les lignes suivantes après cette ligne Fin-Total mise en retrait négatif)

Un plan comptable minimaliste peut être constitué uniquement de lignes de comptes de report. Vous utilisez les quatre autres types pour définir comment le plan comptable affiche également un état financier avec des en-têtes et des sous-totaux. Les comptes de totalisation sont fréquemment utilisés dans les rapports financiers.

> [!TIP]
> Si vous utilisez des types de comptes autres que **Report** dans votre plan comptable, vous pouvez définir différentes vues pour afficher les comptes de report "bruts" sans les types de comptes de type rapport pour la totalisation. et les titres. Par exemple, Afficher uniquement les comptes de report et Masquer les comptes bloqués.

## <a name="use-dimensions-to-simplify-your-chart-of-accounts"></a>Utilisez des dimensions pour simplifier votre plan comptable

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur les documents, tels que les documents de vente. Les dimensions peuvent, par exemple, indiquer de quel projet ou département provient une écriture. Ainsi, au lieu de configurer des comptes GL pour chaque service et projet, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer un plan comptable compliqué.

Pour en savoir plus sur les dimensions, consultez [Utiliser les dimensions](finance-dimensions.md).

## <a name="get-a-quick-overview-of-your-finances"></a>Obtenez un aperçu rapide de vos finances

La page **Plan comptable** affiche les comptes dans une liste hiérarchique qui offre un accès rapide aux informations clés pour chaque compte. Cependant, la liste est statique et si vous avez un grand nombre de comptes, vous devrez peut-être défiler pour afficher les différents comptes. Si vous souhaitez simplement un aperçu rapide des éléments de base, tels que les variations nettes et les soldes, la page **Vue d’ensemble du plan comptable** est une alternative utile. La disposition des colonnes sur la page est la même la page **Plan comptable** (mais avec moins de colonnes), facile à comprendre. Vous pouvez développer ou réduire les niveaux hiérarchiques. Pour faciliter le passage d’une page à l’autre, la page **Vue d’ensemble du plan comptable** est disponible à partir de la page **Plan comptable**.

## <a name="access-to-create-and-edit-the-chart-of-accounts"></a>Accès pour créer et modifier les plan comptables

Dans une petite organisation, comme la compagnie de démonstration CRONUS, la plupart des utilisateurs peuvent modifier le plan comptable, à l’exception des utilisateurs disposant d’une licence MEMBRE D’ÉQUIPE. Cependant, les grandes organisations utilisent généralement des rôles et des autorisations d’utilisation pour limiter l’accès pour modifier le plan comptable. Si vous êtes administrateur ou si vous avez le rôle de Gestionnaire d’activité ou de Comptable, vous pouvez contrôler les autorisations utilisateur pour vous assurer que les bonnes personnes ont accès aux tables pertinentes. Pour plus d’informations, consultez [Pour afficher ou modifier les autorisations d’un utilisateur](ui-define-granular-permissions.md#get-an-overview-of-a-users-permissions).  


<!-- ## Standard chart of accounts in different regions
Uncomment when we have more examples added to our localization documentation

Some regions have defined standards for the chart of accounts structure you should use in your company. 

Here are some examples of such standards that have been implemented in localized versions of [!INCLUDE[prod_short](includes/prod_short.md)]:

* [Standard chart of accounts in Denmark](localfunctionality/denmark/how-to-set-up-standard-coa.md)
-->

## <a name="chart-of-accounts-best-practices"></a>Bonnes pratiques en matière de plan comptable

Voici quelques bonnes pratiques que vous pourriez prendre en compte lorsque vous développez et maintenez vos plans comptables :

* Composez le plan comptable de votre compagnie pour répondre aux besoins de rapport financier permettant à votre direction de prendre des décisions stratégiques.
* Envisagez de commencer simplement avec moins de comptes GL. Vous pouvez toujours ajouter des comptes plus détaillés si nécessaire.
* Définissez des en-têtes et des sous-totaux dans votre plan comptable qui résument les structures internes des comptes GL.
* Utilisez des dimensions pour simplifier votre plan comptable. Ne disposez pas de comptes GL spécifiques pour chaque produit ou département.
* Ajoutez de nouveaux comptes GL au fur et à mesure de leur arrivée, mais supprimez les comptes de votre plan comptable uniquement à la fin de votre période de financement.

## <a name="see-also"></a>Voir aussi .

[Configurer ou modifier le plan comptable](finance-setup-chart-accounts.md)  
[Comprendre le grand livre](finance-general-ledger.md)
[Analyses financières](bi.md)  
[Vue d’ensemble de Finances](finance.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
