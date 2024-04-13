---
title: Suivi des ajustements des coûts d’articles
description: Découvrez comment le suivi des ajustements des coûts des articles peut vous aider à maintenir l’exactitude de vos données sur les coûts des articles.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: andreipa
ms.topic: how-to
ms.search.keywords: null
ms.search.form: null
ms.date: 03/08/2024
ms.service: dynamics-365-business-central
ms.custom: bap-template
---

# <a name="track-item-cost-adjustments"></a>Suivi des ajustements des coûts d’articles

Il est important de maintenir l’exactitude des coûts des articles et de réduire le délai entre le moment où vous reportez une écriture et le moment où le grand livre reflète son coût. Vous pouvez suivre les performances des ajustements de coûts pour des cycles et des articles d’ajustement individuels. Si des erreurs se produisent, vous pouvez identifier les éléments problématiques et apporter des corrections. Par exemple, vous pouvez exclure les éléments des calculs pour garantir que les ajustements ne sont pas interrompus pour d’autres éléments. Vous pouvez ajuster les coûts pour des articles individuels ou créer des lots d’articles et les ajuster tous en même temps.

## <a name="start-tracking-cost-adjustments"></a>Commencez à suivre les ajustements de coûts

C’est facile de commencer. Sur le **Configuration de l’inventaire** page, la **Journalisation des ajustements de coûts** Le champ offre quelques options :

* **Désactivé** signifie que vous n’enregistrez pas les cycles d’ajustement des coûts.
* **Erreurs uniquement** signifie enregistrer uniquement les exécutions qui ont échoué.
* **Tous** signifie enregistrer toutes les exécutions.

> [!NOTE]
> Pour minimiser la taille du journal, [!INCLUDE [prod_short](includes/prod_short.md)] n’enregistre pas les ajustements qui se produisent automatiquement lorsque quelqu’un publie un élément.

Vous devez également configurer l’écriture file d’attente des projets **Reporter coût de l’inventaire au GL (1002)**. Cette écriture file d’attente des projets ajuste automatiquement les coûts en fonction d’un calendrier. Pour en savoir plus sur les écritures file d’attente des projets, consultez [Utiliser les files d’attente des projets pour programmer des tâches](admin-job-queues-schedule-tasks.md).

## <a name="manage-cost-adjustments"></a>Gérer les ajustements de coûts

Utilisez la page **Ajustement du coût de l’inventaire** pour gérer et surveiller le processus d’ajustement des coûts. Cette page affiche les articles avec leurs paramètres de valorisation et leur état d’ajustement des coûts. Vous pouvez filtrer la liste pour vous concentrer sur les éléments qui nécessitent un ajustement ou qui sont exclus du processus d’ajustement des coûts.

### <a name="about-item-batches"></a>À propos des lots d'articles

Vous pouvez exécuter l’ajustement des coûts sur plusieurs articles en les regroupant par lots. Les lots facilitent l’ajustement de certains éléments séparément, par exemple, car leur ajustement prend plus de temps. Les lots peuvent également aider à identifier les éléments présentant des problèmes.

Pour créer un lot, sur la page **Ajustement du coût de l’inventaire**, effectuez l’une des opérations suivantes :

* Sélectionnez les éléments dans la liste, choisissez **Exécuter l’ajustement des coûts**, puis choisissez **Ajouter un lot**.
* Pour créer un lot et exécuter immédiatement l’ajustement des coûts, sélectionnez les articles dans la liste, choisissez **Exécuter l’ajustement des coûts**, puis choisissez **Ajouter un lot et exécuter**.
* Choisir **Exécuter l’ajustement des coûts**, choisir **Lots d’articles**, puis entrez un filtre dans le champ **Filtrer les articles** champ.
  
> [!TIP]
> Pour créer rapidement un autre lot pour tous les articles qui ne sont pas déjà inclus dans un lot, sur le **Ajustement des coûts - Lots d’articles** page, choisissez **Ajouter les articles manquants**.

Lorsqu’une exécution d’un lot se termine, le lot présente l’un des états suivants sur la page **Lots d’articles** :

* **Succès** : L’ajustement des coûts est réussi.
* **Échoué** : Si l’ajustement des coûts échoue, [!INCLUDE [prod_short](includes/prod_short.md)] identifie l’élément à l’origine de l’erreur, puis divise le lot actuel en deux. Un lot avec l’article problématique et un autre avec les articles restants. L’ajustement des coûts est réexécuté pour le lot contenant les articles restants. S’il échoue à nouveau, le processus se répète. Vous définissez le nombre maximum de fractionnements dans le **Max. Nouvelles tentatives** champ. La valeur par défaut pour les tentatives est de 10, mais vous pouvez saisir une nouvelle limite.
* **Fin du temps** : Si l’ajustement des coûts d’un lot ne se termine pas dans le délai spécifié dans le **Délai d’expiration (minutes)** (allant de 1 à 720 minutes), la session se termine et les modifications sont annulées. [!INCLUDE [prod_short](includes/prod_short.md)] divise ensuite le lot actuel en deux et réexécute le processus d’ajustement des coûts pour chaque moitié. Ce processus se poursuit jusqu’à ce que l’ajustement des coûts réussisse ou atteigne le nombre maximal de tentatives.

> [ASTUCE !] Chaque lot s’exécute dans une session distincte. Pour suivre la progression, utilisez l’action **Actualiser** .

### <a name="run-cost-adjustment"></a>Ajustement des coûts d’exécution

Utilisez la page **Ajustement du coût de l’inventaire** pour effectuer des ajustements.

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **Ajustement du coût de l’inventaire**, puis choisissez le lien associé.
1. En fonction de ce que vous souhaitez faire, utilisez l’une des options suivantes :

  * Pour un ou plusieurs articles immédiatement, sélectionnez les articles dans la liste, puis choisissez **Exécuter l’ajustement des coûts**.
  * Pour les lots, utilisez l’une des options suivantes :

    * Pour créer un lot et Ajustement les coûts immédiatement, sélectionnez les articles dans la liste, choisissez **Exécuter l’ajustement des coûts**, puis **Ajouter un lot et exécuter**.
    * Pour l’exécuter pour tous les lots, choisissez **Exécuter l’ajustement des coûts**, **Lots d’articles**, puis choisissez **Exécuter**.
    
    Pour en savoir plus sur les lots, consultez [A propos des lots d'articles](#about-item-batches).

### <a name="explore-item-details"></a>Explorer les Détails article

Utilisez le menu **Article** pour accéder aux informations sur les ajustements de coût pour un article sélectionné.

* **Écritures article** : répertorie les écritures article pour l’article. L’action **Marquer pour ajustement** vous permet de forcer la réexécution de l’ajustement des coûts pour les articles directement ou indirectement liés aux écritures entrantes que vous sélectionnez. Forcer une réexécution peut être utile si les exécutions précédentes ont conduit à des coûts incorrects.
* **Écritures de valeur** : répertorie les entrées de valeur pour l’élément.
* **Points d’entrée ajust. coûts** : ouvrez le **Point d’entrée ajustement coût moyen**, que vous utilisez principalement pour calculer le coût moyen. La page affiche les combinaisons d’articles, d’emplacements, de variantes et de dates de valorisation pour lesquelles des ajustements de coûts sont ou doivent être exécutés.
* **Ajustement des coûts commandes** : ouvrez la page **Écriture ajust. inventaire (commandes)**, dans laquelle vous ajustez les ordres de production et d’assemblage. Il montre que les commandes sont ajustées ou nécessitent un ajustement.

### <a name="view-the-outcome"></a>Affichez le résultat

Utilisez le menu **Journal par** pour afficher le résultat des ajustements de coûts :

* **Exécution** : affiche les journaux d’ajustement des coûts pour chaque exécution. Le journal comprend des données sur le filtre d’élément, l’état (Succès/Échec/Expiration du délai), la date/heure de début et de fin, la durée et les différences de coûts produites par l’exécution.
* **Article** : Afficher des informations détaillées sur le processus d’ajustement pour l’élément sélectionné.

### <a name="include-or-exclude-items-from-adjustments"></a>Inclure ou exclure des éléments des ajustements

Si un ou plusieurs éléments échouent, vous pouvez les exclure de l’exécution d’ajustement, puis les inclure dans les exécutions ultérieures. Sur menu **Fonctions**, choisissez l'une des fonctions suivantes :

* **Exclure l’article de l’ajustement** et **Inclure l’article dans l’ajustement** : désactivez temporairement, puis réactivez l’ajustement des coûts pour un article sélectionné. L’ajustement des coûts continue de garantir l’exactitude des coûts pour d’autres articles pendant que vous étudiez un problème avec un article spécifique.

## <a name="post-adjusted-costs-to-the-general-ledger"></a>Reporter les coûts ajustés dans le grand livre

En règle générale, les nouvelles écritures valeur sont reportées dans le grand livre conformément au calendrier de l’écriture file d’attente des projets **Reporter coût de l’inventaire au GL (1002)** . Toutefois, vous pouvez reporter immédiatement les ajustements dans le grand livre à partir de la page **Ajustement du coût de l’inventaire**. Dans le menu **Fonctions** , choisissez **Reporter le coût de l’inventaire au grand livre**.

## <a name="troubleshoot-cost-adjustments"></a>Résoudre les problèmes d’ajustement des coûts

Utilisez les options suivantes du menu **Diagnostics** pour dépanner les exécutions d’ajustement des coûts.

* **Exporter les données de l’article** : exportez les données relatives à l’article vers un fichier texte. Vous pouvez utiliser le fichier pour une analyse plus approfondie dans un environnement sandbox ou le joindre à une demande d’assistance lors de l’enquête sur des problèmes de calcul des coûts.
* **Importer les données de l’article** : réimportez le fichier texte précédemment exporté dans la base de données. Cette action n’est activée que dans les environnements sandbox ou les compagnies d’évaluation.
* **Coût de réinitialisation ajusté** : réinitialisez le bouton à bascule **Coût ajusté** sur les articles, les bons de production ou les ordres d’assemblage. Ce paramètre vous permet de forcer la réexécution de l’ajustement des coûts pour eux.
* **Rapport de détection des problèmes de calcul des coûts** : diagnostique les problèmes de données typiques qui entraînent des erreurs de calcul dans le calcul des coûts. Il vérifie si les écritures articles, les écritures valeur, les écritures applications article et les écritures capacité sont correctes.
* **Supprimer les données d’article** : effacez toutes les tables liées aux articles dans la base de données. Cette action n’est disponible que dans les environnements sandbox ou les compagnies d’évaluation.

## <a name="see-also"></a>Voir aussi .

[Ajustement coûts article](inventory-how-adjust-item-costs.md)  
[Détails de conception : ajustement des coûts](design-details-cost-adjustment.md)  
