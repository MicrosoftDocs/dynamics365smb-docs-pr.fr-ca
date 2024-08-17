---
title: À propos du calcul des coûts standard
description: Un système de coûts standard détermine le coût unitaire de l’inventaire en fonction d’un coût historique ou prévu plausible.
author: brentholtorf
ms.topic: conceptual
ms.devlang: al
ms.search.form: 5841
ms.author: bholtorf
ms.date: 10/10/2023
ms.service: dynamics-365-business-central
ms.reviewer: bholtorf
---
# <a name="about-calculating-standard-cost"></a>À propos du calcul des coûts standard

De nombreuses compagnies manufacturières sélectionnent une base d'évaluation du coût standard. Ceci est également vrai pour les compagnies qui effectuent une fabrication légère, comme l'assemblage et le montage. Un système de coûts standard détermine le coût unitaire de l'inventaire en fonction d'un coût historique ou prévu plausible. L'analyse des données précédentes et futures en termes de coût peut alors offrir une base pour l'estimation des coûts standard. Ces coûts sont gelés tant que leur modification n'est pas décidée. Le coût réel lié à la production d’un produit peut varier par rapport aux coûts standard estimés. À des fins de contrôle de gestion, le coût réel est comparé au coût standard pour un article spécifique et les différences, ou *écarts*, sont identifiées et analysées.  

Des coûts standard peuvent être conservés pour les articles réapprovisionnés via l'achat, l'assemblage et la production. Pour chaque méthode de réapprovisionnement, les coûts standard peuvent inclure les éléments suivants.  

|Système de réapprovisionnement|Éléments de coût standard|  
|--------------------------|----------------------------|  
|**Achat**|Coût matière direct et coût matière supplémentaire s’il est nécessaire.|  
|**Assemblage**|Coût matière direct, coûts directs ou de main-d'œuvre fixes et frais généraux.|  
|**Ordre de fabrication**|Coût matière direct, coût de main-d'œuvre, coût de sous-traitance et frais généraux.|  

## <a name="set-up-standard-costs"></a>Configuration des coûts standard

Dans la mesure où le coût standard d'un article produit ou assemblé peut comporter plusieurs éléments de coût, dont les coûts matériels, opératoires (main d'œuvre) et de sous-traitance (coûts directs et frais généraux), il convient d'établir des coûts standard pour chacun de ces éléments.  

La tâche de comptabilité pour une compagnie de traitement d'article utilisant une méthode d'évaluation des coûts standard consiste à :  

- estimer un coût standard pour l'article fini et le configurer sur la fiche article.  
- enregistrer et affecter le coût réel des éléments de coût clés et identifier les écarts.  

Pour déterminer le coût direct d'un article fini, il convient de calculer le total des coûts composantes. Un article assemblé ou produit peut inclure des sous-ensembles, qui sont également composés de plusieurs éléments.  

Les éléments principaux d'un coût constituent le coût direct total d'un article fini :  

- Coûts matière.  
- Coût capacité.  
- Les coûts de sous-traitance pour les articles produits uniquement.  

### <a name="material-costs"></a>Coûts matière

Les coûts matière sont des coûts associés aux sous-ensembles et aux matières premières achetées. Le coût unitaire matière peut se décomposer en éléments de coût directs et indirects.  

- Le coût matière direct correspond à un montant facturé pour les matières premières achetées ou le coût de traitement d'un sous-ensemble.  
- Le coût matière indirect, ou *frais généraux*, peut correspondre à des éléments tels que les coûts de transport de l'inventaire pour l’article fini, une fois que celui-ci est produit.  

La configuration du coût matière pour les articles achetés affectant les coûts directs et indirects dépend du mode d'évaluation du stock que vous avez sélectionné pour l'article concerné. Vous configurez les informations de coût pour chacun des modes d'évaluation du stock sur la fiche article. Pour plus d'informations, reportez vous à [Enregistrer de nouveaux articles](inventory-how-register-new-items.md).

Le coût du rebut (production uniquement) est un facteur supplémentaire à prendre en compte lors du calcul du coût matière total. La mise au rebut d'une certaine quantité de matière première lorsque vous assemblez ou produisez un article entraîne généralement une augmentation de la quantité de composants requis pour produire cet article. Cela conduit à une augmentation du coût matière des composants consommés lors de la production d'un article parent. Vous configurez le coût perte pour les matières dans la nomenclature de production ou l'itinéraire.  

Le coût matière d'un article produit peut être représenté de deux façons correspondant aux bases de calcul du coût suivantes.  

|Base de calcul du coût|Calcul du coût matière|  
|----------------------------|-------------------------------|  
|Niveau unique|L'article produit est égal au coût total de tous les articles achetés ou semi-finis dans la nomenclature de production de cet article.|  
|Calcul multi-niveau|Article produit correspond à la somme du coût matière des sous-ensembles dans la nomenclature de cet article et du coût des articles achetés dans la nomenclature de production de cet article.|  

### <a name="capacity-costs"></a>Coûts capacité

Les coûts opératoires sont les coûts internes associés à la main-d'œuvre et aux machines. Vous devez configurer ces coûts pour chaque ressource (dans la gestion d'assemblage) et atelier ou unité de production sur l'itinéraire (dans la production). Comme pour les matières, vous pouvez identifier des éléments de coût capacité directs et indirects. Par exemple, le coût direct pour un atelier peut correspondre au taux usine établi pour exécuter une fonction spécifique. Le coût indirect d’un atelier peut correspondre à certaines dépenses générales de l’usine, comme l’éclairage, le chauffage, etc. Comme avec les coûts matière, vous pouvez exprimer l'utilisation fixe de capacité en pourcentage du coût indirect ou frais généraux fixes.  

La configuration des coûts opératoires des articles assemblés est constituée des éléments suivants :  

- Coût unitaire direct et indirect de la ressource.  
- Type d'utilisation fixe ou direct des ressources.  

La configuration des coûts opératoires des articles produits est constituée des éléments suivants :  

- Coût unitaire direct et indirect de l'atelier ou de l'unité de production.  
- Configuration du délai et de la taille lot  

Pour calculer le coût capacité standard, vous devez déterminer les délais standard requis pour effectuer des opérations sur des unités de production et des ateliers. Le temps total nécessaire à l'exécution d'une opération comprend généralement le délai lié à la configuration, à l'exécution, ainsi que le délai d'attente et de déplacement.  

Vous configurez les taux établis pour chaque type de délai pour chaque unité de production ou atelier dans un itinéraire individuel.  

> [!NOTE]  
>  Si les délais d'exécution affectent chaque unité de mesure d'article produit, les délais de configuration affectent chaque lot. Aussi, vous devez distribuer au prorata le délai de configuration de l'itinéraire pour chaque opération par rapport à la taille lot. Vous spécifiez la taille lot dans le champ correspondant sur le raccourci **Réapprovisionnement** de la page **Fiche article**.  

Pour spécifier le délai de configuration dans l'itinéraire à des fins de planification, sans toutefois inclure cette dépense dans le calcul des coûts standard, désactivez le champ **Inclure coût préparation** de la page **Configuration de la fabrication**.  

Sur une base niveau unique, il s'agit du coût de main-d'œuvre requis pour produire l'article produit fini et spécifié dans l'itinéraire de l'article de production. Sur une base multiniveau, il s'agit du coût capacité spécifié pour chaque article produit individuellement inclus dans la nomenclature de l'article parent.  

### <a name="subcontractor-costs"></a>Coûts de sous-traitance

Les coûts de sous-traitance sont les objets de coûts aux services assurés par des sous-traitants ou fournisseurs externes d'une compagnie. Semblables aux coûts matière et opératoires, les coûts de sous-traitance peuvent se décomposer en coûts directs et frais généraux. Le coût de sous-traitance direct correspond à la charge réelle pour chaque unité de services fournie. Par exemple, les frais de sous-traitance généraux peuvent représenter les coûts de fret et de gestion engagés par la compagnie avec une commande sous-traitée.  

Parce que la sous-traitance correspond à une capacité externalisée, vous configurez les coûts liés à la sous-traitance de services directs et indirects dans la fiche atelier représentant l'opération de sous-traitance.  

## <a name="update-standard-costs"></a>Mise à jour des coûts standard

Pour mettre à jour ou calculer le coût standard d'éléments d'assemblage, utilisez la fonction de la fiche article.  

Le processus de mise à jour ou de calcul des coûts standard comprend généralement les tâches suivantes :  

1.  Mise à jour des coûts aux niveaux des composantes et de la capacité. Pour plus d'informations, consultez les traitements en lot **Suggérer un coût standard d'article** et **Suggérer le coût standard de la capacité**.  
2.  Consolidation et calcul multiniveau des coûts des composantes et de capacité pour calculer le coût d'assemblage ou de fabrication total des articles. Pour plus d’informations, consultez [Pour calculer le coût standard d’un élément d’assemblage](assembly-how-work-assembly-boms.md#to-calculate-the-standard-cost-of-an-assembly-item).  
3.  Application des coûts standard entrés lorsque vous exécutez les traitements par lots précédents. Les coûts standard n’entrent en vigueur que lorsqu’ils sont mis en œuvre. Utilisez le traitement en lot **Appliquer les modifications de coût standard**, qui met à jour les modifications du coût standard sur les articles en fonction de ceux figurant dans la table Feuille coût standard.  
4.  Application des modifications pour mettre à jour le champ **Coût unitaire** sur la fiche article et effectuer une réévaluation du stock. Pour plus d'informations, voir [Réévaluer l'inventaire](inventory-how-revalue-inventory.md).

## <a name="use-batch-jobs-to-update-standard-costs"></a>Utiliser des traitements en lot pour mettre à jour les coûts standard
Les sections suivantes décrivent les traitements en lot que vous pouvez utiliser pour mettre à jour les coûts standard.
### <a name="suggest-item-standard-cost"></a>Suggérer un coût standard d'article

 Crée des propositions pour modifier les coûts et les partages de coûts standard sur les fiches article. Lorsque le traitement en lot est terminé, vous pouvez en visualiser le résultat dans la fenêtre Feuille coût standard.

> [!NOTE]  
> Ce traitement en lot est prévu uniquement pour les articles achetés. Si vous souhaitez mettre à jour un article avec une nomenclature de production ou d’assemblage, vous devez d’abord renseigner la feuille avec toutes les composantes, avant d’exécuter le traitement en lot Cumuler le coût standard.

Ce traitement en lot ne crée que des propositions. Il n’applique pas les modifications suggérées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c’est-à-dire les mettre à jour dans les fiches article et les insérer dans le journal réévaluation, sélectionnez sur Appliquer les modifications de coût standard dans la fenêtre Feuille coût standard.
#### <a name="options"></a>Options

**Coût standard** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre le coût standard à jour. Vous pouvez également sélectionner une méthode arrondissement pour le nouveau coût standard. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

**% coût indirect** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre le % coût indirect à jour. Vous pouvez également sélectionner une méthode arrondissement pour le nouveau coût indirect %. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

**Frais généraux** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre les frais généraux à jour. Vous pouvez également sélectionner une méthode arrondissement pour les nouveaux frais généraux. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

### <a name="suggest-workmach-ctr-std-cost"></a>Suggérer un coût standard de travail/d'unité de production

Crée des propositions pour modifier les coûts et les partages de coûts standard sur les fiches atelier, unité de production ou ressource. Lorsque le traitement en lot est terminé, vous pouvez en visualiser le résultat dans la fenêtre **Feuille coût standard**.

Ce traitement en lot ne crée que des propositions. Il n’applique pas les modifications suggérées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c’est-à-dire les mettre à jour dans les fiches atelier/unité de production et ressource et les insérer dans la fenêtre Journal réévaluation, sélectionnez **Appliquer les modifications de coût standard** dans la fenêtre **Feuille coût standard**.

Lorsque vous avez exécuté le traitement en lot et que vous souhaitez voir l’impact sur vos départements Production et Assemblage, vous exécutez le traitement en lot **Cumuler le coût standard** pour mettre à jour les coûts standard des ateliers, unités de production, ressources d’assemblage, nomenclatures de production et nomenclatures d’assemblage.
#### <a name="options-1"></a>Options
**Coût standard** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre le coût standard à jour. Vous pouvez également sélectionner une **méthode arrondissement** pour le nouveau coût standard. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

**% coût indirect** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre le % coût indirect à jour. Vous pouvez également sélectionner une méthode arrondissement pour le nouveau coût indirect %. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

**Frais généraux** : Saisissez le facteur appliqué que vous souhaitez utiliser pour mettre les frais généraux à jour. Vous pouvez également sélectionner une méthode arrondissement pour les nouveaux frais généraux. Vous devez renseigner le champ à l’aide d’une valeur décimale pour l’augmentation du pourcentage, par exemple 1,1.

### <a name="post-inventory-cost-to-gl"></a>Reporter coût de l’inventaire au GL

 Enregistre les changements de quantité et de valeur en inventaire dans les écritures article et les écritures valeur lorsque vous reportez des transactions inventaire, telles que des livraisons vente ou des réceptions achat.

Sauf si vous avez coché la case **Report coûts automatique** dans la fenêtre **Configuration de l'inventaire**, les coûts inventaire ne sont pas enregistrés de façon dynamique dans le grand livre. Par ailleurs, la valeur sortie inventaire n’est pas calculée en relation avec une vente. Par conséquent, vous devez effectuer manuellement le report dans le grand livre en exécutant le traitement en lot **Reporter le coût de l'inventaire au grand livre** pour mettre à jour le grand livre et éventuellement imprimer un rapport des écritures valeur reportées.

Le traitement en lot utilise des écritures valeur comme base. Pour calculer la valeur à reporter, il utilise la différence entre les champs **Coût indiqué (réel)** et **Coût reporté au GL** dans les écritures valeur. Si vous avez coché la case **Report coût prévu au GL** dans la fenêtre **Configuration de l'inventaire**, le traitement en lot reporte également la différence entre les champs **Coût indiqué (prévu)** et **Coût prévu reporté au GL** sur les comptes provisoires dans le grand livre.

> [!NOTE]
> Si vous n’avez pas coché la case **Report coût prévu au GL** dans la fenêtre **Configuration de l'inventaire**, la dernière section du rapport répertorie les écritures valeur qui sont ignorées, car elles représentent des coûts prévus.

> [!NOTE] 
> Si le traitement en lot rencontre une erreur impliquant des dimensions ou une configuration de dimension, il ignore cette erreur et reporte l’écriture dans le grand livre en utilisant les dimensions de l’écriture valeur.

Pour vous assurer que le traitement en lot ne rencontre pas d’erreur, vous pouvez exécuter le rapport **Reporter le coût de l'inventaire au grand livre - Test** pour consulter toutes les erreurs possibles. Vous pouvez alors corriger les erreurs et exécuter le traitement en lot **Reporter le coût de l'inventaire au grand livre**, en sachant qu'il traite toutes les écritures.
 
> [!IMPORTANT]  
> Avant d’utiliser ce traitement en lot, vous devez exécuter le traitement en lot **Ajuster coûts : Écr. article**. Ainsi, lorsque vous exécutez ce traitement en lot, les coûts reportés dans le grand livre sont à jour.
#### <a name="options-2"></a>Options

|Option  |Désignation  |
|--------------|---------|
|**Méthode de report**|Le traitement en lot peut reporter la valeur inventaire dans le grand livre par groupe de report ou par écriture reportée. Si vous reportez par écriture, vous obtenez une spécification détaillée de l’influence de l'inventaire sur le grand livre, mais vous obtenez également de nombreuses écritures. Si vous reportez par groupe de report, le traitement en lot crée une écriture par date de report par combinaison de groupes de report. Cela signifie qu’une écriture est créée pour chaque combinaison de date de report, groupe de report marché, groupe de report produit, groupe de report inventaire et code d'emplacement. En outre, le traitement en lot crée des écritures séparées pour les coûts de signe différent.|
|**N° document**|Dans ce champ, vous pouvez entrer un numéro de document si vous avez choisi l’option de Report par groupe de report inventaire. Le numéro de document est affiché sur les écritures reportées.|
|**Valider**|Sélectionnez ce champ si vous souhaitez que le traitement en lot effectue un report automatique dans le grand livre. Si vous choisissez de ne pas reporter le coût inventaire dans le grand livre, le traitement en lot n’imprimera qu’un rapport de test présentant les valeurs qui peuvent être reportées dans le grand livre et le rapport indiquera : **Rapport de test (non reporté)**.|

### <a name="roll-up-standard-cost"></a>Cumuler le coût standard

Calcule les coûts standard des articles assemblés et fabriqués. Ceux-ci sont influencés par la modification des coûts standard des composantes proposée par le traitement en lot **Proposer coût standard article**. En outre, ceux-ci sont influencés par la modification du coût standard de la capacité de production et des ressources d’assemblage proposée par le traitement en lot **Prop. coût std atelier/unité de prod.**.

Lorsque vous avez exécuté l’un ou l’autre de ces traitements en lot (ou les deux) et que vous procédez au cumul, toutes les modifications des coûts standard dans la feuille sont introduites dans les nomenclatures de production ou d’assemblage associées et les coûts sont appliqués à chaque niveau de nomenclature.

> [!NOTE] 
> Cette fonction ne cumule le coût standard que sur les fiches article, pas sur les fiches unité de stock.

Ce traitement en lot ne crée que des propositions. Il n’applique pas les modifications suggérées. Si les propositions vous conviennent et que vous souhaitez les appliquer, c’est-à-dire les mettre à jour dans les fiches article et les insérer dans la fenêtre **Journal réévaluation**, vous pouvez utiliser le traitement en lot **Appliquer la modification de coût standard**. Vous accédez à ce traitement en lot à partir de la fenêtre **Feuille coût standard**.
#### <a name="options-3"></a>Options

**Date de calcul** : Saisissez la date qui s’applique à la version de la nomenclature de production pour laquelle vous souhaitez faire remonter l’information.
 
### <a name="implement-standard-cost-change"></a>Appliquer la modification de coût standard

Mettez à jour les modifications du coût standard dans la table **Article** en fonction de celles figurant dans la table **Feuille coût standard**. Les propositions de modification des coûts standard peuvent être créées avec le traitement en lot **Proposer coût standard article** et/ou **Prop. coût std atelier/unité de prod.**, et elles peuvent également être modifiées. La valeur de tous les champs de la proposition de modification de coût standard est transférée. Lorsque vous appliquez des propositions de modification des coûts standard, vous pouvez les afficher dans la fiche article et/ou dans les fiches atelier/unité de production. Un journal de réévaluation est également créé pour vous permettre de mettre à jour la valeur du stock existant.
#### <a name="options-4"></a>Options

**Date de report** : Saisissez la date d’entrée en vigueur de la réévaluation.

**N° document** : Saisissez le numéro des lignes journal réévaluation. Si une série de nombres est définie sur le nom lot journal article, le numéro du document suit les écritures créées par le report du journal réévaluation. Sinon, vous pouvez saisir un numéro manuellement.

**Modèle journal article** : Saisissez le nom du modèle journal réévaluation.

**Nom lot journal article** : saisissez le nom du journal réévaluation réelle

Sélectionnez **OK** pour démarrer le traitement en lot. Si vous ne souhaitez pas exécuter le traitement en lot immédiatement, sélectionnez **Annuler** pour fermer la fenêtre.

## <a name="see-also"></a>Voir aussi .

[Détails de conception : méthodes de calcul des coûts](design-details-costing-methods.md)  
[Mise à jour des coûts standard](finance-how-to-update-standard-costs.md)  
[Détails de conception : stock évaluation stock](design-details-inventory-costing.md)  
[Utilisation des nomenclatures d’assemblage](assembly-how-work-assembly-boms.md)  
[Créer des nomenclatures de production](production-how-to-create-production-boms.md)  
[Utiliser les nomenclatures](inventory-how-work-BOMs.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
