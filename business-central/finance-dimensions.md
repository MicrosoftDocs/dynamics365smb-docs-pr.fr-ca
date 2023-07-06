---
title: Utilisation des dimensions pour suivre et analyser les données
description: 'Utilisez les dimensions pour classer des écritures par catégorie, comme par service ou projet, afin de pouvoir plus facilement suivre et analyser les données pour prendre les bonnes décisions commerciales.'
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.service: dynamics365-business-central
ms.topic: how-to
ms.date: 01/27/2023
ms.custom: bap-template
ms.search.keywords: 'analysis, history, track, business intelligence'
ms.search.form: '408, 479, 480, 481, 484, 536, 537, 538, 539, 540, 541, 542, 543, 544, 545, 548, 560, 562, 564, 567, 568, 577, 578, 580, 699, 1343, 2580, 2581, 2582, 2583, 2584, 2585, 2586, 2587, 2588, 2590, 2591, 2592, 2593, 9083, 9233, 9251, 9252, 9253'
---
# <a name="work-with-dimensions"></a><a name="work-with-dimensions"></a><a name="work-with-dimensions"></a>Utiliser des dimensions

Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur les documents, tels que les documents de vente. Les dimensions peuvent, par exemple, indiquer de quel projet ou département provient une écriture.  

Ainsi, au lieu de configurer des comptes GL pour chaque service et projet, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer un plan comptable compliqué. Pour plus d’informations, consultez [Veille économique](bi.md).

Un autre exemple consiste à configurer une dimension appelée *Département* et utiliser cette dimension lorsque vous reportez des documents de vente. Cela vous permet d’utiliser les outils de veille économique pour savoir quel département a vendu quels articles. Plus vous utilisez de dimensions, plus vos décisions commerciales sont basées sur des rapports détaillés. En fait, une seule écriture vente peut comporter des informations depuis plusieurs dimensions :  

* Le compte sur lequel la vente de l’article a été reportée.  
* L’endroit où l’article a été vendu.
* Le nom du vendeur.
* Le nom du client qui l’a acheté.

## <a name="analyzing-by-dimensions"></a><a name="analyzing-by-dimensions"></a><a name="analyzing-by-dimensions"></a>Analyse par dimensions

La fonctionnalité Dimensions joue un rôle important dans la veille économique, par exemple en définissant des vues d’analyse. Pour en savoir plus, voir [Analyse des données par dimensions](bi-how-analyze-data-dimension.md).

> [!TIP]
> Pour analyser rapidement les données transactionnelles par dimensions, vous pouvez utiliser l'action **Définir le filtre dimension** pour filtrer les totaux par dimensions dans le plan comptable et sur les pages pour les écritures.

> [!NOTE]
> Les vues d′analyse utilisent souvent les données des dimensions. Si vous découvrez qu’une dimension incorrecte a été utilisée sur les écritures GL reportées, vous pouvez corriger les valeurs de dimension et mettre à jour vos vues d’analyse. Cela vous aide à garder vos rapports et analyses financiers exacts. Pour en savoir plus, voir [Dépannage et correction des dimensions](finance-troubleshooting-correcting-dimensions.md#changing-dimension-assignments-after-posting).

## <a name="dimension-sets"></a><a name="dimension-sets"></a><a name="dimension-sets"></a>Ensembles de dimensions

Un ensemble de dimensions est une combinaison unique de sections analytiques. Elles sont stockées comme des écritures de l’ensemble de dimensions dans la base de données. Chaque écriture de l'ensemble de dimensions représente une valeur de dimension unique. De plus, chaque ensemble de dimensions et l’écriture ensemble de dimensions qu’il contient sont identifiés par un code d’ensemble de dimensions commun.  

Lorsque vous créez une ligne de journal, un en-tête de document ou une ligne de document, vous pouvez spécifier une combinaison de valeurs de dimension. Au lieu d'enregistrer explicitement chaque valeur de dimension dans la base de données, un code d'ensemble de dimensions est affecté à la ligne de journal, à l'en-tête du document ou à la ligne du document pour spécifier l'ensemble de dimensions.  

## <a name="setting-up-dimensions"></a><a name="setting-up-dimensions"></a><a name="setting-up-dimensions"></a>Configuration de dimensions

Vous pouvez définir les dimensions et les valeurs de dimension pour classer des journaux et des documents par catégorie, comme des documents de vente et des bons de commande. La page **Dimensions** permet de créer une ligne pour chaque dimension, par exemple *Projet*, *Département*, *Zone* et *Représentant*.

Vous pouvez également définir des valeurs pour des axes. Disons que les valeurs représentent les départements de votre compagnie. Les valeurs de dimension peuvent être configurées selon une structure hiérarchique similaire au plan comptable. Cela signifie que les données peuvent être décomposées en différents niveaux de granularité et que des sous-ensembles de valeurs de dimension peuvent être totalisés. Vous pouvez définir autant de dimensions et de valeurs de dimension que nécessaire, et tous les membres de votre compagnie peuvent les utiliser.

Une fois les dimensions et les valeurs configurées, vous pouvez définir des dimensions globales et de raccourci sur la page **Configuration du grand livre**. Ces dimensions sont alors toujours disponibles pour que vous puissiez les sélectionner en tant que champs sur les lignes de journal et de document ainsi que sur les écritures, sans ouvrir au préalable la page **Dimensions**. Pour plus d’informations, consultez la section [Configurer les dimensions globales et de raccourci](finance-dimensions.md#to-set-up-global-and-shortcut-dimensions).

* Les **dimensions principales** sont utilisées comme filtres, par exemple, dans les rapports, les traitements en lot et les objets XMLport. Vous pouvez uniquement utiliser deux axes principaux, choisissez donc des axes que vous utilisez souvent.
* Les **Raccourcis dimension** sont disponibles sous forme de champs dans les lignes journaux et document, et les écritures. Vous pouvez en créer huit au maximum.  

> [!NOTE]
> Après avoir utilisé une nouvelle dimension dans une écriture, telle qu’une ligne ou un nouvel enregistrement, vous ne pouvez pas supprimer la dimension, même si vous ne reportez pas l’écriture. Ceci est dû au fait que [!INCLUDE[prod_short](includes/prod_short.md)] crée immédiatement un ensemble de dimensions pour la ligne ou l’enregistrement. Pour plus d’informations, consultez la section [Ensembles de dimensions](finance-dimensions.md#dimension-sets).

### <a name="to-set-up-default-dimensions-for-customers-vendors-and-other-accounts"></a><a name="to-set-up-default-dimensions-for-customers-vendors-and-other-accounts"></a><a name="to-set-up-default-dimensions-for-customers-vendors-and-other-accounts"></a>Pour configurer des dimensions par défaut pour les clients, les fournisseurs et d'autres comptes

Vous pouvez attribuer une dimension par défaut pour un compte spécifique. La dimension est copiée sur le journal ou le document lorsque vous saisissez le numéro de compte dans une ligne, mais vous pouvez supprimer ou modifier le code sur la ligne si nécessaire. Vous pouvez également rendre une dimension obligatoire pour valider une écriture avec un type de compte spécifique. > 

> [!NOTE]
> Les priorités de dimension par défaut s’ouvrent pour les scénarios de vente et d’achat qui pourraient nécessiter une attention particulière. Lorsque vous utilisez les priorités de dimension par défaut sur des documents de vente et d’achat, [!INCLUDE [prod_short](includes/prod_short.md)] considère toujours les dimensions dans l’en-tête comme provenant du client ou du fournisseur. Cela est vrai pour les dimensions que vous définissez manuellement ou par défaut, et est particulièrement pertinent lorsque vous utilisez des dimensions par défaut sur des emplacements et des articles, mais pas sur des clients ou des fournisseurs.
>
> **Exemple :**
>
> Vous avez un scénario avec les paramètres de dimension suivants :
>
> * Un client sans dimensions par défaut
> * Un article avec ADM comme valeur de dimension pour la dimension DÉPARTEMENT
> * Un emplacement avec PROD comme valeur de dimension pour la dimension DÉPARTEMENT
> * Les priorités de dimension par défaut sont définies sur Client > Article > Emplacement
>
> Lorsque vous créez un document dans ce scénario, les dimensions sont utilisées comme suit :
>
> * Si vous créez un document et ajoutez un emplacement, la valeur par défaut pour les nouvelles lignes sera PROD. Lorsque vous ajoutez des lignes avec des articles, [!INCLUDE [prod_short](includes/prod_short.md)] conservera PROD car il provient de l’en-tête du document.
>
> * Si vous créez un document et ajoutez des articles qui ont la valeur de dimension ADM, puis spécifiez un emplacement dans l’en-tête du document, [!INCLUDE [prod_short](includes/prod_short.md)] vous demandera si vous souhaitez écraser les lignes existantes en raison d’un conflit.
>
> Nous vous recommandons de tester la configuration de vos dimensions par défaut, les priorités de dimension et l’ordre dans lequel vous saisissez les données dans les documents.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Dimensions**, puis sélectionnez le lien associé.  
2. Sur la page **Dimensions** sélectionnez la dimension appropriée, puis sélectionnez l’action **Dimension par défaut du type de compte**.  
3. Complétez une ligne pour chaque nouvelle dimension à configurer. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]  
> Si vous souhaitez rendre une dimension obligatoire sans lui affecter de valeur par défaut, ne renseignez pas le champ **Code de valeur de dimension**, puis sélectionnez **Code obligatoire** dans le champ **Contrôle report**.  

> [!WARNING]  
> Si un compte doit être utilisé dans un traitement en lot **Ajuster taux de change** ou **Reporter coût de l’inventaire au GL**, ne sélectionnez pas **Code obligatoire** ni **Même code**. Ces traitements en lot ne peuvent pas utiliser de codes de dimensions.  

> [!NOTE]  
> Si un compte doit avoir une dimension différente de la dimension par défaut affectée à ce type de compte, vous devez configurer une nouvelle dimension pour ce compte. La dimension par défaut de ce compte remplace alors celle du type de compte.  

### <a name="to-set-up-default-dimension-priorities"></a><a name="to-set-up-default-dimension-priorities"></a><a name="to-set-up-default-dimension-priorities"></a>Pour configurer des priorités de dimensions par défaut

Des types de compte différents, tels qu’un compte client et un compte article, peuvent avoir des dimensions différentes. Par conséquent, une écriture peut avoir plusieurs dimensions proposées par défaut. Pour éviter de tels conflits, vous pouvez appliquer des règles de priorité aux différentes sources.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Priorités de dimensions par défaut**, puis sélectionnez le lien associé.  
2. Sur la page **Priorités dimension par défaut**, dans le champ **Code source**, entrez le code source pour la table écriture à laquelle les priorités de dimensions par défaut s’appliquent.  
3. Complétez une ligne pour chaque priorité de dimensions par défaut souhaitée pour le code d’origine sélectionné.
4. Répétez la procédure pour chaque code d’origine pour lequel vous souhaitez configurer des priorités de dimensions par défaut.  

> [!IMPORTANT]  
> Si vous configurez deux tables avec la même priorité pour le même code source, [!INCLUDE[prod_short](includes/prod_short.md)] sélectionne toujours la table ayant le plus petit code.  

### <a name="to-set-up-dimension-combinations"></a><a name="to-set-up-dimension-combinations"></a><a name="to-set-up-dimension-combinations"></a>Pour configurer des combinaisons de dimensions

Pour éviter de reporter des écritures avec des dimensions contradictoires ou inappropriées, vous pouvez bloquer ou limiter des combinaisons spécifiques de deux dimensions. Lorsqu’un croisement de dimension est bloqué, vous ne pouvez pas reporter les deux dimensions sur la même écriture, quelles que soient les valeurs de dimension. A contrario, lorsqu’un croisement de dimension est limité, vous pouvez reporter les deux dimensions sur la même écriture, mais uniquement pour certains croisements de valeurs de dimension.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Combinaisons de dimensions**, puis sélectionnez le lien associé.  
2. Sur la page **Croisements de dimensions**, sélectionnez le champ du croisement de dimension souhaité parmi les options suivantes.  

    |Champ|Désignation|
    |----------------------------------|---------------------------------------|  
    |**Aucune limite**|Cette combinaison de dimensions n'a pas de restrictions. Toutes les sections analytiques sont autorisées.|  
    |**Limité**|Cette combinaison de dimensions a des restrictions selon les valeurs de dimension que vous entrez. Vous devez définir ces limites sur la page **Combinaison valeur de dimension**.|  
    |**Bloqué**|Cette combinaison de dimensions n'est pas autorisée.|  

3. Si vous avez sélectionné l'option **Limité**, vous devez définir les croisements de sections analytiques bloqués. Pour cela, sélectionnez le champ pour définir le croisement de valeurs de dimension.  
4. Sélectionnez à présent le croisement de sections analytiques bloqué et entrez **Bloqué** dans le champ. Un champ vide signifie que le croisement de valeurs de dimension est autorisé. Répétez cette procédure si plusieurs croisements sont bloqués.  

> [!NOTE]  
> Les mêmes dimensions s’affichent à la fois dans les lignes et les colonnes et, par conséquent, tous les croisements de dimensions apparaissent deux fois. [!INCLUDE[prod_short](includes/prod_short.md)] affiche automatiquement le paramètre dans les deux champs. Vous ne pouvez rien sélectionner dans les champs situés dans le coin supérieur gauche et en bas car ces champs ont la même dimension de ligne et de colonne.  
>
> L'option sélectionnée s'affiche uniquement lorsque vous quittez le champ.  
>
> Pour afficher le nom des dimensions à la place du code, sélectionnez le champ **Afficher nom colonne**.

### <a name="to-set-up-global-and-shortcut-dimensions"></a><a name="to-set-up-global-and-shortcut-dimensions"></a><a name="to-set-up-global-and-shortcut-dimensions"></a>Pour configurer des dimensions principales et des raccourcis de dimension

Les dimensions principales et les raccourcis de dimension peuvent être utilisés comme filtres dans [!INCLUDE[prod_short](includes/prod_short.md)], y compris sur les rapports, les traitements en lot, les pages d’écritures et les vues d’analyse. Les dimensions principales et les raccourcis peuvent toujours être insérés directement sans ouvrir tout d’abord la page **Dimensions**. Sur les lignes journal et document, vous pouvez sélectionner les dimensions principales et les raccourcis de dimension dans un champ sur la ligne. Vous pouvez définir deux dimensions principales et huit raccourcis de dimension. Sélectionnez les dimensions que vous utilisez le plus souvent.

> [!IMPORTANT]
> Le fait de modifier une dimension principale ou un raccourci dimension exige que toutes les écritures saisies avec la dimension soient mises à jour. Pour modifier une dimension globale, vous pouvez utiliser la fonction **Modifier les dimensions principales**, mais cela peut se révéler chronophage et peut avoir un impact sur les performances et les tables peuvent être verrouillées lors de la mise à jour. Assurez-vous de sélectionner vos dimensions principales et vos raccourcis dimension avec soin afin que vous n’ayez pas à les changer ultérieurement. Pour modifier un raccourci dimension, utilisez l’action **Modifier les dimensions**.
>
> Pour plus d’informations, consultez la section [Pour modifier les dimensions principales](finance-dimensions.md#to-change-global-dimensions).

> [!NOTE]
> Lorsque vous ajoutez ou modifiez une dimension principale ou un raccourci dimension, vous êtes automatiquement déconnecté et la nouvelle valeur est préparée.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.
2. Sur le raccourci **Dimensions**, renseignez les champs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### <a name="to-change-global-dimensions"></a><a name="to-change-global-dimensions"></a><a name="to-change-global-dimensions"></a>Pour modifier les dimensions principales

Lorsque vous modifiez une dimension principale ou un raccourci, toutes les écritures saisies avec cette dimension sont mises à jour. Étant donné que ce processus peut prendre du temps et affecter les performances, deux modes différents sont fournis pour adapter le processus à la taille de la base de données.  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration du grand livre**, puis choisissez le lien associé.
2. Choisissez l'action **Modifier les dimensions principales**.
3. En haut de la page, sélectionnez l’un des deux modes suivants pour exécuter le traitement en lot.

    |Option|Désignation|
    |-|-|
    |**Séquentiel**|(Par défaut) Le changement est effectué en une seule transaction qui restituent à toutes les écritures les dimensions qu’elles avaient avant le changement.<br /><br />Cette option est recommandée si la compagnie a relativement peu d’écritures reportées, auquel cas le traitement en lot prend moins de temps pour s’effectuer. Le processus verrouille plusieurs tables et bloque les autres utilisateurs jusqu'à ce qu'il soit terminé. Notez qu’avec les grandes bases de données, le processus peut ne pas être en mesure de s’effectuer dans ce mode. Dans ce cas, utilisez l'option **Parallèle**.|
    |**Parallèle**|Le changement de dimension se produit dans plusieurs sessions d’arrière-plan et l’opération est divisée en plusieurs transactions. Pour utiliser cette option, activez le bouton bascule **Traitement parallèle**. <br /><br />Cette option est recommandée pour les grandes bases de données ou les compagnies ayant de nombreuses écritures reportées, car c’est ainsi que le processus prendra le moins de temps. Notez que dans ce mode, le processus de mise à jour ne démarrera pas s’il existe plusieurs sessions de base de données actives.|  

4. Dans les champs **Code dimension principale 1** et/ou **Code dimension principale 2**, entrez les nouvelles dimensions. Les dimensions actuelles sont affichées en gris derrière les champs.
5. En fonction du mode, effectuez l’une des opérations suivantes :
    * Dans mode **Séquentiel**, choisissez l’action **Démarrer**.
    * Dans mode **Parallèle**, choisissez l’action **Préparer**.

    L’onglet **Écritures journal** contient des informations sur les dimensions à modifier.
6. Déconnectez-vous de [!INCLUDE[prod_short](includes/prod_short.md)], puis reconnectez-vous.
7. Choisissez l’action **Démarrer** pour commencer le traitement parallèle des changements de dimension.

### <a name="example-of-dimension-setup"></a><a name="example-of-dimension-setup"></a><a name="example-of-dimension-setup"></a>Exemple de configuration de dimension

Imaginons que votre compagnie souhaite suivre les transactions selon la structure organisationnelle et les situations géographiques. Pour ce faire, vous pouvez configurer deux dimensions sur la page **Dimensions** :

* **REGION**  
* **DEPARTEMENT**  

| Code | Nom | Libellé code | Libellé filtre |
| --- | --- | --- | --- |
| REGION |Région |Zone de recouvrement |Filtre zone |
| DEPARTEMENT |Département |Code emplacement immo |Filtre département |

Pour **ZONE**, vous pouvez ajouter les valeurs de dimension suivantes :

| Code | Nom | Type de valeur de dimension |
| --- | --- | --- |
| 10 |Amériques |Début total |
| 2.0 |Amérique du Nord |Standard |
| 30 |Pacifique |Standard |
| 40 |Amérique du Sud |Standard |
| 50 |Amériques, Total |Fin total |
| 60 |Europe |Début total |
| 70 |INTRA |Standard |
| 80 |Non-UE |Standard |
| 90 |Europe, Total |Fin total |

Pour les deux zones géographiques principales, Amériques et Europe, ajoutez des sous-catégories pour les régions en décalant les valeurs de dimension. Cela vous permet de déclarer les ventes ou les dépenses dans les régions, et d’obtenir les totaux des zones géographiques plus étendues. Vous pouvez également choisir d’utiliser les pays, les régions, les comtés ou les villes en tant que valeurs de dimension, en fonction de votre entreprise.

> [!NOTE]  
> Pour configurer une hiérarchie, veillez à trier les codes dans l'ordre alphabétique. Ceci inclut les codes des valeurs de dimension fournis dans [!INCLUDE[prod_short](includes/prod_short.md)].  

Pour **DÉPARTEMENT**, vous pouvez ajouter les valeurs de dimension suivantes :

| Code | Nom | Type de valeur de dimension |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| FABR |Fabrication |Standard |
| VENTES |Ventes |Standard |

Avec cette configuration, vous pouvez ensuite ajouter les deux dimensions en tant que dimensions principales sur la page **Configuration du grand livre**. Cela signifie que vous pouvez utiliser ZONE et DÉPARTEMENT comme filtres pour les écritures du grand livre, ainsi que dans tous les rapports. Les deux axes principaux sont mis à disposition automatiquement pour être utilisés dans les lignes écriture et les en-têtes document comme raccourcis axe.

## <a name="getting-an-overview-of-dimensions-used-multiple-times"></a><a name="getting-an-overview-of-dimensions-used-multiple-times"></a><a name="getting-an-overview-of-dimensions-used-multiple-times"></a>Affichage d’un aperçu des dimensions utilisées plusieurs fois

La page **Dimensions par défaut - Multiples** spécifie la manière dont un groupe de comptes utilise les dimensions et valeurs de dimension. Vous pouvez configurer cela en mettant en surbrillance plusieurs comptes, puis en spécifiant les dimensions et les valeurs de dimension par défaut pour eux. Après cela, l’application suggère ces dimensions et valeurs de dimension chaque fois que l’un de ces comptes est utilisé, par exemple dans une ligne journal. Le report des écritures est ainsi facilité, car les champs de dimension sont renseignés automatiquement. Notez toutefois que les valeurs de dimension proposées peuvent être modifiées, par exemple sur une ligne journal.

La page **Dimensions par défaut - Multiples** contient les champs suivants :

|Champ|Désignation|
|-----|-----------|  
|**Code axe analytique**|Affiche toutes les dimensions définies comme dimensions par défaut sur un ou plusieurs comptes sélectionnés. Si vous sélectionnez ce champ, vous pouvez visualiser la liste de toutes les dimensions disponibles. Si vous sélectionnez une dimension, celle-ci est définie comme dimension par défaut pour tous les comptes en surbrillance.|
|**Code section**|Affiche une valeur de dimension ou le terme (Conflit). Si le champ indique une valeur de dimension, tous les comptes sélectionnés ont la même valeur de dimension par défaut pour une dimension donnée. Si le champ indique le terme (Conflit), les comptes sélectionnés n’ont pas tous la même valeur de dimension par défaut pour une dimension donnée. Lorsque vous sélectionnez le champ **Code dimension**, vous voyez une liste de toutes les valeurs de dimension disponibles pour une dimension donnée. Si vous sélectionnez une valeur de dimension, elle est définie comme valeur de dimension par défaut pour tous les comptes sélectionnés.|
|**Contrôle validation**|Affiche une règle de report valeur ou le terme (Conflit). Si le champ indique une règle de report valeur, tous les comptes sélectionnés ont la même règle de report valeur pour une valeur de dimension donnée. Si le champ indique le terme (Conflit), les comptes sélectionnés n’ont pas tous la même règle de contrôle report pour une valeur de dimension donnée. Lorsque vous sélectionnez le champ **Report valeur**, vous voyez la liste des règles de contrôle report pour une dimension. Si vous sélectionnez une règle de contrôle report, elle s’applique à tous les comptes sélectionnés.|

## <a name="use-dimensions"></a><a name="use-dimensions"></a><a name="use-dimensions"></a>Utiliser des dimensions

Dans un document tel qu'un document de vente, vous pouvez ajouter des informations de dimension pour une seule ligne document et pour le document lui-même. Sur la page **Document de vente**, vous pouvez saisir des valeurs de dimension pour les deux premiers raccourcis dimension directement sur les lignes vente individuelles et ajouter des informations de dimension complémentaires si vous cliquez sur le bouton **Dimensions**.  

Si vous travaillez plutôt sur un journal, vous pouvez également ajouter à une écriture des informations de dimension de la même manière, si vous avez configuré des raccourcis de dimension en tant que champs directement dans les lignes journal.  

Vous pouvez également configurer des dimensions par défaut pour des comptes ou des types de compte, de sorte que les dimensions et les valeurs de dimension soient renseignées automatiquement.

### <a name="to-view-global-dimensions-in-ledger-entry-pages"></a><a name="to-view-global-dimensions-in-ledger-entry-pages"></a><a name="to-view-global-dimensions-in-ledger-entry-pages"></a>Pour afficher les dimensions principales dans les pages écriture

Les dimensions principales sont toujours définies et nommées par la compagnie. Pour visualiser les dimensions globales de votre compagnie, ouvrez la page **Configuration du grand livre**.

Dans une page écriture, vous pouvez voir si des dimensions principales sont associées aux écritures. Les deux dimensions principales sont différentes des autres dimensions car vous pouvez les utiliser en tant que filtres n’importe où dans [!INCLUDE[prod_short](includes/prod_short.md)].  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Plan comptable**, puis choisissez le lien associé.  
2. Sur la page **Plan comptable**, choisissez l'action **Écritures**.  
3. Pour ne visualiser que certaines écritures, positionnez au moins un filtre sur la page.  
4. Pour visualiser toutes les dimensions d’une écriture, sélectionnez l’écriture, puis sélectionnez l’action **Dimensions**.  

> [!NOTE]  
> La page **Dimensions - Écritures** affiche les dimensions d’une écriture à la fois. Lorsque vous faites défiler les écritures, le contenu de la page **Dimensions - Écritures** est modifié en conséquence.

## <a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a><a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/dimensions-dynamics-365-business-central/index) associée

## <a name="see-also"></a><a name="see-also"></a><a name="see-also"></a>Voir aussi .

[Veille économique](bi.md)  
[Finance](finance.md)  
[Analyse des données par dimensions](bi-how-analyze-data-dimension.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
