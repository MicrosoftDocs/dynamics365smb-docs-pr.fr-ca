---
title: Audit des modifications
description: Vous pouvez activer un journal utilisateur de sorte que vous avez un historique de toutes les modifications apportées aux données dans les tables suivies. Vous pouvez également suivre les activités avec certains types de journaux d'activité.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: conceptual
ms.search.keywords: 'user log, user activity, tracking'
ms.search.form: '592, 593, 594, 595, 710, 1366, 1367, 1368, 1369'
ms.date: 05/03/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
---
# Audit des modifications

Un défi courant dans de nombreuses applications de gestion d’entreprise est d’éviter les modifications indésirables des données. Il peut s'agir d'une simple erreur de numéro de téléphone client comme d'une écriture erronée. Cet article décrit les fonctionnalités permettant de savoir ce qui a changé, qui l’a modifié et quand la modification a été effectuée.

## À propos du journal des modifications

Le journal des modifications vous permet de suivre toutes les modifications directes apportées par un utilisateur aux données dans la base de données. Vous spécifiez les opérations que le système doit journaliser, pour chaque table et chaque champ, puis activez le journal modification. Le journal des modifications est basé sur les modifications apportées aux données dans les tableaux que vous suivez. Sur la page **Écritures du journal des modifications**, les entrées sont chronologiquement ordonnées et montrent toutes les modifications apportées aux valeurs des champs des tables que vous spécifiez.

Le suivi des modifications peut affecter les performances, ce qui peut vous faire perdre du temps, et augmenter la taille de votre base de données, ce qui peut à son tour vous coûter cher. Pour réduire ces coûts, gardez ce qui suit à l’esprit :

- Soyez prudent lorsque vous choisissez les tables et les opérations.
- N’ajoutez pas d’écritures et de documents reportés. À la place, donnez la priorité aux champs système tels que Créé par et Date de création.
- N’utilisez pas le type de suivi **Tous les champs**. Au lieu de cela, choisissez **Certains champs** et suivez uniquement les champs les plus importants.

> [!NOTE]
> Le journal des modifications ne suit pas les modifications des champs qui utilisent le `autoIncrement property`. Un exemple de champ qui utilise la propriété est le champ Entier des tables Messages d’erreur et Ligne déclaration TVA.

Également pour des raisons de performances, le journal des modifications est désactivé pendant le processus de mise à niveau de [!INCLUDE [prod_short](includes/prod_short.md)] vers la version suivante. En plus d’accélérer le processus de mise à niveau, la déconnexion aide également à réduire l’encombrement dans le journal des chances. Dès que la mise à niveau est terminée, le journal recommence à suivre les modifications.

> [!Important]
> Les changements s’affichent dans **Écritures journal modification** seulement après le redémarrage de la session de l’utilisateur, ce qui se passe comme suit :
>
> - La session a expiré et a été actualisée.
> - L'utilisateur a sélectionné une autre compagnie ou un autre Tableau de bord.
> - L’utilisateur s’est déconnecté et s’est reconnecté.

## Configuration du journal modifications

Sur la page **Configuration journal modification**, vous pouvez activer ou désactiver le journal des modifications. Lorsque vous le faites, l’activité est enregistrée afin que vous puissiez toujours voir qui a effectué la modification.

Sur la page **Configuration du journal de modification**, si vous choisissez l’action **Tables**, vous pouvez spécifier les tables dont vous souhaitez suivre les modifications, et quelles modifications suivre. [!INCLUDE[prod_short](includes/prod_short.md)] suit également plusieurs tables système.

> [!NOTE]
> Vous pouvez surveiller des champs spécifiques pour les changements, tels que les champs qui contiennent des données sensibles, en configurant la surveillance de champ. Si vous le faites, pour éviter la redondance, la table qui contient le champ ne sera pas disponible pour la configuration du journal des modifications. Pour plus d’informations, voir [Surveiller les champs sensibles](across-log-changes.md#monitor-sensitive-fields).

Une fois que configuré et activé le journal des modifications et modifié des données, vous pouvez afficher et filtrer les modifications sur la page **Écritures journal modification**. Si vous souhaitez supprimer des entrées, configurez une stratégie de rétention, dans laquelle vous pouvez définir des filtres en fonction des dates et de l’heure. Pour en savoir plus sur les stratégies de rétention, accédez à [Définir des stratégies de rétention](admin-data-retention-policies.md).  

## Analyser les données dans le journal des modifications

Vous pouvez utiliser la fonctionnalité **Analyse des données** pour analyser les données du journal des modifications à partir de la page [Entrées du journal des modifications](https://businesscentral.dynamics.com/?page=595) . Vous n’avez pas besoin d’exécuter un rapport ou d’ouvrir une autre application, comme Excel. La fonction fournit un moyen interactif et polyvalent de calculer, résumer et examiner les données. Plutôt que d’exécuter des rapports à l’aide d’options et de filtres, vous pouvez ajouter plusieurs onglets qui représentent différentes tâches ou vues sur les données. Quelques exemples sont "Qui a modifié quelles données et quand" ou "Les données changent par table/champ" ou toute autre vue que vous pouvez imaginer. Pour en savoir plus sur l’utilisation de la fonctionnalité **Analyse des données** , accédez à [Analyser la liste et interroger les données avec le mode d’analyse](analysis-mode.md).

### Scénarios d’analyse ad hoc des journaux de modification

Les sections suivantes fournissent des exemples de scénarios dans lesquels l’analyse du journal des modifications peut vous aider à surveiller et auditer les modifications importantes.

| Aire | Pour... | Ouvrir cette page en mode analyse | Utiliser ces champs |
| ---- | ----- | ------------------------------- |------------------- |
| [Qui a modifié quelles données et quand](#example-who-changed-what-data-and-when) | Voir qui a modifié quelles données. | [Écritures du journal des modifications](https://businesscentral.dynamics.com/?page=595) | **Code utilisateur**, **Date et heure**, **Légende de la table**, **Légende du champ**, **Valeur de clé primaire 2**, **Valeur de clé primaire 3**, **Type de changement**, **Ancienne valeur** et **Nouvelle valeur**. |
| [Modifications des données par table/champ](#example-data-changes-by-tablefield) | Consultez les modifications de données par table/champ et par qui a effectué la modification. | [Écritures du journal des modifications](https://businesscentral.dynamics.com/?page=595) | **Légende de la table**, **Légende du champ**, **Code utilisateur**, **Date et heure**, **Valeur de clé primaire 2**, **Valeur de clé primaire 3**, **Type de changement**, **Ancienne valeur** et **Nouvelle valeur**. |

### Exemple : Qui a modifié quelles données et quand

Pour analyser Qui a modifié Quelles données Quand, procédez comme suit :

1. Ouvrez le [Écritures journal modifications](https://businesscentral.dynamics.com/?page=595) liste et activez icône :::image type="content" source="media/analysis-mode-icon.png" alt-text="Saisissez le mode d’analyse."::: pour activez le mode d’analyse.
1. À la **Colonnes** menu, supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Faites glisser le champ **Code utilisateur** (qui l’a fait) vers la zone **Groupes de lignes**.
1. Maintenant choisissez les champs suivants :
   - Pour afficher quand cela s’est produit, choisissez **Date et heure**.
   - Pour afficher le tableau où cela s’est produit, choisissez **Légende du tableau**. 
   - Pour afficher quel champ, choisissez **Légende du champ**.
   - Pour afficher le code du champ, choisissez **Valeur de clé primaire 2**. 
   - Pour afficher le nom d’une compagnie, choisissez **Valeur de clé primaire 3**.
   - Pour indiquer si la modification était une action d’insertion, de mise à jour ou de suppression, choisissez **Type de changement**.
   - Pour afficher le changement, choisissez **Ancienne valeur** et **Nouvelle valeur**.
1. Renommez votre onglet d’analyse en **Qui a modifié quelles données et quand** ou quelque chose qui décrit cette analyse.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source=" media/data-analysis-change-log-entries-Who-changed-What-data-When.png" alt-text="Exemple de comment effectuer une analyse de données sur la page Modifier les entrées du journal (Qui a modifié quelles données quand)." lightbox="media/data-analysis-change-log-entries-Who-changed-What-data-When.png":::

### Exemple : Modifications des données par table/champ

Pour analyser les modifications de données par table/champ, procédez comme suit :

1. Ouvrez le [Écritures journal modifications](https://businesscentral.dynamics.com/?page=595) liste et activez icône :::image type="content" source="media/analysis-mode-icon.png" alt-text="Saisissez le mode d’analyse."::: pour activez le mode d’analyse.
1. À la **Colonnes** menu, supprimez toutes les colonnes (cochez la case à côté du **Recherche** champ à droite).
1. Faites glisser le **Légende du tableau** (sur quelle table), et **Légende du champ** (sur quel champ) champs au **Groupes de lignes** zone.
1. Maintenant choisissez les champs suivants :
   - Pour afficher quand cela s’est produit, choisissez **Date et heure**
   - Pour montrer qui a effectué la modification, choisissez **Code utilisateur**
   - Pour afficher le code pour le champ, choisissez **Valeur de clé primaire 2**.
   - Pour afficher le nom d’une compagnie, choisissez **Valeur de clé primaire 3** (généralement le nom de la compagnie), 
   - Pour indiquer si la modification était une action d’insertion, de mise à jour ou de suppression, choisissez **Type de changement**.
   - Pour afficher le changement, choisissez **Ancienne valeur** et **Nouvelle valeur**.
1. Renommez votre onglet d’analyse en **Modifications des données par table/champ** ou quelque chose qui décrit cette analyse.

L’image suivante montre le résultat de ces étapes.

:::image type="content" source=" media/data-analysis-change-log-entries-data-changes-by-table-field.png" alt-text="Exemple de comment effectuer une analyse de données sur la page Modifier les entrées du journal (Modifications des données par table/champ)." lightbox="media/data-analysis-change-log-entries-data-changes-by-table-field.png":::

## À propos des journaux d’activité

À partir des pages [!INCLUDE [prod_short](includes/prod_short.md)], vous pouvez afficher un journal d’activités indiquant l’état et les erreurs éventuelles des fichiers que vous exportez ou importez dans [!INCLUDE [prod_short](includes/prod_short.md)].  

### Utiliser les journaux d’activité

Les informations sont affichées dans la page **Journal des activités**, en fonction du contexte de l’ouverture. Par exemple, vous pouvez ouvrir la page depuis les pages **Configuration du service d’échange de documents**, **Document entrant**, **Facture vente reportée** et **Note de crédit vente reportée**, par exemple. Vous pouvez vider la liste des entrées du journal ou simplement effacer la liste des entrées de plus de sept jours.  

## Surveiller les champs sensibles

La protection et la confidentialité des données sensibles est au cœur des préoccupations de la plupart des entreprises. Pour ajouter une couche de sécurité, vous pouvez surveiller les champs importants et recevoir un courriel lorsqu’une personne modifie une valeur. Par exemple, vous souhaiterez peut-être être averti si quelqu’un change le numéro IBAN de votre compagnie.

> [!NOTE]
> Pour envoyer des notifications par courriel, vous devez configurer la fonction courriel dans [!INCLUDE[prod_short](includes/prod_short.md)]. Pour plus d'informations, voir [Configurer la messagerie](admin-how-setup-email.md).

### Configurer la surveillance des champs

Vous pouvez utiliser le guide de configuration assistée **Surveiller la configuration du changement de champ** pour spécifier les champs que vous souhaitez surveiller en fonction de critères de filtre, tels que la classification de sensibilité des données pour les champs. Pour plus d’informations, voir [Classification de la sensibilité des données](admin-classifying-data-sensitivity.md). Le guide vous permet également de spécifier la personne qui reçoit une notification par courriel en cas de modification et le compte de messagerie qui envoie la notification. Spécifiez à la fois l’utilisateur à notifier et le compte à partir duquel envoyer la notification. Une fois le guide terminé, vous pouvez gérer les paramètres de surveillance des champs sur la page **Configuration de la surveillance des champs**.

> [!NOTE]
> Lorsque vous spécifiez le compte de messagerie à partir duquel envoyer les notifications, vous devez ajouter le type de compte **Microsoft 365** ou **SMTP**. Les notifications doivent être envoyées à partir d’un compte qui n’est pas associé à un utilisateur réel. Vous ne pouvez donc pas choisir le type de compte **Utilisateur actuel**. Si vous le faites, les notifications ne seront pas envoyées.

Au fil du temps, la liste des entrées sur la page **Entrées du journal des champs surveillés** grandira. Pour réduire le nombre d’entrées, vous pouvez créer une stratégie de rétention qui supprimera les entrées après une période de temps spécifiée. Pour plus d’informations, voir [Définir les stratégies de rétention](admin-data-retention-policies.md).

Lorsque vous configurez la surveillance des champs ou modifiez quelque chose dans la configuration, des entrées sont créées pour vos modifications. Vous pouvez spécifier si vous souhaitez afficher les entrées liées à la configuration de la surveillance en les affichant ou en les masquant.

Vous pouvez gérer les paramètres de surveillance des champs, par exemple envoyer une notification par courriel ou simplement consigner la modification, pour chaque champ sur la page **Feuille de calcul Champs surveillés**. La page est également l’endroit où vous pouvez ajouter ou supprimer des champs à surveiller.

> [!NOTE]
> Après avoir ajouté un ou plusieurs champs et commencé la surveillance, déconnectez-vous de [!INCLUDE[prod_short](includes/prod_short.md)] et reconnectez-vous pour appliquer vos paramètres.

### Utiliser la surveillance des champs

Les entrées de toutes les valeurs modifiées des champs surveillés sont disponibles sur la page **Entrées du journal des champs surveillés**. Pour cet exemple, les entrées contiennent les informations suivantes :

- Le champ dans lequel la valeur a été modifiée.
- Les valeurs originale et nouvelle.
- Qui a effectué la modification et quand.

Pour étudier plus en détail une modification, choisissez une valeur pour ouvrir la page sur laquelle elle a été effectuée. Pour afficher une liste de toutes les entrées, choisissez **Écritures de modification de champ**.

### Afficher la télémétrie de surveillance des champs

Vous pouvez configurer [!INCLUDE[prod_short](includes/prod_short.md)] pour envoyer une activité de surveillance des champs à une ressource Application Insights dans Microsoft Azure. Ensuite, à l’aide d’Azure Monitor, vous créez des rapports et configurez des alertes sur les données collectées. Pour plus d’informations, voir les articles suivants dans l’aide [!INCLUDE[prod_short](includes/prod_short.md)] dédiée aux développeurs et professionnels de l’informatique.

- [Surveillance et analyse de la télémétrie - Activation d’Application Insights](/dynamics365/business-central/dev-itpro/administration/telemetry-overview?toc=/dynamics365/business-central/toc.json#enable)
- [Analyse de la télémétrie de surveillance des champs](/dynamics365/business-central/dev-itpro/administration/telemetry-field-monitoring-trace?toc=/dynamics365/business-central/toc.json)

## Définir des stratégies de rétention

Vous pouvez créer des stratégies de rétention pour supprimer les données inutiles dans les journaux après une période de temps que vous spécifiez. Par exemple, au fil du temps, le nombre d’entrées dans un journal peut augmenter. En nettoyant les anciennes entrées, vous pouvez vous concentrer plus facilement sur des entrées plus récentes et probablement plus pertinentes. Pour en savoir plus sur les stratégies de rétention, accédez à [Définir des stratégies de rétention](admin-data-retention-policies.md).

## Voir aussi

[Surveiller les champs sensibles](across-log-changes.md#monitor-sensitive-fields)  
[Analyse de la télémétrie de surveillance des champs](/dynamics365/business-central/dev-itpro/administration/telemetry-field-monitoring-trace?toc=/dynamics365/business-central/toc.json)  
[Définir des stratégies de rétention](admin-data-retention-policies.md)  
[Modification des paramètres de base](ui-change-basic-settings.md)  
[Tri, recherche et filtrage](ui-enter-criteria-filters.md)  
[Recherche de pages et d'informations avec Tell Me](ui-search.md)  
[Affectation des autorisations aux utilisateurs et aux groupes](ui-define-granular-permissions.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
