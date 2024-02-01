---
title: Introduction à la gestion des projets Contoso Coffee
description: Cet article vous présente les données de démonstration Contoso Coffee pour la gestion des projets.
author: andreipanko
ms.author: andreipa
ms.topic: how-to
ms.date: 05/31/2023
ms.custom: bap-template
ms.service: dynamics-365-business-central
---

# Introduction à la gestion des projets Contoso Coffee

Contoso Coffee est une compagnie fictive qui produit des cafetières grand public et commerciales. Les applications **Contoso Coffee** pour Business Central ajoutent des données de démonstration que vous pouvez utiliser pour apprendre à utiliser les fonctionnalités de gestion des projets dans Business Central.

Cette application fournit plusieurs éléments qui sont utilisés pour les procédures détaillées principales :

- Ressources avec des compétences et des zones attribuées
- Articles configurés pour créer des articles de service

> [!IMPORTANT]
> Avant d’exécuter l’un des scénarios pour Contoso Coffee, reportez toutes les lignes journal article avec soldes d’ouverture. Pour connaître plus d’exigences, voir la section [Configurer les données de Contoso Coffee](#set-up-contoso-coffee-jobs-and-project-management-data).
>
> 
## Configurer les données de gestion des projets Contoso Coffee

[!INCLUDE [contoso-coffee-app-install](../../includes/contoso-coffee-app-install.md)]

Une fois que les applications appropriées sont installées, accédez à la page [Données de démonstration de projets Contoso Coffee](https://businesscentral.dynamics.com/?page=4767) dans [!INCLUDE [prod_short](../../includes/prod_short.md)] et modifiez les paramètres par défaut en fonction de vos besoins. Les tableaux suivants décrivent les paramètres :  

|Champ  |Description  |
|---------|---------|
|**Année de début** |Spécifie la première année que vous souhaitez utiliser pour les données de démonstration Contoso Coffee. Selon la configuration de la compagnie, l’année est soit une année civile, soit une année fiscale.|
|**N° de client**  |Le client à utiliser pour les scénarios dans les opérations de vente.|
|**N° article 1**  |L’article à utiliser pour les scénarios de contrat.|
|**N° article 2**  |L’article à utiliser pour les scénarios de dépannage.|
|**N° ressource locale 1**  |La ressource à utiliser pour les scénarios de contrat.|
|**N° ressource distante 1**  |La ressource à utiliser pour les scénarios de dépannage.|
|**Groupe de report client**|Spécifie un code entreprise pour les clients nationaux. Les codes entreprise sont utilisés lors du report des transactions. |
|**Groupe de report marché client**|Spécifie un code entreprise pour les clients nationaux. Les codes entreprise sont utilisés lors du report des transactions. |
|**National : groupe de report de marché**|Spécifie un code entreprise pour les clients et fournisseurs nationaux. Les codes entreprise sont utilisés lors du report des transactions. |
|**Négoce - Groupe de report inventaire**    |Spécifie un code pour les articles qui doivent être utilisés pour reporter la revente.|
|**Détail : groupe de report de produit**    |Spécifie un code pour les articles qui doivent être utilisés pour valider la vente de détail.|
|**Groupe de report produit TVA**    |Spécifie un code produit TVA pour les articles pour le report de la TVA si la TVA est activée.|
|**Facteur de prix**     |Spécifie un facteur pour convertir un prix USD/EUR en devise locale. *1* signifie que le prix est le même dans n’importe quelle devise. Un nombre plus élevé sera utilisé pour obtenir le prix dans la devise locale. |
|**Précision arrondissement**  |Définit comment les quantités consommées calculées sont arrondies une fois saisies sur les lignes journal consommation. Les quantités inférieures à 0,5 sont arrondies au chiffre inférieur. Les quantités égales ou supérieures à 0,5 sont arrondies au chiffre supérieur.|

Une fois que vous êtes prêt, choisissez l’action **Créer des données de démonstration**. L’ajout des données à la base de données sous-jacente prend quelques minutes, mais vous êtes ensuite prêt à exécuter les différents scénarios.  

## Voir aussi .
