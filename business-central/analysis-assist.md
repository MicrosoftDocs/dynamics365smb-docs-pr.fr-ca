---
title: Analyse des données dans les listes avec l'aide de Copilot (version préliminaire)
description: Découvrez comment utiliser Copilot dans Business Central pour analyser les données.
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.topic: how-to
ms.date: 06/13/2024
ms.custom: bap-template
ms.service: dynamics-365-business-central
ms.search.form: '456, 457, 458, 459, 460, 461, 16, 22, 25, 26, 27, 31, 143, 144, 9300, 9301, 9303, 9304, 9305, 9306, 9307, 9309, 9310, 9311'
---
# Analyse des données dans les listes avec l'aide de Copilot (version préliminaire)

[!INCLUDE [preview-banner](~/../shared-content/shared/preview-includes/preview-banner.md)]

Cet article explique comment utiliser *assistance à l’analyse* pour vous aider à analyser les données des pages de liste.

[!INCLUDE [preview-note](~/../shared-content/shared/preview-includes/production-ready-preview-dynamics365.md)]

## À propos l’assistance pour les analyses

L’assistance à l’analyse est un copilote pour le [mode d’analyse](analysis-mode.md) sur les pages de liste dans Business Central. Le mode d'analyse fournit un moyen interactif et polyvalent de calculer, résumer et examiner les données. Pour analyser les données en mode analyse, vous créez un onglet *analyse* dans lequel vous transformez les données pour afficher les agrégations et résumés souhaités. Par exemple, vous organisez les champs en lignes et en colonnes, spécifiez des filtres, triez les colonnes et pivotez sur les champs. Avec l’aide à l’analyse, au lieu d’effectuer cette tâche manuellement, vous obtenez en grande partie la même chose&mdash;ou du moins comme début&mdash;en utilisant des mots. En exprimant la structure souhaitée en langage naturel, comme "trier par quantité de la plus petite à la plus grande" ou "afficher le coût moyen par catégorie, l’assistance à l’analyse utilise l’IA pour générer une présentation suggérée sur un onglet d’analyse.

## Langues disponibles

[!INCLUDE[analysis-assist-language-support](includes/analysis-assist-language-support.md)]

## Conditions préalables

- La fonctionnalité d’assistance à l’analyse est activée et vous disposez des autorisations nécessaires pour l’utiliser. Cette tâche est généralement effectuée par un administrateur. [Pour plus d’informations sur la configuration Copilot et les capacités IA](enable-ai.md).
<!-- - The display language in Business Central is set to one the following English locales: en-AU, en-CA, en-GB, en-IE, en-IN, en-NZ, en-PH, en-SG, en-US, en-ZA. [Learn how to change the language](ui-change-basic-settings.md#language)-->
<!-- - Your Business Central environment is in any country/region except Canada (this feature isn't yet available in Canada).-->

## Mise en route

1. Ouvrez la page de liste à analyser.

   Par exemple, pour utiliser la page **Articles**, sélectionnez l’icone en forme de ![Loupe qui ouvre la fenêtre de recherche](media/ui-search/search_small.png) (<kbd>Alt</kbd>+<kbd>Q</kbd>), entrez *articles*, puis choisissez le lien associé.

1. Vous pouvez commencer à analyser les données avec Copilot directement à partir de la page de liste ou en entrant d’abord dans le mode d’analyse. Procédez comme suit pour commencer :

    - Dans la barre d’action en haut de la page, sélectionnez ![Affiche l’icône du copilote](media/copilot-icon.png) **Copilot** > **Analyser la liste**.
    - Dans la barre d’action en haut de la page, sélectionnez ![Affiche l’icône d’entrée en mode analyse](media/analysis-mode-icon.png) **Passer en mode analyse**, puis sélectionnez ![Affiche l’icône du copilote](media/copilot-icon.png) **Copilot** > **Créer une nouvelle analyse**.

1. Dans le **Analyser élément** avec la fenêtre Copilot, saisissez une description de la mise en page souhaitée. Cette description est connue sous le nom de *invite*.

    ![Affiche l’assistance à l’analyse Copilot](media/analysis-assist.png)

    > [!TIP]
    > Pour obtenir de l’aide pour rédiger une invite, sélectionnez ![Affiche l’icône d’invite d’affichage](media/prompt-guide-icon.png) **Guide rapide**, puis choisissez l’une des options pour commencer. Le texte entre parenthèses `[ ]` est affiché uniquement à titre d’exemple et n’est pas inclus dans la fenêtre Copilot.

1. Sélectionner **Générer** puis attendez pendant que Copilot génère la mise en page sur le nouvel onglet d’analyse.
1. Consultez les résultats dans le nouvel onglet d’analyse.

   > [!NOTE]
   > Si vous quittez le nouvel onglet d’analyse (par exemple en accédant à un autre onglet ou une autre page d’analyse) ou si vous apportez des modifications à la disposition de l’onglet (par exemple en triant les colonnes ou en modifiant les paramètres dans le **Colonnes** et **Filtres d’analyse** onglets), le nouvel onglet d’analyse est automatiquement enregistré et Copilot se ferme.

1. Si vous souhaitez modifier l’analyse générée, vous pouvez effectuer l’une des étapes :

   - Pour vous baser sur les instructions précédentes, saisissez les informations dans la case **Ajouter plus de détails sur l’analyse** , puis sélectionnez ![Afficher la flèche de réglage](media/analysis-assist-adjust-button.png) **Ajuster** flèche. Copilot mémorise vos instructions précédentes et les utilise pour effectuer des ajustements.

   - Pour repartir de zéro en ajoutant de nouvelles instructions, sélectionnez l’icône ![Affiche l’icône en forme de crayon d’invite de modification](media/edit-pencil.png) **Modifier l’invite :**, ajoutez les détails à l’invite, puis puis sélectionnez **Générer**.

1. Si vous souhaitez enregistrer l’onglet analyse, sélectionnez **Conserver**. Si vous ne souhaitez pas l’enregistrer, sélectionnez **Ignorer**.

## Conseils et exemples d'invites

La création d’invites efficaces pour Copilot est essentielle pour obtenir des suggestions d’analyse précises et pertinentes. Il existe également des moyens de minimiser le texte que vous ajoutez dans les invites pour le rendre plus rapide lors de la saisie. Voici quelques conseils et directives suivis de quelques exemples :

- Soyez concis et évitez les phrases longues ou multiples.
- Assurez-vous que les noms de champs utilisés dans les invites sont quelque peu proches des noms de champs réels sur la page.
- Utilisez un langage naturel, en exprimant la structure des données de manière amicale et conversationnelle.
- Utilisez des mots-clés, des expressions et des termes courants utilisés dans l’analyse des données, tels que `group by`, `sum`, `sort by`, etc.
- Si la réponse initiale n’est pas celle que vous souhaitez, ajoutez des instructions de suivi ou reformulez la dernière instruction.
- Les abréviations courantes sont acceptables.
- La casse des lettres n’est pas importante.

### Exemples

Les exemples d’invite suivants utilisent l’assistance à l’analyse sur la liste **Éléments** . La page des articles comprend trois champs récapitulables pour l’analyse : **Quantité disponible**, **Coût unitaire**, **Prix unitaire**.

Invite : `Show items by brand and unit of measure`

Cette invite tente d’afficher les totaux de tous les champs récapitulables, regroupés par marque et par champ **Unité de mesure de base**. Mais dans ce cas, "marque" ne correspond à aucun nom de champ, donc Copilot ne peut probablement pas trouver de champ correspondant. Il vous demande donc de reformuler l’invite et de réessayer.

Invite : `Show items by type and uom`

Cette invite afficher les totaux de tous les champs récapitulables, regroupés par champ **Type** et par champ **Unité de mesure de base**. Mais au lieu d’écrire « Unité de mesure », l’abréviation `uom` est utilisée.

Invite : `Show total quantity per type per UoM`

Cette invite crée un tableau croisé dynamique sur le champ **Quantité disponible** par **Unité de mesure de base** par **Type**.

## Voir aussi .

[FAQ sur l’IA responsable pour l’aide à l’analyse](faqs-analysis-assist.md)  
[Analyse de données ad hoc](reports-adhoc-analysis.md)  
