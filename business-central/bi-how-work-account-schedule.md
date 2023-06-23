---
title: Créer des rapports financiers avec des données financières et des catégories de compte
description: Décrit comment utiliser des rapports financiers pour créer différentes vues et différents rapports pour l’analyse des données de performances financières.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bnielse
ms.topic: how-to
ms.date: 02/27/2023
ms.custom: bap-template
ms.search.keywords: 'bi, power BI, analysis, KPI, account schedule, financial report'
ms.search.form: '103, 104, 108, 195, 196, 197, 198, 489, 490, 764, 765, 766'
---
# <a name="prepare-financial-reporting-with-financial-data-and-account-categories" />Préparer la génération de rapports financiers avec des données financières et des catégories de compte

Les rapports financiers vous donnent un aperçu des données financières enregistrées dans votre plan comptable (COA). Les rapports financiers analysent les chiffres des comptes du grand livre (GL) et comparent les écritures et les écritures budget. Les résultats s’affichent dans les graphiques et les rapports de votre tableau de bord, comme le graphique Trésorerie et les rapports État des résultats et Bilan.

Vous accédez à ces deux rapports, par exemple, avec l’action **Relevés financiers** dans les tableaux de bord Gestionnaire d’activité et Comptable.  

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des exemples de rapports financiers que vous pouvez utiliser immédiatement. Vous pouvez également configurer vos propres lignes et colonnes pour spécifier les chiffres à comparer. Par exemple, vous pouvez créer des rapports financiers pour calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. Vous pouvez créer un nombre illimité d’états financiers personnalisés.  

La configuration des rapports financiers exige une compréhension des données financières du plan comptable. Par exemple, vous pouvez afficher les écritures en tant que pourcentages des écritures budget; mais cela nécessite d’avoir créé des budgets. Pour en savoir plus, voir [Créer des budgets GL](finance-how-create-budgets.md).

## <a name="financial-reports" />Rapports financiers

Les rapports financiers organisent les comptes à partir de votre plan comptable de manière à faciliter la présentation des données. Vous pouvez configurer différentes présentations pour définir les informations que vous souhaitez extraire du plan comptable. Les rapports financiers fournissent un emplacement pour les calculs qui ne peuvent pas être effectués directement dans le plan comptable. Par exemple, vous pouvez créer des sous-totaux pour des groupes de comptes, puis inclure ce total dans d'autres totaux. Un autre exemple consiste à calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. De plus, vous pouvez filtrer les écritures et les écritures budget, par exemple, par solde période ou par montant débit.

Vous pouvez également comparer deux ou plusieurs rapports financiers et définitions de colonne à l’aide de formules, qui vous permettent d’effectuer ce qui suit ;

* Créez des rapports financiers personnalisés.
* Créez autant de rapports financiers que nécessaire, en attribuant à chacun un nom unique ;
* Configurez différentes présentations de rapports et imprimez les rapports avec les chiffre actuels.

## <a name="gl-account-categories" />Catégories de compte GL

Vous pouvez utiliser les catégories de compte du grand livre pour modifier la présentation de vos relevés financiers. Par exemple, une fois que vous avez configuré vos catégories de compte sur la page **Catégories de compte GL**, vous pouvez choisir l’action **Générer les rapports financiers**, et mettre à jour les rapports financiers sous-jacents pour les rapports financiers de base. La prochaine fois que vous exécuterez l’un de ces rapports, par exemple le rapport **Relevé de solde**, de nouveaux totaux et sous-entrées seront ajoutés.

> [!NOTE]
> Les catégories de compte de niveau supérieur, telles que le nœud **Passif**, sont fixes et vous ne pouvez pas ajouter les vôtres. Cependant, vous pouvez supprimer et ajouter des catégories de compte à des niveaux inférieurs et définir la façon dont le rapport financier associé apparaît dans les rapports.
>
> Vous devez créer et structurer vos propres catégories de compte GL de niveau inférieur à partir de zéro, dans une hiérarchie si nécessaire, plutôt que d’essayer de réorganiser les catégories existantes. Par exemple, vous pouvez restructurer le nœud **Passif** pour contenir un nouveau nœud **Équité** suivi des nœuds **Passif à court terme** et **Passif à long terme**.

## <a name="create-a-new-financial-report" />Créer un rapport financier

Vous utilisez les rapports financiers pour analyser les comptes du grand livre ou pour comparer les écritures GL et les écritures budget. Par exemple, vous pouvez afficher les écritures en tant que pourcentages des écritures budget.

Les rapports financiers dans la version standard de [!INCLUDE[prod_short](includes/prod_short.md)] peuvent ne pas convenir aux besoins de votre entreprise. Pour créer rapidement vos propres rapports financiers, commencez par en copier un existant, tel que décrit à l’étape trois ci-dessous.

> [!TIP]
> Après avoir créé un rapport financier, vous pouvez utiliser la page **Rapport financier** pour prévisualiser et valider votre rapport financier nouvellement défini. Pour ouvrir la page, sélectionnez l’action **Modifier le rapport financier**.  

> [!NOTE]
> Lorsque vous ouvrez un rapport financier en mode Afficher ou Modifier, le volet Filtre est disponible. Cependant, n’utilisez pas le volet pour définir des filtres pour les données de votre rapport. Les filtres peuvent provoquer des erreurs ou ne pas réellement filtrer les données. À la place, utilisez les champs de filtre des raccourcis **Options** et **Dimensions**.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.  
2. Sur la page **Rapports financiers**, choisissez l’action **Nouveau** pour créer un nom de rapport financier.
3. Sinon, si vous souhaitez réutiliser les paramètres d’un rapport financier existant, choisissez l’action **Copier le rapport financier**.
4. Renseignez les champs selon vos besoins. Dans le champ **Définition de colonne**, sélectionnez une définition existante, que vous pourrez modifier ultérieurement si vous le souhaitez.

    Les définitions de colonne spécifient les paramètres selon lesquels les données financières sont affichées dans les lignes. Par exemple, une définition de colonne peut contenir quatre colonnes pour vous permettre de comparer le solde période et le solde pour une même période de l’exercice actuel et du précédent. Pour plus d’informations, consultez la section [Modifier une définition de colonne](bi-how-work-account-schedule.md#edit-a-column-definition).

5. Choisissez l’action **Modifier la définition de ligne**.
6. Choisissez les actions **Insérer des comptes GL**, **Insérer des comptes CF**, et **Insérer des types de coût** pour créer une ligne pour chaque élément financier que vous souhaitez analyser. Par exemple, vous pouvez avoir une ligne pour les actifs à court terme et une autre ligne pour les immobilisations. Pour avoir de l’inspiration, visualisez les rapports financiers de la compagnie de démonstration CRONUS.

    > [!NOTE]
    > Le champ **N° ligne** affiche les 10 premiers caractères d’un identificateur, par exemple, un numéro de compte. Si vous ajoutez des éléments avec des identificateurs qui commencent par les mêmes 10 caractères, vous aurez des doublons dans le champ **N° ligne** . Si nécessaire, vous pouvez modifier manuellement les identificateurs après avoir inséré les éléments. Les identificateurs complets sont affichés dans le champ **Totalisation**.

7. Sur la page **Rapports financiers**, choisissez l’action **Modifier le rapport financier** pour accéder au rapport financier qui en résulte.
8. Sur la page **Rapport financier**, dans le champ **Définition de colonne**, sélectionnez une autre définition de colonne pour explorer les données financières selon d’autres paramètres.
9. Cliquez sur **OK**.

Vous avez désormais défini la base suivante du rapport financier, les lignes de données financières à afficher, et une disposition existante de colonnes pour afficher les données sur les lignes selon des paramètres personnalisés. Si la définition de colonne par défaut que vous avez sélectionnée à l’étape 4 ne vous convient pas, suivez les étapes de la section [Modifier une définition de colonne](#edit-a-column-definition).

### <a name="edit-a-column-definition" />Modifier une définition de colonne

Utilisez les définitions de colonne pour spécifier les colonnes à inclure dans le rapport. Par exemple, vous pouvez créer une présentation de manière à comparer le solde période et le solde pour une même période de l'exercice actuel et du précédent. Vous pouvez avoir jusqu’à 15 colonnes, ce qui est utile, par exemple, pour afficher les budgets sur 12 mois avec une colonne indiquant le total.

> [!NOTE]
> Une version imprimée/prévisualisée/enregistrée d’un rapport financier affiche un maximum de cinq colonnes. Par opposition, si un rapport financier est uniquement destiné pour l’analyse sur la page **Rapport financier**, vous pouvez créer autant de colonnes que vous le souhaitez.

1. Sur la page **Rapports financiers**, sélectionnez le rapport financier voulu, puis choisissez l’action **Modifier la définition de colonne**.
2. Sur la page **Définition de colonne**, créez une ligne pour chaque colonne de données financières affichées dans le rapport financier. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Cliquez sur **OK**.
4. Ouvrez la page **Rapport financier** de temps en temps pour vérifier que la nouvelle définition de colonne fonctionne comme prévu.

> [!NOTE]
> Les colonnes que vous définissez sur chaque ligne représentent les colonnes 3 et supérieures de la page **Rapport financier**. Les deux premières colonnes, **N° ligne** et **Description**, sont fixes.  

### <a name="create-a-column-that-calculates-percentages" />Créer une colonne qui calcule des pourcentages

Il se peut que vous vouliez inclure une colonne dans un rapport financier pour calculer des pourcentages d’un total. Par exemple, si vous avez des lignes qui ventilent des ventes par dimension, vous pouvez juger utile de disposer d’une colonne indiquant le pourcentage des ventes totales que représente chaque ligne.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
2. Sur la page **Rapports financiers**, sélectionnez un rapport financier.  
3. Choisissez l’action **Modifier le rapport financier** pour configurer une ligne de rapport financier et calculer le total sur lequel les pourcentages seront basés.  
4. Insérez une ligne juste au-dessus de la première ligne pour laquelle vous voulez afficher un pourcentage.  
5. Renseignez les champs de la ligne comme suit : dans le champ **Type totalisation**, entrez **Base de pourcentage**. Dans le champ **Totalisation**, saisissez une formule pour le total sur lequel le pourcentage sera basé. Par exemple, si la ligne 11 contient le total des ventes, saisissez **11**.  
6. Choisissez l’action **Modifier la définition de colonne** pour configurer une colonne.  
7. Renseignez les champs de la ligne comme suit : dans le champ **Type colonne**, sélectionnez **Formule**. Dans le champ **Formule**, saisissez une formule correspondant au montant pour lequel vous voulez calculer un pourcentage, suivie du symbole de pourcentage %. Ainsi, si le numéro de colonne N contient le solde période, saisissez **N%**.  
8. Répétez les étapes 4 à 7 pour chaque groupe de lignes que vous voulez ventiler par pourcentage.

## <a name="set-up-financial-reports-with-overviews" />Configurer des rapports financiers avec des aperçus

Vous pouvez utiliser un rapport financier pour créer un rapport comparant les chiffres du grand livre et les chiffres budgétés.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
2. Sur la page **Rapports financiers**, sélectionnez un rapport financier.  
3. Choisissez l’action **Modifier la définition de ligne**.  
4. Sur la page **Définition de ligne**, sélectionnez le nom du rapport financier par défaut dans le champ **Nom**.
5. Choisissez l’action **Insérer des comptes du grand livre**.  
6. Sélectionnez les comptes à inclure dans votre relevé, puis cliquez sur **OK**.

    Ces comptes sont à présent insérés dans votre rapport financier. Si vous le souhaitez, vous pouvez aussi modifier la définition de colonne.  
7. Choisissez l’action **Modifier le rapport financier**.  
8. Sur la page **Rapport financier**, sur le raccourci **Dimensions**, définissez le filtre budget sur le nom du filtre souhaité.  
9. Cliquez sur **OK**.  

Vous pouvez maintenant copier et coller votre budget dans un classeur.  

## <a name="comparing-accounting-periods-using-period-formulas" />Comparaison de périodes comptables à l’aide de formules de période

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

## <a name="print-and-save-financial-reports" />Imprimer et enregistrer des rapports financiers

Vous pouvez imprimer des rapports financiers à l’aide des services d’impression de votre appareil. [!INCLUDE[prod_short](includes/prod_short.md)] offre également la possibilité d’enregistrer les rapports sous forme de classeurs Microsoft Excel, de documents Microsoft Word, de fichiers PDF et XML.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
2. Sur la page **Rapports financiers**, sélectionnez le rapport à imprimer, puis sélectionnez l’action **Imprimer**.
3. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
4. Dans le champ **Imprimante**, sélectionnez l’appareil auquel le rapport sera envoyé.
    1. L’option **(Géré par le navigateur)** indique qu’il n’y a pas d’imprimante désignée pour le rapport. Dans ce cas, le navigateur gérera l’impression et affichera une expérience standard, où vous pourrez choisir une imprimante locale connectée à votre appareil. **(Géré par le navigateur)** n'est pas disponible dans l'application mobile [!INCLUDE[prod_short](includes/prod_short.md)] ou application pour Microsoft Teams.
5. Choisissez l’action **Imprimer**.

### <a name="schedule-a-financial-report-or-save-as-a-pdf-word-or-excel-document" />Programmer un rapport financier ou l’enregistrer au format PDF, Word ou Excel

Un rapport financier peut être enregistré sous forme de fichier dans différents formats, tels que PDF, XML, Word ou Excel. Alternativement, [!INCLUDE[prod_short](includes/prod_short.md)] peut être configuré pour générer des rapports financiers récurrents :

1. Sélectionnez l’![icône en forme d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
2. Sur la page **Rapports financiers**, sélectionnez l’action **Imprimer**.
3. Définissez le rapport en conséquence, puis choisissez l’action **Envoyer à**.
4. Sélectionnez le format de fichier ou l’action **Programmer**, puis choisissez **OK**.
5. Pour générer un rapport financier programmé ou récurrent, remplissez les champs. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)].
   * Pour les rapports financiers récurrents, définissez les champs **Date/heure de début au plus tôt** et **Date/heure d’expiration** avec la première et la dernière date, respectivement, pour générer le rapport financier. Sélectionnez également les jours où le rapport est généré en définissant le champ **Formule de la date de la prochaine exécution** en suivant le format expliqué dans la section [Utiliser des formules de date](ui-enter-date-ranges.md#use-date-formulas).

## <a name="importing-or-exporting-financial-reports" />Importation ou exportation de rapports financiers

Vous pouvez importer et exporter des rapports financiers sous forme de packages de configuration RapidStart, utiles pour partager les informations avec d’autres compagnies, par exemple. Le package est créé dans un fichier .rapidstart, qui compresse le contenu.

### <a name="import-and-export-financial-reports" />Importer et exporter des rapports financiers

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Rapports financiers**, puis choisissez le lien associé.
2. Choisissez le rapport financier, puis sélectionnez l’action **Importer le rapport financier** ou **Exporter le rapport financier**, selon ce que vous voulez faire.

> [!NOTE]
> Lorsque vous importez des rapports financiers, les enregistrements existants portant les mêmes noms que ceux que vous importez seront supprimés.

## <a name="see-related-microsoft-trainingtrainingmodulesconfigure-financial-reports-dynamics-365-business-centralindex" />Voir la [formation Microsoft](/training/modules/configure-financial-reports-dynamics-365-business-central/index) associée.

## <a name="see-also" />Voir aussi .

[Exécuter et imprimer des rapports](ui-work-report.md)  
[Décisionnel pour le secteur de la finance](bi.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Les écritures comptables et le plan comptable](finance-general-ledger.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
