---
title: Utiliser les axes analytiques| Microsoft Docs
description: Utilisez les axes analytiques pour classer des écritures par catégorie, par exemple, par service ou le projet, afin de facilement suivre et analyser les données.
services: project-madeira
documentationcenter: ''
author: SorenGP
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: analysis, history, track
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 1cb323b374077261ef01591df51b410702681657
ms.sourcegitcommit: ff2b55b7e790447e0c1fcd5c2ec7f7610338ebaa
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/15/2021
ms.locfileid: "5386559"
---
# <a name="working-with-dimensions"></a>Utilisation des axes analytiques
Les dimensions sont des valeurs qui permettent de catégoriser les écritures afin de pouvoir les suivre et les analyser sur les documents, tels que les documents de vente. Les dimensions peuvent, par exemple, indiquer de quel projet ou département provient une écriture.  

Par exemple, au lieu de configurer des comptes GL distincts pour chaque service et projet, vous pouvez utiliser les dimensions comme base d’analyse et éviter d’avoir à créer un plan comptable compliqué. Pour plus d'informations, reportez-vous à [Veille économique](bi.md).

Un autre exemple consiste à configurer un axe analytique appelé *Département* et utiliser cet axe lorsque vous validez des documents vente. Cela vous permet d'utiliser les outils de veille économique pour savoir quel département a vendu quels articles. Plus vous utilisez d'axes analytiques, plus vous pouvez baser vos décisions commerciales sur des états détaillés. Par exemple, une seule écriture vente peut comporter des informations issues de plusieurs dimensions, comme :  

* Le compte sur lequel la vente de l'article a été reportée  
* L'endroit où l'article a été vendu
* Le nom du vendeur
* Le type de client qui a effectué l'achat  

## <a name="analyzing-by-dimensions"></a>Analyse par dimensions
La fonctionnalité Dimensions joue un rôle important dans la veille économique, par exemple en définissant des vues d’analyse. Pour plus d'informations, voir [Analyser des données par dimensions](bi-how-analyze-data-dimension.md).

> [!TIP]
> Pour analyser rapidement les données transactionnelles par dimensions, vous pouvez utiliser le filtre **Définir le filtre dimension** pour filtrer les totaux du plan comptable et les entrées de toutes les pages par dimensions.

## <a name="dimension-sets"></a>Ensembles de dimensions
<!--we describe what they are, but not their value.-->
Un ensemble de dimensions est une combinaison unique de sections analytiques. Il est stocké comme des écritures de l'ensemble de dimensions dans la base de données. Chaque écriture de l'ensemble de dimensions représente une valeur de dimension unique. L'ensemble de dimensions est identifié par un code commun, qui est affecté à chaque écriture correspondante qui appartient à l'ensemble de dimensions.  

Lorsque vous créez une ligne de journal, un en-tête de document ou une ligne de document, vous pouvez spécifier une combinaison de valeurs de dimension. Au lieu d'enregistrer explicitement chaque valeur de dimension dans la base de données, un code d'ensemble de dimensions est affecté à la ligne de journal, à l'en-tête du document ou à la ligne du document pour spécifier l'ensemble de dimensions.  

## <a name="setting-up-dimensions"></a>Configuration d'axes
Vous pouvez définir les axes et les sections analytiques pour classer des feuilles et des documents par catégorie, comme des commandes vente et achat. La page **Dimensions** permet de créer une ligne pour chaque dimension, par exemple *Projet*, *Département*, *Zone* et *Représentant*.

Vous pouvez également définir des valeurs pour des axes. Il peut par exemple s'agir de départements de votre compagnie. Les sections analytiques peuvent être paramétrées sous forme de structure hiérarchique similaire au plan comptable, de manière à ce que les données puissent être réparties en plusieurs niveaux de granularité et à ce que des sous-ensembles de sections analytiques puissent être totalisés. Vous pouvez définir autant de dimensions et de valeurs de dimension que nécessaire, et tous les membres de votre compagnie peuvent les utiliser.

Lorsque les dimensions et les valeurs sont configurées, vous pouvez définir les dimensions principales et les raccourcis de dimension sur la page **Configuration du grand livre** qui seront toujours disponibles pour sélection comme champs sur les lignes journal et document, et les écritures, sans avoir à ouvrir la page **Dimensions** en premier lieu. Pour plus d'informations, reportez-vous à la rubrique [Configurer les dimensions principales et les raccourcis de dimension](finance-dimensions.md#to-set-up-global-and-shortcut-dimensions).

* Les **dimensions principales** sont utilisées comme filtres, par exemple, dans les rapports, les traitements en lot et les objets XMLport. Vous pouvez uniquement utiliser deux axes principaux, choisissez donc des axes que vous utilisez souvent.
* Les **Raccourcis dimension** sont disponibles sous forme de champs dans les lignes journaux et document, et les écritures. Vous pouvez en créer huit au maximum.  

### <a name="to-set-up-default-dimensions-for-customers-vendors-and-other-accounts"></a>Pour configurer des dimensions par défaut pour les clients, les fournisseurs et d'autres comptes
Vous pouvez attribuer une dimension par défaut pour un compte spécifique. La dimension est copiée sur le journal ou le document lorsque vous saisissez le numéro de compte dans une ligne, mais vous pouvez supprimer ou modifier le code sur la ligne si nécessaire. Vous pouvez également rendre une dimension obligatoire pour reporter une écriture avec un type de compte spécifique.  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Dimensions**, puis sélectionnez le lien associé.  
2.  Sur la page **Dimensions** sélectionnez la dimension appropriée, puis cliquez sur **Dimension par défaut du type de compte**.  
4.  Complétez une ligne pour chaque nouvelle dimension par défaut à configurer. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!TIP]  
>  Si vous souhaitez rendre un axe requis sans lui affecter de section analytique par défaut, ne renseignez pas le champ **Code section**, puis sélectionnez **Code obligatoire** dans le champ **Contrôle validation**.  

> [!WARNING]  
>  Si un compte doit être utilisé dans le traitement en lot **Ajuster taux de change** ou **Reporter coût de l'inventaire dans le grand livre**, ne sélectionnez pas **Code obligatoire** ni **Même code**. Ces traitements en lot ne peuvent pas utiliser de codes de dimensions.  

> [!NOTE]  
>  Si une dimension différente de la dimension par défaut configurée pour ce type de compte doit être associée à un compte, vous devez configurer une dimension par défaut pour ce compte. La dimension par défaut de ce compte remplace alors celle du type de compte.  

### <a name="to-set-up-default-dimension-priorities"></a>Pour configurer des priorités de dimensions par défaut  
Des types de compte différents, tels qu'un compte client et un compte article, peuvent avoir des affectations analytiques différentes. Par conséquent, plusieurs dimensions par défaut peuvent être proposées pour une dimension dans une écriture. Pour éviter de tels conflits, vous pouvez appliquer des règles de priorité aux différentes sources.  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Priorités de dimensions par défaut**, puis sélectionnez le lien associé.  
2.  Sur la page **Priorités dimension par défaut**, dans le champ **Code source**, entrez le code source pour la table écriture à laquelle les priorités de dimension par défaut s'appliquent.  
3.  Complétez une ligne pour chaque priorité de dimensions par défaut souhaitée pour le code d'origine sélectionné.
4.  Répétez la procédure pour chaque code d'origine pour lequel vous souhaitez configurer des priorités de dimensions par défaut.  

> [!IMPORTANT]  
>  Si vous configurez deux tables avec la même priorité pour le même code journal, [!INCLUDE[prod_short](includes/prod_short.md)] sélectionne la table ayant le plus petit ID.  

### <a name="to-set-up-dimension-combinations"></a>Pour configurer des combinaisons de dimensions  
Pour éviter de reporter des écritures avec des dimensions contradictoires ou inappropriées, vous pouvez bloquer ou limiter des combinaisons spécifiques de deux dimensions. Lorsqu'une combinaison de dimensions est bloquée, vous ne pouvez pas reporter les deux dimensions sur la même écriture, quelles que soient les valeurs de la dimension. Lorsqu'une combinaison de dimensions est limitée, vous pouvez reporter les deux dimensions sur la même écriture, mais uniquement pour certaines combinaisons de valeurs de dimensions.

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Combinaisons de dimensions**, puis sélectionnez le lien associé.  
2.  Sur la page **Combinaisons de dimensions**, sélectionnez le champ de la combinaison de dimensions et sélectionnez l'une des options suivantes.  

    |Champ|Description|
    |----------------------------------|---------------------------------------|  
    |**Aucune limite**|Cette combinaison de dimensions n'a pas de restrictions. Toutes les sections analytiques sont autorisées.|  
    |**Limité**|Cette combinaison de dimensions a des restrictions selon les valeurs de dimension que vous entrez. Vous devez définir ces limites sur la page **Combinaison valeur de dimension**.|  
    |**Bloqué**|Cette combinaison de dimensions n'est pas autorisée.|  

3.  Si vous avez sélectionné l'option **Limité**, vous devez définir les croisements de sections analytiques bloqués. Pour cela, sélectionnez le champ pour définir la combinaison de dimensions.  
4.  Sélectionnez à présent le croisement de sections analytiques bloqué et entrez **Bloqué** dans le champ. Un champ vierge signifie que la combinaison de valeurs de dimensions est autorisée. Répétez cette procédure si plusieurs croisements sont bloqués.  

> [!NOTE]  
>  Les mêmes dimensions s'affichent à la fois dans les lignes et les colonnes et, par conséquent, toutes les combinaisons de dimensions apparaissent deux fois. [!INCLUDE[prod_short](includes/prod_short.md)] affiche automatiquement le paramètre dans les deux champs. Vous ne pouvez rien sélectionner dans les champs situés dans le coin supérieur gauche et en bas car ces champs ont la même dimension de ligne et de colonne.  
>   
>  L'option sélectionnée s'affiche uniquement lorsque vous quittez le champ.  
>   
>  Pour afficher le nom des dimensions à la place du code, sélectionnez le champ **Afficher nom colonne**.

### <a name="to-set-up-global-and-shortcut-dimensions"></a>Pour configurer des dimensions principales et des raccourcis de dimension
Les dimensions principales et les raccourcis de dimension peuvent être utilisés comme filtres dans [!INCLUDE[prod_short](includes/prod_short.md)], y compris sur les rapports, les traitements en lot, les pages d’écritures et les vues d’analyse. Les dimensions principales et les raccourcis de dimension sont toujours disponibles pour être insérés directement sans ouvrir tout d'abord la page **Dimensions**. Sur les lignes journal et document, vous pouvez sélectionner les dimensions principales et les raccourcis de dimension dans un champ sur la ligne. Vous pouvez définir deux dimensions principales et huit raccourcis de dimension. Sélectionnez les dimensions que vous utilisez le plus souvent.

> [!Important]  
> La modification d'une dimension principale ou d'un raccourci de dimension nécessite la mise à jour de toutes les écritures reportées à l'aide de cette dimension. Pour modifier une dimension principale, utilisez la fonction **Modifier les dimensions principales**, mais cela peut se révéler chronophage et avoir un impact sur les performances, et les tables peuvent être verrouillées lors de la mise à jour. Par conséquent, sélectionnez vos dimensions principales et vos raccourcis de dimension avec soin afin que vous n'ayez pas à les changer ultérieurement. Pour modifier un raccourci dimension, utilisez l’action **Modifier les dimensions**. <br /><br />
> Pour plus d'informations, voir [Pour modifier les dimensions principales](finance-dimensions.md#to-change-global-dimensions).

> [!Note]
> Lorsque vous ajoutez ou modifiez une dimension principale ou un raccourci dimension, vous êtes automatiquement déconnecté et la nouvelle valeur est préparée pour l'utilisation.

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du grand livre**, puis sélectionnez le lien associé.
2. Sur le raccourci **Dimensions**, renseignez les champs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

#### <a name="to-change-global-dimensions"></a>Pour modifier les dimensions principales
Lorsque vous modifiez une dimension principale ou de raccourci, toutes les écritures reportées avec la dimension en question sont mises à jour. Étant donné que ce processus peut prendre du temps et affecter les performances, deux modes différents sont fournis pour adapter le processus à la taille de la base de données.  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Configuration du grand livre**, puis sélectionnez le lien associé.
2. Choisissez l'action **Modifier les dimensions principales**.
3. En haut de la page, sélectionnez l'une des options suivantes pour définir dans quel mode le travail en lot est exécuté.

    |Option|Description|
    |-|-|
    |**Séquentiel**|(Par défaut) Le changement est effectué en une seule transaction qui restituent à toutes les écritures les dimensions qu’elles avaient avant le changement.<br /><br />Cette option est recommandée si la compagnie contient relativement peu d'écritures reportées où elle sera la plus rapide à exécuter. Le processus verrouille plusieurs tables et bloque les autres utilisateurs jusqu'à ce qu'il soit terminé. Notez que sur les grandes bases de données, le processus peut ne pas être en mesure de s’effectuer dans ce mode. Dans ce cas, utilisez l'option **Parallèle**.|
    |**Parallèle**|Le changement de dimension se produit dans plusieurs sessions d’arrière-plan et l’opération est divisée en plusieurs transactions. Pour utiliser cette option, activez le bouton bascule **Traitement parallèle**. <br /><br />Cette option est recommandée pour les grandes bases de données ou les compagnies avec de nombreuses écritures reportées où elle sera exécutée le plus rapidement. Notez qu’avec ce mode, le processus de mise à jour ne démarre pas s’il existe plusieurs sessions de base de données actives.|  

4. Dans les champs **Code dimension principale 1** et/ou **Code dimension principale 2**, entrez les nouvelles dimensions. Les dimensions actuelles sont affichées en gris derrière les champs.
5. En fonction du mode, effectuez l’une des opérations suivantes :
    * Dans mode **Séquentiel**, choisissez l’action **Démarrer**.
    * Dans mode **Parallèle**, choisissez l’action **Préparer**.

    L'onglet **Écritures journal** contient des informations sur les dimensions qui seront modifiées.
7. Déconnectez-vous de [!INCLUDE[prod_short](includes/prod_short.md)], puis reconnectez-vous.
8. Choisissez l'action **Démarrer** pour démarrer le traitement parallèle des changements de dimension. <!--is this also dependent on the mode?-->

### <a name="example-of-dimension-setup"></a>Exemple de configuration de dimension
Imaginons que votre compagnie souhaite suivre les transactions selon la structure organisationnelle et les situations géographiques. Pour ce faire, vous pouvez configurer deux dimensions sur la page **Dimensions** :

* **REGION**  
* **DEPARTEMENT**  

| Code | Nom | Libellé code | Libellé filtre |
| --- | --- | --- | --- |
| REGION |Région |Zone de recouvrement |Filtre zone |
| DEPARTEMENT |Département |Code emplacement immo |Filtre département |

Pour **ZONE**, vous pouvez ajouter les sections analytiques suivantes :

| Code | Nom | Type de valeur de dimension |
| --- | --- | --- |
| 10 |Amériques |Début total |
| 20 |Amérique du Nord |Standard |
| 30 |Pacifique |Standard |
| 40 |Amérique du Sud |Standard |
| 50 |Amériques, Total |Fin total |
| 60 |Europe |Début total |
| 70 |INTRA |Standard |
| 80 |Non-UE |Standard |
| 90 |Europe, Total |Fin total |

Pour les deux zones géographiques principales, Amériques et Europe, ajoutez des sous-catégories pour les régions en décalant les valeurs de dimension. Cela vous permet de déclarer les ventes ou les dépenses dans les comtés, et d'obtenir les totaux des zones géographiques plus étendues. Vous pouvez également choisir d'utiliser des pays ou régions en tant que valeurs de dimension, ou des comtés ou des villes, en fonction de votre entreprise.

> [!NOTE]  
>   Pour configurer une hiérarchie, veillez à trier les codes dans l'ordre alphabétique. Ceci inclut les codes des sections analytiques fournis dans [!INCLUDE[prod_short](includes/prod_short.md)].  

Pour **DÉPARTEMENT**, vous pouvez ajouter les sections analytiques suivantes :

| Code | Nom | Type de valeur de dimension |
| --- | --- | --- |
| ADMIN |Administration |Standard |
| FABR |Fabrication |Standard |
| VENTES |Ventes |Standard |

Avec cette configuration, vous pouvez ajouter vos deux dimensions en tant que dimensions principales sur la page **Configuration du grand livre**. Cela signifie que vous pouvez utiliser ZONE et DÉPARTEMENT comme filtres pour les écritures du grand livre, ainsi que dans tous les rapports et les tableaux d'analyse. Les deux dimensions principales sont mises à disposition automatiquement pour être utilisées dans les lignes écriture et les en-têtes document comme raccourcis de dimension.

## <a name="getting-an-overview-of-dimensions-used-multiple-times"></a>Affichage d'un aperçu des dimensions utilisées plusieurs fois
La page **Dimensions par défaut - Multiples** spécifie la manière dont un groupe de comptes utilise les dimensions et valeurs de dimension. Vous pouvez effectuer cette opération en sélectionnant plusieurs comptes, et en spécifiant des dimensions et valeurs de dimension par défaut pour tous les comptes sélectionnés dans la liste des comptes. Lorsque vous spécifiez des dimensions par défaut pour les comptes sélectionnés, l'application propose ces dimensions et valeurs de dimension chaque fois que l'un de ces comptes est utilisé, par exemple sur une ligne journal. Le report des écritures est ainsi facilité, car les champs de dimension sont renseignés automatiquement. Cependant, les valeurs de dimension proposées peuvent être modifiées, par exemple sur une ligne journal.

La page **Dimensions par défaut - Multiples** contient les champs suivants :

|Champ|Description|
|-----|-----------|  
|**Code axe analytique**|Affiche toutes les dimensions définies comme dimensions par défaut sur un ou plusieurs comptes sélectionnés. Si vous cliquez sur le champ, vous pouvez visualiser la liste de toutes les dimensions disponibles. Si vous sélectionnez une dimension, la dimension sélectionnée est définie comme dimension par défaut pour tous les comptes sélectionnés.|
|**Code section**|Affiche une valeur de dimension ou le terme (Conflit). Si le champ indique une valeur de dimension, tous les comptes sélectionnés ont la même valeur de dimension par défaut pour une dimension donnée. Si le champ indique le terme (Conflit), les comptes sélectionnés n'ont pas tous la même valeur de dimension par défaut pour une dimension donnée. Si vous cliquez sur le champ, vous pouvez visualiser la liste de toutes les valeurs de dimension disponibles pour une dimension. Si vous sélectionnez une valeur de dimension, la valeur de dimension sélectionnée est définie comme valeur de dimension par défaut pour tous les comptes sélectionnés.|
|**Contrôle validation**|Affiche une règle de report valeur ou le terme (Conflit). Si le champ indique une règle de report valeur, tous les comptes sélectionnés ont la même règle de report valeur pour une valeur de dimension donnée. Si le champ indique le terme (Conflit), les comptes sélectionnés n'ont pas tous la même règle de report valeur pour une valeur de dimension donnée. Si vous cliquez sur le champ Report valeur, vous pouvez visualiser la liste des règles de report valeur. Si vous sélectionnez une règle de report valeur, elle s'applique à tous les comptes sélectionnés.|

## <a name="using-dimensions"></a>Utilisation des dimensions
Dans un document tel qu'un document de vente, vous pouvez ajouter des informations de dimension pour une seule ligne document et pour le document lui-même. Par exemple, sur la page **Document de vente**, vous pouvez saisir des valeurs de dimension pour les deux premiers raccourcis dimensions directement sur les lignes vente individuelles et ajouter des informations de dimension complémentaires si vous cliquez sur le bouton **Dimensions**.  

Si vous travaillez plutôt sur un journal, vous pouvez également ajouter à une écriture des informations de dimension de la même manière, si vous avez configuré des raccourcis de dimension en tant que champs directement dans les lignes journal.  

Vous pouvez configurer des axes analytiques par défaut pour des comptes ou des types de compte, de sorte que les axes et les sections analytiques soient renseignés automatiquement.

### <a name="to-view-global-dimensions-in-ledger-entry-pages"></a>Pour afficher les dimensions principales dans les pages écriture  
Les dimensions principales sont toujours définies et nommées par la compagnie\-. Pour visualiser les dimensions globales de votre compagnie, ouvrez la page **Configuration du grand livre**.  

Dans une page écriture, vous pouvez voir si des dimensions principales sont associées aux écritures. Les deux axes principaux sont différents des autres axes car vous pouvez les utiliser en tant que filtres n'importe où dans [!INCLUDE[prod_short](includes/prod_short.md)].  

1.  Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Plan comptable**, puis sélectionnez le lien associé.  
2.  Sur la page **Plan comptable**, choisissez l'action **Écritures**.  
3.  Pour ne visualiser que certaines écritures, positionnez au moins un filtre sur la page.  
4.  Pour visualiser toutes les dimensions d'une écriture, sélectionnez l'écriture, puis cliquez sur l'action **Dimensions**.  

> [!NOTE]  
>  La page **Dimensions - Écritures** affiche les dimensions d'une écriture à la fois. Lorsque vous faites défiler les écritures, le contenu de la page **Dimensions - Écritures** est modifié en conséquence.

## <a name="troubleshooting-dimensions-errors"></a>Dépannage des erreurs liées aux dimensions
Lorsque vous reportez des documents ou des lignes journal qui contiennent des dimensions, différentes erreurs peuvent survenir, généralement liées à un défaut de configuration ou d'affectation des dimensions.

> [!NOTE]
> Dans la liste suivante des messages d'erreur potentielle, les codes *%X* sont des espaces réservés pour les variables de données qui le message réel contient dans l'interface utilisateur selon le contexte. Par exemple, *%1 %2 est bloqué.* pourrait s'afficher dans l'interface utilisateur comme « La ZONE du code de dimension est bloquée ».  

|Problème|Message d'erreur|Solution possible|
|-----|-------------|-----------------|
|Dimension bloquée|%1 %2 est bloqué.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la dimension bloquée et débloquez-la.<br />- Supprimez la ligne ensemble de dimensions pour la dimension bloquée.|
|Dimension supprimée|%1 %2 est introuvable.|- Restaurez la dimension manquante.<br />- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la dimension manquante et ajoutez-la.<br />- Supprimez la ligne ensemble de dimensions pour la dimension manquante.|
|Valeur de dimension bloquée|%1 %2 - %3 est bloqué.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la valeur de dimension bloquée et débloquez-la.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension bloquée.|
|Valeur de dimension supprimée|   %1 pour %2 est manquant.|- Restaurez la valeur de dimension manquante.<br />- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la valeur de dimension manquante et ajoutez-la.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension manquante.|
|Valeur de dimension interdite|Le type de valeur de dimension pour %1 %2 - %3 ne doit pas être %4.|- Modifiez le champ **Type de valeur de dimension** sur la page **Valeurs de dimension** avec **Standard** ou **Début total**.<br />- Supprimez la ligne ensemble de dimensions pour la valeur de dimension bloquée.|
|Combinaison de dimensions bloquée|Les dimensions %1 et %2 ne peuvent pas être utilisées ensemble.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la combinaison de dimensions bloquée et débloquez-la.<br />- Modifiez une des lignes d'ensembles d'autorisation en conflit pour la combinaison de dimensions.|
|Combinaison de valeurs de dimension bloquée|Les combinaisons de dimensions %1 - %2 et %3 - %4 ne peuvent pas être utilisées ensemble.|- Recherchez les documents non reportés contenant l'ensemble de dimensions avec la combinaison de valeurs de dimensions bloquée et débloquez-la.<br />- Modifiez une des lignes d'ensembles d'autorisation en conflit pour la combinaison de valeurs de dimension.|
|Code de valeur de dimension vide pour la dimension par défaut où le champ **Report valeur** contient **Code obligatoire**|- Sélectionnez un %1 pour le %2 %3.<br />- Sélectionnez un %1 pour le %2 %3 pour %4 %5.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez une valeur de dimension non vide pour la dimension en conflit dans l'ensemble de dimensions.|
|Code de valeur de dimension erroné pour la dimension par défaut où le champ **Report valeur** contient **Même code**|- Sélectionnez %1 %2 pour le %3 %4.<br />- Sélectionnez %1 %2 pour le %3 %4 pour %5 %6.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez la valeur de dimension requise pour la dimension en conflit dans l'ensemble de dimensions.|
|Code de valeur de dimension non vide pour la dimension par défaut vide où le champ **Report valeur** contient **Même code**|-%1 %2 doit être vierge.<br />-%1 %2 doit être vierge pour %3 %4.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Saisissez un code de valeur de dimension vide pour la dimension en conflit dans l'ensemble de dimensions.|
|Valeur de dimension inattendue pour la dimension par défaut où le champ **Report valeur** contient **Pas de code**|-%1 %2 ne doit pas être mentionné.<br />- %1 %2 ne doit pas être mentionné pour %3 %4.|- Modifiez le champ **Report valeur** sur la page **Dimension par défaut**.<br />- Supprimez la ligne en conflit de l'ensemble de dimensions.|

## <a name="see-related-training-at-microsoft-learn"></a>Voir la formation associée sur [Microsoft Learn](/learn/modules/dimensions-dynamics-365-business-central/index)

## <a name="see-also"></a>Voir aussi
[Veille économique](bi.md)  
[Finance](finance.md)  
[Analyse des données par dimensions](bi-how-analyze-data-dimension.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]