---
title: Créer des rapports financiers avec des données financières et des catégories de compte
description: Décrit comment utiliser des rapports financiers pour créer différentes vues et différents rapports pour l’analyse des données de performances financières.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 03/27/2024
ms.custom: bap-template
ms.search.keywords: 'bi, power BI, analysis, KPI, account schedule, financial report'
ms.search.form: '103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766'
ms.service: dynamics-365-business-central
---
# Préparer Financial Reporting avec des données financières et des catégories de compte

La fonctionnalité **Rapports financiers** vous donne un aperçu des données financières enregistrées dans votre plan comptable (COA). Vous pouvez configurer les rapports financiers pour analyser les chiffres dans les comptes du grand livre (GL) et comparer les écritures GL et les écritures budget. Les résultats s’affichent dans les graphiques et les rapports de votre tableau de bord, comme le graphique Trésorerie et les rapports État des résultats et Bilan. Vous accédez à ces deux rapports, par exemple, avec l’action **États financiers** dans les tableaux de bord Gestionnaire d’activité et Comptable.  

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des exemples de rapports financiers que vous pouvez utiliser immédiatement comme modèles. Vous pouvez également configurer vos propres rapports pour spécifier les chiffres à comparer. Par exemple, vous pouvez créer des rapports financiers pour calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. Le nombre de rapports financiers que vous pouvez créer est illimité et ne nécessite aucune intervention d’un développeur.  

## Conditions préalables au Financial Reporting

La configuration des rapports financiers exige une compréhension de la structure du plan comptable. Il y a trois concepts clés auxquels vous devrez probablement prêter attention avant de concevoir vos rapports financiers :

- Mappez les comptes de report grand livre aux catégories de comptes du grand livre.
- Concevez la façon dont vous utilisez les dimensions.
- Configurer les budgets GL

Les catégories de comptes du grand livre simplifient les définitions de vos rapports financiers et les rendent plus résistantes aux changements dans la structure du plan comptable. Pour en savoir plus, voir [Utiliser les catégories de compte du grand livre pour modifier la présentation de vos états financiers](#use-gl-account-categories-to-change-the-layout-of-your-financial-statements).

La configuration de dimensions vous permet de découper vos données financières de manière logique pour votre organisation. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md). 

Si vous voulez afficher les écritures du grand livre en tant que pourcentages des écritures budget, vous devez créer des budgets GL. Pour en savoir plus, voir [Créer des budgets GL](finance-how-create-budgets.md).

## Rapports financiers

Les rapports financiers organisent les comptes à partir de votre plan comptable de manière à faciliter la présentation des données. Vous pouvez configurer différentes présentations pour définir les informations que vous souhaitez extraire du plan comptable. Les rapports financiers fournissent aussi un emplacement pour les calculs qui ne peuvent pas être effectués directement dans le plan comptable. Par exemple, vous pouvez créer des sous-totaux pour des groupes de comptes, puis inclure ce total dans d'autres totaux. Un autre exemple consiste à calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. De plus, vous pouvez filtrer les écritures et les écritures budget, par exemple, par solde période ou par montant débit.

> [!NOTE] 
> D’un point de vue mathématique, on peut considérer qu’un rapport financier est défini par deux éléments :
>
> - Un vecteur de définitions de lignes qui définissent ce qui doit être calculé.
> - Un vecteur de définitions de colonnes qui définit les données pour le calcul.
>
> Le rapport financier est alors le produit extérieur de ces deux vecteurs, où chaque valeur de cellule est calculée selon la formule de la ligne appliquée à la définition des données de la colonne.

:::image type="content" source="media/financial-report-definition.svg" alt-text="Montre comment un rapport financier est construit à partir d’une définition de ligne et d’une définition de colonne." lightbox="media/financial-report-definition.svg":::

Le **Rapports financiers** page montre comment tous les rapports financiers suivent un modèle composé des attributs suivants :

* Nom (code)
* Désignation
* Définition de ligne
* Définition de colonne

:::image type="content" source="media/financial-reports.png" alt-text="Montre comment tous les rapports financier est construit à partir d’une définition de ligne et d’une définition de colonne." lightbox="media/financial-reports.png":::

> [!NOTE]
> Les exemples de rapports financiers présentés dans [!INCLUDE[prod_short](includes/prod_short.md)] ne sont pas prêts à être utilisés directement. En fonction de la façon dont vous configurez vos comptes du grand livre, vos dimensions, vos catégories de comptes du grand livre et vos budgets, vous devez ajuster les exemples de définitions de lignes et de colonnes ainsi que les rapports financiers dans lesquels ils sont utilisés pour correspondre à votre configuration.

Vous pouvez également utiliser des formules pour comparer deux ou plusieurs rapports financiers et définitions de colonne. Les comparaisons permettent de faire les choses suivantes :

* Créez des rapports financiers personnalisés.
* Créez autant de rapports financiers que nécessaire, en attribuant à chacun un nom unique ;
* Configurez différentes présentations de rapports et imprimez les rapports avec les chiffre actuels.

## Parcours d’apprentissage : Créer des rapports financiers dans Microsoft Dynamics 365 Business Central

Vous souhaitez apprendre à créer des budgets, puis à utiliser des rapports financiers, des dimensions et des définitions de lignes et de colonnes pour générer les rapports financiers généralement nécessaires à la plupart des entreprises ?

Commencez par apprendre le parcours d’apprentissage [Créer des rapports financiers dans Microsoft Dynamics 365 Business Central](/training/paths/create-financial-reports-dynamics-365-business-central)

## Créer un rapport financier

Vous utilisez les rapports financiers pour analyser les comptes du grand livre ou pour comparer les écritures GL et les écritures budget. Par exemple, vous pouvez afficher les écritures en tant que pourcentages des écritures budget.

Les rapports financiers dans la version standard de [!INCLUDE[prod_short](includes/prod_short.md)] peuvent ne pas convenir aux besoins de votre entreprise. Pour créer rapidement vos propres rapports financiers, commencez par en copier un existant, tel que décrit à l’étape trois ci-dessous.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.  
1. Sur la page **Rapports financiers**, choisissez l’action **Nouveau** pour créer un nom de rapport financier. Sinon, pour réutiliser les paramètres d’un rapport financier existant, choisissez l’action **Copier le rapport financier**.
1. Remplissez le nom court du rapport (celui-ci ne peut pas être modifié) et la description.
1. Choisissez une définition de ligne et une définition de colonne.
1. Vous pouvez éventuellement choisir des vues d’analyse pour les définitions de ligne et de colonne.
1. Choisissez l’action **Modifier le rapport financier** pour accéder à plus de propriétés sur le rapport financier.
1. Dans l’onglet rapide **Options**, vous pouvez modifier la description du rapport, modifier les définitions de ligne et de colonne et définir comment afficher les dates. Vous pouvez afficher les dates par jour, semaine, mois, trimestre, année ou périodes comptables. Pour en savoir plus, accédez à [Comparaison de périodes comptables à l’aide de formules de période](#comparing-accounting-periods-using-period-formulas).
1. Dans l’onglet rapide **Dimensions** , vous pouvez définir des filtres de dimension pour le rapport.
1. Vous pouvez prévisualiser le rapport dans la zone située sous l’onglet rapide **Dimensions** .

> [!TIP]
> Après avoir créé un rapport financier, vous pouvez utiliser la page **Rapport financier** pour prévisualiser et le valider. Pour ouvrir la page, sélectionnez l’action **Afficher le rapport financier**.  

> [!NOTE]
> Lorsque vous ouvrez un rapport financier en mode Afficher ou Modifier, le volet Filtre est disponible. N’utilisez pas le Volet Filtre pour définir des filtres pour les données de votre rapport. Ces filtres peuvent provoquer des erreurs ou ne pas réellement filtrer les données. Utilisez plutôt les champs des **Options** et **Dimensions** FastTabs pour configurer des filtres pour le rapport.

### Créer ou modifier une définition de ligne

Les définitions de lignes dans les rapports financiers fournissent un emplacement pour les calculs qui ne peuvent pas être effectués directement dans le plan comptable. Par exemple, vous pouvez créer des sous-totaux pour des groupes de comptes, puis inclure ce total dans d'autres totaux. Vous pouvez également calculer des étapes intermédiaires qui ne sont pas affichées dans le rapport final.

1. Sur la page **Rapports financiers**, sélectionnez le rapport financier voulu, puis sélectionnez l’action **Modifier la définition de ligne**.
1. Choisissez les actions **Insérer des comptes GL**, **Insérer des comptes CF**, et **Insérer des types de coût** pour créer une ligne pour chaque élément financier que vous souhaitez analyser. Par exemple, vous pouvez avoir une ligne pour les actifs à court terme et une autre ligne pour les immobilisations. Pour avoir de l’inspiration, explorez les rapports financiers de la compagnie de démonstration CRONUS.

    > [!NOTE]
    > Le champ **N° ligne** affiche les 10 premiers caractères d’un identificateur, par exemple, un numéro de compte. Si vous ajoutez des éléments avec des identificateurs qui commencent par les mêmes 10 caractères, vous aurez des doublons dans le champ **N° ligne** . Si nécessaire, vous pouvez modifier manuellement les identificateurs après avoir inséré les éléments. Les identificateurs complets sont affichés dans le champ **Totalisation**.

> [!NOTE]
> Les colonnes que vous définissez sur chaque ligne de la définition de ligne représentent les colonnes 3 et supérieures de la page **Rapport financier**. Les deux premières colonnes, **N° ligne** et **Description**, sont fixes.  

### Créer ou modifier une définition de colonne

Utilisez les définitions de colonne pour spécifier les colonnes à inclure dans le rapport. Par exemple, vous pouvez créer une disposition de rapport de manière à comparer le solde période et le solde pour une même période de l'exercice actuel et du précédent. Vous pouvez avoir jusqu’à 15 colonnes dans une définition de colonne. Par exemple, plusieurs colonnes sont utiles pour afficher les budgets sur 12 mois avec une colonne indiquant le total.

> [!NOTE]
> Une version imprimée/prévisualisée/enregistrée d’un rapport financier affiche un maximum de cinq colonnes. Par opposition, si un rapport financier est uniquement destiné pour l’analyse sur la page **Rapport financier**, vous pouvez créer autant de colonnes que vous le souhaitez.

1. Sur la page **Rapports financiers**, sélectionnez le rapport financier voulu, puis choisissez l’action **Modifier la définition de colonne**.
1. Sur la page **Définition de colonne**, créez une ligne pour chaque colonne de données financières affichées dans le rapport financier. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Cliquez sur **OK**.
1. Ouvrez la page **Rapport financier** de temps en temps pour vérifier que la nouvelle définition de colonne fonctionne comme prévu.

### Créer une définition de colonne pour calcule des pourcentages

Vous voulez peut-être inclure une colonne dans un rapport financier pour calculer des pourcentages d’un total. Par exemple, si vous avez des lignes qui ventilent des ventes par dimension, vous pouvez juger utile de disposer d’une colonne indiquant le pourcentage des ventes totales que représente chaque ligne.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
1. Sur la page **Rapports financiers**, sélectionnez un rapport financier.  
1. Choisissez l’action **Modifier le rapport financier** pour configurer une ligne de rapport financier et calculer le total sur lequel le pourcentage est basé.  
1. insérez une ligne juste au-dessus de la première ligne pour laquelle vous voulez afficher un pourcentage.  
1. Renseignez les champs de la ligne comme suit : dans le champ **Type totalisation**, entrez **Base de pourcentage**. Dans le champ **Totalisation**, saisissez une formule pour le total sur lequel le pourcentage sera basé. Par exemple, si la ligne 11 contient le total des ventes, saisissez **11**.  
1. Choisissez l’action **Modifier la définition de colonne** pour configurer une colonne.  
1. Renseignez les champs de la ligne qui suivent. Dans le champ **Type colonne**, sélectionnez **Formule**. Dans le champ **Formule**, saisissez une formule correspondant au montant pour lequel vous voulez calculer un pourcentage, suivie du symbole de pourcentage %. Ainsi, si le numéro de colonne N contient le solde période, saisissez **N%**.  
1. Répétez les étapes 4 à 7 pour chaque groupe de lignes que vous voulez ventiler par pourcentage.

## Utiliser les catégories de compte du grand livre pour modifier la présentation de vos états financiers

Vous pouvez utiliser les catégories de compte du grand livre pour modifier la présentation de vos relevés financiers. Par exemple, après avoir configuré vos catégories de compte sur la page **Catégories de compte du grand livre**, vous pouvez choisir l’action **Générer les rapports financiers**, et mettre à jour les rapports financiers sous-jacents pour les rapports financiers de base. La prochaine fois que vous exécuterez l’un de ces rapports, par exemple le rapport **Relevé de solde**, de nouveaux totaux et des sous-entrées seront ajoutés.

Un autre avantage de l’utilisation des catégories de comptes du grand livre par rapport aux comptes du grand livre bruts dans vos définitions de lignes est qu’une modification dans la structure de votre plan comptable n’affecte pas vos rapports financiers.

> [!NOTE]
> Les catégories de compte de niveau supérieur, telles que le nœud **Passif**, sont fixes et vous ne pouvez pas ajouter les vôtres. Cependant, vous pouvez supprimer et ajouter des catégories de compte à des niveaux inférieurs et définir la façon dont le rapport financier associé apparaît dans les rapports.
>
> Vous devez créer et structurer vos propres catégories de compte GL de niveau inférieur à partir de zéro, dans une hiérarchie si nécessaire, plutôt que d’essayer de réorganiser les catégories existantes. Par exemple, vous pouvez restructurer le nœud **Passif** pour contenir un nouveau nœud **Équité** suivi des nœuds **Passif à court terme** et **Passif à long terme**. Pour en savoir plus, consultez [Mappage des comptes GL aux catégories de comptes](finance-general-ledger.md#account-categories).

## Utilisation de dimensions dans les rapports financiers

En analyse financière, une dimension correspond à des données que vous ajoutez à une écriture comme une sorte de marqueur. Ces données permettent de regrouper des écritures dotées de caractéristiques similaires, telles que les clients, les régions, les produits et les représentants, et de récupérer facilement ces groupes à des fins d'analyse. Vous pouvez utiliser les dimensions sur des écritures de journaux, de documents et de budgets.

Chaque dimension décrit l’objet de l’analyse. Une analyse à deux axes, par exemple, est une analyse des ventes par zone. En utilisant plus de deux dimensions lors de la création d’une entrée, vous pouvez effectuer une analyse plus complexe. Un exemple d’analyse complexe consiste à explorer les ventes par promotion de vente, par groupe de clients et par zone. Cela vous permet d’obtenir un meilleur aperçu de votre activité commerciale, comme la mesure du bon fonctionnement de votre société, les domaines dans lesquels elle prospère ou non, et ceux dans lesquels il est nécessaire d’affecter davantage de ressources. Ces informations vous aident à prendre des décisions commerciales plus éclairées. Pour plus d’informations, consultez [Utiliser les dimensions](finance-dimensions.md).

## Configurer des rapports financiers avec des aperçus

Vous pouvez utiliser un rapport financier pour créer un rapport comparant les chiffres du grand livre avec les chiffres budgétés.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
1. Sur la page **Rapports financiers**, sélectionnez un rapport financier.  
1. Choisissez l’action **Modifier la définition de ligne**.  
1. Sur la page **Définition de ligne**, sélectionnez le nom du rapport financier par défaut dans le champ **Nom**.
1. Choisissez l’action **Insérer des comptes du grand livre**.  
1. Sélectionnez les comptes à inclure dans votre relevé, puis cliquez sur **OK**.

    Ces comptes sont insérés dans le rapport financier. Si vous le souhaitez, vous pouvez aussi modifier la définition de colonne.  
1. Choisissez l’action **Modifier le rapport financier**.  
1. Sur la page **Rapport financier**, sur le raccourci **Dimensions**, définissez le filtre budget sur le nom du filtre souhaité.  
1. Cliquez sur **OK**.  

Vous pouvez maintenant copier et coller votre budget dans un classeur.  

## Comparaison de périodes comptables à l’aide de formules de période

Votre rapport financier peut comparer les résultats de différentes périodes comptables, par exemple le mois dernier et le même mois l’année précédente. Pour ce faire, ouvrez la page **Définition de colonne** et personnalisez-la en ajoutant le champ **Formule période comparaison** sous forme de colonne. Pour plus d’informations, consultez [Personnaliser votre espace de travail](ui-personalization-user.md). Vous pouvez ensuite définir ce champ sur une formule de période.  

Une période comptable ne doit pas nécessairement correspondre au calendrier. Toutefois, chaque exercice financier doit avoir le même nombre de périodes comptables, même si chaque période peut varier.  

[!INCLUDE[prod_short](includes/prod_short.md)] utilise la formule de période pour calculer la durée de la période de comparaison en fonction de la période représentée par le filtre date sur le rapport. La période de comparaison est basée sur la période de la date de début du filtre de date. Les abréviations utilisées pour les spécifications de période sont les suivantes :

| Abréviation | Désignation                                                                           |
| ------------ | ------------------------------------------------------------------------------------- |
| P            | Période.                                                                                |
| DP           | Dernière période d'un exercice financier, semestre ou trimestre.                                   |
| FP           | Période actuelle d'un exercice financier, semestre ou trimestre. Utilisez FP dans les formules pour définir la période qui commence ou termine la formule. Par exemple, EF\[1..PA\] désigne la durée entre le début de l'exercice financier en cours et la période actuelle.|
| EC           | Exercice financier. Par exemple, EF\[1..3\] désigne le premier trimestre de l’exercice financier actuel. |

Exemples de formule :

| Formule         | Désignation                                                                                     |
| --------------- | ----------------------------------------------------------------------------------------------- |
| \<Blank\>       | Période courante.                                                                                  |
| \-1P            | Période précédente.                                                                                 |
| \-1EC\[1..DP\]  | Ensemble de l’exercice financier précédent.                                                                     |
| \-1EC           | Période en cours dans l’exercice financier précédent.                                                          |
| \-1EC\[1..3\]   | Premier trimestre de l’exercice financier précédent.                                                           |
| \-1EC\[1..FP\]  | Du début de l'exercice financier précédent à période en cours dans l'exercice financier précédent, les deux périodes incluses. |
| \-1EC\[FP..DP\] | De la période en cours dans l'exercice financier précédent à la dernière période de l'exercice financier précédent, les deux périodes incluses.   |

Pour effectuer des calculs basés par périodes, vous devez entrer une formule dans le champ **Formule date comparaison** à la place. Par exemple, si le champ est défini sur -1A, [!INCLUDE [prod_short](includes/prod_short.md)] procède à une comparaison à la même période un an avant.

> [!NOTE]
> Il n’est pas toujours évident de déterminer les périodes comparées, car vous pouvez définir un filtre date sur un rapport qui couvre des dates différentes des périodes comptables représentées dans le plan comptable. Ainsi, si vous créez un rapport financier dans lequel vous souhaitez comparer cette période avec la même période l’année précédente, définissez le champ **Formule date comparaison** sur *-1EF*. Ensuite, vous exécutez le rapport le 28 février et définissez le filtre date sur Janvier et février. Par conséquent, le rapport financier compare les mois de janvier et février de cette année au mois de janvier de l’année précédente, qui est la seule période comptable terminée des deux pour l’année précédente.  

Pour plus d’informations, consultez [Utiliser des dates civiles et des heures](ui-enter-date-ranges.md).

## Imprimer et enregistrer des rapports financiers

Vous pouvez imprimer des rapports financiers à l’aide des services d’impression de votre appareil. [!INCLUDE[prod_short](includes/prod_short.md)] offre également la possibilité d’enregistrer les rapports sous forme de classeurs Excel, de documents Word, de fichiers PDF et XML.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
1. Sur la page **Rapports financiers**, sélectionnez le rapport à imprimer, puis sélectionnez l’action **Imprimer**.
1. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
1. Dans le champ **Imprimante**, sélectionnez l’appareil auquel le rapport sera envoyé.
    1. L’option **(Géré par le navigateur)** indique qu’il n’y a pas d’imprimante désignée pour le rapport. Dans ce cas, le navigateur gérera l’impression et affichera une expérience standard, où vous pourrez choisir une imprimante locale connectée à votre appareil. **(Géré par le navigateur)** n’est pas disponible dans l’application mobile [!INCLUDE[prod_short](includes/prod_short.md)] ou application pour Teams.
1. Choisissez l’action **Imprimer**.

### Programmer un rapport financier ou l’enregistrer au format PDF, Word ou Excel

Un rapport financier peut être enregistré sous forme de fichier dans différents formats, tels que PDF, XML, Word ou Excel. Alternativement, [!INCLUDE[prod_short](includes/prod_short.md)] peut générer des rapports financiers récurrents :

1. Sélectionnez l’![icône en forme d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
1. Sur la page **Rapports financiers**, sélectionnez l’action **Imprimer**.
1. Définissez le rapport en conséquence, puis choisissez l’action **Envoyer à**.
1. Sélectionnez le format de fichier ou l’action **Programmer**, puis choisissez **OK**.
1. Pour générer un rapport financier programmé ou récurrent, remplissez les champs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].<br><br>Pour les rapports financiers récurrents, définissez les champs **Date/heure de début au plus tôt** et **Date/heure d’expiration** avec la première et la dernière date, respectivement, pour générer le rapport financier. Sélectionnez également les jours où le rapport est généré en définissant le champ **Formule de la date de la prochaine exécution** en suivant le format expliqué dans la section [Utiliser des formules de date](ui-enter-date-ranges.md#use-date-formulas).

## Importer ou exporter des définitions de rapports financiers

Vous pouvez importer et exporter des rapports financiers/définitions de ligne sous forme de packages de configuration RapidStart, utiles pour partager les informations avec d’autres compagnies, par exemple. Le package est créé dans un fichier .rapidstart, qui compresse le contenu.

> [!NOTE]
> Lorsque vous importez des rapports financiers/définitions de ligne, les enregistrements existants portant les mêmes noms que ceux que vous importez seront remplacés par les nouvelles définitions. Notez que le package de configuration d’une définition de rapport n’écrasera aucune définition de ligne ou de colonne existante utilisée dans la définition de rapport.

Pour importer ou exporter des définitions de rapports financiers, procédez comme suit :

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
1. Choisissez le rapport financier, puis sélectionnez l’action **Importer le rapport financier** ou **Exporter le rapport financier**, selon ce que vous voulez faire.

Pour importer ou exporter des définitions de lignes de rapports financiers, procédez comme suit :

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Définitions de ligne**, puis sélectionnez le lien associé.
1. Choisissez la définition de ligne, puis choisissez l’action **Importer définition de ligne** ou **Exporter définition de ligne**, selon ce que vous voulez faire.

## Voir aussi .

[Exécuter et imprimer des rapports](ui-work-report.md)  
[Business Intelligence financière](bi.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
