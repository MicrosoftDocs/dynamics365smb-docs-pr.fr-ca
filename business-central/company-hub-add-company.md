---
title: Ajouter des compagnies à votre Hub Entreprise
description: Découvrez comment ajouter des compagnies d’autres environnements Business Central à votre Hub Entreprise afin de pouvoir gérer le travail dans tous les environnements.
author: edupont04
ms.service: dynamics365-business-central
ms.topic: article
ms.search.keywords: accountant, accounting, company hub
ms.date: 10/01/2020
ms.author: edupont
ms.openlocfilehash: 773731ecc860e7d1ea0d13bbf9e6896a746544be
ms.sourcegitcommit: ddbb5cede750df1baba4b3eab8fbed6744b5b9d6
ms.translationtype: HT
ms.contentlocale: fr-CA
ms.lasthandoff: 10/01/2020
ms.locfileid: "3927784"
---
# <a name="add-companies-to-your-company-hub"></a>Ajouter des compagnies à votre Hub Entreprise

Avec le Hub Entreprise, vous pouvez accéder à votre travail à partir de plusieurs compagnies à partir de plusieurs environnements [!INCLUDE [prodshort](includes/prodshort.md)]. Vous pouvez ajouter manuellement des environnements et des compagnies si vos compagnies ne s’affichent pas automatiquement dans le Hub Entreprise.  

Sur la page de destination du Hub Entreprise, vous trouvez le menu **Configurer** , à partir duquel vous pouvez accéder à la page **Liens d’environnements** . Il suffit de sélectionner **Nouveau** , puis de renseigner les champs. [!INCLUDE [tooltip-inline-tip_md](includes/tooltip-inline-tip_md.md)]  

## <a name="environment-links"></a>Liens d’environnements

Un lien d’environnement est une fiche sur laquelle vous spécifiez l’environnement [!INCLUDE [prodshort](includes/prodshort.md)] qui héberge une ou plusieurs compagnies dans lesquelles vous travaillez. Les données de la fiche de chaque environnement sont spécifiées par vous, et vous pouvez les modifier selon vos besoins. Toutefois, le champ **Lien d’environnement** est indispensable, car il vous permet d’accéder à chaque compagnie dans [!INCLUDE [prodshort](includes/prodshort.md)]. Utilisez l’action **Tester la connexion** dans le ruban pour vérifier que vous avez saisi le bon lien. Le lien que vous devez saisir pointe vers l’environnement qui héberge la compagnie que vous ajoutez et doit inclure le code Azure Active Directory (Azure AD) ou le nom de domaine de l’organisation. Par exemple, s’il a spécifié un domaine tel que MyBusiness.com, le lien vers son instance [!INCLUDE [prodshort](includes/prodshort.md)] est ```https://businesscentral.dynamics.com/mybusiness.com?redirectedfromsignup=1```. Sinon, cela ressemblera à ceci : ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```  

Le lien est utilisé lorsque vous choisissez la compagnie dans le Hub Entreprise.  

:::image type="content" source="media/company-hub-company-list-actions.png" alt-text="Actions pour une compagnie répertoriée dans le Hub Entreprise":::

> [!TIP]
> Si vous travaillez dans la version d’essai gratuite de [!INCLUDE [prodshort](includes/prodshort.md)], il est facile d’ajouter les compagnies dans votre abonné. Vous pouvez trouver le lien d’environnement en copiant le code Azure Active Directory de la section **Dépannage** de la page Aide et support. Le nom de l’environnement est probablement la valeur par défaut, PRODUCTION. Ajoutez ces informations au champ **Lien d’environnement** , tel que ```https://businesscentral.dynamics.com/1a23b456-789c-0123-45de-678910fg12h/production?redirectedfromsignup=1```, puis choisissez **Tester la connexion** . La compagnie d’évaluation sera ajoutée à la liste.
>
> Si vous êtes passé à la compagnie d’essai de trente jours, Ma compagnie, vous pouvez l’ajouter à la liste en choisissant l’action **Recharger/Recharger toutes les compagnies** dans la liste.

## <a name="load-companies"></a>Charger des compagnies

Lorsque vous avez ajouté vos environnements, vos compagnies s’affichent automatiquement. Cependant, si vous savez qu’une nouvelle compagnie a été ajoutée à un environnement, vous pouvez choisir l’action **Recharger toutes les compagnies** pour actualiser la liste. Utilisez la même action pour actualiser les données de toutes vos compagnies.  

> [!TIP]
> Afin d’actualiser les données dans le Hub Entreprise, vous devez avoir accès aux données des compagnies dont les données proviennent.

## <a name="see-also"></a>Voir aussi

[Gérer le travail entre plusieurs compagnies dans le Hub Entreprise](company-hub.md)  
[Ressources pour l'aide et l'assistance technique](product-help-and-support.md)  
