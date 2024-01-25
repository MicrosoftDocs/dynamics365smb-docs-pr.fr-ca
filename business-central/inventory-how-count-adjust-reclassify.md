---
title: 'Inventaire, ajustement et reclassement de l''inventaire'
description: Découvrez comment effectuer un comptage physique et faire des ajustements et des reclassements.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics-365-business-central
ms.topic: how-to
ms.date: 12/20/2022
ms.custom: bap-template
---
# Comptabiliser, ajuster et reclasser l'inventaire avec les journaux

Comptez physiquement tous les articles dans l’inventaire pour vous assurer que vos quantités sont correctes. Certaines entreprises effectuent un inventaire physique annuel, tandis que d’autres comptent plus souvent tous les articles ou seulement certains d’entre eux. Après avoir compté les articles, utilisez les journaux pour reporter les quantités réelles dans le grand livre. Par exemple, lorsque vous évaluez l’inventaire à la fin d’une période.

Pour compter certains articles plus souvent que d’autres, peut-être en raison de leur valeur, utilisez des inventaires tournants. Pour les inventaires tournants, attribuez des périodes d’inventaire spéciales aux articles. Learn more at [Pour effectuer un inventaire tournant](inventory-how-count-adjust-reclassify.md#to-do-cycle-counting).

Pour ajuster les quantités après un comptage physique ou à d’autres fins, utilisez un journal article pour modifier les écritures inventaire sans reporter les transactions. Vous pouvez également ajuster la quantité d’un seul article sur une fiche article.

Pour modifier les attributs des écritures article, vous pouvez utiliser un journal reclassement article. Les attributs typiques à reclasser incluent les dimensions et les codes de promotion de vente. Les journaux reclassement peuvent également être utilisés pour les transferts en reclassant les codes de zone et d'emplacement. Des étapes spéciales s'appliquent lorsque vous souhaitez reclasser les numéros de série ou de lot et leurs dates d'expiration. Pour plus d'informations, voir [Utiliser les numéros de lot et de série](inventory-how-work-item-tracking.md).

> [!NOTE]
> Dans les processus à plusieurs étapes, les articles sont enregistrés dans des zones en tant qu’écritures entrepôt, pas en tant qu’écritures article. Par conséquent, vous effectuez l’inventaire, l’ajustement et le reclassement dans des journaux entrepôt qui prennent en charge les zones. Ensuite, vous synchronisez les écritures entrepôt nouvelles ou modifiées avec leurs écritures article correspondantes pour refléter les modifications des quantités et valeurs en inventaire.

[!INCLUDE [edit-in-excel](includes/edit-in-excel.md)]

## Pour effectuer un inventaire

Faites l’inventaire physique, c’est-à-dire comptez les articles réellement disponibles, pour vérifier si la quantité enregistrée est la même que la quantité physique en stock. En règle générale, ces comptages ont lieu à la fin d’un exercice financier, mais parfois, ils sont effectués plus souvent. S’il y a des écarts, reportez les quantités réelles dans les comptes d’articles <!--accounts, or ledger?--> avant de procéder à l’évaluation de l'inventaire.

> [!NOTE]
> Cette procédure explique comment effectuer un inventaire physique à l’aide d’un journal sur la page **Journal inventaire physique**. Vous pouvez utiliser des documents sur les pages **Ordre d’inventaire** et **Enregistrement d’inventaire**. Ces documents offrent plus de contrôle et prennent en charge la répartition du travail de comptage entre plusieurs employés. Learn more at [Faire l’inventaire à l’aide de documents](inventory-how-count-inventory-with-documents.md).<br /><br />
> Vous remarquerez que vous ne pouvez pas utiliser la fonctionnalité basée sur un document pour comptabiliser les articles dans les zones ou les écritures entrepôt.

Le processus de comptage implique également les tâches suivantes :

- Calculez l'inventaire prévu.
- Imprimer le rapport à utiliser lors du comptage.
- Saisir et reporter les quantités réelles.

En fonction de votre configuration entrepôt, vous pouvez effectuer l’inventaire de l’une des manières suivantes. Pour plus d'informations, voir [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

- Si votre emplacement n’utilise pas le rangement et le prélèvement dirigés, utilisez la page **Journal inventaire physique**. La procédure est similaire à l’inventaire physique sans inventaire tournant.  
- Si votre emplacement utilise le rangement et le prélèvement dirigés, utilisez la page **Journal inventaire physique entrepôt**. Utilisez ensuite la page **Journaux article** pour exécuter l’action **Calculer ajustement entrepôt**. <!--We should say what to do on each of these pages.-->

### Pour calculer l’inventaire prévu dans les configurations d’entrepôt de base

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journaux inventaire physique**, puis choisissez le lien associé.
2. Choisissez l'action **Calculer stock**.
3. Sur la page **Calculer inventaire**, indiquez les conditions à utiliser pour créer les lignes journal, par exemple si vous souhaitez inclure les articles pour lesquels aucun inventaire n'est enregistré.
4. Définissez des filtres si vous souhaitez uniquement calculer l'inventaire de certains articles, zones, emplacements ou dimensions.
5. Choisissez le bouton **OK**.

> [!NOTE]  
> Les écritures article sont traitées en fonction des informations que vous avez indiquées, et les lignes sont créées dans le journal inventaire physique. Notez que le champ **Qté (Inventaire physique)** contient la même quantité que le champ **Qté (calculée)**. Vous n’avez pas besoin d’entrer la quantité comptée pour les articles où ces valeurs correspondent. Cependant, si la quantité comptée diffère, entrez la quantité qui a été comptée.

### Pour imprimer le rapport à utiliser lors du comptage

1. Sur la page **Journal inventaire physique** contenant l'inventaire prévu calculé, choisissez l’action **Imprimer**.
2. Sur la page **Liste d’inventaire physique entrepôt**, indiquez si le rapport doit indiquer la quantité calculée et les articles en inventaire par numéros de série et de lot.
3. Définissez des filtres si vous souhaitez uniquement imprimer le rapport pour certains articles, zones, emplacements ou dimensions.
4. Sélectionnez **Imprimer**.

Les employés de l'entrepôt peuvent maintenant procéder au comptage de l'inventaire et noter les éventuelles différences sur le rapport imprimé.

> [!NOTE]
> Plusieurs jours peuvent s'écouler avant que les rapports imprimés reviennent pour traitement final et report. Lorsque vous spécifiez et reportez l'inventaire comptabilisé réel, le système ajuste l'inventaire pour refléter la différence entre l'inventaire comptabilisé attendu et réel. Vous devez conserver les lignes journal initialement calculées et ne pas recalculer l’inventaire attendu, car l’inventaire attendu peut changer et entraîner des niveaux d'inventaire incorrects. Si vous devez émettre plusieurs rapports, par exemple pour différents emplacements ou groupes d'éléments, vous devez créer et conserver des lots journal distincts.

### Pour saisir et reporter l'inventaire réel comptabilisé dans les configurations d'entrepôt de base

1. Sur chaque ligne de la page **Journal inventaire physique** sur laquelle l'inventaire réellement disponible, comme déterminé par le comptage physique, diffère de la quantité calculée, saisissez la quantité réellement disponible dans le champ **Qté (Inventaire physique)**.
  
  > [!NOTE]  
  > Si le décompte physique fait apparaître des différences dues à des articles reportés avec des emplacements incorrects, ne saisissez pas les différences dans le journal inventaire physique. Au lieu de cela, utilisez un journal reclassement ou un ordre de transfert pour rediriger les articles vers les emplacements appropriés. 

2. Pour ajuster les quantités calculées avec les quantités comptées réelles, choisissez **Valider**.

    Le report crée les écritures article et les écritures inventaire physique. Ouvrez la page Fiche article de l’article pour rechercher ses écritures inventaire physique. <!--Where are they shown on an item?-->

3. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
4. Pour vérifier le comptage, ouvrez la fiche article de l’article concerné, puis choisissez l’action **Écritures inventaire physique**. <!--I don't see this action -->

### Pour calculer l'inventaire prévu dans les configurations d'entrepôt avancées

Synchroniser le grand livre article et l’entrepôt <!--warehouse what?--> avant de compter l’inventaire physique. Sinon, ce que vous reportez dans le journal inventaire physique et le grand livre article sera le résultat de l’inventaire physique combiné à d’autres ajustements d’entrepôt pour les articles. Pour en savoir plus, voir [Synchroniser les quantités dans le grand livre article et l'entrepôt](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal inventaire physique entrepôt**, puis choisissez le lien associé.  
2. Choisissez l’action **Calculer inventaire** pour ouvrir la page **Calculer inventaire entrepôt**.  
3. Définissez les filtres pour spécifier les articles à compter dans le journal, puis choisissez **OK**.

   [!INCLUDE [prod_short](includes/prod_short.md)] crée une ligne pour chaque zone répondant aux exigences des filtres. Vous pouvez supprimer des lignes, mais si vous souhaitez reporter les résultats en tant qu’inventaire physique, comptez l’article dans toutes les zones le contenant.  

   Si vous ne comptez qu’un article dans certaines zones mais pas dans d’autres, vous pouvez saisir les différences et les reporter ultérieurement dans le journal article en utilisant l’action **Calculer ajustement entrepôt**. <!--I don't see this action-->  

### Pour saisir et reporter l'inventaire réel comptabilisé dans les configurations d'entrepôt avancées

1. Sur la page **Journal inventaire physique entrepôt**, saisissez les quantités réelles dans le champ **Qté (inventaire physique)**.  

    > [!NOTE]  
    >  Le champ **Qté (Calculée)** est rempli en fonction des enregistrements de zone. Cette quantité est copiée dans le champ **Qté (Physique)** sur chaque ligne. Si les quantités dans ces champs ne correspondent pas, entrez la quantité réelle.  

2. Après avoir saisi toutes les quantités réelles, choisissez l’action **Enregistrer**.  

    Lorsque vous enregistrez le journal, [!INCLUDE [prod_short](includes/prod_short.md)] crée dans l’historique entrepôt deux écritures entrepôt pour chaque ligne comptée et enregistrée :  

    - Si les quantités calculées et les quantités réelles sont différentes, une quantité négative ou positive est reportée pour la zone, et la quantité d’équilibre est reportée dans la zone d’ajustement de l'emplacement.  
    - Si la quantité calculée est égale à la quantité physique, [!INCLUDE [prod_short](includes/prod_short.md)] enregistre **0** à la fois pour la zone et la zone d’ajustement. 

Lorsque vous reportez un inventaire physique, vous ne le reportez pas dans les grands livres article, inventaire physique ou valeur. Cependant, les enregistrements sont disponibles pour le rapprochement en cas de besoin. Pour que les quantités restent exactes, après avoir compté les articles dans toutes les zones, reportez les résultats en tant qu’inventaire physique <!--physical inventory journal-->. Pour en savoir plus, voir [Synchroniser les quantités dans le grand livre article et l'entrepôt](inventory-how-count-adjust-reclassify.md#to-synchronize-the-adjusted-warehouse-entries-with-the-related-item-ledger-entries).

## Pour effectuer un inventaire tournant

Vous pouvez compter les articles aussi souvent que vous le souhaitez. Par exemple, parce qu’ils ont plus de valeur ou parce qu’ils bougent rapidement et représentent une grande partie de votre activité. Spécifiez la fréquence de comptage en attribuant des périodes de comptage spéciales aux articles.

En fonction de votre configuration entrepôt, vous pouvez effectuer un inventaire tournant de l’une des manières suivantes. Learn more at [Configuration de la gestion des entrepôts](warehouse-setup-warehouse.md).  

- Si votre emplacement n’utilise pas le rangement et le prélèvement dirigés, utilisez la page **Journal inventaire physique**. La procédure est similaire au comptage de l’inventaire physique sans inventaire tournant.  
- Si votre emplacement utilise le rangement et le prélèvement dirigés, utilisez la page **Journal inventaire physique entrepôt**. Utilisez ensuite la page **Journaux article** pour exécuter l’action **Calculer ajustement entrepôt**. <!--we should say what to do on each of these pages-->  

### Pour configurer des périodes d'inventaire

Le comptage d’inventaire est généralement une tâche récurrent, par exemple, tous les mois, tous les trimestres ou tous les ans. Vous pouvez configurer les périodes d’inventaire nécessaires et les affecter à chaque article. Ensuite, utilisez l’action **Calculer la période d’inventaire** sur la page **Journal inventaire physique** pour créer automatiquement des lignes pour les articles.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Périodes inventaire**, puis choisissez le lien associé.  
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

### Pour affecter une période d'inventaire à un article

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.  
2. Sélectionnez l'article auquel vous souhaitez affecter une période d'inventaire.  
3. Dans le champ **Code période inventaire stock**, sélectionnez la période d’inventaire.  

> [!NOTE]
> Si vous modifiez la période d’inventaire, un message affiche des informations sur les résultats de la modification. Sélectionnez **Oui** pour modifier le code et calculer la première période d’inventaire de l’article. La prochaine fois que vous choisissez de calculer une période d'inventaire dans le journal inventaire physique, l'article s'affichera en tant que ligne sur la page **Sélection article inventaire physique**. Vous pouvez ensuite compter l’article périodiquement.

### Pour lancer un comptage selon des périodes d’inventaire dans les configurations d’entrepôt de base

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal inventaire physique**, puis choisissez le lien associé.
2. Choisissez l'action **Calculer la période d'inventaire**.

    La page **Sélection article inventaire physique** affiche les articles qui doivent être comptés en fonction de leurs périodes de comptage.
3. Comptez l’inventaire physique. Learn more at [Pour effectuer un inventaire](inventory-how-count-adjust-reclassify.md#to-count-physical-inventory).

### Pour lancer un comptage selon des périodes d’inventaire dans les configurations d’entrepôt avancées

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Journal inventaire physique entrepôt**, puis choisissez le lien associé.  
2. Choisissez l'action **Calculer la période d'inventaire**.

    La page **Sélection article inventaire physique** affiche les articles qui doivent être comptés en fonction de leurs périodes de comptage.
3. Comptez l’inventaire physique. Learn more at [Pour effectuer un inventaire](inventory-how-count-adjust-reclassify.md#to-count-physical-inventory).  

   > [!NOTE]  
   > Comptez l’article dans toutes les zones qui le contiennent. Si vous supprimez des lignes zone qui ont été récupérées pour le comptage sur la page **Inventaire physique entrepôt**, le comptage sera incorrect lorsque vous le reporterez dans un journal inventaire physique.  

## Pour ajuster la quantité d’un article

Après avoir effectué l’inventaire d’un article, utilisez l’action **Ajuster l’inventaire** pour enregistrer la quantité d’inventaire réelle.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Articles**, puis choisissez le lien associé.
2. Sélectionnez l'article pour lequel vous souhaitez ajuster le stock, puis sélectionnez l'action **Ajuster stock**.
3. Dans le champ **Nouvel inventaire** de l’emplacement, saisissez le résultat du comptage.
4. Choisissez le bouton **OK**.

<!-- I don't see a "Quantity on Hand" field on the Item Card page. Should this point to the options for viewing availability?

The item’s inventory is adjusted. The new quantity is shown in the **Quantity on Hand** field on the **Item Card** page.-->

Vous pouvez également utiliser l’action **Ajuster inventaire** comme un moyen simple d’ajouter des articles achetés dans l’inventaire si vous n’utilisez pas des factures achat ou des commandes pour enregistrer vos achats. En savoir plus sur [Enregistrer les achats](purchasing-how-record-purchases.md).

> [!NOTE]  
> Après avoir ajusté l’inventaire, mettez à jour sa valeur actuelle. Pour plus d'informations, voir [Réévaluer l'inventaire](inventory-how-revalue-inventory.md).

### Pour ajuster les quantités de plusieurs articles dans les configurations d’entrepôt de base

Sur la page **Journal article**, vous pouvez reporter les transactions article directement pour ajuster l'inventaire en fonction des achats, des ventes et des changements positifs et négatifs sans utiliser de documents.

Si vous utilisez fréquemment le journal article pour reporter des lignes journal identiques ou similaires (par exemple, pour la consommation de matériel), la page **Journal article standard** peut simplifier cette tâche récurrente. Pour plus d’informations, voir [Utiliser des journaux standard](ui-work-general-journals.md#work-with-standard-journals).

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journaux article**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Choisissez l’action **Reporter** pour ajuster les quantités.

### Pour ajuster les quantités de zone dans les configurations d'entrepôt avancées

Si votre emplacement utilise le rangement et le prélèvement dirigés, utilisez la page **Journal article entrepôt** pour reporter les modifications de quantité positives et négatives non planifiées. Par exemple, pour les articles reportés comme manquants qui apparaissent de manière inattendue, ou les pertes dues à la casse.  

Les journaux article entrepôt vous offrent plus de niveaux d’ajustement pour rendre vos quantités plus précises. L’entrepôt sait combien d’articles sont disponibles et où ils sont stockés, mais chaque ajustement n’est pas reporté dans le grand livre article. Des crédits ou des débits sont créés pour la zone réelle avec l’ajustement de la quantité. Une écriture d’équilibrage est effectuée dans une zone d’ajustement. La zone d’ajustement est une zone virtuelle sans articles réels. Vous spécifiez la zone virtuelle dans le champ **Code zone ajustement inventaire** sur les pages **Fiche emplacement**.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal article entrepôt**, puis choisissez le lien associé.  
2. Renseignez les informations d'ent-ête.  
3. Dans le champ **N° d’article** sur la ligne, choisissez l’article.  
4. Saisissez la zone dans laquelle vous placez les articles supplémentaires ou dans laquelle des articles sont manquants.  
5. Dans le champ **Quantité**, si vous avez trouvé des articles supplémentaires, entrez une quantité positive. Si des articles sont manquants, saisissez une quantité négative.  
6. Sélectionnez l'action **Enregistrer**.

## Pour synchroniser les écritures entrepôt ajustées avec les écritures article associées

Reportez les enregistrements de zone d’ajustement dans le grand livre article pour les périodes que vous avez définies. Certaines compagnies reportent des ajustements quotidiens dans le grand livre article, tandis que d’autres effectuent le rapprochement moins souvent.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Journal article**, puis choisissez le lien associé.  
2. Renseignez les champs de chaque ligne journal.  
3. Choisissez l’action **Calculer ajustement entrepôt**, puis ajoutez des filtres sur la page **Calculer ajustement entrepôt**. Les ajustements sont calculés uniquement pour les écritures de la zone ajustement qui répondent aux exigences des filtres.  
4. Sur le raccourci **Options**, entrez manuellement un numéro dans le champ **N° document**. Étant donné qu'aucune série de numéros n'a été configurée pour ce traitement en lot, utilisez le modèle de numéros configuré par l'entrepôt ou saisissez la date suivie de vos initiales.  
5. Cliquez sur **OK**. Les ajustements positifs et négatifs sont totalisés pour chaque article et des lignes sont créées dans le journal article.  
6. Reportez les lignes journal pour entrer les différences de quantité dans le grand livre article. Les inventaires dans les zones et le grand livre article correspondent maintenant.  

## Voir aussi .

[Faire l'inventaire à l'aide de documents](inventory-how-count-inventory-with-documents.md)  
[Inventaire](inventory-manage-inventory.md)  
[Vue d’ensemble de la gestion d’entrepôt](design-details-warehouse-management.md)  
[Vente](sales-manage-sales.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)


[!INCLUDE[footer-include](includes/footer-banner.md)]
