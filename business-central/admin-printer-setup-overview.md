---
title: Vue d’ensemble de la configuration et de la gestion de l’imprimante
description: Découvrez les différentes opportunités d’impression dans Business Central
author: jswymer
ms.author: jswymer
ms.reviewer: jswymer
ms.service: dynamics-365-business-central
ms.topic: overview
ms.date: 09/28/2023
ms.custom: bap-template
---

# <a name="printer-setup-and-management-overview"></a>Vue d’ensemble de la configuration et de la gestion de l’imprimante

[!INCLUDE[azure-ad-to-microsoft-entra-id](~/../shared-content/shared/azure-ad-to-microsoft-entra-id.md)]

Impression de documents et de rapports à partir de [!INCLUDE[prod_short](includes/prod_short.md)] est une tâche importante pour les utilisateurs professionnels. Les utilisateurs voudront généralement envoyer des travaux d′impression directement à l′une des imprimantes de votre organisation&mdash; peu importe quel client ou application [!INCLUDE[prod_short](includes/prod_short.md)] ils utilisent. Étant donné que [!INCLUDE[prod_short](includes/prod_short.md)] Online est un service en nuage, il ne peut pas atteindre directement les imprimantes locales connectées aux appareils des utilisateurs, mais il peut se connecter à des imprimantes compatibles dans le nuage.

## <a name="what-are-your-printer-possibilities-in-business-central"></a>Quelles sont vos possibilités d’impression dans Business Central ?

Pour répondre à vos besoins d'impression, [!INCLUDE[prod_short](includes/prod_short.md)] offre les fonctionnalités suivantes :

|Fonctionnalité|Description|Client web| Application mobile|Application pour Teams|
|-------|-----------|----------|-----------|--------------|
|Impression universelle|L'impression universelle est une solution de gestion d'imprimante disponible en tant que service en nuage de Microsoft. Avec cette fonction, vous pouvez configurer vos imprimantes dans l'impression universelle, puis les enregistrer pour une utilisation dans [!INCLUDE[prod_short](includes/prod_short.md)]. Cette fonctionnalité nécessite un abonnement d′impression universelle et l′extension **Intégration d′impression universelle**.|![fonctionne en ligne.](media/check.png)|![fonctionne en ligne.](media/check.png)|![fonctionne en ligne](media/check.png)|
|Impression par courriel|Cette fonction vous permet de configurer des imprimantes compatibles avec la messagerie électronique. [!INCLUDE[prod_short](includes/prod_short.md)] envoie ensuite les travaux d'impression à une imprimante à l'aide de l'adresse de courriel de l'imprimante. Cette fonction nécessite des imprimantes compatibles avec la messagerie électronique et l'extension **Envoyer à une imprimante par courriel**.|![fonctionne en ligne.](media/check.png)|![fonctionne en ligne](media/check.png)|![fonctionne en ligne](media/check.png)|
|Impression du navigateur|Les travaux d'impression sont gérés par la fonctionnalité d'impression du navigateur de l'utilisateur. Si aucune imprimante en nuage n’est installée et configurée ou si une imprimante installée échoue, l’impression reprend par défaut les options d’impression du navigateur. Le champ **Imprimante** de la page de demande de rapport affichera *(Géré par le navigateur)*.|![fonctionne en ligne](media/check.png)|||

La majeure partie du travail de configuration des imprimantes peut être effectué à partir de la page **Gestion des imprimantes** dans [!INCLUDE[prod_short](includes/prod_short.md)]. Bien que disposant des imprimantes Impression universelle, vous devrez peut-être également travailler dans le centre d’administration Microsoft 365 ou le portail Azure.

> [!IMPORTANT]
> Pour Business Central en local, l’Impression universelle et l’impression de courriels nécessitent l’utilisation de l’authentification Microsoft Entra ID ou NavUserPassword.

## <a name="custom-printer-extensions"></a>Extensions d’imprimante personnalisées

[!INCLUDE[prod_short](includes/prod_short.md)] prend également en charge les extensions d′imprimante personnalisées qui ajoutent encore plus de fonctionnalités d′impression. Ainsi, si des extensions d′imprimante personnalisées sont installées, votre application peut inclure des fonctionnalités d′impression qui ne sont pas décrites dans cet article.

Si vous êtes un développeur AL et que vous souhaitez savoir comment créer des extensions d’imprimante, consultez [Développement d’extensions d’imprimante dans Business Central](/dynamics365/business-central/dev-itpro/developer/devenv-reports-printing).

## <a name="next-steps"></a>Étapes suivantes

- [Configuration d’imprimantes à impression universelle](admin-printer-setup-universal-print.md)  
- [Configurer des imprimantes par courriel](admin-printer-setup-email.md)  
- [Paramétrer des imprimantes par défaut](ui-specify-printer-selection-reports.md)
