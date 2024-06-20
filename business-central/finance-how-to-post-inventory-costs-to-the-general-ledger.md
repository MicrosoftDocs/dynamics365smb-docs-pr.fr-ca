---
title: Rapprocher les coûts de l'inventaire avec le grand livre
description: 'À la fin de la période comptable, une série de tâches de contrôle des coûts et d’audit doivent être effectuées pour déclarer une valeur en inventaire correcte et équilibrée au département Finances.'
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.keywords: 'warehouse, stock'
ms.search.form: 9297
ms.date: 06/16/2021
ms.author: bholtorf
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# Rapprocher les coûts de l'inventaire avec le grand livre

Lorsque vous reportez des transactions inventaire, tels que des livraisons vente, des factures achat ou des ajustements inventaire, les coûts article modifiés sont enregistrés dans les écritures valeur article. Pour refléter ces modifications de la valeur inventaire dans vos livres financiers, les coûts inventaire sont automatiquement reportés dans les comptes inventaire associés dans le grand livre. Pour chaque transaction inventaire que vous reportez, les valeurs appropriées sont reportées dans le compte inventaire, le compte ajustement et le compte variation inventaire dans le grand livre.

Le report automatique des coûts est défini par le champ **Report coûts automatique** sur la page **Configuration de l'inventaire**.

Bien que les coûts inventaire soient automatiquement reportés dans le grand livre, il est malgré tout nécessaire de vous assurer que les coûts des biens sont transmis à la transaction de vente sortante associée, notamment dans les situations où vous vendez des biens avant de facturer l'achat. Il s'agit d'un ajustement des coûts. Le coût des articles est ajusté automatiquement lorsque vous reportez des transactions article, mais vous pouvez également les ajuster manuellement. Pour en savoir plus, voir [Ajuster coûts article](inventory-how-adjust-item-costs.md).

## Pour reporter des coûts de l'inventaire manuellement

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Reporter coût de l’inventaire au GL**, puis choisissez le lien associé.
2. Reportez les coûts inventaire dans le grand livre manuellement en exécutant le traitement en lot. Lorsque vous exécutez ce traitement en lot, des écritures sont créées, basées sur des écritures valeur. Vous pouvez reporter les écritures de façon à ce qu'elles soient récapitulées par groupe de report.

> [!NOTE]  
> Lorsque vous exécutez ce traitement en lot, il se peut que vous rencontriez des erreurs liées à une configuration manquante ou une configuration de dimension incompatible. Si le traitement en lot détecte des erreurs dans la configuration de dimension, il les ignore et utilise les dimensions de l'écriture valeur. Pour toute autre erreur, le traitement en lot ignore le report des écritures valeur et les répertorie à la fin du rapport dans la section intitulée « Écritures ignorées ». Pour reporter ces écritures, vous devez corriger les erreurs.

Pour afficher la liste des erreurs avant d'exécuter le traitement par lot de validation, vous pouvez générer l'état **Valider coûts ajust. - Test**. Le rapport de test répertorie toutes les erreurs détectées durant le test de report. Vous pouvez ensuite corriger les erreurs et exécuter le traitement en lot de report des coûts inventaire sans ignorer aucune entrée.

Si vous voulez simplement afficher un aperçu des valeurs qui pourraient être reportées dans le grand livre sans réellement effectuer le report, vous pouvez exécuter le traitement en lot **Reporter le coût de l'inventaire au grand livre** sans réellement reporter les valeurs dans le grand livre. Pour ce faire, désactivez le champ **Reporter** sur la page de demande. De cette manière, lorsque vous exécutez le traitement en lot, le rapport est produit, indiquant les valeurs prêtes pour report dans le grand livre, mais elles ne sont pas reportées.

## Pour vérifier le rapprochement entre le livre inventaire et le grand livre
La page **Rapprochement inventaire avec GL** fournit ce qui suit :

- présente les différences de rapprochement en comparant ce qui est enregistré dans le grand livre et dans le livre inventaire (écritures valeur) ;
- affiche les montants coût non rapprochés des écritures valeur dans le livre inventaire comme s'ils étaient mappés aux comptes inventaire correspondants dans le grand livre, et les compare aux totaux réellement enregistrés dans les mêmes comptes du GL ;
- Reflète la structure à double écriture du grand livre en présentant visuellement les données en tant que telles. Par exemple, une écriture COGS est associée à une écriture inventaire.
- permet aux utilisateurs de consulter et de visualiser les écritures qui constituent les coûts indiqués ;
- inclut des filtres qui permettent d'affiner l'analyse par date, article et emplacement ;
- explique les motifs des différences de rapprochement dans des messages à caractère informatif.


La colonne **Nom** située à gauche de la grille répertorie les différents types de compte GL associés à l'inventaire.

Les colonnes **Inventaire**, **Inventaire (provisoire)** et **Inventaire TEC** indiquent les totaux facturés, non facturés et TEC pour chaque type de compte GL. Ceux-ci sont calculés sur la base des écritures valeur, c'est-à-dire qu'ils sont projetés sur les types de compte GL qui seront définitifs lorsqu'ils seront reportés au GL.

La colonne **Total** indique la somme (en gras) des montants des écritures valeur dans les trois colonnes d'inventaire.

La colonne **Total grand livre** indique les montants (en gras) pour chaque type de compte du grand livre existant dans le grand livre. Elles sont calculées sur la base des écritures, c'est-à-dire qu'elles représentent des coûts d'inventaire déjà reportés au GL.

La colonne **Différence** représente la différence entre la valeur des champs **Total GL** et **Total**.

En haut de la page **Rapprochement inventaire avec GL**, vous pouvez appliquer des filtres pour limiter, par exemple, la période sur laquelle vous voulez obtenir des informations.

Si vous cochez la case **Afficher avertissement** et s'il y a des différences entre les totaux inventaire et les totaux GL, l'application affiche des messages dans le champ **Avertissement** de la grille, qui expliquent la différence. Si vous cliquez sur le champ Alerte, l'application fournit des informations supplémentaires sur la signification de l'alerte.

Après avoir entré tous les filtres appropriés, choisissez l'action **Afficher la matrice**. Les données sont calculées et la page de la matrice s'affiche.

La colonne de gauche de la grille affiche les différents types de compte du grand livre associés à l'inventaire. La grille affiche ensuite les totaux facturés, non facturés (en attente) et de l'inventaire TEC pour chacun de ces types de compte. Ces totaux sont calculés à partir des écritures valeur.

Les colonnes suivantes affichent les totaux pour les mêmes types de compte, calculés à partir des écritures GL.

Choisissez le montant dans l'un des champs de Total pour afficher les écritures rapport inventaire utilisées pour calculer les totaux. Pour les totaux en inventaire, les écritures rapport inventaire sont les sommes des écritures valeur pour les articles. Pour les totaux GL, les écritures rapport inventaire sont les sommes des écritures.

## Génération de rapports sur les coûts et rapprochement avec le grand livre
D’autres rapports, des fonctions de traçage et un outil de rapprochement spécial sont à la disposition de l’auditeur ou du contrôleur chargé de rendre compte d’une valeur d’inventaire correcte et équilibrée au service financier.

Le tableau suivant décrit les valeurs.    

|**Pour**|**Voir**|  
|------------|-------------|  
|Affichez la valeur d'inventaire des articles sélectionnés, y compris les informations sur les quantités et les valeurs des augmentations et des diminutions sur une période donnée.|Rapport **Évaluation de l'inventaire**|  
|Afficher la valeur inventaire des bons de production sélectionnés dans votre inventaire TEC, telle que les quantités et valeurs de consommation, l'utilisation des capacités et de production dans les bons de production en cours.|Rapport **Évaluation de l'inventaire - TEC**|  
|Afficher la valeur d'inventaire des articles sélectionnés, y compris leur coût réel et prévu à la date spécifiée.|Rapport **Évaluation de l'inventaire - Spécification coût**|  
|Utiliser un rapport pour analyser les raisons des évolutions de coûts ou pour obtenir un aperçu du coût des marchandises vendues (CMV).|Rapport **Analyse du partage des coûts**|  

## Voir aussi  
[Gestion des coûts ajustés](finance-manage-inventory-costs.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)    
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  
[Fonctionnalités marché](ui-across-business-areas.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]