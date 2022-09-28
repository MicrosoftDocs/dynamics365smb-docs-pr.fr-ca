---
title: Générer des rapports financiers à l'aide de tableaux d'analyse
description: Décrit comment utiliser des tableaux d'analyse pour créer différentes vues et différents rapports pour l'analyse des données de performances financières.
author: edupont04
ms.topic: conceptual
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.search.keywords: bi, power BI, analysis, KPI
ms.search.form: 103, 104, 197, 196, 195, 198, 490, 764, 765, 766
ms.date: 04/01/2021
ms.author: edupont
ms.openlocfilehash: 780034b8c53e7bb1704e13d0b1a00158583c11db
ms.sourcegitcommit: 3acadf94fa34ca57fc137cb2296e644fbabc1a60
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 09/19/2022
ms.locfileid: "9531739"
---
# <a name="prepare-financial-reporting-with-account-schedules-and-account-categories"></a>Préparer la génération de rapports financiers avec des tableaux d'analyse et des catégories de compte

Utilisez les tableaux d'analyse pour obtenir un aperçu des données financières enregistrées dans votre plan comptable. Les tableaux d'analyse analysent les chiffres des comptes du grand livre et comparent les écritures et les écritures budget. Les résultats s’affichent dans les graphiques et les rapports de votre tableau de bord, comme le graphique Trésorerie et les rapports État des résultats et Bilan.

Vous accédez à ces deux rapports, par exemple, avec l'action **États financiers** dans les tableaux de bord Gestionnaire d'activité et Comptable.  

[!INCLUDE[prod_short](includes/prod_short.md)] fournit des exemples de tableaux de comptes que vous pouvez utiliser immédiatement. Vous pouvez également configurer vos propres lignes et colonnes pour spécifier les chiffres à comparer. Par exemple, vous pouvez créer des tableaux d’analyse pour calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. Vous pouvez créer un nombre illimité d’états financiers personnalisés.  

La configuration de tableaux d'analyse exige une compréhension des données financières du plan comptable. Par exemple, vous pouvez afficher les écritures en tant que pourcentages des écritures budget; mais cela nécessite d’avoir créé des budgets. Pour plus d'informations, voir [Créer des budgets GL](finance-how-create-budgets.md).

## <a name="account-schedules"></a>Tableaux d’analyse

Les tableaux comptables organisent les comptes à partir de votre plan comptable de manière à faciliter la présentation des données. Vous pouvez configurer différentes présentations pour définir les informations que vous souhaitez extraire du plan comptable. Les tableaux d’analyse fournissent un emplacement pour les calculs qui ne peuvent pas être effectués directement dans le plan comptable. Par exemple, vous pouvez créer des sous-totaux pour des groupes de comptes, puis inclure ce total dans d'autres totaux. Un autre exemple consiste à calculer les profits bénéficiaires dans des dimensions tels que les départements ou les groupes client. De plus, vous pouvez filtrer les écritures et les écritures budget, par exemple, par solde période ou par montant débit.

Vous pouvez également comparer deux ou plusieurs tableaux d’analyse et présentations colonne à l’aide de formules, qui vous permettent d’effectuer ce qui suit;

* Créez des rapports financiers personnalisés.
* créer autant de tableaux d'analyse que nécessaire, chacun étant doté d'un nom unique ;
* Configurez différentes présentations de rapports et imprimez les rapports avec les chiffre actuels.

## <a name="gl-account-categories"></a>Catégories de compte du grand livre

Vous pouvez utiliser les catégories de compte du grand livre pour modifier la présentation de vos relevés financiers. Une fois que vous avez configuré vos catégories de compte sur la page **Catégories de compte du grand livre**, et que vous sélectionnez l'action **Générer les tableaux d'analyse**, les tableaux d'analyse sous-jacents pour les rapports financiers de base sont mis à jour. La prochaine fois que vous exécuterez l'un de ces rapports, par exemple le rapport **Bilan/État des résultats**, de nouveaux totaux et des sous-entrées seront ajoutés, en fonction de vos modifications.

> [!NOTE]
> Les catégories de compte de niveau supérieur, telles que le nœud **Passif**, sont fixes et vous ne pouvez pas ajouter les vôtres. Cependant, vous pouvez supprimer et ajouter des catégories de compte à des niveaux inférieurs et modifier leur structure pour définir la façon dont le tableau d'analyse associé apparaît dans les rapports.
>
> Il est recommandé de créer et de structurer vos propres catégories de compte du grand livre de niveau inférieur à partir de zéro, dans une hiérarchie si nécessaire, plutôt que d'essayer de réorganiser les catégories existantes. Par exemple, vous pouvez restructurer le nœud **Passif** pour contenir un nouveau nœud **Équité** suivi des nœuds **Passif à court terme** et **Passif à long terme**.

## <a name="to-create-a-new-account-schedule"></a>Pour créer un tableau d'analyse

Vous pouvez utiliser des tableaux d'analyse pour analyser les chiffres des comptes GL ou pour comparer les écritures et les écritures budget. Par exemple, vous pouvez afficher les écritures en tant que pourcentages des écritures budget.

Les tableaux d'analyse dans la version standard de [!INCLUDE[prod_short](includes/prod_short.md)] sont la base des rapports financiers standard, qui ne sont peut-être pas adaptés aux besoins de votre entreprise. Pour créer rapidement vos propres rapports financiers, vous pouvez commencer par copier un tableau d’analyse existant, tel que décrit à l’étape 3.

> [!TIP]
> Après avoir créé un tableau d’analyse, vous pouvez utiliser la page **Aperçu tableau d’analyse** pour prévisualiser et valider le rapport financier défini par l’échéancier de compte. Pour ouvrir la page, choisissez l'action **Vue d’ensemble**.  

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 1.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Tableaux d’analyse**, puis sélectionnez le lien associé.  
2. Sur la page **Tableaux d'analyse**, choisissez **Nouveau** pour donner un nom au tableau d'analyse.
3. Sinon, si vous souhaitez réutiliser les paramètres d’un tableau d’analyse existant, choisissez l’action **Copier le tableau d’analyse**.
4. Renseignez les champs selon vos besoins. Dans le champ **Présentation colonne par déf.**, sélectionnez une présentation existante. Vous pouvez la modifier ultérieurement au besoin.

    Les présentations de colonne définissent des colonnes pour les paramètres par lesquels les données financières sont affichées dans les lignes. Par exemple, une présentation de colonne peut contenir quatre colonnes pour vous permettre de comparer le solde période et le solde pour une même période de l’exercice actuel et du précédent. Pour plus d'informations, voir [Pour modifier une présentation de colonne](bi-how-work-account-schedule.md#to-edit-a-column-layout).

5. Choisissez l'action **Modifier tableau d'analyse**.
6. En fonction de ce que vous souhaitez analyser, choisissez les actions **Insérer des comptes du grand livre**, **Insérer des comptes CF**, et **Insérer des types de coût** pour créer une ligne pour chaque élément financier. Par exemple, vous pouvez avoir une ligne pour les actifs à court terme et une autre ligne pour les immobilisations. Pour obtenir de l’inspiration, visualisez les tableaux d’analyse de la compagnie de démonstration CRONUS.

    > [!NOTE]
    > Le champ **N° ligne** affichera les 10 premiers caractères d’un identificateur, par exemple, un numéro de compte. Si vous ajoutez des éléments avec des identificateurs qui commencent par les mêmes 10 caractères, vous aurez des doublons dans le champ **N° ligne** . Si nécessaire, vous pouvez modifier manuellement les identifiants après avoir inséré les éléments. Les identificateurs complets sont affichés dans le champ **Totalisation**.

7. Choisissez l'action **Aperçu** pour visualiser le rapport financier qui en résulte.
8. Sur la page **Aperçu tableau d'analyse**, dans le champ **Nom présentation colonne**, sélectionnez une autre présentation de colonne pour afficher les données financières selon d'autres paramètres.
9. Cliquez sur le bouton **OK**.

Vous avez désormais défini la base du tableau d’analyse, les lignes de données financières à afficher, et une présentation existante de colonnes pour afficher les données sur les lignes selon divers paramètres. Si la présentation de colonne par défaut que vous avez sélectionnée dans l’étape 4 ne convient pas à votre objectif, suivez la procédure suivante.

### <a name="to-edit-a-column-layout"></a>Pour modifier une présentation de colonne

Les présentations de colonne vous permettent de définir les colonnes à inclure dans le rapport qui en résulte. Par exemple, vous pouvez créer une présentation de manière à comparer le solde période et le solde pour une même période de l'exercice actuel et du précédent. Vous pouvez avoir jusqu'à 15 colonnes, ce qui est utile, par exemple, pour afficher les budgets sur 12 mois avec une colonne indiquant le total.

> [!NOTE]
> Une version imprimée/aperçu/enregistrée du tableau d'analyse peut afficher un maximum de cinq colonnes. Si le tableau d'analyse est uniquement destiné pour l'analyse de la page **Aperçu tableau d'analyse**, vous pouvez créer autant de colonnes que vous le souhaitez.

1. Sur la page **Tableaux d'analyse**, sélectionnez le tableau d'analyse approprié, puis cliquez sur l'action **Modifier configuration présentation colonne**.
2. Sur la page **Présentations colonne**, créez une ligne pour chaque colonne en fonction de laquelle les données financières sont affichées dans le rapport financier. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]
3. Cliquez sur le bouton **OK**.
4. Ouvrez la page **Aperçu tableau d'analyse** de temps en temps pour vérifier que la nouvelle présentation de colonne fonctionne comme prévu.

> [!NOTE]
> Les colonnes que vous définissez sur chaque ligne représentent les colonnes 3 et supérieures de la page **Aperçu tableau d'analyse**. Les deux premières colonnes, **N° ligne** et **Description**, sont fixes.  

### <a name="to-create-a-column-that-calculates-percentages"></a>Pour créer une colonne qui calcule des pourcentages

Il se peut que vous vouliez inclure une colonne dans un tableau d'analyse pour calculer des pourcentages d'un total. Par exemple, si vous avez des lignes qui ventilent des ventes par dimension, vous pouvez juger utile de disposer d’une colonne indiquant le pourcentage des ventes totales que représente chaque ligne.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 2.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Tableaux d’analyse**, puis sélectionnez le lien associé.
2. Sur la page **Noms tableaux d'analyse**, sélectionnez le tableau d'analyse.  
3. Choisissez l'action **Modifier tableau d'analyse** pour configurer une ligne de tableau d'analyse et calculer le total sur lequel le pourcentage sera basé.  
4. Insérez une ligne juste au-dessus de la première ligne pour laquelle vous voulez afficher un pourcentage.  
5. Renseignez les champs de la ligne comme suit : dans le champ **Type totalisation**, entrez **Base de pourcentage**. Dans le champ **Totalisation**, saisissez une formule pour le total sur lequel le pourcentage sera basé. Par exemple, si la ligne 11 contient le total des ventes, saisissez **11**.  
6. Choisissez l'action **Modifier paramètres présentation colonne** pour configurer une colonne.  
7. Renseignez les champs de la ligne comme suit : dans le champ **Type colonne**, sélectionnez **Formule**. Dans le champ **Formule**, saisissez une formule correspondant au montant pour lequel vous voulez calculer un pourcentage, suivie de %. Par exemple, si le numéro de colonne N contient le solde période, saisissez **N%**.  
8. Répétez les étapes 4 à 7 pour chaque groupe de lignes que vous voulez ventiler par pourcentage.

## <a name="to-set-up-account-schedules-with-overviews"></a>Pour configurer des tableaux d'analyse avec des aperçus

Vous pouvez utiliser un tableau d’analyse pour créer un état comparant les chiffres du grand livre et les chiffres budgétés.

1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 3.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Tableaux d’analyse**, puis sélectionnez le lien associé.
2. Sur la page **Noms tableaux d'analyse**, sélectionnez le tableau d'analyse.  
3. Choisissez l'action **Modifier tableau d'analyse**  
4. Sur la page **Tableau d'analyse**, sélectionnez le nom du tableau d'analyse par défaut dans le champ **Nom**.
5. Choisissez l’action **Insérer des comptes du grand livre**.  
6. Sélectionnez les comptes à inclure dans votre relevé, puis cliquez sur le bouton **OK**.

    Ces comptes sont à présent insérés dans le tableau d'analyse. Si vous le souhaitez, vous pouvez aussi modifier la présentation colonne.  
7. Sélectionnez l'action **Présentation**.  
8. Sur la page **Aperçu tableau d’analyse**, sur le raccourci **Filtres dimension**, définissez le filtre budget sur le nom du filtre souhaité.  
9. Cliquez sur le bouton **OK**.  

Vous pouvez maintenant copier et coller votre budget dans un classeur.  

## <a name="comparing-accounting-periods-using-period-formulas"></a>Comparaison de périodes comptables à l'aide de formules de période

Votre tableau d'analyse peut comparer les résultats de différentes périodes comptables, par exemple ce mois et le même mois l'année précédente. Pour ce faire, ouvrez la page **Présentation colonne** et personnalisez-la en ajoutant le champ **Formule période comparaison** sous forme de colonne. Pour plus d'informations, voir [Personnaliser votre espace de travail](ui-personalization-user.md). Vous pouvez ensuite définir ce champ sur une formule de période.  

Une période comptable ne doit pas nécessairement correspondre au calendrier. Toutefois, chaque exercice financier doit avoir le même nombre de périodes comptables, même si chaque période peut varier.  

[!INCLUDE[prod_short](includes/prod_short.md)] utilise la formule de période pour calculer le montant de la période de comparaison en fonction de la période représentée dans le filtre date du formulaire de sélection du rapport. La période de comparaison est basée sur la période de la date de début du filtre de date. Les abréviations utilisées pour les spécifications de période sont les suivantes :

| Abréviation | Description                                                                           |
| ------------ | ------------------------------------------------------------------------------------- |
| P            | Période                                                                                |
| DP           | Dernière période d'un exercice financier, semestre ou trimestre.                                   |
| FP           | Période actuelle d'un exercice financier, semestre ou trimestre. Utilisez FP dans les formules pour définir la période qui commence ou termine la formule. Par exemple, EF\[1..PA\] désigne la durée entre le début de l'exercice financier en cours et la période actuelle.|
| EC           | Exercice financier. Par exemple, EF\[1..3\] désigne le premier trimestre de l'exercice financier actuel |

Exemples de formule :

| Formule         | Description                                                                                     |
| --------------- | ----------------------------------------------------------------------------------------------- |
| \<Blank\>       | Période en cours                                                                                  |
| \-1P            | Période précédente                                                                                 |
| \-1EC\[1..DP\]  | Ensemble de l'exercice financier précédent                                                                     |
| \-1EC           | Période de l'exercice financier précédent équivalente à la période en cours                                                          |
| \-1EC\[1..3\]   | Premier trimestre de l'exercice financier précédent                                                           |
| \-1EC\[1..FP\]  | Du début de l'exercice financier comptable précédent à période en cours dans l'exercice financier précédent, les deux périodes incluses |
| \-1EC\[FP..DP\] | De la période en cours dans l'exercice financier précédent à la dernière période de l'exercice financier précédent, les deux périodes incluses   |

Pour effectuer des calculs basés par périodes, vous devez entrer une formule dans le champ **Formule date comparaison** à la place. Par exemple, si le champ est défini sur -1A, [!INCLUDE [prod_short](includes/prod_short.md)] procède à une comparaison à la même période 1 an avant.

> [!NOTE]
> Il n'est pas toujours transparent de déterminer les périodes à comparer, car vous pouvez définir un filtre date sur un rapport qui couvre des dates différentes des périodes comptables représentées dans les données du plan comptable. Par exemple, vous créez un tableau d'analyse dans lequel vous souhaitez comparer cette période avec la même période l'année précédente. Vous définissez le champ **Formule date comparaison** sur *-1EF*. Ensuite, vous exécutez le rapport le 28 février et définissez le filtre date sur Janvier et février. Par conséquent, le tableau d'analyse compare les mois de janvier et février de cette année au mois de janvier de l'année précédente, qui est la seule période comptable terminée des deux pour l'année précédente.  

Pour plus d’informations sur les formules de date, voir [Utiliser des dates civiles et des heures](ui-enter-date-ranges.md).  

## <a name="import-or-export-account-schedules"></a>Importer ou exporter des tableaux d’analyse
Vous pouvez importer et exporter des tableaux d’analyse comme des packages de configuration RapidStart. Par exemple, les packages de configuration s’avèrent utiles pour le partage avec d’autres compagnies. Le package est créé dans un fichier .rapidstart, qui fournit le contenu du package sous un format compressé.

### <a name="to-import-and-export-account-schedules"></a>Pour importer et exporter des tableaux d’analyse
1. Sélectionnez l’icône en forme ![d’ampoule qui ouvre la fonction Tell Me 4.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Tableaux d’analyse**, puis sélectionnez le lien associé.
2. Choisissez le tableau d’analyse, puis choisissez les actions **Importer le tableau d’analyse** ou **Exporter le tableau d’analyse**, selon ce que vous souhaitez faire. 

> [!NOTE]
> Lorsque vous importez des tableaux d’analyse, les enregistrements existants portant les mêmes noms que ceux que vous importez seront supprimés.

## <a name="see-related-microsoft-training"></a>Voir la [formation Microsoft](/training/modules/configure-financial-reports-dynamics-365-business-central/index) associée

## <a name="see-also"></a>Voir aussi

[Veille économique](bi.md)  
[Finance](finance.md)  
[Configuration de Finance](finance-setup-finance.md)  
[Le grand livre et le plan comptable](finance-general-ledger.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]
