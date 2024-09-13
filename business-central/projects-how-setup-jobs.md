---
title: 'Configurer des projets, des prix et des groupes de report projet'
description: Décrit comment configurer des informations générales sur les projets.
author: brentholtorf
ms.author: bholtorf
ms.reviewer: bholtorf
ms.topic: how-to
ms.date: 02/22/2024
ms.custom: bap-template
ms.search.keywords: project management
ms.search.form: '211, 463, 1012'
ms.service: dynamics-365-business-central
---
# <a name="set-up-projects-prices-and-project-posting-groups"></a>Configurer des projets, des prix et des groupes de report projet

En tant que chef de projet, vous pouvez définir des projets qui définissent chacun des projets que vous gérez dans [!INCLUDE[prod_short](includes/prod_short.md)]. Utilisez la page **Configuration projets** pour définir la façon dont vous utilisez les fonctions du projet.

Pour chaque projet, précisez diverses informations :

* Prix des articles du projet
* Ressources de projet
* Comptes du grand livre du projet
* Groupes de report projet (requis)

## <a name="to-set-general-information-for-projects"></a>Pour configurer des informations générales pour les projets

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Configuration projets**, puis choisissez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> Le bouton bascule **Appliquer le lien d′utilisation par défaut** sur la page **Configuration projets** indique si les écritures projet sont liées aux lignes planification projet par défaut. Activez le bouton bascule pour appliquer ce paramètre à tous les nouveaux projets. Vous pouvez activer ou désactiver le suivi de l′utilisation des projets pour un projet donné en activant ou désactivant le bouton bascule **Appliquer le lien d′utilisation** sur la page **Fiche projet**.

### <a name="to-set-up-project-usage-tracking"></a>Spécifier un emplacement par défaut pour les éléments du projet

Vous pouvez gagner du temps lors de la saisie des données en spécifiant un emplacement et une zone par défaut pour les projets sur la page **Fiche projet** . Lorsque vous créez des tâches projet, des lignes planification projet et des lignes journal projet pour le projet, l’emplacement et la zone par défaut sont automatiquement attribués. Vous pouvez cependant modifier le code d’emplacement et la zone sur les tâches et les lignes si nécessaire.

Si vous définissez un **Code de zone avant projet** sur l’emplacement, le code de zone est renseigné lorsque vous sélectionnez le code d’emplacement. Si votre flux d’entrepôt nécessite des prélèvements entrepôt, vous pouvez également définir d’autres zones à partir desquelles consommer les articles.

Ces champs sont les champs par défaut lorsque vous créez des tâches de projet. Les tâches de projet existantes ne changent pas.

Il y a quelques choses à savoir sur l’utilisation des emplacements par défaut :

* Pour les tâches projet, si vous définissez un **Code de zone avant projet** sur l’emplacement, le code de zone est affecté lorsque vous sélectionnez le code d’emplacement. Si votre flux d’entrepôt nécessite des prélèvements entrepôt, vous pouvez également définir d’autres zones à partir desquelles consommer les articles.
* Pour les lignes de planification de projet, le **Code d’emplacement** est basé sur la valeur sélectionnée sur la ligne de planification de projet lorsque vous sélectionnez un article. Si aucun code de zone n’est défini pour la tâche de projet, la zone du contenu de la zone par défaut est sélectionnée. Vous pouvez modifier les deux valeurs manuellement.
* Pour les lignes journal projet, le **Code d’emplacement** est basé sur la valeur sélectionnée sur la ligne journal projet lorsque vous sélectionnez un article. Si aucun code de zone n’est défini pour la tâche de projet, la zone du contenu de la zone par défaut est sélectionnée. Vous pouvez modifier les deux valeurs manuellement.

### <a name="invoice-multiple-customers-for-project-tasks"></a>Facturer plusieurs clients pour les tâches du projet

Lorsque les projets impliquent plusieurs clients, facturer les bons clients pour les bonnes tâches peut s’avérer difficile. [!INCLUDE [prod_short](includes/prod_short.md)] simplifie la facturation en vous permettant de spécifier les clients à facturer et à vendre sur chaque ligne de tâche du projet, afin que vous puissiez générer automatiquement des factures pour les bons clients. Pour en savoir plus sur la facturation de plusieurs clients, accédez à [Facturer un ou plusieurs clients pour les tâches du projet](projects-how-create-jobs.md#invoice-one-or-more-customers-for-project-tasks).

### <a name="synchronize-the-cost-of-used-items"></a>Pour configurer un suivi d’utilisation de projet

Lors de l’utilisation d’un projet, vous avez peut-être besoin de savoir si votre utilisation est conforme au plan. Pour explorer l’utilisation, vous pouvez créer un lien entre vos lignes planification projet et l’utilisation réelle. Le lien vous permet de suivre vos coûts et de comprendre la quantité de travail restante. Par défaut, le type de ligne planification projet est **Budget**, mais l’utilisation du type de ligne **Budget et Facturable** a des effets similaires.

Après avoir configuré le suivi de l′utilisation en activant le bouton bascule **Appliquer le lien d’utilisation par défaut**, vous pouvez consulter les informations sur la ligne planification projet. Par exemple, vous pouvez définir la quantité de la ressource, de l’article ou du compte GL. Vous pouvez également définir la quantité à transférer vers le journal projet. Le champ **Quantité restante** sur la ligne planification projet indique ce qui reste à transférer et à reporter dans le journal projet.

>[!NOTE]
> Si le champ **Appliquer le lien d′utilisation** est sélectionné dans le projet et que le champ **Type ligne** sur la ligne journal projet ou la ligne achat est **Facturable**, de nouvelles lignes planification projet du type de ligne **Budget et Facturable** sont créées lorsque vous reportez la ligne journal ou le document achat.  
>
> Pour plus d′informations, voir [Enregistrer l′utilisation pour les projets](projects-how-record-job-usage.md) et [Gérer les fournitures de projet](projects-how-manage-project-supplies.md)

> [!IMPORTANT]
> Si vous ne spécifiez pas de valeur dans le champ **Type ligne** de la ligne journal projet ou la ligne achat, les lignes planification projet ne sont pas créées lorsque vous reportez le journal projet ou le document achat.

## <a name="to-set-up-prices-for-resources-items-and-general-ledger-accounts-for-projects"></a>Pour paramétrer les prix pour des ressources, des articles et des comptes GL pour des projets

> [!NOTE]
> Dans la deuxième vague de lancement de 2020, nous avons libéré de nouveaux processus pour la configuration et la gestion des prix et des escomptes. Si vous êtes un nouveau client, vous utilisez la nouvelle expérience. Si vous êtes un client existant, l’utilisation ou non de la nouvelle expérience dépend du fait que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes** dans **Gestion des fonctionnalités**. Pour plus d’informations, consultez [Activer les fonctionnalités à venir à l’avance](/dynamics365/business-central/dev-itpro/administration/feature-management).

Vous pouvez paramétrer les prix pour des articles, des ressources et des comptes GL associés à un projet. 

#### [Expérience actuelle](#tab/current-experience)

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **projet**, puis choisissez le lien associé.  
2. Sélectionnez le projet, puis cliquez sur l’action **Ressource**, **Article** ou **Compte du grand livre**.
3. Sur la page **Prix ressource projet**, **Prix article projet** ou **Prix compte du grand livre projet**, remplissez les champs selon vos besoins.

Lorsque vous choisissez une ressource, un article ou un compte GL pour un projet, [!INCLUDE [prod_short](includes/prod_short.md)] utilise des informations dans les champs facultatifs des lignes planification projet et des journaux projet. Le tableau suivant explique comment.

|Colonne1  |Colonne2  |
|---------|---------|
|**Ressources de projet**|Champs **N° tâche projet**, **Type travail**, **Code devise**, **% escompte ligne** et **Facteur coût unitaire**. La valeur du champ **Prix unitaire** de la ressource est utilisée sur les lignes planification projet et les journaux projet lorsque vous saisissez une ressource ou une ressource affectée au groupe de ressources. Ce prix remplace les prix spécifiés sur la page **Prix de la ressource/Prix du groupe de ressources**.|
|**Articles par projet**|Champs **N° tâche projet**, **Code devise** et **% escompte ligne**. La valeur du champ **Prix unitaire** pour l’article sera utilisée sur les lignes planification projet et les journaux projet lorsque cet article sera entré. Ce prix remplace le prix client habituel (mécanisme du « meilleur prix ») des articles. Pour utiliser le prix client habituel, ne spécifiez pas de prix article projet pour le projet.|
|**Comptes GL**|Les informations contenues dans les champs **N° tâche projet**, **Code devise**, **% escompte ligne**, **Facteur coût unitaire** et **Coût unitaire** serviront sur les lignes planification projet et les journaux projet lorsque ce compte GL sera entré et ajouté à un projet. Lorsque vous choisissez un compte GL, des lignes planification projet et des journaux projet, utilisez la valeur du champ **Prix unitaire** pour les dépenses de projet GL.|

#### [Nouvelle expérience](#tab/new-experience)

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") saisissez **projets**, puis choisissez le lien associé.  
2. Sélectionnez le projet concerné, puis cliquez sur l’action **Listes prix vente**.

---

## <a name="to-set-up-project-posting-groups"></a>Pour configurer des groupes de report projet

L’un des aspects des projets de planification est de décider quels comptes de report utiliser pour l’évaluation du stock projet. Pour reporter des projets, vous configurez des comptes afin d’effectuer le report pour chaque groupe de report projet. Un groupe de report représente un lien entre le projet et la manière dont il doit être traité dans le grand livre. Lorsque vous créez un projet, vous spécifiez un groupe de report et, par défaut, chaque tâche que vous créez pour le projet est associée avec ce groupe de report. Toutefois, lorsque vous créez des tâches, vous pouvez remplacer la valeur par défaut et sélectionner un groupe de report plus approprié.  

> [!NOTE]  
> Vous devez configurer les comptes dans le plan comptable avant de configurer les groupes de report. Pour plus d'informations, reportez-vous à [Configuration ou modification du plan comptable](finance-setup-chart-accounts.md).  

1. Sélectionnez l’icône ![Ampoule qui ouvre la fonction Tell Me.](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire") entrez **Groupes de report projet**, puis choisissez le lien associé.  
2. Cliquez sur l’action **Nouveau**, puis renseignez les champs comme indiqué dans le tableau suivant.  

| Champ de compte | Désignation | Utilisé dans le type TEC |
| --- | --- |  --- |
| **Code** |Identificateur pour le groupe de report. Vous pouvez entrer un maximum de 10 caractères, espaces compris. | |
| **Compte dépenses TEC** |Compte TEC pour les dépenses calculées des TEC du projet, qui est un compte d’actif capital de bilan. | Coût affecté, Coûts reconnus|
| **Compte coûts à payer TEC** |Compte pour la méthode Valeur coût ou Coût des ventes du calcul TEC. Ce compte concerne le passif bilan de charge accumulé sur votre bilan. Lorsqu’un ajustement TEC vous oblige à augmenter les coûts utilisation que vous reportez dans votre compte de gestion, vous les reportez dans ce compte. | Coûts accumulés|
| **Compte coûts affectés projet** |Un compte de contrepartie du Compte dépenses TEC, qui est un compte de contrepartie de frais négatif. Utilisé lorsque **Méthode de report TEC utilisée** est définie sur *Projet*. | Coûts affectés, Coûts reconnus|
| **Compte coûts lettrés article** |Identique à **Compte coûts affectés projet**, mais utilisé lorsque **Méthode de report TEC utilisée** est définie sur *Écriture projet*.| |
| **Compte coûts lettrés ressource** |Identique à **Compte coûts affectés projet**, mais utilisé lorsque **Méthode de report TEC utilisée** est définie sur *Écriture projet*.| |
| **Compte coûts affectés général** |Identique à **Compte coûts affectés projet**, mais utilisé lorsque **Méthode de report TEC utilisée** est définie sur *Écriture projet*.| |
| **Compte ajustement coûts projet** |Compte de contrepartie du compte coûts accumulés TEC, qui est un compte de frais. | Coûts accumulés|
| **Compte frais Général (budget)** |Le compte ventes qui sera utilisé pour les dépenses générales dans les tâches projet avec ce groupe de report. S’il n’est pas renseigné, le compte GL entré sur la ligne planification projet est utilisé. | |
| **Compte ventes à payer TEC** |Compte TEC pour la valeur des ventes calculée des TEC, qui est un compte Produit accumulé pour votre bilan. Lorsqu’un ajustement TEC vous oblige à augmenter le revenu réceptionné, vous le reportez dans ce compte. | Ventes accumulées, ventes reconnues|
| **Compte ventes facturées TEC** |Compte pour la valeur des ventes facturées des TEC qui ne peuvent pas être réceptionnés. Il s'agit d'un compte bilan produit comptabilisé d'avance. | Ventes reconnues, Ventes affectées|
| **Compte ventes affectées projet** |Compte de contrepartie du Compte ventes facturées TEC, qui est un compte de contrepartie de revenu. | Ventes affectées, Ventes reconnues|
| **Compte ajustement vente projet** |Compte de contrepartie du Compte ventes projet TEC, qui est un compte de revenu. | Ventes accumulées|
| **Compte coûts récep.** |Compte frais contenant les coûts réceptionnés du projet. Il s'agit ordinairement d'un compte frais pour débit. | Coûts réceptionnés|
| **Compte ventes récep.** |Compte de revenu contenant les revenus réceptionnés du projet. Il s'agit ordinairement d'un compte de revenu pour crédit. | Ventes réceptionnées|

## <a name="see-also"></a>Voir aussi .

[Configurer la gestion de projet](projects-setup-projects.md)  
[Vidéo : Créer un projet dans Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Gestion des projets](projects-manage-projects.md)  
[Finances](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Ventes](sales-manage-sales.md)  
[Utiliser [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  

[!INCLUDE[footer-include](includes/footer-banner.md)]
