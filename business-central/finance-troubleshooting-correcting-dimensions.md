---
title: Dépannage et correction des dimensions
description: Découvrez comment dépanner les erreurs de dimensions classiques et comment corriger les dimensions après leur utilisation sur des transactions reportées.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'dimension, correction, correct, business intelligence'
ms.search.form: '116, 540, 2588'
ms.date: 04/26/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# Dépannage et correction des dimensions

Les rapports financiers et les vues d′analyse reposent souvent sur les données des dimensions. Malgré les garanties disponibles, il se produit parfois une erreur pouvant entraîner des imprécisions. Cet article décrit certaines erreurs classiques et explique comment corriger les affectations de dimensions sur les transactions reportées afin que les rapports financiers soient précis.

## Résolution des erreurs liées aux dimensions

Lorsque vous reportez des documents ou des lignes journal contenant des dimensions, diverses erreurs peuvent se produire. Cependant, ils sont généralement liés à une configuration ou une affectation de dimension incorrecte.

> [!NOTE]
> Dans la liste suivante des messages d'erreur potentielle, les codes *%X*sont des espaces réservés pour les variables de données qui le message réel contient dans l'interface utilisateur selon le contexte. Par exemple, *%1 %2 est bloqué.* pourrait s'afficher dans l'interface utilisateur comme « La ZONE du code de dimension est bloquée ».  

|Problème|Message d'erreur|Solution possible|
|-----|-------------|-----------------|
|Dimension bloquée|%1 %2 est bloqué(e).|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la dimension bloquée et débloquez-la.<br />- Supprimez la ligne ensemble de dimensions pour la dimension bloquée.|
|Dimension supprimée|%1 %2 est introuvable.|- Restaurez la dimension manquante.<br />- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la dimension manquante et ajoutez-la.<br />- Supprimez la ligne ensemble de dimensions pour la dimension manquante.|
|Valeur de dimension bloquée|%1 %2 - %3 est bloqué.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la valeur de dimension bloquée et débloquez-la.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension bloquée.|
|Valeur de dimension supprimée|    %1 pour %2 est manquant.|- Restaurez la valeur de dimension manquante.<br />- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la valeur de dimension manquante et ajoutez-la.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension manquante.|
|Valeur de dimension interdite|Le type de valeur de dimension pour %1 %2 - %3 ne doit pas être %4.|- Modifiez le champ **Type de valeur de dimension** sur la page **Valeurs de dimension** avec **Standard** ou **Début total**.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension bloquée.|
|Combinaison de dimensions bloquée|Les dimensions %1 et %2 ne peuvent pas être utilisées ensemble.|-Recherchez les documents non validés contenant l’ensemble de dimensions avec la valeur du croisement analytique bloqué et débloquez-le.<br />- Modifiez une des lignes d'ensembles d'autorisation en conflit pour la combinaison de dimensions.|
|Combinaison de valeurs de dimension bloquée|Les combinaisons de dimensions %1 - %2 et %3 - %4 ne peuvent pas être utilisées ensemble.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la combinaison de valeurs de dimensions bloquée et débloquez-la.<br />- Modifiez une des lignes d'ensembles d'autorisation en conflit pour la combinaison de valeurs de dimension.|
|Code de valeur de dimension vide pour la dimension par défaut où le champ **Report valeur** contient **Code obligatoire**|- Sélectionnez un %1 pour le %2 %3.<br />- Sélectionnez un %1 pour le %2 %3 pour %4 %5.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez une valeur de dimension non vide pour la dimension en conflit dans l'ensemble de dimensions.|
|Code de valeur de dimension erroné pour la dimension par défaut où le champ **Report valeur** contient **Même code**|- Sélectionnez %1 %2 pour le %3 %4.<br />- Sélectionnez %1 %2 pour le %3 %4 pour %5 %6.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez la valeur de dimension requise pour la dimension en conflit dans l'ensemble de dimensions.|
|Code de valeur de dimension non vide pour la dimension par défaut vide où le champ **Report valeur** contient **Même code**|-%1 %2 doit être vierge.<br />-%1 %2 doit être vierge pour %3 %4.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez un code de valeur de dimension vide pour la dimension en conflit dans l'ensemble de dimensions.|
|Valeur de dimension inattendue pour la dimension par défaut où le champ **Report valeur** contient **Pas de code**|-%1 %2 ne doit pas être mentionné.<br />- %1 %2 ne doit pas être mentionné pour %3 %4.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Supprimez la ligne en conflit de l'ensemble de dimensions.|
|Une correction de dimension ne se termine pas correctement.||-Choisissez **Réinitialiser** pour rétablir la correction à un état brouillon. Cela réinitialise les modifications et vous pouvez réexécuter la correction.|

## Modification des affectations de dimension après le report

Si vous découvrez une dimension incorrecte sur les écritures GL reportées, vous pouvez corriger les valeurs de dimension et mettre à jour vos vues d’analyse. La correction vous aide à assurer la précision de vos analyses et rapports financiers.

> [!IMPORTANT]
> Les fonctionnalités de correction des dimensions visent uniquement à rendre les rapports financiers précis. Les corrections de dimensions s′appliquent uniquement aux écritures GL. Ils ne modifient pas les dimensions affectées aux écritures d'autres livres pour la même transaction. Un problème de correspondance existe entre les dimensions affectées dans le grand livre et les grands livres auxiliaires.

### Configuration des corrections de dimensions

Il y a deux choses à prendre en compte lors de la configuration des corrections de dimension :

* Y a-t-il des dimensions dont vous ne souhaitez pas autoriser la modification? Sur la page **Paramètres de correction de dimensions**, spécifiez les dimensions que vous souhaitez bloquer pour les modifications.
* Qui peut changer les dimensions? Pour autoriser les utilisateurs à apporter des modifications, attribuez l'autorisation **CORRECTION AXE D365** aux utilisateurs. Les autorisations leur permettent de créer des corrections de dimensions, de les exécuter et de les annuler si nécessaire. Ils peuvent également spécifier des dimensions bloquées. Pour en savoir plus, voir [Attribuer des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md). 

### Correction d’une dimension

Vous pouvez sélectionner manuellement une ou plusieurs écritures ou utiliser des filtres pour sélectionner des séries d'entrées. Si nécessaire, vous pouvez également ajouter ou supprimer des dimensions. 

1. Pour démarrer une correction de dimensions, utilisez l'une des pages suivantes :

    * Sur la page **GL/Registre**, en sélectionnant un registre, puis en choisissant l'action **Corriger les dimensions**. Cette action lance une correction pour les entrées dans le registre sélectionné.
    * Sur la page **Écritures**, en choisissant l'action **Correction de dimensions**. 

2. Dans le champ **Description**, entrez les informations sur la modification. D'autres personnes pourraient utiliser ces informations plus tard pour comprendre ce qui a été fait.
3. Sur le Raccourci **Écritures sélectionnées**, choisissez les entrées appropriées.

    > [!IMPORTANT]
    > Lorsque vous modifiez une sélection, les valeurs du Raccourci **Modifications de correction de dimensions** sont réinitialisées. Par conséquent, sélectionnez toujours les entrées avant de spécifier les changements de valeur de dimensions.

   Le tableau suivant décrit les options.

   |Option  |Description  |
   |---------|---------|
   |Ajouter les écritures associées     |Ajoutez les écritures GL qui sont dans le même registre GL.|   
   |Ajouter par filtre     |Utilisez des critères de filtre lors de l'ajout d'écritures GL.|
   |Sélection manuelle     |Sélectionnez des écritures GL spécifiques.         |
   |Ajouter par dimensions     |Filtrez les écritures GL par dimensions.         |
   |Supprimer des écritures     |Désélectionnez des écritures GL.         |
   |Gérer les critères de sélection     |Suivez le processus de sélection et annulez les sélections si nécessaire.         |

4. Sur le Raccourci **Modifications de correction de dimensions**, choisissez la dimension analytique que vous souhaitez modifier dans le champ **Code de dimension** et la nouvelle valeur dans le champ **Nouveau code de valeur de dimension**.
5. Pour valider la correction, choisissez **Valider les changements de dimensions**. Pour plus d′informations, voir [Validation des corrections de dimensions](finance-troubleshooting-correcting-dimensions.md#validating-dimension-corrections).
6. Choisir **Exécuter**.

### Validation des corrections de dimensions

Avant d'exécuter une correction, il est conseillé de la valider d'abord. La validation vérifie les restrictions sur le report des valeurs pour les comptes du grand livre, les restrictions pour les dimensions et si les valeurs des dimensions sont bloquées. Lors de la validation, l'état de la correction est défini sur **Validation en cours**. Après avoir validé une correction, le résultat s'affiche dans le champ **État de validation**. Si des erreurs ont été trouvées, vous pouvez utiliser l'action **Afficher les erreurs** pour les enquêter. Après avoir corrigé une erreur, vous devez utiliser l'action **Rouvrir** pour exécuter la correction ou une nouvelle validation.

Vous pouvez soit exécuter une correction immédiatement, soit la programmer pour une exécution ultérieure. Si vous exécutez des corrections sur un jeu de données volumineux, nous vous recommandons de le programmer pour qu’il s’exécute en dehors des heures ouvrables. Pour plus d′informations, voir [Corrections de dimensions sur des jeux de données volumineux](finance-troubleshooting-correcting-dimensions.md#dimension-corrections-on-large-data-sets).

### Annuler une correction

Après avoir corrigé une dimension, si vous n'aimez pas ce que vous voyez, vous pouvez utiliser l'action **Annuler** pour réinitialiser la valeur précédente. Cependant, vous ne pouvez annuler que la correction la plus récente. Avant d’annuler une correction, vous pouvez valider les modifications que l’action d'annulation apporte. Par exemple, la validation est utile si les restrictions de dimensions ont changé après la correction.

Si l’action Annuler n’est pas disponible, par exemple parce que vous avez effectué de nombreuses corrections, vous pouvez utiliser l’action **Copier dans le brouillon** pour démarrer une nouvelle correction pour les mêmes entrées.

### Corrections de dimensions sur des jeux de données volumineux

Soyez prudent lorsque vous corrigez de grands ensembles d'entrées, par exemple, des ensembles comprenant plus de 10 000 entrées. Si vous le pouvez, nous vous recommandons d'utiliser les filtres pour exécuter les corrections sur des jeux de données plus petits. Il est également judicieux d'exécuter des corrections en dehors des heures normales de bureau. 

### Utiliser des vues d’analyse avec des corrections de dimensions

Si **Mise à jour lors du report** est activé pour une vue d'analyse, [!INCLUDE[prod_short](includes/prod_short.md)] peut mettre à jour la vue lorsque les documents et les journaux sont reportés. Vous pouvez également mettre à jour les vues avec ce paramètre activé avec les résultats des corrections de dimensions. Pour ce faire, activez le bouton de basculement **Mettre à jour les vues d'analyse**. La mise à jour des vues d’analyse peut affecter sur les performances, en particulier pour les grands jeux de données, c’est pourquoi nous vous recommandons de mettre à jour les vues d’analyse uniquement pour les petits jeux de données.  

### Affichage des corrections de dimensions historiques

Si une écriture GL a été corrigée, vous pouvez étudier la modification en utilisant l'action **Historique des corrections de dimensions**.

### Traitement des corrections incomplètes

Si une correction ne se termine pas, un avertissement s’affiche sur la carte de correction. Si cela se produit, vous pouvez utiliser l'action **Réinitialiser** pour rétablir la correction à un état de brouillon et annuler les modifications. Vous pouvez ensuite exécuter à nouveau la correction.

> [!NOTE]
> La réinitialisation d'une correction incomplète n'affectera pas les mises à jour des vues d'analyse, car celles-ci se produisent à la fin du processus de correction.

### Utiliser la comptabilité analytique avec les écritures GL corrigées

Une fois les dimensions corrigés, vos données pour la comptabilité analytique sont désynchronisées. La comptabilité analytique utilise des dimensions pour agréger les montants des centres de coûts et des objets de coûts, et pour exécuter les affectations de coûts. La modification des dimensions pour les écritures GL signifie probablement que vous devriez réexécuter vos modèles de comptabilité analytique. En fonction des données mises à jour et de la manière dont vos capacités de comptabilité analytique sont configurées, vous devrez peut-être :

* Supprimez seulement quelques registres de coûts et réexécutez les affectations.
* Supprimez tout et réexécutez tous vos modèles.

Vous devez identifier manuellement où les corrections de dimensions ont un impact sur la comptabilité analytique et où des mises à jour sont nécessaires. [!INCLUDE[prod_short](includes/prod_short.md)] ne propose pas actuellement de moyen automatisé de le faire.

## Voir aussi .

[Utilisation des dimensions](finance-dimensions.md)  
[Analyser des données par dimensions](bi-how-analyze-data-dimension.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
