---
title: Configurer des tarifs de projets et des groupes de comptabilisation de projet| Microsoft Docs
description: Décrit comment configurer des informations générales de projets et des prix d'articles de projet, des ressources, ainsi que des comptes du grand livre et des groupes de report projet.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: conceptual
ms.workload: na
ms.search.keywords: project management
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 04f5538b7c904b64c921cc50f64924bcaef93401
ms.sourcegitcommit: a9b771cc2b4b75aed835efca63ef7a6a44219d59
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 02/18/2021
ms.locfileid: "5476780"
---
# <a name="set-up-jobs"></a>Configuration de projets

En tant que chef de projet, vous pouvez définir des projets qui définissent chacun des projets que vous gérez dans [!INCLUDE[prod_short](includes/prod_short.md)]. Sur la page **Configuration des projets**, vous devez spécifier comment utiliser certaines fonctions de projet.

Pour chaque projet, vous précisez ensuite les fiches projet individuelles avec des informations concernant les prix pour les articles, les ressources et les comptes du grand livre du projet, puis vous devez configurer des groupes de report projet.

## <a name="to-set-general-information-for-jobs"></a>Pour configurer des informations générales pour les projets
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Configuration projets**, puis sélectionnez le lien associé.
2. Renseignez les champs selon vos besoins. [!INCLUDE[tooltip-inline-tip](includes/tooltip-inline-tip_md.md)]

> [!NOTE]
> L'impact du champ **Appliquer le lien d'utilisation par défaut** est assez complexe et est donc expliqué dans la section suivante.

### <a name="to-set-up-job-usage-tracking"></a>Pour configurer un suivi d'utilisation de projet

Lors de l'exécution d'un projet, vous aurez peut-être besoin de savoir si votre utilisation est conforme au plan. Pour entreprendre facilement cette tâche, vous pouvez créer un lien entre vos lignes planification du projet et l'utilisation réelle. Cela vous permet de suivre vos coûts et de voir aisément le travail qui reste à effectuer. Par défaut, le type de ligne planification projet est **Budget**, mais l'utilisation du type de ligne **Budget et Facturable** a des effets similaires.

Si vous sélectionnez le champ **Appliquer le lien d'utilisation par défaut**, vous pouvez alors consulter les informations sur la ligne planification projet. Vous pouvez définir la quantité de la ressource, de l'article ou le compte GL, puis indiquer la quantité que vous souhaitez transférer vers le journal projet. Le champ **Quantité restante** dans la ligne planification projet vous aide à déterminer ce qui reste à transférer et à reporter dans le journal projet.

> [!TIP]  
> Vous pouvez activer ou désactiver le suivi de l'utilisation des projets pour un projet spécifique. La valeur du champ **Appliquer le lien d'utilisation** de la fiche projet individuelle remplace le paramètre de la page **Configuration projets**.  

Lorsque la case à cocher **Appliquer le lien d'utilisation par défaut** est activée et que le type de ligne planification projet est défini sur **Facturable**, une ligne planification projet de type **Budget** est créée une fois la ligne journal projet reportée.

> [!IMPORTANT]
> Si le suivi de l'utilisation des projets est activé, sur la page **Configuration projets** ou sur le projet individuel, et si le champ **Type ligne** sur la ligne journal projet est vide, alors des lignes planification projet de type ligne **Budget** sont créées lorsque vous reportez des lignes journal.  
>  
> Si le suivi de l'utilisation des projets n'est *pas* activé, sur la page **Configuration projets** ou sur le projet individuel, et si le champ **Type ligne** de la ligne journal projet est vierge, aucune ligne planification projet n'est créée lorsque vous reportez les lignes journal projet. Pour plus d'informations, voir [Enregistrer l'utilisation pour les projets](projects-how-record-job-usage.md).

1. Sélectionnez l'icône ![Page ou rapport pour la recherche](media/ui-search/search_small.png "Icône Page ou rapport pour la recherche"), saisissez **Configuration projets**, puis sélectionnez le lien associé.
2. Sélectionnez la case à cocher **Appliquer le lien d'utilisation par défaut**.

## <a name="to-set-up-prices-for-resources-items-and-general-ledger-accounts-for-jobs"></a>Pour paramétrer les prix pour des ressources, des articles et des comptes GL pour des projets
> [!NOTE]
> Dans la deuxième vague de lancement de 2020, nous avons libéré de nouveaux processus pour la configuration et la gestion des prix et des escomptes. Si vous êtes un nouveau client, vous utilisez la nouvelle expérience. Si vous êtes un client existant, l’utilisation ou non de la nouvelle expérience dépend du fait que votre administrateur a activé ou non la fonctionnalité **Nouvelle tarification des ventes** dans **Gestion des fonctionnalités**. Pour plus d’informations, consultez [Activer les fonctionnalités à venir à l’avance](/dynamics365/business-central/dev-itpro/administration/feature-management).

Vous pouvez paramétrer les prix pour des articles, des ressources et des comptes GL associés à un projet. 

#### <a name="current-experience"></a>[Expérience actuelle](#tab/current-experience)
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Projets**, puis sélectionnez le lien associé.  
2. Sélectionnez le projet, puis cliquez sur l’action **Ressource**, **Article** ou **Compte du grand livre**.
3. Sur la page **Prix ressource projet**, **Prix article projet** ou **Prix compte du grand livre projet**, remplissez les champs selon vos besoins.

Le tableau suivant montre comment les informations des champs facultatifs seront utilisées sur les lignes planification projet et les journaux lorsque la ressource, l’article ou le compte GL sont choisis pour le projet.

|Colonne1  |Colonne2  |
|---------|---------|
|**Ressources du projet**|Champs **N° tâche projet**, **Type travail**, **Code devise**, **% escompte ligne** et **Facteur coût unitaire**. La valeur du champ **Prix unitaire** de la ressource sera utilisée sur les lignes planning du projet et les feuilles projet lorsque cette ressource, une ressource affectée au groupe de ressources ou une ressource quelconque est entrée. Notez que ce prix remplace toujours les prix paramétrés sur la page **Prix ressource/Prix groupe ressources** existante.|
|**Articles du projet**|Champs **N° tâche projet**, **Code devise** et **% escompte ligne**. La valeur du champ **Prix unitaire** pour l'article sera utilisée sur les lignes planning du projet et les feuilles projet lorsque cet article sera entré. Notez que ce prix remplace toujours le prix client habituel (mécanisme du « meilleur prix ») des articles. Pour utiliser les mécanismes des prix client habituels, ne créez pas de prix article projet pour le projet.|
|**Comptes GL**|Les informations contenues dans les champs **N° tâche projet**, **Code devise**, **% escompte ligne**, **Facteur coût unitaire** et **Coût unitaire** serviront sur les lignes planification projet et les journaux projet lorsque ce compte GL sera entré et ajouté à un projet. La valeur du champ **Prix unitaire** pour les dépenses du compte général sera utilisée sur les lignes planning du projet et les feuilles projet lorsque le compte général sera entré.|

---
#### <a name="new-experience"></a>[Nouvelle expérience](#tab/new-experience)
1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), entrez **Projets**, puis sélectionnez le lien associé.  
2. Sélectionnez le projet concerné, puis cliquez sur l’action **Listes prix vente**.

---

## <a name="to-set-up-job-posting-groups"></a>Pour configurer les groupes compta. projet
L'un des aspects des projets de planification est de décider quels comptes de report utiliser pour l'évaluation de l'inventaire projet. Pour reporter des projets, vous configurez des comptes afin de reporter chaque groupe de report projet. Un groupe report représente un lien entre le projet et la manière dont il doit être traité dans le grand livre. Lorsque vous créez un projet, vous pouvez spécifier un groupe de report et, par défaut, chaque tâche que vous créez pour le projet est associée avec ce groupe de report. Toutefois, lorsque vous créez des tâches, vous pouvez remplacer la valeur par défaut et sélectionner un groupe de report plus approprié.  

> [!NOTE]  
>   Les comptes nécessaires dans la table Plan comptable doivent être configurés avant de créer les groupes comptabilisation. Pour plus d'informations, reportez-vous à [Configuration ou modification du plan comptable](finance-setup-chart-accounts.md).  

1. Choisissez l'icône ![Ampoule qui ouvre la fonction Tell Me](media/ui-search/search_small.png "Dites-moi ce que vous voulez faire"), saisissez **Groupes de report projet**, puis sélectionnez le lien associé.  
2. Cliquez sur **Nouveau**, puis renseignez les champs du compte comme indiqué dans le tableau suivant.  

| Champ de compte | Description |
| --- | --- |
| **Code** |Un code pour le groupe de report. Vous pouvez entrer un maximum de 10 caractères, espaces compris. |
| **Compte dépenses TEC** |Compte TEC pour les dépenses calculées des TEC du projet, qui est un compte d'actif capital de bilan. |
| **Compte coûts à payer TEC** |Compte pour la méthode Valeur coût ou Coût des ventes du calcul TEC, qui est un compte de passif bilan de charge accumulé. Reporté lorsque l'ajustement TEC exige l'augmentation des coûts utilisation reportés dans l'état des résultats. |
| **Compte coûts lettrés projet** |Un compte de contrepartie du Compte dépenses TEC, qui est un compte de contrepartie de frais négatif. |
| **Compte coûts lettrés article** |Un compte de contrepartie du Compte dépenses TEC, qui est un compte de contrepartie de frais négatif. |
| **Compte coûts lettrés ressource** |Un compte de contrepartie du Compte dépenses TEC, qui est un compte de contrepartie de frais négatif. |
| **Compte coûts lettrés** |Un compte de contrepartie du Compte dépenses TEC, qui est un compte de contrepartie de frais négatif. |
| **Compte ajustement coûts projet** |Compte de contrepartie du compte coûts accumulés TEC, qui est un compte de frais. |
| **Compte frais Général (budget)** |Le compte ventes qui sera utilisé pour les dépenses GL dans les tâches projet avec ce groupe de report. S'il n'est pas renseigné, le compte du grand livre entré sur la ligne planification projet est utilisé. |
| **Compte ventes à payer TEC** |Compte TEC pour la valeur des ventes calculée des TEC, qui est un compte Produit accumulé bilan. Reporté lorsque l'ajustement TEC exige l'augmentation du revenu réceptionné. |
| **Compte ventes facturées TEC** |Compte pour la valeur des ventes facturées des TEC qui ne peuvent pas être réceptionnés. Il s'agit d'un compte bilan produit comptabilisé d'avance. |
| **Compte ventes lettrées projet** |Compte de contrepartie du Compte ventes facturées TEC, qui est un compte de contrepartie de revenu. |
| **Compte ajustement vente projet** |Compte de contrepartie du Compte ventes projet TEC, qui est un compte de revenu. |
| **Compte coûts récep.** |Compte frais contenant les coûts réceptionnés du projet. Il s'agit ordinairement d'un compte frais pour débit. |
| **Compte ventes récep.** |Compte de revenu contenant les revenus réceptionnés du projet. Il s'agit ordinairement d'un compte de revenu pour crédit. |

## <a name="see-also"></a>Voir aussi

[Configurer la gestion de projet](projects-setup-projects.md)  
[Vidéo : Créer un projet dans Dynamics 365 Business Central](https://www.youtube.com/watch?v=VqaPWr7BWmw)  
[Gestion des projets](projects-manage-projects.md)  
[Finance](finance.md)  
[Procédure d'achat](purchasing-manage-purchasing.md)  
[Vente](sales-manage-sales.md)  
[Utilisation de [!INCLUDE[prod_short](includes/prod_short.md)]](ui-work-product.md)  


[!INCLUDE[footer-include](includes/footer-banner.md)]